---
id: "0cb07ef0-f4be-4444-a1a2-d8f1a563cc8d"
title: "Credentials"
slug: "6-6-process-engine-manpages-activities-credentials-1"
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
created_at: "2026-01-07T13:42:12.355Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-credentials-1"
synced_at: "2026-01-28T20:55:28.985Z"
checksum: "8b306c1fb75903c0"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(credentials, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1))

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