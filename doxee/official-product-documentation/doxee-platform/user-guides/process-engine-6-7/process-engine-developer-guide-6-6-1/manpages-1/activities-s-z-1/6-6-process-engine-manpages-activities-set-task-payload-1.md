---
id: "ac9379cb-2416-4afe-8268-8a433f89948d"
title: "Set Task Payload"
slug: "6-6-process-engine-manpages-activities-set-task-payload-1"
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
created_at: "2026-01-07T13:42:17.059Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-task-payload-1"
synced_at: "2026-01-28T20:56:21.075Z"
checksum: "6ccd7bb8b299f9ab"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setTaskPayload, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks-1))

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