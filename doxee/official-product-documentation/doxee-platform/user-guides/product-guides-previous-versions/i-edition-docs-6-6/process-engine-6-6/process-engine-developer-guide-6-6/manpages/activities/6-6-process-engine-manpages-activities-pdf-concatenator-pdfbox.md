---
id: "8b1869a2-80e8-493b-9d67-469e663517fb"
title: "PDF Concatenator"
slug: "6-6-process-engine-manpages-activities-pdf-concatenator-pdfbox"
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
created_at: "2025-08-13T11:20:20.154Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-concatenator-pdfbox"
synced_at: "2026-01-28T21:02:27.058Z"
checksum: "9807ad499637e26e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxConcatenator, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox))

Merges multiple PDF documents into one. Supports merging of PDF/A documents, meaning if every document complies with and declares the same PDF/A standard, the merged PDF document will also conform to this standard.

**Input Parameters:**

- pdfs (x-infinica/stream) (1-unbounded) 

List of PDF documents.

- target (x-infinica/url) (0-1)

Path to the file which will contain the concatenation result. If not specified, the result is returned in the variable "mergedPdf" instead.

- startOnOddPage (x-xsd/boolean) (0-1)

If this is "true", each individual document will start on an odd page in the merged document. Default is "false".

Default:

false

**Output Parameter:**

- mergedPdf (x-infinica/stream) (0-1)

Merged PDF. Will only be returned if "target" was not specified.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}