---
id: "9018df1d-bbd3-4c40-a7f3-5a7570c35d3e"
title: "x-infinica/file"
slug: "6-6-process-engine-manpages-xpathfunctions-x-infinicafile-1"
category: "Types"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:07.61Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-x-infinicafile-1"
synced_at: "2026-01-28T20:57:23.605Z"
checksum: "70b92661aea3a775"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

[(Module: Core)](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1)

An object of type `x-infinica/file` identifies a file or a directory on the local file system (including network drives). It corresponds exactly to a URL that starts with file:///. However, while naming standards for URLs (like allowed characters and escape characters) are defined by the relevant RFCs, file names are governed by the underlying OS. Therefore, the type `x-infinica/file` is particularly useful when processing file names or paths that are returned from external tools, while the type `xinfinica/url` is implemented independently of the OS, keeping its behaviour constant across different servers.

**Conversions:**

text/plain → x-infinica/file 

x-infinica/file → text/plain 

x-infinica/file → x-infinica/url 

x-infinica/url → x-infinica/file

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}