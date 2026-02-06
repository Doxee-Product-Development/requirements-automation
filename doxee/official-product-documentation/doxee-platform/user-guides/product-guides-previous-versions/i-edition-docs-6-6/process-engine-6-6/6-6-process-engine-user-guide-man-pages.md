---
id: "2b8f5fb2-3a2f-4575-b397-d0019d811b4c"
title: "Man Pages"
slug: "6-6-process-engine-user-guide-man-pages"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T17:05:13.306Z"
modified_at: "2025-08-19T16:51:13.394Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-man-pages"
synced_at: "2026-01-28T21:01:18.245Z"
checksum: "6b940fa61cc415dd"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Due to the modular structure of Process Engine, different installations can have different activities and XPath functions. The various Process Engine modules contain individual documentation for their own components. In most cases users will only need the documentation for the modules they are using. To provide exactly that, the Process Engine is capable of generating a PDF file containing the documentation for all its modules. This document is called man pages. It can be created via the command line interface using the command below. For &lt;file&gt; the path and filename of the PDF to generate must be specified.

`&gt; java -jar infinica-process-engine.jar --man &lt;file&gt;`The generated document lists all included modules. For each of them the activities, XPath functions, data types and loggers as well as the parameters for them are described.

> Note

As of Doxee 5.3, the distribution includes a 'manpages.pdf' file in the documentation directory which describes all modules available to the 	bundler. Additionally, the bundler automatically creates a specific 'manpages.pdf' file along with a new Process Engine bundle, describing only those modules included in that Process Engine bundle.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}