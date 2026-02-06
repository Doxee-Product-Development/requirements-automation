---
id: "d87b9e7b-66c3-4183-afe5-691be35071c1"
title: "Zip4j"
slug: "6-6-process-engine-manpages-activities-zip4j"
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
created_at: "2025-08-13T14:51:51.924Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-zip4j"
synced_at: "2026-01-28T21:02:57.118Z"
checksum: "5446393a7394f435"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(zip4j, Module: [Zip4j](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-zip4j))

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

- password (x-infinica/secret-text) (0-1)

If set, the generated Zip stream will be AES encrypted with the specified password.

- compressionLevel (text/plain)

Compression level. Supported values are 'none', 'fastest', 'fast', 'normal', 'maximum' and 'ultra'.

Default:

normal

- encryption (text/plain)

Encryption type and strength. Only applies if a password is also set. Supported values are 'standard', 'aes128' and 'aes256'.

Default:

aes256

- splitSize (x-xsd/integer) (0-1)

Creates a spanned Zip archive consisting of individual files with the specified size limit. Requires that 'targetUrl' is set as well. Must be at least 65536.

**Output Parameter:**

- output (x-infinica/stream) (0-1)

Generated Zip stream. Only provided if targetUrl was not set.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}