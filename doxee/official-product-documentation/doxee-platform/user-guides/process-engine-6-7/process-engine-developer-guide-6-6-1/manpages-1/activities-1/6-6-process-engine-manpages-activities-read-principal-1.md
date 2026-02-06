---
id: "2069d2f5-c6f7-4317-9829-2afc74b00635"
title: "Read Principal"
slug: "6-6-process-engine-manpages-activities-read-principal-1"
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
created_at: "2026-01-07T13:42:16.024Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-read-principal-1"
synced_at: "2026-01-28T20:56:17.262Z"
checksum: "60e7b9925f69f756"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(readPrincipals, Module: [User Access](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-user-access-1)) 

Reads principals from the user store.

**Input Parameters:**

- loginName (text/plain) (0-unbounded)

Login name(s) of the requested principal(s).

- id (text/plain) (0-unbounded)

ID(s) of the requested principal(s).

- childrenOf (text/plain) (0-unbounded)

Login name(s) of groups whose children should be read.

- childrenOfId (text/plain) (0-unbounded)

ID(s) of groups whose children should be read.

- parentsOf (text/plain) (0-unbounded)

Login name(s) of principals whose parents should be read.

- parentsOfId (text/plain) (0-unbounded)

ID(s) of principals whose parents should be read.

- recursive (x-xsd/boolean)

Whether child and parent queries should be recursive.

Default:

true

**Output Parameter:**

- principals (text/xml)

Principals as XML structures.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}