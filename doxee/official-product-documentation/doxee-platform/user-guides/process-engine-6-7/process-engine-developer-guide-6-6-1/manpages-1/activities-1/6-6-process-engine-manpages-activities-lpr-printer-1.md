---
id: "86a17aca-ad74-45ca-8ff3-7d0f83e4ed10"
title: "LPR Printer"
slug: "6-6-process-engine-manpages-activities-lpr-printer-1"
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
created_at: "2026-01-07T13:42:14.137Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-lpr-printer-1"
synced_at: "2026-01-28T20:55:37.829Z"
checksum: "996de68e38febf97"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(lprPrinter, Module: [LPR](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1)) Sends a print job to a queue via lpr.

**Input Parameters:**

- host (text/plain)

Server name or ip address of the print server. May be null, defaults to localhost.

Default:

localhost

- port (x-xsd/integer)

Port on the printer server. May be null, defaults to 515.

Default:

515

- timeout (x-xsd/integer)

Timeout for the tcpip connection. May be null, defaults to 60000 ms.

Default:

60000

- user (text/plain)

User name for the print job. May be null, defaults to nobody.

Default:

nobody

- queue (text/plain)

Name of the printer queue.

- data (x-infinica/stream) (0-1)

Data of the print job. May be a string, bytes, or characters. If it is null, source must be specified.

- source (x-infinica/url) (0-1)

Source URI of the print job data. If it is null, data must be specified.

- length (x-xsd/integer)

Length (in bytes) of the print job. Required if data is null.

Default:

 -1

- jobName (text/plain) (0-1) 

Name of the print job.

- jobId (text/plain) (0-1) 

Id of the print job.

- printingMode (text/plain) (0-1)

The printing mode. Can be one of: PR, CIF, DVI, FORMATTED, PLOT, CONTROLCHARS, DITROFF, POSTSCRIPT, FORTRAN, TROFF, RASTER

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}