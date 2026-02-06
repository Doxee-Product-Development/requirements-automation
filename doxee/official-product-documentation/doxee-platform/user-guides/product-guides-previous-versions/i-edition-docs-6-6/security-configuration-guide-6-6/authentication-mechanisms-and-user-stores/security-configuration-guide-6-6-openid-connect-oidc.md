---
id: "253248bc-b446-40c0-a8d7-1edcc1e3c39a"
title: "OpenID Connect (OIDC)"
slug: "security-configuration-guide-6-6-openid-connect-oidc"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 3
public_version: 3
created_at: "2025-12-04T13:58:20.17Z"
modified_at: "2025-12-05T13:55:22.61Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-openid-connect-oidc"
synced_at: "2026-01-28T21:05:02.124Z"
checksum: "2db59d30b6ed0f98"
---

OpenID Connect is an authentication standard built on top of OAuth and is Doxee's default way of supporting OAuth.

This authentication type uses the `Bearer` authentication scheme.

## Registering the OIDC Clients
Before configuring Doxee to use OIDC for authentication and user access, your OIDC provider must first be configured to allow Doxee to access the necessary information.

Doxee uses two separate OAuth clients for its server and rich client applications. The servers use their OAuth clients to receive and provide OAuth tokens and to gather information about users and groups. The clients use a separate OAuth client to provide a login dialogue for users and to generate OAuth tokens for accessing the server applications.

### OIDC Client for Doxee Servers
Doxee's server applications require an OIDC client to be able to authenticate user tokens and access user information. *Interactive web applications* (Workplace, Business Designer) can also use the authorization code flow to display a login form to users. *Backend services* (Content Repository, Process Engine, Task Manager) can only be accessed if the client already provides a valid access token.

The OIDC client for server applications must be registered manually at the OIDC provider. Please refer to your OIDC provider's documentation for details on how to do this. The following settings are required by Doxee:

Option

Value

Name

Doxee Server *(recommended)*

Application type

Web

Redirect URLs

*(see below)*

Response types

Code, ID Token, Token

Grant types

Authorization Code, Refresh Token, JWT Bearer

Required scopes

openid, profile, offline *(and see below)*

The *redirect URLs* depends on the Doxee server applications that will be used. Backend services do not show login dialogs and therefore do not actually use a redirect URL. For these services, an arbitrary URL may be configured, but note that OIDC providers have certain requirements (e.g. the URLs must be HTTPS URLs according to the specification). A simple solution is to use the main URL of the application as a redirect URL.

Interactive web applications, on the other hand, require a specific URL to be configured. Please refer to the following table to find the required redirect URL(s). The *server* in each URL must be replaced with the actual server (and port, if non-standard). For backend services, an example URL is listed.

Application

Redirect URL

Content Repository

