---
id: "c40724c0-749a-4da4-a895-928b6e747b02"
title: "DT3 Counter Operator"
slug: "dt3-counter-operator"
category: "DT3 Aggregation Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Aggregation Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:29:47.628Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-counter-operator"
synced_at: "2026-01-28T20:52:14.562Z"
checksum: "593a50b300f00d40"
---

## Description
The **Counter **operator allows to count the number of instances of an input node element.

## Input
**Input**

**Data type**

**Description**

**in0**

Any

The node element for which you want to count the number of instances

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

Number of instances of the input node element

## Settings
None.

## Special cases
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input value**

The operator does not count instances having a NULL value. If all instances contain a NULL value, the operator returns the value ***0***. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator does not count instances having a non-numeric value. If all instances contain a non-numeric value, the operator returns the value ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}