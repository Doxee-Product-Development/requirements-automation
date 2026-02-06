---
id: "5ed3904a-fa0c-4b36-9432-c2460142339b"
title: "Configuration"
slug: "6-6-process-engine-administration-reference-configuration-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:06.114Z"
modified_at: "2026-01-07T14:06:10.919Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-configuration-1"
synced_at: "2026-01-28T20:55:06.005Z"
checksum: "665bf5832bd2e2d9"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

The Process Engine is configured via the `process_engine.xml` configuration file. For command line and standalone servers of the Process Engine, this file is expected in the Process Engine base directory. The base directory depends on the type of Process Engine being used. The command line and standalone server version uses the current working directory as its base directory unless otherwise specified via a command line option. The web application version uses the current working directory of the application server. For the

Tomcat container running as a system version, this is most commonly the root directory of the Tomcat installation (i.e. the directory containing, among others, the `bin` and `webapps` directories); however, specific installations may be configured differently.

The configuration file is read during startup. If the file is not found, the Process Engine will refuse to start for security reasons.

> Note

Some elements in the configuration reference additional files and directories. These elements typically use URIs that can be either written as absolute URLs or as paths which are resolved relative to the configuration file.

> Tip

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or "2w".

## Structure
The basic structure of the `process_engine.xml` file looks like this:

`&lt;processEngine
	xmlns="http://www.infinica.com/process-engine"&gt;
	&lt;id&gt;{auto}&lt;/id&gt;
	&lt;keyStores
		xmlns="http://www.infinica.com/keystores"&gt;
		&lt;!-- Key store configuration --&gt;
	&lt;/keyStores&gt;
	&lt;userAccessConfiguration
		xmlns="http://www.infinica.com/useraccess"&gt;
		&lt;!-- User access configuration --&gt;
	&lt;/userAccessConfiguration&gt;
	&lt;security&gt;
		&lt;!-- Authentication configuration. Unless this section is configured,
         no authentication will be required. --&gt;
	&lt;/security&gt;
	&lt;server&gt;
		&lt;!-- HTTP probes configuration --&gt;
		&lt;!-- Services to provide when running in server mode --&gt;
	&lt;/server&gt;
	&lt;interface&gt;
		&lt;!-- API settings --&gt;
	&lt;/interface&gt;
	&lt;credentials
		xmlns="http://www.infinica.com/credentials"&gt;
		&lt;!-- Credentials defined here will be used by all processes when opening URL connections. --&gt;
	&lt;/credentials&gt;
	&lt;credentialsConfigs
		xmlns="http://www.infinica.com/credentials"&gt;
		&lt;!-- Credentials configurations --&gt;
	&lt;/credentialsConfigs&gt;
	&lt;technicalCredentials&gt;
		&lt;!-- Technical credentials settings --&gt;
	&lt;/technicalCredentials&gt;
	&lt;!-- Messaging configration. --&gt;
	&lt;messaging ... /&gt;
	&lt;logs&gt;
		&lt;!-- Logging configuration. --&gt;
	&lt;/logs&gt;
	&lt;processes&gt;
		&lt;!-- Configuration for processes --&gt;
	&lt;/processes&gt;
	&lt;watchers&gt;
		&lt;!-- Configuration for process watchers --&gt;
	&lt;/watchers.
  
	&lt;threadPools&gt;
		&lt;!-- Thread pools --&gt;
	&lt;/threadPools&gt;
	&lt;services&gt;
		&lt;!-- Processes configured here can run as services --&gt;
	&lt;/services&gt;
	&lt;autoexec&gt;
		&lt;!-- Processes configured here will be automatically executed when the
         engine starts --&gt;
	&lt;/autoexec&gt;
	&lt;persistence&gt;
		&lt;!-- Persistence configuration --&gt;
	&lt;/persistence&gt;
	&lt;taskManager&gt;
		&lt;!-- Task manager configuration --&gt;
	&lt;/taskManager&gt;
	&lt;errorHandling&gt;
		&lt;!-- Error handling configuration --&gt;
	&lt;/errorHandling&gt;
	&lt;debugging&gt;
		&lt;!-- Debugging configuration --&gt;
	&lt;/debugging&gt;
	&lt;constants&gt;
		&lt;!-- Constants in this section are available to all processes --&gt;
	&lt;/constants&gt;
	&lt;partitions&gt;
		&lt;!-- Additional sub partitions --&gt;
	&lt;/partitions&gt;
	&lt;maintenance&gt;
		&lt;!-- Maintenance levels --&gt;
	&lt;/maintenance&gt;
	&lt;startup&gt;
		&lt;!-- Startup configuration --&gt;
	&lt;/startup&gt;
	&lt;shutdown&gt;
		&lt;!-- Shutdown configuration --&gt;
	&lt;/shutdown&gt;
	&lt;queries&gt;
		&lt;!-- Query configuration --&gt;
	&lt;/queries&gt;
	&lt;scheduler&gt;
		&lt;!-- Scheduler configuration --&gt;
	&lt;/scheduler&gt;
	&lt;caches&gt;
		&lt;!-- Cache configuration --&gt;
	&lt;/caches&gt;
	&lt;janitor&gt;
		&lt;!-- Janitor service configuration --&gt;
	&lt;/janitor&gt;
	&lt;performanceLogs&gt;
		&lt;!-- Performance logging configuration --&gt;
	&lt;/performanceLogs&gt;
	&lt;!-- Compatibility configuration --&gt;
	&lt;compatibility /&gt;
&lt;/processEngine&gt;`> Note

When creating a Process Engine distribution using the bundler tool, a default configuration file will be included in the generated bundle. This file provides the standard default settings but also includes commented out sections that demonstrate the usage of the available configuration settings.

While the configuration file must be available for the Process Engine to start, none of the included settings are mandatory. The `&lt;processEngine&gt;` element may be left empty to use only the default settings.

The individual sections are explained in the following chapters.

> Tip

Timeout values are generally assumed to be in milliseconds if no unit is specified. A unit suffix can be added to specify timeouts in different units, e.g. "10s", "5m", "2h", "1d" or "2w".

## ID
Each Process Engine instance has an ID. A unique ID is recommended, as it can make it easier to differentiate between responses, error messages and log entries from different installations from multiple Process Engine instances.

The value of the ID configuration field is a string pattern which may be a static string or may include any of the following parameters:

**{auto}**

Will be replaced by a combination of host name and ports, or host name and a UUID, or just a UUID, depending on the available information.

**{guid}**

Will be replaced by a randomly generated UUID.

**{host}**

Will be replaced by the system’s host name, if available.

**{port}**

Will be replaced by the Process Engine’s network port, if available.

If not specified, IDs will use `{auto}` as the default pattern.

## Key Store Configuration
`&lt;keyStores&gt;` configures key stores to be used if they are required e.g. for authentication. Please refer to [Key Stores](/doxee-platform/docs/6-6-process-engine-administration-reference-key-stores-1) for details on how to configure key stores.

## User Access
Access to a user store can be configured with the `&lt;userAccessConfiguration&gt;` element:

`&lt;userAccessConfiguration xmlns="http://www.infinica.com/useraccess"&gt;
  &lt;!-- User access configuration --&gt;
&lt;/userAccessConfiguration`This is a standard element used by several Doxee applications. For details on how to configure it, please refer to the separate Security Configuration Guide.

If a user access configuration is provided, the process engine uses the configured user store for authentication (if enabled in the security configuration, see below) and for access to the user store by processes, e.g. when a process uses an activity to perform a user query.

## Security
This section configures authentication and authorization via access roles, and the key store used to encrypt sensitive data.

### Authentication &amp; Access Roles
By default, access to the Process Engine does not require or use authentication. In this mode, users cannot provide access credentials when calling the Process Engine.

Authentication can be enabled using the `&lt;security&gt;` section:

`&lt;security
    enable="true"  ①
    keepCredentials="never"&gt; ②
  
	&lt;authentication
		xmlns="http://www.infinica.com/auth"&gt; ③
    ...

	&lt;/authentication&gt;
	
&lt;roles&gt; ④
		&lt;role id="admins" principalId="engine_users"&gt; ⑤
			&lt;grant privilege="instantiate" /&gt; ⑥
			&lt;grant privilege="execute" /&gt;
		&lt;/role&gt;
	&lt;/roles&gt;
	&lt;audit&gt; ⑦

    ...

  &lt;/audit&gt;
&lt;/security&gt;`The boolean attribute `enable` [1] controls whether authentication is enabled. The default value is `false`. This setting does not apply to the key store also configured in the security section; if a key store is configured, it is always enabled.

