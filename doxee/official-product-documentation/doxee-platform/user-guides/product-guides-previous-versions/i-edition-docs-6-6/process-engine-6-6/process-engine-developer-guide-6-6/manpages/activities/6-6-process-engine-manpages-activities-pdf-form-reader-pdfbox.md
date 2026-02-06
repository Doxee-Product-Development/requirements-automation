---
id: "171e2d5f-d097-492b-ac73-23f44f249e93"
title: "PDF Form Reader"
slug: "6-6-process-engine-manpages-activities-pdf-form-reader-pdfbox"
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
created_at: "2025-08-13T11:37:03.417Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-reader-pdfbox"
synced_at: "2026-01-28T21:02:30.281Z"
checksum: "c1c2d51480847635"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxFormReader, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox)) 

Retrieves form field data from a PDF document.

**Input Parameters:**

- pdfs (x-infinica/stream) (1-unbounded) 

PDF document.

- mode (text/plain)

Either "xml" (default) or "plain". In "xml" mode, the output parameter "data" is used to provide the data extracted from the PDF. In "plain" mode, each form field value is returned as a separate output parameter. The parameter "prefix" is used to control the names of the output parameters.

Default:

xml

- prefix (text/plain)

If "mode" is set to "plain", this parameter controls the names of the output parameters. For a form field named "name", the value will be provided in a parameter named "{$prefix}name".

Default:

data_

- node (text/plain)

Root element name for "xml" mode output.

Default:

data

**Output Parameter:**

- data (x-infinica/xml-node) (0-unbounded) 

Extracted data in XML format.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}