---
id: "f7c24222-fc59-4be7-9c63-cfae5395f932"
title: "User stores"
slug: "security-configuration-guide-6-6-user-stores-1"
category: "Concepts"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Concepts"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:18.466Z"
modified_at: "2026-01-07T13:48:07.06Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-user-stores-1"
synced_at: "2026-01-28T20:40:09.262Z"
checksum: "1f5da8f3713155a1"
---

The *user access configuration* defines the access to the user store, i.e. where Doxee fetches information about *principals* (users and groups). The choice of user store is closely tied to the choice of authentication mechanism, as specific user stores only work with specific mechanisms. For example, the OpenID authentication mechanism requires an OpenID user store. However, some mechanisms support multiple user stores, and some user stores support multiple authentication mechanisms: Basic authentication may be used with the XML, SQL, and LDAP user stores, while the LDAP user store may alternatively also use Kerberos authentication.

## Generic User Access Configuration
`&lt;userAccessConfiguration xmlns="http://www.infinica.com/useraccess"&gt; &lt;!--1--&gt;
  &lt;cache ... /&gt; &lt;!--2--&gt;
  &lt;userStore&gt;
    &lt;!-- User store configuration --&gt; &lt;!--3--&gt;
  &lt;/userStore&gt;
&lt;/userAccessConfiguration&gt;`The `&lt;userAccessConfiguration&gt;` element has a standard namespace of `http://www.infinica.com/useraccess` [1].

The optional `&lt;cache&gt;` element [2] can be set either globally or inside the user store to configure the cache behaviour. It is described below.

`&lt;userStore&gt;` contains an element that is specific to the user store type it describes. Which user stores are available may depend on the installed modules of the application being configured. Please refer to the second section of this documentation (Authentication mechanisms and user stores) for a complete list and detailed description of the available user stores.

> Note

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or "2w".

All user stores support the configuration of *attribute mappings*. These can be used to map attribute names from the user store to different names in the Doxee application.

`&lt;userStore&gt;
  &lt;backendName&gt; &lt;!--1--&gt;
    &lt;attribute name="...&gt;...&lt;/attribute&gt; &lt;!--2--&gt;
  &lt;/backendName&gt;
&lt;/userStore&gt;`> Note

In a real configuration, the user store configuration element [1] will be named according to the used backend, e.g. `&lt;xml&gt;` or `&lt;ldap&gt;`.

The `&lt;attribute&gt;` element [2] may be specified any number of times. Each attribute element defines a mapping for one attribute. The element content is the name of the attribute in the user store, while `name` specifies the name under which this attribute should be seen by the Doxee application.

The following common attributes are required by Doxee and should always be configured:

Attribute

Description

`loginName`

The name a user specifies to log in to Doxee. This attribute must be unique for each principal.

`displayName`

The attribute that Doxee may use to display the name of a principal.

Additional custom attributes may be specified as well.

For example, the following mapping can be used in an LDAP configuration to map an Active Directory's account name and common name attributes to the `loginName` and `displayName` attributes:

`&lt;attribute name="loginName"&gt;sAMAccountName&lt;/attribute&gt;
&lt;attribute name="displayName"&gt;cn&lt;/attribute&gt;`### Technical Access
For user store types that use authentication, a technical user may be configured to access the user store on behalf of the Doxee system without a specific user's credentials (please see the individual user store types for concrete information on how to configure the technical user).

Some environments may not allow regular users to access the user store. In this case, user access can be configured to always access the user store using the technical user, even if the access is carried out on behalf of an actual user:

`&lt;userStore technicalAccess="true"&gt;
...`### Caching
The cache configuration can be set globally or per user store. Each user store inherits the cache settings it does not have explicitly configured from the global configuration. Where the global configuration is not set, default values are used.

`&lt;cache
    enabled="true"&gt; &lt;!--1--&gt;
  &lt;maximumSize&gt;...&lt;/maximumSize&gt; &lt;!--2--&gt;
  &lt;expiry&gt;...&lt;/expiry&gt; &lt;!--3--&gt;
&lt;/cache&gt;``enabled` [1] can be used to activate or deactivate caching. `maximumSize` [2] defines the maximum number of cache entries, while `expiry` [3] sets the duration (in milliseconds, if no unit is specified) for which entries are held in the cache.

The cache settings are used per user that accesses the user store. If the same user (i.e. the same credentials) is used to access the user store multiple times, the same cache is used each time. If a different user accesses the user store, a separate cache is used.

Caching is enabled by default, with a maximum size of 1000 entries and an expiration time of 10 minutes.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}