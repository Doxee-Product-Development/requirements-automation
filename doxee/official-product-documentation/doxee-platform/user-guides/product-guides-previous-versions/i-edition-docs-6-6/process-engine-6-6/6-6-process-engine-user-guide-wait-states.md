---
id: "93340ddf-f1d8-4bec-8037-e1a3a6aa0843"
title: "Wait States"
slug: "6-6-process-engine-user-guide-wait-states"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-06T17:05:13.099Z"
modified_at: "2025-08-19T16:47:32.49Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-wait-states"
synced_at: "2026-01-28T21:01:17.595Z"
checksum: "c3614d9688e59f03"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Wait states provide a mechanism for clients, e.g. Doxee processes, to wait for the occurrence of a specific event. Different wait state types are defined for different events, e.g. for timeouts, incoming emails or new files in a directory. A payload allows clients to stop execution while waiting for the event and automatically resuming their task as soon as the event has occurred. The wait state may also communicate data to the client, e.g. the contents of a new email or the URL of a newly created file.

In the Process Engine, wait states are used by including wait elements in the process. The wait state type is set as element attribute type. Any additional information which might be required can be provided via mappings. The result is always returned as an XML document which can be returned to the process via output mappings. Each wait state type has its own structure for the result XML. The wait state lifecycle is managed by the Process Engine.

## Chaining Wait States
By default, a wait state is registered by a wait element and automatically unregistered once the process resumes. However, sometimes it is necessary to use the same wait state multiple times, e.g. when repeatedly querying the same directory for new files.

In this case, the wait state can be preserved by setting the wait element’s keepWaitState parameter to `true` using the input mappings. When resuming, the element will return a waitStateId. The wait state can then be reused by setting a wait element’s waitStateId parameter via the input mappings (it will still unregister the wait state after completion unless keepWaitState is set again).

This can be especially useful for wait states that carry state, e.g. a file wait state which is aware of files that were already in the monitored directory. Reusing the same wait state makes sure that later calls still know about both the files that existed before the wait state was registered, as well as those files already reported by the wait state. The wait state will still be able to recognised files that were added while it was inactive.

When a wait states is reused and started again, its credentials and base URL will be updated to reflect the current state of the process.

## Parameters
Each wait state type needs different input parameters for controlling their behaviour. They are provided via input mappings on the wait element. These parameters are listed and explained for the individual types in the subsequent chapters. Regardless of the type there are also certain input parameters which control the wait state to be used and output parameters providing information about the wait state and its outcome. These are always applicable. They are described below.

#### Inputs 
**keepWaitState**

Boolean flag for defining whether the wait state should be kept or removed after it is done. Default is false.

**waitStateId**

The ID for an already existing wait state which should be reused.

#### Outputs
**result**

The type-dependent result of the wait state as an XML document.

**waitStateId**

The ID of the wait state used by the wait element. Only available if the wait state has been kept by providing the keepWaitState input parameter.

**error**

In case an error happened while the wait state was executed, this variable provides the error message as plain text. If the wait state finished without errors, this output will be null.

**interrupted**

A boolean variable which has the value `false` when the wait state properly finished waiting, `true` if it was interrupted for some reason.

## Supported Wait State Types
Doxee provides these wait state types:

- timeout

- file

- email

- process

- message

The following sections describe each of these types along with their supported parameters and outputs.

### timeout
A timeout wait state waits for a specific interval before triggering the wait state.

The following parameter is supported:

**milliseconds**

Interval, in milliseconds, until the wait state should stop waiting.

The timeout wait state provides no output.

### file
The file wait state monitors a directory and triggers the wait state when a new file is found, or an existing file is changed.

The following parameters are supported:

**interval**

The interval, in milliseconds, between two checks for new files.

**directory**

The path or URL of the directory that should be monitored.

**file-pattern**

An optional regular expression defining the names or paths (depends on file-patternfull-path parameter) of files that should be recognised by the wait state.

**file-pattern-full-path**

A boolean value specifying if the file-pattern parameter should identify the full path of the file or just the name. Default is `false`.

**find-existing-files**

A boolean value specifying whether files already in the directory when the wait state is registered should also be recognised as new files by the wait state. Defaults to `false`.

**recursive**

A boolean value specifying if the wait state should search recursivley within subdirectories of the given search directory. Default is `false`.

**directory-pattern**

An optional regular expression defining the names or paths (depends on directorypattern-full-path parameter) of directories that should be searched for files. Only makes sense if the recursive parameter is set to true.

**directory-pattern-full-path**

A boolean value specifying if the directory-pattern parameter should identify the full path of the directory or just the name. Default is `false`.

**find-directories**

A boolean value specifying if the wait state should consider directories as files to be found or not. Default is `false`.

**limit**

Specifies the maximum number of files the wait state should find and return in the result xml. If this number is set to 0, there will be no limit and all files are returned. Default is 0.

**relative**

A boolean value specifying if the URLs for the found files in the result xml should be relative to the directory specified by the directory parameter or absolute. Default is `false`.

