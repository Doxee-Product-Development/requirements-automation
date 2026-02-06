---
id: "34c98e03-4964-45ae-b69e-f8d9beb4367a"
title: "RDI Converter"
slug: "6-6-process-engine-manpages-activities-rdi-converter-1"
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
created_at: "2026-01-07T13:42:15.955Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-rdi-converter-1"
synced_at: "2026-01-28T20:56:16.948Z"
checksum: "efd131ae83a8d301"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(rdiConverter, Module: [SAP](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-sap-1))

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