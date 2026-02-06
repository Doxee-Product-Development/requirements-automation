---
id: "d29173f1-a45f-4413-8181-581c3dca016f"
title: "stream"
slug: "6-6-process-engine-manpages-loggers-stream-1"
category: "Loggers"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Loggers"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:08.793Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-loggers-stream-1"
synced_at: "2026-01-28T20:57:29.378Z"
checksum: "d2c0cdb343a808f6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(stream, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1))

Stream logging can be used to write log output to stdout, stderr or a file:

`&lt;stream stream="stdout" timeFormat="HH:mm:ss"&gt; &lt;-- Configuration for individual log types --&gt; &lt;/stream&gt;`Each stream log has to provide either a `stream` attribute (set to `stdout` or `stderr`) or a `file` attribute referencing an output file to which the log output is written in text format.

The formatting of each type of log can be configured separately. For message formatting, *patterns* are used. A pattern is a string that may contain expressions in curly braces. These expressions are replaced at runtime with data from the log message.

The following expressions are available for all log types:

executionId

The unique ID of the process instance.

user

The login name of the user executing the process (if the user was authenticated by the Process Engine).

date

The log message's date and time.

Individual log types may support additional expressions.

Formatted log messages may include time stamps. The format of these time stamps can be configured with the `timeFormat` attribute. The attribute's value must be a Java SimpleDateFormat string (see[http:// docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html](http://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html)).

**Diagnostic Logging**

`&lt;diagnostic level="info" pattern="[infinica:{executionId}] {date} [{level}]
{message}" /&gt;`For diagnostic log output, the `level` and a `pattern` can be specified. The pattern can use the following expressions:

level

The log message`s level.

message

The log message's text content.

**Logging**

`&lt;data level="debug" pattern="[infinica:{executionId}] {date} [{level}]
{name} = {value}" assignmentPattern="" assignmentGlue="," /&gt;`For data logging output, the `level` and a `pattern` can be specified. The pattern can use the following expressions:

level

The log message's level.

name

The key of the log message's data element. 

value

The key of the log message's data element. 

assignments

Concatenated string of data elements, see below.

By default, if a single data log statement logs multiple elements, each element is written as a separate log message. This can be changed by specifying an `assignmentPattern` and `assignmentGlue`. In this case, each data log element is formatted using the assignment pattern and the resulting strings concatenated into a single string using the assignment glue as a separator. The resulting string is provided in the *assignments* parameter for the main pattern.

**Trace Logging**

`&lt;trace enabled="true" pattern="[infinica:{executionId}] {date} {event}{source}" /&gt;`Trace logging can be enabled or disabled using the boolean `enabled` attribute and formatted with a `pattern`. The pattern can use the following expressions:

event

The type of trace event (`ENTER`, `LEAVE` or `TAKE`).

source

The ID of the process component that triggered the trace log message.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}