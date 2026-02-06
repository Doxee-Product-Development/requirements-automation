---
id: "a2456be8-9a2d-4ab1-84d8-d0197376467d"
title: "PDF Encryption Getter"
slug: "pdf-encryption-setter-2"
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
created_at: "2026-01-07T13:42:14.55Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/pdf-encryption-setter-2"
synced_at: "2026-01-28T20:55:41.029Z"
checksum: "e726921839fa757b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfEncryptionGetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1)) 

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