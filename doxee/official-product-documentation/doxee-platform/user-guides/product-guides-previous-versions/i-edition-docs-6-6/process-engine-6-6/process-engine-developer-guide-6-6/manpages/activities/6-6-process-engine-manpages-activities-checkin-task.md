---
id: "c8ecfd96-b2ff-4d4d-b24a-36d96adb6ffd"
title: "CheckIn Task"
slug: "6-6-process-engine-manpages-activities-checkin-task"
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
created_at: "2025-08-13T10:35:47.85Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-checkin-task"
synced_at: "2026-01-28T21:01:51.279Z"
checksum: "3b2d931627a15d78"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(checkinTask, Module: [Tasks](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-tasks))

Calls the checkin operation. Checks in the task with the provided ID and sets it to the provided state. 

Only works if the task is checked out.

Input Parameters:

- taskId (text/plain)

ID of the task to check in.

- state (text/plain)

New state the task should be in once it is check in. Valid states are ready or completed

- mayStoreCredentials (x-xsd/boolean) (0-1)

Whether the task should be allowed to store the user's credentials. If the task is configured to do so and this parameter is false, the checkin operation will fail.

Default:

 false

**Output Parameter:**

- task (text/xml)

The checked in task in XML format.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}