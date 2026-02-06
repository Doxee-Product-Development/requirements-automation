---
id: "e5e7636c-1c25-481a-b131-fb39827f6332"
title: "DT3 Parity Operator"
slug: "dt3-parity-operator"
category: "DT3 Common Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Common Operators"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-10T17:38:17.32Z"
modified_at: "2026-01-13T14:53:40.989Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-parity-operator"
synced_at: "2026-01-28T20:52:27.225Z"
checksum: "02e89c0f6e61aa3b"
---

## **Description**
The **Parity **operator allows to verify if the input data is an even or odd number.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Number

The input data for which you want to verify if it is an even or odd number

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

- The numeric value ***1 ***if the input data is odd

- The numeric value ***0 ***if the input data is even

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}