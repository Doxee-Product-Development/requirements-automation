---
id: "ec25f658-701f-460d-9d5e-1fe45e75613b"
title: "DT3 Not Operator"
slug: "dt3-not-operator"
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
created_at: "2025-12-10T17:33:37.027Z"
modified_at: "2026-01-13T14:43:47.691Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-not-operator"
synced_at: "2026-01-28T20:52:18.326Z"
checksum: "37cc49263ff9a0eb"
---

## Description
The **Not **operator allows to apply the boolean operator NOT to the input node.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Boolean

The input value that the operator will process

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

- ***true ***if the input value is false (in the boolean sense)

- ***false ***if the input value is true (in the boolean sense)

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

**NON BOOLEAN**

**input value**

The operator does not perform any operations and returns an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}