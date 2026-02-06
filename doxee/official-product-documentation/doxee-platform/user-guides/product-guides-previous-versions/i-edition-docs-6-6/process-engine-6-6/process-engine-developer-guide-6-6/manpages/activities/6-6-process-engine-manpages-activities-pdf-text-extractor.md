---
id: "a36f28ac-4940-45c1-8575-d568f138bf9f"
title: "PDF Text Extractor"
slug: "6-6-process-engine-manpages-activities-pdf-text-extractor"
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
created_at: "2025-08-13T13:06:25.485Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-text-extractor"
synced_at: "2026-01-28T21:02:34.205Z"
checksum: "8d8706223eb8ef89"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfTextExtractor, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox)) 

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