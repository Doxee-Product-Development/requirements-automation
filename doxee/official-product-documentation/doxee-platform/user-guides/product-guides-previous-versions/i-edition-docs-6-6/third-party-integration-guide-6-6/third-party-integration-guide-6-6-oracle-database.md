---
id: "86a829f2-aba7-4c2e-a0ff-e8ceb2992c3a"
title: "Oracle database"
slug: "third-party-integration-guide-6-6-oracle-database"
category: "Third-party integration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Third-party integration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T14:04:53.363Z"
modified_at: "2025-12-04T14:06:52.291Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/third-party-integration-guide-6-6-oracle-database"
synced_at: "2026-01-28T21:04:57.989Z"
checksum: "2e8f5e6ae84a7eee"
---

It's possible to configure an Oracle database for use with Doxee products. This section details some known issues which may occur in this use case, and possible solutions.

## Automatic Sequence Generation
The automatic generation of database entities does not correctly create the necessary sequence for Oracle databases. When using an Oracle database, it is therefore necessary to execute the matching SQL script before starting the application.

For more information, see the storage configuration section in the Administration Guide of the respective application.

## Query Performance Optimization
When configuring Doxee products to use an Oracle database (for example as persistence storage in Process Engine) of version 18c or higher, it might occur that connecting to the database takes a lot of time, which leads to very long startup times. This behaviour is caused by the Hibernate library which is used by multiple Infincia products for managing database interaction. When Hibernate establishes the database connection, it executes the following SQL query multiple times. 

`select * from all_sequences;`Depending on how the database is optimized and under which user it is executed, this query can become very slow. To verify that this is a problem when using a particular Oracle database, a user can execute the SQL query directly and measure the time it takes until a result is returned. If this operation takes a few seconds or more, it can significantly delay application startup, since it happens multiple times.

This problem can be mitigated by improving the query performance through optimizations on the database. One way to achieve this is gathering optimizer statistics for the data dictionary and fixed objects. This can be achieved by running the following commands on the Oracle server once. 

`begin
    dbms_stats.gather_dictionary_stats;
    dbms_stats.gather_fixed_objects_stats;
end;`There is no guarantee that this solution will work for every case. Different or additional steps might be necessary to improve the query performance. 

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}