---
id: "c8de1d3e-b02f-4aec-b2f3-7e8c1e9786d7"
title: "Analyze Indexed Item References"
slug: "6-6-process-engine-manpages-activities-analyze-indexed-item-references"
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
created_at: "2025-08-13T10:34:37.732Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-analyze-indexed-item-references"
synced_at: "2026-01-28T21:01:50.948Z"
checksum: "5a2d917c4c4e9d0b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(analyzeIndexedItemReferences, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion)) Analyses the references of an indexed item.

**Input Parameters:**

- indexerConfig (text/xml) (0-1)

Indexer configuration. This configuration takes precedence over any indexer that may be provided by the project. If no configuration is specified, the indexer is acquired from the project directory, if possible.

- url (x-infinica/url)

The URL of the file containing the item that should be queried.

- name (text/plain)

The name of the indexed item.

- type (text/plain)

The type of the indexed item.

**Output Parameter:**

- analysis (text/xml) (0-1) The item analysis.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}