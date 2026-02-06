---
id: "01358785-36f3-4669-aabd-59ffff884f7d"
title: "PDF Printer Activity"
slug: "6-6-process-engine-manpages-activities-pdf-printer-activity"
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
created_at: "2025-08-13T11:40:29.686Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-printer-activity"
synced_at: "2026-01-28T21:02:31.919Z"
checksum: "c806df5eb74d193b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxPrinterWriter, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox))

Prints a PDF document. Each page of the document is rastered and passed to the printer as a bitmap image.

**Input Parameters:**

- pdf (x-infinica/stream) 

PDF document.

- printer (text/plain)

Name of the printer to print to.

- jobName (text/plain) (0-1) 

Name of the printing job.

- copies (x-xsd/integer) Number of copies to print.

Default:

1

- mediaSize (text/plain) (0-1)

Specifies the output media size, e.g. "iso-a4".

Default:

ISO-A4

- chromaticity (text/plain) (0-1)

Colour mode: "monochrome" or "color".

- orientation (text/plain) (0-1)

Page orientation: "landscape", "portrait", "reverse-landscape" or "reverse-portrait".

- autoRotate (x-xsd/boolean)

When printing a PDF document where at least some of the pages have a different orientation than the output paper format, this parameter controls whether such pages should be rotated automatically to match the output orientation. Defaults to "true".

Default:

true

- sides (text/plain) (0-1)

Duplex printing mode: "duplex", "one-sided", "tumble", "two-sided-long-edge" or "two-sided-shortedge"

- tray (text/plain) (0-1)

The index number of a printer tray, or "bottom", "envelope", "large-capacity", "main", "manual", "middle", "side" or "top".

- collate (x-xsd/boolean) (0-1)

Whether the pages of multiple copies should be collated. Defaults to "false".

- quality (text/plain)

Printing quality: "normal", "high" or "draft". Defaults to "normal".

Default:

normal

- autoScale (text/plain)

Whether the output should be automatically scaled to the paper format: "none", "fit" or "shrink".

Default:

none

- printArea (text/plain) (0-1)

Defines which area should be used for printing (and specifically scaling and positioning). Possible values are "page", "printableArea", and "custom". If "custom" is specified, margins must be passed in the parameters customLeft, customRight, customTop and customBottom. Defaults to 'page', or to 'custom' if custom margins have been specified.

- horizontalAlignment (text/plain)

Horizontal alignment within the print area. Possible values are "beginning", "center" and "end".

Default:

beginning

- verticalAlignment (text/plain)

Vertical alignment within the print area. Possible values are "beginning", "center" and "end".

Default:

beginning

- customLeft (x-xsd/float) (0-1)

Left margin in millimetres for the 'custom' print area.

- customRight (x-xsd/float) (0-1)

Right margin in millimetres for the 'custom' print area.

- customTop (x-xsd/float) (0-1)

Top margin in millimetres for the 'custom' print area.

- customBottom (x-xsd/float) (0-1)

Bottom margin in millimetres for the 'custom' print area.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}