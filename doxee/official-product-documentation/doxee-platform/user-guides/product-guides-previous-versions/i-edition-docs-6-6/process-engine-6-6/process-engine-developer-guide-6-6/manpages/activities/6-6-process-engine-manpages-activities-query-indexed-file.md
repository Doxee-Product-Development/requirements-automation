---
id: "2184471b-4d65-48c9-9fbe-8ba0a85e23ad"
title: "Query Indexed File"
slug: "6-6-process-engine-manpages-activities-query-indexed-file"
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
created_at: "2025-08-13T13:18:50.125Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-query-indexed-file"
synced_at: "2026-01-28T21:02:38.571Z"
checksum: "99f60010325e3ca4"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(queryIndexedFile, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion)) 

Fetches information about an indexed file.

**Input Parameters:**

- indexerConfig (text/xml) (0-1)

Indexer configuration. This configuration takes precedence over any indexer that may be provided by the project. If no configuration is specified, the indexer is acquired from the project directory, if possible.

- url (x-infinica/url)

The URL of the file that should be queried.

- recursion (text/plain)

Recursion depth. An integer value or infinite.

Default:

1

**Output Parameter:**

- indexedFile (text/xml) (0-1) The indexed file.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}