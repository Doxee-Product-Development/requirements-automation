---
id: "556c85cd-d3b5-4da6-aed1-fd757d0b6cde"
title: "Send Message"
slug: "6-6-process-engine-manpages-activities-send-message-1"
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
created_at: "2026-01-07T13:42:16.854Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-send-message-1"
synced_at: "2026-01-28T20:56:19.490Z"
checksum: "b41945b192ab6e56"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(message, Module: [Messaging](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-messaging-1))

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