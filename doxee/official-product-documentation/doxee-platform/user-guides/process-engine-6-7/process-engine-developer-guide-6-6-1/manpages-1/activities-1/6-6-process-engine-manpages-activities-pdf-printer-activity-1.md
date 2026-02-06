---
id: "e500c258-5b59-4c07-b4d5-0287360c9b1a"
title: "PDF Printer Activity"
slug: "6-6-process-engine-manpages-activities-pdf-printer-activity-1"
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
created_at: "2026-01-07T13:42:15.119Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-printer-activity-1"
synced_at: "2026-01-28T20:55:45.233Z"
checksum: "c0b2f32823ec232d"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfboxPrinterWriter, Module: [PDFBox](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-pdfbox-1))

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