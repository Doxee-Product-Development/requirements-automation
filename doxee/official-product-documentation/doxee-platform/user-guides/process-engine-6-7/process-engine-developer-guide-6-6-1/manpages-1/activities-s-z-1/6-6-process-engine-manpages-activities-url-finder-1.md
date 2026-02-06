---
id: "1ddf3fd8-01c2-4a28-b73e-27d6fa43ceda"
title: "URL Finder"
slug: "6-6-process-engine-manpages-activities-url-finder-1"
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
created_at: "2026-01-07T13:42:17.933Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-url-finder-1"
synced_at: "2026-01-28T20:56:27.442Z"
checksum: "0588b93a33522614"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(urlFinder, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1)) 

Finds child URLs of a resource.

**Input Parameters:**

- baseUrls (x-infinica/url) (1-unbounded)

The URL or URLs which will be searched for children.

- pattern (text/plain) (0-1)

An optional regular expression to filter the search results. If this is specified, only URLs matching the expression will be returned.

- recursive (x-xsd/boolean)

Whether to recursively seek into directories. Defaults to false.

Default:

false

- count (text/plain)

Valid values: "one", "all". "one" only finds the first matching URL. "all" finds all matching URLs.

Defaults to "all".

Default:

all

- relative (x-xsd/boolean)

Defaults to false. Set this to true if found URLs should be relative to their baseUrl instead of absolute.

Default:

false

**Output Parameter:**

- urls (x-infinica/url) (1-unbounded) 

The URLs of the found resources.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}