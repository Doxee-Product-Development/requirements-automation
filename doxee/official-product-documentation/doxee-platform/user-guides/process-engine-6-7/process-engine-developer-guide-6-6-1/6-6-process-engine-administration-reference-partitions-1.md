---
id: "a79e9da2-07de-40e9-a550-e75305cf09b4"
title: "Partitions"
slug: "6-6-process-engine-administration-reference-partitions-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:06.24Z"
modified_at: "2026-01-07T14:06:10.919Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-partitions-1"
synced_at: "2026-01-28T20:55:06.686Z"
checksum: "60b07ca10eba5c90"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Partitions allow a single Process Engine instance to use different configurations for different processes. Every Process Engine installation has at least one partition: The root partition. Optionally, the root partition (and any other partition) may define additional sub partitions, effectively creating a hierarchy of nested partitions.

Sub partition inherit the configuration settings from their parent and may override some of those settings. This allows partitions to define their own constants, credentials, and process directories.

Each partition is mapped to a specific virtual path. Virtual paths are most commonly used when instantiating processes or otherwise referencing process definitions: The process URL provided by the client consists of the Process Engine’s base URL followed by the virtual path of the process definition.

The root partition’s virtual path is always /, so that the Process Engine’s base URL refers directly to the root partition.

Each sub partition specifies its virtual path relative to its parent partition, so that its full virtual path is determined by the concatenation of the parent partition’s and the partition’s own virtual paths.

## Using Partitions
When calling a Process Engine operation with a virtual path, the corresponding partition will be determined by starting with the root partition and going through all of its defined partitions to see if any of them have a virtual path that corresponds to the beginning of the virtual path provided by the caller. If more than one partition has a matching path, the partition with the longest match is used. The context then switches to that partition, cutting off the partition’s path from the beginning of the provided path and repeating the process with the new partition’s sub partitions until no more matching partitions are found. In the end, this process will have determined the targeted partition and the remaining virtual path within that partition.

By default, a process definition’s physical path will be determined by the partition’s physical path followed by the remaining virtual path. However, the physical path may further differ from the virtual path if the partition defines a separate process directory.

## Defining Partitions
Functionally, each partition represents a separate base path for a Process Engine configuration. The partition configuration defines both the partition’s virtual path and its physical path, i.e. the path to the partition’s physical directory. This directory *must* contain a `process_engine.xml` configuration file, which defines configuration settings specific to that partition. All settings not specified in the partition’s own configuration are derived from its parent partition’s configuration.

Partitions are free to define additional constants and credentials. In all of these cases, the parents' configuration is retained and extended by the partition’s own settings.

A partition may also define its own process directory (relative to the partition’s own physical directory, if a relative path is used), replacing the inherited settings from the parent partition.

Sub partitions may *not* define their own thread pools and persistence and task manager configurations.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}