*(arbitrary)* \[https://server/infinica-content-repository/](https://server/infinica-content-repository/)

Process Engine

*(arbitrary)* \[https://server/infinica-process-engine/](https://server/infinica-process-engine/)

Task Manager

*(arbitrary)* \[https://server/infinica-task-manager/](https://server/infinica-task-manager/)

Workplace

\https://&lt;host&gt;/workplace/login.hbs

Business Designer

\https://&lt;host&gt;/tdwng/login

Composer

\https://&lt;host&gt;/infinica-composer/login

The *required scopes* may depend on any additional user information Doxee should be able to access, e.g. from a process. If your OIDC provider can supply the names of a user's groups in a claim, it may also be necessary to add the corresponding scope here.

#### Configuring JWT Flow
JWT flow is required to allow Doxee to authenticate without an interactive user context, which is required for technical background lookups. To enable JWT flow, a key pair has to be created and its private key uploaded to the OIDC provider.

##### Creating the Key Pair
The `openssl` and Java's `keypair` command line tools can be used to create a key pair. The referenced key store path can be set as required. If it does not reference an existing key store, a new one will be created automatically.

`# Generate private/public keypair
openssl req -newkey rsa:2048 -nodes -keyout private_key.pem -x509 -days 365 -out certificate.pem

# Write certificate in binary file (some systems need binary format)
openssl x509 -outform der -in certificate.pem -out public_key.der

# Get the public key from the certificate
openssl x509 -in certificate.pem -pubkey &gt; public_key.pem

# import certificate into Java Key Store (JKS)
# !!! Be sure to trust the certificate - otherwise it is not imported
keytool -importcert -file certificate.pem -keystore keystore_oidc.jks -alias oidcCertificate -storetype jks

# Create a PKCS12 keystore with private/public keypair
openssl pkcs12 -inkey private_key.pem -in certificate.pem -export -out keystore.p12 -name oidcKey

# Import keypair into Java keystore
keytool -importkeystore -destkeystore keystore_oidc.jks -srckeystore keystore.p12 -srcstoretype pkcs12 -destalias oidcKey -srcalias oidcKey

# Create .csr file
openssl req -new -key private_key.pem -out server.csr

# Use .csr file to create necessary .crt file
openssl x509 -req -sha256 -days 365 -in server.csr -signkey private_key.pem -out server.crt`In the above code, `keystore_oidc.jks` is the path to the key store that will contain the newly created key pair under the alias `oidcKey`. The file `server.crt` will be uploaded to OIDC provider in the following step. All other generated files may be deleted.

##### Activating JWT Flow
To active JWT in OIDC, the `server.crt` file must be uploaded to the OIDC provider as the certificate or private key to be used for JWT flow authentication. Please refer to your OIDC provider's documentation for details on how to configure JWT flow.

### OIDC Client for Doxee Rich Clients
Doxee's rich client applications require another OIDC client. This OIDCclient is used only to allow the client applications to display a login dialog to the user so they can request a token from the OIDC provider on the user's behalf and use it to access the Infincia server applications.

Registration can either be done manually or, if your OIDC provider supports it, automatically via Resource Explorer. In either case, some information about the registered client will be stored in a file named `auth.properties`. This file must then be copied to the working directory of all Template Designer, Process Designer, and Resource Explorer installations that should use OIDC authentication.

#### Self Registration via Resource Explorer
If the OIDC provider allows self registration and you have the *master access token* required to register new clients, you can call Resource Explorer from the command line to automatically register an OIDC client (named `Doxee Design Tools`):

`java -jar resource-explorer.jar --registerOidc _providerUrl_ _masterAccessToken_``providerUrl` must be the main endpoint URL of your OIDC provider, and `masterAccessToken` the master access token.

After the client has been registered, the tool will output a list of properties that can be used to configure the Doxee client applications in their respective authentication configuration dialogues.

#### Manual Registration
Alternative, the OIDC client can be registered manually. The following settings should be configured for the client:

Option

Value

Name

Doxee Design Tools *(recommended)*

Application type

Native

Redirect URL

\[http://localhost/infinica/auth](http://localhost/infinica/auth)

Response types

Code

Grant types

Authorization Code, Refresh Token

Token endpoint authentication method

None

It is recommended that this client should be registered as a *public client*, i.e. not have a client secret.

## OIDC Configuration XML
This configuration contains all the settings Doxee needs to access the OIDC provider. As it is used by both the authentication and the user access configurations, it is recommended to store it in a separate file and use XIncludes to reference it from those configuration settings, as shown in the subsequent sub sections.

`&lt;config xmlns="http://www.infinica.com/openid"&gt;
  &lt;providerUrl&gt;...&lt;/providerUrl&gt; &lt;!--1--&gt;

  &lt;clientId&gt;...&lt;/clientId&gt; &lt;!--2--&gt;
  &lt;clientSecret&gt;...&lt;/clientSecret&gt;

  &lt;keyStoreUrl&gt;...&lt;/keyStoreUrl&gt; &lt;!--3--&gt;
  &lt;keyStorePassword&gt;...&lt;/keyStorePassword&gt;
  &lt;keyPairAlias&gt;...&lt;/keyPairAlias&gt;
  &lt;keyPairPassword&gt;...&lt;/keyPairPassword&gt; &lt;!--4--&gt;  

  &lt;tokenTimeout&gt;...&lt;/tokenTimeout&gt; &lt;!--5--&gt;
  &lt;accessTokenIssuer&gt;...&lt;/accessTokenIssuer&gt; &lt;!--6--&gt;
&lt;/config&gt;``providerUrl` [1] specifies the main endpoint URL of your OIDC provider. If the provider supports endpoint discovery, this is the only endpoint URL you have to configure (otherwise, see below).

The client ID and secret [2] are those of the OIDC client you configured for Doxee servers.

The key store configuration [3] is required for JWT authentication. It defines the URL of a Java keystore file that contains the key pair used for JWT access (see [Configuring JWT Flow](/doxee-platform/docs/security-configuration-guide-6-6-openid-connect-oidc#configuring-jwt-flow)). The key store password specifies the password required to access this file. Key pair alias is the alias of the key pair in the key store. A key pair password [4] is only required if it differs from the key store password.

> Note

The OpenID module does not yet use the generic key store configuration supported by most Doxee applications. The key store information must therefore be set directly in the OIDC configuration elements.

`&lt;tokenTimeout&gt;` [5] can be used to configure the time after which Doxee tries to automatically refresh an existing OIDC token to prevent it from expiring.

`&lt;accessTokenIssuer&gt;` [6] can be used to override the default issuer that is expected when validating access tokens.

### Optional Configuration
The following additional options may be configured:

`&lt;idTokenSignatureAlg&gt;RS256&lt;/idTokenSignatureAlg&gt; &lt;!--1--&gt;
&lt;validateIdTokens&gt;...&lt;/validateIdTokens&gt; &lt;!--2--&gt;
&lt;jwsAlgorithm&gt;...&lt;/jwsAlgorithm&gt; &lt;!--3--&gt;``idTokenSignatureAlg` [1] specifies the algorithm the OIDC provider should use to sign ID tokens. It defaults to `RS256`.

`validateIdTokens` [2] is a boolean value which specifies whether Doxee should validate ID tokens and reject them if they are invalid. It defaults to `true`.

`jwsAlgorithm` [3] specifies the algorithm used to sign JWT tokens (for JWT authentication). It defaults to `RS256`.

### Endpoint Configuration
Endpoint details may also be configured individually, although this should only be necessary for OIDC providers which do not support the discovery endpoint:

`&lt;endpoints&gt;
  &lt;discoveryEndpoint&gt;..&lt;/discoveryEndpoint&gt;
  &lt;authorizatonEndpoint&gt;..&lt;/authorizatonEndpoint&gt;
  &lt;tokenEndpoint&gt;..&lt;/tokenEndpoint&gt;
  &lt;userInfoEndpoint&gt;..&lt;/userInfoEndpoint&gt;
  &lt;jwksUri&gt;...&lt;/jwksUri&gt;
  &lt;issuer&gt;...&lt;/issuer&gt;
  &lt;registrationEndpoint&gt;...&lt;/registrationEndpoint&gt;
&lt;/endpoints&gt;`If the OIDC provider supports discovery but uses a non-standard discovery endpoint URL, specifying only the discovery URL should be sufficient.

### JWT Flow Audience
By default, the audience for JWT flow tokens is constructed automatically based on the provider URL. If the default audience does not work with a given OIDC provider, it can be configured manually:

`&lt;jwtFlowAudience&gt;
  &lt;audience&gt;...&lt;/audience&gt;
  ...
&lt;/jwtFlowAudience&gt;`Any number of audience strings may be configured.

## Authentication Configuration
Once the basic OIDC configuration is finished, the standard Doxee authentication configuration can be created:

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
  &lt;openId
      scope="..." &gt; &lt;!--1--&gt;
    &lt;xi:include href="openid.xml" parse="xml" /&gt; &lt;!--2--&gt;
    &lt;redirectUrl&gt;...&lt;/redirectUrl&gt; &lt;!--3--&gt;
  &lt;/openId&gt;
&lt;/authentication&gt;`The scope [1] lists the scopes required by the application, separated by commas. A typical scope configuration is:

`openid, profile, offline`This allows the application to use your authentication `openid`), access your user information `profile`), and continue using your token even after you have logged out `offline`). The offline scope can be removed, in which case any use of your token will fail if the application still tries to use your credentials after you have logged out of your OIDC provider.

The scopes configured here are used by Doxee when authenticating a user, or when informing a server informs a client application which scopes it requires.

The OIDC specific configuration is collected in a separate element [2]. This configuration is described above ([OIDC configuration XML](/doxee-platform/docs/security-configuration-guide-6-6-openid-connect-oidc#oidc-configuration-xml)).

The redirect URL [3] is required for applications that let the user authenticate interactively (e.g. Workplace and Business Designer; but not in backend services like Content Repository, Process Engine, and Task Manager). It must point back to the authentication URL defined by the application, as listed in [OIDC client for Doxee servers](/doxee-platform/docs/security-configuration-guide-6-6-openid-connect-oidc#oidc-client-for-doxee-servers).

## Credentials
OIDC uses `openIdCredentials`:

`&lt;openIdCredentials xmlns="http://www.infinica.com/credentials"
    userId="..." &lt;!--1--&gt;
    password="..."&gt; &lt;!--2--&gt;
  &lt;tokens&gt; &lt;!--3--&gt;
    &lt;accessToken&gt;...&lt;/accessToken&gt;
    &lt;refreshToken&gt;...&lt;/refreshToken&gt;
    &lt;idToken&gt;...&lt;/idToken&gt;
  &lt;/tokens&gt;
  &lt;openIdConfig&gt; &lt;!--4--&gt;
    &lt;xi:include href="openid.xml" parse="xml" /&gt;
  &lt;/openIdConfig&gt;
&lt;/openIdCredentials&gt;`OIDC credentials can be specified in a number of different ways, also depending on which authentication flows the chosen OIDC provider supports:

Authentication flow

Description

Tokens

If already existing tokens should be used, they can be specified with the `&lt;tokens&gt;` element [3]. Usually, this would include an  access token and/or a refresh token. If tokens are specified in this way, care should be taken to ensure that they are still valid when the application uses them.

JWT Grant

If the provider supports JWT authentication, a user ID [1] can be specified to generate a matching access token. The configuration must provide the necessary settings, including key store information.

Resource Owner Password Grant

If the provider supports the resource owner password flow, a user ID [1] and password [2] can be specified to generate a matching access token.

The credentials configuration [4] must contain the same OIDC settings as the authentication configuration described above. It is recommended to store it in an external file and reference this file from both the authentication configuration and the credentials configuration.

Since OAuth tokens have a limited lifetime, these tokens may expire if they are used for a longer time than the token lifetime configured in the OIDC provider, especially when used by long running processes or as technical tokens, e.g. for Process Engine's technical Task Manager access credentials, which are re-used as long as the application is running. In these cases, the credentials should be used with a  technical credentials manager (see [Technical credentials](/doxee-platform/docs/security-configuration-guide-6-6-technical-credentials)).

## User Store Configuration
The OIDC user store configuration, like the authentication configuration described above, uses the OIDC configuration. It is therefore included from an external file via an XInclude statement [1] in the following XML snippet:

`&lt;userStore&gt;
  &lt;openId&gt;
    &lt;xi:include href="openid.xml" parse="xml" /&gt; &lt;!--1--&gt;

    &lt;technicalUser&gt; &lt;!--2--&gt;
      &lt;userId&gt;...&lt;/userId&gt;
    &lt;/technicalUser&gt;

    &lt;scopes&gt; &lt;!--3--&gt;
      &lt;scope&gt;openid&lt;/scope&gt;
      &lt;scope&gt;profile&lt;/scope&gt;
    &lt;/scopes&gt;

    &lt;groupsClaim&gt;...&lt;/groupsClaim&gt;
  &lt;/openId&gt;
&lt;/userStore&gt;`A technical user should also be configured [2], by specifying the login name of an OIDC user which may be used for looking up user and group information at the OIDC provider. This user must be able to authenticate via JWT token (see [Registering the OIDC clients](/doxee-platform/docs/security-configuration-guide-6-6-openid-connect-oidc#registering-the-oidc-clients)).

The configured scopes [3] define which information should be fetched when Doxee reads users from the OIDC provider, i.e. which user attributes are available to Doxee. At least the `openid` and `profile` scopes should be specified here. To ensure that these scopes are available to Doxee, the scopes listed here should always be a subset of the scopes configured in the authentication configuration, as described above (any scope listed here but not in the authentication configuration may cause the OIDC provider to reject Doxee's user queries).

OIDC does not specify a standard mechanism to receive information about a user's groups, but some providers offer a list of groups in a separate claim. The name of this claim may be configured in `groupsClaim` [4] to allow Doxee to resolve user groups. An additional scope may be required in the scopes configuration to retrieve the configured claim. If no groups claim is configured, Doxee will not be able to resolve a user's groups.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}