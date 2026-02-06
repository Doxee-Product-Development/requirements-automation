---
id: "c8e41e21-1ff0-4091-a530-d18b5445d6a2"
title: "Set Owner"
slug: "6-6-process-engine-manpages-activities-set-owner"
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
created_at: "2025-08-13T13:33:05.547Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-owner"
synced_at: "2026-01-28T21:02:45.378Z"
checksum: "df12a469060d3862"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setOwner, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes))

Sets the process owner. An optional executionId can be specified to set the owner of another process.

Otherwise, the owner of the executing process itself will be set.

**Input Parameters:**

- owner (text/plain)

Login name of the new owner principal (a user or a group). May be empty to make the process have no owner.

- executionId (text/plain) (0-1) 

Execution ID.

- baseUri (x-infinica/url) (0-1)

Base URI of the process engine in which the target process is running.

- user (text/plain) (0-1) 

User name.

- password (x-infinica/secret-text) (0-1) 

Password.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}