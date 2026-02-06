---
id: "bf6860d7-2987-48ad-a0bb-e3793dd8322d"
title: "Salesforce OAuth"
slug: "security-configuration-guide-6-6-salesforce-oauth-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.482Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-salesforce-oauth-1"
synced_at: "2026-01-28T20:40:14.785Z"
checksum: "6de3b7fd33a70e82"
---

Salesforce uses an OAuth implementation which is in most respects similar to the OIDC mechanism described in the previous chapter, but differs in a few areas. Additionally, it has its own API for looking up users and groups, and has fixed patterns for its endpoint URLs, which makes the standard configuration values quite different.

## Registering the Salesforce Apps
Before configuring Doxee to use Salesforce for authentication and user access, Salesforce must first be configured to allow Doxee to access the necessary information.

Doxee uses two separate OAuth clients for its server and rich client applications. The servers use their OAuth clients to receive and provide OAuth tokens and to gather information about users and groups. The clients use a separate OAuth client to provide a login dialogue for users and to generate OAuth tokens for accessing the server applications.

In Salesforce, these OAuth clients are called *connected apps*.

### Server App
The server app is the connected app which should be configured in all Doxee server applications. It allows Doxee to accept Salesforce OAuth tokens for authentication, to access user and group information via the Salesforce API, and (in the case of interactive web applications) to redirect users to Salesforce's login page for authentication.

The recommended name for this app is `Doxee Servers`.

#### Basic Settings
The following settings are required for the app:

- *Enable OAuth Settings* must be activated.

- The following OAuth scopes should be selected:

*Access your basic information (id, profile, email, address, phone)*

- *Access and manager your data (api)*

- *Perform requests on your behalf at any time (refresh*token, offline_access)_

- *Allow access to your unique identifier (openid)*

- The following callback URLs should be set:

`\https://&lt;host&gt;/infinica-workplace/login.hbs` (if using Workplace)

- `\https://&lt;host&gt;/infinica-business-designer/login` (if using Business Designer)

- *Require Secret for Web Server Flow* should be activated.

#### Configuring JWT Flow
JWT flow is required to allow Doxee to authenticate without an interactive user context, which is required for technical background lookups. To enable JWT flow, a key pair has to be created and its private key uploaded to Salesforce.

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
keytool -importcert -file certificate.pem -keystore keystore_salesforce.jks -alias salesforceCertificate -storetype jks

# Create a PKCS12 keystore with private/public keypair
openssl pkcs12 -inkey private_key.pem -in certificate.pem -export -out keystore.p12 -name salesforceKey

# Import keypair into Java keystore
keytool -importkeystore -destkeystore keystore_salesforce.jks -srckeystore keystore.p12 -srcstoretype pkcs12 -destalias salesforceKey -srcalias salesforceKey

# Create .csr file
openssl req -new -key private_key.pem -out server.csr

# Use .csr file to create necessary .crt file
openssl x509 -req -sha256 -days 365 -in server.csr -signkey private_key.pem -out server.crt`In the above code, `keystore_salesforce.jks` is the path to the key store that will contain the newly created key pair under the alias `salesforceKey`. The file `server.crt` will be uploaded to Salesforce in the following step. All other generated files may be deleted.

##### Activating JWT Flow
The following steps are used to activate JWT flow in Salesforce's OAuth settings:

- *Use digital signatures* must be activated

- The file `server.crt` must be uploaded as the new digital signature

To allow users to authenticate via JWT, the connected app's policies must be changed by performing the following steps:

- Click *Manage* and then *Edit Policies* on the app.

- Set *Permitted Users* to *Admin approved users are pre-authorized*.

- Save the settings.

- Back on the management page, you can now click *Manage Profiles* to specify the profiles of users who may access the app. All users who should be able to authenticate via Doxee, including technical users, must belong to one of the listed profiles.

### Client App
Doxee's rich client applications require another connected app. This app is used only to allow the client applications to display a login dialog to the user so they can request a token from Salesforce on the user's behalf and use it to access the Infincia server applications.

The recommended name for this app is `Doxee Design Tools`.

The following settings are required for the app:

- *Enable OAuth Settings* must be activated.

- The following OAuth scopes should be selected:

*Access your basic information (id, profile, email, address, phone)*

- *Access and manager your data (api)*

- *Perform requests on your behalf at any time (refresh*token, offline_access)_

- *Allow access to your unique identifier (openid)*

- The following callback URL must be set:

`\http://localhost/infinica/auth`

- *Require Secret for Web Server Flow should be *deactivated (otherwise, the client secret will have to be included in the configuration files on all client machines).

