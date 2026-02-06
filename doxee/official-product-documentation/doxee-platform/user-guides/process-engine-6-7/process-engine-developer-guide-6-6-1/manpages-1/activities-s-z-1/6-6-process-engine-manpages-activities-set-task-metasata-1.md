---
id: "c564ef37-3a1f-41a3-bbd8-21276cfa5465"
title: "Set Task Metadata"
slug: "6-6-process-engine-manpages-activities-set-task-metasata-1"
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
created_at: "2026-01-07T13:42:17.02Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-task-metasata-1"
synced_at: "2026-01-28T20:56:20.788Z"
checksum: "c32bb4e79db49773"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setTaskMetadata, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks-1))

Calls the setMetadata operation. Creates a task metadata containing all the variables provided through the input parameters starting with metadata_ prefix and sets them on the task with the provided ID 

**Input Parameters:**

- taskId (text/plain)

ID of the task for which to set the metadata.

- * (0-unbounded)

All additional inputs starting with metadata_ prefix will be added to the metadata, others are ignored.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}