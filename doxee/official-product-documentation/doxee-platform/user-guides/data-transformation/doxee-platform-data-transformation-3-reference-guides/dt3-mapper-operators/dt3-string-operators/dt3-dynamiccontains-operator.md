---
id: "13b0dc6e-545d-4b42-ac37-e4c791c4824d"
title: "DT3 DynamicContains Operator"
slug: "dt3-dynamiccontains-operator"
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
created_at: "2025-12-10T17:48:35.921Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-dynamiccontains-operator"
synced_at: "2026-01-28T20:52:44.632Z"
checksum: "cbaba19f912010a7"
---

## **Description**
The **DynamicContains **operator allows to verify if an input data contains data from another input, and returns the position of its first occurrence.

## **Input**
**Input**

**Data type**

**Description**

**value**

String

The input data in which you want to locate a specific substring

**substring**

String

The substring to search for

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

The position, within the string defined in the **value **input, of the first occurrence of the substring defined in the **substring **input.

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns the value ***-1 ***if the input is NULL. The system logs a warning message.

**Input with NULL value**

The operator returns the value ***-1 ***if the input has a NULL value. The system logs a warning message.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}