---
id: "73938e20-58ce-45d5-8c86-88a0170f2a55"
title: "Mappings"
slug: "6-6-process-engine-process-definition-reference-mappings"
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
created_at: "2025-08-06T12:29:52.092Z"
modified_at: "2025-08-20T17:35:20.431Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-mappings"
synced_at: "2026-01-28T21:01:25.851Z"
checksum: "0cc5fa806a88cef6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

A mapping uses sources to collect a list of values which are then written to one or more targets. A mapping always has a source pipeline and a target pipeline. The context in which a mapping is specified defines these pipelines. In some cases, e.g. when specified in a mapping element, a mapping’s source and target pipeline may be one and the same.

`&lt;mapping required="..." condition"..."&gt;
  &lt;!-- Sources --&gt;
  &lt;!-- Targets --&gt;
  &lt;default expression="..."&gt;
    &lt;value&gt;...&lt;/value&gt;
  &lt;/default&gt;
&lt;/mapping&gt;`**required (0..1)**

An optional boolean value that specifies whether the mapping must provide at least one value. If none of the sources of a required mapping provides a value, the mapping raises an exception.

**condition (0..1)**

An optional XPath expression that evaluates to a boolean value. If the value is `false`, the mapping is skipped.

*Sources*** (0..n)**

Any number of sources (see below) for the mapping. A required mapping without sources will always fail.

*Targets*** (1..n)**

A number of targets (see below) for the mapping.

**default (0..1)**

Optional default value(s) for the mapping. If this is specified, at least an expression or at least one value must be present.

