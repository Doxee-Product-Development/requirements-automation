---
id: "37ff8ff5-70c8-42b8-95ec-d49f0512bbc6"
title: "DT3 NodeExist Operator"
slug: "dt3-nodeexist-operator"
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
created_at: "2025-12-10T17:37:46.884Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-nodeexist-operator"
synced_at: "2026-01-28T20:52:26.532Z"
checksum: "b9e8fdfbe53e4c3f"
---

## **Description**
The **NodeExist **operator allows to verify if an input node exists.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The node of which you want to verify the existence

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

The boolean value ***true ***if the input node **in0 **exists

The boolean value ***false ***if the input node **in0 **does not exist

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns the boolean value ***false***.

**Input with NULL value**

The operator returns the boolean value ***true***.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}