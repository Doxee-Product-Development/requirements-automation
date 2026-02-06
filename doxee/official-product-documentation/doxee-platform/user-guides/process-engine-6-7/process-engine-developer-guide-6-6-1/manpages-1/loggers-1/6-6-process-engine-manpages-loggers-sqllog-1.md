---
id: "62cc4389-d9ce-4490-90fd-53a02bd395bf"
title: "sqlLog"
slug: "6-6-process-engine-manpages-loggers-sqllog-1"
category: "Loggers"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Loggers"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:08.735Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-loggers-sqllog-1"
synced_at: "2026-01-28T20:57:29.045Z"
checksum: "158009625aa53396"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(sqlLog, Module: [Database Logging](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-database-logging-1))

SQL logging writes all output to an external SQL database. The database format is well defined so that 3rd party applications can access the log to perform diagnostics and reporting.

`&lt;sql driver="com.mysql.jdbc.Driver" url="jdbc:mysql://localhost/ process_engine" user="doxee" password="test123" cacheSize="100" keyColumnType="..."&gt; &lt;properties&gt; .... &lt;/properties&gt; &lt;processState&gt; &lt;field&gt;...&lt;/field&gt; &lt;/processState&gt; &lt;diagnostic level="debug"&gt; &lt;field&gt;...&lt;/ field&gt; &lt;/diagnostic&gt; &lt;data level="debug"&gt; &lt;field&gt;...&lt;/field&gt; &lt;/data&gt; &lt;trace enabled="true"&gt; &lt;field&gt;...&lt;/field&gt; &lt;/trace&gt; &lt;/sql&gt;``The attributes driver, url, user` and `password` are used to set up the database connection. cacheSize specifies the maximum number of log messages that should be cached before writing them to the database, to reduce the number of individual database operations.

The `keyColumnType` defines how the database handles auto generated IDs. `local` means that IDs are created locally by the Process Engine. `index, lowerCase and upperCase` let the database generate the ID and return it with the result of the SQL operation. index means that the generated ID is read from the result via its column index, while `lowerCase` and `upperCase` use the column name instead. Different JDBC drivers require different settings, but if the type is not specified explicitly, Doxee should determine the correct type for the used driver automatically.

A C3P0 connection pool is used to pool the database connections. Additional properties can be provided for the C3P0 manager in the form of key/value pairs specified as child elements of the &lt;sql&gt; element:

`&lt;property key="key" value="value" /&gt;`For `&lt;diagnostic&gt;` and `&lt;data&gt;` logging, the log `level` can be configured. Trace logging can be enabled or disabled using the `&lt;trace&gt;` element's boolean attribute `enabled`.

All log message types may list a number of field names corresponding to the attributes defined in the main logging configuration. These attributes are then logged along with each log message of that type.

The referenced database must exist and contain the required tables. SQL scripts for creating the database can be found in the distribution.6-6-process-engine-manpages-xpathfunctions-

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}