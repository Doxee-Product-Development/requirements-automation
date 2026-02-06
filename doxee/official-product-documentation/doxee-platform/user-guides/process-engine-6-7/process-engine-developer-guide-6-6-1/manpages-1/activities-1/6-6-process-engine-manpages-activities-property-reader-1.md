---
id: "73f121ae-c0f2-4053-bd49-080217a86eed"
title: "Property Reader"
slug: "6-6-process-engine-manpages-activities-property-reader-1"
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
created_at: "2026-01-07T13:42:15.914Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-property-reader-1"
synced_at: "2026-01-28T20:56:15.677Z"
checksum: "af8b461045a8458e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(propertyReader, Module: [Resource Access](/doxee-platform/docs/resource-access-1)) 

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