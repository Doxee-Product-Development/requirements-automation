---
id: "b9255eec-d98d-4d68-a831-6897c3e78eb8"
title: "Validate PDF/A"
slug: "6-6-process-engine-manpages-activities-validate-pdfa"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T14:45:31.631Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-validate-pdfa"
synced_at: "2026-01-28T21:02:54.466Z"
checksum: "153ee7c20b7bb72e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(PdfAValidator, Module: [PDF/A Validation](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfa-validation)) 

Validates the input PDF/A.

**Input Parameters:**

- pdfAFile (x-infinica/stream) (1-unbounded) 

List of PDF/A document(s) to validate.

- pdfAMode (text/plain) (0-1)

PDF/A standard to validate document(s) against (optional). Valid options are: "PDF/A-1a", "PDF/ A-1b", "PDF/A-2a", "PDF/A-2b", "PDF/A-2u", "PDF/A-3a", "PDF/A-3b", "PDF/A-3u", "PDF/A-4", "PDF/ A-4e", "PDF/A-4f" and "ua1" (PDF/UA-1).

- autoDetect (x-xsd/boolean) (0-1)

Whether or not veraPDF's Auto-detect feature should be used to recognize the standard of a PDF/ A document ahead of validation instead of choosing a PDF/A standard (optional). If both a value for pdfAMode was given and autoDetect is set to true, autoDetect will be used as a fallback in case the entered PDF/a mode is invalid.

**Output Parameter:**

- report (text/plain) (1-unbounded)

A list of veraPDF XML reports containing the validation results.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}