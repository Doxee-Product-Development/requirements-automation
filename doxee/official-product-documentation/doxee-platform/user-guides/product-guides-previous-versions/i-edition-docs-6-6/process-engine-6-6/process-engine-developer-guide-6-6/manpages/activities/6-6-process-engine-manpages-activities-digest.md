---
id: "f266e68f-ea1e-4b40-b969-4b402fdd8478"
title: "Digest"
slug: "6-6-process-engine-manpages-activities-digest"
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
created_at: "2025-08-13T10:45:34.617Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-digest"
synced_at: "2026-01-28T21:01:54.780Z"
checksum: "b77a2321b6031dc7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(digest, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Calculates message digests (as hex strings) for stream variables.

**Input Parameters:**

- input (x-infinica/stream) (0-unbounded) 

Input streams.

- algorithm (text/plain)

Digest algorithm. Available algorithms are: MD2, MD5, SHA-1, SHA-224, SHA-256, SHA-384, SHA-512, SHA3-224, SHA3-256, SHA3-384, SHA3-512

**Output Parameter:**

- digest (text/plain) (0-unbounded)

Digests as hex strings, one per input.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}