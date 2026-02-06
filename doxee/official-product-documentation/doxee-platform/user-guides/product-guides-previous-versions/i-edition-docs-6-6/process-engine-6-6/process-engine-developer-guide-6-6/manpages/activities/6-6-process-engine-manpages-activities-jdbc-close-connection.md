---
id: "84e599b2-2723-4c8f-be7b-dc24906e7474"
title: "JDBC Close Connection"
slug: "6-6-process-engine-manpages-activities-jdbc-close-connection"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T11:07:30.65Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-jdbc-close-connection"
synced_at: "2026-01-28T21:02:01.026Z"
checksum: "9592b1b10e84321b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(jdbcCloseConnection, Module: Base) 

Closes a previously opened JDBC connection.

Deprecated: The generic releaseResource activity should be used instead.

**Input Parameter:**

- connection (x-infinica/jdbc-connection, x-infinica/java)

A JDBC connection previously opened with jdbcConnect.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}