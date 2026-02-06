---
id: "49c87cb8-f04b-458e-85cb-4ee182dbe737"
title: "Advanced Topics"
slug: "advanced-topics"
category: "Pweb Template Developer Manual"
category_path:
  - "Product guides"
  - "Pweb"
  - "Pweb Template Developer Manual"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-16T17:21:34.225Z"
modified_at: "2026-01-19T14:50:18.641Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/advanced-topics"
synced_at: "2026-01-28T20:53:26.699Z"
checksum: "89cb5d66bfc555b0"
---

## Embedded Libraries
ID code includes the following third-party libraries:

Library

Description

[jQuery](http://www.google.com/url?q=http%3A%2F%2Fjquery.com%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNGtx3hYIQpONgUoQvrnRm8YULAPpA)

Common purpose JS helper library

[D3.js](http://www.google.com/url?q=http%3A%2F%2Fd3js.org%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNGRDjOIx27VEdt3kwBvGqXUgHgu7A)

Used for Chart components

[jqGrid](http://www.google.com/url?q=http%3A%2F%2Fwww.trirand.com&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNFtQjjX2RdVptFpNmeACeDWVlTs3A)

Used for Table components

[JSONPath](http://www.google.com/url?q=http%3A%2F%2Fgoessner.net%2Farticles%2FJsonPath%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNG7h6l_S5Hs56deb6LLlP_xzN7wVg)

Used for JSONPath parsing

[bootstrap](http://www.google.com/url?q=http%3A%2F%2Fgetbootstrap.com%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNFcuWE7kcMSjG0AtLf81JzsTheXPQ)

CSS part is used for responsive layout and components styling

[AngularJS](http://www.google.com/url?q=http%3A%2F%2Fangularjs.org%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNFQnYrgZqKaHdJbMRK5SLzP3vZygA)

Used for data binding and custom html elements

Template can leverage all the included libraries to produce rich UI experience and extend ID with new components and elements.

## Responsive Layout with Bootstrap Grid System
Bootstrap is included to ID to allow easy responsive layout building for template.

Use bootstrap [grid system](http://www.google.com/url?q=http%3A%2F%2Fgetbootstrap.com%2Fexamples%2Fgrid%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNHA8TSo-YmGQ5G2vx23FL3r69rZPg)&nbsp;to build a document which fits to all screen sizes for different type of devices.

For example, here you can see two pie charts which will have full screen width on small devices and half screen width (two columns) on medium and large devices, while the table will be always one-columns:

`&lt;!-- Template section --&gt;
 &lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;div class="container"&gt;
                     &lt;div class="row"&gt;
                 &lt;div class="col-sm-12 col-md-6"&gt;
                         &lt;doc-chart-pie …&gt;…&lt;/doc-chart-pie&gt;
                 &lt;/div&gt;
                 &lt;div class="col-sm-12 col-md-6"&gt;
                         &lt;doc-chart-pie …&gt;…&lt;/doc-chart-pie&gt;
                 &lt;/div&gt;
         &lt;/div&gt;
         &lt;div class="row"&gt;
 &lt;doc-table …&gt;…&lt;/doc-table&gt;
         &lt;/div&gt;
 &lt;/div&gt;
 &lt;/script&gt;`More info and examples can be found in bootstrap [help](http://www.google.com/url?q=http%3A%2F%2Fgetbootstrap.com%2Fexamples%2Fgrid%2F&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNHA8TSo-YmGQ5G2vx23FL3r69rZPg).

## Enhanced Data Binding with AngularJS
Simple data binding in ID uses AngularJS. All the data from the Data Section is automatically added to the angular [scope ](http://www.google.com/url?q=http%3A%2F%2Fdocs.angularjs.org%2Fguide%2Fscope&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNHgG90lmqikCjNwoZzMpKN8A-qomA)of the document.

Considering this template have more complex data binding using any AngularJS [directives](http://www.google.com/url?q=http%3A%2F%2Fdocs.angularjs.org%2Fapi%2Fng%2Fdirective&amp;sa=D&amp;sntz=1&amp;usg=AFQjCNFKleDKFDLY95mRZAcJF2XKfDz1Eg).

For example, here you can see a &lt;div&gt; element which is placed into document depending on corresponding value from Data Section:

`&lt;!-- Data section --&gt;
 &lt;script type="doc-data" id="doc-data"&gt;
 {
     …,
     "showGreetings": true
 }
 &lt;/script&gt;
 &lt;!-- Template section --&gt;
 &lt;script type="doc-markup" id="doc-markup"&gt;
         &lt;div ng-if="showGreetings"&gt;Greetings!&lt;/div&gt;
 &lt;/script&gt;`## Styling links in tables
Use **&lt;a&gt;**&nbsp;tag in data to add links to table. Any standard html styling technique can be used for styling.

For example:

`&nbsp;&lt;!-- Data section --&gt;
&lt;script type="doc-data" id="doc-data"&gt;
 {
             "datasetLinks": [

             { "description": "&lt;a href=\"#\" onclick=\"local1(); 
return false;\"&gt;Variable Text with hyperlink, clicking will call a 
javascript function&lt;/a&gt;", "value": "123" },
             { 
"description": "&lt;a href=\"#\" onclick=\"goToOverview(); return 
false;\"&gt;Variable Text with hyperlink, clicking will switch 
tab&lt;/a&gt;", "value": "123" },
             { "description": 
"&lt;a href=\"http://google.com\" target=\"_blank\"&gt;Variable Text 
with hyperlink to a website&lt;/a&gt;", "value": "123" },
             { "description": "Simple text", "value": "123" }
             ]
 }
 &lt;/script&gt;
 &lt;!-- CSS section --&gt;
 &lt;style type="text/css"&gt;
 #tableLinks a {
         color: black;
         font-weight: bold;
 }
         #tableLinks a:hover {
             color: grey;
             font-weight: normal;
         }
 &lt;/style&gt;
 &lt;!-- Template section --&gt;
 &lt;script type="doc-markup" id="doc-markup"&gt;
 &lt;doc-table id="tableLinks" width="100%" doc-data="datasetLinks" doc-sort="true"&gt;
 &lt;doc-col doc-column="dataField: description; width:150; align: left;sortable: true"&gt;Description&lt;/doc-col&gt;
 &lt;doc-col doc-column="dataField: value; width:90; align: right; sortable: true"&gt;Value&lt;/doc-col&gt;
 &lt;/doc-table&gt;
 &lt;/script&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}