---
id: "dbbc58fe-f305-4a4c-b513-d085d01f4d2b"
title: "Release Lock"
slug: "6-6-process-engine-manpages-activities-release-lock"
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
created_at: "2025-08-13T13:26:34.079Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-release-lock"
synced_at: "2026-01-28T21:02:40.555Z"
checksum: "53a0fe8447c97a75"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(lockReleaser, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Releases a lock for a filesystem resource. This is only possible if the filesystem for the identified resource supports an unlock operation. Currently this operation is only supported if the resource is accessed via webdav

**Input Parameter:**

- url (x-infinica/url)

The URL of the file to be unlocked.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}