---
id: "d3c089b5-4323-4790-8602-05027dcdc8b7"
title: "Multi URL Writer"
slug: "6-6-process-engine-manpages-activities-multi-url-writer"
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
created_at: "2025-08-13T11:16:23.066Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-multi-url-writer"
synced_at: "2026-01-28T21:02:25.433Z"
checksum: "bbd3a0a9c89e77c7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(multiUrlWriter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Writes input stream variables to resources. The target URLs are determined by using the specified base URL and resolving the input stream URLs; if an input stream has an absolute URL, only its last component (the resource name) is resolved relative to the base URL.

**Input Parameters:**

- inputs (x-infinica/stream) (1-unbounded)

The input streams to be written to the target location. All streams must have associated URLs.

baseUrl (x-infinica/url)

The URL specifying the target location.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}