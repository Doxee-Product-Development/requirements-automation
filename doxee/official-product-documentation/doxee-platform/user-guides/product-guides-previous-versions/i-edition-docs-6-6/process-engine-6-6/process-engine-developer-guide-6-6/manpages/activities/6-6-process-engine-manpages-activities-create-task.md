---
id: "f3f55df9-7f93-4411-ab05-7e86c3ee4ea0"
title: "Create Task"
slug: "6-6-process-engine-manpages-activities-create-task"
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
created_at: "2025-08-13T10:40:39.168Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-create-task"
synced_at: "2026-01-28T21:01:52.897Z"
checksum: "6b29c5096e8f34ae"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(createTask, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks))

Calls the createTask operation. This will create a new task and return its XML representation.

**Input Parameters:**

- type (text/plain) 

The task type.

- externalId (text/plain) (0-1)

An external ID to set on the task.

- name (text/plain) (0-1) 

The task name.

- description (text/plain) (0-1) 

The task description.

- priority (x-xsd/integer) (0-1)

 The task priority.

- potentialOwner (text/plain) (0-unbounded)

A list of potential owners to set on the task.

- supervisor (text/plain) (0-unbounded)

A list of supervisors to set on the task.

- blacklist (text/plain) (0-unbounded)

A list of users which should not be able to access the task.

- storeCredentialsOnCompletion (x-xsd/boolean) (0-1)

Whether the task should store the user's credentials when checked in. This requires that a key pair is configured for the task manager.

Default:

false

**Output Parameter:**

- task (text/xml)

The created task in XML format.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}