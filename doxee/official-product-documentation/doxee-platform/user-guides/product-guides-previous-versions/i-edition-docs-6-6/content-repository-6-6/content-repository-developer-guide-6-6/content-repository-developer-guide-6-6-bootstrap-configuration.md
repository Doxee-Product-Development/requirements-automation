---
id: "45282288-20eb-4269-bfe7-2128e48de4dc"
title: "Bootstrap configuration"
slug: "content-repository-developer-guide-6-6-bootstrap-configuration"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
  - "Administration guide"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-04T10:18:50.314Z"
modified_at: "2025-12-05T15:45:45.039Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-bootstrap-configuration"
synced_at: "2026-01-28T21:00:51.956Z"
checksum: "897b9cf7914ca1fa"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

The Content Repository is configured via two configuration files. The `repository.properties` file holds the settings for the Jackrabbit JCR implementation on which the Doxee Content Repository is based, while `icr.xml` contains those settings specific to Doxee. Both files are expected in the `infinica` directory.

> Note

Some elements in the configuration reference additional files and directories. These elements typically use URIs that can be either written as absolute URLs or as paths which are resolved relative to the configuration file.

> Tip

In Content Repository versions up to 5.0, nearly all configuration was stored in `repository.properties`, with only the user store configuration in a separate `useraccess.xml` file. This configuration is now part of the new `icr.xml` file, along with all other Doxee specific settings.

A third configuration file `repository.xml` can be used to provide Jackrabbit specific configuration of the repository storage, e.g. to configure an external database.

> Tip

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or "2w".

## repository.properties
This file provides the configuration for the Jackrabbit JCR component of the server, mainly the location of the repository home directory in the local file system, where the repository keeps an index cache and possibly other data:

`repository.home=/path/to/repository // &lt;1&gt;
repository.config=/path/to/repository/repository.xml // &lt;2&gt;
init.initArchive=default_content.zip // &lt;3&gt;
repository.name=infinica.repository
java.naming.provider.url=http\://www.infinica.com/
jndi.enabled=true``repository.home` [1] points to the repository home directory, i.e. a directory where the Content Repository should keep its local data. This data consists of a cached index, and, depending on the settings in `repository.xml`, additional data like large files or a Derby database, if the repository is not configured to use an external database server.  

If this directory does not exist when starting the Content Repository application, it is automatically created and a new repository is initialised based on the settings provided in the repository configuration files.

`repository.config` [2] points to the name of the Jackrabbit specific configuration file, which is automatically created when a new repository is initialised. It is recommended to make this point to a file named `repository.xml` inside the repository home directory.

`init.initArchive` [3] may be specified and point to a ZIP file which is imported automatically when a new repository is initialised. If the file cannot be found while initialising a repository. the initialisation fails.

The remaining properties in this file are Jackrabbit specific settings and can usually be left at their default values. For more detailed information, please refer to the official Apache Jackrabbit documentation.

## icr.xml
`icr.xml` contains all Doxee specific configuration settings for the Content Repository, including the security configuration:

