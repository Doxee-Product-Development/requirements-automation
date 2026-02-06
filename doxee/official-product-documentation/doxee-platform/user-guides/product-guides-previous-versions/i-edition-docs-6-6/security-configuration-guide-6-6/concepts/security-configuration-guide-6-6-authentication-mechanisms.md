---
id: "2c70881d-c5cf-4f13-a8a7-de6150c7281b"
title: "Authentication mechanisms"
slug: "security-configuration-guide-6-6-authentication-mechanisms"
category: "Concepts"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Security configuration"
  - "Concepts"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T13:52:24.693Z"
modified_at: "2025-12-05T11:13:53.47Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-authentication-mechanisms"
synced_at: "2026-01-28T21:04:58.629Z"
checksum: "6067d2940b523208"
---

Doxee supports a number of different authentication mechanisms, including password-based *Basic* authentication and token-based *Kerberos* and *OAuth/OpenID* authentication. Additionally, a custom *Infinica* authentication mechanism is intended to be used for technical service access, alongside a second (standard) authentication mechanism for human users. All of the supported authentication mechanisms are described in the second section of this documentation (Authentication mechanisms and user stores).

On the server side, an authentication mechanism has to be chosen and configured to allow users to access the service. On the client side, the server's chosen authentication mechanism determines which *credentials* have to be used. This chapter deals with the server side configuration of authentication. Client side credentials are described in [Client credentials](/doxee-platform/docs/security-configuration-guide-6-6-client-credentials) and [Technical credentials](/doxee-platform/docs/security-configuration-guide-6-6-technical-credentials).

> Note

Note that a service may well also act as a client if it accesses another service.

## Generic Authentication Configuration
Authentication is configured with the `&lt;authentication&gt;` element, which is usually placed in the service configuration's `&lt;security&gt;` element (but please refer to each specific service's administration guide for details):

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt; &lt;!--1--&gt;
  &lt;!-- Authentication configuration --&gt; &lt;!--2--&gt;
&lt;/authentication&gt;`The authentication element has its own namespace [1]. The element should contain one or more authentication configuration elements [2]. These elements depend on the chosen authentication mechanisms and are described individually and in detail in the second section of this documentation. Note that most authentication mechanisms don't necessarily work well together (especially not if they use different user stores), so it is generally recommended not to mix them and instead to decide on one single authentication mechanism for a service. The one exception to this rule is Doxee's own authentication mechanism for technical access ([Infinica authentication](/doxee-platform/docs/security-configuration-guide-6-6-infinica-authentication)), which is designed to work in parallel with any other chosen mechanism.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}