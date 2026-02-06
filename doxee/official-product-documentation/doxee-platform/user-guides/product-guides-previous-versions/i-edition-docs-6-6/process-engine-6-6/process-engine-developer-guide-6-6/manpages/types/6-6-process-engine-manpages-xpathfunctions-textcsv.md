---
id: "84b1d8e2-3b37-4984-ad57-e9e2bfb27704"
title: "text/csv"
slug: "6-6-process-engine-manpages-xpathfunctions-textcsv"
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
created_at: "2025-08-13T16:04:32.704Z"
modified_at: "2025-08-22T17:34:19.966Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-textcsv"
synced_at: "2026-01-28T21:03:40.669Z"
checksum: "47c2cbcaea92a4a4"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core))

Comma separated values data, or other text data formats with a defined separator character. This type is based on the CSV format as specified in RFC 4180, but provides some parameters to control its behaviour.

Values of this type can be converted to `text/xml` to access and parse their content. If the CSV data contains a header line, the header's column names can be used as the field names in the XML.

**Parameters:**

- **charset**

The character set of the data string.

- **type**

Specifies a standard type, which provides default values for the other parameters. Available types are default and Excel.

**default:**  Corresponds to RFC 4180. Uses a comma separator and double quotes as the quote character. Also enables double quote escaping. Does not use autoDetect. 

**excel:**  Corresponds to the standard Microsoft Excel settings for CSV data with a comma separator.

Differs form default by setting autoDetect to true.

- **separator**

Separator character.

- **quote**

Quote character.

- **doubleQuotesEscape**

If this is true, a quote character followed immediately by another quote character does not start or end a quoted section but instead is used like a regular content character.

- **header**

Specifies whether the CSV data includes a header line. Possible values are present and absent.

- **autoDetect**

If this is true, the CSV data may begin with a line starting with the string sep=, followed by the separator character used in the data. If this is found, it overrides the separator character specified with the separator parameter.

**Conversions:**

x-infinica/stream → text/csv 

text/csv → x-infinica/stream

text/csv → text/xml 

text/plain → text/csv 

text/csv → text/plain

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}