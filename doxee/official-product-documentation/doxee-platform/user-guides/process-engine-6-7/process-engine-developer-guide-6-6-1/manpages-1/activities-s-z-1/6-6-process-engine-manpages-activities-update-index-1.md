---
id: "fae1cc37-bd27-43f4-b307-cbe52913efba"
title: "Update Index"
slug: "6-6-process-engine-manpages-activities-update-index-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:18.26Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-update-index-1"
synced_at: "2026-01-28T20:56:24.674Z"
checksum: "dbde8e1a1e7f4ca6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(updateIndex, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion-1))

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