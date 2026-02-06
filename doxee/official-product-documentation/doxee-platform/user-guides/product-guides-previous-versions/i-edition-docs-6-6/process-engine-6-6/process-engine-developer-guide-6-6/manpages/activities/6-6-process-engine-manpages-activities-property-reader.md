---
id: "6f7f64f6-f5b3-4706-a8e3-7012a1864a8e"
title: "Property Reader"
slug: "6-6-process-engine-manpages-activities-property-reader"
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
created_at: "2025-08-13T13:17:07.198Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-property-reader"
synced_at: "2026-01-28T21:02:38.242Z"
checksum: "80744dadd9d63f69"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(propertyReader, Module: [Resource Access](/doxee-platform/docs/resource-access)) 

Reads the properties of resources specified by their URLs.

**Input Parameters:**

- url (x-infinica/url) (1-unbounded)

The URLs from which properties will be read.

- properties (text/plain) (0-unbounded)

Optional list of properties that will be returned. Properties should be in the format prefix:name or {uri}name.

- versions (x-xsd/boolean)

Optional. If true, information about versioning will also be retrieved. Defaults to "true".

Default:

 true

- versionDate (x-xsd/dateTime) (0-1)

Optional. If specified, lists only the versions back to the one that was valid at the given date.

**Output Parameter:**

- properties (text/xml) (1-unbounded)

The properties read from the URLs, one XML document for each URL.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}