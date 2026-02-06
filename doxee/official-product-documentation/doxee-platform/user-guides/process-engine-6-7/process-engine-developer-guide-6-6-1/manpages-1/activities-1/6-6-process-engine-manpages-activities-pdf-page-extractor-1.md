---
id: "b4e42c29-bb91-494c-bcfa-1b326487bb3d"
title: "PDF Page Extractor"
slug: "6-6-process-engine-manpages-activities-pdf-page-extractor-1"
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
created_at: "2026-01-07T13:42:15.041Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-page-extractor-1"
synced_at: "2026-01-28T20:55:44.586Z"
checksum: "35bcccc7828baf68"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfPageExtractor, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1)) Extracts pages from a PDF.

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