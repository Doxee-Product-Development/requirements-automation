---
id: "2c11ec06-cb9d-44a1-b366-4460ebf29863"
title: "DT3 Progressive Operator"
slug: "dt3-progressive-operator"
category: "DT3 Common Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Common Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:38:47.405Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-progressive-operator"
synced_at: "2026-01-28T20:52:27.856Z"
checksum: "306acd2d39f6334d"
---

## **Description**
The **Progressive **operator allows to increment its value, starting from 1 and increasing the count as the input node changes. The operator resets the counter every time that the parent node of the input node is returned.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The node that you want to use to increment the value of the counter

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The current value of the counter

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}