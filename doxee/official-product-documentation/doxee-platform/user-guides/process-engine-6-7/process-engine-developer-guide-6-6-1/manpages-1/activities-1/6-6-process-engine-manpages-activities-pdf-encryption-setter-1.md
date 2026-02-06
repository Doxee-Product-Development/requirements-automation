---
id: "b15cdc8e-0d1a-4c88-a696-a31ece8cec05"
title: "PDF Encryption Setter"
slug: "6-6-process-engine-manpages-activities-pdf-encryption-setter-1"
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
created_at: "2026-01-07T13:42:14.595Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-encryption-setter-1"
synced_at: "2026-01-28T20:55:41.349Z"
checksum: "60d43cb4eae23001"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfEncryptionSetter, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1))

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