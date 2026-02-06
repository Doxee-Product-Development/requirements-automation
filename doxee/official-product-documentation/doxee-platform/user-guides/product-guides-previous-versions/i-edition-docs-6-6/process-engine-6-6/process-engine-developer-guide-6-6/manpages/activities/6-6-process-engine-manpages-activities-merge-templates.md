---
id: "f01348c9-bdeb-48fa-be6c-37f62343799c"
title: "Merge Templates"
slug: "6-6-process-engine-manpages-activities-merge-templates"
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
created_at: "2025-08-13T11:15:33.889Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-merge-templates"
synced_at: "2026-01-28T21:02:25.130Z"
checksum: "8fa40ef1a9074f9a"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(mergeTemplates, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion)) Merges several templates into one.

**Input Parameters:**

- template (x-infinica/stream, text/xml) (1-unbounded) Template input. Supports any number of templates.

- makeReferencesAbsolute (x-xsd/boolean)

If true, all URL values in all templates will be converted to absolute URLs before merging. This is useful when templates from different directories are merged, where relative references would work off the wrong base URL after merging.

Default:

false

**Output Parameter:**

- template (text/xml) (0-1) Merged template.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}