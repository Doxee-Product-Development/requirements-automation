---
id: "15ca71b1-9a26-4249-b7c8-5847cbff40ae"
title: "WebDAV"
slug: "content-repository-6-6-webdav"
category: "Content Repository"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T10:13:37.956Z"
modified_at: "2025-12-04T10:38:53.787Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-6-6-webdav"
synced_at: "2026-01-28T21:00:49.233Z"
checksum: "6d22af67cad3619f"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

WebDAV (Web-based Distributed Authoring and Versioning) is a standard for providing files and directories via the internet. It is an extension to the HTTP/1.1 standard, which also contains version control. The WebDAV standard is specified in the following RFCs (request for comment):

- 4918 ([https://tools.ietf.org/html/rfc4918[RFC]](https://tools.ietf.org/html/rfc4918[RFC])) HTTP Extensions for Web Distributed Authoring and Versioning (WebDAV)

- 3253 ([https://tools.ietf.org/html/rfc3253[RFC]](https://tools.ietf.org/html/rfc3253[RFC])) Versioning Extensions to WebDAV

- 3744 ([https://tools.ietf.org/html/rfc3744[RFC]](https://tools.ietf.org/html/rfc3744[RFC])) Web Distributed Authoring and Versioning Access Control Protocol

- 5397 ([https://tools.ietf.org/html/rfc5397[RFC]](https://tools.ietf.org/html/rfc5397[RFC])) WebDAV Current Principal Extension

- Draft Searching &amp; Locating ([http://www.webdav.org/dasl/protocol/draft-davis-dasl-protocol-00.html[DASL]](http://www.webdav.org/dasl/protocol/draft-davis-dasl-protocol-00.html[DASL]))

## Methods
Just like in HTTP there are different request methods in WebDAV, specifying what operation should be performed on the resource identified by the provided URL upon a client request. WebDAV uses the common HTTP methods such as GET, HEAD, PUT etc., partly with modified semantics. It also defines additional methods for different purposes such as common filesystem operations (e.g. MKCOL, COPY, MOVE) managing properties (e.g. PROPFIND, PROPPATCH), versioning (e.g. VERSION-CONTROL, CHECKOUT, CHECKIN) or managing access control (ACL).

## Properties
In WebDAV there are certain pieces of information called properties attached to resources. The properties of a resource define its state and provide important metadata (e.g. author of a file). A property consists of a name and a value, which is an XML fragment. Some properties are set and maintained by the server and cannot be changed manually, others must be set by clients. Properties can be fetched using the PROPFIND method and set, modified or removed using the PROPPATCH method.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}