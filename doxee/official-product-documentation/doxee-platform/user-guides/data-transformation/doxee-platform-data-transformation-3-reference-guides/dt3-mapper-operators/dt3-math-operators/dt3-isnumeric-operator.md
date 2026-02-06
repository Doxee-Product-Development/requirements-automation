---
id: "e46cbf3d-84d5-4067-8631-57edd3c4b4de"
title: "DT3 IsNumeric Operator"
slug: "dt3-isnumeric-operator"
category: "DT3 Math Operators"
category_path:
  - "Product guides"
  - "Data Transformation"
  - "Doxee Platform Data Transformation 3 Reference Guides"
  - "DT3 Mapper Operators"
  - "DT3 Math Operators"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-10T17:45:32.748Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-isnumeric-operator"
synced_at: "2026-01-28T20:52:38.250Z"
checksum: "871d7b983e74b802"
---

## **Description**
The **IsNumeric **operator allows to verify if the input data is a numeric value.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The data that you want to verify if it is a numeric value

## **Output**
**Output**

**Data type**

**Description**

**out0**

Boolean

The boolean value ***true ***if the input is a numeric value

The boolean value ***false ***if the input is not a numeric value

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

**NULL input value**

The operator returns the boolean value ***false***.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}