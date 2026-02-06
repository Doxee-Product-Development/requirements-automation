---
id: "d3c09425-4bec-4f6a-8d28-0c0509e1a6c2"
title: "Processes"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-processes-1"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:10.973Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-processes-1"
synced_at: "2026-01-28T20:55:17.933Z"
checksum: "68c8c7ef74fc1a88"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides activities for accessing the Process Engine API.

Activities:

[Get Process Snapshot](/doxee-platform/docs/6-6-process-engine-manpages-activities-get-process-snapshot-1), [Instantiate Process](/doxee-platform/docs/6-6-process-engine-manpages-activities-instantiate-process-1), [Set Instance Constants](/doxee-platform/docs/6-6-process-engine-manpages-activities-set-instance-constants-1), [Start Process](/doxee-platform/docs/6-6-process-engine-manpages-activities-start-process-1)

This module contains process activities, each of which calls a particular operation of the Process Engine API.

Every activity has a `baseUrl` input parameter. Based on this parameter, the activity creates a client for the

Process Engine and calls its operation with the other provided parameters. If no baseUrl is provided, the Process Engine in which the current process is running will be used as the target.

Each activity's output is the regular result of the respective API operation, similar to when the operation is called directly via SOAP or REST. For more information on the individual API operations please refer to the Process Engine User Guide.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}