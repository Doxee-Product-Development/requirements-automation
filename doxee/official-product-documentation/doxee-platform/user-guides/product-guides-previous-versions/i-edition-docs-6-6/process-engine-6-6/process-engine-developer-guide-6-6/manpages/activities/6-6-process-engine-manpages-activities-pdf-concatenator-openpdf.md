---
id: "60d43fd1-abc9-41dc-aa85-8da6a8551fca"
title: "PDF Concatenator"
slug: "6-6-process-engine-manpages-activities-pdf-concatenator-openpdf"
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
created_at: "2025-08-13T11:22:47.05Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-concatenator-openpdf"
synced_at: "2026-01-28T21:02:27.378Z"
checksum: "92f68ee38ea9b1ac"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfLegacyConcatenator, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Merges multiple PDFs into one PDF.

Deprecated: This is a legacy implementation. It does not optimise the resulting PDFs. pdfConcatenator (the new implementation) should be used instead, unless it causes unexpected problems.

**Input Parameters:**

- pdfs (x-infinica/stream) (0-unbounded) 

Input PDFs.

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- startOnOddPage (x-xsd/boolean)

If this is "true", each individual document will start on an odd page in the merged document. Default is "false".

Default:

false

- forceSameSizeOnBack (x-xsd/boolean)

If this is "true", each even-numbered page in the resulting document will have the same size as the previous page. Page content is scaled to fit. Default is "false".

Default:

false

- keepBookmarks (x-xsd/boolean)

If this is "true", the bookmarks of the individual documents will be copied to the result document, with updated page numbers. Default is "true".

Default:

true

- keepScripts (x-xsd/boolean)

If this is "true", the top-level scripts of the individual documents will be copied to the result document. Default is "true".

Default:

true

- target (x-infinica/url) (0-1)

The URL where the result will be written. If not specified, the result is returned in the variable "pdf" instead.

**Output Parameters:**

- pdf (x-infinica/stream) (0-1)

Merged PDF. Will only be returned if "target" was not specified.

- pages (x-xsd/integer)

Number of pages in merged PDF.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}