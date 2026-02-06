---
id: "bd75d06d-dae1-4c8f-9469-c7854caf6543"
title: "URL Writer"
slug: "6-6-process-engine-manpages-activities-url-writer-1"
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
created_at: "2026-01-07T13:42:17.691Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-url-writer-1"
synced_at: "2026-01-28T20:56:29.357Z"
checksum: "767b2b3061126033"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(urlWriter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Writes input data to a resource. If multiple values are provided for the url parameter and only one for the input, the same data is written to all URLs. If multiple values are provided for the input parameter and only one for the url, all the input data is concatenated and written to the url. Otherwise the input

data and url are matched by their index in the list of values. If one of the parameters has more values than the other, the additional values are ignored.

**Input Parameters:**

- input (x-infinica/stream) (1-unbounded)

The input data to be written to the target resource.

- url (x-infinica/url) (1-unbounded)

The URL specifying the target resource.

- createDirs (x-xsd/boolean) (0-1)

Whether to create target directories if they do not yet exist.

Default:

true

- versioning (text/plain) none to ignore versioning, checkin to check the resource in after writing, checkoutCheckin to check out the resource before writing and check it in afterwards, or enable to do the same but also enable versioning if it has not yet been enabled.

Default:

none

- failIfNotVersioned (x-xsd/boolean) (0-1)

If versioning is any other value than none or enable and this value is not explicitly set to false, the activity will fail if the specified resource is not versioned.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}