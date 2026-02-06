---
id: "2736be67-48b0-477b-8bf5-a7a73a9bf270"
title: "DT3 Random Operator"
slug: "dt3-random-operator"
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
created_at: "2025-12-10T17:39:00.457Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-random-operator"
synced_at: "2026-01-28T20:52:28.159Z"
checksum: "51010975cec10918"
---

## **Description**
The **Random **operator allows to generate a random number when receiving any type of input data.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Any

The input data that you want to use to trigger the generation of a random number.

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

A random number

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator does not consider a NULL input. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}