---
id: "e71ccf87-e5d9-45b6-8b8e-846ef5973ab8"
title: "DT3 Positive Operator"
slug: "dt3-positive-operator"
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
created_at: "2025-12-10T17:46:18.912Z"
modified_at: "2025-12-17T18:24:28.268Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/dt3-positive-operator"
synced_at: "2026-01-28T20:52:39.188Z"
checksum: "c9cae55f562d7c18"
---

## **Description**
The **Positive **operator allows to verify if a numeric value provided in input is positive, negative, or zero.

## **Input**
**Input**

**Data type**

**Description**

**in0**

Number

The numeric value that you want to check

## **Output**
**Output**

**Data type**

**Description**

**out0**

Number

- ***-1 ***if the numeric value provided in input is negative

- if the numeric value provided in input is ***0***

- if the numeric value provided in input is positive

## **Settings**
None.

## **Special cases**
In special cases, the operator behaves as follows:

**Case**

**Behavior**

**NULL input (no input)**

The operator returns an empty string. The system logs a warning event.

**NULL input value**

The operator returns an empty string. The system logs a warning event.

**NON NUMERIC input value**

The operator returns an empty string. The system logs a warning event.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}