---
id: "f49f393f-cbda-47f2-a168-61ff5fd2376c"
title: "Impersonation"
slug: "security-configuration-guide-6-6-impersonation"
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
created_at: "2025-12-04T14:00:05.117Z"
modified_at: "2025-12-05T10:40:23.883Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-impersonation"
synced_at: "2026-01-28T21:05:03.745Z"
checksum: "6f565784533c4250"
---

Impersonation is a mechanism that allows clients to access a service authenticating as one user, but telling the service to then proceed as if they had authenticated as another user, or as if the user has additional groups not reported by the user store. Among other things, this allows a service to call another service on behalf of a user while still using technical credentials for authentication, making it unnecessary to keep current credentials of the user being impersonated.

Impersonation does *not* provide its own user store or authentication mechanism, but is used in combination with a standard authentication and user store configuration.

Impersonation is only supported by Doxee services, as it relies on proprietary headers being sent along with the authentication credentials.

## Impersonating Users
Impersonating a user means that the original user A is authenticated using their provided credentials, but once authentication is successful, the service replaces user A with the impersonated user B in its authentication subject (i.e. the state where information about the authenticated user is kept) and from that point on behaves as if user B had authenticated all along. This means that the subject will contain user B and all groups to which user B belongs, but not user A nor any of user A’s groups (except those shared by user B).

A common use case for user impersonation is to access a service on behalf of a human user, but using the credentials of a technical user. The client would access the service using the technical credentials and specify the human user’s login name as the impersonated user. This requires the service to be configured to allow the technical user to impersonate all relevant human users.

## Impersonating Groups
Impersonating a group means adding that group to the authenticated subject’s “actual” groups, i.e. the groups that the authenticated user “really” belongs to (according to the user store). Note that group impersonation takes place after user impersonation, so that the “authenticated subject” may be an impersonated user.

A common use case for group impersonation is to add privileged users to a group that is permitted to impersonate the admins group. These users will not normally be able to perform admin tasks, but may impersonate the admin group to perform requests with admin permissions if necessary.

## Configuring Impersonation
By default impersonation is disabled. Services can be configured for impersonation by adding an `&lt;impersonation&gt;` entry to their `&lt;authentication&gt;` configuration (in addition to the configuration element for actual the authentication mechanism):

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
  &lt;impersonation enabled="true" /&gt;
&lt;/authentication&gt;`Without any further configuration, this enables full user and group impersonation for all users, which will constitute a security risk (at least in production environments). The `&lt;impersonation&gt;` element may therefore specify which users may impersonate which other users and/or groups:

`&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
  &lt;impersonation enabled="true"&gt;
    &lt;allow&gt; &lt;!--1--&gt;
      &lt;for&gt;*&lt;/for&gt; &lt;!--2--&gt;
      &lt;user&gt;*&lt;/user&gt; &lt;!--3--&gt;
      &lt;group&gt;*&lt;/group&gt; &lt;!--4--&gt;
    &lt;/allow&gt;
  &lt;/impersonation&gt;
&lt;/authentication&gt;`An impersonation configuration may contain any number of `&lt;allow&gt;` entries [1], and each `&lt;allow&gt;` entry can have multiple &lt;for&gt;, &lt;user&gt;, and &lt;group&gt; elements. The asterisk `*`) is used as a wildcard and matches all login names.

`&lt;for&gt;` [2] defines the login name of an authenticated user (or one of their groups) which the configuration applies to.

`&lt;user&gt;` [3] defines the login name of a user that may be impersonated, or the login name of a group whose users may be impersonated.

`&lt;group&gt;` [4] defines the login name of a group that may be impersonated as an additional group (i.e. added to the user’s actual groups). This permits impersonation of that group and all its child groups.

Once at least one `&lt;allow&gt;` element is present, only explicitly allowed impersonations are permitted. For example, if the only `&lt;allow&gt;` element permits impersonation of users only to users of a certain group, and does not contain a `&lt;group&gt;` element, then only users of that group are allowed to impersonated other users, and nobody is allowed to impersonate additional groups.

## Impersonation Headers (HTTP)
For HTTP access, impersonation is requested using the following additional headers:

- `infinica-impersonate`: Specifies the user who should be impersonated.

- `infinica-impersonate-groups`: Specifies one or more groups that should be impersonated.

These headers are sent with each HTTP request, along with the actual credentials in the standard authentication header.

## Impersonation Credentials
In a credentials registry, impersonation credentials wrap the credentials that should be used for authentication, like this:

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server host="localhost"&gt;
    &lt;impersonationCredentials user="infinica2"&gt;
      &lt;actualCredentials&gt;
        &lt;passwordCredentials name="infinica" password="theturtlemoves" /&gt;
      &lt;/actualCredentials&gt;
    &lt;/impersonationCredentials&gt;
  &lt;/server&gt;
&lt;/credentials&gt;`Alternatively, the current or authenticated user’s name can be used for impersonation by setting the `live` [1] attribute:

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server host="localhost"&gt;
    &lt;impersonationCredentials
        live="current"&gt; &lt;!--1--&gt;
      &lt;actualCredentials&gt;
        &lt;passwordCredentials name="infinica" password="theturtlemoves" /&gt;
      &lt;/actualCredentials&gt;
    &lt;/impersonationCredentials&gt;
  &lt;/server&gt;
&lt;/credentials&gt;`In this case, the user attribute (if specified) will be ignored. Possible values for this attribute are:

- `current`

- `authenticated`

These work the same way as `currentCredentials` and `authenticatedCredentials` (see [Current credentials](/doxee-platform/docs/security-configuration-guide-6-6-current-credentials)).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}