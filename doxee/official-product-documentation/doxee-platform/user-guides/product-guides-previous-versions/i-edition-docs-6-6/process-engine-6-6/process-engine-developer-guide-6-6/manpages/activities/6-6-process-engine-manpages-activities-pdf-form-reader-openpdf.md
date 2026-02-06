---
id: "0e554e81-9833-449b-a6bb-1dee0d5fea4e"
title: "PDF Form Reader"
slug: "6-6-process-engine-manpages-activities-pdf-form-reader-openpdf"
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
created_at: "2025-08-13T11:37:46.136Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-reader-openpdf"
synced_at: "2026-01-28T21:02:30.598Z"
checksum: "2e9281c37f1104fa"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFormReader, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Reads the form field data of a PDF form. 

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDF.

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- mode (text/plain)

Either "xml" (default) or "plain". In "xml" mode, the output parameter "data" is used to provide the data extracted from the PDF. In "plain" mode, each form field value is returned as a separate output parameter. The parameter "prefix" is used to control the names of the output parameters.

Default:

 xml

prefix (text/plain)

If "mode" is set to "plain", this parameter controls the names of the output parameters. For a form field named "name", the value will be provided in a parameter named "{$prefix}name".

Default:

- data_

- node (text/plain)

Main node name for 'xml' mode.

Default:

data

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader for re-use

- data (text/xml) (0-unbounded) 

Extracted data.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}