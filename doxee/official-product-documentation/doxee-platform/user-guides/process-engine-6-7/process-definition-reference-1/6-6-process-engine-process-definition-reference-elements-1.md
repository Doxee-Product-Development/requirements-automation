---
id: "27a8222d-08e9-4f4b-8073-dd752394a91d"
title: "Elements"
slug: "6-6-process-engine-process-definition-reference-elements-1"
category: "Process Definition Reference"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Process Definition Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:05.298Z"
modified_at: "2026-01-07T14:04:42.012Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-process-definition-reference-elements-1"
synced_at: "2026-01-28T20:54:57.469Z"
checksum: "cebc0e3a2d5ac756"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

## Common Attributes
Certain attributes apply to several or all components. They are listed below.

id

Unique ID of the component. IDs are hierarchical. Child element IDs are automatically prefixed with their parent’s IDs followed by a dot (.). Therefore, multiple elements in different scopes may use the same local IDs - their full IDs will still be unique.

A component always has an ID. If the process definition does not specify one, the ID is automatically generated when loading the process definition.

name

Optional human readable name of the component. Does not have to be unique.

Visual representations of a process use the name attributes to label the components. If a component does not have a name, its ID is displayed instead.

condition

Optional attribute on elements that defines an XPath expression. If the condition evaluates to `false` at runtime when the element is about to be executed, its execution is skipped and execution continues with its successor.

## Activity Element
![](data:image/png;base64,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)Figure 1. Activity Element

An activity element references a specific activity which is called when the activity element is executed at runtime.

The element defines a number of input and output mappings. The input mappings are executed to map data from the process pipeline to the activity’s inputs before calling the activity. The output mappings are executed after the activity to map its outputs back to the process pipeline.

`&lt;decision id="..." name="..." descriptor="..." condition="..."&gt;
  &lt;logBefore... /&gt;
  &lt;inputs&gt;
    ...
  &lt;/inputs&gt;
  &lt;outputs&gt;
    ...
  &lt;/outputs&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/decision&gt;`**descriptor (1)**

The ID of the activity that should be executed when handling the activity element.

**logBefore (0..1)**

Diagnostic log message that is written before the activity is executed.

**inputs (0..1)**

Contains a number (0..n) of input mappings. 

**outputs (0..1)**

Contains a number (0..n) of output mappings. 

**dataLog (0..1)**

Data log, written after the activity is executed.

**logAfter (0..1)**

Diagnostic log message that is written after the activity is executed.

## Decision
##### decision
![](data:image/png;base64,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)*Figure 2. Decision*

Unlike other elements, a decision has multiple outgoing connections. Each connection has a corresponding condition defined on the decision element. At runtime, the conditions' XPath expressions are evaluated in definition order until a matching condition is found. The matching condition’s connection is then followed to continue process execution.

Each decision must define exactly one default condition without an XPath expression. This condition is used when none of the other conditions' XPath expressions evaluates to true.

`&lt;decision id="..." name="..." condition="..."&gt;
  &lt;logBefore... /&gt;
  &lt;condition&gt;...&lt;/condition&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/decision&gt;`**logBefore (0..1)**

Diagnostic log message that is written before the decision is evaluated.

**condition (0..n)**

