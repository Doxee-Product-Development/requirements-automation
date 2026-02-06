---
id: "e295d290-e272-49ea-bb8d-8236c82abe58"
title: "Regex Replacer"
slug: "6-6-process-engine-manpages-activities-regex-replcaer-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:16.066Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-regex-replcaer-1"
synced_at: "2026-01-28T20:56:17.594Z"
checksum: "39caebb025fe09db"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(regexReplacer, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Replacing strings in the input text by fixed value or script. If applying the replace parameter, all matches will be replaced by this value. If applying script and language parameter the matches will be replaced by the computed value of the script. In the script the variable "matcher" (which is the java.util.regex.Matcher) can be used to access the matched value.

**Input Parameters:**

- input (text/plain)

The input text

- pattern (text/plain)

The regular expression.

- replace (text/plain) (0-1)

The string which will replace the matching parts of the input text. (For fixed replacement) 

- script (text/plain) (0-1)

The script as string which will replace the matching parts of the input text. The output of the last expression is returned. (For dynamic     replacement)

- language (text/plain) (0-1)

The script language. (For dynamic replacement)

**Output Parameter:**

- output (text/plain) 

The output text

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}