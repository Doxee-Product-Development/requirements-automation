---
id: "9d5d284e-3845-4d34-8ea5-830094d6afbb"
title: "Types"
slug: "6-6-process-engine-user-guide-types-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.742Z"
modified_at: "2026-01-07T14:04:28.741Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-types-1"
synced_at: "2026-01-28T20:54:53.280Z"
checksum: "39b003f4047ef23c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Types supported by the Process Engine, like activities and XPath functions, are provided by the installed modules. The available types and their descriptions are listed in the man pages.

The type system is based on Internet Media Types (also known as MIME types). Each type name consists of a main type, a sub type and optionally a list of parameters:

*main type* **/** *sub type* **;** *param1* **=** *value1* **;** *param2* **=** *value2* …

The following main types are used by standard installations:

**text**

Text types, including the standard types text/plain and text/xml.

**x-xsd**

Types based on the standard types from the XSD schema specification, e.g. xxsd/integer and x-xsd/boolean.

**x-infinica**

Special types provided by Doxee, e.g. x-infinica/url.

Generally, pipeline variables are immutable. A standard exception to this rule is the type *xinfinica/xml-node*. Variables of this type refer to nodes from other XML documents (of type *text/xml*) without cloning those documents. If the referenced document changes, the *xmlnode* values will change along with them.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}