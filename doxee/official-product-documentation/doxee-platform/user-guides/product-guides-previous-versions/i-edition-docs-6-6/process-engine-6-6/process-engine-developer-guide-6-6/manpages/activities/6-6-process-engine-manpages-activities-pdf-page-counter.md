---
id: "1f477061-cf6b-4a2c-884b-535c2e0d8896"
title: "PDF Page Counter"
slug: "6-6-process-engine-manpages-activities-pdf-page-counter"
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
created_at: "2025-08-13T11:38:54.823Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-page-counter"
synced_at: "2026-01-28T21:02:30.936Z"
checksum: "27e4419cb0ae1f7d"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfPageCounter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Counts pages from a PDF.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDF.

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- unit (text/plain) (0-1)

Optional. If set, the dimensions of all the pages will be returned in the given unit. Valid units are: mm, in, pdf

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Readers for re-use

- pages (x-xsd/integer) (1-unbounded) 

Number of pages in the PDF.

- dimensions (text/xml) (0-1)

If a unit was passed, this output parameter will contain an XML document with one element per PDF document with one element per page.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}