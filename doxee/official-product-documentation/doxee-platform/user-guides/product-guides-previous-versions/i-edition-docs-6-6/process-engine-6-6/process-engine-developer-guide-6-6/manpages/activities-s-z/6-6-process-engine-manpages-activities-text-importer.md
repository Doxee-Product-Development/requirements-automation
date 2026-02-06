---
id: "eeef61a3-e5e6-4746-baa6-65a0b203b491"
title: "Text Importer"
slug: "6-6-process-engine-manpages-activities-text-importer"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T13:43:56.468Z"
modified_at: "2025-08-22T17:33:38.882Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-text-importer"
synced_at: "2026-01-28T21:02:48.716Z"
checksum: "801bea234e115d3e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(textImporter, Module: [Base](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-base)) Imports text lines as XML.

Multiple text data formats can be handled in one file. Each line of the provided data file(s) is imported into a separate XML element, and all the elements generated from one file are grouped into one XML document.

A configuration file must be provided. This file is expected to contain a list of data format declarations. Each declaration except the last one must contain a pattern (most commonly a prefix) which is checked to see if a line belongs to the declared format, followed by the detailed specification of the data format.

Each declaration consists of the following fields:

`match` (regular expression; mandatory except for the last declaration)

A regular expression that must match the text of the data line to determine that this line is of the declared format and will be converted to XML using these settings.Most commonly, the data format of a line is defined by a prefix. To match e.g. the prefix 'XY', use this pattern: ^`XY`.*

`offset` (integer; optional)

If an offset is provided, the given number of characters are stripped away from the data line before importing it. This is most commonly used to skip the prefix that identifies the data format.

`header` (text; optional)

A header line may be provided. If present, it will be used as first line when parsing the data lines.

`builder` (query string; mandatory)

The builder defines how an XML structure is created from the imported data fields. In its simplest form, a builder defines the name of the XML element that contains the data fields (parameter `row`) like this: `row=XY`Other valid parameters are: `field, nameAttribute, valueAttribute, namespace`. For further information, look up these parameters on the types `text/csv` or `x-infinica/fixedwidth`.This is an example with more parameters:`row=XY&amp;field=field&amp;nameAttribute=name&amp;valueAttribute=value&amp;namespace=http://www.infinica.com`

`type` (text; mandatory)

The type of the data format. Supported values are CSV and FIXED, which correspond to the types `text/csv` and `x-infinica/fixed-width`.

`definition` (text; mandatory)

The format of the definition depends on the type:CSVExactly four letters, corresponding (in this order) to the parameters `separator, quote, doubleQuotesEscape`, and `autoDetect` of the type `text/csv`.

FIXED

The pattern of the data format as defined in the parameter `pattern` of the type `xinfinica/fixed-width.`

Multiple declarations are separated by empty lines. If a data line does not match any data type declaration, an exception will be raised.

Comments can be included in the definition file by starting a line with '#', ';', or '//'. Comment lines count as empty lines, so they separate declarations.

The following example is a valid definition:

`match:^AB.* offset:2 header: a b c builder:row=AB type:FIXED definition: (!&lt;4&gt;{\d+}) (!&lt;4&gt;{\d+}) (!&lt;4&gt;{\d+}) match:^XY.* offset:2 builder:row=XY type:FIXED definition:(!&lt;4&gt;[number]{\d+}) | (&lt;10*[name]);`The following data would match this definition:

`XY1138 | Text; AB 1 2 3 AB 13 17 19 XY4711 | More; AB 42 73 37`Finally, this is the expected conversion result in XML:

`&lt;result&gt; &lt;XY&gt; &lt;number&gt;1138&lt;/number&gt; &lt;name&gt;Text&lt;/name&gt; &lt;/XY&gt; &lt;AB&gt; &lt;a&gt;1&lt;/ a&gt; &lt;b&gt;2&lt;/b&gt; &lt;c&gt;3&lt;/c&gt; &lt;/AB&gt; &lt;AB&gt; &lt;a&gt;13&lt;/a&gt; &lt;b&gt;17&lt;/b&gt; &lt;c&gt;19&lt;/c&gt; &lt;/AB&gt; &lt;XY&gt; &lt;number&gt;4711&lt;/number&gt; &lt;name&gt;More&lt;/name&gt; &lt;/XY&gt; &lt;AB&gt; &lt;a&gt;42&lt;/a&gt; &lt;b&gt;73&lt;/b&gt;
&lt;c&gt;37&lt;/c&gt; &lt;/AB&gt; &lt;/result&gt;` 

**Input Parameters:**

- definition (x-infinica/stream)

The text format definition file in UTF-8 encoding.

- data (x-infinica/stream) (1-unbounded) 

The data file(s).

- encoding (text/plain) (0-1)

Optional: Encoding of the data file(s). Defaults to UTF-8.

**Output Parameter:**

- converted (text/xml) (1-unbounded)

The imported data file(s) as XML document(s), one document for each file.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}