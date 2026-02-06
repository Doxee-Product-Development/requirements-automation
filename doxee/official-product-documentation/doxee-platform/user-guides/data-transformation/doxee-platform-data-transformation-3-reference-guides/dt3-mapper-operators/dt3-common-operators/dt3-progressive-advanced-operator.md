---
id: "4eaa3344-01a5-4279-9c04-c54542d907c4"
title: "DT3 Progressive Advanced Operator"
slug: "dt3-progressive-advanced-operator"
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
created_at: "2025-12-10T17:38:29.121Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-progressive-advanced-operator"
synced_at: "2026-01-28T20:52:27.536Z"
checksum: "34c2a5d23d5669ae"
---

## **Description**
The **Progressive Advanced **operator allows to increment its value, defining when to reset the counter to 1 and after which event to increment it.

## **Input**
**Input**

**Data type**

**Description**

**#reset**

Any

The node that you want to use to reset the counter to 1

**#update**

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