---
id: "bd59cc3e-4bce-4761-985c-9e1705e33187"
title: "E-Mail"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-e-mail-1"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:09.748Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-e-mail-1"
synced_at: "2026-01-28T20:55:12.007Z"
checksum: "f865e0ab308dbd89"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides an activity for sending emails via an SMTP server.

Activity:	

[Email Writer](/doxee-platform/docs/6-6-process-engine-manpages-activities-email-writer-1)

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