---
id: "afaf0c5f-9a42-4698-a0fd-0a760a4ea060"
title: "PDF Script Reader"
slug: "6-6-process-engine-manpages-activities-pdf-script-reader"
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
created_at: "2025-08-13T12:59:03.238Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-script-reader"
synced_at: "2026-01-28T21:02:32.555Z"
checksum: "51ab0c4d45d3dcfc"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfScriptReader, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Read top-level scripts from PDFs and return them as texts.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDF.

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader

- password (x-infinica/secret-text) (0-unbounded)

If provided, will be used to open password-protected input PDFs.

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded)

PDF Reader for re-use

- scripts (text/plain) (0-unbounded) 

Scripts of the PDFs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}