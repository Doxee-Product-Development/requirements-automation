---
id: "94cfe905-ca87-45dd-811e-925371c8f479"
title: "URL Mover"
slug: "url-mover-1"
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
created_at: "2026-01-07T13:42:17.891Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/url-mover-1"
synced_at: "2026-01-28T20:56:27.764Z"
checksum: "174e0731a5841270"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(urlMover, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

 Moves one or more resources to a target resource. If only one resource is specified, the target can be

 a directory, or a resource which does not exist yet. If the target does not exist, the source is moved

 and renamed so that its new URL exactly equals the target URL. If the target is a directory, the source

 resource is moved into the directory. If multiple resources are specified, the target resource must be an

 existing directory.

 **Input Parameters:**

- sources (x-infinica/url) (1-unbounded)

The source URL or URLs.

- target (x-infinica/url)

The target URL.

-  createDirs (x-xsd/boolean) (0-1)

Whether to create target directories if they do not yet exist.

Default:

 false

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}