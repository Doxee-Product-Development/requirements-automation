---
id: "2dee6b09-6099-4d02-bada-d087c0146475"
title: "Process Definiton Reporter"
slug: "6-6-process-engine-manpages-activities-process-definiton-reporter"
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
created_at: "2025-08-13T13:12:39.115Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-process-definiton-reporter"
synced_at: "2026-01-28T21:02:36.595Z"
checksum: "7d81b9013c30c664"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(processDefinitionReporter, Module: [Process Engine Reporting](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-process-engine-reporting))

This activity reads process definition files from the ICR or filesystem, extracts reporting data from these files and returns it as 2 text variables either as SQL insert statements or in CSV format.

**Input Parameters:**

- url (x-infinica/url) (1-unbounded)

The URL(s) of the process file(s) to be analyzed.

- recursive (x-xsd/boolean) (0-1)

Search all sub directories for process files if the url points to a directory.

Default:

true

- pattern (text/plain) (0-1)

An optional regex pattern for the filename of process definitions. Only files with a matching name are considered. By default all files with extension .ipd are used.

Default:

.*\.ipd

- format (text/plain) (0-1)

Defines the format of the text in the output variables. Valid values are SQL or CSV

Default:

SQL

- processTable (text/plain) (0-1)

The name of the database table for which the process insert statements should be created. Only relevant if the format is SQL.

Default:

STG.PROCESS

- elementTable (text/plain) (0-1)

The name of the database table for which the element insert statements should be created. Only relevant if the format is SQL.

Default:

STG.PROCESS_ELEMENT

**Output Parameters:**

- processes (text/plain) (0-1)

The fields extracted from the process files as SQL or CSV.

- elements (text/plain) (0-1)

The fields extracted from the process elements as SQL or CSV.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}