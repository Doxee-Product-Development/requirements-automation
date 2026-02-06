---
id: "0cd42d8d-7bc2-4ad6-828b-f7e798e4b1ae"
title: "Set Instance Constants"
slug: "6-6-process-engine-manpages-activities-set-instance-constants-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:16.936Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-instance-constants-1"
synced_at: "2026-01-28T20:56:20.122Z"
checksum: "d1525d8c2cb9d90d"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setInstanceConstants, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes-1))

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