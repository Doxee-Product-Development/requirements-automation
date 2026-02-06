---
id: "da97abd5-2f91-4993-a697-bc9a59596cfb"
title: "Zip"
slug: "6-6-process-engine-manpages-activities-zip"
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
created_at: "2025-08-13T14:51:25.053Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-zip"
synced_at: "2026-01-28T21:02:56.778Z"
checksum: "3b92bcd420bc7d3d"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(zip, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Compresses one or more streams into a Zip stream. If the input streams have base URLs, the path from the URL is used as the file name (and path) of their corresponding entries in the generated Zip archive.

Streams without a base URL are given automatically generated file names based on their MIME type.

**Input Parameters:**

- inputs (x-infinica/stream) (1-unbounded) 

Input streams.

- sourceBaseUrl (x-infinica/url) (0-1)

Common base URL for all input streams. If this is specified, all input streams that have absolute URLs which are sub URLs of this base URL are converted into relative URLs.

- zipStreamUrl (x-infinica/url) (0-1)

The URL (typically, the file name) to assign to the generated Zip stream. Only relevant if targetUrl is not set.

- targetUrl (x-infinica/url) (0-1)

If set, the generated Zip stream is written to this URL instead of being returned as a stream variable.

**Output Parameter:**

- output (x-infinica/stream) (0-1)

Generated Zip stream. Only provided if targetUrl was not set.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}