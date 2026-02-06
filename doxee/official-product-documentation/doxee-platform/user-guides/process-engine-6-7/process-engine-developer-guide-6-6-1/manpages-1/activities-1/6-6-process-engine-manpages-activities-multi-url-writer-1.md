---
id: "b8fc7a3c-fa38-47b1-9a35-eb8440c9682c"
title: "Multi URL Writer"
slug: "6-6-process-engine-manpages-activities-multi-url-writer-1"
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
created_at: "2026-01-07T13:42:14.262Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-multi-url-writer-1"
synced_at: "2026-01-28T20:55:38.799Z"
checksum: "013d717a55db9631"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(multiUrlWriter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Writes input stream variables to resources. The target URLs are determined by using the specified base URL and resolving the input stream URLs; if an input stream has an absolute URL, only its last component (the resource name) is resolved relative to the base URL.

**Input Parameters:**

- inputs (x-infinica/stream) (1-unbounded)

The input streams to be written to the target location. All streams must have associated URLs.

baseUrl (x-infinica/url)

The URL specifying the target location.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}