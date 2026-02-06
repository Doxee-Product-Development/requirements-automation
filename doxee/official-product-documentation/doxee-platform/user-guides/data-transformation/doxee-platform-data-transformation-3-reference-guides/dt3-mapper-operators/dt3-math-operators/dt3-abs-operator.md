---
id: "cba4023e-ef51-4a8d-8409-bad618a95d0c"
title: "DT3 Abs Operator"
slug: "dt3-abs-operator"
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
created_at: "2025-12-10T17:44:51.017Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-abs-operator"
synced_at: "2026-01-28T20:52:37.251Z"
checksum: "5854fec535f9f3b0"
---

## **Description**
The **Abs **operator allows to calculate the absolute value of the numeric value provided in input.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Number

The numeric value for which you want to calculate the absolute value

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The numeric value provided in input without a sign

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

**NULL input value**

The operator considers a NULL input as ***0***. The system logs a warning event.

**NON NUMERIC input value**

The operator considers a non-numeric input as ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}