A number of conditions (see [Condition](/doxee-platform/docs/6-6-process-engine-process-definition-reference-elements-1#condition)).

**dataLog (0..1)**

Data log, written after the decision is evaluated.

**logAfter (0..1)**

Diagnostic log message that is written after the decision is evaluated.

### Condition
`&lt;condition connection="..." expression=".." /&gt;`**connection (1)**

The ID of the connection associated with the condition.

**expression (0..1)**

The condition’s XPath expression. A condition’s connection is taken when its expression evaluates to `true`.

One condition per decision should have no expression. This is the default condition that is used when no other condition returns `true`. Only the default condition can have no expression.

> Note

If no default condition is specified for a decision, a warning will be returned when the process definition is validated. The process definition can be instantiated without validation. In this case, the decision will throw an exception if a default condition is required (because non of the other conditions matched) but is missing.

## End Element
![](data:image/png;base64,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)*Figure 3. End Element*

An end element marks the end of a process, or a sub structure (e.g. a group or a loop). When a process’s end element is encountered at runtime, the process ends and the end element’s mappings are used to map data from the process pipeline back to the caller.

When a sub structure’s end element is encountered at runtime, its mappings are used to map data from the sub structure’s pipeline back to the outer pipeline. Process execution then continues along the outgoing connection of the end elements' parent element.

`&lt;endElement id="..." name="..."&gt;
  &lt;log... /&gt;
  &lt;mapping&gt;...&lt;/mapping&gt;
&lt;/endElement&gt;`**log (0..1)**

Diagnostic log message that is written before the end element is executed.

**mapping (0..n)**

A number of [mappings](/doxee-platform/docs/chapter-5-mappings).

## Group
![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAADICAYAAAAEJfNmAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAsbSURBVHhe7d3fa5f1/8fxx3rr3Ob8sUjTOrDsoAVGP8ykjMAICYmoUDHwRIJ+edB/UBB0Eh2E0YEURESGZZAEIiMpUjO3pX42Lc1whJY/QtTGnFO39/fgW/u6dxby6Vv5fnG7gTCv6/mS94ncr+t6X7uuhmq1Wg0AUJSGarVaXb9+fe12AKDOLFmyZPTnq8bsAQCKMOYM/o033khDQ0MaGxvz31y5P3fuXFatWlW7GQD4B/zhGfxVV/3vX6dOnZopU6Zc9p+pU6dm0qRJaWhouPifAwD+JWPO4N96660MDw/n6aefrp27LGvWrPmv1wIAf80fnsFf7mX5S8319/fXbgIA/iWXfZPd+fPn093dnZ6eHpfiAeAKd9mBHxwczN69e7Nt27baXcA/6MSJE9m6dWu6u7tz8ODBdHZ25ty5czl06FA6Oztz7NixbNu2LcPDwxkeHk5vb28+//zzdHZ2ZmBgIElG1124cCFJ0tnZmQMHDiRJvvnmm+zatSvHjh3Lli1bsnv37oyMjIz5DMCV77ID39LSkqGhoVQqlTHbL3W5Hvh79Pf3Z/369dm/f38OHz6cTZs2paurK+fOncvhw4fT1dWVjRs3Zt++fRkeHs6GDRuyZcuW/PLLL+nt7c3777+fgYGB9PX1paurazTwXV1dYwK/Y8eOfPbZZzly5Ei2bduW7du313wS4Er3p4H/7bL8rl270t3dnZGRkYyMjKS3tzc7d+50uR7+Yfv378+FCxeyaNGiPProo5k9e3btSObPn58nn3wyJ06cyJEjRzJ37tw88sgjWbRoUYaGhrJv377aJZf0+OOPZ+nSpWlubk5fX1/tbuAK96eBP3PmTPbv35+enp7RM4KRkZHs3Lkzvb29+eqrr2qXAH+jM2fOJEkmT56cJGlubq6ZSGbMmJEkOXv2bJJk0qRJya9X4fLr8yp+U61WL3kVbsKECWlsbBx9LoZL9FB//jTwjY2NqVQqaWlpSVNT0+jZ+sSJE9Pc3Jxp06bVLgH+Rm1tbUmSnp6eHD58OAcPHqwdGf1/Om3atFQqlXz77bc5duxYenp6kiTXXXfd6IHBgQMHsnfv3jHrc9HB/b59+3L69OnRgwagfvxp4Jubm7N8+fIsXbo0y5cvz7hx41KpVLJkyZIsW7Ysjz322CWP/oG/R3t7e2bOnJmenp58+umnmTJlSpJk3LhxtaNpbW3NwoULc/LkydHv7e++++7MmjUr7e3taWpqypYtW/Lzzz/XLk1jY2N2796dzZs3p62tLffcc0/tCHCFG/OgmzfffDMjIyOXfFjN6dOn89FHH+Xs2bN57rnnanenv78/a9euveRa4P/HbwfUZ8+eTWNjYz744IOcPXs2K1eurB0dVa1WMzg4mKamptGnVSbJ8PBwzp8/n6ampjHz69evT39/f1auXJnBwcFLfg0AXJn+8EE3f6axsTHNzc2ZOXNm7S7gHzIwMJB33nknmzdvznvvvZeTJ0/m3nvvrR0bo6GhIS0tLWPiniSVSuV3ca8l7lC/Ljvwzc3NeeKJJ1yWh39Rc3Nz7rjjjrS1tWXOnDlZvnx5br755tqxv6S9vT233npr7WagzowJfENDw2X92tulZhzpw9+vUqnktttuy4IFC3LnnXfm6quvrh35y+bMmZO77rqrdjNQZ8Z8B79mzZpUq9UsWLBg9AEYl2toaCi7d+/OM888U7sLAPgHXPwd/CXfBz9hwoSLxi9PtVrN0NCQ98EDwL/kDwMPANSv3wX+66+/HjMAANSfuXPnjv582XfRAwD1Q+ABoEACDwAFEngAKJDAA0CB3EUPdeLIkSPp6upKS0tLrr322hw5ciT3339/Dh06lL6+vrS3t+c///lPFi9enGq1mh07duTo0aOZNGlS5s+fnylTpmTPnj356aefsnDhwowfPz4dHR2ZPn16br/99uzYsSODg4OZPXt2du7cmba2ttx3332pVCq1HwW4QrmLHurMqVOnsnr16nR3d+fAgQN5991309HRkaGhoXz33Xfp6OjI22+/na6urpw/fz5r1qzJhg0bcuLEiWzdujWvvvpqTp8+nT179qSjoyPnzp1LknR0dGTXrl1Jkh07dmTTpk358MMP09fXl08++SQbN26s+SRAvRB4qAPd3d05f/58VqxYkWeffTZz5sypHclDDz2Ul156KUePHk1fX18eeOCBPPXUU1mxYkUGBwfT3d1du+SSVq1aleeffz6tra3Zu3dv7W6gTgg81IH+/v4kGX25zMSJE2smkhtuuCH59ZWySdLW1pYkmTRpUvLrO+R/e1FUtVq95Fshm5ubR98bP2HChAwPD9eOAHVC4KEOTJ8+PUmydevWfP/999mzZ0/tyGi8r7/++lQqlXR2duaHH37Ili1bkiQ33XTT6IHB7t27s3379jHr8+uBRHd3d7q6unLixInMmjWrdgSoEwIPdWDevHm58cYbs3Xr1qxduzbXXHNNkmT8+PG1o5k6dWqWLVuW48eP5/XXX8/OnTuzaNGitLe3Z968eWlpacnHH3+cH3/8sXZpmpqa8sUXX2TdunWZPn16Fi9eXDsC1Al30UMdGBkZSZKcOXMmTU1Nee211zIwMJAXX3yxdnRUtVpNf39/Wltbc9VV/3csPzw8nKGhobS0tIyZX716dU6ePJkXXnghAwMDaW1tHbMfuPK5ix7qTH9/f15++eWsW7cur7zySo4fP56HH364dmyMhoaGTJ48eUzck6RSqfwu7hdraGgQdyiAM3ioAxcuXMj27dtz6tSptLa25pZbbsmMGTNqx/6SL7/8MmfOnMmDDz5YuwuoExefwQs8ABTCJXoAKJzAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBAAg8ABRJ4ACiQwANAgQQeAAok8ABQIIEHgAIJPAAUSOABoEACDwAFEngAKJDAA0CBBB4ACiTwAFAggQeAAgk8ABRI4AGgQAIPAAUSeAAokMADQIEEHgAKJPAAUCCBB4ACCTwAFEjgAaBADdVqtVq7EQCob87gAaBAAg8ABRJ4ACjQ/wD2ZT1Egv32TAAAAABJRU5ErkJggg==)*Figure 4. Group*

A group is used to group multiple process elements together as a sub structure.

Each group must contain a start element and one or more end elements. At runtime, mappings inside the group have access only to the group’s pipeline. Variables from the outer pipeline are only available if they are mapped to the group’s pipeline by the start element. Likewise, variables from the group’s pipeline are lost when the group finished execution unless the end element maps them back to the outer pipeline.

The group’s elements, except for its start and end elements, are called the group body.

`&lt;group id="..." name="..." condition="..." collectIterationResults="..."&gt;
  &lt;constants&gt;
    ...
  &lt;/constants&gt;
  &lt;logBefore... /&gt;
  &lt;!-- Body --&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/group&gt;`**constants (0..1)**

Constants.

**logBefore (0..1)**

Diagnostic log message that is written before the group is executed.

**Body**

Contains at least one start and one end element. May contain any additional number of elements and connections.

**dataLog (0..1)**

Data log, written after the group is executed.

**logAfter (0..1)**

Diagnostic log message that is written after the group is executed.

**collectIterationResults**

If this is `true`, then the outputs of iterated executions (for groups with an iteration target in its start element’s input mappings) are collected and returned as lists by the end element. If it is `false` (the default), only the last iteration’s results are returned.

## Loop
As of Process Engine version 6.5, the loop element does not exist anymore. Instead, groups with iteration targets can be used. Older process definitions are automatically updated accordingly when they are loaded.

## Mapping Element
![](data:image/png;base64,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)Figure 5. Mapping Element

A mapping element performs calculations and data initialisation tasks by executing a series of mappings. The process pipeline is used as both the source and target pipeline for these mappings.

`&lt;mappingElement id="..." name="..." condition="..."&gt;
  &lt;logBefore... /&gt;
  &lt;mapping&gt;...&lt;/mapping&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/mappingElement&gt;`**logBefore (0..1)**

Diagnostic log message that is written before the element’s mappings are performed.

**mapping (0..n)**

A number of [mappings.](/doxee-platform/docs/chapter-5-mappings)

**dataLog (0..1)**

Data log, written after the element’s mappings are performed.

**logAfter (0..1)**

Diagnostic log message that is written after the element’s mappings are performed.

## Script Element
![](data:image/png;base64,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)Figure 6. Script Element

A script element executes script code when it is called. The script code can be provided inside the element or in a separate file referenced via a URL.

`&lt;script id="..." name="..." condition="..."&gt;
  &lt;logBefore... /&gt;
  &lt;code language="..." url="..."&gt;
    ...
  &lt;/code&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/script&gt;`**logBefore (0..1)**

Diagnostic log message that is written before the group is executed.

**code (1)**

Script code

code (1)/l**anguage (1)**

Script language.

code (1)/**url (0..1)**

URL of a file containing the script code.

code (1)**/Body**

Script code.

**dataLog (0..1)**

Data log, written after the group is executed.

**logAfter (0..1)**

Diagnostic log message that is written after the loop is executed.

The script itself must be provided either via a URL or as the content of the `code` element. It is not allowed to specify both a URL and the code at the same time.

## Start Element
![](data:image/png;base64,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)*Figure 7. Start Element*

A start element marks the beginning of a process, or a sub structure (e.g. a group or a loop). When a process is started, execution begins at its start element and the start element’s mappings are used to map parameters provided by the caller into the process pipeline.

When a sub structure is executed at runtime, its inner execution begins at the structure’s start element. The start element’s mappings are used to map variables from the outer pipeline into the sub structure’s pipeline.

`&lt;startElement id="..." name="..."&gt;
  &lt;mapping&gt;...&lt;/mapping&gt;
  &lt;log... /&gt;
&lt;/startElement&gt;`mapping (0..n)

A number of [mappings.](/doxee-platform/docs/chapter-5-mappings)

log (0..1)

Diagnostic log message that is written after the start element has been executed.

## Task Element
![](data:image/png;base64,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)*Figure 8. Task Element*

A task element creates a new task and waits for its state to be changed to `finished`.

The task element can only be used if a task manager has been configured for the Process Engine.

`&lt;task id="..." name="..." condition="..." type="..." uncache="..."
    becomeSupervisor="true" storeCredentials="false"
    taskReadCredentials="technicalTaskCredentials"
    supervisorPasscode="true" &gt;
  &lt;logBefore... /&gt;
  &lt;inputs&gt;
    ...
  &lt;/inputs&gt;
  &lt;outputs&gt;
    ...
  &lt;/outputs&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/task&gt;`**type**

The task’s type.

**uncache**

Specifies whether the process execution should be removed from the cache once the process is waiting.

**becomeSupervisor**

If this is `true`, the current process user will be automatically added as a supervisor of the newly created task.

**storeCredentials**

If this is `true`, the created task my only be checked in if the user agrees to have their current credentials stored in the task, and the process will continue running with those credentials as its current user once the task has been completed.

**taskReadCredentials**

Whether tasks should be read with credentials specified by the credentials registry (i.e. the same that new tasks are created with) `(processRegistryCredentials)`, or with the technical task credentials specified in the configuration `(technicalTaskCredentials)`. Technical credentials are the default.

**supervisorPasscode**

If this is `true`, a supervisor passcode is created for the task, and used when reading the task. The supervisor passcode is a secure code, known only to the Process Engine, that causes the Task Manager to treat the caller as a supervisor for the task even if the actual user does not have supervisor privileges. If technical credentials are used to read tasks, and the technical user is not configured as a supervisor of the task created by the task element, the supervisor passcode is necessary; otherwise, the process will fail when trying to read the task after it has finished. By default, the supervisor passcode is enabled.

> Note

Process Engine can only create tasks that store credentials if the Task Manager configuration in `process_engine.xml` defines a key pair to encrypt the credentials.

Like with a [Wait Element](/doxee-platform/docs/6-6-process-engine-process-definition-reference-elements-1#wait-element), the process will change its state to waiting while `waiting` for the task to be finished.

Aside from the type defined in the task element, the values provided by the input mappings are used to create the task. The following parameters are handled specially:

**description**

Human readable description for the new task.

**priority (optional)**

Integer priority for the new task.

**potentialOwners**

The users who are allowed to check out the task. 

**supervisors**

Users who are allowed to change the owners of a task.

**autoTaskConstants (optional)**

A list of constant names. The available constants identified by these names are set as metadata of the task. This is a convenience feature for passing certain parameters into tasks without having to map each of them separately.

Any other variables mapped into the task element are passed on to the task’s payload.

The user and password parameters can be used to create the task as a specific user. If they are not specified, the credentials of the process’s current user are used instead. This requires authentication to be configured for the Process Engine.

When the task element continues, the task’s final payload is provided in the output variables and can be mapped to the process pipeline using the output mappings. Additionally, the task’s XML metadata is provided via an output paramter called `task`.

Accessing the task manager requires credentials. The process will look for a matching server entry in the credentials registry when calling the task manager.

## Wait Element
![](data:image/png;base64,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)Figure 9. Wait Element

A wait element triggers a wait state, which waits for a certain event before continuing process execution. While the process is `waiting` for the event, its process state is waiting, which also allows it to be persisted and the Process Engine to be temporarily stopped without affecting the process’s further execution.

`&lt;wait id="..." name="..." condition="..." type="..." uncache="..."
    throwExceptionOnError="true"&gt;
  &lt;logBefore... /&gt;
  &lt;inputs&gt;
    ...
  &lt;/inputs&gt;
  &lt;outputs&gt;
    ...
  &lt;/outputs&gt;
  &lt;dataLog... /&gt;
  &lt;logAfter... /&gt;
&lt;/wait&gt;`**type**

Defines the wait state type to be used.

**uncache**

Specifies whether the process execution should be removed from the cache once the process is waiting.

**throwExceptionOnError**

Since version 6.5, a failing wait state raises an exception in the process. Previous versions simply returned an output containing an error code, which was easy to accidentally ignore (especially if the wait state did not provide any output data that the process was interested in). This original behaviour can still be activated by setting `throwExceptionOnError` to `false`.

Doxee provides a number of different wait state types, which are listed in the user guide. Each type waits for a specific event, e.g. a timeout, an incoming email or a new file in a directory.

The wait state type defines a set of input parameters it supports. These can be set using the input mappings. If the wait state type produces output, it is always in XML format and provided as an output parameter.

The following output parameters are available:

**result ***(text/xml)*

The output provided by the wait state, or `null` if the wait state did not produce any output.

**interrupted ***(x-xsd/boolean) *

`true` if the wait state was interrupted instead of being triggered by its expected event.

**error ***(text/plain)*

An error message if an error occured while the wait state was active.

By default, the wait state is deleted as soon as the requested event occurs and the process continues. By setting the parameter keepWaitState to true, the wait element can be instructed to keep the wait state even after the element has returned. The wait state’s ID is reported as output parameter waitStateId.

Instead of creating a new wait state, a wait element can reactivate an existing wait state by providing the matching waitStateId via the input mappings. This allows wait states to track their progress through multiple iterations, e.g. making sure that a file wait state correctly recognises files that have been added between subsequent uses of the wait state, even if files are added while the wait state is inactive. Even if a wait state ID is provided by the caller, the corresponding wait state will be deleted at the end of the wait element unless keepWaitState is set to `true`.

Wait states that are kept beyond their wait elements' scope are process resources and as such bound to the process lifecycle. They will be deleted when the process reaches an end state.

## Include Process Element
![](data:image/png;base64,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)Figure 10. Include Process

Includes another process definition (called the *sub process definition*) as part of this process definition.

`&lt;includeProcess id="..." name="..." process="..." collectIterationResults="..."&gt;
  &lt;inputs&gt;
    ...
  &lt;/inputs&gt;
  &lt;outputs&gt;
    ...
  &lt;/outputs&gt;
  &lt;dataLog... /&gt;
&lt;/task&gt;`process

The path to the sub process definition.

collectIterationResults::See [Group](/doxee-platform/docs/6-6-process-engine-process-definition-reference-elements-1#group). Unlike for groups, this flag defaults to `true` for include elements.

Sub process definitions are loaded at instantiation time and therefore are a part of the process at runtime. They are *not* executed as a separate process instance.

After a process definition is loaded, its include elements are resolved by loading each sub process as a new group that is added as the include element’s child. This group represents the root element of the sub process, i.e. a start element with the ID `start` of a sub process loaded via an include element with the ID `include` will have the full ID `root.include.root.start`.

The provided input mappings specify those variables which are passed to the sub process’s inputs. Likewise, the sub process’s outputs can be mapped back to the main process using the output mappings.

To prevent endless recursions, a process definition may not, directly or indirectly, include itself.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}