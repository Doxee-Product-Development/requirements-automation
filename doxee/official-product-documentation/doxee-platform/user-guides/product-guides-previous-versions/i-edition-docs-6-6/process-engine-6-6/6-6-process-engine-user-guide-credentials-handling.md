---
id: "0b7e7b2a-ce54-409a-bde8-94012ecdbc96"
title: "Credentials Handling"
slug: "6-6-process-engine-user-guide-credentials-handling"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T17:05:11.966Z"
modified_at: "2025-08-19T14:50:33.762Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-credentials-handling"
synced_at: "2026-01-28T21:01:15.355Z"
checksum: "54411f43cfc1f5ec"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Processes frequently have to access external services which often require authentication. When accessing these services, a process has to provide the matching credentials. By convention, an activity accessing such a service takes the corresponding credentials from the process’s credentials registry.

> Note

Certain activities may choose to handle the credentials in a different way, e.g. by requiring the caller to provide them as input parameters. Such activities should make sure to mention this non standard behaviour in their documentation.

## Configuring Credentials
At runtime, each process has its own credentials registry. The credentials managed by the registry can be provided in several ways:

- In the global Process Engine configuration.

- In the process definition.

- At runtime (e.g. via the `credentials` activity provided by the `core` module).

A credentials registry consists of a list of descriptions for external services with all information required to identify them, and for each of those services a list of credentials which can be used to access them. The available types of credentials depend on the installed authentication modules. The separate Security Configuration Guide contains a detailed overview of all supported credential types.

When authentication has been configured for the Process Engine and a process has been instantiated with credentials, the process can use these credentials to access a service. To do this, the credentials registry needs to specify credentials of the type currentCredentials for the service.

Details about credentials registries and how to define them can be found in the Process Definition Reference and Administration Reference of the Process Engine.

## Current User Credentials
Depending on the `keepCredentials` flag in the Process Engine configuration, a process may keep the credentials it was instantiated with. In this case, these credentials can be used via `currentCredentials` entries in the credentials registry. Depending on the specific setting of `keepCredentials`, the current user’s credentials may be persisted (using encryption) along with the process when it is written to the configured storage, or they may be lost when the process is persisted and later restored. If credentials persistence is deactivated, `currentCredentials` may not always be able to provide credentials.

## Credentials Expiration
Long running processes may face the issue of changing credentials. A user’s credentials (e.g. their password) may change while the process is still running, or a ticket that was created when the process was first started may expire. Process Engine provides two mechanisms for dealing with these situations, depending on whether the credentials are static (i.e. directly specified by a credentials registry) or dynamic (i.e. current user credentials).

### Technical Credentials
*Technical credentials* are static credentials which are stored in a credentials registry and do not depend on the current user. They may be used to access specific services like a database, or for background access to the Task Manager, or access to the Content Repository if the specific process user is not required for authorisation.

If these credentials have a limited lifetime (e.g. token based credentials, where the token expires after a specific timeout interval), storing them directly in a credentials registry will result in the process still trying to use them after they have expired. Furthermore, even if the credentials do not expire themselves, they may be changed in the user store (e.g. a user’s password may be updated for security reasons). If persistence is activated, a process using such credentials might persist them and still try to use an outdated set of credentials even if the configuration is updated and the Process Engine restarted after the credentials have changed.

To prevent these issues, the Process Engine configuration can define a *technical credentials manager*. The credentials manager is configured with a list of credentials, each identified with a unique name. The credentials registry, instead of directly containing these credentials, then simply refers to a set of technical credentials by name. Whenever a process uses credentials that have been configured in this manner, they are retrieved from the credentials manager. This allows the manager to recreated token based credentials before they expire, and to provide the process with updated credentials if the configuration is changed and the server restarted.

The Administration Reference describes how to configure a technical credentials manager.

### Updating User Credentials
For situations where a user’s own credentials are used by a process and may expire while the process is still active, an interactive solution is required to request new credentials from the user. If a Task Manager is available, the Process Engine can be configured to automatically handle authentication errors. Instead of aborting the process when an authentication attempt fails, the Process Engine can instead put the process in a *broken* state and create a system task that prompts the user to provide updated credentials. Once the task has been completed, the process will be resumed, using the updated credentials as its current credentials and reattempting the operation that caused the earlier authentication error.

For more details on configuring this feature, please refer to the sections describing the Task Manager and *error health mapping* configurations in the Administration Reference.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}