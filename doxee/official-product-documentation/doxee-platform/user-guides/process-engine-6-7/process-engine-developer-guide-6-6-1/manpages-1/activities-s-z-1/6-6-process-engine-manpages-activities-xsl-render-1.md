---
id: "7c48c22c-2581-4f40-9a36-08f2694a7112"
title: "XSL Renderer"
slug: "6-6-process-engine-manpages-activities-xsl-render-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:17.437Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-xsl-render-1"
synced_at: "2026-01-28T20:56:31.001Z"
checksum: "ffbb351c28159fa7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(xslRenderer, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Renders FO code to a target format by applying an (implicit) XSL transformation.

**Input Parameters:**

- fo (x-infinica/stream) 

FO input.

- baseUri (x-infinica/url) (0-1)

Base URI for the XSL transformation.

- mimetype (text/plain) (0-1)

The mimetype of the rendering result.

- configUrl (x-infinica/url) (0-1) 

URL for xsl config.

**Output Parameter:**

- output (x-infinica/stream) 

The rendered document.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}