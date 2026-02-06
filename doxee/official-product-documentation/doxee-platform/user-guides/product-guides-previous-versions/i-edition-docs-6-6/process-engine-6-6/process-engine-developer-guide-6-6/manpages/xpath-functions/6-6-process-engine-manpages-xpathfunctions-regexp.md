---
id: "3e61f4ae-02cd-447a-9897-3525f4191248"
title: "regexp"
slug: "6-6-process-engine-manpages-xpathfunctions-regexp"
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
created_at: "2025-08-13T15:52:13.53Z"
modified_at: "2025-08-22T17:36:29.777Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-regexp"
synced_at: "2026-01-28T21:03:35.041Z"
checksum: "7816530322a7d0fe"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pattern, string, allGroups)

([http://www.infinica.com/](http://www.infinica.com/), Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Matches a string with a regular expression. If the string doesn't match, it returns null. If it matches and there are no groups in the regular expression, it returns the string. If it matches and there are groups, the result depends on the 'allGroups' parameter: If true, all groups are returned, otherwise only the first group is returned.

**Parameters:**

- **pattern**

The regular expression to use for matching.

Type:

text/plain

- **string**

The string to match with the regular expression.

Type:

text/plain

- **allGroups** (**0-1)**

Whether to return all match groups or only the first. Defaults to 'false'.

Type:

x-xsd/boolean

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}