---
id: "fdb530d3-d48c-41af-ae32-9520336b5fee"
title: "Structure of a Pweb Template"
slug: "structure-of-a-pweb-template"
category: "Pweb Template Developer Manual"
category_path:
  - "Product guides"
  - "Pweb"
  - "Pweb Template Developer Manual"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-16T17:22:25.585Z"
modified_at: "2026-01-21T16:41:13.919Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/structure-of-a-pweb-template"
synced_at: "2026-01-28T20:53:25.766Z"
checksum: "9b9b448e78b26e8f"
---

In its basic form, a&nbsp;Pweb template is an HTML page with embedded data, template, CSS and script components.

The HTML page contains the following sections:&nbsp;

Section

Tag

Description

**Data**

*&lt;script type="doc-data" id="doc-data"&gt;*&nbsp;

The *doc-data* tag contains data in JSON format.

**Template**

*&lt;script type="doc-markup" id="doc-markup"&gt;*

The *doc-markup* tag contains the template in HTML format. Layout meta-language is valid HTML with set of parameters to define blocks and their properties, bind data to them.

**Styles**

*&lt;style type="text/css"&gt;*

*Style* tags define the CSS style of the page.

**Components**

*&lt;script type="text/javascript"&gt;*

*Script* tags define the JavaScript ID component and any third-party components.

**Static content**

The static content section represents the content inside the HTML *&lt;body&gt;*&nbsp;tag. It can contain a link to the online version of the interactive document. This block should be generated on the back-end.

This section is displayed in the following situations: 

- JavaScript is not allowed 

- Gmail (any other web-mailer) strips out JavaScript, tags and embedded images when previewing HTML attachments

> Important

The first four sections (Data, Template, Styles and Components) must be placed within the HTML *&lt;head&gt;* tag. The last section (Static content) belongs to the *&lt;body&gt;* tag.

**Example of ID structure with all five sections:**

`&lt;HTML lang="en"&gt;
&lt;head&gt;
     &lt;meta charset="utf-8" /&gt;
     &lt;meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no"&gt;
     &lt;title&gt;Interactive Document&lt;/title&gt;

	 &lt;!--Data section--&gt;
     &lt;script type="doc-data" id="doc-data"&gt;
         ...
     &lt;/script&gt;
     &lt;!--Data section end--&gt;

&nbsp;	 &lt;!--Template section--&gt;
     &lt;script type="doc-markup" id="doc-markup"&gt;
         …
     &lt;/script&gt;
     &lt;!--Template section end--&gt;
     
     &lt;!--Styles section--&gt;
     &lt;style type="text/css"&gt;
         ...
     &lt;/style&gt;
     &lt;!--Styles section end--&gt;

	&nbsp;&lt;!--Components section--&gt;
     &lt;script type="text/javascript"&gt;
         …
     &lt;/script&gt;
     &lt;!--Components section end--&gt;
&lt;/head&gt;
&lt;body&gt;
     &lt;!--Static content section--&gt;
     &lt;div&gt;...&lt;/div&gt;
     &lt;!--Static content section end--&gt;
&lt;/body&gt;
&lt;/HTML&gt;`> Note

In order to determine the behavior of the template on different screen sizes and orientations, follow the responsive web design approach while defining the template. For more information, see: [Advanced Topics - Responsive Layout with Bootstrap Grid System](/doxee-platform/docs/5-advanced-topics#id-5.AdvancedTopics-h.pxva4uzdi31p).

## Pweb Template
Please, download this file as a starting point for your project.

[](https://cdn.document360.io/ee696953-f8e9-4660-8939-86dc8e02028b/Images/Documentation/Pweb Template.htm?sv=2022-11-02&spr=https&st=2026-01-28T20%3A53%3A25Z&se=2026-01-28T21%3A08%3A25Z&sr=c&sp=r&sig=iU4VHQ71acJLb9lZ9dBQkPVDzSV7jnojMsGewxCkLGw%3D)Pweb Template904.39 KB[**](https://cdn.document360.io/ee696953-f8e9-4660-8939-86dc8e02028b/Images/Documentation/Pweb Template.htm?sv=2022-11-02&spr=https&st=2026-01-28T20%3A53%3A25Z&se=2026-01-28T21%3A08%3A25Z&sr=c&sp=r&sig=iU4VHQ71acJLb9lZ9dBQkPVDzSV7jnojMsGewxCkLGw%3D)The file contains the five sections with the following content:

- **Data **section: empty

- **Template **section: empty

- **Style **section: contains the predefined stylesheets for the components

- **Components **section: contains the code of the [embedded libraries](/doxee-platform/docs/advanced-topics#embedded-libraries)

- **Static content **section: empty

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}