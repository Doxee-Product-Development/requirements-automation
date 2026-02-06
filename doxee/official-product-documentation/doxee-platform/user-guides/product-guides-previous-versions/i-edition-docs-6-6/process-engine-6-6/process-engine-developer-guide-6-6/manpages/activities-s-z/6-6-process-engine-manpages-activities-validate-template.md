---
id: "04f732c6-1cd3-46a4-89b2-f0fde7cf7f91"
title: "Validate Template"
slug: "6-6-process-engine-manpages-activities-validate-template"
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
created_at: "2025-08-13T14:46:27.012Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-validate-template"
synced_at: "2026-01-28T21:02:54.792Z"
checksum: "ab202c3bde649d62"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(validateTemplate, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion))

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