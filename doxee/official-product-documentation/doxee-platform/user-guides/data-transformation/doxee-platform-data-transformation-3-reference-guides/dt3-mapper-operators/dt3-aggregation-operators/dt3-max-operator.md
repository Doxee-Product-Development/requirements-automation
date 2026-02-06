---
id: "dc62884f-98dd-44b7-9b38-453c1930e8b2"
title: "DT3 Max Operator"
slug: "dt3-max-operator"
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
created_at: "2025-12-10T17:30:05.354Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-max-operator"
synced_at: "2026-01-28T20:52:15.400Z"
checksum: "c8f3bf16de3abb85"
---

## Description
The **Max **operator allows to calculate the maximum value of all values of the instances in an input node element.

## Input
**Input**

**Data type**

**Description**

**in0**

Number

The node element for which you want to calculate the maximum value of all instance values

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The maximum value of all instance values in the input node element

## Settings
None.

## Special cases
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL**

**input (no input)**

The operator does not consider a NULL input. If all inputs are NULL, the operator retur ns the value ***0***. The system logs a warning event.

**NULL**

**input value**

The operator does not consider instances having a NULL value. If all instances contain a NULL value, the operator returns the value ***0***. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator does not consider instances having a non-numeric value. If all instances contain a non-numeric value, the operator returns the value ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}