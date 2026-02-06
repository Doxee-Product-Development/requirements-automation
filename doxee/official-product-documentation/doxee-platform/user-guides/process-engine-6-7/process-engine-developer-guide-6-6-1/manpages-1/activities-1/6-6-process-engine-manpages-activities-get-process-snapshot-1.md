---
id: "97b1de6f-a76a-45ec-98c0-38a9c8f8df18"
title: "Get Process Snapshot"
slug: "6-6-process-engine-manpages-activities-get-process-snapshot-1"
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
created_at: "2026-01-07T13:42:13.545Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-get-process-snapshot-1"
synced_at: "2026-01-28T20:55:33.704Z"
checksum: "2053885f61fc5227"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(getProcessSnapshot, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes-1))

Calls the getProcessSnapshot operation. Retrieves a snapshot of the process instance with the specified execution ID.

**Input Parameters:**

- baseUrl (x-infinica/url) (0-1)

Base URL of the Process Engine on which the operation should be called.

- executionId (text/plain)

Execution ID of the process instance for which the snapshot should be retrieved.

- peek (x-xsd/boolean) (0-1)

Boolean flag which determines whether the process instance should be retained after returning the snapshot, if it was already in an end state.

- prefix (text/plain) (0-1)

The prefix is put at the front of the name of each pipeline variable taken from the snapshot and set as output parameter of the activity.

**Output Parameters:**

- processSnapshot (text/xml) (0-1)

A snapshot of the created process instance as XML.

- All pipeline variables which are returned with the snapshot are available as output parameters. If the input parameter prefix is provided, the names of all variables are prefixed with the text from this input.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}