---
id: "892231a6-2400-4465-a3af-3681b763478e"
title: "Stream Printer"
slug: "6-6-process-engine-manpages-activities-stream-printer-1"
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
created_at: "2026-01-07T13:42:17.228Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-stream-printer-1"
synced_at: "2026-01-28T20:56:22.539Z"
checksum: "db525436b14977d1"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(streamPrinter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

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