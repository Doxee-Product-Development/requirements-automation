---
id: "22003a6e-423f-4bcc-ba4e-460bea27311b"
title: "DT3 DynamicReplace Operator"
slug: "dt3-dynamicreplace-operator"
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
created_at: "2025-12-10T17:48:55.602Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-dynamicreplace-operator"
synced_at: "2026-01-28T20:52:44.952Z"
checksum: "5ef076958743c45a"
---

## **Description**
The **DynamicReplace **operator allows to replace part of an input string with data taken from another input string.

## **Input**
**Input**

**Data type**

**Description**

**value**

String

The string to which you want to apply the partial replacement

**old**

String

The string that you want to locate

**new**

String

The string that you want to use for the replacement

## **Output**
**Output**

**Data type**

**Description**

**out0**

String

The resulting string

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns an empty string if one or more inputs are NULL. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}