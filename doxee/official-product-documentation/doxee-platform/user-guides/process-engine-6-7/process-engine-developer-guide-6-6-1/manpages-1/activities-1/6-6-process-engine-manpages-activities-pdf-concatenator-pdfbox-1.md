---
id: "73e3a16a-7374-4b41-8016-fd21f18693c1"
title: "PDF Concatenator"
slug: "6-6-process-engine-manpages-activities-pdf-concatenator-pdfbox-1"
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
created_at: "2026-01-07T13:42:14.471Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-concatenator-pdfbox-1"
synced_at: "2026-01-28T20:55:40.347Z"
checksum: "009d77e67593c0fe"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxConcatenator, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox-1))

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