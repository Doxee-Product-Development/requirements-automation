---
id: "a638dfcb-d5b4-45f6-94cd-c52f66324d74"
title: "log4j"
slug: "6-6-process-engine-manpages-loggers-log4j-1"
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
created_at: "2026-01-07T13:42:08.628Z"
modified_at: "2026-01-07T14:06:50.05Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-loggers-log4j-1"
synced_at: "2026-01-28T20:57:28.396Z"
checksum: "ff2d12119a703ec9"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(log4j, Module: [Log4j Support](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log4j-support-1))

Uses a Log4j logger to write log messages to Log4j appenders.

This logger supports the same configuration patterns and filter levels as the *stream* logger provided by the core module. Additionally, at least one Log4j appender must be configured, using the standard Log4j XML configuration format. For simpler configuration, the appender elements to not have to explicitly specify a namespace; elements from the Infinica process namespace are automatically considered to have no namespace, as expected by Log4j.

Also, for process state and trace logging, the Log4j log level to use when writing messages of these types can be configured (as Log4j uses a log level for each log message, while Doxee does not normally assign a log level to messages of these types).

**Example configuration:**

`&lt;log4j&gt; &lt;diagnostic level="info" pattern="[infinica:{executionId}]
{message}" /&gt; &lt;appenders&gt; &lt;Console name="stdout" target="SYSTEM_OUT"&gt; &lt;PatternLayout&gt; &lt;Pattern&gt;%d{HH:mm:ss} [%p] %m%n&lt;/Pattern&gt; &lt;/PatternLayout&gt;
&lt;/Console&gt; &lt;/appenders&gt; &lt;/log4j&gt; `

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}