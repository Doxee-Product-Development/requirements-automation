---
id: "aae00ac9-6967-446a-ac07-66df0a148faf"
title: "Installation"
slug: "task-manager-6-6-installation-1"
category: "Task Manager"
category_path:
  - "Product guides"
  - "Task Manager"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:39:37.285Z"
modified_at: "2026-01-08T08:58:41.782Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/task-manager-6-6-installation-1"
synced_at: "2026-01-28T20:58:13.744Z"
checksum: "4b3180ad7cc7b252"
---

The following steps must be performed to install the Task Manager:

- Stop Tomcat

- Copy the installation files

Copy `infinica-task-manager.war` to `$TOMCAT/webapps`

- Copy the `infinica` directory to `$TOMCAT` (or if a directory `$TOMCAT/infinica` already exists, copy the contents of the directory

- Edit the configuration files

- Start Tomcat

- Check the log files to see if any errors occurred during the startup process

If there were errors, stop Tomcat, fix the configuration and continue with step 4

- Verify that the Task Manager can be accessed

## Verifying Task Access
Once the Task Manager is up and running, it can be accessed using the following URL (assuming Tomcat is running on the same machine on its standard port):

`http://localhost:8080/infinica-task-manager/tasks`Accessing this URL via a web browser should show a brief overview page for the tasks SOAP service.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}