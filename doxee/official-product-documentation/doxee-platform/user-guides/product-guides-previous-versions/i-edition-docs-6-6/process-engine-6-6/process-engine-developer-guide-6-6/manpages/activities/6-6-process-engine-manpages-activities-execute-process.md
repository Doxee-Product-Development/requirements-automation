---
id: "bd81c424-82e6-4443-b449-d49fa823f45c"
title: "Execute Process"
slug: "6-6-process-engine-manpages-activities-execute-process"
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
created_at: "2025-08-13T10:49:33.779Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-execute-process"
synced_at: "2026-01-28T21:01:56.326Z"
checksum: "cd70497d3723ce58"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(executeProcess, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core))

Executes a process. Any parameters that are passed and not defined here will be passed to the process. Any parameters that are returned by the process are available as outputs and can be mapped to the process pipeline.

**Input Parameters:**

- processUri (x-infinica/url) 

Process URI.

- baseUri (x-infinica/url) (0-1)

Base URI of the process engine which should execute the process. Leave blank to execute the process in the same process engine that calls it.

- externalId (text/plain) (0-1)

External ID for the new process. If none is specified, the current process' ID is used by default.

- setExternalId (x-xsd/boolean)

Whether to set an external ID on the new process. If this is false, no external ID will be set, even if the externalId parameter was provided.

Default:

true

- timeout (x-xsd/integer) (0-1)

Timeout in millseconds. Activity will return after the timeout has passed, if the process didn't finish before. -1 (which is the default) means synchronous execution.

- cache (x-xsd/boolean) (0-1)

Instructs the process engine to read the process definition from the cache if available.

- threadPool (text/plain) (0-1)

ID of the thread pool in which the process should be executed. If not set, the default thread pool is used.

- autoDispose (text/plain) (0-1)

Auto dispose flag for the new process. Possible values are `never, fetch, endedNotFailed, endedOrFailed`.

- paramPrefix (text/plain) (0-1)

Optional. Prefix that will be stripped away from parameter names before they are passed to the process. This allows the calling process to pass parameters that are called processUri, baseUri, or async. This prefix will also be applied to all output parameters of the called process.

- *

Input parameters for the process.

**Output Parameters:**

- state (text/plain)

State of the executed process.

- message (text/plain)

The message that the process returned. May be empty.

- processCreatedAt (x-xsd/date)

The creation date/time of the process instance.

- processStartedAt (x-xsd/date)

The start date/time of the process execution.

- processFinishedAt (x-xsd/date)

The finish date/time of the process execution. May be empty.

- processExecutionId (text/plain)

The unique ID of the process instance.

- processExternalId (text/plain) (0-1) 

The external the process instance.

- Output parameters returned by the process.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}