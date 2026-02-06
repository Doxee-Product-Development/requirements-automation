---
id: "f6edc8e9-1c43-4a28-958a-97bd90c07673"
title: "Postscript Bundler"
slug: "6-6-process-engine-manpages-activities-postscript-bundler"
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
created_at: "2025-08-13T13:09:04.103Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-postscript-bundler"
synced_at: "2026-01-28T21:02:34.859Z"
checksum: "b09025d7ca28f423"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(postscriptBundler, Module: [PostScript Handler](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-postscript-handler)) 

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