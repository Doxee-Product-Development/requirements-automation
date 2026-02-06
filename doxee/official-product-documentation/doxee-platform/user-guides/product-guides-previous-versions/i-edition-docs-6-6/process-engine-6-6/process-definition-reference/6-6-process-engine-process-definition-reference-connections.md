---
id: "542c7e2b-846d-4dea-ae44-e8affd373b25"
title: "Connections"
slug: "6-6-process-engine-process-definition-reference-connections"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T12:29:52.003Z"
modified_at: "2025-08-20T14:22:23.311Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-connections"
synced_at: "2026-01-28T21:01:25.491Z"
checksum: "c306dca39ed2487e"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

## Common Attributes
**id (1)**

Connections, like all process components, always have an ID. If the process definition does not specify one, the ID is automatically generated when loading the process definition. As with elements, the IDs are hierarchical. IDs of connections defined inside elements (e.g. groups) are automatically pr2efixed with their parent element’s IDs followed by a dot (.). Therefore, multiple elements in different scopes may use the same local IDs - their full IDs will still be unique.

**name (0..1)**

Optional human readable name of the connection. Does not have to be unique. In visual representations the name is used as a label for the connection.

**from (1)**

ID of the connection’s source element. 

**to (1)**

ID of the connection’s target element.

**savePoint (0..1)**

If the connection has a savePoint element, the process will persist at this point. For more information about save points and process persistence please refer to the Process Engine User Guide.

**delay (0..1)**

An optional delay (in milliseconds). If this is set, the process will await for the specified amount of time before continuing execution after the connection. The process will *not *change its execution state, i.e. it will remain `RUNNING`.

## Standard Connections
A standard connection connects a source element to a target element to define the regular process execution flow. At runtime, after successfully executing a source element, process execution will follow its outgoing connection to continue at the connection’s target element.

`&lt;connection id="..." name="..." from="..." to="..." &gt;
    &lt;savePoint/&gt;
&lt;/connection&gt;`### Implicit Connections
If the process’s connections parameter is set to `implicit` (or not set at all), not all connections have to be included in the process definition. When reading a process definition, any element that is not an end element and does not have an outgoing connection will automatically cause an implicit connection to be created. The element without a previous outgoing connection will be set as the connection’s source, and the element defined next in the process definition will be the connection’s target. The connection will also have an automatically generated ID.

Generation of implicit connections can be deactivated by setting the process’s connections parameter to `explicit`. In this case, no connections will be generated automatically, and non end elements without outgoing connections will be considered errors in the process definition.

Implicit connections can be useful when writing IPD code manually. When using Process

Designer, using implicit connections is discouraged, as the order of elements in the resulting IPD code, and therefore the order in which elements would be linked by implicit connections, is not strictly defined. Process definitions created using Process Designer will therefore always have their connections parameter set to `explicit`.

## Exception Connections
An exception connection can be defined to handle exceptions that occur at its source element. When an exception of a matching type is raised, execution will continue along the exception connection. The target element of an exception connection is called the exception handler.

`&lt;exceptionConnection id="..." name="..." from="..." to="..." type="..." &gt;
    &lt;savePoint/&gt;
&lt;/exceptionConnection&gt;`**type (1)**

Defines the exception types(s) handled by the connection.

The exception type element can specify either exact exception types or groups of exceptions using the asterisk wildcard (*). Multiple exception types can be listed by separating them with commas (,).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}