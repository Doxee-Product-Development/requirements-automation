---
id: "ce5ff3a9-d910-4bb2-80ae-2bc4d26a728e"
title: "Set Task Principals"
slug: "6-6-process-engine-manpages-activities-set-task-principals"
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
created_at: "2025-08-13T13:36:01.028Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-task-principals"
synced_at: "2026-01-28T21:02:46.365Z"
checksum: "aa975e9afce7ca1c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setTaskPrincipals, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks))

Calls a combination of the operations setSupervisors, setPotentialOwners and setBlacklist. Which operations are called depends on the provided input parameters as described below.

**Input Parameters:**

- taskId (text/plain)

ID of the task for which the operation(s) should be called.

- supervisor (text/plain) (0-unbounded)

A list of supervisors to set on the task. If this parameter is provided and not empty, the setSupervisors is called.

- potentialOwner (text/plain) (0-unbounded)

A list of potential owners to set on the task. If this parameter is provided and not empty, the setPotentialOwners is called.

- blacklist (text/plain) (0-unbounded)

A list of users which should not be able to access the task. If this parameter is provided and not empty, the setBlacklist is called.

- clearSupervisors (x-xsd/boolean)

If this boolean flag is set to true, the operation setSupervisors is called with an empty list, removing all existing supervisors. When clearSupervisors is true, the input parameter supervisor will be ignored.

Default:

false

- clearPotentialOwners (x-xsd/boolean)

If this boolean flag is set to true, the operation setPotentialOwners is called with an empty list, removing all existing potential owners. When clearPotentialOwners is true, the input parameter potentialOwner will be ignored.

Default:

false

- clearBlacklist (x-xsd/boolean)

If this boolean flag is set to true, the operation setBlacklist is called with an empty list, removing any existing blacklist. When clearBlacklist is true, the input parameter blacklist will be ignored.

Default:

false

**Output Parameter:**

- task (text/xml)

The modified task after all operations have been called.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}