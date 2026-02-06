---
id: "5ea8ec92-7c58-4c6a-9331-7f4d702f7262"
title: "DT3 Trim Operator"
slug: "dt3-trim-operator"
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
created_at: "2025-12-10T17:52:35.096Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-trim-operator"
synced_at: "2026-01-28T20:52:50.743Z"
checksum: "a6d4f16643627a05"
---

## **Description**
The **Trim **operator allows to remove any spaces present before and after a string, based on the configuration settings.

## **Input**
**Input**

**Data type**

**Description**

**in0**

String

The string containing spaces that you want to trim from the beginning or end.

## **Output**
**Output**

**Data type**

**Description**

**out0**

String

The resulting string

## **![](data:image/png;base64,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)****Settings**
- From the **Trim **drop-down menu, select the side of the string from which you want to remove space characters. The available options are:

**Left**: Remove all spaces found at the beginning of the string.

- **Right**: Remove all spaces found at the end of the string.

- **Both**: Remove all spaces found both at the beginning and at the end of the string.

- Click **Apply **to confirm.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator considers a NULL input as an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}