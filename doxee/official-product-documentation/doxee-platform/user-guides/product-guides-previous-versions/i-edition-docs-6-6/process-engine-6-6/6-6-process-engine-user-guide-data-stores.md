---
id: "466c7001-f943-498f-821c-069380207c9c"
title: "Data Stores"
slug: "6-6-process-engine-user-guide-data-stores"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T17:05:13.609Z"
modified_at: "2025-08-19T17:02:23.984Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-data-stores"
synced_at: "2026-01-28T21:01:19.410Z"
checksum: "f790dcd9f6271f6f"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

A *data store* is a container for typed data. Uses include the representation of process pipelines, process constants and task payload.

Each data store consist of a series of *data store entries*. An entry has a *name*, a *type* (in the form of a content type, e.g. `text/plain`), and one or more *values*.

Data stores can be represented in XML and JSON, allowing their persistence and the exchange of partial or entire data stores between applications, e.g. between a Process Engine and a Task Manager. A data store can be represented in `standard format` or `simple format`. The following sections describe both types in XML form; JSON representations of the respective formats are simple conversions of these XML structures.

## Standard Format
The standard format is able to exactly represent a data store, including shared structures (e.g. multiple `x-infinica/xml-node` entries belonging to the same `text/xml` document). As a result, this format is considerably more complex than the alternative simple format.

A data store in standard format consists of a list of values and a list of entries which reference these values. Multiple entries may reference the same value.

Values are represented in a format defined by their respective type. Each value has its own unique content and may also reference additional values. For example, `text/plain` values are represented simply as their string content, while `text/xml` values use their XML data as the content. `x-infinica/xml-node` values reference their XML data as a separate value and themselves store the reference to that value and an XPath expression which describes the position of the node in the XML. This allows multiple XML nodes to share the same XML document (possibly even one that also has its own named data store entry as a `text/xml` value), and it allows clients to receive XML node values and 'step upwards' in their XML document, as the full document is retained.

`&lt;dataStore xmlns="http://www.infinica.com/datastore"&gt;
  &lt;values&gt;
    &lt;value&gt; ①
        id="..." ②
        type="..."&gt; ③
      &lt;ref&gt;...&lt;/ref&gt; ④
      ...
      &lt;content&gt;...&lt;/content&gt; ⑤
    &lt;/value&gt;
  &lt;/values&gt;
  &lt;entries&gt;
    &lt;entry ⑥
        name="..."&gt; ⑦
      &lt;value&gt;...&lt;/value&gt; ⑧
      ...
    &lt;/entry&gt;
  &lt;/entries&gt;
&lt;/dataStore&gt;`### Values
**value (0..n) [1]**

Each value is represented by its own element.

**id [2]**

The unique ID of the value.

**type [3]**

The type of the value, as a content type.

**ref (0..n) [4]**

The IDs of other values references by this value.

**content [5]**

This value’s unique content, as a string or sub XML structure.

### Entries
**entry (0..n) [6]**

Each data store entry is represented by its own element.

**name [7]**

The unique name of the data store entry.

**value (1..n) [8]**

The entry’s values. Each value is represented as the ID of the corresponding `value` element. Each entry has at least one value.

## Simple Format
The simple format presents a data store as a list of entries, each consisting of a name, a type, and a list of values. It is easy to parse, but cannot accurately represent some details of the actual data store, and some values can not be turned back into their exact original internal representations.

The simple format is recommended for client applications retrieving some data from Doxee, e.g. the output values of a process. To accurately exchange partial or complete data store between applications, the standard format should be used instead.

Entry values are simply string or XML representations of the entry’s original value. The exact format depends on the entry’s type. For example, `text/plain` values are represented simply as their string content, while `text/xml` values use their XML data as the content. `xinfinica/xml-node` values are represented as a standalone XML document with the value’s XML node as the root element. Any information 'above' that node is lost in the simple format.

`&lt;dataStore xmlns="http://www.infinica.com/datastore"&gt;
  &lt;entry ①
      name="..."&gt; ②
      type="..."&gt; ③
    &lt;value&gt;...&lt;/value&gt; ④
    ...
  &lt;/entry&gt;
  ...
&lt;/dataStore&gt;`**entry (0..n) [1]**

Each data store entry is represented by its own element.

**name [2]**

The unique name of the data store entry. 

**type [3]**

The type of the entry, as a content type.

**value (1..n) [4]**

The entry’s values, as strings or sub XML structures. Each entry has at least one value.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}