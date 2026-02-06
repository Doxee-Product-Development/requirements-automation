---
id: "c79b7d5a-46ec-4bf9-a53b-cf585e965f12"
title: "RDI Converter"
slug: "6-6-process-engine-manpages-activities-rdi-converter"
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
created_at: "2025-08-13T13:22:38.323Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-rdi-converter"
synced_at: "2026-01-28T21:02:39.537Z"
checksum: "36ee103afe27a5d1"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(rdiConverter, Module: [SAP](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-sap))

Converts RDI inputs (stream, byte array, string) to XMLs.

**Input Parameters:**

- rdi (x-infinica/stream, x-infinica/java, text/plain) (1-unbounded) 

RDI input.

- encoding (text/plain) (0-unbounded)

Encoding of the input stream. Optional. Defaults to UTF-8. Not needed if input is text.

- singleDoc (x-xsd/boolean)

Flag for producing a single result document. Optional. Defaults to false.

Default:

false

**Output Parameter:**

- xml (text/xml) (1-unbounded) 

The converted documents.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}