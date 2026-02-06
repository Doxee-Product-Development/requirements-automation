---
id: "d563063c-77c7-4d30-9a35-a7659da5ebb4"
title: "Images"
slug: "6-6-business-designer-user-guide-images"
category: "Business Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Business Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-13T15:17:56.668Z"
modified_at: "2025-11-18T10:37:44.835Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-business-designer-user-guide-images"
synced_at: "2026-01-28T21:00:11.114Z"
checksum: "bb3ba8a5b51a6e45"
---

Navigate to other release versions of Doxee Platform Business Designer

[6.6](https://docs.doxee.com/docs/en/business-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/business-designer-6-7)

## Insert image, formats
To insert an image, drag an image element from the palette onto the template, then double- click the image frame and select the image file (see also Quick Start Guide, [Insert images](/doxee-platform/docs/6-6-business-designer-user-guide-create-and-edit-templates-short-instruction-guide#insert-images))

The Business Designer supports a wide range of image formats. The editor can display the usual standard formats (e.g. JPEG, GIF and PNG). However a rendered document can also contain other formats like SVG.

If an image format cannot be displayed by the editor, only a placeholder icon is displayed instead of the image.

The list of supported formats depends on the selected PDF renderer. The formats supported by the existing FOP render engine are:

- GIF

- BMP

- EPS

- JPEG

- PNG

- SVG

- TIFF

- EMF

## Image properties
Under *Style &amp; Properties *&lt; *Advanced *you can set image attributes:

*Area Dimension*

content-width or content-height: width and height of the image (as in *image*). The original image size is applied with "auto". In order to keep the aspect ratio the same, just change either the width or the height, the attribute scaling (corresponds to lock symbol under *image*) must be set to "uniform".

*Miscellaneous*

src: Location of the image file (corresponds to source under *image*) - a relative path is stored. If the location of the file changes, enter the new path here.

The image element can be used as a "semi-dynamic" element by specifying the image file as XPath string. This allows to use different image files for the same picture element depending on dynamic data. In this case the Business Designer ignores the specification in the src- attribute of each image.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}