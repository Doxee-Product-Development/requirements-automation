---
id: "c027e4ac-9c9e-4b29-b840-ca808733ad11"
title: "XML Splitter"
slug: "6-6-process-engine-manpages-activities-xml-splitter-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:17.476Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-xml-splitter-1"
synced_at: "2026-01-28T20:56:31.343Z"
checksum: "5c73f91369fbbd4c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(xmlSplitter, Module: [Splitter](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-splitter-1))

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