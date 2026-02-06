---
id: "16f14118-3b7a-4a81-b561-6b679959b1cf"
title: "Create temp file"
slug: "6-6-process-engine-manpages-activities-create-temp-file-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:12.415Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-create-temp-file-1"
synced_at: "2026-01-28T20:55:28.664Z"
checksum: "c13fc493e6085cc7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(tempFile, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Generates a temporary file or directory. The file will be deleted after process execution has finished. Temp directories will be created if they do not yet exist. For temp files, only the parent directory will be created, so that the file can be written to.

**Input Parameters:**

- url (x-infinica/url) (0-1)

Optionally specifies the exact URL for the temp file or directory. If this is set, the necessary directories will be created, but no file name will be generated, and the parameters prefix, suffix and parent may not be specified.

- directory (x-xsd/boolean) true to create a directory. Defaults to false.

Default:

false

- shared (x-xsd/boolean) true if the temp file is created in a shared directory. In this case, the temp file will not prevent the process from being relocated to another cluster node.

Default:

 false

- prefix (text/plain) (0-1)

Optional file name prefix. If no URL is specified and no prefix is set, *tmp* will be used as the prefix.

- suffix (text/plain) (0-1)

Optional file name suffix.

- parent (x-infinica/url) (0-1) Optional parent directory.

**Output Parameters:**

- url (x-infinica/url)

The URL of the temp file or directory.

- name (text/plain)

The name of the temp file or directory.

- resourceId (text/plain)

The ID of the created process resource.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}