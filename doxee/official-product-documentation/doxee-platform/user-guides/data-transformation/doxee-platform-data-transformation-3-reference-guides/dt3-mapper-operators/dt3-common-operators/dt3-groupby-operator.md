---
id: "9dde5092-6c76-4ea1-a0ed-b05ba4e0b94d"
title: "DT3 GroupBy Operator"
slug: "dt3-groupby-operator"
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
created_at: "2025-12-10T17:37:05.545Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-groupby-operator"
synced_at: "2026-01-28T20:52:25.610Z"
checksum: "891c341c8982bc8b"
---

## **Description**
The **GroupBy **operator allows to group instances of an input node based on the defined grouping key.

## **Input**
**Input**

**Data type**

**Description**

**groups / lines**

Any

The instances of the node that you want to group

**key**

Number

The grouping key to use

## **Output**
**Output**

**Data type**

**Description**

**groups / lines**

Any

The grouped instances of the input node

**key**

Number

The value of the grouping key used

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**Input with NULL value**

The operator does not group instances with NULL value. If all instances contain a NULL value, the operator returns the value ***0***. The system logs a warning event.

**Input with NON NUMERIC**

**value**

The operator does not group instances with NON NUMERIC value. If all instances contain a NON NUMERIC value, the operator returns the value ***0***. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}