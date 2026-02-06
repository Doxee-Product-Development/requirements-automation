---
id: "bee3f0fe-9d07-4765-8a4b-f32db943e33c"
title: "Set Instance Constants"
slug: "6-6-process-engine-manpages-activities-set-instance-constants"
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
created_at: "2025-08-13T13:32:20.773Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-instance-constants"
synced_at: "2026-01-28T21:02:45.041Z"
checksum: "c9e715d067979416"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setInstanceConstants, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes))

Calls the setInstanceConstant operation once for each constant provided through the input parameters. This will set constants which are specific to the process instance provided with the specified execution ID.

**Input Parameters:**

- baseUrl (x-infinica/url) (0-1)

Base URL of the Process Engine on which the operation should be called.

- executionId (text/plain)

Execution ID of the process instance for which the constants should be set.

- prefix (text/plain) (0-1)

The prefix identifies inputs which should be set as instance constants. If a prefix is set, only inputs with a name which starts with this text are passed as constants. This can be used when setting a constant which has the same name as one of the fixed inputs.

- transitive (x-xsd/boolean) (0-1)

Whether the set constants should be transitive.

Default:

false

- *

If the input parameter prefix is not provided, all additional inputs will be set as instance constants. If there is a prefix, only inputs starting with this prefix are used as instance constants, others are ignored.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}