---
id: "2883fe29-bf5c-4614-b0d0-48ae9bb39725"
title: "Set Task Payload"
slug: "6-6-process-engine-manpages-activities-set-task-payload"
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
created_at: "2025-08-13T13:34:50.533Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-task-payload"
synced_at: "2026-01-28T21:02:46.028Z"
checksum: "902365adab417a54"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setTaskPayload, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks))

Calls the setPayload operation. Creates a task payload containing all the variables provided through the input parameters and sets it on the task with the provided ID 

**Input Parameters:**

- taskId (text/plain)

ID of the task for which to set the payload.

- mergeMode (text/plain)

If there is already a payload for this task, the mergeMode determines whether the old data should be replaced or added to. The possible values are replaceAll, addAndAppend and addAndReplace.

Default:

replaceAll

- prefix (text/plain) (0-1)

The prefix identifies inputs which should be set as part of the payload. If a prefix is set, only inputs with a name which starts with this text are added to the payload. This can be used when setting payload data which has the same name as one of the fixed inputs.

- * (0-unbounded)

If the input parameter prefix is not provided, all additional inputs will be added to the payload. If there is a prefix, only inputs starting with this prefix are used for the payload, others are ignored.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}