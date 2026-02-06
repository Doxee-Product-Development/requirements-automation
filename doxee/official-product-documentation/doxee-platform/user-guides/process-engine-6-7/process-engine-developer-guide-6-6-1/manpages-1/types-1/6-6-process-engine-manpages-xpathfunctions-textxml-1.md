---
id: "53e31ad1-e482-463e-894d-8a5fbb873dc8"
title: "text/xml"
slug: "6-6-process-engine-manpages-xpathfunctions-textxml-1"
category: "Types"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:07.45Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-textxml-1"
synced_at: "2026-01-28T20:57:22.318Z"
checksum: "399611cbb07bb894"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1))

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