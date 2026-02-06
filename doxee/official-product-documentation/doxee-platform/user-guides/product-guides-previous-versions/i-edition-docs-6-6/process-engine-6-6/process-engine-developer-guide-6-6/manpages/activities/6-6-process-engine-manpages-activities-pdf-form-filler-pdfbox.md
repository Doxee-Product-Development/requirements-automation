---
id: "0ba6b7ca-cd9d-441b-b662-273f88de7945"
title: "PDF Form Filler"
slug: "6-6-process-engine-manpages-activities-pdf-form-filler-pdfbox"
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
created_at: "2025-08-13T11:34:50.797Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-filler-pdfbox"
synced_at: "2026-01-28T21:02:29.635Z"
checksum: "4f567af260a7f3f9"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxFormFiller, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox))

Fills the form fields of a PDF document with the specified data.

**Input Parameters:**

- pdf (x-infinica/stream) (1-unbounded) 

PDF document.

- mode (text/plain)

Either "xml" (default) or "plain". In "xml" mode, the parameter "data" is used to retrieve the form data. In "plain" mode, the parameter "prefix" and all parameters of the form "{$prefix}name" are used as key/value pairs providing form data instead.

Default:

xml 

- data (text/xml) (0-unbounded)

Form data for "xml" mode. The root element of this XML document should provide a series of elements with attributes named "name" and "value".

- prefix (text/plain)

Parameter name prefix for "plain" mode (default: "data_"").

Default:

data_

**Output Parameter:**

- filled (x-infinica/stream) (1-unbounded) 

The resulting PDF document.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}