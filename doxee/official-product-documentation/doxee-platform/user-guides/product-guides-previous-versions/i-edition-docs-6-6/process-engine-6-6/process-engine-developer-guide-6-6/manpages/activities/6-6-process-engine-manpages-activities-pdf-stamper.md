---
id: "d3a03e46-222f-47ae-b411-99eea05ced6e"
title: "PDF Stamper"
slug: "6-6-process-engine-manpages-activities-pdf-stamper"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T13:05:35.964Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-stamper"
synced_at: "2026-01-28T21:02:33.878Z"
checksum: "bbc5538abb43cee0"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfStamper, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf))

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