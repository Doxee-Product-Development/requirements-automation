---
id: "021479de-0df1-4667-a346-939a3c8ffac5"
title: "PDF Attachment Embedder"
slug: "6-6-process-engine-manpages-activities-pdf-attachment-embedder"
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
created_at: "2025-08-13T11:17:55.382Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-attachment-embedder"
synced_at: "2026-01-28T21:02:26.072Z"
checksum: "8884465a190f54bd"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfAttachmentEmbedder, Module: PDFBox) Embeds one or more files of any format into a PDF as an attachment **Input Parameters:**

- pdf (x-infinica/stream)

The PDF document to embed into.

- attachments (x-infinica/stream) (1-unbounded) The attachments to embed.

- attachmentNames (text/plain) (0-unbounded)

The names under which the attachments should be embedded. If this input is provided it must have the same number of values as the attachments input. If it is empty, the name is derived from the URI the attachment stream variable is annotated with, if any.

- pdfA (x-xsd/boolean) (0-1)

If this flag is set to true, the activity sets some additional parameters to ensure that in case the input PDF is PDF/A compliant, the output PDF will still be compliant, if possible. The default is true, because the additional settings don't seem to cause problems for PDFs which are not compliant. According to our research PDF/A compliance is possible for PDF/A-3 and PDF/A-4 with arbitrary files and for PDF/ A-2 if the embedded file is also a compliant PDF/A.

Default:

 true

**Output Parameter:**

- pdf (x-infinica/stream)

The resulting PDF document.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}