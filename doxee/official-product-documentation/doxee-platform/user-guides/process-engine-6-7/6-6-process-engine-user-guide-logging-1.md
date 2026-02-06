---
id: "b9fd1433-0ccb-4b2a-9127-90832855990a"
title: "Logging"
slug: "6-6-process-engine-user-guide-logging-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.27Z"
modified_at: "2026-01-08T08:59:40.336Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-logging-1"
synced_at: "2026-01-28T20:54:50.391Z"
checksum: "c5eef9898a6e530d"
---

Logging is used to output information about a process at runtime. This can be useful for different reasons:

- Provide debugging information for troubleshooting and fixing defective processes.

- Provide status information for monitoring process execution.

- Collect runtime data to perform metrics and performance measurements.

To enable logging, it must be configured in the Process Engine configuration. Please see the Administration Reference for details.

Logging is achieved through a number of different log types which each have specific tasks. The following log types are available:

**Process State Logging**

Provides basic information about process state changes, e.g. start and end times of process instances.

**Trace Logging**

Provides detailed information about the execution flow throughout the lifetime of a process instance. This is particularly useful for tracking and finding bugs.

**Diagnostic Logging**

Outputs custom text (including values from the pipeline) to provide specific information about the process at runtime.

**Data Logging**

Outputs typed data from the process pipeline that can then be read and aggregated to calculate metrics.

## Log Output
As described in the Administration Reference, log output can be written to text streams (stdout and stderr), text files or a database. When writing to text streams and files, all log output must be formatted as text. This makes reading log messages easy, but complicates automated evaluation of logged data. By contrast, database logging writes all its raw output to database tables, allowing clients to easily query logged data, but without a straightforward way to view the logged output in text format.

Depending on the desired usage scenario, different types of log output may be used, individually or together at the same time.

## Log Levels
Diagnostic and data logging uses log levels to specify the relevance of each log message. The supported log levels are, in increasing order of relevance:

- debug

- info

- warn

- error • fatal

When configuring logging, the minimum log level for each log output channel can be set.

Only messages with a level equal to or higher than the configured log level will be written. For example, setting the log output level to `warn` will output all log messages with the levels `warn`, `error` and `fatal`, but will skip anything with the lower levels debug and info.

## Log Types
Different log types produce different type of log messages, but the following attributes are common to all log messages:

- Process instance ID

- Time stamp describing the date and time at which the log message occurred

### Process State Logging
Process State Logging is rather straightforward. Once enabled, all changes to a process instance’s state from the point of its creation to the change to an end state, is written to the log.

### Trace Logging
The trace log is similar to the process state log, but more low level. When enabled, the following events are logged during process execution:

- enter: When execution enters a process element

- leave: When execution leaves a process element

- take: When execution takes a connection to propagate from one process element to the next

Each log message contains the type of trace event and the ID of the component (element or connection) in question.

### Diagnostic Logging
Diagnostic logging is the most flexible form of logging arbitrary text message during process execution. Similar to logging frameworks in programming languages, log messages are produced by explicitly including log directives in a process definition.

Each log directive defines the desired log level and the actual log message. The log message is a parametrised literal which may contain XPath expressions enclosed in curly braces ({}). When writing the log message, these expressions are resolved against the current pipeline at the point where the log directive is defined.

Diagnostic log directives can be specified at any of the following locations:

- At the beginning and end of a process.

- At the beginning of a start element.

- At the end of an end element.

- At the beginning and end of an activity, a mapping element, a script element, a decision, a wait element or a task element.

- On a decision condition

### Data Logging
Like diagnostic log messages, data log messages are created by explicitly defining data log directives in a process definition. However, unlike the diagnostic log, the data log is meant to collect runtime information data for calculations and metrics rather than to be read directly by a human.

Each data log directive writes one or more values to a data log field. The available data log fields are defined in the Process Engine configuration. Each field has a unique name and a type.

A data log directive specifies the target field and an XPath expression that is evaluated on the current pipeline. The resulting value (or values) is converted to the matching data field type and written to the log.

Data log directives can be specified at any location where a diagnostic log message may be specified.

The output produced by the data log, especially when written to the database, can be queried, filtered and sorted according to process IDs, data field names, types and time stamps to produce metrics both for diagnostic use and for production monitoring. For example, the data log can be used to calculate the total and average number of PDF pages created per day by having the PDF renderer activity log the number of rendered pages to an integer field.

## Message Logging
Message logging is a special type of logging output. It is available through the Process Engine module message-logging. Through message logging all diagnostic, trace, data and process state log messages can be pushed directly to a client during execution. Process Designer makes use of this for tracking the progress of processes and for making the log available directly in the UI for testing purposes. The messages are sent in JSON format.

> Note

Message logging has been implemented partly as a replacement for the in	memory log messages which were provided to the client as part of the execution snapshot in previous versions.

Log messages are published to a broker which any client can subscribe to in order to receive the log messages. This broker can be embedded in the Process Engine or running as a separate external server application. To enable message logging, a broker and a message logger need to be defined in the Process Engine configuration. For details on how to do the configuration please refer to the Administration Reference. How to configure Process Designer for using message logging is described in the Process Designer User Guide.

> Important

Message logging is currently only intended for testing and debugging purposes. It lacks security features such as authentication or encryption, 	meaning that anyone who connects to the broker will get all log messages. Therefore it should only be used in test scenarios, not in productive environments.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}