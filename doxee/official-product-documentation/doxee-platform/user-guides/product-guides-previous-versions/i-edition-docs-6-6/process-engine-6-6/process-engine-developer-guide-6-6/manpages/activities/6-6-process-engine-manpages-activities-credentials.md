---
id: "672ccf6b-deaa-44bb-8b36-93ebbb1b7602"
title: "Credentials"
slug: "6-6-process-engine-manpages-activities-credentials"
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
created_at: "2025-08-13T10:41:55.451Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-credentials"
synced_at: "2026-01-28T21:01:53.608Z"
checksum: "9e59e8395d1d5438"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(credentials, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core))

Performs operations on the process's credentials registry.

**Input Parameter:**

- operations (text/xml) (1-unbounded)

An XML containing the credentials operations, similar to credentials registry configuration. Root node 'operations' can contain an arbitrary number of 'server' nodes. The attributes of the 'server' node describe the server and consist of:

- host

- port

- protocol

- path

- service

The 'server' node can contain an arbitrary number of operations. Current operation types are setCredentials and setDefaultUser. The setCredentials node has a credentials node containing the credentials information.

The setDefaultUser node has one attribute 'defaultUser' specifying the username of the default user.

Example XML:

`&lt;operations xmlns="http://www.infinica.com/credentials&gt;
  &lt;server host="localhost"&gt;     &lt;setDefaultUser user="test" /&gt;
    &lt;setCredentials&gt;       &lt;passwordCredentials name="test" password="1234" /&gt;
    &lt;/setCredentials&gt;
  &lt;/server&gt;
&lt;/operations&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}