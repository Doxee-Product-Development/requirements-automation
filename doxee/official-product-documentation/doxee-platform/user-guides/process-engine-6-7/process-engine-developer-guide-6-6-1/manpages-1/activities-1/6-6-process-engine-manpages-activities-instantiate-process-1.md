---
id: "d4718373-71ed-410f-b1bb-8af1967dc030"
title: "Instantiate Process"
slug: "6-6-process-engine-manpages-activities-instantiate-process-1"
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
created_at: "2026-01-07T13:42:13.762Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-instantiate-process-1"
synced_at: "2026-01-28T20:55:35.315Z"
checksum: "8c46558b1da482df"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(instantiateProcess, Module: [Processes](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-processes-1))

Calls the instantiate operation. This will create a new process instance and return its snapshot.

**Input Parameters:**

- baseUrl (x-infinica/url) (0-1)

Base URL of the Process Engine on which the operation should be called.

- processUrl (x-infinica/url)

URL of the process definition file from which the process instance is created.

- externalId (text/plain) (0-1)

External ID for the new process. If none is specified, the current process' ID is used by default.

- setExternalId (x-xsd/boolean)

Whether to set an external ID on the new process. If this is false, no external ID will be set, even if the externalId parameter was provided.

Default:

true

- threadPool (text/plain) (0-1)

ID of the thread pool in which the process must be executed.

- cache (x-xsd/boolean) (0-1)

Boolean flag which determines whether the process definition should be cached or not.

- autoDispose (text/plain) (0-1)

Auto dispose flag for the new process. Possible values are never, fetch, endedNotFailed, endedOrFailed.

**Output Parameter:**

- processSnapshot (text/xml)

A snapshot of the created process instance as XML.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}