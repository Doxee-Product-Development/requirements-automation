---
id: "e048077e-8a29-461d-96bb-ca725805601b"
title: "Constants and Attributes"
slug: "6-6-process-engine-process-definition-reference-constants-and-attributes"
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
created_at: "2025-08-06T12:29:52.249Z"
modified_at: "2025-08-20T17:37:22.255Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-constants-and-attributes"
synced_at: "2026-01-28T21:01:26.495Z"
checksum: "c2422d07fb0d9205"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Constants are a special type of variables which have fixed values and cannot be modified throughout process execution. Accessing them works just like for normal variables. They are inherited by all pipelines of a process. This means they can be accessed from any point within the process, without the need to map them between pipelines.

Constants can be defined in three ways and have different scopes depending on where they have been defined. There are engine scoped (global), definition scoped and instance scoped constants. If multiple constants have the same name, the one with the lowest scope is used during execution.

## Engine Scoped Constants
Engine scoped constants are defined in the configuration file of the process engine. They can be accessed from any process which is executed by this engine. Detailed information on how to configure constants for the engine can be found in the Administration Reference of the Process Engine.

## Definition Scoped Constants
Definition scoped constants can be included in the process definition file as part of the header. They can be accessed by any process instance created from this process definition. Engine scoped constants are overwritten by these during execution. The structure for defining them in XML is described below.

`&lt;constants&gt;
  &lt;constant&gt;...&lt;/constant&gt;
&lt;/constants&gt;`constant (0..n)

Constant definition.

Each constant definition has the following format:

`&lt;constant name="..." type="..." public="..." final="..." transitive="..."&gt;
  &lt;value&gt;...&lt;/value&gt;
&lt;/constant&gt;`**name (1)**

Constant name.

**type (0..1)**

Optional constant type. Defaults to `text/plain.`

**public (0..1)**

A boolean value defining whether the constant is public and may be queried by clients. Defaults to `false`.

**final (0..1)**

A boolean value specifying whether the constant is final. Defaults to `false`. Final constants may not be redefined by sub groups of the process or group they are defined in. Final global constants may also not be redefined on the top level of process definitions. An instance constant may only be set if there is no final constant either in the global configuration or on the top level of the process definition. Sub processes included via include elements may redefine final constants of the process they are loaded into, as long as those constants are not globally final.

**transitive (0..1)**

A boolean value specifying whether the constant is transitive. Defaults to `false`. Transitive constants are automatically passed on to other processes instantiated from the process containing them, e.g. via the `instantiateProcess` and `executeProcess` activities, and the `process` wait state.

**value (1..n)**

One or more values for the constant. Each value is specified as a literal (see [Literal Source](/doxee-platform/docs/chapter-5-mappings#literal-source) for details).

If a constant’s type is defined, its values are automatically converted to and stored as the correct type. If the literal given by a value element does not represent a valid value of the specified type, loading the process definition fails with an exception.

> Note:

By convention, constants are usually named using only upper case letters. This naming pattern is not mandatory, but recommended to easily recognise the difference between constants and regular pipeline variables.

## Instance Scoped Constants
Instance scoped constants can be defined by calling the `setConstant` method of the Process Engine API. They are always set for a specific process instance and only exist while this instance is executed. Only this instance can access them. Engine and definition scoped constants are both overwritten by these during execution.

## Attributes
Similar to constants, attributes are special variables with fixed values. They can be set on a process instance using the `setAttribute` method of the Process Engine API. Set attributes can be fetched with the `getAttributes` method. The main purpose of these attributes is to provide metadata about the process execution. From within the process, attributes can be accessed by using *attributes..* as prefix. The combination of prefix and attribute name can be used in the same way as a variable or constant.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}