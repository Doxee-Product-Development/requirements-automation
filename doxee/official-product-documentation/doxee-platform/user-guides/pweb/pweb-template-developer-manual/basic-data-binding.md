---
id: "2cb193ad-8b66-4aac-9c90-5f85a2dbbfd5"
title: "Basic Data Binding"
slug: "basic-data-binding"
category: "Pweb Template Developer Manual"
category_path:
  - "Product guides"
  - "Pweb"
  - "Pweb Template Developer Manual"
status: "published"
content_type: "block"
version: 4
public_version: 4
created_at: "2025-12-16T17:22:56.076Z"
modified_at: "2026-01-16T12:54:49.316Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/basic-data-binding"
synced_at: "2026-01-28T20:53:26.078Z"
checksum: "a7b81a0ae6db074e"
---

Any data values placed in the Data section can be bound to any location in the template.

> Tip

Use [***path.to***](http://path.to)***.data.value*** anywhere in the template to place the data value section.

## Inline Data Binding
**Example:**

`&lt;!--Data section --&gt;
&lt;script type="doc-data" id="doc-data"&gt;
        {
                "users": [
                        {"firstname": "Mary", "lastname", "Hamill"},
                {"firstname": "Lucy", "lastname", "Clark"}
                ]
        }
&lt;/script&gt;
&lt;!--Template section-&gt;
&lt;script type="doc-markup" id="doc-markup"&gt;
&lt;div&gt;
        Hello, users[1].firstname users[1].lastname!
&lt;div&gt;
&lt;/script&gt;
will result HTML:
&lt;div&gt;
        Hello, Lucy Clark!
&lt;div&gt;`## Multi-line Summary
This block is implemented using Inline Data Binding. To define a Multi-line Summary, provide summary data in the Data Section and bind it to the HTML table as follows:

`&lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;table rules="rows"&gt;
  &lt;thead&gt;
    &lt;tr&gt;
      &lt;td&gt;&lt;h3 class="blockHeader"&gt;TEMPLATE[0].ACCOUNT.@xLabel&lt;/h3&gt;&lt;/td&gt;
      &lt;td&gt;&lt;/td&gt;
      &lt;td&gt;&lt;h3 class="blockHeader"&gt;(USD)&lt;/h3&gt;&lt;/td&gt;
      &lt;td&gt;&lt;/td&gt;
    &lt;/tr&gt;
  &lt;/thead&gt;
  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH1.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH1.@balance&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH3.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH3.@balance&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH2.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH2.@balance&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH5.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH5.@balance&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH4.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH4.@balance&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
  &lt;/tr&gt;

  &lt;tr&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH6.@month&lt;/td&gt;
    &lt;td&gt;&lt;/td&gt;
    &lt;td&gt;TEMPLATE[0].ACCOUNT.BALANCE_SUMMARY.BALANCE_MONTH6.@balance&lt;/td&gt;
    &lt;td&gt;
      &lt;tr&gt;&lt;/tr&gt;
    &lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;
&lt;/script&gt;`## Custom Logo Coming from the Data File (Base64)
Use Inline Data Binding to bind a Base64-encoded image to the *&lt;img&gt;*&nbsp;tag *src*&nbsp;attribute, as shown below:

` &lt;!--Data section --&gt;
 &lt;script type="doc-data" id="doc-data"&gt;
         { "logoImageData": "data:image/jpg;base64,/9…" }
 &lt;/script&gt;
 &lt;!--Template section→
 &lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;div&gt;
 &lt;img src="logoImageData"/&gt;
 &lt;div&gt;
 &lt;/script&gt;`## Custom HTML Snippet Coming from the Data File
> Important

Inline Data Binding does not allow the use of HTML markup.

Data is treated as string when bound directly, as shown below:

`&nbsp;&lt;!-Template section-&gt;
 &lt;div&gt;
 HTMLData
 &lt;div&gt;
 To bind data with HTML markup HTML Snippet &lt;snippet&gt; tag is used. Example:
 &lt;!--Data section --&gt;
 &lt;script type="doc-data" id="doc-data"&gt;

         { "htmlSnippetData": "&lt;a href=\"http://example.com/\" 
target=\"_blank\"&gt;\n               &lt;div style=\"width: 156px; 
height: 502px;\"&gt;\n&lt;h3 class=\"blockHeader\"&gt;Click to 
buy"&lt;/div&gt;\n&lt;/a&gt;" }
 &lt;/script&gt;
 &lt;!--Template section→
 &lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;div&gt;
 &lt;snippet doc-data="htmlSnippetData"/&gt;
 &lt;div&gt;
 &lt;/script&gt;`### Required Properties
**doc-data**&nbsp;binds the HTML markup from an interactive document's Data section to the component. *JSONPath* is supported for this property.

## Action Button and Link with URL
As ID is an HTML page, buttons and links can be defined either as HTML Snippet (as described in&nbsp;[Custom HTML Snippet Coming from the Data File](#)) or directly, as HTML button/link in the Template section, using Inline Binding:

`&nbsp;&lt;!--Data section --&gt;
 &lt;script type="doc-data" id="doc-data"&gt;
         { "htmlLink": "&lt;http://example.com"}
 &lt;/script&gt;
 &lt;!-Template section-&gt;
 &lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;div&gt;
         &lt;a href="htmlLink" target="_blank"&gt;Click me!&lt;/a&gt;
 &lt;div&gt;
 &lt;/script&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}