---
id: "59415349-9b09-4ed3-ba34-56fda6ba87ff"
title: "Security configuration"
slug: "composer-developer-guide-6-7-security-configuration"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Composer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-11-13T12:50:52.233Z"
modified_at: "2026-01-07T13:57:06.625Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/composer-developer-guide-6-7-security-configuration"
synced_at: "2026-01-28T20:50:32.276Z"
checksum: "b6de340436bd0669"
---

Navigate to other release versions of Doxee Platform Composer

[6.6](https://docs.doxee.com/docs/en/composer-6-6)

[6.7](https://docs.doxee.com/docs/en/composer-6-7)

By convention, the security of Doxee applications is configured in a `&lt;security&gt;` element within the application's XML configuration.

`&lt;security&gt;
  &lt;authentication xmlns="http://www.infinica.com/auth"&gt; &lt;!--1--&gt;
    &lt;!-- Authentication configuration --&gt; &lt;!--2--&gt;
  &lt;/authentication&gt;
&lt;/security&gt;`The security element uses the same namespace as the configuration which it is part of. Applications may add their own attributes and elements to this element. An application's authentication is configured via the standardised `&lt;authentication&gt;` element in the `http://www.infinica.com/auth` namespace [1] which may be contained in the security configuration. Multiple XML configuration files for different applications may share the same user access configuration via an *XInclude* element.

The authentication configuration only defines what kinds of credentials clients must use to authenticate against the server application. To validate these credentials, the server uses the user store configured in the user access configuration (see [User Access Configuration](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1#user-access-configuration)). Care must therefore be taken to use an authentication mechanism that is compatible with the chosen user store. For example, an XML use store requires password based credentials (e.g. `basic`), while an LDAP server may supported Kerberos tickets if set up accordingly.

Doxee provides a number of standard authentication modules and may be extended with custom modules. The following authentication modules are provided by a standard Doxee installation:

- Basic (user name/password authentication) for HTTP, WebDAV and SOAP

- Negotiate (using Kerberos/SPNEGO tickets) for HTTP, WebDAV and SOAP

The configuration for these modules is contained in a child element [2] of `&lt;authentication&gt;` which carries the name of the configured backend, e.g. `&lt;basic&gt;` or `&lt;negotiate&gt;`. These element typically use the same namespace as the `&lt;authentication&gt;` element, which is why the namespace declaration is emitted in the following examples.

The configuration format for these standard backends is described in the following sections.

### Basic authentication (basic)
*Basic* authentication authenticates users based on a user name and a password, using HTTP Basic credentials in HTTP, WebDAV and HTTP SOAP requests.

`&lt;basic
    realm="..." &lt;!--1--&gt;
    charset="..." /&gt; &lt;!--2--&gt;`A realm [1] and a character set [2] for the credentials may be configured. If the character set is not specified, `ISO-8859-1` is used by default.

### Negotiate authentication (negotiate)
*Negotiate* authentication uses Kerberos/SPNEGO tokens for authentication in HTTP, WebDAV and HTTP SOAP requests.

`&lt;negotiate /&gt;`A correctly configured Kerberos user access configuration is required when Negotiate authentication is used.

### OpenID authentication (openid)
*OpenID* authentication uses OpenID Connect (OIDC) bearer tokens for authentication in HTTP, WebDAV and HTTP SOAP requests. It is typically used in conjunction with an OpenID user store (see [OpenID User Store](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1#openid-user-store)).

To use OpenID authentication with n Doxee server application, Doxee must first be registered as a client at the OIDC server. This creates the necessary client ID and secret which have to be specified in the authentication configuration. To access user data without a user's credentials, a key pair has to be registered and configured as well.

`&lt;openId
    realm="..." &lt;!--1--&gt;
    scope="..."&gt; &lt;!--2--&gt;
  &lt;providerUrl&gt;...&lt;providerUrl&gt; &lt;!--3--&gt;
  &lt;redirectUrl&gt;...&lt;redirectUrl&gt; &lt;!--4--&gt;
  &lt;clientId&gt;...&lt;clientId&gt; &lt;!--5--&gt;
  &lt;clientSecret&gt;...&lt;clientSecret&gt;
  &lt;acceptRefreshTokens&gt;...&lt;acceptRefreshTokens&gt; &lt;!--6--&gt;
  &lt;keyStoreUrl&gt;...&lt;keyStoreUrl&gt; &lt;!--7--&gt;
  &lt;keyStorePassword&gt;...&lt;keyStorePassword&gt;
  &lt;keyPairAlias&gt;...&lt;keyPairAlias&gt;
  &lt;keyPairPassword&gt;...&lt;keyPairPassword&gt;
  &lt;tokenTimeout&gt;...&lt;tokenTimeout&gt; &lt;!--8--&gt;
  &lt;authorizationEndpoint&gt;...&lt;/authorizationEndpoint&gt; &lt;!--9--&gt;
  &lt;discoveryEndpoint&gt;...&lt;/discoveryEndpoint&gt;
  &lt;registrationEndpoint&gt;...&lt;/registrationEndpoint&gt;
  &lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
  &lt;userInfoEndpoint&gt;...&lt;/userInfoEndpoint&gt;
  &lt;idTokenSignatureAlg&gt;...&lt;/idTokenSignatureAlg&gt; &lt;!--10--&gt;
  &lt;validateIdTokens&gt;...&lt;/validateIdTokens&gt;
&lt;/openId&gt;``realm` [1], `scope` [2], `&lt;providerUrl&gt;` [3], `&lt;redirectUrl&gt;` [4], `&lt;clientId&gt;` [5], and `&lt;acceptRefreshTokens&gt;` [6] are communicated to the client when authentication is requested. This allows matching clients (i.e. mainly Doxee applications) to open an authentication dialogue to receive a token on behalf of the user which can then be passed on to the Doxee server application.

The configured scopes should match those specified in the user access configuration ([OpenID User Store](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1#openid-user-store)).

For interactive web applications (e.g. Workplace and Composer), the matching redirect URL for the application must be configured (please refer to each application's specific documentation for details). For Infinica Content Repository, the URL is only passed to Resource Explorer to allow it to initiate its own authentication at the OpenID provider, but the user is never redirected to the specified location. In this case, any URL registered with the OpenID client may be used (e.g. the Workplace URL, or any custom URL). All other web services (e.g. Process Engine and Task Manager) do not currently use the redirect URL. Please note that if a redirect URL is specified, it must be one of the redirect URLs registered at the OpenID provider.

`&lt;acceptRefreshTokens&gt;` [6] may be set to `true` to inform the client that it may send a refresh token (if available) along with the usual access token to allow the server to request a new access token if the one provided by the client expires. If set to `false`, clients will only send a single access token as authentication credentials.

`&lt;clientSecret&gt;` [5] is the matching secret for the client ID, as received when registering Doxee at the OIDC provider.

`&lt;keyStoreUrl&gt;`, `&lt;keyStorePassword&gt;`, `&lt;keyPairAlias&gt;` and `&lt;keyPairPassword&gt;` [7] are used to access the key pair registered along with the Doxee application at the OIDC server. These are required to access user data without the user's credentials. If no key pair password is set, the key store password is used for the key pair as well.

`&lt;tokenTimeout&gt;` [8] is the maximum age for access tokens that are forwarded to other applications before trying to refresh them, if a refresh token is available.

If the OIDC server does not support *Discovery*, the individual endpoint URLs for the operations used by Doxee must be specified manually [9].

`&lt;idTokenSignatureAlg&gt;` [10] specifies the algorithm used by the OpenID provider to sign ID tokens and defaults to `RS256`. If `&lt;validateIdTokens&gt;` is `true` (the default), ID tokens must be signed with the specified algorithm. To disable signature checking, set `&lt;validateidTokens&gt;` to `false`.

#### Salesforce authentication
When using a [Salesforce User Store](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1#salesforce-user-store), no special extension is used for authentication. Instead, standard `openId` authentication should be configured, as described above.

Based on the features provided by Salesforce, an OpenID authentication configuration for a Salesforce server will look like this:

`&lt;openId realm="..." scope="..."&gt;
  &lt;providerUrl&gt;...&lt;/providerUrl&gt;
  &lt;redirectUrl&gt;...&lt;/redirectUrl&gt;
  &lt;clientId&gt;...&lt;/clientId&gt;
  &lt;clientSecret&gt;...&lt;/clientSecret&gt;
  &lt;acceptRefreshTokens&gt;true&lt;/acceptRefreshTokens&gt;
  &lt;tokenTimeout&gt;...&lt;/tokenTimeout&gt;
  &lt;authorizationEndpoint&gt;...&lt;/authorizationEndpoint&gt;
  &lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
  &lt;userInfoEndpoint&gt;... &lt;/userInfoEndpoint&gt;
&lt;/openId&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}