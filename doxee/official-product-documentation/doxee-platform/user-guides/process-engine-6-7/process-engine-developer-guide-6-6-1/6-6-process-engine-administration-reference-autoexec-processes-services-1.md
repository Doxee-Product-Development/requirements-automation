---
id: "884d62ce-7495-44a5-9c5e-d398a5a63e8a"
title: "Autoexec Processes & Services"
slug: "6-6-process-engine-administration-reference-autoexec-processes-services-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:06.197Z"
modified_at: "2026-01-07T14:06:10.919Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-autoexec-processes-services-1"
synced_at: "2026-01-28T20:55:06.321Z"
checksum: "c8f561dc713e8002"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Regular processes are instantiated and started through the Process Engine API. However, certain process definitions may be configured for autoexec processes and services, which are handled in a special manner.

## Autoexec Processes
Autoexec processes are started synchronously during Process Engine startup, i.e. the Process Engine waits for each process to finish before proceeding with the next one, and before continuing the startup process. Multiple processes are executed in the order they are defined.

An autoexec process should not perform a lengthy operation and does not have access to the task and waitstate services. A typical use case for autoexec processes is to perform cleanup tasks whenever the Process Engine starts.

## Service Processes
Service processes are processes which may be started by specifying their service ID. In this case, the process is started only if it is not running already, i.e. the Process Engine guarantees that each service process is running exactly once (or not at all).

Like autoexec processes, service processes may be configured to start during Process Engine startup by setting their autostart flag. However, service processes are started asynchronously and are allowed to continue running indefinitely.

If a process persistence storage has been configured and an autostart service process is still running and the Process Engine is shut down, the process continues running normally when the Process Engine is restarted and the service is *not* started anew.

Service processes that are not running can be started via the Process Engine API. Running services are assigned a process execution ID like all standard processes and can be controlled via the regular API operations.

> Note

A process definition that is configured as a service process may still be instantiated manually as a regular process, even multiple times. Only the process instance started via the service ID is protected from being run more than once. The same process definition may also be configured for multiple different services.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}