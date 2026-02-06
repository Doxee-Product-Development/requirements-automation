---
id: "e175f3ac-b0dc-4252-840a-4cb6fc8ff593"
title: "Variables and the Pipeline"
slug: "6-6-process-engine-user-guide-variables-and-the-pipeline-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.175Z"
modified_at: "2026-01-07T14:04:28.741Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-variables-and-the-pipeline-1"
synced_at: "2026-01-28T20:54:49.374Z"
checksum: "7a080a3930303372"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

At runtime, the pipeline is primarily accessed via mappings. Other ways to access the pipeline include XPath expressions in log directives and scripts which may directly read from and write to the pipeline.

## Mappings
A mapping takes a number of source values and writes them to a target. The source values are typically taken from the source pipeline, but a source value may also be a literal or a constant. The target of a mapping is always a variable in the target pipeline.

A mapping’s source and target pipeline vary depending on where the mapping is defined. For example, a mapping in a mapping element will always have the process’s pipeline as both its source and its target. By contrast, an activity element’s input mappings map from the process pipeline to the activity’s input parameters, while its output mappings map from the activity’s output parameters back to the process pipeline. A start element on the process level maps from the caller’s provided input parameters into the process pipeline, whereas an end element on the process level maps from the process pipeline to the output parameters returned to the caller. Start and end elements in groups and loops map between the group’s outer and inner pipelines.

### Mapping Steps
When a mapping is performed, the following steps are executed:

- Mapping sources are evaluated

- The resulting values are merged into a list

- Each resulting value is validated and converted to the target type, if necessary

- The final values are written to the targets

### Sources
A mapping may specify any number of sources. When the mapping is applied, each of these sources is evaluated and the resulting values are all written to the mapping’s target(s).

The following types of mapping sources are available:

#### **Literal Source**
Directly specifies the value it represents as a text string.

#### Parameterized Literal Source
Similar to a literal source, but may contain XPath expressions enclosed in curly braces ({}). These expressions are evaluated against the source pipeline. Their results are interpreted as strings.

#### Variable Source
Specifies the name of a variable in the source pipeline. All values from this variable are used. This source has a boolean attribute deleteFromSource which determines whether the variable should be deleted from the source pipeline after the Mapping. The default for the attribute is `false`.

#### XPath Source
Specifies an XPath expression that is evaluated on the source pipeline. The returned values of this expression are used.

#### **URL Source**
Specifies a URL from which the value is read.

#### **Null Source**
Provides no value.

### Value Resolution
Pipeline variables can have multiple values, but each existing variable has at least one value only non existent variables result in null values when they are evaluated as sources.

After evaluating a mapping’s sources, each source has provided a number (possibly 0) of values. All of these values are merged into a list of values, resulting in one, possibly empty, single list of values.

### Targets
#### Variable
The standard target for mappings is the variable target which specifies the name and type of a variable in the target pipeline to which the mapped values are written.

If a types is specified, each value collected from the mapping’s sources will be validated against and, if necessary, converted to the specified type. If any of the values fails this validation, the mapping will fail and throw a mapping exception.

#### Iteration
The iteration target is similar to the variable target and also specifies a name and type. In contrast to the variable target, the resolved list of values is not directly written to a variable. Instead the list is used for executing the element which the mapping belongs to multiple times, once for each value in the list. Each time the element is executed, one of the values is written to a variable with the name and type specified by the target. These iteration targets can be used to cause multiple executions for the following elements:

- Group: When used in a mapping within the start element of its sub-process.

- Mapping Element

- Activity: When used in an input mapping.

- Wait Element: When used in an input mapping.

- Task Element: When used in an input mapping.

- Whole process: When used in a mapping within the start element of the process.

For more information about iteration targets please refer to the Process Definition Reference.

#### Keep-Variables
A mapping with a Keep-Variables target clears the target pipeline and retains only those variables which are referenced by this mapping. The sources provide the names of variables which should still exist after the mapping has been executed.

### Null Values and Defaults
As variables must contain at least one value, the mapping cannot write a target variable if none of its sources provided any values. By default, this will result in a mapping exception.

However, a mapping can be made optional by setting its required parameter to `false`. In this case, if the mappings sources provide no values, the target variable is removed from the pipeline and regular execution continues.

