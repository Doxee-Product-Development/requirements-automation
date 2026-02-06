---
id: "b8ea1fb1-7fab-42f9-b45e-0e6a343af199"
title: "String Replacer"
slug: "6-6-process-engine-manpages-activities-string-replacer-1"
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
created_at: "2026-01-07T13:42:17.267Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-string-replacer-1"
synced_at: "2026-01-28T20:56:22.887Z"
checksum: "aaf5d526ca6af3f2"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(stringReplacer, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

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