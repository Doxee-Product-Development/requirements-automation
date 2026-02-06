---
id: "b30f8c4b-48af-4f62-8b74-97e3eca7e9e6"
title: "DT3 DynamicSubstring Operator"
slug: "dt3-dynamicsubstring-operator"
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
created_at: "2025-12-10T17:49:13.064Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-dynamicsubstring-operator"
synced_at: "2026-01-28T20:52:45.267Z"
checksum: "19e6e038cca72a41"
---

## **Description**
The **DynamicSubstring **operator allows to extract a string from an input data, based on the parameters defined by other inputs.

## **Input**
**Input**

**Data type**

**Description**

**string**

String

The input data from which you want to extract a string

**start**

Number

The position of the first character of the string that you want to extract

**length**

Number

The length of the string that you want to extract

## **Output**
**Output**

**Data type**

**Description**

**out0**

String

The partial string extracted from the **string **input

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Bahavior**

**NULL input (no input)**

The operator returns an empty string if one or more inputs are NULL. The system logs a warning event.

**Input with NULL value**

The operator returns an empty string if one or more inputs have a NULL value. The system logs a warning event.

**The *start *or *length *inputs have a NON NUMERIC value**

The operator returns an empty string if one or more inputs have a NON NUMERIC value. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}