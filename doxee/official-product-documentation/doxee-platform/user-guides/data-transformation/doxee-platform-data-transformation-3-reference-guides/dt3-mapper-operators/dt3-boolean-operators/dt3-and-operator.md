---
id: "03b52f62-8370-49e3-bc7e-33fafe051ee6"
title: "DT3 And Operator"
slug: "dt3-and-operator"
category: "DT3 Boolean Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Boolean Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:32:57.712Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-and-operator"
synced_at: "2026-01-28T20:52:16.642Z"
checksum: "5fc6580c87a54500"
---

## Description
The **And **operator allows to apply the boolean operator AND to two input nodes.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Boolean

The first input value for the operator to process

**in1**

Boolean

The second input value for the operator to process

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

***true ***if both input nodes are true (in the boolean sense)

***false ***in all other cases

## **Settings**
None.

## Special cases
In special cases, the operator behaves as follows:

Case

Behavior

**NULL input (no input)**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

**NULL input value**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

**NON NUMERIC**

**input value**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}