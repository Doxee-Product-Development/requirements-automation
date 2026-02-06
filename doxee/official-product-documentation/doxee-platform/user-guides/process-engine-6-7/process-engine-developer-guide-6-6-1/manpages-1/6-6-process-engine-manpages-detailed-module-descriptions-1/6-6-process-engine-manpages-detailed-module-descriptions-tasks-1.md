---
id: "89d73462-5162-4b46-bb61-82ebc0cf586a"
title: "Tasks"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-tasks-1"
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
created_at: "2026-01-07T13:42:11.503Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-tasks-1"
synced_at: "2026-01-28T20:55:20.785Z"
checksum: "664b5edd166879f5"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

This module contains task activities, each of which calls a particular operation of the Task Manager API. All calls are executed on the task manager configured for the Process Engine, which executes the current process. The result is the same as when calling the API directly via SOAP or REST.

Activities:

[Checkin Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-checkin-task-1), [Checkout Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-checkout-task-1), [Create Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-create-task-1), [Delete Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-delete-task-1), [Delete Tasks](/doxee-platform/docs/6-6-process-engine-manpages-activities-delete-tasks-1), [Find Tasks](/doxee-platform/docs/6-6-process-engine-manpages-activities-find-tasks-1), [Get Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-get-task-1), [Get Task Payload](/doxee-platform/docs/6-6-process-engine-manpages-activities-get-task-payload-1), [Set Task Metadata](/doxee-platform/docs/6-6-process-engine-manpages-activities-set-task-metasata-1), [Set Task Payload](/doxee-platform/docs/6-6-process-engine-manpages-activities-set-task-payload-1), [Set Task Principals](/doxee-platform/docs/6-6-process-engine-manpages-activities-set-task-principals-1), [Terminate Task](/doxee-platform/docs/6-6-process-engine-manpages-activities-terminate-task-1)

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