---
id: "eff23e14-0b55-48f9-ad21-ee63dfacd669"
title: "PDF Form Filler"
slug: "6-6-process-engine-manpages-activities-pdf-form-filler-openpdf-1"
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
created_at: "2026-01-07T13:42:14.862Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-filler-openpdf-1"
synced_at: "2026-01-28T20:55:43.282Z"
checksum: "ea19183ac1fb8566"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFormFiller, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1)) 

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