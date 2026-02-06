---
id: "602c381b-7a66-492a-9be4-9ea64b5f7494"
title: "Accessing the Process Engine"
slug: "6-6-process-engine-user-guide-accessing-the-process-engine-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.53Z"
modified_at: "2026-01-07T14:04:28.741Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-accessing-the-process-engine-1"
synced_at: "2026-01-28T20:54:52.008Z"
checksum: "2dec10a022c9f187"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

## Overview
Process Engine can be accessed via a number of interfaces. While each interface may offer slightly different features and capabilities, each operation exposed by these interfaces can generally be attributed to one of these categories:

- Process lifecycle management

- Process state queries

- Administration

- Other operations

No specific interface operations are necessary for deploying process definitions. Instead, definitions are deployed simply by copying them into the storage defined by the Process Engine’s process definition URL. If an existing process definition is upgraded by replacing it with a new version of the IPD file, it may be necessary to clear the Process Engine’s cache either with a corresponding operation or by specifying a flag to skip the cache when instantiating the process definition the next time. This is only relevant if process definition caching has been enabled in the Process Engine configuration.

### Process Lifecycle Management
Lifecycle management operations include operations for instantiating, continuing, pausing and terminating processes.

#### Instantiating a Process
When instantiating a process, the client provides the virtual process path and Process Engine responds by loading the process definition and creating a new process execution. The execution will be put in the CREATED state. Typically, clients will also be able to provide additional flags, e.g. to specify that the process definition should not be read from the cache, or the name of a thread pool to use when executing the process. Because the new execution will be in the CREATED state, it will not be started until the client explicitly instructs the Process Engine to do so.

If a process is in a BROKEN state because it could not be reinitialised after restarting the Process Engine, the client can request the process to be reloaded after the problem has been fixed.

#### Starting a Process
A process in the state CREATED is ready for execution, but still on hold and will not be executed until the client instructs the Process Engine to continue the execution. Such a call will put the process in the READY state, which signals to the Process Engine that it is ready for execution and should be started or continued as soon as resources are available. Execution may still be delayed e.g. when the execution is assigned to a thread pool that currently has no threads available.

#### Terminating a Process
A process that is not currently in an end state can be terminated by a client. A regular termination call requests that the Process Engine stops the process execution, leaving it up to the process to finish its current action (e.g. a currently running activity if the execution is in the RUNNING state). If an execution is non-responsive and does not react to a regular termination request, a client may specify the KILL flag to instruct Process Engine to immediately terminate the process’s thread at the risk of data loss.

#### Offline Processes
At any point before it reaches an end state, a process execution’s online state may be set to *offline*. This will prevent the process to switch from the READY to the RUNNING state and thus effectively prevent the process from being executed as long as it is offline. If a process is set offline while it is currently RUNNING, it will stop execution at the next opportunity and then be set offline.

Offline processes may perform other state switches as normal. For example, an offline process that is WAITING may receive a signal from its wait state and change its state back to READY (but it will not switch from READY to RUNNING until it is back online).

To automatically take a process offline at specific points during its execution, breakpoints may be set. Whenever a process reaches a breakpoint (at which point it is necessarily in the RUNNING state), it will go offline and therefore cease execution, reverting to the READY state.

An offline process may be set online at any time to allow it to resume execution.

#### Results
Operations that refer to a process execution usually return an execution snapshot. This snapshot represents the process’s state at the time the operation provided its result. It does not prevent the process from changing once the operation has concluded, and will not reflect any changes to the process’s state after that point.

For example, the snapshot returned by an instantiation call provides the execution ID that is necessary for the client to perform further operations on the newly created process execution, e.g. a continue call.

#### Timeouts
Operations that cause a (direct or indirect) change to a process’s execution state often support a timeout flag that specifies when the operation should return.

Timeouts always refer to changes of the execution state, allowing an operation to block until the state has changed, but the specific change may depend on the type of operation. For example, a continue operation may by default wait for a non-active state. Additional flags may allow the client to specify exactly which state a operation should wait for.

Timeout values are in milliseconds and are interpreted as follows:

**-1**

The operation will block until the process reaches the desired state. A returned snapshot will therefore always specify a non-active state.

**0**

The operation will return immediately after the request has been noted by Process Engine. A returned snapshot’s state may vary depending on how quickly the Process Engine starts performing the request. For example, a continue call on a CREATED process may result in a snapshot in the READY or RUNNING state, or even in a nonactive state.

**&gt;0**

Any positive value *n* requests that the operation should try to block as described for the value -1, but only for a maximum of *n* milliseconds. After that time, the operation will return regardless of the current process state.

### Process State Queries
Queries allow clients to receive information about specific process executions or even multiple executions. A client can request the process snapshot for a specific execution ID, or the list of current process execution IDs.

