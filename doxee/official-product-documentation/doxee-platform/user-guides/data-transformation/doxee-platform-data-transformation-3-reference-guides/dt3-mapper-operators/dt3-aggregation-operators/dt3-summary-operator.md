---
id: "15052a2e-5fd1-4c45-bcc4-b060f87e4bee"
title: "DT3 Summary Operator"
slug: "dt3-summary-operator"
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
created_at: "2025-12-10T17:30:49.326Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-summary-operator"
synced_at: "2026-01-28T20:52:16.333Z"
checksum: "e4dfb9dfc6576df9"
---

## Description
The **Summary **operator allows to calculate the sum of the values of all instances in an input node eleme nt.

## Input
**Input**

**Data type**

**Description**

**in0**

Number

The node element for which you want to calculate the sum of the values of all instances

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The sum of all instance values in the input node element

## Settings
None.

## Special cases
In special cases, the operator behaves as follows:

Case

Behavior

**NULL**

**input (no input)**

The operator does not consider a NULL input. If all inputs are NULL, the operator returns the value ***0***. The system logs a warning event.

**NULL**

**input value**

The operator does not consider instances having a NULL value. If all instances contain a NULL value, the operator returns the value ***0***. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator does not consider instances having a non-numeric value. If all instances contain a non-numeric value, the operator returns the value ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}