`keepCredentials `[2] specifies whether credentials used for authentication may be stored in the process. The following configuration values are available:

**never**

Credentials are only used for authentication and are not stored in the processes. This is the default setting.

**always**

Credentials are stored in the process, even when it is persisted in the storage.

**notPersisted**

Credentials are stored in the process, but not persisted. Thus, if a process is persisted and later reloaded, it will continue execution without user credentials.

If a credentials registry specifies the `&lt;currentCredentials /&gt;` entry for accessing an external service, the process must have stored the current user’s credentials to successfully access the service.

`&lt;authentication&gt;` [3] configures the authentication mechanism used by the Process Engine server. This is a standard element used by several Doxee applications. For details on how to configure it, please refer to the separate Security Configuration Guide.

For more fine grained access control, a `&lt;roles&gt;` element [4] defining a number of roles [5] may be provided. The following predefined roles are available and can be configured by providing a `&lt;role&gt;` element with the matching `id`:

**everyone**

All users who are allowed to access the process engine.

**owners**

Process owners (only applies to operations targeted at specific process instances).

Additional roles can be defined by assigning them to a `principalId` which references a user or a group, and applies to that user or all users in that group.

Each role contains a set of `&lt;grant&gt;` elements [6] which define the privileges granted to the role. If roles are configured, users may only perform operations for which their roles grant them the necessary permissions. The following privileges are available:

**all**

Includes all other privileges.

**breakpoints**

Required to set and modify breakpoints.

**cache**

Required for cache maintenance.

**execute**

Required to continue processes.

**getAttributes**

Required to query the attributes of a process instance.

**info**

Required to retrieve general information of the Process Engine.

**instantiate**

Required to instantiate process definitions from the process base directory.

**instantiateStream**

Required to instantiate process definitions provided by the client via a stream.

**maintenance**

Required to set the maintenance mode.

**processInfo**

Required to retrieve information about a process.

**reload**

Required to reload broken processes.

**setAttributes**

Required to set the attributes of a process instance.

**setConstants**

Required to set the dynamic constants of a process instance.

**setOwner**

Required to modify a processes instance’s owner.

**setPermissions**

Required to modify a processes instance’s permissions.

**systemInfo**

Required to retrieve system specific information of the Process Engine, like information about the configuration.

**validate**

Required to validate process definitions from the process base directory.

**validateStream**

Required to validate process definitions provided by the client via a stream.

**watch**

Required to create and access watchers on a process instance. Also required for `waitForProcess`.

`&lt;audit&gt;` [7] can be used to specify an audit log configuration. Please refer to the Security Configuration Guide for more information.

## HTTP Probes Configuration
HTTP probes can be used to monitor the status of the Process Engine by an external application. They are configured in the &lt;server&gt; element:

`&lt;server&gt;
	&lt;probes
		xmlns:probes="http://www.infinica.com/probes"&gt;
		&lt;probes:startup ... /&gt; ①
		&lt;probes:liveness ... /&gt; ②
		&lt;probes:readiness ... /&gt; ③
	&lt;/probes&gt;
	&lt;maxReadinessRequests&gt;...&lt;/maxReadinessRequests&gt;  ④
&lt;/server&gt;`The application supports three different types of probes - startup [1], liveness [2], and readiness [3] probes. Each probe’s configuration has the same pattern (with `&lt;probe&gt;` being replaced by `&lt;startup&gt;, &lt;liveness&gt;`, or `&lt;readiness&gt;`, depending on the probe being configured):

`&lt;probe
  enabled="true" ①
  port="..." ②
  bindAddress="0.0.0.0" ③
  timeout="..." /&gt; ④`Each probe is disabled by default if not configured at all, but enabled if configured without the `enabled` [1] attribute present.

The probe’s port [2] can be omitted, in which case a random available port is chosen automatically and reported in the log. The bind address [3] can be specified to limit the IP address range from which the probe accepts connections (it defaults to `0.0.0.0`, which allows connections from any client).

The probe’s timeout [4] is only available for certain probes and defines how long a call to the probe may be delayed until the probe automatically responds with a negative status code. The default timeouts differ depending on the probe being configured (see below).

> Tip

For test systems, letting the application select a port automatically can be useful, but for production environments, explicitly specifying ports for every probe is recommended, since the same ports have to be configured in the applications calling the probes as well. Also, specifying a bind address that limits the probes to the internal network can improve security.

### Startup Probe
The startup probe can be used to test if the application’s startup sequence has finished. It returns a negative status code up until the startup sequence is complete and from that point on always returns a positive status code. A startup probe is a synchronous probe and therefore does not have a timeout; it always responds immediately.

Until the startup probe is positive, no other probe should be expected to return a positive status code.

### Liveness Probe
The liveness probe tests whether the application is still *alive* (i.e. not crashed). For the Process Engine, this is determined by testing if the engine’s scheduler still responds to new executions. Since this operation can take a little while, the probe has a configurable timeout, which defaults to 30 seconds.

### Readiness Probe
The readiness probe tests whether the application is *ready* (i.e. working below maximum capacity and still responding to requests). Since readiness is hard to measure, the Process Engine considers itself ready as long as the number of currently active client requests does not exceed a configurable limit (`maxReadinessRequests` [4] in the `&lt;server&gt;` configuration). This limit has no default value; if it is not configured, the readiness probe will always return a positive result. The readiness probe can take a little while to determine its status and therefore has a configurable timeout, which defaults to 30 seconds.

> Tip

The number of maximum requests for the readiness check should be set depending on the maximum number of simultaneous requests handled by the container (e.g. Tomcat). The value for `maxReadinessRequests` should be close to, but never higher, than this value.

### Accessing Probes
Once the application is started, clients may call the probes via simple HTTP GET requests to the probes' TCP ports. The paths, query parameters, or header fields of these requests do not matter. Once called, the probe will determine its state, and respond with a positive (204) or negative (503) HTTP status code.

## Server Configuration
A process engine started in server mode provides a configurable set of services:

`&lt;server
        host="0.0.0.0" ①
        port="8080"&gt; ②
  &lt;ssl&gt;...&lt;/ssl&gt; ③
  &lt;soap name="soap" enabled="true" /&gt; ④
  &lt;rest name="rest" enabled="true" /&gt; ⑤
  &lt;jsp enabled="true" /&gt; ⑥
&lt;/server&gt;`The optional `host` [1] and `port` [2] attribute set the server interface and port for the HTTP service. If no host is specified, the service is bound to all available network interfaces. Similarly, a host value of `0.0.0.0` binds the service to all available IP4 interfaces, whereas any other host name or IP address binds to that specific interface only (for example, `127.0.0.1` will make the service accessible only locally). The default port is 8080.

If the Process Engine should be accessed via HTTPS, the necessary SSL configuration can be specified in the `&lt;ssl&gt;` [3] element (see below).

`&lt;soap&gt;` [4] enables or disables the SOAP web service. The element specifies the name of the service, which is appended to the base URL of the Process Engine, and whether the service should be enabled.

`&lt;rest&gt;` [5] enables or disables the REST web service. The element specifies the name of the service, which is appended to the base URL of the Process Engine, and whether the service should be enabled.

`&lt;jsp&gt;` [6] enables the overview page shown as the start page of the Process Engine.

> Note

If no service is enabled, the Process Engine will refuse to start in server mode.

### SSL Configuration
An HTTPS service can be set up using the SSL configuration element:

`&lt;ssl
    keyStore="..." ①
    keyStorePassword="..." ②
    keyAlias="..." ③
    keyPassword="..." /&gt; ④``keyStore` [1] specifies the path to the Java keystore containing the SSL certificate that should be used. `keyStorePassword` [2] must be set to the password necessary to access this keystore.

If the keystore contains more than one certificate, the alias of the certificate to be used may be specified with `keyAlias` [3].

If the certificate uses a different password than the keystore, that password can be set with `keyPassword` [4]. Note that all certificates in the keystore must use the same password. Java keystores allow different entries to have different passwords, but Java is not able to use such keystores for SSL certicates.

## API Settings
This section configures settings controlling the behaviour of the Process Engine API.

`&lt;interface&gt;
  &lt;maxTimeout&gt;0&lt;/maxTimeout&gt; ①
&lt;/interface&gt;``maxTimeout` [1] can be used to set a maximum timeout for all API calls which include a timeout parameter (e.g. `startProcess` or `waitForProcess`). The maximum timeout will be applied even for calls which specify an endless timeout. This can be useful to prevent clients from receiving a protocol timeout (e.g. an HTTP timeout) if their specified timeout exceeds the properties of the underlying protocol, especially when accessing the Process Engine via the SOAP and REST interfaces.

