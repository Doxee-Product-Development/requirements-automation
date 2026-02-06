---
id: "09b66475-cf98-4c10-a475-d5f8d44a90a5"
title: "Process Engine API"
slug: "6-6-process-engine-user-guide-process-engine-api-1"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:03.823Z"
modified_at: "2026-01-07T14:04:28.741Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-process-engine-api-1"
synced_at: "2026-01-28T20:54:53.754Z"
checksum: "297d38bb4adaa6de"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

This appendix gives a complete overview of the operations provided by the Process Engine API. All operations are available via SOAP and REST. The exact operation names and paths for each service type are included with the individual operation entries.

## Data Structures
Some API operations use structured data types as parameters or responses. These structures are described in the following sections.

Data structures are represented as XML. When using the REST API with JSON types, the JSON structures are simple JSON representations of the XML structures.

### Process Snapshot
Many API operations return a snapshot of the requested process. A process snapshot is a structure of the following format:

`&lt;processExecutionSnapshot xmlns:dat="http://www.infinica.com/datastore"
                          autoDispose="..."
                          createdAt="..."
                          currentElement="..."
                          currentTime="..."
                          currentUser="..."
                          debug="..."
                          executionId="..."
                          externalId="..."
                          finishedAt="..."
                          locked="..."
                          message="..."
                          online="..."
                          owner="..."
                          ownerNode="..."
                          processEngineId="..."
                          startedAt="..."
                          state="..."
                          stateChangeIndex="..."
                          threadPoolId="..."&gt;
   &lt;definitionInfo changedAt="..."
                   location="..."
                   name="..."
                   uri="..."
                   version="..."/&gt;
   &lt;exceptionReport message="..."
                    source="..."
                    type="..."&gt;
        &lt;cause&gt;...&lt;/cause&gt;
   &lt;/exceptionReport&gt;
   &lt;health state="..."
           message="..."
           exceptionType="..." /&gt;
   &lt;permissions&gt;
        &lt;ace name="..."&gt;
            &lt;privilege&gt;...&lt;/privilege&gt;
        &lt;/ace&gt;
   &lt;/permissions&gt;
   &lt;pipeline&gt;
      &lt;dat:values&gt;
         &lt;dat:value id="..." type="..."&gt;
            &lt;dat:content&gt;...&lt;/dat:content&gt;
         &lt;/dat:value&gt;
      &lt;/dat:values&gt;
      &lt;dat:entries&gt;
         &lt;dat:entry name="..."&gt;
            &lt;dat:value&gt;...&lt;/dat:value&gt;
         &lt;/dat:entry&gt;
      &lt;/dat:entries&gt;
   &lt;/pipeline&gt;
&lt;/processExecutionSnapshot&gt;`**autoDispose**

The process' auto dispose setting (`never, fetch, endedNotFailed`, or `endedOrFailed`).

**createdAt**

The time at which the process instance was created.

**currentElement**

The hierarchical id of the process element currently being executed.

**currentTime**

The time at which the process snapshot was created.

**currentUser**

The name of the process’s current user. Initially, this is the same as the process owner, but may differ if new credentials are assigned to the process (or if the owner is changed).

**debug**

The process' debug setting (`true` or `false`). 

**executionId**

The unique ID of the process execution.

**externalId**

The external ID of the process, if set. This can be used to associated the process with other elements.

**finishedAt**

The time at which the process instance reached an end state. Not present if the process is still running.

**health**

The current health of the process instance.

