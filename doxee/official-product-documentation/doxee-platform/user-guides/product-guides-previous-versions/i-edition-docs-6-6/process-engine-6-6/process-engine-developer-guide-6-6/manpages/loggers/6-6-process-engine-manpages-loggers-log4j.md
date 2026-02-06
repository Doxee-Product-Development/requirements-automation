---
id: "b54e2c25-f930-4cdb-b265-16989c5b4acd"
title: "log4j"
slug: "6-6-process-engine-manpages-loggers-log4j"
category: "Loggers"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Loggers"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T16:20:21.128Z"
modified_at: "2025-08-22T17:34:51.705Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-loggers-log4j"
synced_at: "2026-01-28T21:03:49.505Z"
checksum: "8a93116c5ebd28de"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(log4j, Module: [Log4j Support](/doxee-platform/docs/log4j-support))

Uses a Log4j logger to write log messages to Log4j appenders.

This logger supports the same configuration patterns and filter levels as the *stream* logger provided by the core module. Additionally, at least one Log4j appender must be configured, using the standard Log4j XML configuration format. For simpler configuration, the appender elements to not have to explicitly specify a namespace; elements from the Infinica process namespace are automatically considered to have no namespace, as expected by Log4j.

Also, for process state and trace logging, the Log4j log level to use when writing messages of these types can be configured (as Log4j uses a log level for each log message, while Doxee does not normally assign a log level to messages of these types).

**Example configuration:**

`&lt;log4j&gt; &lt;diagnostic level="info" pattern="[infinica:{executionId}]
{message}" /&gt; &lt;appenders&gt; &lt;Console name="stdout" target="SYSTEM_OUT"&gt; &lt;PatternLayout&gt; &lt;Pattern&gt;%d{HH:mm:ss} [%p] %m%n&lt;/Pattern&gt; &lt;/PatternLayout&gt;
&lt;/Console&gt; &lt;/appenders&gt; &lt;/log4j&gt; `

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}