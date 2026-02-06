---
id: "f6391908-2eef-4bb8-867c-b7e02a8c9e2a"
title: "DT3 RowParity Operator"
slug: "dt3-rowparity-operator"
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
created_at: "2025-12-10T17:39:13.345Z"
modified_at: "2026-01-13T15:01:03.965Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-rowparity-operator"
synced_at: "2026-01-28T20:52:28.479Z"
checksum: "a02544169c6db682"
---

## **Description**
The **RowParity **operator allows to verify if an input node instance is even or odd.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The input node for which you want to verify if the instance is even or odd.

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

- The numeric value ***1 ***if the input node instance is odd

- The numeric value ***0 ***if the input node instance is even

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}