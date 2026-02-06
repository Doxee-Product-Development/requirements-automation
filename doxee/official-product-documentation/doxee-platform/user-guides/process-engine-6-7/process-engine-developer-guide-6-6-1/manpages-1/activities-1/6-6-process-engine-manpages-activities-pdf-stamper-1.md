---
id: "130e9fce-467a-4aaa-8409-2c03f8e167df"
title: "PDF Stamper"
slug: "6-6-process-engine-manpages-activities-pdf-stamper-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:15.362Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-stamper-1"
synced_at: "2026-01-28T20:55:47.157Z"
checksum: "09b94a51e1be9664"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfStamper, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1))

Stamps stampable items on a PDF's pages. Takes one or more XML structures describing what should be stamped as 'stamps' parameter.

**Input Parameters:**

- pdf (x-infinica/stream) 

Input PDF.

- password (x-infinica/secret-text) (0-1)

Optional. Necessary if the pdf requires a password.

- stamps (text/xml) (0-unbounded)

The stamp XMLs as outlined in the main activity description.

- flipY (x-xsd/boolean)

Boolean parameter specifying if the y value should be flipped.

Default:

true

- *

**Output Parameter:**

- pdf (x-infinica/stream) 

Modified PDF.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}