`&lt;repository xmlns="http://www.infinica.com/repository"&gt;
  &lt;adminName&gt;...&lt;/adminName&gt; &lt;--1--&gt;

  &lt;transactions&gt; &lt;!--2--&gt;
    timeout="30m" /&gt;

  &lt;keyStores xmlns="http://www.infinica.com/keyStores"&gt;  &lt;--3--&gt;
    ...
  &lt;/keyStores&gt;

  &lt;userAccessConfiguration xmlns="http://www.infinica.com/useraccess"&gt;  &lt;--4--&gt;
    ...
  &lt;/userAccessConfiguration&gt;

  &lt;security&gt;
    &lt;authentication xmlns="http://www.infinica.com/auth"&gt;  &lt;!--5--&gt;
      ...
    &lt;/authentication&gt;

    &lt;roles&gt;  &lt;!--6--&gt;
      &lt;role name="admin" loginName="..." /&gt;
      &lt;role name="access" loginName="..." /&gt;
    &lt;/roles&gt;
  &lt;/security&gt;

  &lt;search&gt; &lt;!--7--&gt;
    &lt;index&gt;true&lt;/index&gt;
    &lt;autodetectTypes&gt;true&lt;/autodetectTypes&gt;
    &lt;indexingConfigFile&gt;...&lt;/indexingConfigFile&gt;
    &lt;tikaConfigFile&gt;...&lt;/tikaConfigFile&gt;
    &lt;synonymsFile&gt;...&lt;/synonymsFile&gt;
  &lt;/search&gt;

  &lt;debug&gt; &lt;!--8--&gt;
    &lt;logErrorExceptions&gt;false&lt;/logErrorExceptions&gt;
    &lt;operationIdType&gt;integer&lt;/operationIdType&gt;
  &lt;/debug&gt;

  &lt;performanceLog enabled="false"&gt; &lt;!--9--&gt;
    &lt;logNewEntries&gt;false&lt;/logNewEntries&gt;
  &lt;/performanceLog&gt;

  &lt;server&gt;
    &lt;!-- HTTP probes configuration --&gt; &lt;!--10--&gt;
  &lt;/server&gt;
&lt;/repository&gt;``&lt;adminName&gt;` [1] sets the user name the repository should use if it performs any administrative tasks. This user does not have to exist in the user store.

The `&lt;transactions&gt;` element [2] can be used to configure the `timeout` for transactions. Most repository operation is performed in transactions. If an operation takes longer than the specified timeout, it fails. To allow lengthy operations like searches and ZIP imports/exports to succeed, this value should therefore not be set too small. The default value is 30 minutes.

`&lt;keyStores&gt;` [3] configures key stores to be used if they are required e.g. for authentication. Please refer to [Key stores](/doxee-platform/docs/6-6-process-engine-administration-reference-key-stores) for details on how to configure key stores.

`&lt;userAccessConfiguration&gt;` [4] and `&lt;authentication&gt;` [5] configure the user store that should be used for authentication and user queries and the authentication mechanism used by the repository. These are standard elements used by several Doxee applications. For details on how to configure it, please refer to the separate Security Configuration Guide.

If no authentication is configured in this file, *Basic *authentication is used by default.

### Role Configuration
The `&lt;roles&gt;` [6] element is used to assign principals (user groups or, rarely, individual users) to specific roles. Each `&lt;role&gt;` element has a `roleName` which specifies the role being configured (see below for available roles). The corresponding principal can be set either with a `loginName` or an `id` attribute. Multiple principals can be assigned to the same role by putting their login names or IDs in `&lt;assignment&gt;` child elements:

`&lt;role name="..."&gt;
  &lt;assignment id="..." loginName="..." /&gt;
  ...
&lt;/role&gt;`> Caution

If possible, the roles should be configured via the principals' login names, as those are usually handled by users and are easy to configure. For some user stores, like LDAP, the ID might be a long and not easily readable string, and may also change over time if the user store is reconfigured. Specifying the login name lets the role manager discover the corresponding ID automatically.

With some authentication systems, it may not be possible for Doxee to look up users and groups by their login name without the credentials of an active user. In these cases, dynamically looking up the user IDs would fail, and specifying them directly instead of the login names can solve the problem.

#### Available Roles
The following roles can be configured for the Content Repository:

- `access`: If configured, only users with this role will be able to access the repository. Users outside this group will receive authentication errors when trying to access the repository.

- `admin`: All users with this role are considered administrators and granted full permission on all operations, regardless of any permission restrictions on individual files and folders in the repository.

### Search Index Configuration
`&lt;search&gt;` [7] configures the repository's indexed search feature. If `&lt;index&gt;` is set to `false` (nor not specified), the index is deactivated and WebDAV searches are performed by individually testing all candidate files and folders against the search terms. If `&lt;index&gt;` is `true`, the repository maintains a Lucene index of all its files and folders and uses that for more efficient searching. Also, file content can only be searched if the index is activated.