## Credentials
A credentials registry can be configured to provide credentials for when a process accesses an external server that requires authentication.

`&lt;credentials xmlns="http://www.infinica.com/credentials"&gt;
  ...
&lt;/credentials&gt;`A global credentials registry configured here is valid for all processes. A process may also define its own credentials registry. In that case, the credentials configured in the process take precedence over those from the global configuration where applicable. For connections where the credentials are not provided by the process, the global configuration is used.

Additionally, a process may modify its own credentials registry during execution. These changes only apply to the corresponding process instance and do not affect other process instances of the same or different process definitions.

A credentials configuration registry can also be specified:

`&lt;credentialsConfigs xmlns="http://www.infinica.com/credentials"&gt;
  ...
&lt;/credentialsConfigs&gt;`The configurations listed here will be used by all credentials in the registry that do not specify their own configuration. Additionally, for credentials that have neither their own configuration nor a matching entry in the configurations registry, a configuration will automatically be created from the Process Engine’s authentication configuration if one is available and matches the types of the credentials in question.

For details on configuring and using a credentials registry, please refer to [Credentials Registry](/doxee-platform/docs/6-6-process-engine-administration-reference-credentials-registry-1).

## Technical Credentials
If the process engine should support technical credentials, e.g. in the task manager configuration or in credentials registries (both the global one configured above and those in individual processes), the technical credentials manager must be configured here. Please refer to the separate Security Configuration Guide for more information.

## Logging
If processes should be able to output logging information to a stream, file or database, a logging configuration has to be provided:

`&lt;logs
    processState="true" ①
    trace="false"
    diagnostic="true"
    data="true"
    diagnosticLevel="info"  ②
    dataLevel="info"  ③
    mappingPattern="..."&gt;  ④
    &lt;data&gt;...&lt;/data&gt;  ⑤
    &lt;attributes&gt;...&lt;/attributes&gt;  ⑥
    &lt;!-- Loggers --&gt; ⑦
&lt;/logs&gt;`Any number of loggers [7] can be configured as output targets. The available loggers depend on the installed modules. The core module provides the `stream` log which can be used to write logging output to a file or the standard output streams. For documentation on the specific logger types, please refer to the man pages of the corresponding modules.

The `&lt;logs&gt;` element itself specifies whether process state, diagnostic and trace logging are available globally. `processState`, `trace`, `diagnostic`, and `data` [1] are boolean attributes that can be used to enable or disable the process state, trace, diagnostic, and data logs, respectively. By default, all logs except trace are enabled. `diagnosticLevel` [2] specifies the minimum level of diagnostic log messages that are written. Similarly, `dataLevel` [3] sets the minimum level for data log messages. These attributes can be set to one of the following levels:

- debug

- info

- warning

- error

- fatal

Setting a log to one of these levels means that only messages of the specified level or a more severe level are logged.

By default, trace logging is disabled and diagnostic logging is set to `warn`.

Individual loggers may specify their own log levels. This makes it possible to configured multiple log outputs using different log levels. However, the globally specified diagnostic and trace logging settings take precedence. For example, a stream log set to level info will only receive `info`log messages if the global diagnostic level is also set to `info `(or `debug`).

`mappingPattern` [4] can be used to set the default mapping pattern for loggers that do not specify their own pattern. This pattern will be used when mappings are written to the diagnostic log. The `parameters`name and `value`in curly braces can be used to insert the name of the mapped variable and the value it was assigned.

Additionally, available fields for data logging can be set up in the `&lt;data&gt;` [5] element. Custom log attributes can be configured in `&lt;attributes&gt;` [6]. These settings are described in the following sections.

> Note

Up to version 3, the Process Engine used to read the logging configuration from a separate file called `infinica_engine_logging.xml`. This file is 	no longer used, but if it exists, the Process Engine will issue a warning during startup to notify you that an unused legacy configuration file was found.

> Tip

