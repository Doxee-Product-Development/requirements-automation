---
id: "96fff80d-8ac0-436b-a7ba-c74e591f7b3a"
title: "PDF Form Creator"
slug: "6-6-process-engine-manpages-activities-pdf-form-creator"
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
created_at: "2025-08-13T11:30:05.73Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-form-creator"
synced_at: "2026-01-28T21:02:28.990Z"
checksum: "110f55709e7d88ae"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFormCreator, Module: [PDF Forms](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdf-forms))

Creates a PDF form based on the field definitions in the bookmarks.

**Input Parameters:**

- pdf (x-infinica/stream) (1-unbounded) 

Input PDFs.

- password (x-infinica/secret-text) (0-unbounded) 

Passwords for encrypted PDFs.

- mode (text/plain) (0-unbounded)

Operation mode. Normally auto-detected from the creator field in the PDF.

**Output Parameter:**

- pdf (x-infinica/stream) (1-unbounded) Created PDF forms.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}