---
id: "8f3e5654-8215-4b8d-8913-6dbe364bd2c7"
title: "alphaNumeral"
slug: "6-6-process-engine-manpages-xpathfunctions-alphanumeral"
category: "XPath Functions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "XPath Functions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T15:18:36.64Z"
modified_at: "2025-08-22T17:36:29.777Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-alphanumeral"
synced_at: "2026-01-28T21:02:57.773Z"
checksum: "34c0dd06be1c0001"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(value, upperCase)

([http://www.infinica.com/](http://www.infinica.com/), Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

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