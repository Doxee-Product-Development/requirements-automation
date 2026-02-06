---
id: "c7720d50-4bdb-413d-8cd0-91ba4c8dc9ca"
title: "Start Process"
slug: "6-6-process-engine-manpages-activities-start-process"
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
created_at: "2025-08-13T13:37:46.131Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-start-process"
synced_at: "2026-01-28T21:02:47.016Z"
checksum: "0acf2a676ba699a6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(startProcess, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes))

Calls the startProcess operation. This will set a process instance which is in the state CREATED to READY, making it available for execution.

**Input Parameters:**

- baseUrl (x-infinica/url) (0-1)

Base URL of the Process Engine on which the operation should be called.

- executionId (text/plain)

Execution ID of the process instance which should be started.

- timeout (x-xsd/integer) (0-1)

Time to wait for the operation to finish in milliseconds. A value of -1 means it will wait synchronously.

- peek (x-xsd/boolean) (0-1)

Boolean flag which determines whether the process instance should be retained after returning the snapshot, if it was already in an end state.

- prefix (text/plain) (0-1)

The prefix identifies inputs which should be used as process parameters. It is also put at the front of the names of pipeline variables taken from the snapshot and set as output parameters of the activity. If a prefix is set, only inputs with a name which starts with this text are passed as parameters in the operation. This can be used when passing a process parameter which has the same name as one of the fixed inputs.

- *

If the input parameter prefix is not provided, all additional inputs will be passed as process parameters. If there is a prefix, only inputs starting with this prefix are used as parameters, others are ignored.

**Output Parameters:**

- processSnapshot (text/xml)

A snapshot of the created process instance as XML.

- All pipeline variables which are returned with the snapshot are available as output parameters. If the input parameter prefix is provided, the names of all variables are prefixed with the text from this input.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}