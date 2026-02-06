---
id: "20cc8236-5fb4-441d-b4bb-47bcf504761d"
title: "DT3 NodeDiff Operator"
slug: "dt3-nodediff-operator"
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
created_at: "2025-12-10T17:37:33.819Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-nodediff-operator"
synced_at: "2026-01-28T20:52:26.226Z"
checksum: "0a323f0c90421858"
---

## **Description**
The **NodeDiff **operator allows to verify if the input node data has changed compared to the previous node.

## **Input**
**Input**

**Data type**

**Description**

**node**

Any

The input node data for which you want to verify changes

**#state**

Integer number

The node that determines the change of state for the operator

## **Output**
**Output**

**Data type**

**Description**

**groups / lines**

Boolean

The boolean value ***true ***if the input node data has changed

The boolean value ***false ***if the input node data has not changed

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not perform any operation. The system logs a warning event.

**Input with NULL value**

The operator considers an input with NULL value as an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}