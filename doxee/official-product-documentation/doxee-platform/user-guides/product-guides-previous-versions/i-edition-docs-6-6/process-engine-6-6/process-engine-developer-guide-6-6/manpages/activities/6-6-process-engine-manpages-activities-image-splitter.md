---
id: "98031867-9860-44b8-86ee-8fd3732cee4a"
title: "Image Splitter"
slug: "6-6-process-engine-manpages-activities-image-splitter"
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
created_at: "2025-08-13T11:05:30.37Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-image-splitter"
synced_at: "2026-01-28T21:02:00.359Z"
checksum: "7f4902c6ba66c6a0"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(imageSplitter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

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