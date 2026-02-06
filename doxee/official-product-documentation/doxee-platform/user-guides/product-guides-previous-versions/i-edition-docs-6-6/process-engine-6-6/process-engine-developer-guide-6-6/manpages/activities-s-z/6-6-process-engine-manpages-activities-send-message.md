---
id: "9a41d577-abaa-444f-9e61-b195d1bf462a"
title: "Send Message"
slug: "6-6-process-engine-manpages-activities-send-message"
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
created_at: "2025-08-13T13:30:47.515Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-send-message"
synced_at: "2026-01-28T21:02:44.363Z"
checksum: "758d1838125ad172"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(message, Module: [Messaging](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-messaging))

Sends a JMS text message to a queue or topic of a JMS message broker.

**Input Parameters:**

- messageClient (text/xml)

An XML configuration for the message client to be used for sending the message. The structure of the XML is described in the Process Engine Administration Reference in the configuration chapter under Message configuration.

- text (text/plain)

The text content for the message.

- paramPrefix (text/plain) (0-1)

Optional. Prefix that will be stripped away from property names before they are passed to the process. This allows the process to pass properties with the same name as other parameters.

- JMSDestinationHeader (text/xml) (0-1)

An XML configuration for the destination which is written to the Header Property JMSDestination.

The format is the same as for the destination in the messageClient XML.

- JMSReplyToHeader (text/xml) (0-1)

An XML configuration for the destination which is written to the Header Property JMSReplyTo. The format is the same as for the destination in the messageClient XML.

- JMSDeliveryModeHeader (x-xsd/integer) (0-1) 

Sets the Header Property JMSDeliveryMode.

- JMSDeliveryTimeHeader (x-xsd/integer) (0-1)

 Sets the Header Property JMSDeliveryTime.

- JMSMessageIDHeader (text/plain) (0-1)

Sets the Header Property JMSMessageID.

- JMSTimestampHeader (x-xsd/integer) (0-1) 

Sets the Header Property JMSTimestamp.

- JMSExpirationHeader (x-xsd/integer) (0-1) 

Sets the Header Property JMSExpiration.

- JMSRedeliveredHeader (x-xsd/boolean) (0-1) 

Sets the Header Property JMSRedelivered.

- JMSPriorityHeader (x-xsd/integer) (0-1) 

Sets the Header Property JMSPriority.

- JMSCorrelationIDHeader (text/plain) (0-1)

Sets the Header Property JMSCorrelationID.

- JMSTypeHeader (text/plain) (0-1)

Sets the Header Property JMSType.

- *

Custom message parameters.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}