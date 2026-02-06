---
id: "8bb4fda4-39d5-4537-a91c-a08f73869f49"
title: "PDF/A Validation"
slug: "6-6-template-designer-user-guide-pdfa-validation-1"
category: "Template Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Template Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-14T16:03:09.007Z"
modified_at: "2025-11-18T10:26:30.578Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-template-designer-user-guide-pdfa-validation-1"
synced_at: "2026-01-28T21:04:27.929Z"
checksum: "03b5e2b7534658ea"
---

Navigate to other release versions of Doxee Platform Template Designer

[6.6](https://docs.doxee.com/docs/en/template-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/template-designer-6-7)

Since version 6.5, the Process Engine supports PDF/A validation using veraPDF, enabling users to validate PDF documents against various PDF/A standards as well as PDF/UA-1. This feature can be used in the Template Designer to create a document preview for PDF/A documents that includes PDF/A validation as a post-processing step.

To do so, create a new preview process, set the format to "PDF" and include the path to an engine that was bundled with the `pdfa` module as well as the path to a PDF/A preview process. As part of this installation, an example process including FOP configuration is provided in *&lt;Template Designer Workspace&gt;/processes/renderPdfA_2b_ipd*.

Once the preview is generated, the validation result can be found in the Events view by double-clicking on the "Preview created" success message.

> Note

If Apache FOP is used to render the PDF/A document, the same PDF/A standard should always be specified in the FOP configuration and the preview process. Only one standard at a time can be rendered and validated.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}