---
id: "9a54c8e8-93f8-4185-9354-abb757673958"
title: "Maintenance"
slug: "6-6-process-engine-administration-reference-maintenance"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-04T10:14:46.488Z"
modified_at: "2025-08-20T18:56:06.684Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-maintenance"
synced_at: "2026-01-28T21:01:34.626Z"
checksum: "2ff00b7979d04dd2"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Process engine maintenance refers to actions intended to cleanly shut down the process engine, or to temporarily prevent certain operations (e.g. the instantiation of new processes), without loss of data.

## Maintenance Levels
Maintenance levels are states which can temporarily restrict certain process engine functionalities. A maintenance level can limit the globally configured permissions to specific users or groups and can control the online/offline state of existing and new processes.

Maintenance levels are defined in the process engine configuration. Each level has an ID and defines its own permission restrictions and online settings.

The current maintenance level can be set at any time via the process engine API and applies to the whole process engine. It can also be deactivated, which results in the same behaviour as if a maintenance level without specific settings had been activated.

As long as a maintenance level is active, its permission restrictions are in effect, which may also limit the permission to change the maintenance level to a specific set of users or groups.

If a maintenance level defines an online state, all current processes are set to online or offline, according to this setting, when the maintenance level is activated. Also, while the maintenance level is active, the process engine’s default online state (which defines the online state for newly instantiated processes) is the maintenance level’s online state instead of the globally configured one.

## Shutting Down
When shutting down the process engine (either by terminating the Java Virtual Machine, e.g. by pressing `Ctrl+C` in the command line window, by shutting down Tomcat or by stopping the service if the process engine is running as a system service), the shutdown phase is initiated to try to prepare the engine for a clean shutdown.

The shutdown phase has two possible functions, which can be configured in the process engine configuration:

- Switch to a specific maintenance level

- Wait for all currently running processes to become inactive

If the process engine is set offline during shutdown, or to a maintenance level which sets the processes offline, a long enough delay should ensure that all processes become inactive within a short time. Once this state is reached, the engine can be terminated without leaving any processes in an undefined state, and without data loss. If process persistence has been configured, all processes can be resumed from their current state after restarting the process engine.

Because the Java VM, Tomcat and the Windows service manager may force termination of an application if it does not shut down quickly enough on its own, a timeout for the shutdown phase can be configured if it is set to wait for all processes to become inactive. This timeout should be set as long as possible, but short enough to guarantee that the shutdown phase will be finished before the system force terminates the process engine.

If the timeout is reached before all processes have become inactive, a warning is logged specifying the number of processes that were still active when the engine was shut down. These processes are left in an undefined state and may not have been persisted at their current state of execution. After restarting the process engine, these processes will be reset to their last saved state, which may lead to parts of these processes being executed twice.

Save points can be configured in processes to help protect against repetition of critical steps.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}