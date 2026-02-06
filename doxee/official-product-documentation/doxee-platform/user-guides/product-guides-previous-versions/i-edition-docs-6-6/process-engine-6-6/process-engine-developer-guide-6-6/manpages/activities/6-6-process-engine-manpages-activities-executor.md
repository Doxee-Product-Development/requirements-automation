---
id: "335547c2-a6ac-405a-b7be-093deab04356"
title: "Executor"
slug: "6-6-process-engine-manpages-activities-executor"
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
created_at: "2025-08-13T10:50:25.768Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-executor"
synced_at: "2026-01-28T21:01:57.290Z"
checksum: "a065ae6ec982cf1a"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(executor, Module: Base) 

Executes a system process.

**Input Parameters:**

- cmd (text/plain)

The command to execute. May include parameters if the params property is not specified.

- params (text/plain) (0-unbounded) 

Optional list of parameters.

- workingDir (x-infinica/url) (0-1) 

Optional working directory.

- async (x-xsd/boolean)

Whether the process should be executed asynchronously. Defaults to false.

Default:

false

**Output Parameters:**

- result (x-xsd/integer) (0-1)

Exit code. Only set if the process was executed synchronously.

- stdout (x-infinica/stream) (0-1)

stdout output written by the process. Only set if the process was executed synchronously.

- stderr (x-infinica/stream) (0-1) 

stderr output written by the process. Only set if the process was executed synchronously.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}