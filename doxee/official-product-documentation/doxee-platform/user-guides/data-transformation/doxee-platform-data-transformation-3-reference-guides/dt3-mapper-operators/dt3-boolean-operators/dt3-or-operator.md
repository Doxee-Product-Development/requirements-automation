---
id: "0e02b7eb-e0e0-4c4a-bc20-a1423b236219"
title: "DT3 Or Operator"
slug: "dt3-or-operator"
category: "DT3 Boolean Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Boolean Operators"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-10T17:33:54.362Z"
modified_at: "2026-01-13T14:45:09.04Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-or-operator"
synced_at: "2026-01-28T20:52:18.646Z"
checksum: "fb1987103bc87b7f"
---

## Description
The **Or **operator allows to apply the boolean operator OR to two input nodes.

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

- ***false ***if all input nodes are false (in the boolean sense)

- ***true ***in all other cases

## **Settings**
None.

## Special cases
In special cases, the operator behaves as follows:

ase

Behavior

**NULL input (no input)**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

**NULL input value**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

**NON BOOLEAN**

**input value**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}