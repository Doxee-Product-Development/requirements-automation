---
id: "390382bb-b767-4ec9-a376-777be7e438ab"
title: "Base"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-base-1"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:09.454Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-base-1"
synced_at: "2026-01-28T20:55:10.728Z"
checksum: "7a1c1cc6175bbfc3"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Common activities and XPath functions required for many processes.

Activities:

[Acquire Lock](/doxee-platform/docs/6-6-process-engine-manpages-activities-acquire-lock-1), [Create temp file](/doxee-platform/docs/6-6-process-engine-manpages-activities-create-temp-file-1), [Digest](/doxee-platform/docs/6-6-process-engine-manpages-activities-digest-1), [Directory Creator](/doxee-platform/docs/6-6-process-engine-manpages-activities-directory-creator-1), [Executor](/doxee-platform/docs/6-6-process-engine-manpages-activities-executor-1), [Image Splitter](/doxee-platform/docs/6-6-process-engine-manpages-activities-image-splitter-1), [JDBC Close Connection](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-close-connection-1), [JDBC Commit](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-commit-1), [JDBC Connect](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-connect-1), [JDBC Reader](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-reader-1), [JDBC Rollback](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-rollback-1), [JDBC Runner](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-runner-1), [JDBC Writer](/doxee-platform/docs/6-6-process-engine-manpages-activities-jdbc-writer-1), [Multi URL Writer,](/doxee-platform/docs/6-6-process-engine-manpages-activities-multi-url-writer-1) [Printer Finder,](/doxee-platform/docs/6-6-process-engine-manpages-activities-printer-finder-1) [Properties Converter txt to xml](/doxee-platform/docs/6-6-process-engine-manpages-activities-properties-converter-txt-to-xml-1), [Properties Converter xml to txt](/doxee-platform/docs/6-6-process-engine-manpages-activities-properties-converter-xml-to-txt-1), [Regex Replacer,](/doxee-platform/docs/6-6-process-engine-manpages-activities-regex-replcaer-1) [Release Lock](/doxee-platform/docs/6-6-process-engine-manpages-activities-release-lock-1), [Stream Printer](/doxee-platform/docs/6-6-process-engine-manpages-activities-stream-printer-1), [String Replacer,](/doxee-platform/docs/6-6-process-engine-manpages-activities-string-replacer-1) [TCP Writer](/doxee-platform/docs/6-6-process-engine-manpages-activities-tcp-writer-1), [Text Importer](/doxee-platform/docs/6-6-process-engine-manpages-activities-text-importer-1), [Text Splitter](/doxee-platform/docs/6-6-process-engine-manpages-activities-text-splitter-1), [URL Connector](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-connector-1), [URL Copier](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-copier-1), [URL Deleter](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-deleter-1), [URL Disconnector](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-disconnector-1), [URL Finder](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-finder-1), [URL Mover](/doxee-platform/docs/url-mover-1), [URL Reader](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-reader-1), [URL Writer](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-writer-1), [Xsl Renderer](/doxee-platform/docs/6-6-process-engine-manpages-activities-xsl-render-1), [Zip](/doxee-platform/docs/6-6-process-engine-manpages-activities-zip-1)

XPath functions:

[alphaNumeral](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-alphanumeral-1), [currentTimeMillis](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-currenttimemillis-1), [propertiesToXml](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-propertiestoxml-1), [regexp](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-regexp-1), [uuid](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-uuid-1), [xmlToProperties](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-xmltoproperties-1)

Type:

[x-infinica/jdbc-connection](/doxee-platform/docs/6-6-process-engine-manpages-xpathfunctions-x-infinicajdbc-connection-1)

## Database Access
### SQL Statements
The JDBC activities (`jdbcRunner` in particular) use SQL statements which are provided as input parameters. While these parameters, like all others, can use parameterised literal sources and XPath sources, they should not be used to insert dynamic values into SQL statements, for two reasons

- Some values, like strings, require quotation characters, while others, like numbers, must not use them.

- If a dynamic value in an SQL statement contains a special character which is significant in SQL (like a semicolon or a quote), the statement can be changed significantly, even turning simple queries into delete statements. This is known as SQL injection.

Instead, SQL statements for these activities may contain references to additional parameters which are mapped into the activity as separate inputs. These parameters are referred to by surrounding their name with curly braces in the statement string. For example, the following statement uses a parameter named `myId: SELECT * FROM myTable WHERE id={myId:string}`

The value for the myId parameter must be provided as a separate input mapping. `string` specifies the parameter's type and will automatically add the necessary quote characters to the effective statement.

Supported types are:

- bigDecimal

- boolean

- blob

- byte

