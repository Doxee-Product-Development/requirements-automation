---
id: "686efecd-8f46-434b-b4d9-5a1a2a58ac8b"
title: "PDF Signer"
slug: "6-6-process-engine-manpages-activities-pdf-signer-1"
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
created_at: "2026-01-07T13:42:15.284Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-pdf-signer-1"
synced_at: "2026-01-28T20:55:46.491Z"
checksum: "8f70e7b196b093d7"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pdfSigner, Module: [OpenPDF](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-openpdf-1))

Signs a PDF stream using a Java key store. layer2Text and layer4Text can contain parameters in curly braces, e.g. "{signDate}". The following parameters are available:

- "signDate" - The date and time at the moment the PDF was signed.

- "certAttributes" - The certificate's attributes, as key/value pairs, separated by colons.

- "certAttribute:XY" - The certificate's XY attribute value.

**Input Parameters:**

- pdf (x-infinica/stream) 

Input PDF.

- pdfPassword (text/plain) (0-1)

Optional. Necessary if the pdf requires a password.

- keyStore (x-infinica/stream) 

Java keystore.

- alias (text/plain)

Private key alias.

- password (x-infinica/secret-text) (0-1) 

Key store password.

- keyStorePassword (text/plain) (0-1) 

Key store password.

- keyPassword (text/plain) (0-1)

Private key password. If not specified, the key store password is used.

- reason (text/plain) (0-1)

Optional signing reason.

- location (text/plain) (0-1)

Optional signing location.

- layer2Text (text/plain) (0-1) Optional text for layer 2. layer4Text (text/plain) (0-1)

 Optional text for layer 4.

- page (x-xsd/integer)

Page number where the visible signature (if enabled) should be placed. Defaults to 1.

Default:

1

- rectangle (x-xsd/integer) (0-4)

Optional location for the visible signature. A visible signature is created only if this parameter is specified. If set, it must contain 4 integer values specifying the X and Y coordinates of first the lower left and then the upper right corner.

- appearance (text/plain)

Display type of the visible signature. Possible values are "self-signed", "verisign" and "wincer".

Defaults to "self-signed".

Default:

self-signed

- dateFormat (text/plain) (0-1)

Optional date format pattern for the "signDate" parameter in layer2Text and layer4Text. Must be a valid pattern string for java.text.SimpleDateFormat. Defaults to Java's default date time format.

**Output Parameter:**

- pdf (x-infinica/stream) 

Signed PDF.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}