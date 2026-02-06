---
id: "aa848b85-e8dc-4764-9aaf-ca95fcc70397"
title: "PDF Encryption Setter"
slug: "6-6-process-engine-manpages-activities-pdf-encryption-setter"
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
created_at: "2025-08-13T11:27:37.758Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-encryption-setter"
synced_at: "2026-01-28T21:02:28.020Z"
checksum: "6402d005ea040b03"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfEncryptionSetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf))

Encrypt the specified PDFs. Permissions flags that are not specified are kept set to the same values as in the input PDFs. 

**Input Parameters:**

- pdf (x-infinica/stream) (0-unbounded) 

Input PDFs.

- password (x-infinica/secret-text) (0-unbounded)

If provided, will be used to open password-protected input PDFs.

- userPassword (text/plain) (0-1)

User password for the newly encrypted PDFs.

- ownerPassword (text/plain) (0-1)

Owner password for the newly encrypted PDFs.

- encryption (text/plain)

Encryption type. Allowed values are 'none', 'standard40', 'standard128' and 'aes128'.

Default:

none

- encryptMetaData (x-xsd/boolean) (0-1)

Whether to also encrypt metadata. If this is not specified and the PDF was not encryped before, metadata is encrypted by default.

- allowPrinting (x-xsd/boolean) (0-1) 

The 'allowPrinting' permission.

- allowModifyContents (x-xsd/boolean) (0-1) 

The 'allowModifyContents' permission.

- allowCopy (x-xsd/boolean) (0-1) 

The 'allowCopy' permission.

- allowModifyAnnotations (x-xsd/boolean) (0-1) 

The 'allowModifyAnnotations' permission.

- allowFillIn (x-xsd/boolean) (0-1) 

The 'allowFillIn' permission.

- allowScreenReaders (x-xsd/boolean) (0-1) 

The 'allowScreenReaders' permission.

- allowAssembly (x-xsd/boolean) (0-1) 

The 'allowAssembly' permission.

- allowDegradedPrinting (x-xsd/boolean) (0-1) 

The 'allowDegradedPrinting' permission.

**Output Parameter:**

- pdf (x-infinica/stream) (0-unbounded) 

Modified PDFs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}