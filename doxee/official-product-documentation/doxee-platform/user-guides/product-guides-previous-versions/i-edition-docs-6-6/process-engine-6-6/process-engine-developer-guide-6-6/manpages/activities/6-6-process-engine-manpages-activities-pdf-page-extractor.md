---
id: "6f36e7f0-f3bc-4117-ade6-cd7b49dfc4e1"
title: "PDF Page Extractor"
slug: "6-6-process-engine-manpages-activities-pdf-page-extractor"
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
created_at: "2025-08-13T11:39:15.457Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-page-extractor"
synced_at: "2026-01-28T21:02:31.248Z"
checksum: "77f64ba006909fde"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfPageExtractor, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) Extracts pages from a PDF.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) Input PDF.

pdf-reader (x-infinica/java) (0-unbounded) PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- pages (x-xsd/integer) (1-unbounded)

Page numbers of the pages to extract from the PDF.

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader for re-use

- extracted (x-infinica/stream) (1-unbounded) 

PDF with extracted pages.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}