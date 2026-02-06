---
id: "961dfc71-54b5-474f-8be1-4416ddd47b33"
title: "Text Splitter"
slug: "6-6-process-engine-manpages-activities-text-splitter-1"
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
created_at: "2026-01-07T13:42:18.296Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-text-splitter-1"
synced_at: "2026-01-28T20:56:24.332Z"
checksum: "b2a8c4c55dc4f2ab"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(textSplitter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

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