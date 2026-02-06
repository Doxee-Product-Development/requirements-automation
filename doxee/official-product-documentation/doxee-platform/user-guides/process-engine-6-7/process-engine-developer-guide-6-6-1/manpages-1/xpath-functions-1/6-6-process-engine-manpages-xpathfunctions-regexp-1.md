---
id: "38269e46-c442-4674-98e7-c37a2520c096"
title: "regexp"
slug: "6-6-process-engine-manpages-xpathfunctions-regexp-1"
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
created_at: "2026-01-07T13:42:20.365Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-regexp-1"
synced_at: "2026-01-28T20:56:47.222Z"
checksum: "19dd9626b2edda15"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(pattern, string, allGroups)

([http://www.infinica.com/](http://www.infinica.com/), Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

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