Alternatively, each mapping can define a list of default values. If defaults are defined and the mapping’s sources provided no values, the default values will be used instead, without raising an exception.

### Sub Pipelines
Certain variables may contain entire process pipelines of their own. An example is the _exception variable passed to exception handlers, which contains the pipeline from the moment the exception was thrown. These pipelines are called sub pipelines.

The contents of a sub pipeline can be accessed using the dot character. For example, if a variable `pipeline` stores a pipeline which contains the variable `value`, it would be accessed like this:

`pipeline.value`For this reason, the dot character should be avoided when naming variables.

## XPath Queries
Variable source based mappings are limited to reading the unmodified values of variables in the pipeline. For more complex pipeline queries, XPath expressions can be used.

XPath expressions are allowed in XPath sources of mappings and also in all curly brace expressions in parameterised literals.

### Accessing Pipeline Variables
When accessing the pipeline via XPath, each pipeline variable and constant is exposed as an XPath variable. That means that for each pipeline variable `x` there is an XPath variable `$x` providing access to it.

XPath expressions can also be used to access elements within XML typed variables. If a variable named `xml` is assigned the type `text/xml`, the XPath expression $xml refers to the root element of the variable’s XML structure. The standard XPath axes can be used to access other nodes in the XML.

Assuming the variable `xml` contains the following structure:

`&lt;root data="..."&gt;
  &lt;element id="1" /&gt;
  &lt;element id="2"&gt;
    &lt;subElement id="x" /&gt;
  &lt;/element&gt;
&lt;/root&gt;`Then the following XPath expressions could be used to access the XML’s values:

`$xml`

Refers to the document, whose sole child element is the root element.

`$xml/root`

Refers to the root element.

`$xml/root/@attribute`

Refers to the attribute `data` on the root element.

`$xml/root/element[2]/subElement`

Refers to the `subElement` node inside the second `element` node of the root element.

### Functions and Namespaces
In addition to the standard XPath functions, the Process Engine supports a number of additional functions. Like activities, these are provided by modules.

XPath functions may be assigned to different namespaces. For example, the standard Process Engine XPath functions are part of the namespace [http://www.infinica.com/](http://www.infinica.com/). To use these functions, the corresponding namespace has to be configured in the process.

When creating a process definition with Process Designer, the Infinica namespace is automatically assigned to the prefix `infinica`. This documentation assumes that this configuration is in place when referring to elements from the `infinica` namespace.

## Types and Type Conversions
Values stored in the pipeline or provided by sources always have a type. For literals, the type is always `text/plain`. For XPath queries, the type depends on the query.

A variable’s type defines its possible values. For example, string values may contain all printable characters, while numeric values may only contain digits and a few special characters like the comma. An attempt to assign a value to a variable whose type is not compatible with that value will raise an exception.

The available types and conversions depend on the modules included in a Process Engine installation. A list of the standard types defined in the core module of the Process Engine can be found in [Types](/doxee-platform/docs/appendix-b-types).

### Target Types
When mapping one or more sources to a target, the mapping may have a target type. Similarly, when calling a Process Engine XPath function, each parameter also has a target type. If the target type differs from a source value’s type, the value is automatically converted to the target type.

Additionally, each mapping may define a type. This is the so-called intermediate type. As with target types, if the intermediate type differs from the source value’s type, the value is automatically converted to the target type.

In cases where a mapping has a source, intermediate and target type (e.g. when mapping a variable to an activity’s input parameter and also specifying a type on the mapping), the value is converted first to the intermediate type and then to the target type.

### Conversions
Type conversions are used to convert values from one type to another. They can happen automatically when target types involved (see [Target Types](/doxee-platform/docs/6-6-process-engine-user-guide-variables-and-the-pipeline-1#target-types)), or they can be triggered manually by calling the XPath function `infinica:convert()`.

A conversion is only possible if a type conversion has been defined for the two types involved in the conversion, i.e. the source and the target type. The Process Engine defines conversions between most of its standard types, where possible.

If no matching type conversion has been defined, the conversion will fail with an exception. Likewise, if a type conversion exists but fails to convert the provided value to the specified type (e.g. because a string that is supposed to be converted to a number does not actually represent a valid numeric value), an exception is thrown.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}