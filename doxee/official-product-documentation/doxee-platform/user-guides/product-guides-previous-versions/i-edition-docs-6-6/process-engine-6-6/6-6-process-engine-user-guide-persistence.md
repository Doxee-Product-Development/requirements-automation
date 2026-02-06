---
id: "ae2bd14d-5c74-4364-8d4c-4a94f21bccb3"
title: "Persistence"
slug: "6-6-process-engine-user-guide-persistence"
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
created_at: "2025-08-06T17:05:12.924Z"
modified_at: "2025-08-19T16:09:18.373Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-persistence"
synced_at: "2026-01-28T21:01:16.922Z"
checksum: "d61cdf84634ab88f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

By default the Process Engine keeps process instances, pipelines and all associated data only in memory. To ensure that this information is not lost when Process Engine shuts down, a storage for persistent saving of execution data must be configured. If a storage is configured, Process Engine will automatically handle persistence to ensure that:

- A process instance which was created is never lost.

- After a clean shut-down and restart all process execution data is restored.

- A process instance which has finished executing will remain in its state and keep all of its data until it is purged.

These conditions are enforced by the persistence mechanisms of the Engine. They can **not **ensure that all data is preserved if the Engine is shut down in an unclean way (forced shutdown of machine, power outage, etc.). To avoid data loss and inconsistent states in such scenarios, save points can be defined within a process definition.

## Save Points
Save points can be used when a process designer wants to force the Process Engine to persist the state and pipeline of a process instance at specific locations in the process. A save point can be set on any connection in the process definition. If execution reaches a connection with a save point, the current instance is persisted to the storage configured for this Engine. This ensures that if the Process Engine is shut down in an unclean way, after restarting it, the process will continue from the save point or a later position at which the instance has been persisted. In other words, it ensures that no elements before the save point will be executed again.

> Note

A storage only stores the last persisted state, regardless whether it was triggered by a save point or the automatic persistence mechanisms. This means that the state persisted by a save point can be automatically overwritten at any time.

## Storages
To enable persistence, a storage must be defined in the Process Engine configuration. There are three types of storages which can be used:

- File Storage: Stores process instances as files on the local file system.

- SQL Database Storage: Stores process instances as rows in tables of a SQL database.

- MongoDB Storage: Stores process instances as BSON documents in a MongoDB document store.

The storages are also used by the wait state manager for persisting wait states and by the task manager for persisting tasks. Those currently do not support all three types of storages.

How to configure these storages is described in detail in the Process Engine Administration Reference.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}