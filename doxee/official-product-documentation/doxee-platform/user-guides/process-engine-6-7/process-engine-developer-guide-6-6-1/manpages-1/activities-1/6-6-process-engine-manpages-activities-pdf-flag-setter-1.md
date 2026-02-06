---
id: "0d8b8f4a-a4a1-4415-9dd0-9692be9892a2"
title: "PDF Flag Setter"
slug: "6-6-process-engine-manpages-activities-pdf-flag-setter-1"
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
created_at: "2026-01-07T13:42:14.658Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-flag-setter-1"
synced_at: "2026-01-28T20:55:41.672Z"
checksum: "55ce9f003afb63e1"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfFlagSetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1))

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