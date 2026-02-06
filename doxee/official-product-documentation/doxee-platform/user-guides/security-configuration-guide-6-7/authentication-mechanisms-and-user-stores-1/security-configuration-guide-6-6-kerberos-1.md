---
id: "9d30aca5-ac02-4e1f-995d-ce94df529c92"
title: "Kerberos"
slug: "security-configuration-guide-6-6-kerberos-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.301Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-kerberos-1"
synced_at: "2026-01-28T20:40:13.458Z"
checksum: "aa17eddb43ebf2d0"
---

Kerberos authentication can be used in combination with an LDAP user store, as an alternative to basic authentication.

It uses the `negotiate` authentication scheme to wrap Kerberos credentials in *SPNEGO tokens*. To use Kerberos authentication in a server application, an LDAP user store must be configured (see [LDAP](/doxee-platform/docs/security-configuration-guide-6-6-ldap-user-store-1)).

## Authentication Configuration
*Negotiate* authentication relies on the Kerberos settings provided by the LDAP user store configuration and does not have any configuration attributes of its own:

`&lt;negotiate /&gt;`## Credentials
Kerberos credentials are used to send a Kerberos token created for the current user.

`&lt;kerberosCredentials
    serviceName="..."&gt; &lt;!--1--&gt;
  &lt;negotiateConfig
      serviceName="..." &lt;!--1--&gt;
      lifetime="60m" /&gt; &lt;!--2--&gt;
&lt;/kerberosCredentials&gt;`Explicitly defining Kerberos credentials is only necessary if the application wants to set the service name [1]. If the service name can be determined automatically from the server URL (which normally is the case), `&lt;currentCredentials&gt;` should be used instead. The service name may be defined in the configuration, in which case it can be omitted from the `&lt;kerberosCredentials&gt;` element. Alternatively, multiple credentials using the same configuration may provide different service names.

The lifetime of created tokens can be configured with the `lifetime` attribute [2]. The default lifetime is 1 hour.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}