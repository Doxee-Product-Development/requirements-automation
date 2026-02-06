---
id: "72e4ae4a-ae7b-4a8c-9070-0e647347d622"
title: "DT3 Division Operator"
slug: "dt3-division-operator"
category: "DT3 Math Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Math Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:45:03.523Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-division-operator"
synced_at: "2026-01-28T20:52:37.543Z"
checksum: "4a281572b4cb5082"
---

## **Description**
The **Division **operator allows to divide two numeric values provided in input.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Number

The numeric value that you want to use as dividend

**in1**

Number

The numeric value that you want to use as divisor

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The result of the division

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns ***0 ***if one or both input values are NULL. The system logs a warning event .

**NULL input value**

The operator considers a NULL input as ***0***. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator considers a non-numeric input as ***0***. The system logs a warning event .

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}