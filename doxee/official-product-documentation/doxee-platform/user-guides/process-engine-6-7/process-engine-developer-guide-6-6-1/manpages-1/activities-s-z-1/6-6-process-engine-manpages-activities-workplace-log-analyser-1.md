---
id: "8e0503a4-5276-4f32-bda1-2bb663ab7a7f"
title: "Workplace Log Analyser"
slug: "6-6-process-engine-manpages-activities-workplace-log-analyser-1"
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
created_at: "2026-01-07T13:42:17.524Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-workplace-log-analyser-1"
synced_at: "2026-01-28T20:56:30.678Z"
checksum: "421e2c5d3a468387"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(workplaceLogAnalyser, Module: [Log Analysis](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log-analysis-1))

Analyses Workplace logs for performance. There are 4 types of log entries: The type taskManager contains performance numbers for calls to Task Manager. The type processEngine contains performance numbers for calls to the Process Engine. The type humanTask contains performance numbers for the execution of Human Tasks. The type browserStatistics contains the performance numbers for requests and time stamps for various points during processing of the requests.

**Input Parameters:**

- url (x-infinica/url) (0-unbounded) 

The URL(s) of the log file(s).

- logString (text/plain) (0-1) 

Log entries as String.

- outputUrl (x-infinica/url) (0-1)

The URL to which the resulting XML should be written. If this is null, the XML is not written.

- taskManager (x-xsd/boolean) (0-1)

Flag which determines whether the entries of type taskManager should be included in the result.

Default:

true

- processEngine (x-xsd/boolean) (0-1)

Flag which determines whether the entries of type processEngine should be included in the result.

Default:

true

- humanTask (x-xsd/boolean) (0-1)

Flag which determines whether the entries of type humanTask should be included in the result.

Default:

true

- browserStatistics (x-xsd/boolean) (0-1)

Flag which determines whether the entries of type browserStatistics should be included in the result.

Default:

true

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

An XML containing one node per log entry type. The children of each type represent different operations and contain min, max and average performance numbers.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}