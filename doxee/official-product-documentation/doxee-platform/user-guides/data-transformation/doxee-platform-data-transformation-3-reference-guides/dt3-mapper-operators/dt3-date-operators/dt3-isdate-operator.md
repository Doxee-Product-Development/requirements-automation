---
id: "6d3e84d1-8638-495f-9ab1-3097e5b22402"
title: "DT3 IsDate Operator"
slug: "dt3-isdate-operator"
category: "DT3 Date Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Date Operators"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-10T17:43:31.935Z"
modified_at: "2026-01-13T15:03:30.154Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-isdate-operator"
synced_at: "2026-01-28T20:52:35.814Z"
checksum: "44ece9feeb870960"
---

## **Description**
The **IsDate **operator allows to verify if an input value is in date format.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The value to check and verify if it is in date format

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

- The boolean value ***true ***if the input value is in date format

- The boolean value ***false ***if the input value is not in date format

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns the boolean value ***false***.

**NULL input value**

The operator returns the boolean value ***false***.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}