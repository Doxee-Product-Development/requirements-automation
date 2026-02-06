---
id: "10cecdd1-7157-4bb4-b140-092700bf0e24"
title: "Introduction to Process Engine"
slug: "6-6-process-engine-user-guide-overview-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.013Z"
modified_at: "2026-01-07T14:04:28.741Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-overview-1"
synced_at: "2026-01-28T20:54:45.754Z"
checksum: "a648db2d868dbf01"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Process Engine is a software solution for defining and executing processes. Processes are graph based programs, similar to scripts but designed to be easily editable with visual tools. Processes perform most operations by executing activities, which are predefined program elements designed for specific tasks like reading and writing files, rendering templates or sending emails. For most use cases, users can design processes by simply arranging existing activities and combining them with input data, although it is possible to provide custom activities for more custom solutions.

Processes are defined in Infinica Process Definition (IPD) files and stored alongside the Process Engine installation. Users and clients can then call the Process Engine to execute these processes through a variety of interfaces, including command line, SOAP, REST, and embedded Java interfaces.

Workplace uses the Process Engine to execute its business cases, allowing processes to contain human tasks which allow users to interact with processes by filling out web based forms.

This document provides an introduction to the Process Engine concepts and a basic overview of the building blocks used to define processes. Its intended target audience includes all users who intend to create, maintain or manually executed processes, or to administer a Process Engine installation or interface with it in custom applications.

Further documentation provides specific information aimed at administrators and users installing and configuring their own Process Engine instances (Administration Reference) and users creating and editing their own processes (Process Definition Reference).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}