---
id: "5c02e15f-1707-416c-942d-736f164035b4"
title: "Configuration"
slug: "task-manager-6-6-configuration-1"
category: "Task Manager"
category_path:
  - "Product guides"
  - "Task Manager"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:39:37.34Z"
modified_at: "2026-01-08T08:42:54.287Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/task-manager-6-6-configuration-1"
synced_at: "2026-01-28T20:58:14.056Z"
checksum: "83ecc42de937b322"
---

The task manager configuration is defined in the file `infinica/tasks.xml`:

`&lt;taskManagers xmlns="http://www.infinica.com/tasks"&gt;
  &lt;taskManager&gt;
    &lt;storage&gt; &lt;!--1--&gt;
      ..
    &lt;/storage&gt;
    &lt;keyStores xmlns="http://www.infinica.com/keystores"&gt; &lt;!--2--&gt;
      ...
    &lt;/keyStores&gt;
    &lt;userAccessConfiguration xmlns="http://www.infinica.com/useraccess"&gt; &lt;!--3--&gt;
      ...
    &lt;/userAccessConfiguration&gt;
    &lt;security&gt;
      &lt;authentication xmlns="http://www.infinica.com/auth"&gt; &lt;!--4--&gt;
        ...
      &lt;/authentication&gt;
      &lt;roles&gt; &lt;!--5--&gt;
        &lt;role name="admin" loginName="..." /&gt;
        &lt;role name="contributor" loginName="..." /&gt;
        &lt;role name="manager" loginName="..." /&gt;
        &lt;role name="supervisor" loginName="..." /&gt;
        &lt;role name="watcher" loginName="..." /&gt;
      &lt;/roles&gt;      
    &lt;/security&gt;
    &lt;caseSensitivePrincipals&gt;true&lt;/caseSensitivePrincipals&gt; &lt;!--6--&gt;
    &lt;server&gt;
      &lt;!-- HTTP probes configuration --&gt; &lt;!--7--&gt;
    &lt;/server&gt;
  &lt;/taskManager&gt;
&lt;/taskManagers&gt;`## Storage Configuration
The storage configuration [1] defines where tasks and task payloads are stored. Please refer to Storage configuration for a description of the generic way to configure storage in Doxee applications. The remained of this section will give additional information on specific task manager related settings.

Tasks currently must be stored in an SQL database, while task payloads may be stored in an SQL database or in the filesystem. A simple configuration might look like this:

`&lt;sql xmlns="http://www.infinica.com/storage"
    url="jdbc:..."&gt;
  &lt;sqlTaskStorage /&gt;
  &lt;sqlTaskPayloadStorage /&gt;
&lt;/sql&gt;`Alternatively, a more complex configuration using a filesystem storage for the task payloads may be:

`&lt;sql xmlns="http://www.infinica.com/storage"
    url="jdbc:..."&gt;
  &lt;sqlTaskStorage /&gt;
&lt;/sql&gt;
&lt;filesystem xmlns="http://www.infinica.com/storage"
    baseUri="storage/"&gt;
  &lt;fileTaskPayloadStorage /&gt;
&lt;/filesystem&gt;`The SQL task storage may define addition Hibernate connection properties:

`&lt;sql xmlns="http://www.infinica.com/storage"
    url="jdbc:..."&gt;
  &lt;sqlTaskStorage&gt;
    &lt;properties&gt;
      &lt;prop name="..." value="..." /&gt;
    &lt;/properties&gt;
  &lt;/sqlTaskStorage&gt;
&lt;/sql&gt;`The file task payload storage can define a custom sub directory of the main filesystem storage:

`&lt;filesystem xmlns="http://www.infinica.com/storage"
    baseUri="storage/"&gt;
  &lt;fileTaskPayloadStorage
      uri="taskPayloads/" /&gt;
&lt;/filesystem&gt;`In this case, the payloads would be stored in the directory `storage/taskPayloads`. When using a database storage, Doxee will automatically create the necessary tables (and other database entities) if they do not exist. Alternatively, the databases can be initialised manually be executing the appropriate SQL scripts from the `sql` directory.