code (1)/**expression (0..1)**

An XPath expression which provides default values for the mapping. 

code (1)/**value (0..n)**

Default values for the mapping, in the same format as literal sources.

## Defaults and Required Mappings
Unless specified otherwise, a mapping is considered a *required* mapping. A required mapping will fail if none of its sources provide a value during evaluation.

A mapping can be configured to allow an empty value list by setting its required parameter to `false`. In this case, mapping an empty list of values to a target will simply delete the target.

Alternatively, a mapping can specify default values to be used if none of its sources provided a value. These defaults can be provided either via an XPath expression or as a list of literal values. If both an XPath expression and a list of literals is specified, the expression is evaluated first, and the values are only used if the expression also fails to provide a value.

Specifying default values for a mapping implicitly makes it a non required mapping.

## Sources
A number of different mapping sources is supported. Multiple sources of different types may be used in the same mapping.

A mapping’s sources are always evaluated in the order they are specified. The resulting values of all sources are collected in a single list of values. The values in this list are called the mapping’s values.

### Null Source
A null source never provides a value.

`&lt;nullSource /&gt;`### Literal Source
The value of a literal source is its string content.

`&lt;literalSource&gt;...&lt;/literalSource&gt;`*Content*

Literal.

### Parameterised Literal Source
The value of a parameterised literal source is its content evaluated as a parameterised literal Any expressions contained within the literal are evaluated as XPath queries on the mapping’s source pipeline.

`&lt;parameterizedLiteralSource&gt;...&lt;/parameterizedLiteralSource&gt;`***Content***

Parameterised literal.

### URL Source
A URL source specifies the URL of a file. The content of that file, in string format, is used as the source’s value.

`&lt;urlSource&gt;...&lt;/urlSource&gt;`***Content***

URL.

The URL may contain XPath expressions in curly braces ({}). If present, these expressions will be evaluated to determine the final URL.

### Variable Source
A variable source defines the name of a variable in the source pipeline which provides the source’s values. If the variable does not exist, the source provides no values.

This source has a boolean attribute deleteFromSource which determines whether the variable should be deleted from the source pipeline after the Mapping. The default for the attribute is `false`.

`&lt;variableSource deleteFromSource="..."&gt;...&lt;/variableSource&gt;`*Content*

Variable name.

The variable name may contain XPath expressions in curly braces ({}). If present, these expressions will be evaluated to determine the actual name of the variable.

### XPath Source
An XPath source defines an XPath expression which is evaluated on the source pipeline. The expression’s results are used as the source’s values.

`&lt;xpathSource&gt;...&lt;/xpathSource&gt;`*Content*

XPath expression.

## Targets
### Variable Target
A variable target specifies the name of a variable in the target pipeline. The values collected from the mapping’s sources are written to this variable. If the mapping provided no values and is not required, the variable will be deleted from the target pipeline.

If a type is defined on the target, the variable is written in that type. This implicitly converts all provided source values to the specified type. If any value’s type conversion fails, the mapping raises an exception.

`&lt;variableTarget type="..." logLevel="..." logPattern="..." logConvert="..."&gt;...&lt;/variableTarget&gt;`**type (0..1)**

Target variable type.

**logLevel (0..1)**

Log level.

**logPattern (0..1)**

Log message pattern.

**logConvert (0..1)**

XPath expression for converting the mapping value for the log output.

***Content***

Target variable name.

For information on logging, please see [Variable Target Logging.](/doxee-platform/docs/chapter-6-logging#variable-target-logging)

### Iteration Target
The iteration target is a special variation of the variable target used for executing elements multiple times. It has the same attributes as the variable target.

`&lt;iterationTarget type="..." logLevel="..." logPattern="..."
logConvert="..."&gt;...&lt;/variableTarget&gt;`If an element contains a mapping with an iteration target, the element will be executed once for each of the values the iteration target is set to. For each execution/iteration one of the values is used as a separate variable, in the order which they were provided by the mapping sources. The name and type of this variable is defined in the target the same way as for a normal variable target.

The exact behaviour of an element with an iteration target depends on its type. Below is a list of the different element types (only those which can have mappings) and how they behave when an iteration target is used.

**Start Element of a Process**

If the start element of a process contains a mapping with an iteration target, the whole process between the start and the end element is executed once for each value. As long as there are more values in the list provided by the mapping sources, every time the process reaches an end element, it will jump back to the start element and continue from there. In each iteration the process pipeline contains a variable with a single value and the name and type defined by the iteration target. Other mappings in the start element are applied only once, before the iterations start. Mappings in the end element are only applied once all iterations are done. If the list of values is empty, the whole process will be skipped and set to finished.

**Start Element of a Group**

If the start element of a group contains a mapping with an iteration target, the sub process within the group between the start and the end element is executed once for each value. The behaviour of the sub process is the same as for a normal process. If the list of values is empty, the group will be skipped. A group with a start element containing an iteration target mapping has the same functionality as a loop element and might replace the loop completely in future versions.

**Start Element of a Loop**

An iteration target has the same effect as the combination of the mapping to variable iterate and the element attribute in a loop element. If an iteration target is used, there is no need to have a loop, the same behaviour can also be achieved with a group.

**Mapping Element**

If a mapping element contains one or more mappings with an iteration target, those will be applied first and only once. All the others will be applied once for each resulting iteration afterwards. If there are no values in the list, the element is skipped. Note that each time a mapping is applied, the target is overwritten.

**Activity**

If the input mappings of an activity element contain a mapping with an iteration target, the activity is executed once for each value. The input mappings are only applied once, before the iterations. The output mappings are also only applied once, after all iterations are done. In between, the values of the variables in the local pipeline of the activity are accumulated. This means that when a variable is mapped out of the activity pipeline it contains the values resulting from all iterations. Mappings with iteration targets are not allowed in the output mappings of an activity.

**Wait Element**

Iteration targets behave the same for wait elements as for activities.

**Task Element**

Iteration targets behave the same for task elements as for activities.

**End Element**

Iteration targets are not allowed for end elements. Instantiating the process will fail, if an end element contains a mapping with an iteration target.

It is possible to use more than one mapping with an iteration target within the same element. Doing so will create nested iterations. For example, if the first mapping assigns three values (A,B,C) and the second one assigns three values (1,2,3) to the iteration target, there will be 9 iterations with all possible combinations of the provided values as separate variables (A1,A2,A3,B1,B2,B3,C1,C2,C3).

> Caution

Be careful when using nested iterations. They are less obvious to notice and harder to understand for novices. This can make the process more difficult to read and lead to unexpected behaviours. Wrapping elements in groups with a single iteration target might be more convenient in some cases.

### Keep-Variables
`&lt;keepVariablesTarget/&gt;`A mapping with a Keep-Variables target clears the target pipeline and retains only those variables which are referenced by this mapping. The sources provide the names of variables which should still exist after the mapping has been executed.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}