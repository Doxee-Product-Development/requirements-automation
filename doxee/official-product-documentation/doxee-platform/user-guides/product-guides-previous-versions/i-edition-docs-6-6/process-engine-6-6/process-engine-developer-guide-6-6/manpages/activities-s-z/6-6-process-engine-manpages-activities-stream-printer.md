---
id: "ea4b9820-eb03-4a95-aebe-80072ae55a5c"
title: "Stream Printer"
slug: "6-6-process-engine-manpages-activities-stream-printer"
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
created_at: "2025-08-13T13:38:44.369Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-stream-printer"
synced_at: "2026-01-28T21:02:47.342Z"
checksum: "5988f0b124436f26"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(streamPrinter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Sends the input streams to a printer as a single print job.

**Input Parameters:**

- printer (text/plain)

Name of the printer to print to.

- input (x-infinica/stream) (1-unbounded)

Input streams which will be printed. The specified printer must support the stream format.

- printToStream (x-xsd/boolean)

If this is "true", output will not be printed but written to a stream variable using the printer driver (if the driver supports it). Defaults to "false".

Default:

false

- jobName (text/plain) (0-1)

If specified, sets the name of the printer job.

**Output Parameter:**

- stream (x-infinica/stream) (0-1)

If "printToStream" is "true", this will contain the streamed output from the printer driver.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}