health/**state**

Health status. One of `OK, LOST, BROKEN, DEFINITION_CONFLICT, CORRUPT`, or `KILLED`.

health/**message**

A human readable message describing the health status.

health/**exceptionType**

The type of the exception that caused the current health status, if any.

**locked**

** **`true` if the process is locked to one Process Engine node (preventing it from being relocated in the cluster).

**message**

A message describing the execution state, for example an error message if the process failed.

**online**

True if the instance is online, false otherwise.

**owner**

The name of the user who currently owns the process.

**ownerNode**

The process engine node currently executing the process, or if the process is locked, the last node which executed the process if it is not currently running. 

**processEngineId**

The ID of the last Process Engine which modified this instance.

**startedAt**

The time at which the process was started.

**state**

The lifecycle state of the process.

**stateChangeIndex**

An index that increases whenever the process changes its state. 

**threadPoolId**

The ID of the thread pool in which this instance should be executed.

**processDefinitionInfo**

Information about the underlying process definition.

processDefinitionInfo/**id**

The unique ID of the process definition.

processDefinitionInfo/**changedAt**

The date and time when the definition was last changed.

processDefinitionInfo/**name**

An optional name for the process.

processDefinitionInfo/**location**

The process definition URI. Used as the base URI during process execution.

processDefinitionInfo/**versionNumber**

Currently not used, always 0.

**exceptionReport**

If an exception occurred, this node contains details about what happened.

exceptionReport/**message**

Human readable message of the exception.

exceptionReport/**source**

The element where the exception occurred.

exceptionReport/**type**

The exception type.

exceptionReport/**cause**

If there is a nested exception, this node contains its exceptionReport.

**permissions (0..n)**

A list of access control entries set for the process instance.

permissions (0..n)/**ace**

An access control entry.

permissions (0..n)/ace/**name**

The name of the permission.

** **permissions (0..n)/ace/**privileges (0..n)**

The privileges for the entry.

**pipeline (0..1)**

The process pipeline as a data store.

### Data Store
A data store is a format for transferring collections of typed key/value entries. The Process Engine uses data stores to transfer process pipelines and constants. The format is also used by other Doxee products like the Task Manager. This guarantees that different Doxee tools can exchange typed data without data loss.

Process pipelines, constants, and similar collections of key/value collections are transferred as *data stores*.

The data store structure is described in [Data Stores.](/doxee-platform/docs/appendix-d-data-stores)

Data stores can be represented in two ways. The *standard format* is an exact representation of the internal data store used by Doxee. The *simple data store format* is a simplified structure which loses some detail information but is easier to parse. When sending requests which contain a data store, clients may use either format (the service automatically detects which format is used). For operations which return a data store, clients can choose their desired data store representation.

#### **SOAP**
SOAP operations which return a data store contain an additional parameter `simpleDataStore`. Setting this to true will cause the service to return simple data stores, while `false` will use the standard data store format instead. By default, simple data stores are returned.

#### **REST**
For REST operations which return a data store, clients can choose the data store format using the HTTP header` x-infinica-datastore-mode`. Possible values are simple or standard. By default, simple data stores are returned.

### Process Validation Result
This data structure represents the result of a call to the validate operation. It contains information about the process definition.

### Maintenance Level
Represents a maintenance level as specified in the Process Engine configuration.

`&lt;maintenanceLevel
    id="..."
    label="..."
    online="..." /&gt;`**id**

The level ID. This can be used to set a new maintenance level.

##### **label**
A human readable label.

**online **

`allOnline` or `allOffline` if all existing processes should be set online or offline when the maintenance level is activated, or `noChange` if the online state of processes should not be affected.

### Node State
The node state structure contains information about the current state of a single Process Engine node.

`&lt;nodeState engineId="..." 
           online="..." 
           runningProcesses="..."&gt;
  &lt;cluster rootNode="..." 
           master="..." 
           connectionStatus="..." 
           statusMessage="..."&gt;
    &lt;waitStateHandlers&gt;
      &lt;handler&gt;
        ...
      &lt;/handler&gt;
      ...
    &lt;/waitStateHandlers&gt;
  &lt;/cluster&gt;
&lt;/nodeState&gt;`**engineId**

The unique ID of the Process Engine node.

**online**

Whether the node is currently online.

**runningProcesses**

The number of processes currently being executed (i.e. in a `RUNNING` state) on this node.

#### Cluster Specific Information
**rootNode**

The path to the Process Engine node specific ZNode in Zookeeper. 

**master**

Whether the node is currently the master node. `true` or `false`.

**connectionStatus**

Current cluster connection status; `before, connected, tryingReconnect, disconnected, or connectionLost`.

**statusMessage**

May contain a human readable status message relating to the connection status (e.g. an error description).

**waitStateHandlers/handler (0..1)**

A list of wait state handlers running on this node. In a cluster, each wait state handler will run on no more than one node at a time.

### Service Configuration Info
Provides a list of services as set up in Process Engine configuration.

`&lt;serviceConfigInfos&gt;
  &lt;service id="..." 
           autostart="..." 
           threadPoolId="..."&gt;
    &lt;description&gt;
      ...
    &lt;/description&gt;
  &lt;/service&gt;
  ...
&lt;/serviceConfigInfos&gt;`**service (0..n)**

One entry per service process.

**id**

The service ID. Can be used to start and query services.

**autostart**

Whether the service process should start automatically during Process Engine startup (if it is not already running).

**threadPoolId**

Optional ID of a thread pool in which the service process is executed.

**description**

A human readable description of the service.

### Queries
Queries are used to look up specific processes based on their properties.

**XML**

`&lt;query xmlns="http://www.infinica.com/query"
    xmlns:dat="http://www.infinica.com/datastore"
    offset="0" ①
    limit="10"&gt; ②
  &lt;!-- Query tree --&gt;  ③
  &lt;sort&gt;
    &lt;criterion field="..." ascending="true" /&gt; ④
  &lt;/sort&gt;
&lt;/query&gt;`**JSON**

`{
  "query": {
    &lt;!-- Query tree --&gt; ③
    "sort": {
      "criterion": { ④
        "field": "...",
        "ascending": "true"
      }
    },
    "offset": "0", ①
    "limit": "1000"  ②
  }
}`A query consists of a query tree [3] (see below) and optionally:

**offset [1]**

The index of the first element to return (for paged queries).

**limit [2]**

The maximum number of elements to return (i.e. the page size for paged queries). 

**criterion [4]**

Any number of optional sorting criteria, each specifying one field (i.e. process property) to sort by and the sorting direction (ascending or descending).

The query tree can be empty (in which case all processes are found) or start with a query node, which depending on its type can contain further sub nodes. The following query nodes are available:

##### and
**XML**

`&lt;and&gt;
    &lt;!-- sub nodes --&gt;
&lt;/and&gt;`**JSON**

`"and": {
    &lt;!-- sub nodes --&gt;
}`An and node can contain any number of sub nodes. A process must match all of these nodes to be found by the query.

##### or
**XML**

`&lt;or&gt;
    &lt;!-- sub nodes --&gt;
&lt;/or&gt;`**JSON**

`"or": {
    &lt;!-- sub nodes --&gt;
}`An or node can contain any number of sub nodes. A process must match at least one of these nodes to be found by the query.

##### not
**XML**

`&lt;not&gt;
    &lt;!-- sub node --&gt;
&lt;/not&gt;`**JSON**

`"not": {
    &lt;!-- sub node --&gt;
}`A not node must contain exactly one sub node. The result of that node will be inverted (i.e. a positive match will be converted to a negative one, and vice versa).

#### param
**XML**

`&lt;param
    field="..."
    operation="..."&gt;
    &lt;values type="..."&gt;
      &lt;dat:value&gt;...&lt;/dat:value&gt;
    &lt;/values&gt;
&lt;/param&gt;`**JSON**

`"param": {
  "values": {
    "value": [...]
    },
    "field": "...",
    "operation": "..."
}`A param node tests whether a specific process property matches the query. The node consists of the following items:

**field**

The name of the process propery (see below).

**operation**

The query operation (see below).

**values**

One or more comparison values, depending on the operation. The type attribute specifies the content type of the values (e.g. text/plain). See [Data Stores](/doxee-platform/docs/6-6-process-engine-user-guide-data-stores-1) for more details.

#### Operations
The following operations are supported by queries:

**isNull**

Tests whether a property is null.

**equals**

Tests whether a property matches a given value.

**in**

Tests whether a property is listed in a given set of values.

**like**

Tests a string property against a pattern.

**lessThan**

Tests whether a number or time stamp is less than a given value.

**greaterThan**

Tests whether a number or time stamp is greater than a given value.

#### Properties
The following process properties can be used in queries:

**executionId**

Execution ID.

**externalId**

External ID.

**state**

Current execution state.

**owner**

Process owner.

**processUri**

Process definition URL. 

**online**

Online state (boolean).

**health**

Health state.

**previousNode**

The last Process Engine node owning the process.

**ownerNode**

The Process Engine node currently owning the process.

**createdAt**

The creation time stamp.

**startedAt**

The time stamp at which the process was started.

**finishedAt**

The time stamp at which the process reached an end state.

### Multi-Error Responses
Some operations which affect multiple named entities (e.g. setInstanceConstants) can return a multi error response which contains an entry for each failed entity, along with the corresponding error message:

**XML**

`&lt;pe:errors&gt;
  &lt;entry&gt;
    &lt;key&gt;...&lt;/key&gt;
    &lt;value&gt;...&lt;/value&gt;
  &lt;/entry&gt;
&lt;/pe:errors&gt;`**JSON**

`{
  "multiErrorResponse": {
    "errors": {
      "entry": [
        {
          "key": "...",
          "value": "..."
        }
      ]
    }
  }
}`## Synchronous vs. Asynchronous Calls
Some operations will by default wait for the request to be completely handled before returning. For example, startProcess will normally wait for the process to reach an end state. These operations are called synchronous operations.

Operations that may be carried out synchronously typically support three parameters:

- `states`

- `waitOnline`

- `timeout`

states and waitOnline define the state of the process for which the operation should wait. The default depends on the particular operation. For example, as mentioned above, startProcess will wait for any end state (i.e. `FINISHED, FAILED, or TERMINATED`). This behaviour may be changed by defining specific execution states to wait for with the `states` parameter. For example, startProcess may be instructed to only wait for a RUNNING state, in which case the command will return as soon as the process actually starts running.

Likewise, waitOnline may be used to wait until a process reaches a specific online state (i.e.

online or offline). This is particularly useful for operations that affect the online state, like setOnline, but it may also be used with operations that are not directly related to the online state. For example, `waitForProcess` may be called with `waitOnline` to wait until some other event (e.g. an unrelated call to `setOnline`) has changed the process' state.

If both `states` and `waitOnline` are specified, the operation will wait until the process matches one of the specified execution states *and* the desired online state.

Every synchronous operation which supports a `timeout` parameter can be turned into an asynchronous operation by setting a timeout value. The timeout defines the maximum duration, in milliseconds, for which the operation should block until returning, even if the desired result has not yet occurred. For example, calling `startProcess` with a timeout value of 0 will immediately return without waiting for the process to reach an end state (or even an active state before that, for that matter). Alternatively, a timeout value of `10000` will try to wait for the process to reach an end state, but after waiting for 10 seconds return regardless of what state the process is in.

A timeout value of -1 causes the operation to block as long as necessary for the desired result. This is usually the default.

> Inportant

If the Process Engine configuration specifies a maximum timeout, all timeout parameters will be capped with the specified maximum. This applies even to -1 (indefinite) timeouts.

## Peeking
Process Engine will keep a list of all active process instances. Once a process instance reaches an end state, its information will be kept until a client directly or indirectly requests its snapshot (e.g. calling `startProcess` returns a snapshot of the corresponding process). Depending on the process' `autoDispose` setting (specified during instantiation, or as a default setting in the Process Engine configuration), its state information may be purged from the Process Engine after its state has been queried, and the process’s execution ID will no longer be available. For example, the default `autoDispose` setting is `fetch`, which disposes the process on fetch if it has reached an end state.

Some operations provide a boolean `peek` flag which allows clients to override this behaviour. If `peek` is set to true, the call will not cause the Process Engine to dispose the process, regardless of its state.

## Operations
### Lifecycle Management
#### disposeProcess
**SOAP**

**disposeProcess**

**REST**

**DELETE /processes/{*executionId*}**

Deletes a process instance. The instance must not be in an active state, otherwise the operation will fail.

*Parameters*

Name

Description

Position

`executionId`

ID of the process execution that should be disposed.

Path

*Response*

A snapshot of the disposed process. Nothing, if the specified process did not exist.

#### disposeProcesses
**SOAP**

`disposeProcesses`

**REST**

`DELETE /processes`

Deletes multiple process instances based on the specified filters. The same rules as for disposeProcess apply. The filters match those described in findExecutions.

Once the target process instances have been selected, they will be disposed one by one. If an instance could not be disposed (e.g. because it was in an invalid state for disposal, or because of insufficient user privileges), an exception will be thrown. In this case, some but not all of the selected instances may have been already disposed.

*Parameters*

Name

Description

Position

`query`

A query specifying which processes should be disposed. For REST, the query must be provided as the request body. This is a mandatory parameter.

Body

`reportExecutionIds`

An optional boolean parameter that specifies whether a list containing the execution IDs of the disposed processes should be returned. If false (the default), only the number of disposed processes is returned.

Query

*Response*

Snapshots of all disposed processes. Nothing, if no matching processes were found.

#### instantiate
**SOAP**

`instantiate`

**REST**

`POST /processes`

Creates a new process instance from a process definition. If successful, the new process will be ready for execution, but remain in state `CREATED `until started via `startProcess`.

If the `process `parameter is specified, the process will not be read from the specified URI, or the cache, but the provided IPD will be used to instantiate the process. The process instance will still use the specified `processUri `as its base URI, e.g. when resolving relative URIs within the process. Note that instantiating a process from a stream requires different privileges than instantiating a process from a path on the server.

*Parameters*

Name

Description

Position

`processUri`

URI (or path) to the process definition that should be instantiated.

Body

`externalId`

An optional external ID string for the process instance. This can be used as a custom foreign key to associate the process with other entities known to the caller.

Body

`cache`

Whether the process definition may be read from the cache, if it has already been cached. Defaults to `true` if caching is enabled. Does not have an effect if an IPD stream is provided in the `process` parameter.

Body

`threadPoolId`

If specified, the process instance will be assigned to this thread pool.

Body

`process`

Optional IPD stream.

Body

`debug`

An optional boolean flag to enable or disable debug mode. If not specified, the default setting from the configuration will be used. Process in debug mode will always return the full pipeline content in snapshots, even when they are still active.

Body

*Parameters*

`autoDispose`

An optional auto dispose mode for the process. If not specified, the default setting from the configuration will be used. Possible values are `never, fetch, endedNotFailed, and endedOrFailed.`

Body

`locked`

An optional boolean value that specifies whether the process should be locked to the engine node on which it was instantiated.

Body

The parameters need to be specified in the Body of the request using `multipart/formdata` as Content-Type.

`--
xxx
Content-Type: text/plain
Content-Disposition: form-data; name="processUri"
processes/simple.ipd
--
xxx
Content-Type: text/plain
Content-Disposition: form-data; name="cache"
false
--
xxx
Content-Type: text/xml
Content-Disposition: form-data; name="process"
&lt;process xmlns="http://www.infinica.com/process-engine" version="4"&gt;
   &lt;startElement id="start"/&gt;
   &lt;endElement id="end"/&gt;
&lt;/process&gt;
--
xxx
--`*Response*

Snapshot of the instantiated process.

#### reload
**SOAP**

`reload`

**REST**

`POST /processes/{executionId}/reload`

Reloads the process definition for an already instantiated process.

This operation can only be executed on processes in the state `CREATED `or a process with health `BROKEN`.

If the `process `parameter is specified, the process will not be read from the specified URI, or the cache, but the provided IPD will be used to instantiate the process. The process instance will still use the specified `processUri `as its base URI, e.g. when resolving relative URIs within the process.

Parameters

Name

Description

Position

`executionId`

ID of the target process execution.

Path

`Parameters`

`processUri`

URI (or path) to the process definition that should be loaded.

Query

`setOnline`

If `true`, the process will automatically be set online after it has been reloaded

Query

`process`

Optional IPD stream. (Content-Type: multipart/formdata)

Body

*Response*

Snapshot of the reloaded process.

#### recoverProcess
**SOAP**

`recoverProcess`

**REST**

`POST /processes/{executionId}/recover`

Recovers a lost process instance. Recovering a process instance means that the health is set from `lost `to `ok `and the process can be executed again. If the parameter `setOnline `is set to `true`, the process instance will also be set online.

*Parameters*

Name

Description

Position

`executionId`

ID of the process instance which should be recovered.

Path

`setOnline`

If `true`, the process will automatically be set online after it has been recovered.

Query

`updateCredentials`

If `true`, the process' current credentials will be updated to those of the caller before it is recovered.

See also [updateCredentials](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#updatecredentials).

Query

*Response*

Snapshot of the recovered process.

#### recoverProcesses
**SOAP**

`recoverProcesses`

**REST**

`POST /recover`

Recover lost process instances identified by the provided parameters. Recovering a process instance means that the health is set from `lost `to `ok `and the process can be executed again. If the parameter setOnline is set to true, the processes will also be set online.

*Parameters*

Name

Description

Position

`setOnline`

If `true`, the processes will automatically be set online after they have been recovered

Query

`query`

A query specifying which processes should be recovered. For REST, the query must be provided as the request body.

Body

`reportExecutionIds`

An optional boolean parameter that specifies whether a list containing the execution IDs of the recovered processes should be returned. If false (the default), only the number of recovered processes is returned.

Query

*Response*

Snapshots of the recovered processes.

#### run
**SOAP**

`run`

**REST**

`POST /run`

**REST**

`GET /run`

Instantiates and runs a process.

This is essentially a combination of the `instantiate `and `startProcess `calls in a single operation. It makes it harder to distinguish instantiation errors from runtime errors, but allows clients behind a load balancer to execute processes.

When using a load balancer to distribute operations across multiple non-clustered Process Engine instances, only the Process Engine which instantiated a particular process will know its ID. A `startProcess` call (or other process related calls) that is directed to a different Process Engine by the load balancer will result in an error caused by an unknown execution ID. `run` provides a way to make sure that instantiation and execution are handled by the same Process Engine.

*Parameters*

Name

Description

Position

`processUri`

Process definition URI. See [instantiate](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#instantiate).

Query

`externalId`

An optional external ID string for the process instance. This can be used as a custom foreign key to associate the process with other entities known to the caller.

Query

`cache`

Whether the process definition may be read from the cache. See [instantiate](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#instantiate).

Query

`threadPoolId`

Optional thread pool ID. See [instantiate](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#instantiate).

Query

`processParams`

An optional set of parameters that will be passed to the process, in the form of a data store (POST) or as query parameters (GET).

Body/Query

`peek`

Peek flag. See [startProcess.](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#process-snapshot)

Query

`timeout`

Timeout. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startProcess).

Query

`states`

A list of execution states to wait for. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startProcess).

Query

`waitOnline`

Whether to wait for the process to go online. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startProcess).

Query

`inspectPipeline`

If set, the entire process pipeline will be included in the returned process snapshot. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startProcess).

Query

`setOnline`

If set to true, the instance will be set to online in case it is currently offline. The default for this parameter depends on the timeout parameter. If the timeout is &lt;

0 (synchronous) the default is `true`, otherwise it is `false`.

Query

`debug`

An optional boolean flag to enable or disable debug mode. If not specified, the default setting from the configuration will be used. Process in debug mode will always return the full pipeline content in snapshots, even when they are still active.

Query

`autoDispose`

An optional auto dispose mode for the process. If not specified, the default setting from the configuration will be used. Possible values are `never, fetch, endedNotFailed, and endedOrFailed`.

Query

`locked`

An optional boolean value that specifies whether the process should be locked to the engine node on which it was instantiated.

Body

The position of the `processParams` parameter depends on the HTTP method used. When using the POST method, the parameter needs to be supplied as a [Data Store](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#data-store) in the body of the request. For example, to pass a variable `foo` with the value `bar` to the process, all of the following Data Store representations would be viable.

##### Simple Data Store Format XML
`&lt;dataStore xmlns="http://www.infinica.com/datastore"&gt;
    &lt;entry name="foo" type="text/plain"&gt;
        &lt;value&gt;bar&lt;/value&gt;
    &lt;/entry&gt;
&lt;/dataStore&gt;`##### Standard Data Store Format XML
```
&lt;dataStore xmlns="http://www.infinica.com/datastore"&gt;
    &lt;values&gt;
        &lt;value id="1" type="text/plain"&gt;
            &lt;content&gt;bar&lt;/content&gt;
        &lt;/value&gt;
    &lt;/values&gt;
    &lt;entries&gt;
        &lt;entry name="foo"&gt;
            &lt;value&gt;1&lt;/value&gt;
        &lt;/entry&gt;
    &lt;/entries&gt;
&lt;/dataStore&gt;
```##### Simple Data Store Format JSON
```
{
  "dataStore": {
    "entry": {
      "name": "a",
      "type": "text/plain",
      "value": ["text"]
    }
  }
}
```##### Standard Data Store Format JSON
```
{"dataStore": {
    "values": {
      "value": [{
          "type": "text/plain",
          "id": "1",
          "content": {
            "value": ["bar"]
          }
      }]
    },
    "entries": {
      "entry": [{
          "name": "foo",
          "value": ["1"]
      }]
    }
  }
}
```When using the GET method, the parameter needs to be supplied in the query using the variable name prefixed with `in`. as the query parameter name.

`http://localhost:8080/infinica-process-engine/rest/run?processUri=process.ipd&amp;in.foo=bar`In order to pass a variable that contains a list of values, the query parameter needs to be specified once for each value.

`http://localhost:8080/infinica-process-

engine/rest/run?processUri=process.ipd&amp;in.foo=bar1&amp;in.foo=bar2`*Response*

Snapshot of the executed process.

#### setAttribute
**SOAP**

`setAttribute`

**REST**

`PUT /processes/{executionId}/attributes/{name}`

Sets an attribute for a process instance. Detailed information regarding attributes can be found in the Process Definition Reference.

*Parameters*

Name

Description

Position

`executionId`

ID of the target process.

Path

`name`

Attribute name.

Path

`value`

Attribute value. (Content-Type: text/plain)

Body

*Response*

No response.

#### setBreakpoint
**SOAP**

`setBreakpoint`

**REST**

`POST /processes/{executionId}/breakpoints/{elementId}`

`DELETE /processes/{executionId}/breakpoints/{elementId}`

Sets or deletes a breakpoint on the specified element. In synchronous mode (default), the call waits for the process to reach an inactive state before returning.

*Parameters*

`Name`

`Description`

`Position`

`executionId`

ID of the target process.

Path

`elementId`

Full ID of the element on which the breakpoint should be set (e.g. `root.start`).

Path

`timeout`

Timeout.

Query

`remove`

(Not for REST) Set to `true` to delete the breakpoint instead of setting it.

*Response*

Snapshot of the executed process.

#### setInstanceConstants
**SOAP**

`setInstanceConstants`

**REST**

`POST /processes/{executionId}/constants`

Sets process instance scoped constants. Detailed information regarding instance scoped constants can be found in the Process Definition Reference.

*Parameters*

`Name`

`Description`

`Position`

`executionId`

ID of the target process.

Path

`constants`

A data store containing the constants that should be set. See `processParams` parameter of run.

Body

*Response*

Snapshot of the executed process.

#### setLogSettings
**SOAP**

`setLogSettings`

**REST**

`POST /processes/{executionId}/logSettings`

Applies settings for Process Engine logging on a process instance.

*Parameters*

`Name`

`Description`

`Position`

`executionId`

ID of the target process.

Path

`diagnosticLevel`

Diagnostic log level.

Query

`dataLevel`

Data log level.

Query

`trace`

Whether to enable trace logging.

Query

*Response*

Snapshot of the executed process.

#### setOnline
**SOAP**

`setOnline`

**REST**

`PUT /processes/{executionId}/online`

Sets a process instance online or offline.

*Parameters*

Name

Description

Position

`executionId`

ID of the target processes.

Path

`online`

Boolean flag to set the process instance online `(true)` or offline `(false)`. (Content-Type: text/plain)

Body

`timeout`

Timeout.

Query

`peek`

Peek flag.

Query

`states`

A list of execution states to wait for.

Query

`waitOnline`

Whether to wait for the process to go online.

Query

*Response*

Snapshot of the executed process.

#### setOwner
**SOAP**

`setOwner`

**REST**

`PUT /processes/{executionId}/owner`

Sets the process owner.

*Parameters*

`Name`

`Description`

`Position`

executionId

ID of the target process.

Path

`owner`

Login name of the new process owner. (Content-Type:

text/plain)

Body

*Response*

Snapshot of the executed process.

#### **setPermissions**
**SOAP**

`setPermissions`

**REST**

`PUT /processes/{executionId}/permissions/{name}`

Sets permissions on a process instance for a specific role or principal.

*Parameters*

Name

Description

Position

`executionId`

ID of the target process.

Path

`name`

A role name or principal login name.

Path

`privileges`

Comma-separated list of names of the privileges to be granted for the specified role or principal. (Content-Type: text/plain)

Body

*Response*

Snapshot of the process with the set permissions.

#### startProcess
**SOAP**

`startProcess`

**REST**

`POST /processes/{executionId}/start`

Starts a newly instantiated process, or continues a paused one. The state of the process execution will be set to READY, causing Process Engine to pick it up for execution at the next possible instance.

By default, the operation waits until the process reaches an end state. This can be changed using the timeout and states parameters.

*Parameters*

Name

Description

Position

`executionId`

ID of the process execution that should be started.

Path

`processParams`

An optional set of parameters that will be passed to the process, in the form of a data store. See [run](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#run).

Body

`peek`

Peek flag.

Query

`timeout`

Timeout.

Query

`states`

A list of execution states to wait for.

Query

`waitOnline`

Whether to wait for the process to go online.

Query

`inspectPipeli ne`

If set, the entire process pipeline will be included in the returned process snapshot.

Query

`setOnline`

If set to true, the instance will be set to online in case it is currently offline. The default for this parameter depends on the timeout parameter. If the timeout is &lt;

0 (synchronous) the default is `true`, otherwise it is `false`.

Query

*Response*

Snapshot of the process with the set permissions.

#### terminateProcess
**SOAP**

`terminateProcess`

**REST**

`POST /processes/{executionId}/terminate`

Terminates a process by stopping it at the next opportunity. The process’s end state will be `terminated`. Since processes may react to the terminate event via an exception handler, a process can only be terminated when it is running. The `setOnline `flag can be used to make sure that the process is online.

The `kill `flag can be used to forcefully terminate processes that do not respond and therefore do not react to a regular termination call.

In synchronous mode (default), the call waits for the process to end before returning.

*Parameters*

Name

Description

Position

`executionId`

Process execution ID.

Path

`kill`

Optional boolean kill flag.

Query

`fail`

Optional boolean fail flag. If `true`, the process state is set to `FAILED` instead of `TERMINATED`.

Query

`message`

Optional string value for the process message.

Query

`timeout`

Timeout.

Query

`peek`

Peek flag.

Query

`states`

A list of execution states to wait for.

Query

`waitOnline`

Whether to wait for the process to go online.

Query

`inspectPipeli ne`

If set, the entire process pipeline will be included in the returned process snapshot.

Query

`setOnline`

Whether to set the process online as well.

Query

`stateChangeIn dex`

If specified, the wait operation will only react to process state changes with a *higher* state change index than specified. See `waitForProcess` for details.

Query

*Response*

Snapshot of the process with the set permissions.

#### updateCredentials
**SOAP**

`updateCredentials`

**REST**

`POST /processes/{executionId}/updateCredentials`

Update the process' current credentials to those provided by the caller with this operation.

*Response*

A snapshot of the process.

### Process State Queries
#### **getAttributes**
**SOAP**

`getAttributes`

**REST**

`GET /processes/{executionId}/attributes`

Returns attributes of a process instance. If a list of names is provided, the attributes identified by these names are retrieved, otherwise all attributes are returned. Detailed information regarding attributes can be found in the Process Definition Reference.

*Parameters*

Name

Description

Position

`executionId`

Process execution ID.

Path

`name`

Optional list of attribute names.

Query

*Response*

Snapshot of the process with the set permissions.

#### getInstanceConstants
**SOAP**

`getInstanceConstants`

**REST**

`GET /processes/{executionId}/constants`

Returns all constants set on a specific process instance.

*Parameters*

Name

Description

Position

`executionId`

Process execution ID.

Path

*Response*

Snapshot of the process with the set permissions.

#### getProcessSnapshot
**SOAP**

`getProcessSnapshot`

**REST**

`GET /processes/{executionId}`

Returns a current snapshot of the specified process.

*Parameters*

Name

Description

Position

`executionId`

Process execution ID.

Path

`peek`

Peek flag.

Query

`inspectPipeline`

If set, the entire process pipeline will be included in the returned process snapshot.

Query

*Response*

Snapshot of the process with the set permissions.

#### findExecutions
**SOAP**

`findExecutions`

**REST**

`POST /processes/query`

Lists the snapshots of all currently known process executions (including processes that have finished execution but have not yet been disposed), or those matching a set of specified filters.

The specified filters are used to select the target processes. If multiple values are provided for one filter (e.g. more than one execution ID), a process will be chosen as a target process if it matches *one* of the specified values. If multiple separate filters are provided (e.g. execution ID and owner), a process must match one value for each provided filter to be chosen.

Once the target process instances have been selected, they will be returned as a list of snapshots. If the target processes include processes which the user may not see due to insufficient privileges, they will be excluded from the returned list.

*Parameters*

Name

Description

Position

`query`

The query. For REST, the query must be provided as the request body.

Body

`inspectPipeline`

If set, the entire process pipelines will be included in the returned process snapshots.

Query

*Response*

Snapshot of the process with the set permissions.

#### validate
**SOAP**

`validate`

**REST**

`POST /validate`

Validates a specific process definition. If the process definition is invalid (i.e. it cannot be loaded and instantiated correctly), an exception is thrown. Otherwise, some information about the process definition is returned.

If the `process `parameter is specified, the process definition will not be read from the specified URI, or the cache, but the provided IPD will be validated instead. The Process Engine will still use the specified `processUri `as the process base URI, e.g. when resolving relative URIs within the process.

*Parameters*

Name

Description

Position

`processUri`

URI (or path) to the process definition that should be validated.

Query

`cache`

Whether the process definition may be read from the cache, if it has already been cached. Defaults to `true` if caching is enabled. Does not have an effect if an IPD stream is provided in the `process` parameter.

Query

`process`

Optional IPD stream. (Content-Type: multipart/formdata)

Body

*Response*

Snapshot of the process with the set permissions.

#### waitForProcess
**SOAP**

`waitForProcess`

**REST**

`GET /processes/{executionId}/wait`

Waits for the specified process to reach a specific state. By default, the operation waits for any end state. When called with a `timeout `of 0, this operation is effectively identical to [getProcessSnapshot](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#getProcessSnapshot).

##### NOTE
*waitForProcess* has been replaced by the more robust process watcher system (see [Process Watchers](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#process-watchers)). Currently, the old operation is still available, but it is recommended to use process watchers instead.

*Parameters*

`Name`

Description

Position

`executionId`

Process execution ID.

Path

`timeout`

Timeout.

Query

`peek`

Peek flag.

Query

`afterTimestamp`

If specified, the operation will only react to process state changes that happen on or after this timestamp.

Query

`inspectPipeline`

If set, the entire process pipeline will be included in the returned process snapshot.

Query

`states`

A list of execution states to wait for.

Query

`waitOnline`

Whether to wait for the process to go online.

Query

`stateChangeIndex`

If specified, the operation will only react to process state changes with a *higher* state change index than specified. Each process snapshot includes the process' current state change index. Each process state change increases this index. This parameter can be used to e.g. wait for a currently `WAITING` process to become `WAITING` *again*, by waiting for it to be `WAITING` with a higher state change index than its current one.

Query

*Response*

Snapshot of the process with the set permissions.

### Process Watchers
Process watchers can be used to monitor state changes of a process, even while the client is not active. The client first creates a watcher, specifying the specific state for which the watcher should wait. The watcher will then automatically be updated when the process reaches the desired state, or an end state. The client can use the returned watcher ID to periodically get the watcher’s state. When the watcher is no longer needed, it should be deleted by the client.

#### createWatcher
**SOAP**

`createWatcher`

**REST**

`POST /watchers`

Creates a new process watcher.

*Parameters*

`Name`

Description

Position

`executionId`

Execution ID of the process that should be watched. Required.

Query

`groupId`

An optional custom group ID for the watcher. Not yet used.

Query

`expectedState`

One or more process execution states for which the watcher should wait (optional).

Query

`expectedOnlin eState`

The expected online state `(true or false`) for which the watcher should wait (optional).

expectedStateCha ngeIndex

`The expected online state change index (an integer value) for which the watcher should wait (optional). Note: The watcher will wait for the process to reach a state change index higher than the specified value.`

expectedHealthState

One or more process health states for which the watcher should wait (optional).

`Query`

expectedElement

The full ID of a process element for which the watcher should wait (optional).

`Query`

peek

Unless this is `true`, the watcher will monitor the process without peeking and may trigger auto disposal when the process reaches an end state.

`Query`

inspectPipeline

Whether the pipeline of the process should be captured by the watcher.

Defaults to `true`.

#### getWatcher
**SOAP**

`getWatcher`

**REST**

`GET /watcher/{watcherId}`

Gets the current state of a process watcher, optionally waiting for the watcher to finish first.

*Parameters*

`Name`

Description

Position

`watcherId`

ID of the requested watcher.

Path

`finish`

Whether the watcher should be finished after the timeout, even if it did the process did not meet its requirements. If this is true, the current process state will be fetched at the end of the timeout and set as the watcher’s finish state.

Query

`timeout`

If this is specified, the operation will wait for up to the specified number of milliseconds for the watcher to finish before returning.

Query

`updateTimeout`

*Deprecated. Do not use.*

Query

#### deleteWatcher
**SOAP**

`deleteWatcher`

**REST**

`DELETE /watcher/{watcherId}`

Deletes a process watcher.

*Response*

A boolean value; `true` if the watcher was deleted, `false` otherwise (usually because it did not exist).

### Administration
#### **clearCache**
**SOAP**

clearCache

**REST**

POST /clearCache

Clears the Process Engine caches.

*Parameters*

Name

Description

Position

`cachePaths`

An optional list of cache paths, indicating the caches, or individual cache entries, that should be cleared. If not specified, all caches are cleared.

Query

#### getBrokerUri
**SOAP**

getBrokerUri

**REST**

GET /brokerUrl

Returns the URI of the message broker, if one is configured for this Process Engine.

*Parameters*

No parameters.

*Response*

URI of the message broker, if one is configured for the Process Engine.

#### getConstants
**SOAP**

getConstants

**REST**

GET /constants

Returns all public constants defined in the Process Engine or optionally a specific partition.

*Parameters*

Name

Description

Position

path

Optional partition path.

Query

*Response*

A data store containing the requested constants.

#### getFeatures
**SOAP**

getFeatures

**REST**

GET /features

Reports the available features and their states. Features denote certain Process Engine functionality that is only available when the feature is active. For example, the instantiate feature is required for instantiating new processes and may not be available instantly when API becomes accessible during startup, as the required services are only started during the warm-up phase.

*Parameters*

No parameters.

*Response*

List of features.

#### getMaintenanceLevel
**SOAP**

getMaintenanceLevel

**REST**

GET /maintenance

Returns the process engine’s current maintenance level.

*Parameters*

No parameters.

*Response*

The current maintenance level.

#### getModules
**SOAP**

getModules

**REST**

GET /modules

Lists all modules installed in the Process Engine.

*Parameters*

Name

Description

Position

`lang`

Optional language.

Query

*Response*

A data structure describing all available modules.

#### getNodeState
**SOAP**

getNodeState

**REST**

GET /nodeState

Returns information about the current state of the Process Engine, specifically (in a cluster) of the Process Engine node which handled the operation.

*Parameters*

No parameters.

*Response*

Node state.

#### getNodeStates
**SOAP**

getNodeStates

**REST**

GET /nodeStates

Returns information about the current states of all the Process Engine nodes in the cluster.

*Parameters*

No parameters.

*Response*

Node states.

#### getTaskManagerUrl
**SOAP**

getTaskManagerUrl

**REST**

GET /taskManagerUrl

Returns the URL of the Task Manager used by the Process Engine, if one has been configured.

*Parameters*

No parameters.

*Response*

Task Manager URL.

#### listProcessDefinitions
**SOAP**

listProcessDefinitions

**REST**

GET /processDefinitions

Not yet implemented.

#### listServices
**SOAP**

listServices

**REST**

GET /services

Returns a list of all registered Process Engine services and their states.

> Note

Services (as opposed to service processes) are the internal system services of the Process Engine. They are initialised and started during the startup phase and are used internally by the Process Engine. Some services are only enabled if certain settings are configured, e.g. the tasks service will not be enabled if no Task Manager has been configured.

*Parameters*

No parameters.

*Response*

Service states.

#### setEngineOnline
**SOAP**

setEngineOnline

**REST**

POST /setOnline

Sets the Process Engine online or offline.

*Parameters*

Name

Description

Position

`online`

Whether to set the Process Engine online (`true`) or offline (`false`).

Query

`param`

Only relevant for clustered Process Engines. Specifies whether the operation should apply to all nodes (`all`), only the receiving node (`self`), or to those nodes listed with the node parameter.

Query

`node`

A list of Process Engine node IDs. Only relevant if `param` has been set to `specified`.

Query

*Response*

No response.

#### setMaintenanceLevel
**SOAP**

setMaintenanceLevel

**REST**

PUT /maintenance

Sets the Process Engine’s maintenance level. The specified level must have been set up in the Process Engine configuration.

*Parameters*

Name

Description

Position

`levelId`

ID of the new maintenance level. (Content-Type:

text/plain)

Body

*Response*

No response.

#### uncacheProcesses
**SOAP**

uncacheProcesses

**REST**

POST /uncacheProcesses

Removes cached process instances and executions corresponding to the filter parameters. This operation can only be executed if a storage is configured. Individual instances/executions are only removed from the cache if they are persisted in the storage and not running. The main purpose of this operation is to free up memory when there are many inactive processes.

> **Caution**

Removing instances from the cache means that they need to be restored once they are needed again which comes with a performance overhead.

*Parameters*

Name

Description

Position

`executionId`

IDs of the target processes.

Query

`owner`

Owners of the target processes.

Query

`processUri`

Process definition URIs of the target processes.

Query

`states`

States of the target processes.

Query

`health`

Health states of the target processes.

Query

`timestamp`

If specified, only processes at least as old (or older) than this timestamp will be selected. The age of a process is taken from its finished timestamp, or if the process has not yet reached an end states, from its creation timestamp.

Query

`engineId`

IDs of the Process Engines of the target processes.

Query

*Response*

No response.

#### version
**SOAP**

version

**REST**

GET /version

Returns the exact version of the Process Engine.

*Parameters*

No parameters.

*Response*

The version of the Process Engine.

#### waitForNoRunningProcesses
**SOAP**

waitForNoRunningProcesses

**REST**

GET /waitForNoRunningProcesses

Waits until there are no more processes running for this Process Engine instance or the timeout is reached. Only processes in the RUNNING state are counted. This is useful to wait until an offline Process Engine has stopped actively executing processes so it can be shut down safely.

*Parameters*

Name

Description

Position

`timeout`

Timeout.

Query

*Response*

The number of remaining running processes.

### **Service Management **
#### **getServiceSnapshot**
**SOAP**

getServiceSnapshot

**REST**

GET /services/{*serviceId*}

Returns a current snapshot of the specified service process.

*Parameters*

Name

Description

Position

`serviceId`

Service ID.

Path

`peek`

Peek flag.

Query

`inspectPipeli ne`

If set, the entire process pipeline will be included in the returned process snapshot. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startprocess).

Query

*Response*

Snapshot of the service process, or nothing if the service process has not been started.

#### listServices
**SOAP**

`listServices`

**REST**

`GET /services`

Lists the available services configured for this Process Engine, regardless of whether they are currently running.

*Parameters*

No parameters.

*Response*

A list of service configurations.

#### startService
**SOAP**

`startService`

**REST**

`POST /services/{serviceId}/start`

Starts a service process configured for this Process Engine. If the service process has already been started, its current state is returned.

*Parameters*

Name

Description

Position

`serviceId`

Service ID.

Path

`peek`

Peek flag.

Query

`inspectPipeli ne`

If set, the entire process pipeline will be included in the returned process snapshot. See [startProcess](/doxee-platform/docs/6-6-process-engine-user-guide-process-engine-api-1#startProcess).

Query

*Response*

Snapshot of the service process.

### Cluster Control
#### **clusterConnect**
**SOAP**

`clusterConnect`

**REST**

`POST /cluster/connect`

Connects the Process Engine node to the configured cluster. It will try to establish a connection to the Zookeeper server and if successful, send a connect request to the master. This operation will only work if the Process Engine is configured for clustering and is currently not connected to the cluster.

*Parameters*

Name

Description

Position

`timeout`

Maximum time to wait for the operation to complete in milliseconds. A value of -1 means that the operation will wait synchronously for the connection to be established or refused.

Query

*Response*

New Node State of this node in the cluster after the connect operation.

#### clusterDisconnect
**SOAP**

`clusterDisconnect`

**REST**

`POST /cluster/disconnect`

Disconnects the Process Engine node from the cluster it belongs to. It will disconnect from the Zookeeper server and set the connection state to disconnected. This operation will only work if the Process Engine is configured for clustering and is currently not connected to the cluster.

*Parameters*

Name

Description

Position

`timeout`

Maximum time to wait for processes to complete executing on this node before disconnecting.

Query

*Response*

New Node State of this node in the cluster after the disconnect operation.

### Diagnostic Operations
#### checkSanity
**SOAP**

`checkSanity`

**REST**

`GET /diagnostic/sanity`

Runs a series of checks for verifying the sanity and consistency of internal Process Engine data. This includes checks on process instances, wait states, tasks, in-memory data, persistent storages and ZNodes in Zookeeper. The operation returns a report containing messages for any potential problems in the reviewed information. If the report is empty, no problems were detected. The standard checks are:

- zookeeperWaitState: Checks consistency between Zookeeper ZNodes and wait state storage.

- zookeeperProcess: Checks consistency between Zookeeper ZNodes and process instance storage.

- signal: Checks for obsolete signals.

- waitState: Checks consistency between wait states and process instances.

- execution: Checks consistency between process execution data and process instances.

- taskPayload: Checks consistency between task payloads and tasks.

- zookeeperWatcher: Checks for obsolete watchers.

- waiter: Checks for obsolete waiters.

These standard checks are executed if no checks are specified via the `checks` parameter. The following non-standard checks are only executed when included in the parameter:

- noRunning: Checks whether there is any leftover execution data from previous process executions including storage execution data, wait states, threads or ZNodes.

- cleanState: Checks the same as noRunning but also includes a check for leftover process instances in the cache or the storage.

*Parameters*

Name

Description

Position

`checks`

A list of IDs for sanity checks which should be run. If no checks are provided, the operation will run all standard checks.

Query

*Response*

Sanity Report listing potential problems.

#### getTelemetryData
**SOAP**

`getTelemetryData`

**REST**

`GET /diagnostic/telemetry`

Fetches the current telemetry data. Telemetry data contains internal information from the

Process Engine, for example the content of the persistent storages, information about process instances, wait states or tasks and the ZNodes on the Zookeeper server, if available. All these informations have individual data types. For querying only certain types, use the `types` parameter. The available types are:

- PROCESS_INSTANCE: The process instances in the storage.

- CACHED_PROCESS_INSTANCE: The process instances currently cached on the Process Engine node.

- PROCESS_EXECUTION: The process execution data in the storage.

- SIGNAL: The process signals in the storage.

- THREAD_POOL: The thread pools available on this node, including the IDs of all process instances currently running in them.

- WAITSTATE: The wait states in the wait state storage

- TASK: Task telemetry data retrieved from the Task Manager, if configured.

- WAITERS: Lists the number of requests waiting for each process instance.

- CACHE: Usage data for all Process Engine caches.

- VOLATILE_INSTANCES: The current volatile process instances.

*Parameters*

Name

Description

Position

`types`

A set of telemetry data types. The operation will fetch only data for the provided types. If no types are provided, the operation will fetch all standard types.

Query

*Response*

Telemetry data.

#### garbageCollect
**SOAP**

`garbageCollect`

**REST**

`GET /diagnostic/garbageCollect`

This operation blocks until all dispose and cleanup tasks in the Process Engine are completed or the timeout is reached.

*Parameters*

Name

Description

Position

`timeout`

Maximum time to wait for the operation to complete in milliseconds. A value of -1 means that the operation will wait synchronously.

Query

*Response*

None

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}