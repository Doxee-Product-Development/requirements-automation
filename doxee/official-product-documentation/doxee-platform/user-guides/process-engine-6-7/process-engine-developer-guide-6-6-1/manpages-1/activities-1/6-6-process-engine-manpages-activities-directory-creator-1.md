---
id: "8fe95fc3-0e59-4f24-bf07-a68a881aef3b"
title: "Directory Creator"
slug: "6-6-process-engine-manpages-activities-directory-creator-1"
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
created_at: "2026-01-07T13:42:13.058Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-directory-creator-1"
synced_at: "2026-01-28T20:55:30.297Z"
checksum: "eb14f8530511bd72"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(directoryCreator, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Creates directories. For each provided URL, the corresponding directory is created. Also, parent directories are created as necessary if they do not yet exist.

**Input Parameter:**

- url (x-infinica/url) (1-unbounded)

The URL specifying the directory to be created.

**Output Parameter:**

- created (x-infinica/url) (0-unbounded)

The URLs of all the specified directories that were actually created. Directories that already existed are not included in this list.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}