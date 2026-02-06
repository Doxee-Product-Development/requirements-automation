---
id: "f15036db-38b8-4000-9ff7-0e7577edecfd"
title: "Create Task"
slug: "6-6-process-engine-manpages-activities-create-task-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:12.489Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-create-task-1"
synced_at: "2026-01-28T20:55:28.343Z"
checksum: "64f3626958e38e77"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(createTask, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks-1))

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