### Administration
Administration operations allow clients to perform administrative tasks not related to specific processes. This includes querying the list of available modules and global constants, setting and retrieving the maintenance level and clearing the Process Engine cache.

### Other Operations
Additional operations include calls to verify a process definition provided by the client. Process Engine will respond with an error if the process definition is not valid.

### Security
If authentication is enabled, access to the Process Engine may be limited depending on the user’s permissions. Some operations may only be available to certain users, and different users may be able to see different processes.

## Command Line Interface
The command line interface is a very restricted Process Engine interface designed to execute a single process. The client provides the path of a process definition and the Process Engine instantiates and executes the process, returning once the execution has reached an end state. If the execution fails, the corresponding error message is written to the output.

The command line tool can also be used to perform the same task through an external Process Engine by specifying the external installation’s base URL. This way, a command line call can act as a conduit for executing a process on a server installation of Process Engine e.g. through the SOAP interface. However, regardless of the server, the functionality of the client is still limited to the straightforward execution of a single process.

### Executing a Process
The command line tool is executed as a Java application like this:

`&gt; java -jar infinica-process-engine.jar process.ipd`The only required argument after the name of the jar file is the path to the process definition. However, further arguments can be specified to pass input variables to the process in the format *name=value*:

`&gt; java -jar infinica-process-engine.jar my_process.ipd valueA=x valueB=y`> Note

Since the shell treats space characters as separators between arguments,

variable assignments containing spaces must be put between quotes like this:

`&gt; java -jar infinica-process-engine.jar process.ipd "valueA=y z"`#### **Options**
The following options can be specified when calling the tool:

**--help**

Prints a usage message to the console instead of executing a process.

**--user**

Provides the user name.

**--password**

Provides the user’s password.

**--version**

Prints the Process Engine version instead of executing a process.

**--config**

Prints the Process Engine configuration instead of executing a process.

**--man**

Creates a PDF containing the man pages for all installed modules and writes it to the specified file.

**--validate**

Validates the specified process definition instead of executing it

**--base**

Specifies the Process Engine base URI. If not provided, the current directory will be used.

**--log**

Displays the process log.

**--nolog**

Disables displaying the process log.

**--diagnosticpattern **

Specifies the diagnostic log pattern.

**--tracelog**

Displays the trace log.

**--notracelog**

Disables displaying the trace log.

--tracepattern *&lt;pattern&gt;*: Specifies the trace log pattern.

Additional options are available to run Process Engine in server mode instead of directly executing a process.

#### Default Configuration
Default configuration options can be provided in a file named `process_engine_launcher.xml`. Any options specified in this file may be overrided by options provided on the command line.

`&lt;launcher xmlns="http://www.infinica.com/process/launcher"
    baseUri="base/"&gt;
  &lt;log enabled="true"&gt;
    &lt;diagnostic pattern="{level} {message}" /&gt;
  &lt;/log&gt;
  &lt;traceLog enabled="false" pattern="[{event}] {source}" /&gt;
&lt;/launcher&gt;`All elements and attributes provided in the file are optional. Their meaning corresponds with the command line options described above.

## Web Service Access
The common way for clients to access a Process Engine installation is through the web service API. Process Engine offers both a SOAP and a REST interface.

### SOAP Access
When running on the local system in standalone server mode with the settings from the default configuration, the SOAP interface can be reached at this URL:

`http://localhost:8080/soap`If running in a Tomcat container as a web application with the name *infinica-process-engine *instead, the URL is:

`http://localhost:8080/infinica-process-engine/soap`In both cases, the WSDL is accessible by adding *?WSDL* to the URL, e.g.:

`http://localhost:8080/soap?WSDL`The operations provided by the SOAP interface are closely related to the embedded Java interface. The XML namespace for all requests and responses is:

`http://server.webservice.access.engine.infinica.com/`### REST Access
When running on the local system in standalone server mode with the settings from the default configuration, the REST interface can be reached at this URL:

`http://localhost:8080/rest`If running in a Tomcat container as a web application with the name *infinica-process-engine *instead, the URL is:

`http://localhost:8080/infinica-process-engine/rest`When accepting and returning structured data, the REST interface defaults to JSON (`application/json`) encoded data. Clients may choose to use XML instead by specifying the `application/xml` type when sending data and in the HTTP requests' `Accept` header.

### Authentication
Both web service interfaces can use all authentication mechanisms supported by Doxee. For both SOAP and REST, authentication credentials are provided via HTTP (e.g. HTTP basic authentication). If the client sends no credentials or otherwise invalid credentials to a Process Engine service requiring authentication, the server will replay with a standard `401` `Unauthorized` response.

### Operations
A full list of all web service operations can be found in [Process Engine API](/doxee-platform/docs/appendix-c-process-engine-api).

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}