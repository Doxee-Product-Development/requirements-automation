---
id: "a03073c4-b171-437c-98e6-438ee77931ab"
title: "PDF Encryption Getter"
slug: "pdf-encryption-setter"
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
created_at: "2025-08-13T11:27:04.974Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/pdf-encryption-setter"
synced_at: "2026-01-28T21:02:27.692Z"
checksum: "2c9ac1a6a92be709"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfEncryptionGetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf)) 

Returns encryption information for the specified PDFs.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDFs.

- password (x-infinica/secret-text) (0-unbounded)

If provided, will be used to open password-protected input PDFs.

**Output Parameter:**

- encryption (text/xml)

Encryption information.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}