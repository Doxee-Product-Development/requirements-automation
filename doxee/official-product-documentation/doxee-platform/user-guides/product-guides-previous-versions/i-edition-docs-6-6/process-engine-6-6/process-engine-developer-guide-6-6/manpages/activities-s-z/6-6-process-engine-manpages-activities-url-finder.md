---
id: "b7240765-995d-49d4-bd51-50a1aa5cd62e"
title: "URL Finder"
slug: "6-6-process-engine-manpages-activities-url-finder"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T14:39:01.456Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-url-finder"
synced_at: "2026-01-28T21:02:52.002Z"
checksum: "124f00d71839bb84"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(urlFinder, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base)) 

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