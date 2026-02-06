---
id: "45bb8ff1-dddf-41f4-849b-f9370f8c8301"
title: "PDF Page Counter"
slug: "6-6-process-engine-manpages-activities-pdf-page-counter-1"
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
created_at: "2026-01-07T13:42:14.997Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-page-counter-1"
synced_at: "2026-01-28T20:55:44.242Z"
checksum: "02e5d2cf797f7244"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfPageCounter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1)) 

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