If `&lt;autodetectTypes&gt;` is `true`, the types of files without a configured content type are determined via their file extensions (e.g. files with names ending in `.txt` will automatically be treated as text files). If type autodetection is disabled, only the files' content type properties are evaluated, and files without a configured content type are not indexed.  

`&lt;indexingConfigFile&gt;` and `&lt;tikaConfigFile&gt;` can be used to specify custom indexing and Tika configurations. Please note that indexing and search will behave incorrectly or fail if these configurations do not match the requirements of the repository's search implementation.

`&lt;synonymsFile&gt;` can be used to provide a properties file containing search synonyms. Relative paths are allowed and are interpreted as relative to the directory containing `icr.xml`. A synonyms file contains lines of key/value pairs of synonym terms separated by the `=` character. Each value way contain multiple terms by separating them with commas `,`). All terms in one line are treated as equal by the search.

An example `synonym.properties` file may look like this:

`color=colour
synonym=equivalent,metonym`### Debug Configuration
The optional `&lt;debug&gt;` element configures settings useful for testing and debugging faulty configurations.

If `&lt;logErrorExceptions&gt;` is set to `true`, all error responses will be written to the Log4j log on the `info` level, including a stack trace of the exception that caused the error response. Otherwise (the default), the responses are logged on `debug` level without a stack trace.

`&lt;operationIdType&gt;` defines how the unique part of an operation ID is constructed. Each request has its own operation ID, which is constructed from the operation method (e.g. PUT or GET) and a unique value. The operation ID is used as the ID of the thread that processes the incoming request, so Log4j output can be configured to include it in the log output. The following types of unique values can be configured (`integer` is the default):

Value

Description

`integer`

An easy to read integer number. Each request gets a number one higher than the previous request. This is unique as long as the repository is not clustered or restarted (after each restart, the counter is reset to 0, and each cluster node uses it own counter).

`uuid`:: 

A hexadecimal UUID string. This is not as easy to read as an integer number, but values are unique even in clustered setups and when restarting the server.

### Performance Log Configuration
The `&lt;performanceLog&gt;` [9] element can be used to activate the performance log by setting `enabled` to `true`. When enabled, the performance log will track performance statistics of all WebDAV method types and WebDAV properties.

The performance log statistics can be queried via WebDAV, and are also written to the standard Log4j log when the repository is shut down. `&lt;logNewEntries&gt;` can be enabled to also write a line to the Log4j log whenever a new performance log entry is created (i.e. when a WebDAV method has been performed or a WebDAV property has been evaluated).

### HTTP Probes Configuration
HTTP probes can be used to monitor the status of the Content Repository by an external application. They are configured in the  `&lt;server&gt;` [10] element:

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

> Tip

For test systems, letting the application select a port automatically can be useful, but for production environments, explicitly specifying ports for every probe is recommended, since the same ports have to be configured in the applications calling the probes as well. Also, specifying a bind address that limits the probes to the internal network can improve security.

#### Startup Probe
The startup probe can be used to test if the application's startup sequence has finished. It returns a negative status code up until the startup sequence is complete and from that point on always returns a positive status code. A startup probe is a synchronous probe and therefore does not have timeout; it always responds immediately.

Until the startup probe is positive, no other probe should be expected to return a positive status code.

#### Liveness Probe
The liveness probe tests whether the application is still *alive *(i.e. not crashed). For the Content Repository, this is determined by testing if the repository still responds to new connections. Since this operation can take a little while, the probe has a configurable timeout, which defaults to 30 seconds.

#### Readiness Probe
The readiness probe tests whether the application is *ready *(i.e. working below maximum capacity and still responding to requests). Since readiness is hard to measure, the Content Repository considers itself ready as long as the number of currently active client requests does not exceed a configurable limit `maxReadinessRequests` [4] in the `&lt;server&gt;` configuration). This limit has no default value; if it is not configured, the readiness probe will always return a positive result. The readiness probe can take a little while to determine its status and therefore has a configurable timeout, which defaults to 30 seconds.

> Tip

The number of maximum requests for the readiness check should be set depending on the maximum number of simultaneous requests handled by the container (e.g. Tomcat). The value for `maxReadinessRequests` should be close to, but never higher, than this value.

