---
id: "a36d0f73-974f-43aa-9148-788751fe0d63"
title: "Postscript Handler"
slug: "6-6-process-engine-manpages-activities-postscript-handler-1"
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
created_at: "2026-01-07T13:42:15.516Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-postscript-handler-1"
synced_at: "2026-01-28T20:51:33.189Z"
checksum: "17674d29ad3809a5"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(postscriptHandler, Module: [PostScript Handler](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-postscript-handler-1)) 

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