---
id: "27d5c51e-0ad7-401c-83a0-0bd2d18fd2da"
title: "PDF Form Analyzer"
slug: "6-6-process-engine-manpages-activities-pdf-form-analyzer"
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
created_at: "2025-08-13T11:29:24.348Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-analyzer"
synced_at: "2026-01-28T21:02:28.680Z"
checksum: "6c27d1249c3d9190"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFormAnalyzer, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf))

Analzyes a PDF form and produces an XML describing the available form fields and their types and positions.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDF.

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

**Output Parameters:**

- result (text/xml) (1-unbounded) 

XML report.

- pdf-reader (x-infinica/java) (0-unbounded) 

PDF Reader for re-use

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}