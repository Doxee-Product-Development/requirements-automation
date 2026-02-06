---
id: "137ae735-1da0-42c9-a227-f8591eb8a1bc"
title: "Zip4j"
slug: "6-6-process-engine-manpages-activities-zip4j-1"
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
created_at: "2026-01-07T13:42:17.307Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-zip4j-1"
synced_at: "2026-01-28T20:56:32.847Z"
checksum: "9ac58d067b9ee29b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(zip4j, Module: [Zip4j](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-zip4j-1))

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