---
id: "632cd6f2-be46-43c1-972e-02da62950d8c"
title: "Image Splitter"
slug: "6-6-process-engine-manpages-activities-image-splitter-1"
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
created_at: "2026-01-07T13:42:13.714Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-image-splitter-1"
synced_at: "2026-01-28T20:55:34.998Z"
checksum: "465ef3560bb0ce03"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(imageSplitter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Splits a bitmap image into multiple smaller bitmaps suitable for using on several pages.

For splitting SVG images, use the XSL provided at infinica://resources/xsl/split_svg.xsl.

The splitter outputs an XML that describes the result (number of rows, columns, and total pages) and the list of images as streams and URLs.

**Input Parameters:**

- image (x-infinica/stream) 

The source image.

- pageWidth (x-xsd/integer)

Desired page width in pixels.

- pageHeight (x-xsd/integer)

Desired page height in pixels.

- leftWidth (x-xsd/integer)

The width of the left border area within the image.

Default:

0

- rightWidth (x-xsd/integer)

The width of the right border area within the image.

Default:

 0

- topHeight (x-xsd/integer)

The height of the top border area within the image.

Default:

 0

- bottomHeight (x-xsd/integer)

The height of the bottom border area within the image.

Default:

0

- repeatLeft (x-xsd/boolean)

Decides whether the left border should be repeated on each page.

Default:

false

- repeatRight (x-xsd/boolean)

Decides whether the right border should be repeated on each page.

Default:

false

- repeatTop (x-xsd/boolean)

Decides whether the top border should be repeated on each page.

Default:

false

- repeatBottom (x-xsd/boolean)

Decides whether the bottom border should be repeated on each page.

Default:

false

- splitX (x-xsd/integer) (0-unbounded)

The x-coordinates (in ascending order) where vertical page breaks are preferred. Page breaks will happen at these coordinates, unless the space between two of them is too large for the page size, in which case an arbitrary page break is added.

- splitY (x-xsd/integer) (0-unbounded)

The y-coordinates (in ascending order) where horizontal page breaks are preferred. Page breaks will happen at these coordinates, unless the space between two of them is too large for the page size, in which case an arbitrary page break is added.

- imageFormat (text/plain)

- The format that is used to save the resulting images.

Default:

png

**Output Parameters:**

- result (text/xml)

A description of the split result.

- imgData (x-infinica/stream) (1-unbounded) 

Images as input streams.

- imgUrls (x-infinica/url) (1-unbounded) 

Images as data: URLs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}