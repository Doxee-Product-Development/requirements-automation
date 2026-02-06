---
id: "dfb4ef4f-a57a-4385-8051-ac5b7da8d638"
title: "PDF Page Remover"
slug: "6-6-process-engine-manpages-activities-pdf-page-remover-1"
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
created_at: "2026-01-07T13:42:15.083Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-page-remover-1"
synced_at: "2026-01-28T20:55:44.902Z"
checksum: "a3236dac11cfe693"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfPageRemover, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1)) Removes individual pages from a PDF.

**Input Parameters:**

- pdf (x-infinica/stream) 

Input PDF.

- password (x-infinica/secret-text) (0-unbounded)

Optional. Necessary if the pdf requires a password.

- pages (x-xsd/integer) (0-unbounded)

Page numbers of pages which should be selected for deletion. If not specified, selection depends on the XPath condition: If a condition is specified, all pages are selected and tested against the condition; if no condition is specified, no pages are selected (and therefore, no pages will be removed).

- condition (text/xpath) (0-1)

XPath condition to test whether a specific page should be deleted. The condition will be evaluated for each selected page and passed that page's number in the variable $pageNumber. Only if the condition evaluates to "true" will the corresponding page be deleted. If no condition is specified, all selected pages will be deleted.

**Output Parameters:**

- pdf (x-infinica/stream) 

Modified PDF.

- pages (x-xsd/integer)

Number of pages in the modified PDF.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}