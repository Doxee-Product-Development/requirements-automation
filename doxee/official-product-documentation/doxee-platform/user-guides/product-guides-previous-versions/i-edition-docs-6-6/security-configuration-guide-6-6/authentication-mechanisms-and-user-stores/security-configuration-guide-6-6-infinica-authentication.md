---
id: "829640f0-b24e-47a4-8fde-8c0ab407594e"
title: "security configuration guide 6 6 Infinica authentication"
slug: "security-configuration-guide-6-6-infinica-authentication"
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
created_at: "2025-12-04T13:59:38.228Z"
modified_at: "2025-12-05T10:35:02.541Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-infinica-authentication"
synced_at: "2026-01-28T21:05:03.418Z"
checksum: "9512964ce3713ccd"
---

*Infinica authentication* allows one Doxee application (typically a service) to access another Doxee service using technical credentials, without requiring a matching technical user to be present in the user store that contains the “regular” users. Infinica authentication is typically configured in addition to a standard authentication mechanism, e.g. together with HTTP Basic authentication. Regular users will use the normal authentication mechanism, while technical access uses Infinica credentials.

When Infinica authentication is enabled for a Doxee service, every client is assigned a key pair. A client can then access a service with an Infinica ticket signed with its own private key. The service will use the client's public key to validate and authenticate the ticket.

Optionally, services may also be assigned a key pair. Clients may then use a service's public key to encrypt a ticket and ensure that it can only be used to access this specific service (or any other service that shares the same key pair).

> Important

To use Infinica credentials, an application must also define a *key store configuration*. Please refer to the application's own documentation for specific information on configuring a key store.

This authentication type uses the `Bearer` authentication scheme, with tickets based on the JWT standard.

## Authentication Configuration
Among other things, the authentication configuration specifies the service and client keys to be used for Infinica tickets. Every Infinica tickets must always be signed by its client, and the service must be able to validate this signature with the matching public key. Optionally, a service may also be configured with its own private service key. In this case, all incoming tickets must be encrypted with the matching public key (in addition to being signed with the client's own private key).

`&lt;infinica
    service="..." &lt;!--1--&gt;
    acceptUnlistedClients="..." &lt;!--2--&gt;
    unlistedClientsKeyStore="..." &lt;!--3--&gt;
    userNamePrefix="..." &lt;!--4--&gt;
    group="..."&gt; &lt;!--5--&gt;

  &lt;groups&gt; &lt;!--6--&gt;
    &lt;group&gt;...&lt;/group&gt;
    ...
  &lt;/groups&gt;

  &lt;userGroups&gt; &lt;!--7--&gt;
    &lt;groups user="..."&gt;
      &lt;group&gt;...&lt;/group&gt;
      ...
    &lt;/groups&gt;
  &lt;/userGroups&gt;

  &lt;keys:privateKey alias="myService" /&gt; &lt;!--8--&gt;

  &lt;client ... /&gt; &lt;!--9--&gt;
  ...
&lt;/infinica&gt;`> Note

The namespace prefix `keys` references the namespace URL \[http://www.infinica.com/keystores](http://www.infinica.com/keystores).

The optional service name [1] specifies that a ticket will only be accepted if the same name is listed in its audience.

If `acceptUnlistedClients` [2] is `false`, only tickets from clients specifically listed below will be accepted. Otherwise, any client for which a public key can be found in the key store will be accepted. `unlistedCredentialsKeyStore` [3] can be used to specify a separate key store for these keys.

`userNamePrefix` [4] is a prefix that is added to all user names created from Infinica tickets (i.e. the user name will consist of this prefix and the client's name).

The `group` attribute [5] and the `&lt;groups&gt;` element [6] specify groups that will be added to all users authenticated by Infinica tickets. Additionally, `&lt;userGroups&gt;` [7] can be used to specify groups for individual user names.

`&lt;privateKey&gt;` [8] specifies an optional key for decrypting tickets. If set, clients must encrypt all tickets with the matching public key.

Any number of `&lt;client&gt;` [9] elements can be listed to define well known clients that may access this service. Depending on the `acceptUnlistedClients` setting, only these clients will be permitted access, or additionally any other clients with a matching entry in the key store as well:

`&lt;client name="client1"&gt; &lt;!--1--&gt;
  &lt;keys:publicKey alias="myKey" /&gt;
&lt;/client&gt;

&lt;client&gt; &lt;!--2--&gt;
  &lt;keys:publicKey alias="client2" /&gt;
&lt;/client&gt;`A client may define a name [1], in which case the referenced key will be used for tickets whose client name matches the name specified here.

If no name is set [2], the entry will be used for all tickets whose name matches the entry's key alias.

## Credentials
Infinica credentials can be included in a credentials registry like this:

`&lt;infinicaCredentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;client&gt; &lt;!--1--&gt;
    &lt;keys:privateKey alias="myClient" /&gt;
  &lt;/client&gt;

  &lt;service&gt; &lt;!--2--&gt;
    &lt;keys:publicKey alias="myService" /&gt;
  &lt;/service&gt;

  &lt;audienceSet&gt; &lt;!--3--&gt;
    &lt;audience&gt;...&lt;/audience&gt;
    ...
  &lt;/audienceSet&gt;

  &lt;infinicaConfig&gt; &lt;!--4--&gt;
	  &lt;client&gt;...&lt;/client&gt;
	  &lt;service&gt;...&lt;/service&gt;
	  &lt;audienceSet&gt;...&lt;/audienceSet&gt;
  &lt;/infinicaConfig&gt;
&lt;/infinicaCredentials&gt;`This specifies the private key of the client [1] and optionally the public key of the service [2]. Tickets are always signed with the client's key, and will be encrypted with the service's key if specified.

`audience` [3] specifies the audience to be used for the ticket. If a service name was configured on the service, it must be listed in the ticket's audience. If no audience is set, but a service key is used, the service key's name automatically doubles as the ticket's audience.

The credentials configuration [4] can be used to provide default values for the client and service keys and the audience. All settings not specified in the credentials themselves will be taken from the credentials configuration (if available).

> Note

A client key must always be specified (either in the credentials or in the credentials configuration). The service key must be specified if the target service is using a service key, and must be omitted otherwise.

> Tip

The audience can be used to create tickets that are accepted by multiple services. This only works if the services either use the same service key or no key at all.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}