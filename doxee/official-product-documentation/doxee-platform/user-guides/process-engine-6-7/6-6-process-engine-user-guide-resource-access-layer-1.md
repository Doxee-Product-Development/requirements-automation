---
id: "a7b34738-f892-4b30-b164-cdaf230eaadf"
title: "Resource Access Layer"
slug: "6-6-process-engine-user-guide-resource-access-layer-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:04.038Z"
modified_at: "2026-01-08T09:03:45.907Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-resource-access-layer-1"
synced_at: "2026-01-28T20:54:54.503Z"
checksum: "5a9a7cb3c8f6dd64"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

The Resource Access Layer (RAL) is used whenever Doxee accesses files or folders, e.g. on the local file system, on a file share, on an SFTP server or on an HTTP or WebDAV server, like Doxee Content Repository.

Resources are typically accessed through a URL. The URL’s scheme defines the protocol which should be used to access the resource. Doxee currently supports the following protocols:

**file**

Local file system (including mounted shares).

**http**

HTTP or WebDAV servers.

**https**

HTTP or WebDAV servers via SSL.

**sftp**

SFTP servers.

> Tip

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or

## File System (file)
File system access is used to access files on the local file system or on file shares mounted or mapped on the local system.

The file system is always accessed with the system user running the, Doxee applications. Therefore, user based features like creator and owner properties or access control lists are not supported.

## HTTP/WebDAV (http/https)
HTTP supports reading resources from URLs, and storing ('PUT') and deleting resources, if allowed by the server. WebDAV is an extension of the HTTP protocol and supports additional features like directory listings, file and directory properties, access control lists, and versioning. Some of these features are optional and not necessarily supported by all servers.

## SFTP (sftp)
SFTP (SSH File Transfer Protocol) is an alternative to FTP and supports file transfer using a single Secure Shell or SSH-connection. SFTP features include directory listings, remote file deletion and username-password authentication as well as public key authentication. Since SFTP was never officially standardised, servers can differ in their support of the protocol.

To establish a secure connection to SFTP servers, Doxee requires a client configuration file with an entry containing the SSH host key of the server. This file can be defined per user or per system, with the default path depending on the operating system. Alternatively, this VM parameter can be used to define a custom path to the configuration file:

`-Dinfinica.sshKeysFile=/path/to/my_known_hosts`Additionally, the validation of ssh host keys can be bypassed using this parameter (for security reasons, this is not recommended in production environments):

`-Dinfinica.trustAllSshKeys=true`## Connection Pooling
Doxee uses connection pools to prevent opening a large number of connections, which can cause problems in Microsoft Windows systems. Connection pooling allows Doxee to reuse connections for later requests to the same server without having to open additional system sockets.

The connection pool has a maximum number of connections that may be open at one time, and an additional limit per route (i.e. per server). If an application (e.g. Process Engine) tries to open more connections than allowed by the pool, it must wait for connections to become available in the pool. Timeouts may occur if no connections become available in time.

## Configuration
Some properties for HTTP connections can be configured via Java system properties. These properties are specified as VM parameters for the Java command, like this:

`-Dscheme.property``scheme `is the name of the protocol, i.e. `http `or `https. property` is the name of the property, as described in the following table.

Since HTTP and HTTPS are treated as separate protocols, properties must be configured individually for both protocols (if both are used).

*Table 1. HTTP/HTTPS Configuration Properties*

**Property**

**Default**

**Description**

`connectionPoolTimeout`

`60s`

Timeout for establishing a connection to a resource. This includes the timeout when waiting for a connection to become available in the connection pool.

`connectionTimeout`

`10s`

Timeout for connecting to a server. This only applies to the actual server connection and does not include the connection pool timeout

(this is covered by `connectionPoolTimeout`).

`requestTimeout`

`5m`

Timeout for servers to respond to requests, once the connection has been established.

`maxConnections`

`1000`

Maximum total number of connections.

`maxConnectionsForRoute`

`50`

Maximum number of connections for a single route (i.e. to a single server).

`proxyHost`

-

Proxy host name or IP.

`proxyPort`

-

Proxy port.

`proxyUser`

-

Proxy user name.

`proxyPassword`

-

Proxy password.

`username`

-

Default user name to use for accessing servers if no credentials are otherwise available (e.g. through a credentials registry).

`password`

-

Default password to use for accessing servers if no credentials are otherwise available (e.g. through a credentials registry).

## SSL
To access HTTPS servers, their certificates must be trusted by Java. Well-known certificates are already trusted by Java out of the box, but custom, self-signed certificates must be registered manually.

Custom certificates can be installed in the default Java trust store:

`JAVA_HOME/lib/security/cacerts`Alternatively, a custom key store can be created via Java’s `keytool`. In this case, the custom store can be configured via VM parameters:

`-Djavax.net.ssl.trustStore=/my/path/mycacerts
-Djavax.net.ssl.trustStorePassword=changeit`For further information on installing certificates in a key store, please refer to the official documentation of Java’s `keytool`.

## Doxee Content Repository
Infinica Content Repository (ICR) is accessed via WebDAV. A select number of proprietary features are exposed via custom WebDAV extensions. The availability of these features is detected automatically, so that clients can reference an ICR server via `http `or `https `like any regular WebDAV server.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}