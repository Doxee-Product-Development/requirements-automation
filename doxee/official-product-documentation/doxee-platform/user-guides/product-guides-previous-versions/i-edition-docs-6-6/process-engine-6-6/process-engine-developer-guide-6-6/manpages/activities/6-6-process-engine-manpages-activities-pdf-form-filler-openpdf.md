---
id: "94a467d0-85c7-4787-b430-f06142380fa9"
title: "PDF Form Filler"
slug: "6-6-process-engine-manpages-activities-pdf-form-filler-openpdf"
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
created_at: "2025-08-13T11:35:50.499Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-filler-openpdf"
synced_at: "2026-01-28T21:02:29.962Z"
checksum: "177426eeae877aa3"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFormFiller, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Fills the form fields of a PDF with data.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDF.

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- mode (text/plain)

Either 'xml' (default) or 'plain'. In 'xml' mode, the parameter 'data' is used. In 'plain' mode, the parameter 'prefix' and all parameters of the form {$prefix}name are used.

Default:

xml

- data (text/xml) (0-unbounded) 

Form data for 'xml' mode.

- prefix (text/plain)

Parameter name prefix for 'plain' mode (default: data_).

Default:

data_

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader for re-use

- filled (x-infinica/stream) (1-unbounded) 

Filled PDFs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}