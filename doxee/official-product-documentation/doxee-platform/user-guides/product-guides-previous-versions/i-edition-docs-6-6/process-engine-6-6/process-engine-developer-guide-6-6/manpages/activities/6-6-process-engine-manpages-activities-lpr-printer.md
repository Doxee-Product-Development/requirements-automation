---
id: "5eb1ffdf-57be-4d0b-998a-4e9ab93aca60"
title: "LPR Printer"
slug: "6-6-process-engine-manpages-activities-lpr-printer"
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
created_at: "2025-08-13T11:13:12.532Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-lpr-printer"
synced_at: "2026-01-28T21:02:24.470Z"
checksum: "7b7423a541efbc18"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(lprPrinter, Module: [LPR](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base)) Sends a print job to a queue via lpr.

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