#### Accessing Probes
Once the application is started, clients may call the probes via simple HTTP GET requests to the probes' TCP ports. The paths, query parameters, or header fields of these requests do not matter. Once called, the probe will determine its state, and respond with a positive (204) or negative (503) HTTP status code.

## repository.xml
This configuration file is used by Jackrabbit to manage the repository storage. It can be used to configure an external database to  store the repository content.

The `repository.xml` file in the `infinica` directory is *only* used when initialising a new repository. Once a new repository has been created, a copy of this file (with some Doxee specific modifications which are automatically performed during repository creation) will be stored in the repository home directory as defined in `repository.properties`. In this case, any later changes to the file in `infinica` will not have an effect, and will instead have to be made in the repository home directory.

If `repository.xml` is missing in the `infinica` directory when a new repository is created, and internal default configuration is used instead. The `repository.xml` file included in the Content Repository installation bundle is a copy of this default configuration.

For more detailed information on all possible entries in this configuration file, please refer to the official Apache Jackrabbit documentation.

### Configuring Database Storage
The Content Repository always stores its structure and content in a database. If no specific database is configured, a local Derby database is used by default, which stores its contents in files inside the repository home directory.

This behaviour is defined by two persistence managers configured in `repository.xml`, one for the default workspace (containing regular repository content) and one for the version storage. In the default configuration, they both use the same Derby database and only differ in their `schemaObjectPrefix` parameters, which define a name prefix for the tables and other database objects created by the persistence manager.

The default workspace persistence manager configuration looks like this:

`&lt;PersistenceManager class="org.apache.jackrabbit.core.persistence.
                           bundle.DerbyPersistenceManager"&gt;
  &lt;param name="url" value="jdbc:derby:${wsp.home}/db;create=true"/&gt;
  &lt;param name="schemaObjectPrefix" value="${wsp.name}_"/&gt;
&lt;/PersistenceManager&gt;`To use a different database, both persistence manager configurations must be changed accordingly. It is recommended to leave the `schemaObjectPrefix` settings at their default values, to guarantee that both configurations use different names for all their database objects. The remaining parameters can be changed as required for the desired database connection. These settings are typically the same for both persistence managers.

For example, a configuration for an MSSQL database connection may look like this:

`&lt;PersistenceManager class="org.apache.jackrabbit.core.persistence.
                           pool.MSSqlPersistenceManager"&gt;
  &lt;param name="url" value="jdbc:sqlserver://localhost:1433;databaseName=icr"/&gt;
  &lt;param name="schemaObjectPrefix" value="${wsp.name}_"/&gt;
  &lt;param name="user" value="user"/&gt;
  &lt;param name="password" value="password"/&gt;
&lt;/PersistenceManager&gt;`This configuration defines a different persistence manager class to match the new database type, a database URL in the standard format used by the MSSQL JDBC driver, and a user name and password for accessing the database.

Please refer to the official Apache Jackrabbit documentation for a list of the available persistence manager classes and the parameters they support.

### The Virtual File System
The repository stores some global information, including namespace definitions, in a so called *virtual filesystem*. By default, the virtual filesystem is stored locally in the repository directory. Alternatively, the virtual filesystem can be configured to be stored in a database. A template for the database configuration is included in the default `repository.xml`:

`&lt;FileSystem class="org.apache.jackrabbit.core.fs.db.DbFileSystem"&gt;
  &lt;param name="driver" value="DRIVER"/&gt;
  &lt;param name="schema" value="SCHEMA"/&gt;
  &lt;param name="url" value="URL"/&gt;
  &lt;param name="user" value="USER" /&gt;
  &lt;param name="password" value="PASSWORD" /&gt;				
  &lt;param name="schemaObjectPrefix" value="globalfs_"/&gt;
&lt;/FileSystem&gt;`The database driver class, schema (i.e. database type), database URL and user and password have to be filled in depending on the database server. For specific databases, a different filesystem class might be recommended. Please refer to the Jackrabbit documentation for more details.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}