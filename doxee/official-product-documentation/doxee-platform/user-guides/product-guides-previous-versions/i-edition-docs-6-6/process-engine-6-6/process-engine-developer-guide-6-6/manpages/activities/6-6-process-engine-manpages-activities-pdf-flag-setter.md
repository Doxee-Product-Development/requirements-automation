---
id: "da464e8e-8902-4bad-bfa1-c14bcee26afe"
title: "PDF Flag Setter"
slug: "6-6-process-engine-manpages-activities-pdf-flag-setter"
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
created_at: "2025-08-13T11:28:45.085Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-flag-setter"
synced_at: "2026-01-28T21:02:28.360Z"
checksum: "7e53578d5fc64073"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFlagSetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf))

Sets control flags in a PDF. Flags that are not specified in the inputs will remain unchanged.

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDFs.

- pdf-reader (x-infinica/java) (0-unbounded) 

PDF Readers.

- password (x-infinica/secret-text) (0-unbounded)

If provided, will be used to open password-protected input PDFs.

- printScaling (x-xsd/boolean) (0-1)

Controls the print scaling flag of the PDFs. true sets the PDF to use the application default scaling setting. false disables print scaling by default.

**Output Parameters:**

- pdf-reader (x-infinica/java) (0-unbounded) 

PDF Readers for re-use.

- pdf (x-infinica/stream) (0-unbounded) 

Resulting PDFs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}