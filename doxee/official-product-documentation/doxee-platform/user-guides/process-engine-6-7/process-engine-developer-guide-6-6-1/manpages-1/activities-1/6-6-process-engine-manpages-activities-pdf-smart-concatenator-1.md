---
id: "5d19e108-295f-4f66-9f27-47012002db65"
title: "PDF Smart Concatenator"
slug: "6-6-process-engine-manpages-activities-pdf-smart-concatenator-1"
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
created_at: "2026-01-07T13:42:15.326Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-smart-concatenator-1"
synced_at: "2026-01-28T20:55:46.848Z"
checksum: "b3740a51063130d2"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfConcatenator, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1))

Merges multiple PDFs into one PDF. Makes sure that embedded fonts are not duplicated (unless they are embedded as subsets). May not handle form fields correctly.

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