- bytes

- clob

- double

- float • int

- long

- short

- string

The parameter values must match the specified types. `blob` values are typically stream variables `(xinfinica/stream-variable)`. All other types use string representations of their values, e.g. a float parameter may be of type `x-xsd/float, x-xsd/intger`, or `text/plain`, as long as it represents a valid float value.

Instead of referencing an input parameter directly, a curly brace expression in an SQL statement may also specify an XPath expression, by wrapping it in an additional pair of curly braces:

`INSERT INTO myTable(name) VALUES({{concat($firstName, ' ',$lastName)}:string})`

In this case, all referenced parameters must be provided as input mappings.

**Important:** Parameter expressions must be wrapped in curly braces (or double curly braces for XPath expressions) in the SQL statement as received by the activity, i.e. the result of the input mapping providing the statement must contain the curly brace characters. This is true for regular literal sources. For parameterised literal sources, the curly braces for SQL parameters must be escaped using backslash characters, to prevent them from being treated as parameterised literal parameters instead of SQL parameters:

`INSERT INTO myTable(name) VALUES(\{\{concat($firstName, ' ',$lastName)\}:string\})`

### SQL Query Results
The result sets returned by jdbcRunner are presented in a customiseable XML format. The default format looks like this:

`&lt;tableName&gt;
  &lt;row&gt;
    &lt;col1&gt;value1&lt;/col1&gt;     &lt;col2&gt;value2&lt;/col2&gt;
  &lt;/row&gt;
  &lt;row&gt;
    &lt;col1&gt;value3&lt;/col1&gt;     &lt;col2&gt;value4&lt;/col2&gt;
  &lt;/row&gt;
&lt;/tableName&gt;`In this example, `tableName` and `col1` and `col2` are taken from the result set produced by the JDBC driver and represent the table and column names in the database, while `row` is a hardcoded default name for each result set row. Note that this will fail if either of these names are not valid XML names. In this case, the customisation options must be used to change the XML format.

The XML always consists of a root element containing one child element for each result set row. Each row contains one *field element* per database column.

With input parameters for the activity, the name of the root, row, and field elements can be set to custom strings. A name for a value attribute can be provided, in which case the column values will not be presented as the text content of the field elements, but instead as attributes of the column elements. Likewise, a name for the 'name attributes' can be specified, which causes the column name to be provided as an attribute on the field element. The namespace for all elements can be configured as well.

These following settings would produce the following XML structure (for the same content as the above example):

rootElementName

resultSet

rowElementName

entry

fieldElementName

field

nameAttribute

column

valueAttribute

value

`&lt;resultSet&gt;
  &lt;entry&gt;
    &lt;field column="col1" value="value1" /&gt;     &lt;field column="col2" value="value2" /&gt;
  &lt;/entry&gt;
  &lt;entry&gt;
    &lt;field column="col1" value="value3" /&gt;     &lt;field column="col2" value="value4" /&gt;
  &lt;/entry&gt;
&lt;/tableName&gt;`### JDBC Connections
The `jdbcConnect` activity can be used to create a new JDBC connection. This connection will remain open so that it can be shared by multiple other JDBC activities (e.g. multiple `jdbcRunners`). If transactions are enabled on the connection, any changes made on the connection will not be committed automatically. The `jdbcCommit` activity can then be used to commit all pending changes.

A JDBC connection is a process resource. As such, it will be automatically released when the process is unloaded from memory, e.g. when it finishes. To release a JDBC connection before the process ends, the standard `releaseResource` activity can be used.

#### Dirty Connections
As long as a connection is not *dirty*, it may also be closed during process execution to allow the process to be unloaded while paused, e.g. in a wait state. The connection will then automatically be reopened when the process resumes. While a connection is dirty, it will prevent the process from being automatically unloaded (unless forced).

Only transactional connections can be dirty. A connection becomes dirty by executing an SQL statement that may write to the database, e.g. a `jdbcRunner` that does not have the `readOnly` flag set. Committing or rolling back a transaction will un-dirty the connection.

## Printer Access
### Printer Finder Results
The results of the printer finder activity are presented as an XML structure with the following format:

`&lt;printers&gt;
  &lt;printer name="..."&gt;
    &lt;attribute name="..."&gt;...&lt;/attribute&gt;
    ...  
    &lt;supportedAttribute name="..."&gt;       &lt;supportedValue default="true"&gt;...&lt;/supportedValue&gt;       &lt;supportedValue&gt;...&lt;/supportedValue&gt;       ...     &lt;/supportedAttribute&gt;     ...
&lt;/printers&gt;`Each printer may contain any number of attributes and supported attributes.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}