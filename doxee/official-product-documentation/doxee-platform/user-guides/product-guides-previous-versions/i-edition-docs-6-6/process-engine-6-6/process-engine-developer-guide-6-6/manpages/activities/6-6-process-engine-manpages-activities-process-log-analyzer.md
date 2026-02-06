---
id: "db3e696d-6a44-46ca-ac14-5fc40ff853ea"
title: "Process Log Analyzer"
slug: "6-6-process-engine-manpages-activities-process-log-analyzer"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T13:13:26.46Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-process-log-analyzer"
synced_at: "2026-01-28T21:02:36.940Z"
checksum: "0b494e40247ef512"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(processLogAnalyser, Module: [Log Analysis](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log-analysis))

Analyses the execution times of process instances based on the Process State and Trace log from the Process Engine logs.

**Input Parameters:**

- url (x-infinica/url) (0-unbounded)

The URL(s) of the log file(s) to be analysed.

- logString (text/plain) (0-1) 

Log entries as String.

- outputUrl (x-infinica/url) (0-1)

The URL to which the resulting XML should be written. If this is null, the XML is not written.

- processState (x-xsd/boolean) (0-1)

Flag which determines whether the Process State log entries should be analyzed.

Default:

true

- trace (x-xsd/boolean) (0-1)

Flag which determines whether the Trace log entries should be analyzed.

Default:

true

- timeFormat (text/plain) (0-1)

The time-format of the log file. Corresponds to the timeformat attribute in the Process Engine log format.

Default:

yyyy-MM-dd HH:mm:ss.SSS

- tracePattern (text/plain) (0-1)

The Trace Pattern of the log file. Corresponds to the pattern configured in the log config of the Process Engine. (regular expressions must be escaped!).

Default:

\[infinica:{executionId}\] {date} {event} {source}

- processStatePattern (text/plain) (0-1)

The Process State Pattern of the log file. Corresponds to the pattern configured in the config of the Process Engine. (regular expressions must be escaped!).

Default:

\[infinica:{executionId}\] {date} New process state: {state}

- limit (x-xsd/integer) (0-1)

The maximum number of processes which should be included in the result. Can be used to keep the resulting XML from becoming too big.

Default:

-1

**Output Parameter:**

- xml (text/xml) (0-1)

An xml containing one node per process instances. The instance node has attributes for the times between state changes and one child node for each process element.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}