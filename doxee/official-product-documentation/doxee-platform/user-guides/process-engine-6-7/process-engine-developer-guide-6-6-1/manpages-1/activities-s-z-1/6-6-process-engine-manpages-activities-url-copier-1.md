---
id: "16791e35-5ed5-49c3-8f43-2ccf9ef2f3c7"
title: "URL Copier"
slug: "6-6-process-engine-manpages-activities-url-copier-1"
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
created_at: "2026-01-07T13:42:18.097Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-url-copier-1"
synced_at: "2026-01-28T20:56:26.055Z"
checksum: "82ccc1d4f7155e2a"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(urlCopier, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Copies one or more resources to a target resource. If only one resource is specified, the target can be a directory, or a resource which does not exist yet. If the target does not exist, the source is copied and named so that the new URL exactly equals the target URL. If the target is a directory, the source resource is copied into the directory. If multiple resources are specified, the target resource must be an existing directory.

**Input Parameters:**

- sources (x-infinica/url) (1-unbounded) 

The source URL or URLs.

- target (x-infinica/url) 

The target URL. createDirs (x-xsd/boolean) (0-1)

Whether to create target directories if they do not yet exist.

Default:

true

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}