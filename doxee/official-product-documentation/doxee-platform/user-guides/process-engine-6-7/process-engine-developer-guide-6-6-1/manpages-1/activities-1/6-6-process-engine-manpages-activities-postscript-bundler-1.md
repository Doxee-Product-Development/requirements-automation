---
id: "b4cc13ba-bf8b-4231-be90-6c23dc6f57bd"
title: "Postscript Bundler"
slug: "6-6-process-engine-manpages-activities-postscript-bundler-1"
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
created_at: "2026-01-07T13:42:15.476Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-postscript-bundler-1"
synced_at: "2026-01-28T20:55:48.127Z"
checksum: "431abcc94e723672"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(postscriptBundler, Module: [PostScript Handler](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-postscript-handler-1)) 

Modifies a postscript file.

**Input Parameters:**

- export (text/plain) (0-unbounded)

The bundler jobs to export. May be null.

- saveAndExport (text/plain) (0-unbounded)

The bundler jobs to save and export. Does the same as export but saves to the filesystem before exporting. May be null.

- dispose (text/plain) (0-unbounded)

The bundler jobs to dispose. May be null.

**Output Parameter:**

- output (x-infinica/stream) (0-unbounded) 

The exported bundler jobs. May be null.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}