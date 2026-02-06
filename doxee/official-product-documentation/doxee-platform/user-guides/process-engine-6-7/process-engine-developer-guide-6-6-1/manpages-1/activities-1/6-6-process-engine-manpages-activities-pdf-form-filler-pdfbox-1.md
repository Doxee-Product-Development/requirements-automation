---
id: "465dabdb-4f4d-44a2-992d-ee297eceaa8a"
title: "PDF Form Filler"
slug: "6-6-process-engine-manpages-activities-pdf-form-filler-pdfbox-1"
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
created_at: "2026-01-07T13:42:14.823Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-filler-pdfbox-1"
synced_at: "2026-01-28T20:55:42.958Z"
checksum: "6c39b293493b87a6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxFormFiller, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox-1))

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