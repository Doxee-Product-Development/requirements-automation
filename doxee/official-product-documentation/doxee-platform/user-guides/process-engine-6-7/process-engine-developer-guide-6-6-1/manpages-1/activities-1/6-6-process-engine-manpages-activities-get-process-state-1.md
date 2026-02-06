---
id: "da1db1fe-9061-46e0-9d60-931f33a3ca6a"
title: "Get Process State"
slug: "6-6-process-engine-manpages-activities-get-process-state-1"
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
created_at: "2026-01-07T13:42:13.589Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-get-process-state-1"
synced_at: "2026-01-28T20:55:34.026Z"
checksum: "6446fe343742675c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(getProcessState, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1))

Gets the state of a process. The returned values are the same as the values of the executeProcess activity.

**Input Parameters:**

- processExecutionId (text/plain)

The execution ID of the process instance of which the state will be queried.

- baseUri (x-infinica/url) (0-1)

Optional. Base URI of the process engine which should execute the process. Leave blank to execute the process in the same process engine that calls it.

- block (x-xsd/boolean)

Optional, default is "false". If `true` , the activity will wait until the process is in an end state.

Default:

false

- peek (x-xsd/boolean)

Optional, default is "false". If `true` , the call will not have any side-effects and the queried process state will not be deleted from the map of process states, even if the process has already ended.

Default:

 false

- sleep (x-xsd/integer)

Optional, default is 100. If block is `true` , this is the time in milliseconds that the activity will wait between two queries.

Default:

 100

- paramPrefix (text/plain) (0-1)

Optional. Prefix that will be applied to all output parameters of the queried process.

**Output Parameters:**

- state (text/plain)

Process state. Note that all outputs may be empty if no process is found for the given process execution ID.

- message (text/plain)

The message that the process returned. May be empty.

- processCreatedAt (x-xsd/dateTime)

The creation date/time of the process instance.

- processStartedAt (x-xsd/dateTime)

The start date/time of the process execution.

- processFinishedAt (x-xsd/dateTime)

The finish date/time of the process execution. May be empty.

- processExecutionId (text/plain)

The unique ID of this process instance.

- The output parameters from the queried process' pipeline. If 'paramPrefix' is set, it will be used as the prefix for each parameter name.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}