---
id: "4f86523e-78ad-4b5e-b6bf-53feb5c826c8"
title: "Processes"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-processes"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T09:52:22.148Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-processes"
synced_at: "2026-01-28T21:01:45.928Z"
checksum: "cb40df19149da6ab"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides activities for accessing the Process Engine API.

Activities:

[Get Process Snapshot](/doxee-platform/docs/get-process-snapshot), [Instantiate Process](/doxee-platform/docs/instantiate-process), [Set Instance Constants](/doxee-platform/docs/set-instance-constants), [Start Process](/doxee-platform/docs/start-process)

This module contains process activities, each of which calls a particular operation of the Process Engine API.

Every activity has a `baseUrl` input parameter. Based on this parameter, the activity creates a client for the

Process Engine and calls its operation with the other provided parameters. If no baseUrl is provided, the Process Engine in which the current process is running will be used as the target.

Each activity's output is the regular result of the respective API operation, similar to when the operation is called directly via SOAP or REST. For more information on the individual API operations please refer to the Process Engine User Guide.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}