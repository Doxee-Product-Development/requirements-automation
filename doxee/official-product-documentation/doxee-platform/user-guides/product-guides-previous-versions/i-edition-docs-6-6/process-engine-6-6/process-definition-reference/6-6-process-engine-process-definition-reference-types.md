---
id: "b084eb13-2588-4570-828e-2eddafb60ba4"
title: "Types"
slug: "6-6-process-engine-process-definition-reference-types"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T12:29:52.416Z"
modified_at: "2025-08-20T17:44:21.613Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-types"
synced_at: "2026-01-28T21:01:27.153Z"
checksum: "a951f5b13f70ca1a"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Types supported by the Process Engine, like activities and XPath functions, are provided by the installed modules. The available types and their descriptions are listed in the man pages.

The type system is based on Internet Media Types (also known as MIME types). Each type name consists of a main type, a sub type and optionally a list of parameters:

*main type* **/** *sub type* **;** *param1* **=** *value1* **;** *param2* **=** *value2* …

The following main types are used by standard installations:

text

Text types, including the standard types *text/plain* and *text/xml*.

x-xsd

Types based on the standard types from the XSD schema specification, e.g. *xxsd/integer* and *x-xsd/boolean*.

x-infinica

Special types provided by Doxee, e.g. *x-infinica/url*.

Generally, pipeline variables are immutable. A standard exception to this rule is the type *xinfinica/xml-node*. Variables of this type refer to nodes from other XML documents (of type *text/xml*) without cloning those documents. If the referenced document changes, the *xmlnode* values will change along with them.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}