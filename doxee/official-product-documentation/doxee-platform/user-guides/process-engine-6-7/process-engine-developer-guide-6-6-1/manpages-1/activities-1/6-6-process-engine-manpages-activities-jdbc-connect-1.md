---
id: "48fc60de-b879-432c-bcfd-76b07ed1ae84"
title: "JDBC Connect"
slug: "6-6-process-engine-manpages-activities-jdbc-connect-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:13.911Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-jdbc-connect-1"
synced_at: "2026-01-28T20:55:36.249Z"
checksum: "27dc7c2af0713134"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(jdbcConnect, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base-1))

Creates a JDBC connection which can be used by subsequent JDBC activities.

**Input Parameters:**

- driver (text/plain) (0-1)

The database driver class name.

- url (x-infinica/url)

The database URL from which input will be read.

- user (text/plain) (0-1)

The database user name.

- password (x-infinica/secret-text) (0-1) 

The database password.

- transactions (x-xsd/boolean)

Whether to use explicit transactions. If this is true, jdbcCommit has to be used to persist database updates. Defaults to false.

Default:

false

- readOnly (x-xsd/boolean)

Whether the connection should be read only. Write operations will fail when they are performed on a read only connection.

Default:

 false

- commitOnClose (x-xsd/boolean)

Whether an open transaction should be automatically committed if it is dirty when it is closed. Unless this is true, the transaction will be rolled back.

Default:

false

**Output Parameter:**

- connection (x-infinica/jdbc-connection) The database connection.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}