## Salesforce Configuration XML
This configuration contains all the settings Doxee needs to access Salesforce. As is used by both the authentication and the user access configurations, it is recommended to store it in a separate file and use XIncludes to reference it from those configuration settings, as shown in the subsequent sub sections.

`&lt;salesforceConfig xmlns="http://www.infinica.com/salesforce"&gt;
  &lt;salesforceInstance&gt;login&lt;/salesforceInstance&gt; &lt;!--1--&gt;
  &lt;organizationInstance&gt;...&lt;/organizationInstance&gt; &lt;!--2--&gt;

  &lt;clientId&gt;...&lt;/clientId&gt; &lt;!--3--&gt;
  &lt;clientSecret&gt;...&lt;/clientSecret&gt;

  &lt;keyStoreUrl&gt;...&lt;/keyStoreUrl&gt; &lt;!--4--&gt;
  &lt;keyStorePassword&gt;...&lt;/keyStorePassword&gt;
  &lt;keyPairAlias&gt;...&lt;/keyPairAlias&gt;
  &lt;keyPairPassword&gt;...&lt;keyPairPassword&gt; &lt;!--5--&gt;

  &lt;tokenTimeout&gt;...&lt;/tokenTimeout&gt; &lt;!--6--&gt;
  &lt;apiKeepAliveTimeout&gt;...&lt;/apiKeepAliveTimeout&gt; &lt;!--7--&gt;
  &lt;accessTokenIssuer&gt;...&lt;/accessTokenIssuer&gt; &lt;!--8--&gt;
&lt;/salesforceConfig&gt;`The configured Salesforce [1] and organization [2] instances depend on your specific Salesforce setup. The Salesforce instance is used for all standard OAuth endpoints, while the organization instance is used to access the Salesforce API when performing user and group queries.

