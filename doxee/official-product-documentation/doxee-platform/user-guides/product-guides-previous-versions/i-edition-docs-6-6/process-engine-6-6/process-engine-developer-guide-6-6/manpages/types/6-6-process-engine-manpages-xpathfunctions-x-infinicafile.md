---
id: "948cf616-ee03-491e-8daf-398577bd01bc"
title: "x-infinica/file"
slug: "6-6-process-engine-manpages-xpathfunctions-x-infinicafile"
category: "Types"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T16:07:59.371Z"
modified_at: "2025-08-22T17:34:19.966Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-x-infinicafile"
synced_at: "2026-01-28T21:03:42.959Z"
checksum: "89096d7029c8bb05"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

[(Module: Core)](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core)

An object of type `x-infinica/file` identifies a file or a directory on the local file system (including network drives). It corresponds exactly to a URL that starts with file:///. However, while naming standards for URLs (like allowed characters and escape characters) are defined by the relevant RFCs, file names are governed by the underlying OS. Therefore, the type `x-infinica/file` is particularly useful when processing file names or paths that are returned from external tools, while the type `xinfinica/url` is implemented independently of the OS, keeping its behaviour constant across different servers.

**Conversions:**

text/plain → x-infinica/file 

x-infinica/file → text/plain 

x-infinica/file → x-infinica/url 

x-infinica/url → x-infinica/file

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}