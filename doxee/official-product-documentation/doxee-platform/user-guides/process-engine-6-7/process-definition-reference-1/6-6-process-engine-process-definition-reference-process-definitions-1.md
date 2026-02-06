---
id: "fb1ea9e4-3996-4ae6-9691-18a3fd731aa7"
title: "Process Definitions"
slug: "6-6-process-engine-process-definition-reference-process-definitions-1"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:05.247Z"
modified_at: "2026-01-07T14:04:42.012Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-process-definitions-1"
synced_at: "2026-01-28T20:54:55.737Z"
checksum: "b5196670309722cc"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

A process definition always contains at least a process body, consisting of process components. There are two types of components:

**Process elements**

The nodes in the process graph. Each element carries out a specific task when it is executed.

**Process connections**

The directed edges in the process graph. A connection always leads from one element to another.

Additionally, a process definition may contain any of the following top level elements, collectively called the process header:

- Constants

- Credentials

All of these have the same effect as their counterparts in the global Process Engine configuration, but define their elements only for the specific process definition they are specified in.

## The Process Header
`&lt;process xmlns="http://www.infinica.com/process-engine"
    version="4" connections="...&gt;
  &lt;config&gt;
    ...
  &lt;/config&gt;
  &lt;constants&gt;
    ...
  &lt;/constants&gt;
  &lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
    ...
  &lt;/credentials&gt;
  &lt;!-- Process body --&gt;
  &lt;metadata&gt;
    &lt;data domain="..."&gt;...&lt;/data&gt;
  &lt;/metadata&gt;
&lt;/process&gt;`**version (1)**

Specifies the version of the IPD format used by the process definition. For processes conforming to this reference documentation, this should always be `4`.

**connections (0..1)**

Can be set to `explicit` to disable implicit connections (see [Implicit Connections](/doxee-platform/docs/6-6-process-engine-process-definition-reference-connections-1#implicit-connections)). Defaults to `implicit`.

**config (0..n)**

[Process definition configuration](/doxee-platform/docs/6-6-process-engine-process-definition-reference-process-definitions-1#process-definition-configuration). See Process Definition Configuration.

**constants (0..n)**

Constants.

** credentials (0..n)**

** **Credentials.

**metadata (0..1)**

A metadata section that can be freely used by applications to store their own data associated with the process definition. For example, Process Designer will use this section to store the visual layout of the process diagram.

metadata (0..1)/**data (0..n)**

A single metadata item. Applications are free to add their own items identified by the items' domains. Applications should ignore items with unknown domains. The items' content depends entirely on the applications.

metadata (0..1)/data (0..n)/**domain (1)**

Identifies the type of this data item. An application should use unique domain names to identify their items so as not to conflict with metadata stored by other applications.

The `process` element should also define any namespaces used in the process definition, e.g. by XPath expressions.

### Process Definition Configuration
This section configures the default behaviour of process instances created from the process definition.

`&lt;config&gt;
  &lt;defaultThreadPool&gt;...&lt;/defaultThreadPool&gt; ①
  &lt;defaultLocked&gt;...&lt;/defaultLocked&gt; ②
&lt;/config&gt;``defaultThreadPool` [1] defines the thread pool to which instances of this process definition should be assigned if no thread pool is specified at instantiation time.

The boolean setting `defaultLocked `[2] can be used to lock process instances to the current engine node by default, unless specified differently at instantiation time.

### Credentials
Credentials for when the process accesses an external server that requires authentication, can be configured in a credentials registry.

A global credentials registry can also be defined in the Process Engine configuration. In that case, the credentials configured in the process take precedence over those from the global configuration where applicable. For connections where the credentials are not provided by the process, the global configuration is used.

Additionally, a process may modify its own credentials registry during execution. These changes only apply to the corresponding process instance and do not affect other process instances of the same or different process definitions.

For details on configuring and using a credentials registry, please refer to [Credentials Registry.](/doxee-platform/docs/6-6-process-engine-process-definition-reference-process-definitions-1#credentials)

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}