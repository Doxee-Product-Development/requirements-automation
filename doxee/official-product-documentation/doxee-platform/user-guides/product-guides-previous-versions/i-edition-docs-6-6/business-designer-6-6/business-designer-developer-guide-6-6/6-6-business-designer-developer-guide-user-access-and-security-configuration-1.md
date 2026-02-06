---
id: "1bcae4b4-8ee6-46f9-b4e7-91fee2fba2ec"
title: "User Access and Security Configuration"
slug: "6-6-business-designer-developer-guide-user-access-and-security-configuration-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Business Designer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-13T16:03:08.685Z"
modified_at: "2026-01-07T13:52:34.606Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-business-designer-developer-guide-user-access-and-security-configuration-1"
synced_at: "2026-01-28T21:00:29.808Z"
checksum: "16b77784e15c340f"
---

Navigate to other release versions of Doxee Platform Business Designer

[6.6](https://docs.doxee.com/docs/en/business-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/business-designer-6-7)

## User Access Configuration
The `&lt;userAccessConfiguration&gt;` element has a standard namespace of [http://www.infinica.com/useraccess ](http://www.infinica.com/useraccess)[1]. This allows multiple XML configuration files for different applications to share the same user access configuration.

`&lt;userAccessConfiguration  xmlns="http://www.infinica.com/useraccess"&gt;  ①
&lt;cache ... /&gt; ②
&lt;userStore&gt;
&lt;cache ... /&gt; ②
&lt;!-- User store configuration --&gt; ③
&lt;/userStore&gt;
&lt;/userAccessConfiguration&gt;`The optional `&lt;cache&gt;` element [2] can be set either globally or inside the user store to configure the cache behaviour. It is described below.

`&lt;userStore&gt;` contains an element that is specific to the user store type it describes. Which user stores are available may depend on the installed modules of the application being configured. The following user stores are supported in a standard Doxee setup:

- database

- ldap

- xml

- openId

The configuration for these modules is contained in a child element [3] of `&lt;userStore&gt;` which carries the name of the configured backend, e.g. `&lt;ldap&gt;` or `&lt;xml&gt;`. These element typically use the same namespace as the `&lt;userAccessConfiguration&gt;` element, which is why the namespace declaration is emitted in the following examples.

The configuration format for these standard backends is described in the following sections.

> Tip

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units,

e.g. "10s", "5m", "2h", "1d" or "2w".

### Generic user store configuration
All user stores support the configuration of *attribute mappings*. These can be used to map attribute names from the user store to different names in the Doxee application.

`&lt;userStore&gt;
&lt;backendName&gt; ①
&lt;attribute  name="...&gt;...&lt;/attribute&gt;  ②
&lt;/backendName&gt;
&lt;/userStore&gt;`> Note

In a real configuration, the user store configuration element [1] be named according to the used backend, e.g. `&lt;xml&gt;` or `&lt;ldap&gt;`.

The `&lt;attribute&gt;` element [2] may be specified any number of times. Each attribute element defines a mapping for one attribute. The element content is the name of the attribute in the user store, while name specifies the name under which this attribute should be seen by the Doxee application.

The following common attributes are required by Doxee and should always be configured:

`loginName`

The name a user specifies to log in to Doxee. This attribute must be unique for each principal.

`displayName`

The attribute that Doxee may use to display the name of a principal.

Additional custom attributes may be specified as well.

For example, the following mapping can be used in an LDAP configuration to map an Active Directory’s account name and common name attributes to the `loginName` and `displayName` attributes:

`&lt;attribute  name="loginName"&gt;sAMAccountName&lt;/attribute&gt;
&lt;attribute name="displayName"&gt;cn&lt;/attribute&gt;`#### Technical Access
For user store types that use authentication, a technical user may be configured to access the user store on behalf of the Doxee system without a specific user’s credentials (please see the individual user store types for concrete information on how to configure the technical user).

Some environments may not allow regular users to access the user store. In this case, user access can be configured to always access the user store using the technical user, even if the access is carried out on behalf of an actual user:

`&lt;userStore technicalAccess="true"&gt;
...`#### Caching
The cache configuration can be set globally or per user store. Each user store inherits the cache settings it does not have explicitly configured from the global configuration. Where the global configuration is not set, default values are used.

`&lt;cache
enabled="true" ① 
maximumSize="" ② expiry="" /&gt;    ③``enabled`[1] can be used to activate or deactivate caching. `maximumSize` [2] defines the maximum number of cache entries, while `expiry` [3] sets the duration (in milliseconds, if no unit is specified) for which entries are held in the cache.

The cache settings are used per user that accesses the user store. If the same user (i.e. the same credentials) is used multiple to access the user store multiple times, the same cache is used each time. If a different user accesses the user store, a separate cache is used.

Caching is enabled by default, with a maximum size of 1000 entries and an expiration time of 10 minutes.

### Database user store (database)
The `database` backends keeps its principals in an SQL database. The database is created automatically if it does not yet exist on the server. The User Management application can be used to administrate the users and groups stored in the database.

`&lt;database&gt;
&lt;connection&gt;  ①
...
&lt;/connection&gt;
&lt;attribute  name="..."&gt;...&lt;/attribute&gt;  ②
&lt;users&gt;  ③
&lt;attribute name="..."&gt;...&lt;/attribute&gt;
...
&lt;passwordAttribute&gt;...&lt;/passwordAttribute&gt; ④
&lt;/users&gt;
&lt;groups&gt; ⑤
&lt;attribute name="..."&gt;...&lt;/attribute&gt;
&lt;/groups&gt;
&lt;/database&gt;`The database connection is configured in the `&lt;connection&gt;` element [1] using Java Hibernate properties. A typical configuration looks like this:

`&lt;connection&gt;
&lt;hibernate.connection.url&gt;...&lt;/hibernate.connection.url&gt;
&lt;hibernate.connection.driver_class&gt;...&lt;/hibernate.connection.driver_class&gt;
&lt;hibernate.connection.username&gt;...&lt;/hibernate.connection.username&gt;
&lt;hibernate.connection.password&gt;...&lt;/hibernate.connection.password&gt;
&lt;hibernate.dialect&gt;...&lt;/hibernate.dialect&gt;
&lt;/connection&gt;`Like any user store configuration, attribute mappings for all principals may be configured using `&lt;attribute&gt;` elements [2].

Specific configurations may be defined for users [3] and groups [5]. For both of these, attribute mappings may be defined which are only used for the corresponding principal type. Additionally, the attribute which stores a user’s password must be defined [4].

### LDAP user store (ldap)
The `ldap` backend is used to connect to an LDAP server, including Microsoft Active Directoy (AD) servers. Authentication against LDAP can performed via username/password credentials or via Kerberos tickets.

`&lt;ldap&gt;
&lt;server&gt;ldap://localhost:389/&lt;/server&gt;  ①
&lt;baseDn&gt;DC=localhost&lt;/baseDn&gt;  ②
&lt;loginPattern&gt;{login}@localhost&lt;/loginPattern&gt; ③
&lt;allowEmptyPasswords&gt;false&lt;/allowEmptyPasswords&gt; ④
&lt;technicalUser  loginName="technical"  password="technical123"  /&gt;  ⑤
&lt;users&gt;
...
&lt;/users&gt;
&lt;groups&gt;
...
&lt;/groups&gt;
&lt;ssl&gt;
...
&lt;/ssl&gt;
&lt;paging&gt;
...
&lt;/paging&gt;
&lt;activeConfig&gt;
...
&lt;/activeConfig&gt;
&lt;authenticationTypes&gt;
...
&lt;/authenticationTypes&gt;
&lt;/ldap&gt;`The server element [1] defines the URL of the LDAP server. The port does not have to be specified if the standard LDAP port is used (389 for regular LDAP). If SSL should be used, the URL must begin with the `ldaps:` scheme and an SSL configuration must be included (see [SSL](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#ssl) below).

The base DN [2] specifies the root of the LDAP directory tree that is used by Doxee. Only users and groups defined within this sub tree will be known to Doxee applications. Note that more specific DNs can be defined for users and groups separately (see [Users and Groups](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#users-and-groups) below).

The login pattern [3] defines how user’s login names are mapped to a login string that is understood by the LDAP server. The parameter {login} is replaced with the user’s login name. This allows users to log in to Doxee applications with a simpler name than the one required by the LDAP server. For instance, the sample configuration above allows a user known to the LDAP server as test@localhost to log in to Doxee using the name test. Some LDAP servers may require the user’s DN as the login name, in which case the above configuration might look like this:

`&lt;loginPattern&gt;sAMAccountName={login},OU=users,DC=localhost&lt;/loginPattern&gt;`> Note

Other LDAP servers may require a different login pattern, such as `domain\{login}` or `domain/{login}`. The administrator of the LDAP server should be able to tell the exact requirement.

If `&lt;allowEmptyPasswords&gt;` [4] is set to `true`, users may log in without a password (as long as the LDAP allows them to authenticate with their user name and no password). The default is `false`, as Active Directory servers may successfully authenticate users without a password even if they have a password assigned.

`&lt;technicalUser&gt;` [5] defines the login name and password of the LDAP user that should be used for technical access, e.g. when Doxee itself needs to query the user store. If no technical user is configured, LDAP access is only possible in the name of the logged in user. Note that some Doxee applications to require a technical user to perform their own queries.

#### Users and Groups
Specific configuration for users and groups is defined like this:

`&lt;users&gt;  ①
&lt;baseDn&gt;OU=users,DC=localhost&lt;/baseDn&gt;  ②
&lt;objectClass&gt;person&lt;/objectClass&gt;  ③
&lt;attribute  name="surname"&gt;sn&lt;/attribute&gt;  ④
...
&lt;modifiable&gt;  ⑤
&lt;objectClass&gt;...&lt;/objectClass&gt;  ⑥
...
&lt;passwordAttribute&gt;...&lt;/passwordAttribute&gt; ⑦
&lt;/modifiable&gt;
&lt;/users&gt;
&lt;groups&gt; ⑧
&lt;baseDn&gt;OU=groups,DC=localhost&lt;/baseDn&gt;  ②
&lt;objectClass&gt;groupOfUniqueNames&lt;/objectClass&gt; ③
&lt;attribute  name="..."&gt;...&lt;/attribute&gt;  ④
...
&lt;memberAttribute&gt;uniqueMember&lt;/memberAttribute&gt; ⑨
&lt;modifiable&gt;  ⑤
&lt;objectClass&gt;...&lt;/objectClass&gt;  ⑥
...
&lt;/modifiable&gt;
&lt;/groups&gt;`Both users [1] and groups [2] may define their own base DN. In that case, that DN is used instead of the global base DN for queries applying specifically to users or groups, respectively.

An object class [3] must be specified for both users and groups to allow Doxee to determine the type of a principal. A principal is only recognised as a user or a group if it belongs to the configured object class.

Individual attribute mappings may be defined for users and groups [4]. These are similar to the global attribute mappings (see [Generic user store configuration](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#generic-user-store-configuration)) but only apply to users or groups, respectively.

Groups must also specify a member attribute [9] which defines the LDAP attribute containing the references to the group’s member principals.

Some Doxee applications, e.g. User Management, may require write access to the LDAP server to modify users. To enable write access, a &lt;modifiable&gt; [5] configuration must be provided for both users and groups. This configuration defines any additional object classes

[6] that should be assigned to users and groups in addition to the main object class already defined in the standard configuration [3]. For users, the password attribute [7] must be specified as well to allow Doxee to set and change a user’s password.

#### SSL
An SSL configuration [8] can be added to let Doxee communicate with the directory server via LDAPS instead of LDAP.

`&lt;ssl&gt;
&lt;trustStore&gt;...&lt;/trustStore&gt;  ①
&lt;trustStorePassword&gt;...&lt;/trustStorePassword&gt;  ②
&lt;/ssl&gt;`To allow Java to communicate with an SSL enabled server, a keystore with the server’s certificate must be provided. `&lt;trustStore&gt;` [1] defines the path to the keystore. If a password is required to access the keystore, it must be specified as well [2].

To create a keystore, the Java `keytool` command can be used.

#### Paging
Including a paging configuration may speed up principal queries by some Doxee applications because the principals are not returned as a single long list, but split into individual 'pages'.

`&lt;paging&gt;
&lt;enabled&gt;true&lt;/enabled&gt;  ①
&lt;defaultSize&gt;10&lt;/defaultSize&gt;  ②
&lt;/paging&gt;``&lt;enabled&gt;` [1] must be set to `true` to activate paging. The default number of principals per page [2] should be set as well.

#### Active Flag
Doxee can distinguish between 'active' and 'inactive' principals and allow logins and certain other operations only for active users.

To determine whether an LDAP principal is considered active, an active configuration can be defined [10]. If no such configuration is provided, all principals are considered active.

`&lt;activeConfig&gt;
&lt;activeAttribute&gt;...&lt;/activeAttribute&gt; ①
&lt;activeValue&gt;...&lt;/activeValue&gt;  ②
&lt;inactiveValue&gt;...&lt;/inactiveValue&gt; ③
&lt;/activeConfig&gt;`The configuration specifies the name of the LDAP attribute containing a user’s active state [1] and the value this attribute has for active [2] and inactive [3] principals. One of these attributes may be left out.

If only the inactive value [3] is specified, users with an active attribute set to any other value than this will be considered active.

#### Authentication
Doxee can access an LDAP server using *simple *or *Kerberos *authentication. If no autentication type is configured, simple authentication is used by default.

Simple authentication can be explicitly enabled using the `&lt;simple&gt;` [1] element.

`&lt;authenticationTypes&gt;
&lt;simple /&gt; ①
&lt;kerberos  ②
krb5File="krb5.conf" ③ serviceName="HTTP/infinica.localhost@LOCALHOST" ④ keyTabFile="my_service.keytab" ⑤ useTicketCache="false" ⑥
debug="true" /&gt; ⑦
&lt;/authenticationTypes&gt;`Likewise, Kerberos authentication can be enabled using `&lt;kerberos&gt;` [2]. In this case, some additional parameters must be provided. `krb5File` [3] points to a Java Kerberos configuration file. When configuring a Doxee application which allows users to log in with a Kerberos ticket, `serviceName` [4] specifies the SPN of the application and `keyTabFile` [5] points to a keytab file containing the credentials of the service user. `useTicketCache`[6] allows Doxee to use the session ticket of the user running the Doxee application and should not be enabled for server applications (it is turned off by default). Setting `debug` [7] to `true` will produce additional log output when handling Kerberos tickets. This can be useful to troubleshoot a faulty Kerberos configuration.

For accessing the LDAP server with the technical user’s credentials, the standard authentication method may be overwritten using the `authentication` attribute:

`&lt;technicalUser 
loginName="technical" 
password="technical123" 
authentication="simple" /&gt;`Possible values are `simple` and `kerberos`. Not specifying the attribute will use the standard authentication method.

> Tip

This setting can be useful to configure Kerberos authentication when the LDAP server itself cannot be accessed with `Kerberos`. In this case, kerberos can be configured as the general authentication type, while also specifying a technical user with `simple` authentication and setting the user store’s `technicalAccess` flag to `true`.

### XML user store (xml)
The xml backend provides a very simple file based user store. Principals are defined in an XML file and read from there during startup.

`&lt;xml&gt;
&lt;source&gt;users.xml&lt;/source&gt;  ①
&lt;/xml&gt;`The only configuration option is the &lt;source&gt; element [1] which defines the relative URL to the XML file containing the principals.

The principals file looks like this:

`&lt;principals xmlns="http://www.infinica.com/"&gt;
&lt;user ①
id="user1" ② loginName="user1" ③ displayName="..." ④ password="..." ⑤
attr1="..."  ⑥
attr2="...&gt;
&lt;group&gt;group1&lt;/group&gt;  ⑦
...
&lt;/user&gt;
...
&lt;group ⑧
id="group1"&gt;
&lt;group&gt;group2&lt;/group&gt;
...
&lt;/group&gt;
&lt;group id="group2" /&gt; ⑨
...
&lt;/principals&gt;`Any number of `&lt;user&gt;` [1] and `&lt;group&gt;` [8] elements may be specified to define the principals.

Each principal can have attributes. Standard attributes include the ID [2], a login name [3], a display name [4] and (only relevant for users) a password [5]. Arbitrary custom attributes may be specified as well [6].

Each user and group can be assigned as a member of another group by including a `&lt;group&gt;` element containing the ID of the parent group [8].

In the above example, the user `user` [1] is a member of the group `group1`[8], which in turn is a member of the group `group2` [9].

If a principal does not define a login name, its ID doubles as its login name. If a principal does not define a display name, its login name is used as the display name.

### OpenID User Store
The OpenID user store gets user data from an OpenID Connect (OIDC) server and tokens provided by the accessing users. It can only be used correctly in conjunction with the OpenID authentication module (see [OpenID authentication (openid)](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#openid-authentication-openid)).

`&lt;openId&gt;
&lt;url&gt;...&lt;/url&gt;  ①
&lt;clientId&gt;...&lt;/clientId&gt; ②
&lt;clientSecret&gt;...&lt;/clientSecret&gt;
&lt;technicalUser&gt;  ③
&lt;userId&gt;...&lt;/userId&gt;
&lt;/technicalUser&gt;
&lt;scopes&gt; ④
&lt;scope&gt;openid&lt;/scope&gt;
&lt;scope&gt;profile&lt;/scope&gt;
...
&lt;/scopes&gt;
&lt;groupsClaim&gt;...&lt;/groupsClaim&gt;  ⑤
&lt;keyStoreUrl&gt;...&lt;/keyStoreUrl&gt; ⑥
&lt;keyStorePassword&gt;...&lt;/keyStorePassword&gt;
&lt;keyPairAlias&gt;...&lt;/keyPairAlias&gt;
&lt;keyPairPassword&gt;...&lt;/keyPairPassword&gt;
&lt;authorizationEndpoint&gt;...&lt;/authorizationEndpoint&gt; ⑦
&lt;discoveryEndpoint&gt;...&lt;/discoveryEndpoint&gt;
&lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
&lt;userInfoEndpoint&gt;...&lt;/userInfoEndpoint&gt;
&lt;idTokenSignatureAlg&gt;...&lt;/idTokenSignatureAlg&gt;  ⑧
&lt;validateIdTokens&gt;...&lt;/validateIdTokens&gt;
&lt;accessTokenSignatureAlg&gt;...&lt;/accessTokenSignatureAlg&gt;  ⑨
&lt;accessTokenType&gt;...&lt;/accessTokenType&gt;
&lt;/openId&gt;``&lt;clientId&gt;` and `&lt;clientSecret&gt;` [2] are the ID and secret received when registering Doxee as an application at the OIDC provider.

`technicalUser` [3] configures the name of a technical user. Some Doxee applications uses this user to access other services in a context where they do not have the credentials of an interactive user on whose behalf the access is performed. As the JWT authentication flow is used to generate an access token for the technical user, this also requires a key pair (see item

6) to be configured.

`&lt;scopes&gt;` [4] lists the OIDC scopes Doxee requests when accessing user data. If groupsClaim [5] is specified, it denotes a claim which contains the names of groups to which a user belongs. Without a groups claim, Doxee cannot access a user’s groups.

`&lt;keyStoreUrl&gt;`, `&lt;keyStorePassword&gt;`, `&lt;keyPairAlias&gt;` and `&lt;keyPairPassword&gt;`[6] are used to access the key pair registered along with the Doxee application at the OIDC server. These are required to access user data without the user’s credentials. If no key pair password is set, the key store password is used for the key pair as well.

If the OIDC server does not support *Discovery*, the individual endpoint URLs for the operations used by Doxee must be specified manually [7]. In this case, `&lt;discoveryEndpoint&gt;` is obsolete and does not have to be specified.

`&lt;idTokenSignatureAlg&gt;` [8] specifies the algorithm used by the OpenID provider to sign ID tokens and defaults to `RS256`. If `&lt;validateIdTokens&gt;` is true (the default), ID tokens must be signed with the specified algorithm. To disable signature checking, set &lt;validateidTokens&gt; to `false`.

Similarly, `&lt;accsesTokenSignatureAlg&gt;` [9] specifies the algorithm used to sign access tokens. By default, none is set (since not all providers sign their access tokens). Enable access token validation by specifying the provider’s signature algorithm here. Additionally, the access token type can be checked as well by setting `&lt;accessTokenType&gt;` to the matching type, e.g. `at+jwt. &lt;url&gt;` [1] specifies the URL of the OIDC provider.

### Salesforce User Store
The Salesforce user store is an extension of the generic OpenID user store. It is able to authenticate users against Salesforce and fetch their user data and public groups via Salesforce’s REST API.

As this chapter only describes the Salesforce-specific parts of the configuration, please also refer to [OpenID User Store](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#openid-user-store) for more information.

There Salesforce-specific element &lt;restQueryEndpoint&gt; [1] must be set to the sObject query endpoint URL, e.g.:

`&lt;salesforce&gt;
&lt;url&gt;...&lt;/url&gt;
&lt;clientId&gt;...&lt;/clientId&gt;
&lt;clientSecret&gt;...&lt;/clientSecret&gt;
&lt;technicalUser&gt;
&lt;userId&gt;...&lt;/userId&gt;
&lt;/technicalUser&gt;
&lt;scopes&gt;
&lt;scope&gt;openid&lt;/scope&gt;
&lt;scope&gt;profile&lt;/scope&gt;
...
&lt;/scopes&gt;
&lt;authorizationEndpoint&gt;...&lt;/authorizationEndpoint&gt;
&lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
&lt;userInfoEndpoint&gt;...&lt;/userInfoEndpoint&gt;
&lt;restQueryEndpoint&gt;...&lt;/restQueryEndpoint&gt;  ①
&lt;/salesforce&gt;````
https://&lt;your-organization-specific&gt;/services/data/&lt;version&gt;/query
```Also note that the scopes configured here must also be listed in Salesforce’s configuration under *Manage Connected Apps*.

## Security Configuration
By convention, the security of Doxee applications is configured in a &lt;security&gt; element within the application’s XML configuration.

`&lt;security&gt;
&lt;authentication xmlns="http://www.infinica.com/auth"&gt; ①
&lt;!-- Authentication configuration --&gt; ②
&lt;/authentication&gt;
&lt;/security&gt;`The security element uses the same namespace as the configuration which it is part of. Applications may add their own attributes and elements to this element. An application’s authentication is configured via the standardised `&lt;authentication&gt;` element in the [http://www.infinica.com/auth ](http://www.infinica.com/auth)namespace [1] which may be contained in the security configuration. Multiple XML configuration files for different applications may share the same user access configuration via an *XInclude *element.

The authentication configuration only defines what kinds of credentials clients must use to authenticate against the server application. To validate these credentials, the server uses the user store configured in the user access configuration (see [User Access Configuration](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#user-access-configuration)). Care must therefore be taken to use an authentication mechanism that is compatible with the chosen user store. For example, an XML use store requires password based credentials (e.g. `basic`), while an LDAP server may supported Kerberos tickets if set up accordingly.

Doxee provides a number of standard authentication modules and may be extended with custom modules. The following authentication modules are provided by a standard Doxee installation:

- Basic (user name/password authentication) for HTTP, WebDAV and SOAP

- Negotiate (using Kerberos/SPNEGO tickets) for HTTP, WebDAV and SOAP

The configuration for these modules is contained in a child element [2] of `&lt;authentication&gt;` which carries the name of the configured backend, e.g. `&lt;basic&gt;` or `&lt;negotiate&gt;`. These element typically use the same namespace as the `&lt;authentication&gt;` element, which is why the namespace declaration is emitted in the following examples.

The configuration format for these standard backends is described in the following sections.

### Basic authentication (basic)
*Basic *authentication authenticates users based on a user name and a password, using HTTP Basic credentials in HTTP, WebDAV and HTTP SOAP requests.

A realm [1] and a character set [2] for the credentials may be configured. If the character set is not specified, ISO-8859-1 is used by default.

`&lt;basic
realm="..."  ①
charset="..."  /&gt;  ②`### Negotiate authentication (negotiate)
*Negotiate *authentication uses Kerberos/SPNEGO tokens for authentication in HTTP, WebDAV and HTTP SOAP requests.

`&lt;negotiate /&gt;`A correctly configured Kerberos user access configuration is required when Negotiate authentication is used.

### OpenID authentication (openid)
*OpenID *authentication uses OpenID Connect (OIDC) bearer tokens for authentication in HTTP, WebDAV and HTTP SOAP requests. It is typically used in conjunction with an OpenID user store (see [OpenID User Store](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#openid-user-store)).

To use OpenID authentication with n Doxee server application, Doxee must first be registered as a client at the OIDC server. This creates the necessary client ID and secret which have to be specified in the authentication configuration. To access user data without a user’s credentials, a key pair has to be registered and configured as well.

`&lt;openId
realm="..."  ①
scope="..."&gt;  ②
&lt;providerUrl&gt;...&lt;providerUrl&gt;  ③
&lt;redirectUrl&gt;...&lt;redirectUrl&gt;  ④
&lt;clientId&gt;...&lt;clientId&gt;  ⑤
&lt;clientSecret&gt;...&lt;clientSecret&gt;
&lt;acceptRefreshTokens&gt;...&lt;acceptRefreshTokens&gt; ⑥
&lt;keyStoreUrl&gt;...&lt;keyStoreUrl&gt;  ⑦
&lt;keyStorePassword&gt;...&lt;keyStorePassword&gt;
&lt;keyPairAlias&gt;...&lt;keyPairAlias&gt;
&lt;keyPairPassword&gt;...&lt;keyPairPassword&gt;
&lt;tokenTimeout&gt;...&lt;tokenTimeout&gt;  ⑧
&lt;authorizationEndpoint&gt;...&lt;/authorizationEndpoint&gt; ⑨
&lt;discoveryEndpoint&gt;...&lt;/discoveryEndpoint&gt;
&lt;registrationEndpoint&gt;...&lt;/registrationEndpoint&gt;
&lt;tokenEndpoint&gt;...&lt;/tokenEndpoint&gt;
&lt;userInfoEndpoint&gt;...&lt;/userInfoEndpoint&gt;
&lt;idTokenSignatureAlg&gt;...&lt;/idTokenSignatureAlg&gt;  ⑩
&lt;validateIdTokens&gt;...&lt;/validateIdTokens&gt;
&lt;/openId&gt;``realm` [1], `scope` [2], `&lt;providerUrl&gt;` [3], `&lt;redirectUrl&gt;` [4], `&lt;clientId&gt;` [5], and `&lt;acceptRefreshTokens&gt;` [6] are communicated to the client when authentication is requested. This allows matching clients (i.e. mainly Doxee applications) to open an authentication dialogue to receive a token on behalf of the user which can then be passed on to the Doxee server application.

The configured scopes should match those specified in the user access configuration ([OpenID User Store](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#openid-user-store)).

For interactive web applications (e.g. Workplace and Composer), the matching redirect URL for the application must be configured (please refer to each application’s specific documentation for details). For Infinica Content Repository, the URL is only passed to Resource Explorer to allow it to initiate its own authentication at the OpenID provider, but the user is never redirected to the specified location. In this case, any URL registered with the OpenID client may be used (e.g. the Workplace URL, or any custom URL). All other web services (e.g. Process Engine and Task Manager) do not currently use the redirect URL. Please note that if a redirect URL is specified, it must be one of the redirect URLs registered at the OpenID provider.

`&lt;acceptRefreshTokens&gt;` [6] may be set to `true` to inform the client that it may send a refresh token (if available) along with the usual access token to allow the server to request a new access token if the one provided by the client expires. If set to `false`, clients will only send a single access token as authentication credentials.

`&lt;clientSecret&gt;` [5] is the matching secret for the client ID, as received when registering Doxee at the OIDC provider. 

`&lt;keyStoreUrl&gt;`, `&lt;keyStorePassword&gt;`, `&lt;keyPairAlias&gt;` and `&lt;keyPairPassword&gt;`[7] are used to access the key pair registered along with the Doxee application at the OIDC server. These are required to access user data without the user’s credentials. If no key pair password is set, the key store password is used for the key pair as well.

`&lt;tokenTimeout&gt;` [8] is the maximum age for access tokens that are forwarded to other applications before trying to refresh them, if a refresh token is available.

If the OIDC server does not support *Discovery*, the individual endpoint URLs for the operations used by Doxee must be specified manually [9].

`&lt;idTokenSignatureAlg&gt;` [10] specifies the algorithm used by the OpenID provider to sign ID tokens and defaults to `RS256`. If `&lt;validateIdTokens&gt;` is true (the default), ID tokens must be signed with the specified algorithm. To disable signature checking, set `&lt;validateidTokens&gt;` to `false`.

#### Salesforce authentication
When using a [Salesforce User Store](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1#salesforce-user-store), no special extension is used for authentication. Instead, standard `openId` authentication should be configured, as described above.

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
&lt;userInfoEndpoint&gt;...  &lt;/userInfoEndpoint&gt;
&lt;/openId&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}