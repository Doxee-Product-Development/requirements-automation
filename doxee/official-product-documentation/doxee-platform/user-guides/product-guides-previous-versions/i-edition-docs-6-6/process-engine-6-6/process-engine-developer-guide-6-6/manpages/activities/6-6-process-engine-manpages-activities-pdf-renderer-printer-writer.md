---
id: "145d61bc-8cb8-4004-8f1e-eb97088b0a74"
title: "PDF Renderer Printer Writer"
slug: "6-6-process-engine-manpages-activities-pdf-renderer-printer-writer"
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
created_at: "2025-08-13T11:41:09.497Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-renderer-printer-writer"
synced_at: "2026-01-28T21:02:32.257Z"
checksum: "8cb5ef9462b3230b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfRendererPrinterWriter, Module: [PDF Renderer](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdf-renderer)) 

Renders and prints the input PDF.

**Input Parameters:**

- pdf (x-infinica/stream) 

PDF data.

- startPage (x-xsd/integer) (0-1)

First page to print. Defaults to 1.

- endPage (x-xsd/integer) (0-1)

Last page to print. Defaults to the last page in the document.

- printer (text/plain)

Name of the printer to print to.

- copies (x-xsd/integer) Number of copies to print.

Default:

1

- mediaSize (text/plain) (0-1)

Specifies the output media size, e.g. "iso-a4".

- chromaticity (text/plain) (0-1) 

"monochrome" or "color".

- orientation (text/plain) (0-1)

"landscape", "portrait", "reverse-landscape" or "reverse-portrait".

- sides (text/plain) (0-1)

"duplex", "one-sided", "tumble", "two-sided-long-edge" or "two-sided-short-edge"

- tray (text/plain) (0-1)

The index number of a printer tray, or "bottom", "envelope", "large-capacity", "main", "manual", "middle", "side" or "top".

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