The client ID and secret [3] are the *consumer key* and *consumer secret *of your registered *server app* (see [Registering the Salesforce Apps](/doxee-platform/docs/security-configuration-guide-6-6-salesforce-oauth-1#registering-the-salesforce-apps)).

The key store configuration [4] is required for JWT authentication. It defines the URL of a Java keystore file that contains the key pair used for JWT access (see [Configuring the JWT Flow](/doxee-platform/docs/security-configuration-guide-6-6-salesforce-oauth-1#configuring-jwt-flow)). The key store password specifies the password required to access this file. Key pair alias is the alias of the key pair in the key store. A key pair password [5] is only required if it differs from the key store password.

> Note

The Salesforce module does not yet use the generic key store configuration supported by most Doxee applications. The key store information must therefore be set directly in the Salesforce configuration elements.

`&lt;tokenTimeout&gt;` [6] can be used to configure the time after which Doxee tries to automatically refresh an existing Salesforce token to prevent it from expiring.

`&lt;apiKeepAliveTimeout&gt;` [7] can be set to change the timeout of HTTP connections to the Salesforce API used to query group information. This can be useful if connections to the Salesforce API are unstable with the default settings.

`&lt;accessTokenIssuer&gt;` [8] can be used to override the default issuer that is expected when validating access tokens.

### Optional Configuration
Instead of configuring a Salesforce and organization instance, the full URLs to access Salesforce's OAuth endpoints and API may be specified instead:

`&lt;salesforceInstanceUrl&gt;...&lt;/salesforceInstanceUrl&gt;
&lt;organizationInstanceUrl&gt;...&lt;.organizationInstanceUrl&gt;`### Endpoint Configuration
Endpoint details may also be configured individually, although this should not be necessary, as Doxee automatically uses the standard settings officially provided by Salesforce:

`&lt;endpoints&gt;
  &lt;discoveryEndpoint&gt;...&lt;/discoveryEndpoint&gt;
  &lt;authorizatonEndpoint&gt;...&lt;/authorizatonEndpoint&gt;
  &lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
  &lt;userInfoEndpoint&gt;...&lt;/userInfoEndpoint&gt;
  &lt;jwksUri&gt;...&lt;/jwksUri&gt;
  &lt;issuer&gt;...&lt;/issuer&gt;
  &lt;restQueryEndpoint&gt;...&lt;/restQueryEndpoint&gt;
&lt;/endpoints&gt;`### JWT Flow Audience
By default, the audience for JWT flow tokens is constructed automatically based on the provider URL. If the default audience does not work with a given Salesforce setup, it can be configured manually:

`&lt;jwtFlowAudience&gt;
  &lt;audience&gt;...&lt;/audience&gt;
  ...
&lt;/jwtFlowAudience&gt;`## Authentication Configuration
Once the basic Salesforce configuration is finished, the standard Doxee authentication configuration can be created:

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
  &lt;salesforce
      scope="..." &gt; &lt;!--1--&gt;
    &lt;xi:include href="salesforce.xml" parse="xml" /&gt; &lt;!--2--&gt;
    &lt;redirectUrl&gt;...&lt;/redirectUrl&gt; &lt;!--3--&gt;
  &lt;/salesforce&gt;
&lt;/authentication&gt;`The scope [1] lists the scopes required by the application, separated by commas. A typical scope configuration is:

`openid, profile, offline`This allows the application to use your authentication `openid`), access your user information `profile`), and continue using your token even after you have logged out `offline`). The offline scope can be removed, in which case any use of your token will fail if the application still tries to use your credentials after you have logged out of Salesforce.

The scopes configured here are used by Doxee when authenticating a user, or when informing a server informs a client application which scopes it requires.

The Salesforce specific configuration is collected in a separate element [2]. This configuration is described above ([Salesforce configuration XML](/doxee-platform/docs/security-configuration-guide-6-6-salesforce-oauth-1#salesforce-configuration-xml)).

The redirect URL [3] is required for applications that let the user authenticate interactively (e.g. Workplace and Business Designer; but not in backend services like Content Repository, Process Engine, and Task Manager). It must point back to the authentication URL defined by the application, as listed in [OIDC client for Doxee servers](/doxee-platform/docs/security-configuration-guide-6-6-openid-connect-oidc-1#oidc-client-for-doxee-servers).

## Credentials
Salesforce uses `salesforceCredentials`:

`&lt;salesforceCredentials xmlns="http://www.infinica.com/credentials"
    userId="..." &lt;!--1--&gt;
  &lt;tokens&gt; &lt;!--2--&gt;
    &lt;accessToken&gt;...&lt;/accessToken&gt;
    &lt;refreshToken&gt;...&lt;/refreshToken&gt;
    &lt;idToken&gt;...&lt;/idToken&gt;
  &lt;/tokens&gt;
  &lt;salesforceConfig&gt; &lt;!--3--&gt;
    &lt;xi:include href="salesforce.xml" parse="xml" /&gt;
  &lt;/salesforceConfig&gt;
&lt;/salesforceCredentials&gt;`Salesforce credentials can be specified in a number of different ways:

Authentication flow

Description

Tokens

If already existing tokens should be used, they can be specified with the `&lt;tokens&gt;` element [2]. Usually, this would include an  access token and/or a refresh token. If tokens are specified in this way, care should be taken to ensure that they are still valid when the application uses them.

JWT Grant

If JWT authentication should be used, a user ID [1] can be specified to generate a matching access token. The configuration must provide the necessary settings, including key store information.

The credentials configuration [3] must contain the same Salesforce settings as the authentication configuration described above. It is recommended to store it in an external file and reference this file from both the authentication configuration and the credentials configuration.

Since Salesforce tokens have a limited lifetime, these tokens may expire if they are used for a longer time than the token lifetime configured in Salesforce, especially when used by long running processes or as technical tokens, e.g. for Process Engine's technical Task Manager access credentials, which are re-used as long as the application is running. In these cases, the credentials should be used with a technical credentials manager (see [Technical credentials](/doxee-platform/docs/security-configuration-guide-6-6-technical-credentials-1)).

## User Store Configuration
The Salesforce user store configuration, like the authentication configuration described above, uses the Salesforce configuration. It is therefore included from an external file via an XInclude statement [1] in the following XML snippet:

`&lt;userStore&gt;
  &lt;salesforce&gt;
    &lt;xi:include href="salesforce.xml" parse="xml" /&gt; &lt;!--1--&gt;

    &lt;technicalUser&gt; &lt;!--2--&gt;
      &lt;userId&gt;infa@infinica.com&lt;/userId&gt;
    &lt;/technicalUser&gt;

    &lt;scopes&gt; &lt;!--3--&gt;
      &lt;scope&gt;openid&lt;/scope&gt;
      &lt;scope&gt;profile&lt;/scope&gt;
    &lt;/scopes&gt;
  &lt;/salesforce&gt;
&lt;/userStore&gt;`A technical user should also be configured [2], by specifying the user ID (i.e. email address) of a Salesforce user which may be used for looking up user and group information in Salesforce. This user must be able to authenticate via JWT token (see [Registering the Salesforce Apps](/doxee-platform/docs/security-configuration-guide-6-6-salesforce-oauth-1#registering-the-salesforce-apps)).

The configured scopes [3] define which information should be fetched when Doxee reads users and groups from Salesforce, i.e. which user attributes are available to Doxee. At least the `openid` and `profile` scopes should be specified here. To ensure that these scopes are available to Doxee, the scopes listed here should always be a subset of the scopes configured in the authentication configuration, as described above (any scope listed here but not in the authentication configuration may cause Salesforce to reject Doxee's user queries).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}