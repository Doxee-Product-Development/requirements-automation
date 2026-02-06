---
id: "2a333390-276b-4e6c-9a38-23a5df39e18f"
title: "DT3 Min Operator"
slug: "dt3-min-operator"
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
created_at: "2025-12-10T17:30:21.112Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-min-operator"
synced_at: "2026-01-28T20:52:15.685Z"
checksum: "5d99949877bdef5d"
---

## Description
The **Min **operator allows to calculate the minimum value of all values of the instances in an input node element.

## Input
**Input**

**Data type**

**Description**

**in0**

Number

The node element for which you want to calculate the minimum value of all instance values

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The minimum value of all instance values in the input node element

## Settings
None.

## Special cases
In special cases, the operator behaves as follows:

Case

Behavior

**NULL**

**input (no input)**

The operator does not consider a NULL input. If all inputs are NULL, the operator returns the value ***0 ***. The system logs a warning event.

**NULL**

**input value**

The operator does not consider instances having a NULL value. If all instances contain a NULL value, the operator returns the value ***0 ***. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator does not consider instances having a non-numeric value. If all instances contain a non-numeric value, the operator returns the value ***0 ***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}