---
id: "7d4264e1-fcea-4cbd-a033-a5441291fc3c"
title: "Technical credentials"
slug: "security-configuration-guide-6-6-technical-credentials-1"
category: "Concepts"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Concepts"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:18.625Z"
modified_at: "2026-01-07T13:48:07.06Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-technical-credentials-1"
synced_at: "2026-01-28T20:40:10.277Z"
checksum: "0947fdff59c569b1"
---

Some services use technical credentials to access other services, i.e. credentials entirely specified by the configuration which do not depend on a current user. These credentials may have to be updated occasionally when the credentials on the server side change. Also, if they are token based, they may be used much longer than the authentication provider is configured to allow token sessions to last (e.g. credentials for technical task access are used throughout the entire runtime of the Process Engine, which may be weeks, months, or years).

To ensure that technical credentials can be updated easily, are not persisted as part of any user's data (e.g. a user's process, which may be started before the technical credentials change on the server side and continue running after they are changed), and can refresh their sessions before they time out, a  *technical credentials manager* is configured in services that require it (currently, that includes Process Engine and Workplace).

## Configuring the Technical Credentials Manager
The technical credentials manager is configured in the application's XML configuration (please refer to the respective application's Administration Guide for details):

`&lt;technicalCredentials
    cacheTimeout="..." &lt;!--1--&gt;
    maxCacheSize="...&gt; &lt;!--2--&gt;
	&lt;entry name="..."&gt; &lt;!--3--&gt;
		(credentials) &lt;!--4--&gt;
	&lt;/entry&gt;
&lt;/technicalCredentials&gt;`> Note

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or "2w".

`cacheTimeout` [1] and `maxCacheSize` [2] configure the maximum age of cached technical credentials before their session is renewed or re-created, and the maximum number of credentials to keep in the cache at any given moment.

A configuration may contain any number of entries [3]. Each entry has a name that will be used to refer to its credentials where they are actually used, and contains one actual credentials XML element as its child, just like it would be specified e.g. in a credentials registry.

> Tip

If token-based credentials are used, it is important to configure the cache timeout so that credentials that have just reached the maximum age may still be passed on to other services, i.e. their session has not yet expired and will remain valid for as long as the other service requires it. In particular, that means that the `cacheTimeout` should always be shorter than the session timeout configured at the authentication provider.

> Note

The cache remains active only as long as the application is running. When the application is restarted, all technical credentials are re-created from this configuration whenever they are used for the first time. This means that for password credentials, no cache timeout has to be configured, because they do not expire on their own, and whenever they are changed on the server, the application has to be reconfigured and restarted anyway, at which point it will use the new password credentials from the updated configuration file.

## Using Technical Credentials
Once a technical credentials manager has been configured, technical credentials may be used wherever an application expects credentials, e.g. in a credentials registry or when specifying the credentials used for technical task access by Process Engine and Workplace:

`&lt;technical xmlns="http://www.infinica.com/credentials" 
  name="..." /&gt; &lt;!--1--&gt;`> Tip

When configuring a credentials registry, the namespace of the technical credentials element is the same as that of the parent element.

The `name` attribute [1] references the name of the entry in the technical credentials manager configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}