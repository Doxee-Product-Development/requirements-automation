---
id: "48b32791-dbc3-4fe2-810b-2e0916d8222a"
title: "Zip"
slug: "6-6-process-engine-manpages-activities-zip-1"
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
created_at: "2026-01-07T13:42:17.344Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-zip-1"
synced_at: "2026-01-28T20:56:31.995Z"
checksum: "df01e7598030ed0f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(zip, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

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