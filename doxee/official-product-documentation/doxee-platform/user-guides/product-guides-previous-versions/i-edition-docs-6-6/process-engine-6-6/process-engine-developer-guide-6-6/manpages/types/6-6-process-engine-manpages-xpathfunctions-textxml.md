---
id: "27084c70-72c6-48b7-aba8-3550e684d5f7"
title: "text/xml"
slug: "6-6-process-engine-manpages-xpathfunctions-textxml"
category: "Types"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T16:06:11.345Z"
modified_at: "2025-08-22T17:34:19.966Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-textxml"
synced_at: "2026-01-28T21:03:41.645Z"
checksum: "afe3efa3edfabf75"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core))

By default, XML documents are created with version 1.0. In case of compatibility issues the default `version` can be changed by setting the version parameter or the system property `com.infinica.engine.pipeline.xmlVersion`.

**Parameters:**

- **charset**

The XML charset.

- **version**

The XML version (1.0 or 1.1).

- **standalone**

A boolean value specifying the XML's standalone flag.

- **indent**

A boolean value specifying whether text representations of the XML should use identation.

- **declaration**

A boolean value specifying whether text representations of the XML should include the XMLdeclaration. Even if this is set to `false`, the declaration may be included if the other parameters require it.

- **root**

Name of the root element when converting table data (e.g. CSV) to XML. Defaults to `root`.

- **row**

Name of the row elements when converting table data (e.g. CSV) to XML. Defaults to `row`.

- **field**

Name of the field elements when converting table data (e.g. CSV) to XML. Defaults to `field`. If this is set to an empty string, the field's column name will be used as the element name.

- **nameAttribute**

Name of the attribute containing the column name of a field when converting table data (e.g. CSV) to XML.

- **valueAttribute**

Name of the attribute containing the value of a field when converting table data (e.g. CSV) to XML. If not set, the value will be set as the element's content.

- **namespace**

Optional namespace URL for the XML elements when converting table data (e.g. CSV) to XML.

**Conversions:**

text/plain → text/xml 

text/xml → text/plain 

text/xml → x-infinica/stream 

text/xml → x-infinica/stream 

x-infinica/stream → text/xml 

text/xml → application/xslt+xml 

application/xslt+xml → text/xml 

text/xml → text/html 

text/html → text/xml 

x-infinica/xml-node → text/xml

text/xml → x-infinica/xml-node 

x-infinica/exception → text/xml 

text/csv → text/xml

x-infinica/fixed-width → text/xml

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}