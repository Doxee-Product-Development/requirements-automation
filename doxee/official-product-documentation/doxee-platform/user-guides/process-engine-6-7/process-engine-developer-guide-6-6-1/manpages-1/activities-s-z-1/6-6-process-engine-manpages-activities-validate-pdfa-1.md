---
id: "c26378fe-c5c2-4767-a239-110497a74f03"
title: "Validate PDF/A"
slug: "6-6-process-engine-manpages-activities-validate-pdfa-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:17.65Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-validate-pdfa-1"
synced_at: "2026-01-28T20:56:29.678Z"
checksum: "36445ddeade8f8c7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(PdfAValidator, Module: [PDF/A Validation](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfa-validation-1)) 

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