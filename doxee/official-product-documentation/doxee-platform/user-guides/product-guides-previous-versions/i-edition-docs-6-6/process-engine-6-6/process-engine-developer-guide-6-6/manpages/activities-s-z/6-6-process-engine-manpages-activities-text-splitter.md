---
id: "4948fb16-f50c-4840-945a-6110e7416f9e"
title: "Text Splitter"
slug: "6-6-process-engine-manpages-activities-text-splitter"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T13:46:28.993Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-text-splitter"
synced_at: "2026-01-28T21:02:49.043Z"
checksum: "e836ca6fe6cc37e5"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(textSplitter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Splits a text stream into multiple text blocks, based on a set of defined splitter patterns.

The splitter outputs one or more output streams, each containing all lines of one section of the input stream. If the stream has a name, that name is used as the base URL of the corresponding output stream.

One or more section start patterns define which lines are recognised as the beginnings of new sections.

Each new section produces a new output stream.

**Input Parameters:**

- input (x-infinica/stream) (1-unbounded) 

Input text stream.

- skipPattern (text/plain) (0-unbounded)

Lines matching this regular expression pattern and are not recognised as section start or end lines are skipped when reading the input text stream.

- sectionStartPattern (text/plain) (0-unbounded)

Lines matching this regular expression pattern are recognised as the starting lines of a new section. If the pattern includes a capture group, its captured text is used as the name of the new section.

- sectionEndPattern (text/plain) (0-unbounded)

Lines matching this regular expression pattern are recognised as the ending lines of a section.

- sectionStartRewrite (text/plain) (0-1)

If specified, a section start line is converted to this pattern before it is reported as a section content line (only relevant if includeSectionStart is true).

Capture groups from the section start pattern can be accessed using the parameter {0}, {1} etc.

- sectionEndRewrite (text/plain) (0-1)

If specified, a section start line is converted to this pattern before it is reported as a section content line (only relevant if includeSectionStart is true). The line is treated as still belonging to the section that is ended by it.

Capture groups from the section start pattern can be accessed using the parameter {0}, {1} etc.

- includeSectionStart (x-xsd/boolean)

Specifies whether section start lines are also parsed as section content.

Default:

false

- includeSectionEnd (x-xsd/boolean)

Specifies whether section end lines are also parsed as section content.

Default:

false

- skipOutsideSection (x-xsd/boolean)

If set to true, lines that are not part of a section are ignored.

Default:

false

- trimLeft (x-xsd/boolean)

Specifies whether to trim lines by removing white space at the start of the line before they are parsed as content lines.

Default:

false

- trimRight (x-xsd/boolean)

Specifies whether to trim lines by removing white space at the end of the line before they are parsed as content lines.

Default:

false

**Output Parameter:**

- output (x-infinica/stream) (0-unbounded) Output streams.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}