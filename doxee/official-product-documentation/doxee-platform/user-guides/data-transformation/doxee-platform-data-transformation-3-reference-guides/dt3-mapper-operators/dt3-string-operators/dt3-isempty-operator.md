---
id: "06c41c5c-7fd9-4b3b-8dbf-730352b85f86"
title: "DT3 IsEmpty Operator"
slug: "dt3-isempty-operator"
category: "DT3 String Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 String Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:50:04.429Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-isempty-operator"
synced_at: "2026-01-28T20:52:46.342Z"
checksum: "25b38f4f799d528b"
---

## **Description**
The **IsEmpty **operator allows to verify if an input string is empty.

## **Input**
**Input**

**Data type**

**Description**

**in0**

String

The string that you want to check

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

***true ***if the input string is empty

***false ***if the input string is not empty

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator considers a NULL input as an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}