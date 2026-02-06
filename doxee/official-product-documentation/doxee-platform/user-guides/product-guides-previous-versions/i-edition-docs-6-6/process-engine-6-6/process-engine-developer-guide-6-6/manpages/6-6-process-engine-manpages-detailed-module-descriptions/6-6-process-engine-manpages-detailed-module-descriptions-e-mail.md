---
id: "dea57163-c123-4eed-9e8e-e7bf045c9dcd"
title: "E-Mail"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-e-mail"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T09:32:25.674Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-e-mail"
synced_at: "2026-01-28T21:01:39.731Z"
checksum: "060d45c76ef770a1"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides an activity for sending emails via an SMTP server.

Activity:	

[Email Writer](/doxee-platform/docs/email-writer)

## Server Configuration
To send an email message, at least the host name or IP address of an SMTP server must be specified.

Optionally, a port, a user name and a password may be specified as well. If no port is specified, the default SMTP port is used. If user name and a password are provided, they are used to authenticate against the SMTP server, otherwise no authentication is used.

## Message Structure
Messages have a subject, one optional "FROM" address and any number of "TO", "CC" and "BCC" addresses.

Multiple addresses can be specified as separate strings, or, separated by commas, as a single string.

The message content can be provided as a plain text string or as HTML, or both. Mails are sent as multipart messages.

## Attachments
Attachments are provided as "x-infinica/stream", the stream's binary content is used directly as the attachment's content. The stream's MIME type and base URI are used for the attachment type and file name, if specified.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}