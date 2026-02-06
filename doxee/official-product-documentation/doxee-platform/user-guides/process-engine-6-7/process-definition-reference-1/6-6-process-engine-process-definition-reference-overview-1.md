---
id: "9368a536-225e-4783-8af0-9f998cbbf5f1"
title: "Overview"
slug: "6-6-process-engine-process-definition-reference-overview-1"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:05.199Z"
modified_at: "2026-01-07T14:04:42.012Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-overview-1"
synced_at: "2026-01-28T20:54:55.419Z"
checksum: "b9c054bad6330628"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

This reference documentation is intented to give a full and detailed overview of process definitions and the Infinica Process Definition (IPD) format. It is targeted at readers already familiar with the general concepts of Doxee Process Engine and the basic elements making up a process definition. For an introduction to these concepts and elements, please refer to the Process Engine User Guide.

The IPD format is an XML based format used to store Infinica process definitions. To give as exact a specification of the IPD format as possible, elements described in this guide are presented in a somewhat formalised way. Each element is accompanied by an exemplary XML representation along with a complete list of its supported attributes and elements and their descriptions. Where possible, the visual representation of the same element in Process Designer is also shown.

This document aims to define the IPD format in such a way that readers can create custom process definitions either manually (using a text or XML editor application) or with Process Designer. Attributes and elements described in this document are given with the exact names used by the IPD format. As these are technical names in the form of XML tags and attributes, their names and labels in Process Designer may differ slightly from the names given here. For more information on how to use Process Designer, please see the Process Designer User Guide.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}