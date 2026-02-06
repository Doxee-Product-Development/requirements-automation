---
id: "35f0e635-9732-4f62-a88c-2550413c9495"
title: "Master Template Activity"
slug: "master-template-activity-1"
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
created_at: "2026-01-07T13:42:14.181Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/master-template-activity-1"
synced_at: "2026-01-28T20:55:38.151Z"
checksum: "20f7f3aeac69693f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(masterTemplate, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion-1)) 

Derives a Template from a Master Template.

**Input Parameters:**

- masterTemplateUri (x-infinica/url) (0-1)

URI of the Master Template. Required if input parameter "state" is not set.

- templateTargetUri (x-infinica/url) (0-1)

URI of the Template to create. Required if input parameter "state" is not set.

- perform (x-xsd/boolean)

Boolean flag which determines whether the action is executed directly. If set to false, the action is created and returned as an output "state".

Default:

true

- storageStrategy (text/plain) (0-1)

The storage strategy for the external resources of the Master Template. Valid values are FLAT and HIERARCHICAL.

- prefixTemplateName (x-xsd/boolean) (0-1)

Boolean flag which determines whether the Template name should be added as a prefix to the derived resources.

- customPrefix (text/plain) (0-1)

Optional custom prefix for the derived resources.

- customSuffix (text/plain) (0-1)

Optional custom suffix for the derived resources.

- state (text/xml) (0-1)

Optional TemplateMaster-Action created in a previous execution of the masterTemplate activity as output parameter "state". If this is set, all other input parameters are ignored as the settings are taken from the existing action.

**Output Parameter:**

- state (text/xml) (0-1)

Only available when input parameter perform is set to false. Returns a TemplateMaster-Action persisted as XML, which can be mapped into another execution of the activity.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}