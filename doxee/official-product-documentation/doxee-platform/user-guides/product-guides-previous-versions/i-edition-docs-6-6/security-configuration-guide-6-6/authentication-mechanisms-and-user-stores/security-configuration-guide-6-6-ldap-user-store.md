---
id: "07cba745-af33-42d4-a8d5-b3f3f6a6b72b"
title: "LDAP user store"
slug: "security-configuration-guide-6-6-ldap-user-store"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-05T10:46:39.196Z"
modified_at: "2026-01-07T13:49:21.205Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-ldap-user-store"
synced_at: "2026-01-28T21:05:01.487Z"
checksum: "94cf9996321f4db3"
---

The `ldap` backend is used to connect to an LDAP server, including Microsoft Active Directoy (AD) servers. Authentication against LDAP can be performed via basic credentials or via Kerberos tickets.

`&lt;ldap&gt;
  &lt;server&gt;ldap://localhost:389/&lt;/server&gt; &lt;!--1--&gt;

  &lt;config loginRegex=... idRegex=...&gt; &lt;!--2--&gt;
	  &lt;baseDn&gt;DC=localhost&lt;/baseDn&gt; &lt;!--3--&gt;
	  &lt;loginPattern&gt;{login}@localhost&lt;/loginPattern&gt; &lt;!--4--&gt;
	  &lt;users&gt;...&lt;/users&gt;
	  &lt;groups&gt;...&lt;/groups&gt;
  &lt;/config&gt;

  &lt;allowEmptyPasswords&gt;false&lt;/allowEmptyPasswords&gt; &lt;!--5--&gt;
  &lt;technicalUser loginName="technical" password="technical123" /&gt; &lt;!--6--&gt;

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

&lt;/ldap&gt;`The server element [1] defines the URL of the LDAP server. The port does not have to be specified if the standard LDAP port is used (389 for regular LDAP). If SSL should be used, the URL must begin with the `ldaps:` scheme and an SSL configuration must be included (see [SSL](/doxee-platform/docs/security-configuration-guide-6-6-ldap-user-store#ssl) below).

The config element [2] contains the login configurations of the LDAP server which should be accessed, depending on which principal should be used for the access. A principal can be specified using a variety of patterns (see below). The config element may be present multiple times, for example if there are potential principals which cannot be covered by one config specification. `loginRegex` and `idRegex` are optional attributes of the config element specifying regular expressions for the login and ID (typically the DN).

> Tip

When specifying more than one config element, make sure that every potential principal can be matched to at least one config specification. When an application makes a call to an LDAP server, it tries the regular expressions in sequence until a matching one is found.

The base DN [3] specifies the root of the LDAP directory tree that is used by Doxee. Only users and groups defined within this sub tree will be known to Doxee applications. Note that more specific DNs can be defined for users and groups separately (see [Users and groups](/doxee-platform/docs/security-configuration-guide-6-6-ldap-user-store#users-and-groups) below).

The login pattern [4] defines how user's login names are mapped to a login string that is understood by the LDAP server. The parameter `{login}` is replaced with the user's login name. This allows users to log in to Doxee applications with a simpler name than the one required by the LDAP server. For instance, the sample configuration above allows a user known to the LDAP server as `test@localhost` to log in to Doxee using the name `test`. Some LDAP servers may require the user's DN as the login name, in which case the above configuration might look like this:

`&lt;loginPattern&gt;sAMAccountName={login},OU=users,DC=localhost&lt;/loginPattern&gt;`> Note

Other LDAP servers may require a different login pattern, such as `domain\\{login}` or `domain/{login}`. The administrator of the LDAP server should be able to tell the exact requirement.

If `&lt;allowEmptyPasswords&gt;` [5] is set to `true`, users may log in without a password (as long as the LDAP allows them to authenticate with their user name and no password). The default is `false`, as Active Directory servers may successfully authenticate users without a password even if they have a password assigned.

`&lt;technicalUser&gt;` [6] defines the login name and password of the LDAP user that should be used for technical access, e.g. when Doxee itself needs to query the user store. If no technical user is configured, LDAP access is only possible on behalf of a currently authenticated user. Note that some Doxee applications require a technical user to perform their own queries.

## Users and Groups
Specific configuration for users and groups is defined like this:

`&lt;users&gt; &lt;!--1--&gt;
  &lt;baseDn&gt;OU=users,DC=localhost&lt;/baseDn&gt; &lt;!--2--&gt;
  &lt;objectClass&gt;person&lt;/objectClass&gt; &lt;!--3--&gt;

  &lt;attribute name="surname"&gt;sn&lt;/attribute&gt; &lt;!--4--&gt;
  ...

  &lt;modifiable&gt; &lt;!--5--&gt;
    &lt;objectClass&gt;...&lt;/objectClass&gt; &lt;!--6--&gt;
    ...
    &lt;passwordAttribute&gt;...&lt;/passwordAttribute&gt; &lt;!--7--&gt;
  &lt;/modifiable&gt;
&lt;/users&gt;

&lt;groups&gt; &lt;!--8--&gt;
  &lt;baseDn&gt;OU=groups,DC=localhost&lt;/baseDn&gt; &lt;!--2--&gt;
  &lt;objectClass&gt;groupOfUniqueNames&lt;/objectClass&gt; &lt;!--3--&gt;

  &lt;attribute name="..."&gt;...&lt;/attribute&gt; &lt;!--4--&gt;
  ...

  &lt;memberAttribute&gt;uniqueMember&lt;/memberAttribute&gt; &lt;!--9--&gt;

  &lt;modifiable&gt; &lt;!--5--&gt;
    &lt;objectClass&gt;...&lt;/objectClass&gt; &lt;!--6--&gt;
    ...
  &lt;/modifiable&gt;
&lt;/groups&gt;`Both users [1] and groups [2] may define their own base DN. In that case, that DN is used instead of the global base DN for queries applying specifically to users or groups, respectively.

An object class [3] must be specified for both users and groups to allow Doxee to determine the type of a principal. A principal is only recognised as a user or a group if it belongs to the configured object class.

Individual attribute mappings may be defined for users and groups [4]. These are similar to the global attribute mappings (see [Generic user access configuration](/doxee-platform/docs/security-configuration-guide-6-6-user-stores#generic-user-access-configuration)) but only apply to users or groups, respectively.

Groups must also specify a member attribute [9] which defines the LDAP attribute containing the references to the group's member principals.

Some Doxee applications, e.g. User management, may require write access to the LDAP server to modify users. To enable write access, a `&lt;modifiable&gt;` [5] configuration must be provided for both users and groups. This configuration defines any additional object classes [6] that should be assigned to users and groups in addition to the main object class already defined in the standard configuration [3]. For users, the password attribute [7] must be specified as well to allow Doxee to set and change a user's password.

## SSL
An SSL configuration [8] can be added to let Doxee communicate with the directory server via LDAPS instead of LDAP.

`&lt;ssl&gt;
  &lt;trustStore&gt;...&lt;/trustStore&gt; &lt;!--1--&gt;
  &lt;trustStorePassword&gt;...&lt;/trustStorePassword&gt; &lt;!--2--&gt;
&lt;/ssl&gt;`To allow Java to communicate with an SSL enabled server, a keystore with the server's certificate must be provided. `&lt;trustStore&gt;` [1] defines the path to the keystore. If a password is required to access the keystore, it must be specified as well [2].

To create a keystore, the Java `keytool` command can be used.

## Paging
Including a paging configuration may speed up principal queries by some Doxee applications because the principals are not returned as a single long list, but split into individual 'pages'.

`&lt;paging&gt;
  &lt;enabled&gt;true&lt;/enabled&gt; &lt;!--1--&gt;
  &lt;defaultSize&gt;10&lt;/defaultSize&gt; &lt;!--2--&gt;
&lt;/paging&gt;``&lt;enabled&gt;` [1] must be set to `true` to activate paging. The default number of principals per page [2] should be set as well.

## Active Flag
Doxee can distinguish between 'active' and 'inactive' principals and allow logins and certain other operations only for active users.

To determine whether an LDAP principal is considered active, an active configuration can be defined [10]. If no such configuration is provided, all principals are considered active.

`&lt;activeConfig&gt;
  &lt;activeAttribute&gt;...&lt;/activeAttribute&gt; &lt;!--1--&gt;
  &lt;activeValue&gt;...&lt;/activeValue&gt; &lt;!--2--&gt;
  &lt;inactiveValue&gt;...&lt;/inactiveValue&gt; &lt;!--3--&gt;
&lt;/activeConfig&gt;`The configuration specifies the name of the LDAP attribute containing a user's active state [1] and the value this attribute has for active [2] and inactive [3] principals. One of these attributes may be left out.

If only the inactive value [3] is specified, users with an active attribute set to any other value than this will be considered active.

## Authentication
Doxee can access an LDAP server using *simple* or *Kerberos* authentication.

If no autentication type is configured, simple authentication is used by default.

`&lt;authenticationTypes&gt;
  &lt;simple /&gt; &lt;!--1--&gt;

  &lt;kerberos &lt;!--2--&gt;
	    krb5File="krb5.conf" &lt;!--3--&gt;
	    serviceName="HTTP/infinica.localhost@LOCALHOST" &lt;!--4--&gt;
	    keyTabFile="my_service.keytab" &lt;!--5--&gt;
	    useTicketCache="false" &lt;!--6--&gt;
	    debug="true" /&gt; &lt;!--7--&gt;
&lt;/authenticationTypes&gt;`Simple authentication can be explicitly enabled using the `&lt;simple&gt;` [1] element.

Likewise, Kerberos authentication can be enabled using `&lt;kerberos&gt;` [2]. In this case, some additional parameters must be provided. `krb5File` [3] points to a Java Kerberos configuration file. When configuring an Doxee application which allows users to log in with a Kerberos ticket, `serviceName` [4] specifies the SPN of the application and `keyTabFile` [5] points to a keytab file containing the credentials of the service user. `useTicketCache` [6] allows Doxee to use the session ticket of the user running the Doxee application and should not be enabled for server applications (it is turned off by default). Setting `debug` [7] to `true` will produce additional log output when handling Kerberos tickets. This can be useful to troubleshoot a faulty Kerberos configuration.

For accessing the LDAP server with the technical user's credentials, the standard authentication method may be overwritten using the `authentication` attribute:

`&lt;technicalUser
    loginName="technical"
    password="technical123"
    authentication="simple" /&gt;`Possible values are `simple` and `kerberos`. Not specifying the attribute will use the standard authentication method.

> Tip

This setting can be useful to configure Kerberos authentication when the LDAP server itself cannot be accessed with Kerberos. In this case, `kerberos` can be configured as the general authentication type, while also specifying a technical user with `simple` authentication and setting the user store's `technicalAccess` flag to `true`.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}