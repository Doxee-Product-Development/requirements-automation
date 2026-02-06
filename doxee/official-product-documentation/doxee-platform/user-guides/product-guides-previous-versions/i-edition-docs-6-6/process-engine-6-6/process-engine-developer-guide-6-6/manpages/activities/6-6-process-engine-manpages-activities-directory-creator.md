---
id: "7ade1056-12e5-4055-b226-eec13e2c1e08"
title: "Directory Creator"
slug: "6-6-process-engine-manpages-activities-directory-creator"
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
created_at: "2025-08-13T10:46:21.979Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-directory-creator"
synced_at: "2026-01-28T21:01:55.112Z"
checksum: "98892462fae96c47"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(directoryCreator, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Creates directories. For each provided URL, the corresponding directory is created. Also, parent directories are created as necessary if they do not yet exist.

**Input Parameter:**

- url (x-infinica/url) (1-unbounded)

The URL specifying the directory to be created.

**Output Parameter:**

- created (x-infinica/url) (0-unbounded)

The URLs of all the specified directories that were actually created. Directories that already existed are not included in this list.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}