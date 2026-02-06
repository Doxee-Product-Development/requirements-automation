---
id: "19f8ae21-214a-4840-a9bd-2aa83d04704e"
title: "Logging"
slug: "6-6-process-engine-process-definition-reference-logging-1"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:05.468Z"
modified_at: "2026-01-07T14:04:42.012Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-logging-1"
synced_at: "2026-01-28T20:54:58.445Z"
checksum: "7118c5d2191dd026"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Of the various types of log messages used by the Process Engine, some are created by specifically including log directives in a process definition.

These are:

- Diagnostic Logging

- Data Logging

- Variable Target Logging

Custom activities, XPath functions and scripts are free to also write to the diagnostic and data log without a specific log directive.

Log message created by a logging directive on a variable target is written to the diagnostic log.

## Log Levels
Both the diagnostic log and the data log assign log levels to their log messages. The available log levels are, in ascending severity order:

- debug

- info

- warn

- error

- fatal

The Process Engine can be configured to only output log messages of a specific minimum level. Any log messages with a lower level are then simply ignored. For more information on configuring logging, please refer to the Administration Reference.

## Diagnostic Logging
Diagnostic logging simply consists of strings written to the log. The format and content of these strings is entirely up to the log directive.

`&lt;log level="..."&gt;...&lt;/log&gt;`**level (1)**

The log level.

*Content*

The log message.

The log message is a parameterised literal. Expressions in the literal are evaluated as XPath queries on the process pipeline at the location where the log directive is defined.

## Data Logging
A data log directive can be used to write specific values to a field in the data log. Each field has a clearly defined type, which defines the format of the written values.

`&lt;dataLog level="..."&gt;
  &lt;data name="..."&gt;...&lt;/data&gt;
&lt;/dataLog&gt;`**logLevel (0..1)**

Log level. 

**data (0..n) **

Data item.

data (0..n)/**name (1)**

Name of the data log field to write the value to.

data (0..n)/***Content***

The value to be written to the data log as an XPath expression.

The XPath expression for each data item is evaluated on the process pipeline at the location where the log directive is defined. The resulting value(s) is converted to the type of the corresponding data log field and written to the log.

## Variable Target Logging
A variable target can be configured to write a message to the diagnostic log by specifying at least its logLevel and logPattern attributes. The log level defines the level of the log message, while the pattern sets its content.

`&lt;variableTarget type="..." logLevel="..." logPattern="..." logConvert="..."&gt;...&lt;/variableTarget&gt;`logLevel (0..1)

Log level.

logPattern (0..1)

Log message pattern.

logConvert (0..1)

XPath expression for converting the mapping value for the log output.

The pattern is a parameterised literal which does *not* support XPath expressions but may use the following predefined parameters:

name

The name of the variable being mapped to.

value

The new value(s) mapped to the variable.

By default, the Process Engine tries to convert non-string values with a simple string conversion. For more complex types, the logConvert parameter may specify an XPath expression which handles the conversion. The expression does not have access to the pipeline, but can read the mapping values via the `$value` variable.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}