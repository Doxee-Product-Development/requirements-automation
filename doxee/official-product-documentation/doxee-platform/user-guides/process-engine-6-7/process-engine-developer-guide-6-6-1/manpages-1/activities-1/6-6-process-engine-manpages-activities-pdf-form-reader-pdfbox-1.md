---
id: "c7593b18-15f4-4256-a673-8b713cde279b"
title: "PDF Form Reader"
slug: "6-6-process-engine-manpages-activities-pdf-form-reader-pdfbox-1"
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
created_at: "2026-01-07T13:42:14.924Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-reader-pdfbox-1"
synced_at: "2026-01-28T20:55:43.595Z"
checksum: "8b2cd4d5972a897f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxFormReader, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox-1)) 

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