If you want to keep the logging configuration in a separate file, you can use 	an XInclude directive in the Process Engine configuration. See [XInclude](/doxee-platform/docs/6-6-process-engine-administration-reference-xml-configuration-files-1#a2-xinclude) for more information.

### Common Logger Settings
Although most configuration settings for the loggers [8] depend on the actual logger type, a number of options are shared by most loggers:

`&lt;someLogger ...
    cacheSize="..." ①
    brokenTimeout="..." ②
    failuresLimit="..."&gt; ③
  ...
&lt;/someLogger&gt;``cacheSize` [1] specifies the maximum number of log messages that should be cached before writing them to the log target, to reduce the number of individual output operations. This is especially relevant for logs writing to network resources, such as databases.

`brokenTimeout` [2] defines a time span for which a logger should be considered broken if access to the log target fails. The default for most logs is 10 minutes. Zero means no timeout, i.e. the logger will never be flagged as broken. While a logger is broken, nothing will be written to the log target, but errors about the broken logger will be logged in the application’s own Log4j log (usually on stdout). This can e.g. help compensate for brief database connection outages.

`failuresLimit` defines how many times accessing the log target must fail in a row before the logger is flagged as broken. The default is `1`. A zero value means that the logger will never be flagged as broken.

### Data Logging
When a process writes to the data log, it specifies a key/value pair of a data field. The available keys are defined in the logging configuration and assign a type to each data field which controls how values are formatted in the log.

`&lt;data&gt;
  &lt;field ①
      name="data_int" ②
      type="integer" ③
      allowTransfer="true" /&gt; ④
  &lt;field
      name="data_string"
      type="string"
      allowTransfer="false" /&gt;
  ...
&lt;/data&gt;`Each `&lt;field&gt;` [1] defines a unique `name` [2] and a `type` [3]. The boolean attribute `allowTransfer` [4] can be used to control whether the data field is included in logs passed to Process Engine clients. This allows a configuration to prevent fields containing large amounts of data from being streamed to clients. By default, all fields are transferred.

The following data field types are supported:

- string

- boolean

- integer

- float

### Log Attributes
With every log entry, regardless of the specific data logged by the process, some additional attributes like the process execution ID, the current date and log level, etc. are written to the log. Custom attributes can be defined to extend this set of attributes.

How exactly these attributes are logged depends on the specific logger. For the stream logger, they can be referenced in the patterns used to format the log text lines. For the SQL logger included as a standard module, the each log message type configuration can specify a list of attributes to log along with messages of its type.

`&lt;attributes&gt;
  &lt;attribute ①
      name="my_attribute" ②
      type="integer"&gt; ③
    &lt;!-- XPath expression --&gt; ④
  &lt;/attribute&gt;
  ...
&lt;/data&gt;`Each attribute [2] defines a unique name [2] and a type [3] (the available types are the same as those used by the data log, please see [Data Logging](/doxee-platform/docs/6-6-process-engine-administration-reference-configuration-1#data-logging) above). Additionally, an XPath expression [4] is provided which is evaluated each time the attribute is logged to determine its current value.

## Process Configuration
The `&lt;processes&gt;` section specifies configuration settings related to process definitions:

`&lt;processes
    cache="perUserAccess" ①
    base="processes" ②
    defaultOnline="true" ③
    recovery="auto" ④
    autoDispose="fetch"&gt; ⑤
  &lt;initProcess url="init_process.ipd" /&gt; ⑥

  &lt;credentials&gt; ⑦
    ...

  &lt;/credentials&gt;

  &lt;systemCredentials&gt; ⑧
    ...

  &lt;/systemCredentials&gt;
&lt;/processes&gt;``cache` [1] can be used to enable, disable, and control process definition caching. If caching is enabled, process definitions are read from the disk only once and then cached in memory and reused when the same process definition is instantiated again. In this case, the cache must be cleared (or the Process Engine must be restarted) after modifying a process definition to make the Process Engine aware of the new process definition.

The following options are available:

`none`

Process definitions are not cached.

`shared`

Process definitions are cached once for all users. Once a process definition has been cached, all users have access to the cached definition regardless of whether they are allowed to access the IPD file.

`perUserAccess`

Process definitions are cached once for all users, but every user’s access rights are checked individually and cached as well. This means that users are only permitted access to the cached process definition if during their first access they have read access to the IPD file. These permissions are cached as well, and users who have successfully accessed a process definition will be able to access the cached version even if the file permissions change.

`perUser`

Process definitions are cached per user. Every user can access a process definition only if they have permissions to read the underlying IPD file on first access. If two users see different versions of the same file, they also cache these different versions.

The default cache setting is `perUserAccess`.

> Tip

The default setting `perUserAccess `is fitting for systems where different users may have different access rights on IPD files, but all users see the same files. If different users see different files under the same URL (e.g. because the base URL points to their home directories in the Doxee Content Repository), `perUser `should be used to make sure every user sees their own version of every IPD.

Note that different user permissions only apply when accessing a service with different credentials (e.g. when the processes are stored in the Doxee Content Repository and accessed with the users' own credentials). Local files are always accessed using the credentials of the Process Engine application. If processes are stored in the local file system, a cache setting of `shared` is therefore sufficient (and more efficient). The same holds true if process definitions are stored in the Content Repository but readable by all users (or always accessed with the same technical credentials).

The `base` attribute [2] specifies the location of process definitions. By default, this is the Process Engine’s base directory, but this attribute can be used to store processes in a different sub directory, or even an external directory not related to the base directory.

For example, if the Process Engine configuration is stored in:

`/infinica/process-engine/process_engine.xml`

If a client tries to instantiate the process `my_processes/my_process.ipd`, its default location is:

`/infinica/process-engine/my_processes/my_processes.ipd`

However, with the following configuration:

`&lt;processes base="../processes" /&gt;`The same processes will refer to:

`/infinica/processes/my_processes/my_processes.ipd`

The default online state [3] configures whether newly instantiated processes are automatically set online. This defaults to `true`, but can be set to `false `for new process instances to stay offline until they are manually set online.

> Note

Maintenance levels may override this behaviour. For details, please see [Maintenance Configuration](/doxee-platform/docs/6-6-process-engine-administration-reference-configuration-1#323-maintenance-configuration).

The recovery mode [4] defines what should happen to process instances which are lost (this happens when restoring a process which has been running on an engine which did not shut down in a clean way). The possible values are `auto`and `manual`. When set to `auto`, any process which is lost will be recovered immediately by the Process Engine. In `manual`recovery mode the Process Engine will just ignore lost instances until they are either disposed or recovered manually with a call to the API operation `recoverProcess`. The default value is `auto`.

`autoDispose`[5] can be used to configure when processes are automatically disposed (i.e. deleted from memory and storage). The following options are available:

`never`

Processes are never disposed automatically. `disposeProcess `must be called on all processes to remove them from memory.

`fetch`

Processes are disposed when their state is fetched via the API after they have reached any end state (unless the peek flag has been specified for the fetch operation). This is the default setting.

`endedNotFailed`

Processes are disposed immediately after they have finished successfully or after they have been terminated. Processes that fail and reach the `FAILED `end state are *not *disposed automatically (but are disposed on fetch, see `fetch`).

`endedOrFailed`

Processes are disposed immediately after they reach an end state, even if they have failed.

> Note

This setting can be overwritten for each process by specifying a different auto dispose mode at instantiation time.

> Tip

`endedNotFailed `and `endedOrFailed `can be useful for "fire and forget" scenarios where processes are started by a client but their execution ID is not kept and their state is never checked again.

> Caution

If a client starts a process and then waits for it with a separate `waitForProcess `call, `endedNotFailed `and `endedOrFailed `could cause the process to be disposed before the `waitForProcess `call begins (if the process finishes quickly), causing the wait call to fail because of an unknown execution ID. The same can happen when running multiple `waitForProcess `with timeouts sequentially (e.g. in a group with iteration target) and the process terminates between two calls. The `process `wait state is particularly vulnerable to this, as it starts the process before waiting for it, and then repeatedly loops over wait calls until the process reaches the desired state. It is therefore recommended to not use

`endedNotFailed `or `endedOrFailed `in combination with the `process `wait state or similar scenarios, either by globally configuring a different autoDispose setting, or by specifically setting a different autoDispose setting on the affected processes.

The `processes `element may contain an optional sub element named `initProcess `[6]. If this is specified, it defines a process which is executed during the initialisation phase of all processes (except for the initialisation of the init process itself). The initialisation process is passed the `executionId, processUrl` and `owner `of the process in question as input parameters. Its outputs are added to the newly initialised process’s attributes. This allows an initialisation process to automatically provide custom meta data for all new processes, e.g. for logging or monitoring purposes.

`&lt;credentials&gt;` [7] may be configured to specify the credentials that will be used when loading an IPD file, e.g. during an instantiate operation. If it is not specified, the current user’s credentials will be used:

`&lt;credentials&gt;
  &lt;currentCredentials xmlns="http://www.infinica.com/credentials" /&gt;
&lt;/credentials&gt;`Sometimes, the Process Engine has to load IPD files without a user context, e.g. when loading autostart processes or service processes. `&lt;systemCredentials&gt;` can be used to specify these credentials. If this option is not configured, the regular `&lt;credentials&gt;` will be used. Since those default to using the current credentials, and without a user context no current credentials are available, it may be necessary to configure static technical credentials as system credentials when configuring an IPD base URL that requires authentication.

## Process Watchers
Process watchers are used to monitor the state of processes. To prevent watchers from leaking, unused watchers are automatically disposed after a certain time.

`&lt;watchers
    unusedWatcherTimeout="1d" /&gt; ①``unusedWatcherTimeout `[1] defines the interval after which unused process watchers may be purged by the janitor service.

## Thread Pools
By default, the Process Engine provides a single, unlimited thread pool. The `&lt;threadPools&gt;` [1] element can be used to set up a number of custom partitions instead.

`&lt;threadPools&gt; ①
  &lt;threadPool threads="unbounded" /&gt; ②
  &lt;threadPool id="limited" threads="3" /&gt;
  &lt;threadPool id="unpersisted" threads="unbounded" persists="false" /&gt; ③
&lt;/threadPools&gt;`Each thread pool [2] can have an ID and a maximum number of parallel threads. The value `unbounded` can be used to configure a pool with an unlimited number of threads.

> Tip

Setting the threads attribute to 0 means that a thread pool does not have any threads and will never execute any processes.

There is always one default thread pool, which is the only thread pool without an ID. This thread pool will be used when the process caller does not specifically specify a thread pool ID.

`persists`[3] can be set to `false` to prevent all processes in the corresponding thread pool from being persisted in the storage. This can be useful to define a high performance thread pool for non-interactive short-time processes.

## Service Processes
Process definitions can be configured as service processes. Each service process has an ID and can be started using its service ID, in which case it is guaranteed that the service process runs only once (i.e. it is not started again if it was already running).

`&lt;services
    threadPool="..." ①
    autoDispose="..."&gt; ②
  &lt;service id="myService" autostart="true"&gt; ③
    &lt;description&gt;My demo service&lt;/description&gt; ④
    &lt;process url="my_service.ipd"&gt; ⑤
      &lt;param name="param1"&gt; ⑥
        &lt;value&gt;myValue&lt;/value&gt; ⑦
      &lt;/param&gt;
    &lt;/process&gt;
  &lt;/service&gt;
&lt;/services&gt;`The `threadPool `attribute [1] can be used to specify the thread pool that should be used to execute services. If none is configured, the default thread pool is used.

`autoDispose `[2] defines the auto dispose behaviour of service processes.

A `service`[3] must have a unique ID. The `autostart`parameter defaults to `false`if omitted. An optional `description`[4] for display in status and management interfaces may be specified.

Each service defines exactly one `process`[5] via its `url`. Input parameters [6] may be specified depending on the process definition. Each parameter may have one or more values[7].

Please refer to [Service Processes](/doxee-platform/docs/6-6-process-engine-administration-reference-autoexec-processes-services-1#42-service-processes) for details.

> Note

Unlike regular processes, service process definitions may be loaded from outside the configured processes directory, e.g. by specifiying a URL that begins with ".." to step outside the process directory, or by use of an absolute URL like "file://…" or "http://…".

This also allows service processes to be loaded from the local disk even when the standard process directory points to the Doxee Content Repository, which may not yet be available at the time when service processes are started.

## Autoexec Processes
Whenever the Process Engine starts (including when the web application container hosting it is restarted), all configured autoexec processes are started before the Process Engine accepts new requests.

`&lt;autoexec&gt;
  &lt;process url="autoexec.ipd"&gt; ①
    &lt;param name="param1"&gt; ②
      &lt;value&gt;myValue&lt;/value&gt;
    &lt;/param&gt;
  &lt;/process&gt;
&lt;/autoexec&gt;`Each `&lt;process&gt;` [1] in the `&lt;autoexec&gt;` section defines a single process via its url. Like services, autoexec processes can be configured with input parameters [2].

Please refer to [Autoexec Processes](/doxee-platform/docs/6-6-process-engine-administration-reference-autoexec-processes-services-1#41-autoexec-processes) for details.

> Note

Like service processes, autoexec process definitions may be loaded from outside the configured processes directory, e.g. by specifiying a URL that begins with ".." to step outside the process directory, or by use of an absolute URL like "file://…" or "http://…".

This also allows autoexec processes to be loaded from the local disk even when the standard process directory points to the Doxee Content Repository, which may not yet be available at the time when autoexec processes are started.

## Persistence Configuration
The `&lt;persistence&gt;` element configures where the Process Engine stores persisted processes:

`&lt;persistence&gt;
  &lt;storage&gt; ①
    &lt;!-- ... --&gt;
  &lt;/storage&gt;

  &lt;setOnlineAfterRestore&gt;true&lt;/setOnlineAfterRestore&gt; ②
  &lt;credentialsErrorHandling&gt;health&lt;/credentialsErrorHandling&gt; ③
  &lt;defaultLockTimeout&gt;1m&lt;/defaultLockTimeout&gt; &lt;!---4--&gt;
  &lt;validateInstances&gt;false&lt;/validateInstances&gt; ⑤
  &lt;validateWaitStates&gt;false&lt;/validateWaitStates&gt; ⑥
&lt;/persistence&gt;``&lt;storage&gt;` [1] defines the storage type and configuration to be used (see below).

`setOnlineAfterRestore `[2] controls whether all existing processes should automatically be set online after starting the Process Engine. If this is set to `false`, processes will stay offline and will have to be set online manually to continue their execution. The default setting is true.

`credentialsErrorHandling `[3] controls how the Process Engine deals with errors that happen when reading previously persisted credentials. These errors can occur after upgrading if credentials were not migrated correctly. The following values are supported:

`log`

A warning is written to the log file and the lost credentials are discarded. The process will continue as if no credentials had been persisted in the first place.

`health`

The process’s health will be changed to `BROKEN `with an exception type of `persistence.credentials`. The process will be taken offline and will not be resumed until the error is resolved.

`fail`

The process will be terminated with a `FAILED`state.

The default setting is `health`.

> Note

When using the `health`settings, broken processes can be resumed by first calling the API endpoint `updateCredentials`to provide new credentials for the process, followed by `recoverProcess`to reset its health. The process must also be set online before it will resume (this can be done with a parameter for `recoverProcess`).

If system tasks are enabled (see below), the Process Engine will automatically create a credentials task for each broken process. Committing this task will update the process’s credentials, recover it, and set it online. The previously mentioned API endpoints do not have to be called manually in this case.

`&lt;defaultLockTimeout&gt;` [4] configures the default timeout for internal locks. Locks are used to prevent concurrent unsafe access to Process Engine resources (e.g. process instances). If an operation requires a lock an has to wait for it for longer than the specified timeout, it will fail. The default timeout is 1 minute.

If `&lt;validateInstances&gt;` [5] or `&lt;validateWaitStates&gt;` [6] are set to `true`, validations will be performed on all existing process instances or wait states, respectively, during Process Engine startup. By default, validations are disabled. It is recommended to temporarily enable these options after migrating to a new version of Process Engine. Once the Process Engine has started successfully, the validation options can be disabled again.

### Storage Configuration
As the Process Engine consists of a range of sub systems, several storages are used when persistence is enabled. The following storage types are used:

- Process Storage

- Wait State Storage

Please refer to [Storage Configuration](/doxee-platform/docs/6-6-process-engine-administration-reference-storage-configuration-1) for a description of the generic way to configure storage in Doxee applications. The remainder of this section will give additional information on specific Process Engine related settings.

#### Process Storage
A process can be stored in the filesystem, in an SQL database or in a Mongo database. 

**Filesystem**

`&lt;filesystem xmlns="http://www.infinica.com/storage" ...&gt;
  &lt;fileProcessStorage
      uri="" ①
      instancesDir="instances/" ②
      executorsDir="executors/" ③
      cache="true" ④
      discardCorruptPersistenceStorage="false" /&gt; ⑤
&lt;/filesystem&gt;``uri `[1] may refer to a common base directory for the process storage within the configured filesystem directory. `instancesDir `[2] and `executorsDir `[3] specify individual sub directories for process instances and process executors, which store the runtime data of processes. `cache `[4] configures whether the storage is allowed to cache some information in memory.

By default, if restoring a persisted process fails because of broken files in the persistence directory (e.g. because of a system outage while data was written to the process storage), the Process Engine will output an error and refuse to start. This behaviour can be changed by setting `discardCorruptPersistenceStorage `[5] to `true`. In this case, each broken process’s state will be set to `CORRUPTED `and the Process Engine will start normally.

> Important

This setting should only be activated if the Process Engine’s log files are 	routinely and reliably checked to make sure that no previously running processes are lost.

**Databases**

`&lt;sql xmlns="http://www.infinica.com/storage" ...&gt;
  &lt;sqlProcessStorage&gt;
    &lt;properties&gt;...&lt;/properties&gt; ①
  &lt;/sqlProcessStorage&gt;
&lt;/sql&gt;````
&lt;mongo xmlns="http://www.infinica.com/storage" ...&gt;
  &lt;mongoProcessStorage&gt;
    &lt;properties&gt;...&lt;/properties&gt; ①
  &lt;/mongoProcessStorage&gt;
&lt;/mongo&gt;
```For both SQL and Mongo storages, additional database `properties`[1] may be configured.

#### Wait State Storage
Wait states can be stored in the file system or in an SQL database.

`&lt;filesystem xmlns="http://www.infinica.com/storage" ...&gt;
  &lt;fileWaitStateStorage
      uri="" /&gt; ①
&lt;/filesystem&gt;````
&lt;sql xmlns="http://www.infinica.com/storage" ...&gt;
  &lt;sqlWaitStateStorage&gt;
    &lt;properties&gt;...&lt;/properties&gt; ②
  &lt;/sqlWaitStateStorage&gt;
&lt;/sql&gt;
````uri` [1] may refer to a sub directory for the wait state storage within the configured filesystem directory. For the SQL storage, additional database `properties` [2] may be configured.

#### Simplified Configuration with Default Storages
If the Process Engine requires a storage that is not configured directly, but for which a matching main storage has been configured, a default configuration for that storage is created automatically.

This means that in most cases, it is enough to configure one or more main storages (e.g. a filesystem storage or an SQL storage) and leave the rest to the Process Engine.

For many simple scenarios, the following configuration may be sufficient:

`&lt;filesystem xmlns="http://www.infinica.com/storage"
  base="storage/" /&gt;`In this case, all required storages will be configured as filesystem storages in the `storage `directory.

Note that this configuration will not suffice if an internal task manager has been configured, as tasks can currently only be stored in an SQL database. To store all data in a single SQL database, a setup like this will work:

`&lt;sql xmlns="http://www.infinica.com/storage"
  url="..." /&gt;`## Task Manager Configuration
For processes to be able to handle tasks, a Task Manager must be installed. A Process Engine is conncted to a Task Manager by adding some settings to the configuration.

> Important

If no task manager is configured, processes will fail when trying to create or access a task.

`&lt;taskManager&gt;
  &lt;webserviceUrl&gt;http://localhost/infinica-tasks-manager/rest/&lt;/webserviceUrl&gt; ①
  &lt;credentials&gt;...&lt;/credentials&gt; ②
  &lt;watcherOwner&gt;...&lt;/watcherOwner&gt; ③
  &lt;watcherInterval&gt;...&lt;/watcherInterval&gt; ④
  &lt;watcherErrorDelay&gt;...&lt;/watcherErrorDelay&gt; ⑤
  &lt;keys:privateKey alias="..." /&gt; ⑥
  &lt;keys:publicKey alias="..." /&gt; ⑦
  &lt;systemTasks&gt;...&lt;/systemTasks&gt; ⑧
&lt;/taskManager&gt;`The `&lt;webserviceUrl&gt;` [1] element must specify the REST endpoint URL of the task manager.

Processes have to provide their own credentials when creating tasks or otherwise accessing task manager, but for all task operations not performed by a specific process (e.g. when checking for task updates while the associated processes are asleep and waiting to be woken up by their tasks), technical credentials [2] have to be provided in the configuration.

> Tip

Any supported type of credentials can be specified here, but it is highly recommended to configure a technical credentials manager and to use `&lt;technicalCredentials&gt;`, as this makes it easier to update credentials when they change and allows Doxee to make sure tokens are up to date if token-based credentials are used.

The `watcherOwner `[3] may specify the name of a user or group that is set as the owner of any task watchers created by the process engine.

> Tip

It is recommended to set `watcherOwner `to the name of the user whose credentials are configured for task access, or to the name of a group containing that user. This ensures that the configured credentials can access all watchers created by the process engine. If a different (or no) owner is configured, the specified credentials must match a user with the global watcher role in the task manager, or any calls the process engine makes to check for task updates will fail.

`watcherInterval `[4] and `watcherErrorDelay`[5] configure the watcher calls made by the Process Engine to the Task Manager. As long as tasks are active, Process Engine keep querying for watcher updates via the Task Manager’s `stream`endpoint. The interval defines the duration for one individual call to this endpoint. After the specified interval, the call times out, and a new call is started. If the call receives an error (e.g. because the server is not available, or the configured credentials are incorrect, the Process Engine waits for the configured error delay until trying again. The watcher interval defaults to 2 minutes, the error delay defaults to 10 seconds.

> Tip

The interval is intended to prevent timeouts caused by HTTP GET requests 	that are kept open for too long. If you experience connection problems with the watcher calls, reducing the watcher interval may be a way to solve them.

A private [6] and a public [7] key have to be configured if the process engine should be able to create tasks that store the credentials of the user who checks them in. They are specified as key references to a configured key store (see [Key Stores](/doxee-platform/docs/6-6-process-engine-administration-reference-key-stores-1)), e.g.:

`&lt;keys:privateKey alias="tasks" /&gt;
&lt;keys:publicKey alias="tasks" /&gt;`> Note

If no keys are configured, attempts to create tasks that store credentials will fail.

### System Tasks
*System tasks* are management tasks automatically created and handled by the process engine. Currently, system tasks can be used together with *error health mapping* (see [Error Handling Configuration](/doxee-platform/docs/6-6-process-engine-administration-reference-configuration-1#error-handling-configuration)) to automatically create a task for each process that runs into an authentication exception. Once a user checks in such a task, their credentials will be stored, and the process will be resumed with those credentials.

> Note

For credentials tasks to work, keys have to be configured in the task manager configuration. Additionally,  *error health mapping* has to be activated in the error handling configuration (see below). Otherwise, unhandled authentication errors will cause their process to fail like any other type of exception.

`&lt;systemTasks
    watcherTimeout="30s"&gt; ①
  &lt;clientId&gt;process-engine.system&lt;/clientId&gt; ②
  &lt;supervisor&gt;...&lt;/supervisor&gt; ③
  &lt;credentialsTasks enabled=""&gt; ④
    &lt;exceptions&gt; ⑤
      &lt;exception type="..." /&gt;
      ...
    &lt;/exceptions&gt;
  &lt;/credentialsTasks&gt;
&lt;/systemTasks&gt;`System tasks are monitored by watcher requests to the task manager. The timeout for these watcher requests can be configured with the `watcherTimeout `[1] attribute and defaults to 30 seconds.

The client ID used to create watchers for system tasks can be configured with a `&lt;clientId&gt;` [2]. The placeholder `{id}` can be used to insert the process engine’s ID in the pattern. The client ID defaults to `process-engine.system`.

> Tip

The client ID should not be changed while the task manager has active watchers for the process engine, as the process engine will not be able to access the old watchers with the new ID. Care should be taken with the `{id}` parameter if the configured process engine ID is not static.

If a `&lt;supervisor&gt;` [3] is specified, it will be used as the supervisor for all system tasks created by the process engine. Setting this to the user (or a group containing the user) matching the task manager credentials ensures that the process engine will be able to access the system tasks.

> Tip

If no supervisor is specified, the task manager user should have the global supervisor role assigned in the task manager.

`&lt;credentialsTasks&gt;` [4] configures the tasks used to request updated credentials for processes with authentication problems. This is the only type of system tasks currently supported. To use them, the `enabled` attribute must be set to true. `&lt;exceptions&gt;` [5] can be used to customise the process exception types that should be handled by credentials tasks. System tasks will automatically be created for all broken processes with one of the specified types of exceptions. If not specified, all standard authentication exceptions are handled.

## Error Handling Configuration
By default, any exception that occurs while executing a process and is not caught by exception handlers defined in the process causes the process to fail, i.e. end execution with the state `FAILED`. This section can be used to configure the exception handling.

`&lt;errorHandling
    errorHealthMapping="false" /&gt; ①`If `errorHealthMapping `[1] is set to `true`, exception types that define a health state will not cause a process to fail. Instead, the process state will be set to `BROKEN`, and its health state to the health state specified by the exception. This allows users to resolve the issue that caused the problem and to resume process execution from the point where the exception occured.

## Debugging Configuration
This section can be used to enable Process Engine features that may be useful during debugging but are not recommended for production environments.

`&lt;debugging&gt;
  &lt;provideSecretVariables&gt;true&lt;/provideSecretVariables&gt; ①
  &lt;showFullProcessPath&gt;true&lt;/showFullProcesPath&gt; ②
  &lt;performanceLogLevel&gt;trace&lt;performanceLogLevel&gt; ③
  &lt;debugAllProcesses&gt;false&lt;/debugAllProcesses&gt; ④
&lt;/debugging&gt;``&lt;provideSecretVariables&gt;` [1] can be set to `true`to allow the Process Engine to return values of secret data types (e.g. `x-infinica/secret-text`, which is typically used to keep passwords in a process pipeline) to the caller. Without this option, these values are never shown to Process Engine clients.

> Note

A process may of course map a secret value to a non-secret type, e.g. `text/plain`. In this case, the new variable will be visible to clients regardless of this setting.

Normally, Process Engine error messages will only contain the relative path to process definitions, as specified by the client when instantiating the process. This prevents clients from seeing potentially sensitive details of the server configuration. If `&lt;showFullProcesPath&gt;` [2] is set to `true`, the full paths to process definitions will be reported, which can be useful to solve configuration issues where process definitions are not looked up correctly.

Some operations will write performance data to the Log4j log. This can help to trace down performance bottlenecks. &lt;performanceLogLevel&gt; [3] defines the log level with which these messages are logged. The default is `trace`.

 `&lt;debugAllProcesses&gt;` [4] can be used to enable debug mode for all processes, even if the debug flag was not specified at instantiation time.

## Constants
Constants defined here have the same structure as constants defined in processes, but are valid for all processes. When a process is started, all globally defined constants are carried over the new process instance’s constants.

Details on defining constants can be found in the Process Definition Reference.

## Partitions
The `&lt;partitions&gt;` element can be used to configure a list of sub partitions. Each partition references a directory that has to contain the partition’s files. A partition’s configuration file may in turn define additional sub partitions.

`&lt;partitions&gt;
  &lt;partition path="partition_a" baseUrl="partition_a" /&gt;
  &lt;partition path="partition_b" baseUrl="partition_b" /&gt;
&lt;/partitions&gt;`Each partition has a path and a base URL. The path defines the virtual path of the partition within the current partition. The base URL defines the location of the partition’s base directory, which must contain at least a `process_engine.xml` configuration file.

## Maintenance Configuration
Maintenance levels can be configured to temporarily restrict the process engine’s functionality. For more details, please see [Maintenance Levels](/doxee-platform/docs/6-6-process-engine-administration-reference-maintenance-1#maintenance-levels).

`&lt;maintenance&gt;
  &lt;maintenanceLevel id="shutdown"&gt; ①
    &lt;label&gt;Shutdown&lt;/label&gt; ②
    &lt;online&gt;allOffline&lt;/online&gt; ③
    &lt;restriction privilege="instantiate,execute"&gt; ④
      &lt;role id="admins" /&gt; ⑤
    &lt;/restriction&gt;
  &lt;/maintenanceLevel&gt;
&lt;/maintenance&gt;`Each maintenance level [1] has a unique ID. The label [2] is used to display the level in status and administration interfaces.

`online`[3] specifies if the online state of new and existing processes should be affected by the maintenance level:

- noChange

- allOffline

- allOnline

A number of restrictions [4] may be defined to restrict certain privileges to a specified set of role. Each restriction defines the affected privilege (multiple privileges may be separated by commas). Each role which should still be granted the privilege is specified by its own `role`element [5].

## Startup Configuration
The startup configuration can define a list of probers that will be run before the Process Engine finishes its startup phase.

`&lt;startup&gt;
    &lt;probers&gt; ①
        &lt;http name="..."  url="..." pollInterval="5s" timeout="60s" failOnTimeout="true"&gt; ②
            &lt;statusCode&gt;200&lt;/statusCode&gt;
        &lt;/http&gt;
        &lt;process name="..."  processUrl="..." timeout="60s" failOnTimeout="true" /&gt; ③
    &lt;/probers&gt;
&lt;/startup&gt;`Each prober waits for a specific service or situation to become available before startup can continue. Probers can test HTTP probes or custom situations via processes.

Probers are run in sequence, during the warmup phase, and before the process instantiation service.

### HTTP Probers
A HTTP prober [2] waits for a specific HTTP probe to return a positive result. A prober specifies a name and the URL of the HTTP probe. The probe will be repeatedly called with the specified poll interval, until either one of the specified status codes is returned or the configured timeout is reached. If the probe was not successful when the timeout is reached, the `failOnTimeout `parameter determines the behaviour: If it is `true`(the default), the prober fails and the Process Engine’s startup phase will stop with an error. Otherwise, the startup phase will continue.

## Process Probers
A process prober [3] executes a process that implements the actual probing behaviour. The prober name and process URL can be configured. Once the process returns successfully, the startup phase continues. If the process fails, the startup phase will stop with an error. The timeout parameters specifies how long the startup phase will wait for the process to finish. If the timeout is reached, the `failOnTimeout`parameter determines the behaviour: If it is true (the default), the prober fails and the Process Engine’s startup phase will stop with an error. Otherwise, the startup phase will continue.

## Shutdown Configuration
The shutdown configuration configures what happens during the shutdown phase, which is triggered when the Java VM, servlet container or system service running the Process Engine stops.

`&lt;shutdown
    maintenanceLevel="shutdown" ①
    timeout="30s" ②
    hardTimeout="30s" /&gt; ③`The shutdown configuration may define a maintenance level to activate during the shutdown phase [1]. A timeout [2] can be specified, in which case the shutdown phase will wait, up to the specified timeout, for all currently running processes to become inactive. An additional hard timeout [3] controls the extra duration to wait for processes that are forcefully interrupted if they are still active after the regular timeout. If no timeouts are specified, the shutdown phase will not wait for processes.

If no shutdown configuration is specified, the default configuration is:

`&lt;shutdown timeout="30s" hardTimeout="30s" /&gt;`For details, please see [Shutting Down](/doxee-platform/docs/6-6-process-engine-administration-reference-maintenance-1#shutting-down).

## Query Configuration
The query configuration defines the limits for queries executed through the Process Engine API, with the intention of preventing malicious queries from destabilising the Process Engine.

`&lt;queries&gt;
  &lt;executionIds defaultLimit="1000" maxLimit="10000" /&gt; ①
  &lt;executionSnapshots defaultLimit="100" maxLimit="1000" /&gt; ②
&lt;/queries&gt;``&lt;executionIds&gt;` [1] defines the limits for queries returning only the IDs of the queried executions. `&lt;executionSnapshots&gt;` [2] defines the limits for queries returning full execution snapshots. In both cases, a default limit and a maximum limit can be configured. The default limit is used whenever a query does not specify its own limit. The maximum limit is enforced regardless of whether a query’s limit is taken from the query or from the configured default.

The above values represent the default values.

## Scheduler Configuration
The scheduler configuration controls the behaviour of the process scheduler.

`&lt;scheduler
    guardInterval="5m" ①
    pageSize="100" /&gt; ②`The scheduler can attempt to schedule all `READY`processes in regular intervals, to compensate for potential situations where a process was not scheduled correctly when it was supposed to. This interval can be configured with the `guardInterval`attribute [1]. `none`can be specified to disable this feature. The default interval is 5 minutes.

`pageSize`[2] defines the maximum number of processes that can be handled in a single scheduler cycle. If more than the specified number of processes are ready for scheduling, and the necessary resources are available, the remaining processes will be considered in the following cycles. The default page size is 100.

### NOTE
As the scheduling order of processes it currently not defined, it is not guaranteed that the remaining processes from a previous cycle will be scheduled before any newly instantiated processes. If the number of pending processes is significantly larger than the available resources, and new processes are instantiated quickly, this can lead to *starvation* if new processes are scheduled early and older processes are never reached. Increasing the page size may help in this situation.

## Cache Configuration
The Process Engine uses various caches. Each cache can be configured in the cache configuration:

`&lt;caches&gt;
  &lt;cache
      name="..." ①
      enabled="true"&gt; ②
    &lt;maxSize&gt;...&lt;/maxSize&gt; ③
    &lt;timeout&gt;...&lt;/timeout&gt; ④
  &lt;/cache&gt;
  ...
&lt;/caches&gt;`Each cache configuration entry specifies the `name`[1] of the cache it configures (see below). `enabled`[2] can be used to enable the cache or disable it altogether.

`&lt;maxSize&gt;` [3] specifies the maximum number of entries in the cache. If necessary, older entries are evicted from the cache to make space for new ones.

`&lt;timeout&gt;` [4] specifies the maximum duration for which an item is kept in the cache before it is evicted. A timeout value of `0` means that items are kept indefinitely (but may still be evicted if the cache would otherwise exceed its maximum size).

The default settings differ for each cache and depend on the cache definition.

### Standard Caches
Caches are defined by modules. Additional modules may introduce additional caches. The following standard caches are available in every Process Engine installation:

`infinica:instances`

Caches process instances. Reduces the overhead of reading from the storage when instance data is required internally or for API calls.

`infinica:executors`

Caches process executors. Prevents executors from having to be re-created from the storage if they stop executing for a short amount of time, e.g. due to a wait state.

`infinica:processDefinitions`

Caches process definitions. By default, this cache has a maximum size, but no timeout.

As loading a process definition is an expensive operation, process instantiation is sped up when the required instance is available in the cache.

## Janitor Service Configuration
The janitor service is used to prevent leaks by automatically purging unused resources in the background.

`&lt;janitor&gt;
  &lt;processes&gt;
    &lt;cleanupProcessesInterval&gt;1d&lt;/cleanupProcessesInterval&gt; ①
    &lt;finishedTimeout&gt;none&lt;/finishedTimeout&gt; ②
    &lt;failedTimeout&gt;none&lt;/failedTimeout&gt; ③
    &lt;terminatedTimeout&gt;none&lt;/terminatedTimeout&gt; ④
  &lt;/processes&gt;
  &lt;cleanupWatchersInterval&gt;30s&lt;/cleanupWatchersInterval&gt; ⑤
&lt;/janitor&gt;``cleanupProcessesInterval `[1] specifies how frequently the janitor service purges old process instances. This is only relevant if at least one of the following three timeouts is configured.

`finishedTimeout `[2], `failedTimeout `[3], and `terminatedTimeout `[4] define how long after a process has ended it may be automatically purged by the janitor service, depending on its end state. None of these timeouts have default values. A finished process will only be purged if a timeout has been configured for its end state.

`cleanupWatchersInterval `[5] specifies how frequently the janitor services purges old process watchers.

## Performance Logging Configuration
If performance logging is enabled, the Process Engine will collect performance data of various operations, e.g. API operations and storage access. The performance data can be written to the log and can also be queried via the diagnostic manager.

`&lt;performanceLogs
    markerPrefix="..."&gt; ①
  &lt;log id="..." ②
      level="..." ③
      logNewEntries="..." ④
      statisticsOnShutdown="..." /&gt; ⑤
  ....
&lt;/performanceLogs&gt;`When writing to the Process Engine log, each performance log uses its performance log ID as a marker, to allow for advanced filtering in the Log4j configuration. If `markerPrefix`[1], is set, every performance log marker will be prefixed with this string.

Multiple performance logs can be configured individually. For each log, identified by its `id`, the following options can be set:

`level `[3] defines the log level for when information from this performance log is written to the Process Engine log. Allowed values are: `off, debug, info, warn, error, fatal.`

If `logNewEntries `[4] is `true`, every new performance log entry will be immediately written to the Process Engine log, along with the exact execution time of the related operation.

If `statisticsOnShutdown `[5] is `true`, the collected data of this entire performance log will be written to the Process Engine log during shutdown. For each operation type, the number of executions will be logged, along with the minimum, maximum, average, and total time of execution.

The following performances logs are available for configuration:

`api`

Execution times of API operations.

`internal`

Execution times of certain internal operations.

`processDefinitionExecutions`

Process execution times per process definition.

`activityTypeExecutions`

Activity execution times per activity type.

By default, all of these logs are set to the `debug `logging level, with the exception of the `api`log, which is set to `info`. By default, the data of all these logs is logged during shutdown.

## Compatibility Configuration
The *compatibility* section may be used to make the Process Engine behave like an earlier version in certain situations where an update has introduced a different behaviour:

`&lt;compatibility&gt;
  &lt;legacyConstants&gt;true&lt;/legacyConstants&gt; ①
  &lt;nestedCurlyBraces&gt;true&lt;/nestedCurlyBraces&gt; ②
  &lt;ignoreRedefinedNamespaces&gt;true&lt;/ignoreRedefinedNamespaces&gt; ③
  &lt;taskElementOutputPayloadOnly&gt;true&lt;/taskElementOutputPayloadOnly&gt; ④
  &lt;guessCredentialsRegistryPorts&gt;false&lt;/guessCredentialsRegistryPorts&gt; ⑤
&lt;/compatibility&gt;`Legacy constants [1] are constants like *_engineBaseUrl* and *_VERSION*, which have been replaced by XPath functions. If this setting is activated, the legacy constants are still available.

Nested curly braces [2] refer to the treatment of nested pairs of curly braces in parameterised literals and similar constructs. In earlier versions, *some* of these expressions were parsed, somewhat inconsistently, in such a way that additional opening curly braces in an expression were counted and matched with closing braces. For example, '{ x { } y }' would in those cases have been considered a single curly brace expression. In other locations, the same expression was considered to end at the first closing brace, i.e. was treated as '{ x { }', with the remaining 'y }' not part of the same expression. Newer versions of the Process Engine consistently treat all expressions this way, and curly braces *inside* an expression should be escaped to prevent them from being treated as expression delimiters: '{ x \{ \} y }'. Activating this compatibility option restores the older, inconsistent behaviour.

As of version 5.4, included sub processes may not redefine namespace prefixes used in the parent process, as this would cause conflicts when resolving XPath expressions using those prefixes. By default, if an included processes tries to redefine a namespace, instantiation of the process definition will fail. *&lt;ignoreRedefinedNamespaces&gt;* [3] can be activated to revert to the old behaviour. In this case, sub processes with redefined namespaces may be instantiated, but the namespace redefinitions are ignored and a warning is logged. Note that such sub processes will use the namespace definitions of their parent process for all XPath expressions.

Prior to version 5.4, the task element’s output parameters only included the resulting task payload. Starting with 5.4, the task element also includes the task itself (as an XML document) in the `task` parameter. This could cause conflicts with an earlier version if the task payload itself contains an entry named `task`. If *&lt;taskElementOutputPayloadOnly&gt;* [4] is enabled, task elements will skip outputting the task XML in the `task`parameter.

Until 6.2, issues with credentials lookups could cause credentials registry entries to be used even if their ports did not match the actually accessed ports. At the same time, specifying `http`or `https`as a protocol would automatically set the matching port. In 6.2, the lookup fix will result in such mismatched registry entries to be ignored, which can lead to old registries with mismatched ports to stop working. Setting `&lt;guessCredentialsRegistryPorts&gt;` [5] to `false`disables the automatic setting of ports from the protocol.

> Warning

Compatibility features should only be used as a temporary measure before the process definitions and configurations can be upgraded to adhere to the new behaviour. Legacy behaviour is considered deprecated and may be removed (along with its corresponding compatibility settings) in any future version.

## Messaging Configuration
On startup Process Engine can start an embedded Apache ActiveMQ message broker or connect to an existing JMS message broker. These options are configured in the *messaging *section. The broker is mainly intended to be used for message logging, but can also be used for message activities and message wait states, as well as any other application of JMS messaging. The message client will be used as default client for message logging.

The snippet below shows an example configuration for an embedded server:

`&lt;messaging port="61616" serverIp="0.0.0.0" /&gt;`**port**

The port under which the broker should be available.

**serverIp**

IP address or hostname under which the broker is reachable. This is used to construct the broker URL which can be queried from the Process Engine API, so it should point to a host which is reachable from the outside.

In order to connect to an existing message broker, a message client configuration must be provided as child of the messaging node. A simple example is shown below. The message client configuration in general is described in more detail in the following subsection.

`&lt;messaging&gt;
    &lt;messageClient uri="tcp://127.0.0.1:61616" xmlns="http://www.infinica.com/messaging" /&gt;
&lt;/messaging&gt;`### Message Client Configuration
Wherever the Process Engine connects to a message broker (currently for message logging, message activities and message wait states), the message client which sends or receives messages can be configured using a common XML format. This format is described below:

`&lt;messageClient xmlns="http://www.infinica.com/messaging"
uri="..." clientId="..." username="..." password="..." reconnectAttempts="..."
reconnectInterval="..."&gt;
    &lt;jndi connectionFactory="..."&gt;
        &lt;property key="..."&gt;...&lt;/property&gt;
    &lt;/jndi&gt;
    &lt;destination name="..." jndi="..." topic="..." /&gt;
    &lt;consumer destination="..." selector="..." noLocal="..." subscription="..." durable="..."
shared="..." /&gt; &lt;/messageClient&gt;`**uri (1)**

The URI of the message broker which this client should connect to.

**clientId (0..1)**

The JMS client ID under which this client should connect.

**username (0..1)**

Username for login in case the broker uses authentication.

**password (0..1)**

Password for login in case the broker uses authentication.

**reconnectAttempts (0..1)**

The number of times, the message client tries to reconnect to the server in case the connection is lost. If all attempts have been unsuccessful, the client will be closed. When set to 0, it will not attempt to restore the connection at all, when set to -1 it will make periodic attempts indefinitely. When a reconnect attempt is successful and a working connection is established again, the reconnectAttempts for the next connection loss will be reset to the configured value. The default used when the attribute is not set is 5.

**reconnectInterval (0..1)**

The time to wait between reconnect attempts in milliseconds. If the attribute reconnectAttempts is set to 0, this has no effect. The default value is 5000.

**jndi (0..1)**

This node is required if JNDI should be used to look up the necessary objects. For more information about message clients with JNDI see [JNDI Message Client.](/doxee-platform/docs/6-6-process-engine-administration-reference-configuration-1#jndi-message-client)

jndi (0..1)/**connectionFactory (0..1)**

Name of the connection factory to look up via JNDI

jndi (0..1)/**property (0..n)**

JNDI properties for the lookup. The content of the node specifies the property value.

jndi (0..1)/property (0..n)/**key (1)**

Property key.

**destination (0..1)**

The default destination which should be used for sending and/or receiving messages. The client will automatically try to connect to this destination when opened.

destination (0..1)/**name (1)**

Either the name of the destination on the broker when not using JNDI or the JNDI lookup name if JNDI is used.

destination (0..1)/**jndi (0..1)**

Boolean flag specifying whether or not JNDI should be used to look up the destination. Default is false.

destination (0..1)/**topic (1)**

Boolean flag specifying whether the destination is a topic or a queue. True for topic, false for queue.

**consumer (0..1)**

The default consumer which should be used for receiving messages. The client will automatically create this consumer, connect to the specified destination and receive messages when opened.

consumer (0..1)/**destination (1)**

The name of the destination from which this consumer receives messages. 

consumer (0..1)/**selector (0..1)**

JMS message selector expression which can be used to filter messages on the server side. For details about these selector expressions please consult documentation for JMS.

consumer (0..1)/**noLocal (0..1)**

Boolean flag controlling whether or not this consumer will receive messages produced via the same connection. Only relevant for destinations of type topic. 

**subscription (0..1)**

If the consumer should be durable and/or shared, it needs to have a subscription name which is provided through this attribute. If the attributes "durable" and "shared" are both "false", this has no effect. Otherwise it will connect to an existing subscription or create a new one with the value of this attribute as subscription ID. Only relevant for destinations of type topic. For more information about durable and shared subscribers please consult documentation for JMS.

consumer (0..1)/**durable (0..1)**

Set to "true" if the consumer should create a durable subscription. Also requires the attribute "subscription". Default is "false".

consumer (0..1)/**shared (0..1)**

Set to "true" if the consumer should create a shared subscription. Also requires the attribute "subscription". Default is "false".

Specific use cases of the message client might require different configurations. The message activity requires a destination, the message wait state requires a consumer to be specified.

### JNDI Message Client
If the message client is configured without the jndi element, it uses an ActiveMQ client as the JMS implementation. This client will work with ActiveMQ servers, but will not be compatible with every messaging software implementing JMS. In order for the Process Engine to use a compatible client for other server implementations, JNDI can be used. This requires that the server provides the necessary information via JNDI (the availability and how to configure it, depends on the implementation) and that the Java libraries containing the specific JMS implementation are added to the Process Engine classpath. If those conditions are met, the message client configuration in the Process Engine can contain settingsfor JNDI. These include the following options:

- The attribute "connectionFactory" in the jndi element, which must be set to the JNDIname of the implementation-specific JMS ConnectionFactory to be used. In case of ActiveMQ this value is ConnectionFactory by default, it might be different for other servers.

- The JNDI property "java.naming.factory.initial" with the name of the JNDI ContextFactory class as value. In case of ActiveMQ this would be "org.apache.activemq.jndi.ActiveMQInitialContextFactory", in other implementations this will be different.

- If the server requires authentication, two additional properties are necessary:

java.naming.security.principal

- java.naming.security.credentials

- If a destination should be loaded through JNDI (which is the preferred way in most cases), the attribute "jndi" on the destination element must be set to "true".

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}