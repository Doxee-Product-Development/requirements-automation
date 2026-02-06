---
id: "4cd859a5-ff90-40b7-b3af-4cb3fb9bef8e"
title: "FOP Renderer"
slug: "6-6-process-engine-manpages-activities-fop-renderer"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T10:52:28.283Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-fop-renderer"
synced_at: "2026-01-28T21:01:58.280Z"
checksum: "5389c4ff85ec20cd"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(fopRenderer, Module: [FOP](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-fop)) 

Renders FO input using Apache FOP.

**Input Parameters:**

- fo (x-infinica/stream) 

FO input.

- baseUri (x-infinica/url) (0-1)

Base URI for resolving external references. If this is not specified, the base URI is taken from the FO input stream.

- mimetype (text/plain)

Optional MIME type for output.

Default:

application/pdf

- configUrl (x-infinica/url) (0-1) 

Optional FOP configuration file URL.

- fontConfig (0-1)

Optional font configuration from a project configuration. This may be the actual font configuration, or a URI that points to the configuration file.

- fontsDir (x-infinica/url) (0-1)

Optional directory as base location for fonts.

- strictValidation (x-xsd/boolean)

Whether to use strict validation when parsing the FO code. Defaults to "false".

Default:

 false

- producer (text/plain) (0-1)

Optional producer string to be set in PDF meta data.

- title (text/plain) (0-1)

Optional title string to be set in PDF.

- author (text/plain) (0-1)

Optional author to be set in PDF.

- mimic (text/plain) (0-1)

Optional MIME type for referencing a section of the configuration when generating intermediate format or area tree.

- msgLevel (text/plain) (0-1)

Optional level of messages to be collected from the renderer. Valid values are: NONE, FATAL, ERROR, WARN, INFO, ALL. Default is NONE for maximum performance.

- failOnError (text/plain) (0-unbounded)

If specified, any error type that FOP reports will be matched against the provided list. In case of a match, rendering will fail with the reported error. Useful values are '*' (fail on all errors) or 'imageNotFound' (fail when a referenced image is not found). Default is an empty list, which means that no (recoverable) error will cause the rendering to fail.

- pdfAMode (text/plain) (0-1)

Optional PDF/A mode. Allowed values are "PDF/A-2a", "PDF/A-2b", "PDF/A-2u", "PDF/A-3a", "PDF/ A-3b" and "PDF/A-3u". If specified and the output format is PDF, a PDF/A will be generated.

**Output Parameters:**

- output (x-infinica/stream)

The document rendered from the FO input.

- pageCount (x-xsd/integer) Number of rendered pages.

messages (text/plain) (0-1) Rendering messages.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}