---
id: "a34b8daf-31f2-4112-b73a-3766ddd546c5"
title: "Email Writer"
slug: "6-6-process-engine-manpages-activities-email-writer"
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
created_at: "2025-08-13T10:46:57.492Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-email-writer"
synced_at: "2026-01-28T21:01:55.434Z"
checksum: "f36e4fd8bb44ef5e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(emailWriter, Module: [E-Mail](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-e-mail)) 

Sends email messages via an SMTP server.

**Input Parameters:**

- host (text/plain)

Server host name or IP.

- port (x-xsd/integer) (0-1)

Optional server port. Defaults to standard SMTP port.

- username (text/plain) (0-1)

Optional server login name.

- password (x-infinica/secret-text) (0-1) 

Optional server password.

- charset (text/plain) (0-1)

Custom charset to be used for the subject, text and HTML contents, for the name parts of email addresses and for the file names of attachments.

- starttls (x-xsd/boolean) (0-1)

Offer SSL/TLS encryption during negotiation. Defaults to false.

Default:

false

- from (text/plain)

"FROM" mail address.

- replyTo (text/plain) (0-unbounded) 

"REPLYTO" mail addresses.

- to (text/plain) (1-unbounded)

"TO" mail addresses.

- cc (text/plain) (0-unbounded)

 "CC" mail addresses.

- bcc (text/plain) (0-unbounded) "

BCC" mail addresses.

- subject (text/plain) 

Email subject.

- text (text/plain) (0-1)

Plain text email content.

- html (text/html) (0-1)

HTML email content.

- userAgent (text/plain) (0-1)

User agent name for the SMTP header. A default name is used if not specified. Set to an empty string to suppress the header entirely.

- sign (x-xsd/boolean) (0-1)

Create a digital signature of the body and include it with the email. Uses SMIME for the signature.

Defaults to false.

Default:

 false

- certificate (x-infinica/xml-node) (0-1)

Reference to a certificate in the configured Key Store. The certificate is used for signing Emails and is required when the sign parameter is set to true.

- encodeAttachmentNames (x-xsd/boolean)

Whether to encode attachment names with the specified charset. This is not a standardised feature and may not be supported by all e-mail clients.

Default:

 false

- attachments (x-infinica/stream, text/xml, text/plain) (0-unbounded)

Attachments provided as a stream. Attachments defined through text or an XML used to be supported as well, but this functionality is deprecated.

- headerPrefix (text/plain) (0-1)

All variables mapped into the activity with a name starting with this prefix, will be used as email headers. The variable name without the prefix is used as the header name and the content as the header value.

Default:

 header_

- *

Any variable starting with the text defined in headerPrefix, will be used as email headers.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}