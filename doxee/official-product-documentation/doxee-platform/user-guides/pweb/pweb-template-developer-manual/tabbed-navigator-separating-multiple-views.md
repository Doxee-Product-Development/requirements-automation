---
id: "d820cf87-439c-4c70-b9d0-c4dd943ccb6e"
title: "Tabbed Navigator Separating Multiple Views"
slug: "tabbed-navigator-separating-multiple-views"
category: "Pweb Template Developer Manual"
category_path:
  - "Product guides"
  - "Pweb"
  - "Pweb Template Developer Manual"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-16T17:22:20.455Z"
modified_at: "2026-01-19T14:48:43.708Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/tabbed-navigator-separating-multiple-views"
synced_at: "2026-01-28T20:53:26.389Z"
checksum: "d77c7ba7e15e8b68"
---

Tabbed Navigator control is used to show multiple views with tab control for switching between views. To define a Tabbed navigator use **&lt;tabs&gt;**&nbsp;tag. Every view is defined by **&lt;pane&gt;**&nbsp;tag inside **&lt;tabs&gt;**. A tab's label is defined in **&lt;... label=""&gt;**&nbsp;attribute of **&lt;pane&gt;**&nbsp;tag.&nbsp;

`&lt;!-- Template section --&gt;
&lt;script type="doc-markup" id="doc-markup"&gt;
…
&lt;tabs&gt;
&lt;pane label="First tab"&gt;
        &lt;!-- First view content--&gt;
        ...
&lt;/pane&gt;
&lt;pane label="Second tab"&gt;
        &lt;!-- Second view content--&gt;
        ...
&lt;/pane&gt;
&lt;/tabs&gt;
&lt;/script&gt;`## Programmatically switching panes
To switch selected pane call **selectPane()**&nbsp;function of the pane element:

`&lt;!-- Template section --&gt;
 &lt;script type="doc-markup" id="doc-markup"&gt;
 …
 &lt;tabs&gt;
 &lt;pane label="First tab"&gt;
         &lt;!-- First view content--&gt;
         ...
 &lt;/pane&gt;
 &lt;pane label="Second tab" id="secondTab"&gt;
         &lt;!-- Second view content--&gt;
         ...
 &lt;/pane&gt;
 &lt;/tabs&gt;
 &lt;/script&gt;
 &lt;script type="text/javascript"&gt;
             function goToSecondPane() {
                 var pane = jQuery("#secondTab")[0];
                 pane.selectPane();
             }
 &lt;/script&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}