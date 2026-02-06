---
id: "c46b0ab6-62fe-4995-99b2-f7424675a0dc"
title: "Merge Templates"
slug: "6-6-process-engine-manpages-activities-merge-templates-1"
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
created_at: "2026-01-07T13:42:14.22Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-merge-templates-1"
synced_at: "2026-01-28T20:55:38.512Z"
checksum: "779ee843d8e67e8c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(mergeTemplates, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion-1)) Merges several templates into one.

**Input Parameters:**

- template (x-infinica/stream, text/xml) (1-unbounded) Template input. Supports any number of templates.

- makeReferencesAbsolute (x-xsd/boolean)

If true, all URL values in all templates will be converted to absolute URLs before merging. This is useful when templates from different directories are merged, where relative references would work off the wrong base URL after merging.

Default:

false

**Output Parameter:**

- template (text/xml) (0-1) Merged template.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}