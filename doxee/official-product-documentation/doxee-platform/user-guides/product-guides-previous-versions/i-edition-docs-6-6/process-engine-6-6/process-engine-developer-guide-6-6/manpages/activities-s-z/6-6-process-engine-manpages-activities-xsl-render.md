---
id: "1da9a569-13f4-483d-9365-91ae2b5b8509"
title: "XSL Renderer"
slug: "6-6-process-engine-manpages-activities-xsl-render"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T14:49:51.305Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-xsl-render"
synced_at: "2026-01-28T21:02:55.779Z"
checksum: "e8ed69263071f522"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(xslRenderer, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

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