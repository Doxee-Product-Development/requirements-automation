---
id: "2d2f9448-569a-444e-be0e-2d98b01b2888"
title: "Validate Template"
slug: "6-6-process-engine-manpages-activities-validate-template-1"
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
created_at: "2026-01-07T13:42:17.605Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-validate-template-1"
synced_at: "2026-01-28T20:56:30.010Z"
checksum: "597e7b619c833b04"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(validateTemplate, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion-1))

Validates one or more templates.

**Input Parameters:**

- template (x-infinica/stream) (0-unbounded) 

Template(s) that should be validated.

- locale (text/plain) (0-1) 

Validation locale.

- severities (text/xml) (0-1)

Model validation severities.

- severityCutoff (text/plain) (0-1)

Global cutoff level for severities.

- followOffToggle (x-xsd/boolean)

Whether inactive toggles should be validated as well.

Default:

true

**Output Parameter:**

- problems (text/xml) (0-unbounded)

Resulting validation problems (one result per template).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}