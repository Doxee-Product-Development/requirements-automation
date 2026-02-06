---
id: "2e746cf9-471b-408c-9d59-9f488197704d"
title: "x-infinica/fixed-width"
slug: "x-infinicafixed-width"
category: "Types"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T16:08:24.332Z"
modified_at: "2025-08-22T17:34:19.966Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/x-infinicafixed-width"
synced_at: "2026-01-28T21:03:43.896Z"
checksum: "525ac40aa92070c3"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core))

Line based fixed width string formats.

Values of this type can be converted to text/xml to access and parse their content. If the fixed width data contains a header line, the header's column names can be used as the field names in the XML. There are two types of parameters listed below. Charset, header and pattern can be set directly on the fixed-width type and are applied when parsing the text. The rest of the parameters can only be set on an XML type when converting from fixed-width to XML. The descriptions for those parameters start with "[XML]".

**Parameters:**

- **charset**

The character set of the data string.

- **header**

Specifies whether the fixed width data includes a header line. Possible values are present and absent.

- **pattern**

Describes the pattern of a single line in the data string. The pattern can have a prefix, a suffix and any number of column definitions separated by separators:

`prefix(c1)sep1(c2)sep2(c3)suffix`

Prefixes, separators and suffixes are static strings. Column definitions are always specified between parentheses and consist of the following parts:

Optional flag

! marks a column as mandatory, while ? marks it as optional. If neither flag is specified, the column is considered mandatory. No mandatory columns may follow an optional column.

Skip flag

- specifies that the column should be parsed, but not included in the data. Columns with this flag can be used as complex separators. 

Trim flags

&lt; means that the column's content should be trimmed on the left. &gt; signifies trimming on the right. Trimming removes all whitespace at the beginning or end of the data string.

Length

A decimal number specifying the length of the column, in characters. Unless otherwise specified, values in this column must have exactly the specified length. 

Variable length flag

* specifies that values in this column may be shorter than the specified length. Only optional columns are allowed after a column with variable length.

Name

A name for the data column may be specified in brackets. If the data includes a header line, column names from the header line take precedence.

Pattern

A regular expression in curly braces may be specified. If a data column contains a string which does not match the specified expression, an exception will be raised when parsing the fixed width data.

An example pattern defining a prefix, a column 'number' of 4 digit characters (trimmed on both sides), a character separator consisting of a space, a pipe, and a space, a second column 'name' of up to 10 characters (trimmed on the left), and a suffix may look like this:

`Data: (!&lt;4&gt;[number]{\d+}) | (&lt;10*[name]);`The following data would match this pattern:

`Data: 1138 | Text; Data: 42 | ;`- **root**

[XML]

Name of the root element when converting to XML. Defaults to root.

- **row**

[XML]

Name of the row elements when converting to XML. Defaults to row.

- **field**

[XML]

Name of the field elements when converting to XML. Defaults to field. If this is set to an empty string, the field's column name will be used as the element name.

- **nameAttribute**

[XML]

Name of the attribute containing the column name of a field. Only used if field is empty. Defaults to name if a field name is specified.

- **valueAttribute**

[XML]

Name of the attribute containing the value of a field. If not set, the value will be set as the element's content.

- **namespace**

[XML]

Optional namespace URL for the XML elements.

**Conversions:**

x-infinica/stream → x-infinica/fixed-width

x-infinica/fixed-width → x-infinica/stream 

x-infinica/fixed-width → text/xml 

text/plain → x-infinica/fixed-width 

x-infinica/fixed-width → text/plain

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}