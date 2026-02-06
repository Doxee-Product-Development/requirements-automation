---
id: "49b530cb-3a0e-4b24-888e-6644a2d9a925"
title: "Performance Log Analyzer"
slug: "6-6-process-engine-manpages-activities-performance-log-analyzer-1"
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
created_at: "2026-01-07T13:42:15.437Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-performance-log-analyzer-1"
synced_at: "2026-01-28T20:55:47.810Z"
checksum: "9778d77ef320edb4"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(performanceLogAnalyser, Module: [Log Analysis](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log-analysis-1))

Analyses the performance of internal operations of applications based on performance logging. The result contains minimal, maximal and average exeution times for each operation, grouped by the application type and id.

**Input Parameters:**

- url (x-infinica/url) (0-unbounded)

The URL(s) of the log file(s) to be analysed.

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

The maximum number of performance log entries which should be included into the result.

Default:

-1

**Output Parameter:**

- xml (text/xml) (0-1)

An XML containing one node per application. Each application has one child node for every operation present in the logs.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}