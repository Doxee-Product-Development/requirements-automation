---
id: "17a826df-136b-4bd7-bae0-093baff9456e"
title: "Current credentials"
slug: "security-configuration-guide-6-6-current-credentials-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:18.97Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-current-credentials-1"
synced_at: "2026-01-28T20:40:10.999Z"
checksum: "e89feb42a5ea8444"
---

This special type of credentials defines that the current user's credentials should be used when authenticating against another service. Doxee will automatically determine the required credentials type from the server's authentication response (or the configured preemptive scheme) and try to find matching credentials for the current user. If the user does not have credentials of the required type, no credentials are used.

`&lt;currentCredentials /&gt;`Current credentials do not specify their own authentication mechanism or user store, but can be used with any valid authentication and user store configuration described in the following chapters.

## Impersonation
By default, `&lt;currentCredentials&gt;` represents the credentials of the current user. When using impersonation (see [Impersonation](/doxee-platform/docs/security-configuration-guide-6-6-impersonation-1)), that user may be impersonated and therefore have no actual credentials (as authentication was performed with a different user). In this situation, using `&lt;currentCredentials&gt;` directly would result in missing credentials.

For these cases, `&lt;currentCredentials&gt;` supports an `impersonation` flag. Setting this flag means that the current user’s own credentials should be used, unless it is an impersonated user, in which case the authentication credentials should be used along with impersonation info for the current user:

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server ...&gt;
    &lt;currentCredentials impersonation="true" /&gt;
  &lt;/server&gt;
&lt;/credentials&gt;`If the current application accesses another service using this configuration, the behaviour depends on whether the current user A is an impersonated user:

- If the current application was accessed with credentials for user A and no impersonation, the service will also be called with A's credentials and no impersonation

- If the current application was accessed with credentials for user B impersonating user A, the service will also be called with  B's credentials and the instruction to impersonate A.

In both cases, the current user in the target application will be A.

> Caution

Keep in mind that impersonation only works with Doxee services. Authenticating this way against a 3rd party service will still use the authentication credentials, but the external service will not perform the impersonation step. Calling a 3rd party service with credentials for user B and the instruction to impersonate A will therefore cause the service to adopt B as its current user.

### authenticatedCredentials
Alternatively, if authentication against another service should use the credentials used to authenticate the current user, regardless of whether impersonation was performed or not, `&lt;authenticatedCredentials&gt;` may be used:

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server ...&gt;
    &lt;authenticatedCredentials /&gt;
  &lt;/server&gt;
&lt;/credentials&gt;`In this case, authentication will be performed normally if the current user is not impersonated (i.e. without impersonation it is equivalent to `&lt;currentCredentials&gt;`). If the current user is using impersonation, the credentials of the authenticated user will be used, without the impersonation information.

Therefore, if the current application was called with credentials for user B impersonating user A, `&lt;authenticatedCredentials&gt;` will access another service using the credentials of user B without further impersonation, making B the current user in the target service.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}