---
id: "a5d3f2db-99c1-437d-b247-9110f9beb9f9"
title: "Introduction"
slug: "task-manager-6-6-introduction"
category: "Task Manager"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Task Manager"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-22T12:54:27.4Z"
modified_at: "2025-10-23T12:39:32.561Z"
authors:
  - name: "Davide Daccico"
    email: "ddaccico@doxee.com"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/task-manager-6-6-introduction"
synced_at: "2026-01-28T21:03:56.166Z"
checksum: "b8f9ea9a872906ee"
---

This document is targeted at administrators and describes how to install and configure the Task Manager. The Task Manager is a server-side component for handling tasks and is required by Workplace 1 and Process Engine (when executing Workplace processes). These services communicate with the Task Manager via a SOAP interface.

## System Requirements
The following software and resources are required for installing ICR:

- OpenJdk

- Apache Tomcat

- A relational database and/or local file system storage for storing the tasks.

An overview of the supported software versions can be found in the general document *Software Requirements*.

The following optional dependencies may be necessary:

- Relational database for storing the tasks. Most JDBC enabled 

- databases are supported.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}