> Important

The automatic generation of database entities does not correctly create the necessary sequence for Oracle databases. When using an Oracle database, it is therefore necessary to execute the matching SQL script before starting Task Manager.

### Simplified Configuration with Default Storages
If a required storage is not configured directly, but a matching main storage has been configured, a default configuration for that storage is created automatically.

This means that in most cases, it is enough to configure the main storages and leave the rest to the task manager.

For most scenarios, the following configuration should be sufficient:

`&lt;sql xmlns="http://www.infinica.com/storage"
    url="jdbc:..." /&gt;`In this case, all data will be stored in the SQL database.

## Key Store Configuration
`&lt;keyStores&gt;` [2] configures key stores to be used if they are required e.g. for authentication. Please refer to Key stores for details on how to configure key stores.

## User and Authentication Configuration
`&lt;userAccessConfiguration&gt;` [3] and `&lt;authentication&gt;` [4] configure the user store and authentication mechanism used by the Task Manager. These are standard elements used by several Doxee applications. For details on how to configure them, please refer to the external Security Configuration Guide.

## Role Configuration
The `&lt;roles&gt;` [5] element is used to assign principals (user groups or, rarely, individual users) to specific roles. Each `&lt;role&gt;` element has a `roleName` which specifies the role being configured (see below for available roles). The corresponding principal can be set either with a `loginName` or an `id` attribute. Multiple principals can be assigned to the same role by putting their login names or IDs in `&lt;assignment&gt;` child elements:

`&lt;role name="..."&gt;
  &lt;assignment id="..." loginName="..." /&gt;
  ...
&lt;/role&gt;`> Caution

If possible, the roles should be configured via the principals' login names, as those are usually handled by users and are easy to configure. For some user stores, like LDAP, the ID might be a long and not easily readable string, and may also change over time if the user store is reconfigured. Specifying the login name lets the role manager discover the corresponding ID automatically. With some authentication systems, it may not be possible for Doxee to look up users and groups by their login name without the credentials of an active user. In these cases, dynamically looking up the user IDs would fail, and specifying them directly instead of the login names can solve the problem.

### Available Roles
The following roles can be configured for the Task Manager:

- `admin`: All users with this role are considered administrators and granted full permission on all operations, regardless of any task specific role assignments. The admin role includes all other roles.

- `contributor`: Contributors may register task type providers. This role is usually assigned to technical users, e.g. the user Workplace uses to access the Task Manager.

- `manager`: Managers may carry out technical management tasks which do not require full administrative privileges, including accessing runtime and debug information.

- `supervisor`: Supervisors are allowed to read tasks, their attributes, and payload; change task attributes; and delete tasks. Assigning this role in the configuration makes matching users the supervisor for *all* tasks. Additionally, each task can have a list of supervisor principals which have supervisor privileges for that particular task.

- `viewer`: Viewers are allowed to read all tasks. This does not automatically give them permissions to check out or otherwise modify the tasks, or to read their payloads.

- `watcher`: Users with the watcher role may query all watchers, regardless of their owners. This role is usually assigned to technical users, e.g. Process Engine's task access user.

TIP: Certain privileges depend on a task's state. For example, setting a task's payload and checking in a task are only allowed for the task's owner, i.e. the user who has currently checked out the task. The admin role does not grant these privileges. However, supervisors (and thus also admins) may change the owner of a checked out task to grant these privileges to a specific user, including themselves if necessary.

## Case Sensitivity
Principal names used in tasks are case sensitive by default. `&lt;caseSensitivePrincipals&gt;` [6] can be used to change this behaviour. When set to `false`, task security and task queries will ignore the case of principal names.

> Caution

Case insensitivity can cause problems with other software components. For example, if the user store itself is case sensitive, Task Manager will not be able to resolve the parents (groups) of user if the user name does not have the correct case, regardless of this configuration. It is therefore highly recommended to leave case sensitivity enabled and take care to always preserve the correct case of principal names.

