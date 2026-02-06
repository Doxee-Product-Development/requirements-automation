---
id: "e8c58a4c-36d8-4bce-8466-4b2217e9bbdc"
title: "Checkout Task"
slug: "6-6-process-engine-manpages-activities-checkout-task"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T10:36:18.453Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-checkout-task"
synced_at: "2026-01-28T21:01:51.601Z"
checksum: "08bdb29356a35619"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(checkoutTask, Module: Tasks)

Calls the checkout operation. The task with the provided ID is locked so only the user who checked it out can work on it until it is checked in again. Only works if the task isn't checked out already.

**Input Parameters:**

- taskId (text/plain)

ID of the task to check out.

forUser (text/plain) (0-1)

Optional parameter providing the name of a user for whom the task should be checked out instead of the user who called the operation.

**Output Parameter:**

- task (text/xml)

The checked out task in XML format.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}