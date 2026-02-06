---
id: "b1dd4b18-f6d4-464e-825a-ac1148b3b0be"
title: "Tasks"
slug: "6-6-process-engine-user-guide-tasks"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T17:05:13.218Z"
modified_at: "2025-08-19T16:50:37.747Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-tasks"
synced_at: "2026-01-28T21:01:17.920Z"
checksum: "edfd1c021d00a0a8"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

A task is a way to delegate the responsibility for performing a certain action to another user or client. Tasks are handled by a task manager, which maintains a list of all active tasks and their states.

## Task Clients
Doxee’s standard client application for handling tasks is Workplace. It presents users with their invidivual task lists and lets them perform tasks by filling out web forms based on the tasks' types.

Process Engine can also act as a task client. Processes may create tasks and wait for their execution by a user before continuing their own operation. Processes may also directly access task lists and check out and edit tasks.

Other applications, including 3rd party and customer tools, can become task clients by accessing the task manager through a SOAP interface.

## Task Attributes
A task has the following attributes:

**ID**

Unique ID by which the task can be identified.

**External ID**

An optional ID to an external entity connected to the task, e.g. the ID of a process that created the task and is waiting for it. Multiple tasks may share the same external ID.

**Type**

The type of task which should be created. Task client applications need the task’s type to determine whether and how to display it and how to let owners edit it. If required, the types can be hierarchical. In this case the levels in the hierarchy should be separated by a dot.

**State**

The task’s current lifecycle state. See [The Task Lifecycle.](/doxee-platform/docs/6-6-process-engine-user-guide-tasks#the-task-lifecycle)

**Priority**

Task priority as an integer number. Higher numbers denote more important tasks. The priority may be used for ordering, filtering and displaying tasks according to their importance.

**Description**

A brief, human readable description of the specific task.

**Creator**

The user who created the task.

**Owner**

The user who is currently the owner of the task, if the task is checked out.

**Creation time stamp**

The date and time at which the task was created.

**Potential owners**

A list of users or groups who may become owners of the task by checking it out.

**Supervisors**

A list of users or groups who are supervisors of the task. They may not check it out (unless they are also potential owners), but may view it and perform maintenance operations.

**Payload**

The task’s data content. The specific values stored in the payload depend on the task’s type the client application handling the task.

**Credentials**

Tasks can store the credentials of the user who completed them. This feature must be explicitly activated on the task, and the task user has to confirm that their credentials are stored (but the task may not be completed if they refuse). The credentials are asymmetrically encrypted with a key provided by the Process Engine and can only be decrypted by the Process Engine or any user in possession of the matching private key.

> Note

Process Engine can only create tasks that store credentials if the Task Manager configuration in `process_engine.xml` defines a key pair to encrypt the credentials.

## The Task Lifecycle
A task has a lifecycle that consists of the following phases:

- created

- ready

- checked out

- completed

- finished

Every task starts out in the `created` state. Once all task details have been configured by the user or client creating the task, its state changes to `ready`.

When a task is `ready`, any of its potential owners may claim the task by checking it out. This changes the task’s state to `checked_out`. While in this state, the task is assigned to a single current owner, the user who checked it out. The owner of a checked out task is free to modify the task’s payload. Checking a task back in unsets the current owner and changes the task’s state, either back to `ready` (in case the task should remain open for further processing) or to `completed`. A completed task is picked up for post processing by the task manager and then updated to its final state, finished. A `finished` task has completed its lifecycle and may be deleted at any point.

## The Task Payload
The creator of a task can specify the task’s initial payload. The payload consists of key/value pairs with typed keys. Which specific keys a task uses depends primarily on the task’s type and the way the task is presented to users by a client application. For example, a task displayed as a web form may have payload providing the initial values for the form’s fields.

When a task is checked out, the task’s current owner may view and edit the payload, e.g. via a web form displayed by the client application. The changed payload content is stored in the task, and after completion the creator of the task may use that content to continue performing its own operations.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}