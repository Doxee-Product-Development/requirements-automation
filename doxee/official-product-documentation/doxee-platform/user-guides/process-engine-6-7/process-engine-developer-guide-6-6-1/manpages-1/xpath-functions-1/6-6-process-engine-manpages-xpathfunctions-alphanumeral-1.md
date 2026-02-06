---
id: "e62b9e3e-a6a8-4508-9665-aa1d9c2069d3"
title: "alphaNumeral"
slug: "6-6-process-engine-manpages-xpathfunctions-alphanumeral-1"
category: "XPath Functions"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "XPath Functions"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:19.08Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-alphanumeral-1"
synced_at: "2026-01-28T20:56:33.498Z"
checksum: "7b671f0402e78b49"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(value, upperCase)

([http://www.infinica.com/](http://www.infinica.com/), Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Converts an integer number to an alpha numeral string representation.

For example:

- 1 -&gt; A

- 2 -&gt; B

- 26 -&gt; Z

- 27 -&gt; AA

- 28 -&gt; AB

- ...

**Parameters:**

- **value**

Integer value.

Type:

x-xsd/integer

- **upperCase** (**0-1)**

A boolean value specifying whether to return upper case or lower case strings. The default is true, which returns upper case strings.

Type:

x-xsd/boolean

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}