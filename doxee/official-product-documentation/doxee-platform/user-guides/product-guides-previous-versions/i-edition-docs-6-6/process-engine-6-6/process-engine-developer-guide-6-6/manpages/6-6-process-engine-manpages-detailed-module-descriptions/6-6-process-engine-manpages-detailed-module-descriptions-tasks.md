---
id: "dbac8630-a1b1-403e-a130-4b8e36609c6c"
title: "Tasks"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-tasks"
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
created_at: "2025-08-13T10:01:35.512Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-tasks"
synced_at: "2026-01-28T21:01:48.989Z"
checksum: "29858bcd4f853572"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

This module contains task activities, each of which calls a particular operation of the Task Manager API. All calls are executed on the task manager configured for the Process Engine, which executes the current process. The result is the same as when calling the API directly via SOAP or REST.

Activities:

[Checkin Task](/doxee-platform/docs/checkin-task), [Checkout Task](/doxee-platform/docs/checkout-task), [Create Task](/doxee-platform/docs/create-task), [Delete Task](/doxee-platform/docs/delete-task), [Delete Tasks](/doxee-platform/docs/delete-tasks), [Find Tasks](/doxee-platform/docs/find-tasks), [Get Task](/doxee-platform/docs/get-task), [Get Task Payload](/doxee-platform/docs/get-task-payload), [Set Task Metadata](/doxee-platform/docs/set-task-metasata), [Set Task Payload](/doxee-platform/docs/set-task-payload), [Set Task Principals](/doxee-platform/docs/set-task-principals), [Terminate Task](/doxee-platform/docs/terminate-task)

This module provides activities to access an Infinica Task Manager server via SOAP or REST. For details about the Task Manager API, please refer to the official Task Manager documentation.

## Task Queries
The task query format is defined in task_query.xsd. An example query looks like this:

`&lt;taskQuery xmlns="http://www.infinica.com/tasks"&gt;
  &lt;parameters&gt;     &lt;parameter name="state" operation="equals"&gt;
      &lt;values&gt;
        &lt;value type="taskState"&gt;ready&lt;/value&gt;
      &lt;/values&gt;
    &lt;/parameter&gt;
  &lt;/parameters&gt;
  &lt;sortCriteria&gt;
    &lt;criterion name="type" ascending="true" /&gt;     &lt;criterion name="priority" ascending="false" /&gt;
  &lt;/sortCriteria&gt; &lt;/taskQuery&gt;  `

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}