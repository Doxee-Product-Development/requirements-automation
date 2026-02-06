---
id: "2044fa02-4306-4860-87c2-2f4dc8a4d97f"
title: "Get Process Snapshot"
slug: "6-6-process-engine-manpages-activities-get-process-snapshot"
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
created_at: "2025-08-13T11:01:44.663Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-get-process-snapshot"
synced_at: "2026-01-28T21:01:59.034Z"
checksum: "b6b4976a0c18be08"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(getProcessSnapshot, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes))

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