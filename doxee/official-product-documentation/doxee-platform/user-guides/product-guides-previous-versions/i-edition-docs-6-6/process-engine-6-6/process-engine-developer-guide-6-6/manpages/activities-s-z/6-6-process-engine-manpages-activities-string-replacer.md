---
id: "2df0b3e4-ea9e-470d-a181-e12e359cce98"
title: "String Replacer"
slug: "6-6-process-engine-manpages-activities-string-replacer"
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
created_at: "2025-08-13T13:42:31.627Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-string-replacer"
synced_at: "2026-01-28T21:02:47.687Z"
checksum: "0f05e5e1ff323548"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(stringReplacer, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Replacing strings in the input stream. All occurrences of the search string will be replaced by the replacement string.

**Input Parameters:**

- input (x-infinica/stream) 

Input stream.

- search (text/plain)

The string that will be replaced.

- replace (text/plain)

The string which will replace the search string.

- charset (text/plain) (0-1)

Charset encoding of the input and output stream. If not set, the system default is used.

**Output Parameter:**

- output (x-infinica/stream) (1-unbounded) 

Output stream.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}