---
id: "d665278d-eee7-4c6e-8243-dfc254200807"
title: "Read Principal"
slug: "6-6-process-engine-manpages-activities-read-principal"
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
created_at: "2025-08-13T13:23:14.576Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-read-principal"
synced_at: "2026-01-28T21:02:39.899Z"
checksum: "c298b292e1b94507"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(readPrincipals, Module: [User Access](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-user-access)) 

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