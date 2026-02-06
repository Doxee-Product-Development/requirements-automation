---
id: "20c744dd-5b0d-434c-9650-74f41f7bb13c"
title: "Composer Log Analyser"
slug: "6-6-process-engine-manpages-activities-composer-log-analyser-1"
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
created_at: "2026-01-07T13:42:12.62Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-composer-log-analyser-1"
synced_at: "2026-01-28T20:55:26.327Z"
checksum: "85c78c6b7f35eefe"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(composerLogAnalyser, Module: [Log Analysis](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log-analysis-1)) Analyses Composer logs for the performance of operations and resources.

**Input Parameters:**

- url (x-infinica/url) (0-unbounded) 

The URL(s) of the log file(s).

- logString (text/plain) (0-1) 

Log entries as String.

- outputUrl (x-infinica/url) (0-1)

The URL to which the resulting XML should be written. If this is null, the XML is not written.

- prefix (text/plain) (0-1)

A regular expression which represents the first part of the log line up to the actual message. Can beused for adapting to various log4j patterns.

Default:

.*

- suffix (text/plain) (0-1)

A regular expression which represents the last part of the log line after the actual message. Can beused for adapting to various log4j patterns.

Default:

.*

- limit (x-xsd/integer) (0-1)

The maximum number of log entries which should be included into the result.

Default:

 -1

**Output Parameter:**

- xml (text/xml) (0-1)

An XML containing one node per operation present in the logs. The operations contain attributes for the performance numbers and child nodes for all the resources the operation was used for.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}