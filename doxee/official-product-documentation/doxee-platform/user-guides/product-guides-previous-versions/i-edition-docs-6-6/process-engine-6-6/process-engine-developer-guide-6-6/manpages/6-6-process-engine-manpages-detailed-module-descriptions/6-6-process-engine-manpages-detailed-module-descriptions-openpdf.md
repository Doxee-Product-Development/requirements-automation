---
id: "c000db43-658b-47a9-a12e-8af1c0fa5c0e"
title: "OpenPDF"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-openpdf"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T09:43:59.867Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-openpdf"
synced_at: "2026-01-28T21:01:43.000Z"
checksum: "fcd5e9fc7d304b73"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides activities for using and modifying PDFs via OpenPDF (a fork of iText).

Activities:	

[PDF Bookmark Reader](/doxee-platform/docs/pdf-bookmark-reader), [PDF Bookmark Writer](/doxee-platform/docs/pdf-bookmark-writer), [PDF Concatenator](/doxee-platform/docs/pdf-concatenator-openpdf), [PDF Encryption Getter](/doxee-platform/docs/pdf-encryption-setter), [PDF Encryption Setter](/doxee-platform/docs/pdf-encryption-setter-1), [PDF Flag Setter](/doxee-platform/docs/pdf-flag-setter), [PDF Form Analyzer](/doxee-platform/docs/pdf-form-analyzer), [PDF Form Field Remover](/doxee-platform/docs/pdf-form-field-remover), [PDF Form Filler](/doxee-platform/docs/pdf-form-filler), [PDF Form Reader](/doxee-platform/docs/pdf-form-reader-1), [PDF Page Counter](/doxee-platform/docs/pdf-page-counter), [PDF Page Extractor](/doxee-platform/docs/pdf-page-extractor), [PDF Page Remover](/doxee-platform/docs/pdf-page-remover), [PDF Script Reader](/doxee-platform/docs/pdf-script-reader), [PDF Script Writer](/doxee-platform/docs/pdf-script-writer), [PDF Signer](/doxee-platform/docs/pdf-signer), [PDF Smart Concatenator](/doxee-platform/docs/pdf-smart-concatenator), [PDF Stamper](/doxee-platform/docs/pdf-stamper)

## Font Directories
The `PDF Stamper` activity can reference fonts that are not included in the source PDF. To use these fonts correctly, they must be locally available on the system running Process Engine.

OpenPDF looks for fonts in different directories depending on the operating system.

On Windows:

- *C:\Windows*\fonts 

On Linux:

- /usr/share/X11/fonts

- /usr/X/lib/X11/fonts

- /usr/openwin/lib/X11/fonts

- /usr/share/fonts

- /usr/X11R6/lib/X11/fonts

- /Library/Fonts

- /System/Library/Fonts

## PDF Reader Parameters
Some of the activities in this module have an input and output parameter `pdf-reader`. If a process uses multiple such activities with the same PDFs as their inputs and output, the first one can map the output `pdfreader` to the pipeline and the subsequent ones can use that reader as input instead of the `pdfs` parameter. The functionality is the same when doing this but it can improve performance because there is no need to create a new reader for each activity.

## Stamps
When stamping PDFs via the pdfStamper activity, a structure of the following kind is required to define each stamp:

`&lt;stamp    
 x="10"    
 y="20"    
 condition="xpath"&gt;   
...(stampable items)...
&lt;/stamp&gt;`- x and y: Coordinates in *user units* (typically 1/72") at which the item should be stamped. If they are not specified, the item will be stamped at the corner.

- condition: XPath which will be evaluated for each page of the source PDF, passing the current page number in the $currentPage variable. The item will be stamped only if the condition evaluates to "true".

If no condition is specified, the item will be stamped on all pages.

Each stamp can have an arbitrary number of stampable items, stamped after each other. Stampable items, described below.

## Stampable Items
There are four types of items which can be stamped. All of them can have an attribute "layer" which can have the value "front" or "back", referring to whether the image should be stamped above or below existing content. Other attributes and children are specific to the individual types.

### image
Stamps an image loaded from a provided URL.

Example:

`&lt;image     
layer="back"     
url="testImage.jpg"     
width="30"     
height="40" /&gt;`- url: URL to an image file (GIF, JPEG, PNG, WMF, BMP or TIFF).

- width and height: Dimensions (in user units) at which the image should be stamped. If they are not specified, the image's original size (if known) will be used if "x" and "y" coordinates have been provided; otherwise, the image will be stamped filling the entire page.

### pdf page
Stamps a specific page from a pdf provided to the activity through the input mappings.

Example:

`&lt;pdfPage     
layer="back"     
pdf="testPdf"     
page="1" /&gt;`- pdf: Name of a pipeline variable that contains a pdf reader or a stream variable.

page: Page number of the pdf that is used for stamping. 

### text
Stamps a styled text. The text needs to be provided as content of the "text" node.

Example:

`&lt;text     
layer="front"     
font="Arial"     
size="12"     
angle="0"     
color="#000000"&gt;   
...(text content)...
&lt;/text&gt;`- color: Color of the text as color name or hex code.

- angle: Degree by which the text should be rotated.

- font: Name of the font for the stamped text.

- font-path: Path to the font-file for the stamped text.

- embed-font: Boolean specifying if the font should be embedded in the PDF. Default is false. The font may still be embedded if necessary. If the value is true, an effort is made to embed the font. This may fail due to technical or legal restrictions of the font.

- size: Size of the stamped text. Default is 10.

### rectangle
Stamps a rectangle which can be colored.

Example:

`&lt;rectangle     
layer="front"     
width="50"     
height="50"     
angle="45"     
color="WHITE" /&gt;`- color: Color of the rectangle as color name or hex code.

- angle: Degree by which the rectangle should be rotated.

- width and height: Dimensions of the rectangle

- fill: Boolean specifying if the rectangle should be filled with a color or not. Default is true.

- lineWidth: The width of the rectangle border. Default is 1.

## Form Reader Output
In XML mode, the pdfFormReader activity produces a list of XML elements with the following structure:

`&lt;field name="..." value="..." /&gt;`## Form Analyzer Output
The pdfFormAnalyzer activity produces an XML report with the following structure:

`&lt;fields&gt;
  &lt;field
      name="..."
       type="..."
       page="..."
       left="..."
       top="..."
       right="..."
       bottom="..." /&gt;  ...
&lt;/fields&gt;`Coordinate values for the `left, top, right`, and bottom attributes are provided as floating point values in user units.

Supported field types are:

- checkbox

- combo

- list

- none

- pushButton

- radioButton

- signature

- text

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}