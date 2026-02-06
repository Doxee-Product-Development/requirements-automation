---
id: "48d8dddc-990a-4067-90bb-11120ba09f43"
title: "Analyze Indexed File References"
slug: "6-6-process-engine-manpages-activities-analyze-indexed-file-references-1"
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
created_at: "2026-01-07T13:42:12.307Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-analyze-indexed-file-references-1"
synced_at: "2026-01-28T20:55:24.762Z"
checksum: "7c783708563aa34e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(analyzeIndexedFileReferences, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion-1)) Analyses the references of an indexed file.

**Input Parameters:**

- indexerConfig (text/xml) (0-1)

Indexer configuration. This configuration takes precedence over any indexer that may be provided by the project. If no configuration is specified, the indexer is acquired from the project directory, if possible.

- url (x-infinica/url)

The URL of the file that should be queried.

- includeItemUses (x-xsd/boolean)

Whether item references should be included in the analysis.

Default:

false

- includeTransitive (x-xsd/boolean)

Whether transitive references should be included in the analysis.

Default:

 false

- filterItem (text/plain) (0-1)

If specified, only items of this type will be included in the analysis.

- filterItemIncoming (text/plain) (0-1)

If specified, only incoming item references of this type will be included in the analysis.

- filterItemOutgoing (text/plain) (0-1)

If specified, only outgoing item references of this type will be included in the analysis.

**Output Parameter:**

- analysis (text/xml) (0-1) The item analysis.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}