---
id: "b9966f06-8a50-497f-96f5-7bd18b545f3d"
title: "Process Log Reporter"
slug: "6-6-process-engine-manpages-activities-process-log-reporter"
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
created_at: "2025-08-13T13:14:04.725Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-process-log-reporter"
synced_at: "2026-01-28T21:02:37.272Z"
checksum: "e20aac73d7c2ec4b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(processLogReporter, Module: [Process Engine Reporting](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-process-engine-reporting))

This activity reads Process Engine logs, extracts reporting data from them and returns it as 2 text variables containing SQL insert statements.

**Input Parameters:**

- url (x-infinica/url) (1-unbounded)

The URL(s) of the logs to be analyzed.

- tracePattern (text/plain) (0-1)

A pattern for the Process Engine Trace Log containing placeholders for the specific variables.

Default:

{date} \[doxee:{executionId}\] \[{processDefinitionId}\] \[{externalId}\] \[{engineId}\] ${env:USER:doxee01} {event} {source} \(User: {user}\) \(Owner: {owner}\)

- processStatePattern (text/plain) (0-1)

A pattern for the Process Engine State Log containing placeholders for the specific variables.

Default:

{date} \[doxee:{executionId}\] \[{processDefinitionId}\] \[{externalId}\] \[{engineId}\] ${env:USER:doxee01} New process state: {state} \(User: {user}\) \(Owner: {owner}\)

- dataPattern (text/plain) (0-1)

A pattern for the Process Engine Data Log containing placeholders for the specific variables.

Default:

- {date} \[doxee:{executionId}\] \[{processDefinitionId}\] \[{externalId}\] {name} = {value}

- limit (x-xsd/integer) (0-1)

The maximum number of lines to put into one insert statement provided in the outputs. If this number is exceeded, the lines will be split between multiple values in the output variables.

Default:

1000

- traceTable (text/plain) (0-1)

The name of the database table for which the trace insert statements should be created.

Default:

REPORTING_PROCESS_ELEMENT_INSTANCE

- processStateTable (text/plain) (0-1)

The name of the database table for which the state insert statements should be created.

Default:

REPORTING_PROCESS_INSTANCE

- dataTable (text/plain) (0-1)

The name of the database table for which the data insert statements should be created.

Default:

REPORTING_PROCESS_INSTANCE_DISTRIBUTION

contentPattern (text/plain) (0-1)

A pattern for log lines which can occur within a data log value. Must contain exactly one group toidentify the content to extract.

Default:

- \!infinica:traceElement:(.*):com\.infinica.*

- contentKey (text/plain) (0-1)

Name for values identified by the content pattern.

Default:

TEMPLATE_PART

**Output Parameters:**

- trace (text/plain) (0-unbounded)

The trace logs as SQL insert statements. This variable can have multiple values, if the number of found trace logs is larger than the number parameter.

- state (text/plain) (0-unbounded)

The process state logs as SQL insert statements. This variable can have multiple values, if the number of found process state logs is larger than the number parameter.

- data (text/plain) (0-unbounded)

The data logs as SQL insert statements. This variable can have multiple values, if the number of found data logs is larger than the number parameter.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}