When the wait state finds one or more files matching the specified pattern while polling the directory, the wait state is triggered and a list of the newly found files is provided as the output. The wait state keeps track of all already known files so that if it is reactivated at a later time, no files that were previously reported trigger the wait state again. However, files that were added while the wait state was inactive will be recognised and immediately trigger the wait state once it is reactivated.

The output of the file wait state has the following format:

`&lt;files&gt;
  &lt;file url="..." /&gt;
&lt;/files&gt;`**file (1..n)**

Each new file is represented by a separate `file` entry in the output.

file (1..n)/**url (1)**

The URL of the file.

### email
The email wait state monitors an email account via the POP protocol and triggers the wait state when a new mail arrives.

The following parameters are supported:

**interval**

The interval, in milliseconds, between two checks for new emails.

**host**

The host name or IP of the POP server.

**port**

The port of POP server.

**user**

User name for accessing the server.

**password**

Password for accessing the server.

**ssl-encryption**

Whether to use SSL encryption for accessing the server. Defaults to `false`.

**new**

An optional boolean flag that defines whether the wait state only reacts to emails that were sent after the wait state was registered. Defaults to `true`.

**address**

An optional regular expression defining what 'from' address an email must have to be recognised by the wait state.

**subject**

An optional regular expression defining what subject an email must have to be recognised by the wait state.

**content**

An optional regular expression defining what content an email must have to be recognised by the wait state.

**contentTypes**

An optional set of content types that should be included in the returned email content, and used to filter emails by content if content is specified. Defaults to `text/plain` and `text/html`.

**filterInAttachments**

If this is `true`, the content filter will also be applied to attachments (as long as they match the configured content types), and the content of attachments of matching types will be included in the returned email content. Defaults to `false`.

**alwaysFetchContent**

If this is `true`, the content of emails will be fetched before the address, subject, and content filters are evaluated. This guarantees that POP servers recognise emails as 'read' regardless of which filters did or did not match. If the `new` flag is `true`, the email date is always checked before the content is fetched, so that older emails are left untouched. Defaults to `false`.

When the wait state finds one or more emails matching the specified patterns while polling the server, the wait state is triggered and a list containing the newly found emails is provided as the output. The wait state does *not* keep track of emails it has already handled. It is therefore *not* recommended to use the same email wait state more than once.

The output of an email wait state is an XML structure containing all emails that have been found by the wait state:

`&lt;emails&gt;
  &lt;email subject="..."&gt;
    &lt;from&gt;...&lt;/from&gt;
    &lt;to&gt;...&lt;/to&gt;
    &lt;cc&gt;...&lt;/cc&gt;
    &lt;text&gt;...&lt;/text&gt;
    &lt;html&gt;...&lt;/html&gt;
    &lt;attachment filename="..." contentType="..."&gt;...&lt;/attachment&gt;
  &lt;/email&gt;
&lt;/emails&gt;`**email (1..n)**

Each new email is represented by a separate `email` entry in the output.

email (1..n)/**subject (1)**

The email subject.

email (1..n)/**from (0..n)**

The email’s 'from' addresses.

email (1..n)/**to (0..n)**

The email’s 'to' addresses.

email (1..n)/**cc (0..n)**

The email’s 'cc' addresses.

email (1..n)/**text (0..n)**

The email’s plain text content blocks.

email (1..n)/**html (0..n)**

The email’s HTML content blocks.

email (1..n)/**attachment (0..n)**

Email attachments.

email (1..n)/attachment (0..n)/**filename (0..1)**

Attachment file name.

email (1..n)/attachment (0..n)/**contentType (0..1)**

Attachment content type.

email (1..n)/attachment (0..n)/**Content (1)**

Attachment content, base 64 encoded.

### process
The process wait state waits for a process running on the same or a different Process Engine to reach a certain state. In the background it uses a process watcher to monitor the procss on the specified Engine.

The process wait state can also instantiate and start a new process, which it then waits for. If the timeout parameter is set to 0, it starts an asynchronous process execution and returns immediately. The wait state covers all the functionality previously provided by the executeProcess activity.

The following parameters are supported:

**baseUri**

The base URI of the Process Engine in which the process to wait for is supposed to run. If not provided, the Engine which created the wait state will be used.

**executionId**

The execution ID of the process instance to wait for. If this is not provided, the wait state will try to instantiate a process and the processUri parameter must be provided.

**processUri**

The URI of the process to instantiate. Only relevant if no executionId is provided.

**timeout**

The maximum time to wait in milliseconds. If the process does not return until the timeout is reached, the waitstate is triggered. If no timeout is provided or the value is -1, it will wait indefinitely.

**states**

The process execution states which should trigger the waitstate. By default it waits for the process to end. If the process reaches an end state the waitstate will always be triggered, regardless of the value of this parameter.

**stateChangeIndex**

The number of state changes which must have occurred at least to trigger the wait state. Only applicable if the states parameter is set and contains states which are not end states.

**timestamp**

If set, only state changes which happened after the provided timestamp will trigger the wait state. Only applicable if the states parameter is set and contains states which are not end states.

**inspectPipeline**

A boolean flag specifying whether the result pipeline of the process execution should be included in the wait state result. The default is true.

**peek**

Boolean flag which specifies whether the peek parameter should be set for the Process Engine call. Default is false.

**threadPool**

Thread Pool for executing a process. Only relevant if no executionId is provided.

**cache**

Cache flag for executing a process. Only relevant if no executionId is provided.

**start**

Boolean flag which can be set to true if the process instance identified by the executionId is not running yet and should be started.

**runAtomic**

By default, if the wait state instantiates and starts a new process, it does so via separate calls to the instantiate and startProcess operations. If this boolean flag is set to true, such processes are instead run with a single run call. The downside is that if during waiting the wait state is temporarily interrupted, it has not yet received an execution ID for its new process instance, and when the wait state is resumed it will start another process instance with a new run call.

**paramPrefix**

A prefix identifying parameters which should be passed when executing a process. Can be used for passing process parameters with the same name as one of the parameters of the wait state. The prefix is stripped away before passing the parameter. Only relevant if the process is started by the wait state.

*****

If the process is started by the wait state, any additional parameters will be passed as input parameters when starting the process.

The output of the process wait state consists of an XML representation of the process instance snapshot returned by the API call to the Process Engine. For the structure of this snapshot see [Process Snapshot](/doxee-platform/docs/appendix-c-process-engine-api#process-snapshot).

### message
The message wait state waits for a JMS message to arrive via a certain message queue or topic.

The message wait state is only available if the *messaging* Process Engine module is present.

The following parameters are supported:

**messageClient**

The XML configuration for a local message client which will try to connect to a JMS messaging server. Must contain a default message consumer. The structure of the XML configuration is described in the Process Engine Administration Reference in the configuration chapter under Message configuration.

**type**

An optional type string specifying the type of message which should trigger the wait state. Can be one of text, byte, map or stream.

**contentPattern**

An optional regular expression for filtering text messages by content. The wait state is only triggered if the pattern matches the text. If this parameter is provided but a received message is not a text message, the wait state is not triggered.

**properties**

An optional list of property names for filtering messages by properties. The wait state is only triggered if a property exists for each provided name.

**number**

Optional number of messages the wait state should wait for. The wait state is only triggered when enough messages have arrived. The provided number is also the number of messages returned in the result. If the number is -1 The wait state will fire as soon as a message arrives but will return any additional messages it receives before closing the message client. The default is 1.

The output of the message wait state is a list of received messages. The XML structure is described below:

`&lt;messageResultList&gt;
  &lt;message timestamp="...", messageId="...", type="..."&gt;
    &lt;header&gt;
        &lt;JMSTimestamp&gt;...&lt;/JMSTimestamp&gt;
        &lt;JMSMessageID&gt;...&lt;/JMSMessageID&gt;
        &lt;JMSType&gt;...&lt;/JMSType&gt;
        &lt;JMSDestination&gt;...&lt;/JMSDestination&gt;
        &lt;JMSDeliveryMode&gt;...&lt;/JMSDeliveryMode&gt;
        &lt;JMSCorrelationID&gt;...&lt;/JMSCorrelationID&gt;
        &lt;JMSReplyTo&gt;...&lt;/JMSReplyTo&gt;
        &lt;JMSDeliveryTime&gt;...&lt;/JMSDeliveryTime&gt;
        &lt;JMSPriority&gt;...&lt;/JMSPriority&gt;
    &lt;/header&gt;
    &lt;properties&gt;...&lt;/properties&gt;
    &lt;text&gt;...&lt;/text&gt;
    &lt;xml&gt;...&lt;/xml&gt;
    &lt;binary&gt;...&lt;/binary&gt;
    &lt;map&gt;...&lt;/map&gt;
  &lt;/message&gt;
&lt;/messageResultList&gt;`**message (1..n)**

Each received message is represented by a `message` node.

message (1..n)/**timestamp (1)**

The JMS timestamp, set when the message was received by the server.

message (1..n)/**messageId (1)**

Unique JMS message id set by the server.

message (1..n)/**type (1)**

Message type, must be one of text, byte, map or stream.

message (1..n)/**header (1)**

Contains standard JMS Header properties if they are present in the received message.

message (1..n)/**properties (1)**

Contains a map of key-value pairs corresponding to the properties of the message. The keys are the property names as strings, values are the property values with different types.

message (1..n)/**text (0..1)**

Text content of the message. Only available if type is text.

message (1..n)/**xml (0..1)**

Arbitrary XML structure provided as text of the message. Only available if type is text and the text content is valid XML.

message (1..n)/**binary (0..1)**

Binary content of the message, encoded as Base64 string. Only available if type is byte.

message (1..n)/**map (0..1)**

Map of key-value pairs contained in the message. Only available if type is map or stream.

If the connection to the JMS messaging server is lost, the client will try to reconnect based on the *reconnectAttempts* and *reconnectInterval* configured in the message client configuration XML. How to configure these values is described in the Process Engine Administration Reference in the configuration chapter under Message configuration. If no *reconnectAttempts *are configured or all the attempts were unsuccessful, the Wait State will wake up and the Process will continue. No exception will be thrown, but the result of the Message Wait State will be empty, the output parameter *interrupted* will be *true* and the output parameter *error *will contain an error message related to the connection loss.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}