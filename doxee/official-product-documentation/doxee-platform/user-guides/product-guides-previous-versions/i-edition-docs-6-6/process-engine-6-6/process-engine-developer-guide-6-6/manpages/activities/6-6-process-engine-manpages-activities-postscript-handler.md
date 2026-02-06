---
id: "35bd8733-cef8-48dc-b3a5-3171996f9256"
title: "Postscript Handler"
slug: "6-6-process-engine-manpages-activities-postscript-handler"
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
created_at: "2025-08-13T13:09:41.659Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-postscript-handler"
synced_at: "2026-01-28T21:02:35.196Z"
checksum: "931f25a411cba534"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(postscriptHandler, Module: [PostScript Handler](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-postscript-handler)) 

Modifies a postscript file.

**Input Parameters:**

- postscript (x-infinica/stream) 

The postscript file.

- operations (text/xml) (0-unbounded)

Operations to be performed. May be null.

- printjob (text/plain) (0-unbounded)

Postscript Bundler print jobs for output. May be null.

**Output Parameters:**

- postscript (text/plain) 

The postscript file. pages

- (x-xsd/integer)

The number of pages in the resulting postscript file or print jobs.

- sheets (x-xsd/integer)

The number of sheets in the resulting postscript file or print jobs.

- bytes (x-xsd/integer)

The number of bytes in the resulting postscript file or print jobs.

- docs (x-xsd/integer) (0-1)

The number of documents in the resulting print jobs. May be null.

- postscriptProlog (text/plain) (0-1)

The postscript file prolog. May be null.

- postscriptPages (text/plain) (0-1)

The postscript file pages (as list of single pages). May be null.

- postscriptTrailer (text/plain) (0-1)

The postscript file trailer. May be null.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}