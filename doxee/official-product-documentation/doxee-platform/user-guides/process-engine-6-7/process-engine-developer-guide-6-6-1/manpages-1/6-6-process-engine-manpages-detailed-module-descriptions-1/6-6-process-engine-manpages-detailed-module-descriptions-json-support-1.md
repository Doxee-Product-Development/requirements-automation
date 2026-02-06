---
id: "62ec5925-ce85-43d3-bf43-6b7d7db0489c"
title: "JSON Support"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-json-support-1"
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
created_at: "2026-01-07T13:42:10.015Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-json-support-1"
synced_at: "2026-01-28T20:55:13.279Z"
checksum: "89cb1699d7b75a07"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides a JSON data type with conversions to text and XML types.

Type:	

[application/json](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-applicationjson-1)

Please be aware that the JSON format is simpler than the XML format and cannot fully and unambiguously represent every possible XML document. Conversions between JSON and XML therefore have certain limitations, and converting from JSON to XML and back to JSON, or from XML to JSON and back to XML, may produce a result that is not exactly the same as the original document.

In particular, unlike XML, JSON does not distinguish between attributes and elements. When converting an XML element that contains both attributes and sub elements to JSON, the distinction between attributes and elements is lost. If attributes and elements share the same name, the JSON representation will not be able to keep their values separate. Also, when converting back to XML, all original attributes and elements will be converted to either attributes or elements.

This module is based on the Jackson library.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}