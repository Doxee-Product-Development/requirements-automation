---
id: "bccb45f2-63b0-4ab9-bbd0-8aa69de61c32"
title: "Squash Flow Batch Workflow Task Reference"
slug: "squash-flow-batch-workflow-task-reference"
category: "Doxee Platform Batch Workflows Task Reference"
category_path:
  - "Product guides"
  - "Batch Workflows"
  - "Batch Workflows Reference Guides"
  - "Doxee Platform Batch Workflows Task Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-08T10:52:01.069Z"
modified_at: "2025-12-17T18:16:11.636Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/squash-flow-batch-workflow-task-reference"
synced_at: "2026-01-28T20:49:06.898Z"
checksum: "1bea4a90b5d38852"
---

## Description
The **Squash Flow **task allows to merge data from the selected branch, combining all input chunks into a single output chunk.

Typical use cases for this task are:

- Combining the outputs of a task that is processed multiple times during the execution of a job in order to feed a single input chunk to the following task (e.g. the Archive Documents (DA) task).

- Merging all output chunks produced by tasks that have the "Split" option enabled (e.g. the Transform Files (DT) task) into a single chunk.

> Important

The Lot ID is lost during the squash operation, therefore the Assign Lot option should be enabled after the Squash Flow task, if required.

## Configuration
**![](data:image/png;base64,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)**

In the **Alias **field, enter the name of the task that will be displayed in the workflow.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}