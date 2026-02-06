---
id: "97a5742b-886a-431b-883e-8008468241c8"
title: "DT3 Mod Operator"
slug: "dt3-mod-operator"
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
created_at: "2025-12-10T17:45:53.169Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-mod-operator"
synced_at: "2026-01-28T20:52:38.550Z"
checksum: "5df74db2f65b5c3f"
---

## **Description**
The **Mod **operator allows to calculate the modulo division of two numeric values provided in input, returning the remainder of the division in output.

## **Input**
**Input**

**Data Type**

**Description**

**in0**

Number

The numeric value that you want to use as dividend

**in1**

Number

The numeric value that you want to use as divisor

## **Output**
**Output**

**Data Type**

**Description**

**out0**

Number

The remainder of the division

## **Settings**
None.

## **Special Cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns ***0 ***if one or both input values are NULL. The system logs a warning event.

**NULL input value**

The operator returns ***0 ***if one or both input values have a NULL value. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator considers a non-numeric input as ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}