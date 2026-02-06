---
id: "8a7ce875-ce97-455b-9fdf-f6245ceee086"
title: "PDF Text Extractor"
slug: "6-6-process-engine-manpages-activities-pdf-text-extractor-1"
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
created_at: "2026-01-07T13:42:15.4Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-text-extractor-1"
synced_at: "2026-01-28T20:55:47.479Z"
checksum: "71f58a5deb2f2d93"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfTextExtractor, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox-1)) 

Extracts text from a PDF document.

**Input Parameters:**

- pdf (x-infinica/stream) 

- PDF document.

- byPage (x-xsd/boolean) (0-1)

If set to "true", text will be extracted separately by page, and the result will be a list of strings, one string per page. If set to "false", the entire document's text will be returned as a single string.

- page (x-xsd/integer) (0-unbounded)

If provided, exactly the pages listed will be extracted, all pages otherwise.

- encodeChar (text/plain) (0-1)

If provided, defines the character that starts a 3-digit encoded character sequence. For example, if 'c' is provided (usually), every sequence of the form 'cxxx' will be decoded to the character whose unicode value is specified by xxx, if xxx is a valid integer.

- area (x-xsd/integer) (0-4)

If provided, only text from the specified rectangle (4 numbers will be interpreted as x, y, width and height) will be returned. Also, the "byPage" parameter will default to "true" in this case.

**Output Parameter:**

- text (text/plain) (1-unbounded) 

The extracted text.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}