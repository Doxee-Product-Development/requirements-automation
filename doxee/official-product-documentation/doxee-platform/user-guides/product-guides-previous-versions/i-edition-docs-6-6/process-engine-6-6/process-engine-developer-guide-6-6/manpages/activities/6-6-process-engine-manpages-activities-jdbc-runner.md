---
id: "cc67eddd-52e9-4273-9b2c-250e2d2c6d26"
title: "JDBC Runner"
slug: "6-6-process-engine-manpages-activities-jdbc-runner"
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
created_at: "2025-08-13T11:11:31.17Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-jdbc-runner"
synced_at: "2026-01-28T21:02:23.807Z"
checksum: "3367734f4be2dfca"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(jdbcRunner, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base))

Runs an SQL statement and creates a DOM result from the result sets, if available. Also writes any output parameters to the activity's output parameters.

**Input Parameters:**

- connection (x-infinica/jdbc-connection, x-infinica/java) (0-1)

A JDBC connection previously opened with jdbcConnect. If no connection is provided, a new one willbe opened and closed afterwards.

- driver (text/plain) (0-1)

The database driver class name. Only used if no connection was specified.

- url (x-infinica/url) (0-1)

The database URL from which input will be read. Required if no connection was specified, not used otherwise.

- query (text/plain)

The SQL statement that should be executed. Curly brace parameters inside this statement may specify ":in", ":out", or ":inOut" as parameter types between their name and type e.g. "param:out:string"). If not specified, this flag defaults to "in". Output parameters (and in/out parameters) are only allowed for stored procedure calls. Stored procedure calls are recognised by starting with the 'call' keyword, unless explicitly specified with the 'storedProcedureCall' parameter. Stored procedure using the 'call' keyword are automatically wrapped in curly braces for execution, unless specified differently with the 'wrapCallsWithComment' parameter.

- user (text/plain) (0-1)

The database user name. Only used if no connection was specified.

- password (x-infinica/secret-text) (0-1)

The database password. Only used if no connection was specified.

- deadlockPattern (text/plain)

The regex pattern to detect if an SQL exception is reporting a deadlock. Defaults to ".*deadlock.*", i.e. any exception message with the text "deadlock" in it will be interpreted as a deadlock exception.

Default:

 (?i).*deadlock.

- deadlockRetries (x-xsd/integer)

The number of retries after a deadlock was detected. Defaults to 10.

Default:

10

- deadlockDelay (x-xsd/integer)

The number of milliseconds that the activity will wait after a deadlock before retrying. Defaults to 5.

Default:

5

- namespace (x-infinica/url) (0-1)

The namespace URI for the DOM result.

- rootElementName (text/plain) (0-1)

The name for the root element in the DOM result.

- rowElementName (text/plain) (0-1)

The name for the row elements in the DOM result. If not specified, "row" will be used.

Default:

 row

- fieldElementName (text/plain) (0-1)

The name for the field elements in the DOM result. If not used, these elements will be named after their respective database columns.

- nameAttribute (text/plain) (0-1)

The name for the column name attribute of field elements in the DOM result. If not specified, names will not be provided as attributes.

- valueAttribute (text/plain) (0-1)

The name for the value attribute of field elements in the DOM result. If not specified, values will be provided as text content of their field elements.

- storedProcedureCall (x-xsd/boolean) (0-1)

Whether the SQL query represents a stored procedure call. If not specified, the value is autodetected by checking if the query begins with a 'call' statement or, in the case of MSSQL, with an 'exec' statement.

- returnKeys (x-xsd/boolean) (0-1)

Whether to return created keys. If not set, it will be automatically set to true if the statement start with 'insert'. Set this to false if the JDBC driver does not support the getGeneratedKeys() method.

- queryParameterValues (0-unbounded)

If the query contains parameter names in curly braces, their values are usually taken from activity parameters with the same names. Alternatively, this parameter may be used to provide a list of values for the query parameters. In this case, a query parameter that is not provided as a named activity parameter will instead be taken from the parameter values list using the index of the curly brace parameter as the list index.

- dialect (text/plain)

JDBC dialect (i.e. database type). Currently supported values are 'auto', 'derby', 'mssql', 'mysql', 'oracle', 'postgresql', and 'other'. If 'auto' (the default) is specified, the dialect will be determined automatically from the database connection.

Default:

auto

- wrapCallsWithComment (0-1)

If activated, the SQL query will automatically be wrapped in a curly brace comment if it is a stored procedure call that uses a 'call' statement. Other stored procedure calls (e.g. MSSQL's 'exec' statement) will not be modified. Some database systems require this when calling stored procedures.

If not specified, the value is determined automatically from the dialect.

- readOnly (x-xsd/boolean) FIXME

Default:

false

- *

Additional input parameters to be mapped by query parameters.

**Output Parameters:**

- xml (text/xml) (0-1)

The data read from the database.

- xsd (text/xml) (0-1)

The schema created from the database query.

- rowCount (x-xsd/integer) (0-1)

The number of rows affected by the SQL statement.

- keys (text/plain) (0-unbounded)

All keys created by the statement.

- Any output parameters specified in the query are provided as outputs with their corresponding names.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}