> Important

Microsoft SQL Server databases are always case insensitive and will not perform case sensitive queries even if caseSensitivePrincipals is set to true. For the reasons mentioned above, queries should still be made with the correct case to ensure that user lookup and other operations are performed correctly.

> Note

By default, MySQL databases are case sensitive as well, but the table creation scripts provided with this documentation explicitly create tables with a case sensitive collation.

## HTTP Probes Configuration
HTTP probes can be used to monitor the status of the Task Manager by an external application. They are configured in the `&lt;server&gt;` [7] element:

`&lt;server&gt;
  &lt;probes xmlns="http://www.infinica.com/probes"&gt;
    &lt;startup ... /&gt; &lt;!--1--&gt;
    &lt;liveness ... /&gt; &lt;!--2--&gt;
    &lt;readiness ... /&gt; &lt;!--3--&gt;
  &lt;/probes&gt;
  &lt;maxReadinessRequests&gt;...&lt;/maxReadinessRequests&gt;  &lt;!--4--&gt;
&lt;/server&gt;`The application supports three different types of probes - startup [1], liveness [2], and readiness [3] probes. Each probe's configuration has the same pattern (with `&lt;probe&gt;` being replaced by `&lt;startup&gt;`, `&lt;liveness&gt;`, or `&lt;readiness&gt;`, depending on the probe being configured):

`&lt;probe
  enabled="true" &lt;!--1--&gt;
  port="..." &lt;!--2--&gt;
  bindAddress="0.0.0.0" &lt;!--3--&gt;
  timeout="..." /&gt; &lt;!--4--&gt;`Each probe is disabled by default if not configured at all, but enabled if configured without the `enabled` [1] attribute present.

The probe's port [2] can be omitted, in which case a random available port is chosen automatically and reported in the log. The bind address [3] can be specified to limit the IP address range from which the probe accepts connections (it defaults to `0.0.0.0`, which allows connections from any client).

The probe's timeout [4] is only available for certain probes and defines how long a call to the probe may be delayed until the probe automatically responds with a negative status code. The default timeouts differ depending on the probe being configured (see below).

TIP: For test systems, letting the application select a port automatically can be useful, but for production environments, explicitly specifying ports for every probe is recommended, since the same ports have to be configured in the applications calling the probes as well. Also, specifying a bind address that limits the probes to the internal network can improve security.

### Startup Probe
The startup probe can be used to test if the application's startup sequence has finished. It returns a negative status code up until the startup sequence is complete and from that point on always returns a positive status code. A startup probe is a synchronous probe and therefore does not have timeout; it always responds immediately.

Until the startup probe is positive, no other probe should be expected to return a positive status code.

### Liveness Probe
The liveness probe tests whether the application is still *alive *(i.e. not crashed). For the Task Manager, this is determined by testing if the manager can still connect to the task database. Since this operation can take a little while, the probe has a configurable timeout, which defaults to 30 seconds.

### Readiness Probe
The readiness probe tests whether the application is *ready *(i.e. working below maximum capacity and still responding to requests).

Since readiness is hard to measure, the Task Manager considers itself ready as long as the number of currently active client requests does not exceed a configurable limit `maxReadinessRequests` [4] in the `&lt;server&gt;` configuration). This limit has no default value; if it is not configured, the readiness probe will always return a positive result. The readiness probe can take a little while to determine its status and therefore has a configurable timeout, which defaults to 30 seconds.

> Tip

The number of maximum requests for the readiness check should be set depending on the maximum number of simultaneous requests handled by the container (e.g. Tomcat). The value for maxReadinessRequests should be close to, but never higher, than this value.

### Accessing Probes
Once the application is started, clients may call the probes via simple HTTP GET requests to the probes' TCP ports. The paths, query parameters, or header fields of these requests do not matter. Once called, the probe will determine its state, and respond with a positive (204) or negative (503) HTTP status code.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}