---
id: "345079f0-7da7-41c4-8222-fe9ceed33f05"
title: "Set Task Metadata"
slug: "6-6-process-engine-manpages-activities-set-task-metasata"
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
created_at: "2025-08-13T13:34:05.09Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-task-metasata"
synced_at: "2026-01-28T21:02:45.703Z"
checksum: "5401ab4e08d9be5c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setTaskMetadata, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks))

Calls the setMetadata operation. Creates a task metadata containing all the variables provided through the input parameters starting with metadata_ prefix and sets them on the task with the provided ID 

**Input Parameters:**

- taskId (text/plain)

ID of the task for which to set the metadata.

- * (0-unbounded)

All additional inputs starting with metadata_ prefix will be added to the metadata, others are ignored.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}