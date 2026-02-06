---
id: "36fa9446-b1ef-4d86-84a9-f5d9c1739e2c"
title: "Credentials Registry"
slug: "6-6-process-engine-administration-reference-credentials-registry"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-04T10:14:46.887Z"
modified_at: "2025-08-20T18:58:09.51Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-credentials-registry"
synced_at: "2026-01-28T21:01:35.600Z"
checksum: "41c9c8cbad85b9bc"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

A credentials registry configures a Doxee Application to access certain services and servers using specific sets of credentials.

The registry can be configured to use the current credentials of the user logged into the application that accesses the service requiring credentials, or to use a set of explicitly specified credentials, e.g. a user name/password pair.

## Configuration
`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server  ①
      host="..." ②
      port="..." ③
      protocol="..." ④
      path="..." ⑤
      preemptive="..."&gt; ⑥
    &lt;!-- Credentials --&gt; ⑦
  &lt;/server&gt;
&lt;/credentials&gt;`A credentials registry can contain credentials for any number of servers [1] (or services). Each server is identified by several attributes that together are called the *credentials descriptor*. The following attributes are supported:

**host [2]**

The host name of the server. This can be a DNS name or an IP number. It must be an exact match for the host name in the URL that is used to access the server. For example, `localhost `will match URLs beginning with `http://localhost/`, but not URLs beginning with `http://127.0.0.1/`.

**port [3]**

The network port of the server.

**protocol [4]**

The protocol used to access the server, e.g. `http`.

**path [5]**

The path of the server. This must be an exact match or a parent path of the path in the URL used to access the server.

**preemptive [6]**

By default, credentials configured in a credentials registry are applied *preemptively*, i.e. they are always used in requests to their matching servers without first asking the server whether authentication is required. This improves the performance and also avoids unnecessary warning in the audit logs of accessed services. Preemptive authentication can be disabled by setting this attribute to `false`.

Each server entry may define exactly one credentials element [7]. Credentials may provide their own credentials configuration. If they do not, a separate credentials configuration registry may be set up (see [Credentials Configuration Registry](/doxee-platform/docs/6-6-process-engine-administration-reference-credentials-registry#credentials-configuration-registry)).

### URL Patterns
Instead of specifying the host, port, protocol, and path of a service, a credential descriptor may specify a URL pattern:

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  &lt;server
      url="..."
      preemptive="..."&gt;
    &lt;!-- Credentials --&gt;
  &lt;/server&gt;
&lt;/credentials&gt;`In this case, the attributes are taken from the URL. The asterisk character (*) may be used as as a wildcard to mark arbitrary parts of the URL.

Example URL patterns are:

- `http://localhost:8080/infinica-content-repository/`

Host: `localhost`

Port: `8080`

Protocol: `http`

Path: `/infinica-content-repository/`

- `http://localhost/`

Host: `localhost`

Port: (any)

Protocol: `http`

Path: (any)

- `*://*:8080/`

Host: (any)

Port: `8080`

Protocol: (any)

Path: (any)

## Credentials Lookup
When a Doxee application with a credentials registry accesses a service via a URL, the credentials registry is queried for the server entry that provides the closest match for the service URL.

To find entries in a registry, a given URL is checked against these attributes in the following order:

- Host

- Port

- Protocol

- Path

If any of these attributes of an entry do not match the given URL, no credentials are taken from that entry. All matching entries (i.e. entries where all specified attributes match the URL) are ranked, and the best matching entry is used to provide credentials.

If an attribute is an exact match, it gets full points. If it is not specified by the registry entry (i.e. the entry is valid for all values for that attribute), it matches, but gets zero points. Paths (if specified) must match exactly, or the registry’s path must be a parent path of the given URLs. Multiple path matches are ranked by longest match.

If multiple entries match different attributes of the given URL, the best match according to the order listed above and the points is used for resolution. E.g. if entry 1 matches the port, protocol, and exact path, but does not specify a host, and entry 2 matches the host, but does not specify any other attributes, entry 2 wins, because the host match is the first in the list.

## Preemptive Credentials
Normally, credentials are looked up preemptively, i.e. before first accessing the server. If a server is listed in the credentials registry, but preemptive authentication is explicitly disabled in its entry, access will first be attempted without credentials. If the server responds with an authentication error, the application will then re-try the request with the credentials from the registry. In this case, whatever additional authentication information the server may have provided with the error response may be used by the application for the credentials configuration.

## Credentials Configuration Registry
In addition to a credentials registry, a credentials configuration registry may be specified.

When a credentials entry does not specify its own configuration, and the entry is used preemptively or the server’s authentication error response did not provide enough data, a matching entry from the credentials configuration registry is used, if available. The registry may contain one credentials configuration entry for each supported type of credentials.

If a credentials entry has neither its own configuration nor a matching entry in a credentials configuration registry, but is of the same type as the application’s own authentication mechanism, the application will try to automatically create a configuration based on its own authentication settings. This may not be possible for some credentials types that require additional settings. Please refer to the separate Security Configuration Guide for more information about the available credential types.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}