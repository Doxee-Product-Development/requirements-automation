---
id: "6af56a46-4b20-413a-a781-6c9e8e151ae8"
title: "Basic authentication"
slug: "security-configuration-guide-6-6-basic-authentication-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.035Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-basic-authentication-1"
synced_at: "2026-01-28T20:40:11.374Z"
checksum: "0fdecaa2ee2cd990"
---

Basic authentication uses credentials consisting of a login name and a password. It can be used with a variety of user stores, including Doxee's own XML and SQL user stores, and with standard LDAP servers (including Active Directory servers).

This authentication type uses the `Basic` authentication scheme.

## Authentication Configuration
The authentication configuration for Basic authentication is very simple. It specifies a *realm*, which is a name that should be the same for all services using the same sets of credentials, and optionally a charset (the default is UTF-8):

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
  &lt;basic realm="My realm" charset="UTF-8" /&gt;
&lt;/authentication&gt;`## Credentials
Basic authentication uses password credentials:

`&lt;passwordCredentials xmlns="http://www.infinica.com/credentials"
    name="..."
    password="..."&gt;
  &lt;basicConfig charset="UTF-8" /&gt;
&lt;/passwordCredentials&gt;`The default charset is `UTF-8`. Unless a different charset is required, basic credentials can therefore be used entirely without a credentials configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}