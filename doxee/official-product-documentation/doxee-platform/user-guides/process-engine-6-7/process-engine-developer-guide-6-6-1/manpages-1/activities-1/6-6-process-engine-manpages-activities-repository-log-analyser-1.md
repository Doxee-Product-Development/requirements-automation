---
id: "3e4d30c5-fb99-494a-a994-919bda5ce040"
title: "Repository Log Analyser"
slug: "6-6-process-engine-manpages-activities-repository-log-analyser-1"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:16.189Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-repository-log-analyser-1"
synced_at: "2026-01-28T20:56:18.551Z"
checksum: "4015056850c1014b"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(repositoryLogAnalyser, Module:[ Log Analysis](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-log-analysis-1))

Analyses Repository log files. The result contains min, max and average performance numbers aggregated for HTTP methods, resources and status codes.

**Input Parameters:**

- url (x-infinica/url) (0-unbounded) 

The URL(s) of the log file(s).

- logString (text/plain) (0-1) 

Log entries as String.

- outputUrl (x-infinica/url) (0-1)

The URL to which the resulting XML should be written. If this is null, the XML is not written.

- prefix (text/plain) (0-1)

A regular expression which represents the first part of the log line up to the actual message. Can beused for adapting to various log4j patterns.

Default:

.*

- suffix (text/plain) (0-1)

A regular expression which represents the last part of the log line after the actual message. Can be used for adapting to various log4j patterns.

Default:

.*

- limit (x-xsd/integer) (0-1)

The maximum number of log entries which should be included into the result.

Default:

-1

**Output Parameter:**

- xml (text/xml) (0-1)

An XML containing one node per HTTP method which occurred in the logs. Each method node contains child nodes for all the resources this method was used on. If the requests on a certain method and resource resulted in more than one status code, there are child nodes for all the individual status codes on the resource.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}