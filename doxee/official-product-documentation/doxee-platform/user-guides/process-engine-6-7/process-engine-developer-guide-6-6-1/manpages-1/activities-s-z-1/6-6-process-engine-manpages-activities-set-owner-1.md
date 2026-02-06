---
id: "abbfe848-56a2-401e-be64-335cc3c0af85"
title: "Set Owner"
slug: "6-6-process-engine-manpages-activities-set-owner-1"
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
created_at: "2026-01-07T13:42:16.975Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-set-owner-1"
synced_at: "2026-01-28T20:56:20.463Z"
checksum: "1b09737ffbafdc1d"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(setOwner, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes-1))

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