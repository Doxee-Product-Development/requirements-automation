---
id: "2cdd2a9f-3a9d-4dbb-ba08-4a93751b2d90"
title: "Update Index"
slug: "6-6-process-engine-manpages-activities-update-index"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T13:47:50.85Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-update-index"
synced_at: "2026-01-28T21:02:49.377Z"
checksum: "cac7ae5d0f5a1755"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(updateIndex, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion))

Updates the index for a specific file, folder, sub directory, or entire project.

**Input Parameters:**

- indexerConfig (text/xml) (0-1)

Indexer configuration. This configuration takes precedence over any indexer that may be provided by the project. If no configuration is specified, the indexer is acquired from the project directory, if possible.

- url (x-infinica/url)

The URL of the folder or file that should be reindexed.

- reindex (x-xsd/boolean)

Whether to re-calculate the index for the specified URL, even if it is up-to-date. If this is false, the contained file(s) will only be updated if their timestamp in the index database is older than the timestamp in the storage.

Default:

false

**Output Parameter:**

- indexedFolder (x-infinica/url) (0-1) 

The indexed folder.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}