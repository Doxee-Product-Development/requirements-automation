---
id: "a1420e01-461b-45b8-a063-7bdd7be55ea1"
title: "Process Definiton Reporter"
slug: "6-6-process-engine-manpages-activities-process-definiton-reporter-1"
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
created_at: "2026-01-07T13:42:15.704Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-process-definiton-reporter-1"
synced_at: "2026-01-28T20:56:14.055Z"
checksum: "ef98450a90f3e60f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(processDefinitionReporter, Module: [Process Engine Reporting](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-process-engine-reporting-1))

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