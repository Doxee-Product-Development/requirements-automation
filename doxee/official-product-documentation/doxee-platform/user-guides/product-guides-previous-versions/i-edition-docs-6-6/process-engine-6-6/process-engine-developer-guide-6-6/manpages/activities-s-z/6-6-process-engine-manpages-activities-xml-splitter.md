---
id: "2098edde-9c8c-4beb-9a64-beb9e62f6e8d"
title: "XML Splitter"
slug: "6-6-process-engine-manpages-activities-xml-splitter"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T14:48:45.323Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-xml-splitter"
synced_at: "2026-01-28T21:02:56.105Z"
checksum: "98ddf6289234b8d0"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(xmlSplitter, Module: [Splitter](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-splitter))

Splits an XML into several smaller ones, using a SAX parser (linear performance).

**Input Parameters:**

- configDoc (text/xml) (0-1)

Configuration document. May be omitted if configUrl is specified.

- configUrl (x-infinica/url) (0-1)

URL for the configuration document. May be omitted if configDoc is specified and contains a base URL.

- xmlUrl (x-infinica/url)

URL for the XML document.

- docUrl (x-infinica/url) (0-1)

Base URL for SaxParser. If not provided the xmlUrl is used instead.

- encodingIn (text/plain) (0-1)

Name of the actual encoding of the input stream. May be null.

- encodingOut (text/plain) (0-1)

Name of the desired encoding of the input stream. May be null. Translation will be applied as necessary.

- listUrls (x-xsd/boolean)

If this is true, the output parameter urls will be provided.

Default:

false

**Output Parameters:**

- documents (x-xsd/integer)

The number of created XML documents.

- urls (x-infinica/url) (0-unbounded)

The URLs of the created XML files. For memory reasons, this parameter will only be provided if the input parameter listUrls is true.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}