# 05 - Process Engine & Workflows Context Bible

> Compressed from ~443 markdown files across 8 documentation sections.
> Sources: process-engine-6-7, process-designer-6-7, batch-workflows, on-demand-workflows, batch-jobs, on-demand-jobs, batch-workloads, batch-jobs-legacy

---

## 1. Process Engine Core (PE 6.7)

### 1.1 Overview
The Doxee Process Engine is a **graph-based process execution engine** that processes IPD (Infinica Process Definition) XML files. It provides:
- **Interfaces**: CLI, SOAP, REST (JSON/XML), embedded Java
- **Base URL pattern**: `http://{host}:{port}/infinica-process-engine/rest/`
- **Process definitions**: Stored as IPD files, typically created in Process Designer

### 1.2 Process Elements (BPMN-like)

| Element | Description |
|---------|-------------|
| **Start** | Entry point; has output mappings for initial variables |
| **End** | Exit point; has input mappings for return values |
| **Mapping** | Transforms data between elements; has input/output mappings |
| **Activity** | Executes a predefined module activity (e.g., render, transform, DB read) |
| **Group** | Container for sub-processes (replaced loops since v6.5); can be collapsed |
| **Decision** | Conditional branching with ordered conditions on outgoing connections |
| **Wait** | Pauses execution; types: timeout, file watcher, email; `uncache` frees memory |
| **Task** | External task (managed by Task Manager); supports `uncache`, `storeCredentials` |
| **Script** | Executes inline or URL-referenced script code |
| **Include Process** | References an external IPD file for modular composition |

### 1.3 Connections

| Type | Description |
|------|-------------|
| **Standard** | Normal flow between elements; supports `savePoint`, `delay` |
| **Exception** | Error handling flow; has `type` (dot-separated hierarchy), `retries`, `delay` |

### 1.4 Process Lifecycle States

```
CREATED -> READY -> RUNNING -> WAITING / FINISHED / FAILED / TERMINATED
```

- **Online/Offline**: Controls whether PE picks up process for execution
- **Health**: `ok`, `broken`, `lost`
- **Breakpoints**: Can be set on elements for debugging
- **Auto-dispose modes**: `never`, `fetch`, `endedNotFailed`, `endedOrFailed`

### 1.5 Variables & Pipeline

**Mapping Sources**:
| Source Type | Syntax |
|-------------|--------|
| Literal | Plain text value |
| Parameterized Literal | Contains `{expressions}` in curly braces |
| Variable | `$variableName` |
| XPath | `{xpath-expression}` |
| URL | File/resource reference |
| Null | Empty (no value) |

**Mapping Targets**:
- **Variable**: Creates/overwrites a pipeline variable with name, type, and optional default
- **Iteration Target**: Processes multiple values from source sequentially
- **Keep-Variables**: Preserves specified variables, removes all others

### 1.6 Credentials Handling

| Type | Description |
|------|-------------|
| **Credentials Registry** | Stores credential sets for activities; configurable per-process |
| **Technical Credentials** | From PE configuration; used when no user credentials available |
| **Current User Credentials** | From the API caller; can be updated via `updateCredentials` |

- Credentials propagate through process execution and include expiration handling

### 1.7 Data Stores

Two XML/JSON formats for passing data:

| Format | Description |
|--------|-------------|
| **Standard** | Exact format with shared value structures; `<values>` + `<entries>` sections |
| **Simple** | Easier to parse; `<entry name="x" type="text/plain"><value>y</value></entry>` |

Both support XML and JSON representations. Used in `run`, `startProcess`, `setInstanceConstants`.

### 1.8 Exception Handling

- **Exception types**: Hierarchical dot-separated (e.g., `system.terminate`, `io.file`)
- **Retry handlers**: Exception connections with `retries` count and `delay` (ms)
- **Terminate exceptions**: `system.terminate` -- cannot be caught, forces process end
- **Error Health mapping**: Maps specific exceptions to health states

### 1.9 Logging

| Log Type | Description |
|----------|-------------|
| **Process State** | Lifecycle state changes |
| **Trace** | Enter/leave elements, take connections |
| **Diagnostic** | Parameterized literal messages; levels: none through all |
| **Data** | Typed name-value fields for metrics; levels: none through all |
| **Message** | JSON via message broker (ActiveMQ/similar) |

### 1.10 Persistence

| Storage Type | Description |
|-------------|-------------|
| **File Storage** | Filesystem-based; save points on connections |
| **SQL Database** | Relational DB storage |
| **MongoDB** | NoSQL document storage |

Save points are placed on connections; when a process reaches a save point, its state is persisted.

### 1.11 Wait States
- **Timeout**: Pauses for specified duration
- **File Watcher**: Waits for file to appear at specified location
- **Email**: Waits for incoming email
- `uncache` property: Removes process from memory cache while waiting

---

## 2. Process Engine REST API

### 2.1 Process Lifecycle Operations

| Operation | REST Endpoint | Description |
|-----------|---------------|-------------|
| `instantiate` | `POST /processes` | Create process instance from IPD URI or stream; params: `processUri`, `cache`, `threadPoolId`, `externalId` |
| `startProcess` | `POST /processes/{id}/start` | Start/continue process; params: `processParams`, `timeout`, `states`, `setOnline`, `inspectPipeline` |
| `run` | `POST /run` or `GET /run` | Combined instantiate+start; supports `processParams` as DataStore body (POST) or `in.varName=value` query (GET) |
| `reload` | `POST /processes/{id}/reload` | Reload process definition; only for CREATED or BROKEN |
| `terminateProcess` | `POST /processes/{id}/terminate` | Stop process; supports `kill` (force), `fail` (set FAILED vs TERMINATED) |
| `disposeProcess` | `DELETE /processes/{id}` | Remove process instance |
| `recoverProcess` | `POST /processes/{id}/recover` | Set health from `lost` to `ok` |
| `recoverProcesses` | `POST /recover` | Bulk recover via query |
| `setOnline` | `PUT /processes/{id}/online` | Set online/offline |
| `updateCredentials` | `POST /processes/{id}/updateCredentials` | Update process credentials to caller's |

### 2.2 Process State Queries

| Operation | REST Endpoint | Description |
|-----------|---------------|-------------|
| `getProcessSnapshot` | `GET /processes/{id}` | Current process snapshot; params: `peek`, `inspectPipeline` |
| `findExecutions` | `POST /processes/query` | Query processes with filters; body: query XML |
| `getAttributes` | `GET /processes/{id}/attributes` | Get process attributes |
| `getInstanceConstants` | `GET /processes/{id}/constants` | Get instance constants |
| `validate` | `POST /validate` | Validate IPD without executing |
| `waitForProcess` | `GET /processes/{id}/wait` | Wait for state (deprecated; use watchers) |

### 2.3 Process Configuration

| Operation | REST Endpoint | Description |
|-----------|---------------|-------------|
| `setAttribute` | `PUT /processes/{id}/attributes/{name}` | Set process attribute |
| `setBreakpoint` | `POST/DELETE /processes/{id}/breakpoints/{elementId}` | Set/remove breakpoint |
| `setInstanceConstants` | `POST /processes/{id}/constants` | Set instance-scoped constants |
| `setLogSettings` | `POST /processes/{id}/logSettings` | Set diagnostic/data/trace log levels |
| `setOwner` | `PUT /processes/{id}/owner` | Change process owner |
| `setPermissions` | `PUT /processes/{id}/permissions/{name}` | Set role/principal privileges |

### 2.4 Process Watchers (replaces waitForProcess)

| Operation | REST Endpoint | Description |
|-----------|---------------|-------------|
| `createWatcher` | `POST /watchers` | Create watcher; params: `executionId`, `expectedState`, `expectedOnlineState`, `expectedElement` |
| `getWatcher` | `GET /watcher/{id}` | Get watcher state; optional `timeout` and `finish` |
| `deleteWatcher` | `DELETE /watcher/{id}` | Remove watcher |

### 2.5 Administration

| Operation | REST Endpoint | Description |
|-----------|---------------|-------------|
| `clearCache` | `POST /clearCache` | Clear process definition caches |
| `getBrokerUri` | `GET /brokerUrl` | Message broker URI |
| `getConstants` | `GET /constants` | Public constants; optional `path` for partition |
| `getFeatures` | `GET /features` | Available features and states |
| `getMaintenanceLevel` | `GET /maintenance` | Current maintenance level |
| `setMaintenanceLevel` | `PUT /maintenance` | Set maintenance level |
| `getModules` | `GET /modules` | Installed activity modules |
| `getNodeState` | `GET /nodeState` | Single node state |
| `getNodeStates` | `GET /nodeStates` | All cluster node states |
| `getTaskManagerUrl` | `GET /taskManagerUrl` | Task Manager URL |
| `listServices` | `GET /services` | Internal PE services |
| `setEngineOnline` | `POST /setOnline` | Engine online/offline; cluster: `all`, `self`, `specified` |
| `uncacheProcesses` | `POST /uncacheProcesses` | Free memory by removing persisted inactive processes |
| `version` | `GET /version` | PE version |

### 2.6 Query Language
Queries use XML with `<and>`, `<or>`, `<not>`, `<param>` nodes:
```xml
<query><and>
  <param name="state" value="FINISHED"/>
  <param name="owner" value="admin"/>
</and></query>
```

### 2.7 Process Snapshot Structure
Response includes: `executionId`, `processUri`, `state`, `health`, `online`, `owner`, `elementId`, `message`, `externalId`, `threadPoolId`, `createdTimestamp`, `finishedTimestamp`, `stateChangeIndex`, pipeline (optional), attributes, permissions.

---

## 3. Process Designer (Eclipse-based IDE)

### 3.1 Overview
Eclipse-based graphical IDE for creating, editing, and testing IPD process definitions. Main components:
- **Editor**: Graphical canvas with palette, editing area, connections
- **Palette**: Lists available activities (from PE modules) and task types (from Task Manager)
- **Data Mode**: Visualization of mappings between elements
- **Views**: Outline, Properties, Pipeline, Log, Process Execution List, Resource Explorer

### 3.2 Editor Features
- Drag-and-drop from palette to canvas
- Connection creation via button pad drag
- Group collapse/expand
- Auto-layout (horizontal/vertical orientation)
- Include/close referenced processes
- Cut/copy/paste/undo/redo

### 3.3 Properties View Tabs

| Tab | Content |
|-----|---------|
| **Main** | ID, name, conditions, descriptor, language, process reference, uncache, save point |
| **Data** | Input/output mappings; sources (literal, variable, XPath, URL, null); targets (variable, iteration, keep-variables) |
| **Log** | Diagnostic messages (before/after), data log fields |
| **Execution** | Process state, element, started/finished times, exceptions |
| **Note** | Text annotations |

### 3.4 Process Execution
- **Engine types**: Remote (SOAP/REST), Managed (local), Cluster
- **Launch configurations**: Process file, URL, stream, thread pool, auto-dispose, credentials, parameters, log settings, attributes
- **Sync vs Async**: Synchronous (default, waits for completion) or Asynchronous (via message queue)
- **Debug**: Breakpoints, pipeline inspection, trace logging

### 3.5 Project Directory
- Marked by `.infinica/project.xml` file in any directory
- References via `~project~/path` notation (not relative, not absolute)
- Resolves by walking up parent directories

---

## 4. Batch Workflows

### 4.1 Overview
Multi-step document processing pipelines with **production** and **delivery** phases. Workflows are designed in a visual editor and executed as batch jobs.

### 4.2 Workflow Structure
- **Steps**: Sequential processing stages
- **Branches**: Parallel paths with optional "Assign lot" for separate lot tracking
- **Branch types**: Default (mandatory), Discard, custom distribution branches
- **Task types**: Production tasks, delivery tasks

### 4.3 Batch Workflow Task Reference

#### Production Tasks

| Task | Purpose | Key Config |
|------|---------|------------|
| **Compose Documents (DC)** | Generate documents via DP2 Document Composition | Project resource, input pattern, output format (PDF/AFP/PCL/PS/TIFF/XLSX/CSV/Web/Email/FOP), layout (duplex/simplex/mixplex), serializer, profile, images (static/dynamic/shared), overprints, max 10 custom attributes |
| **Count Pages (DC)** | Count pages per document via DP2 Document Composition | Same config as Compose DC |
| **Compose Invoices (DC)** | Add attachments to electronic invoices | Catalog pattern, invoices + attachments from previous tasks, output format/layout |
| **Create Documents (BD)** | Generate PDF/PDF-A/PDF-UA via ITX templates | Templates project, reference file, document/template selectors, rules, input pattern, images, output format, optional DA and Analytics elements |
| **Create Layout (BD)** | Create document layouts via ITX templates | Templates project, rules, output management resource, input pattern, images |
| **Transform Files (DT)** | Process data via Data Transformation service | DT resource, input readers (name, pattern, format: FLAT/XML/AFP, separator, encoding), input catalogs (file/resource), output writers |
| **Produce Indexes (OM)** | Create indexes / manipulate spool files via Output Management | DC resource, attributes, input pattern, output format/layout, serializer, profile, overprints |
| **Process Content** | Execute custom Java/Python code | Batch Program resource, variables |
| **Combine Flows** | Merge outputs from different branches | Origin (main branch), Batch Program resource, variables |
| **Package Files** | Package/filter output files | Include/exclude patterns |
| **Rename Files** | Rename files with transformations | RENAME ALL/MATCHING, TO/SET EXTENSION/MAKE CASE/PREPEND/APPEND/TRUNCATE/REPLACE/COUNTER, system attributes |

#### Archiving Tasks

| Task | Purpose | Key Config |
|------|---------|------------|
| **Archive Documents (DA)** | Load to Digital Archiving 3 via DA Store | DA Store resource, index pattern (default: LOADER.DA.INDEX.xml) |
| **Archive Documents (DA-hotspot)** | Load to DA3 via legacy DA Endpoint | DA Hotspot resource, index pattern |
| **Archive Documents (LEA)** | Load to Legal Electronic Archiving | Authorization tag, optional manual approval (Milan tenants only) |
| **Archive Receipts (LEA)** | Load receipts to LEA | Authorization tag, optional manual approval (Milan tenants only) |
| **Extract Documents (DA)** | Extract from DA3 via DA Store | DA Store resource, index pattern, query element, category attribute, output content (metadata/metadata+docs/docs) |
| **Extract Documents (DA-hotspot)** | Extract from DA3 via legacy endpoint | DA Hotspot resource, same params as DA extract |
| **Extract Documents (LEA)** | Extract from LEA | Input XML with legalEntityCode, targetEnvironmentCode (Milan tenants only) |
| **Extract Events (TR)** | Extract from Tracking & Reporting | Customer, procedure |

#### Distribution & Aggregation Tasks (Staging & Aggregation)

| Task | Purpose | Key Config |
|------|---------|------------|
| **Aggregate Shipments (SA)** | Group shipments by criteria | Site, reference file (shipment/document elements), aggregation query: `GROUP BY`, `ORDER BY` |
| **Distribute Digitals (SA)** | Route digital channels by business rules | Site, reference file, distribution rules with queries: `SELECT ALL/BY`, `ORDER BY`, `SPLIT BY`, `LIMIT BY` |
| **Distribute Hybrids (SA)** | Route hybrid mail channels | Site, reference file, optional aggregation, distribution/envelope/attachment/sheet profiles, queries: `SELECT`, `ORDER BY`, `SPLIT BY`, `LIMIT BY`, `LOOKUP BY`, `TRACK ALL/WHEN` |

#### Delivery Tasks

| Task | Purpose | Key Config |
|------|---------|------------|
| **Deliver Emails** | Send emails | Email Template resource or LOTXML mode; x-header validation |
| **Deliver Files (FTP)** | Deliver via (S)FTP | FTP Endpoint resource, temp files, semaphore files (base/full name + extension), LOTXML or folder+pattern |
| **Deliver SMS** | Send SMS messages | SMS Template resource |
| **Deliver PEC** | Send certified email (PEC) | PEC Configuration alias (LOTXML mode) |

#### Electronic Invoicing Tasks

| Task | Purpose | Key Config |
|------|---------|------------|
| **Manage Invoices (EI)** | Process electronic invoices | Default + custom output branches |
| **Create Packages (EI)** | Create signed FI packages for SDI | Consumes Manage Invoices output |
| **Deliver Packages (EI)** | Deliver packages to SDI | Consumes Create Packages output; supports eipa.delay (FROM_DATE, EXPIRY_DATE) |
| **Sign Documents** | Sign with CAdES/XAdES/PAdES | Signing profile code; CAdES->P7M, XAdES->XML, PAdES->PDF |

#### Publishing & Analytics Tasks

| Task | Purpose | Key Config |
|------|---------|------------|
| **Publish Documents (Pvideo)** | Create Pvideo + load to store + return Purl | Pvideo Store + Template resources, generate Purl (signed/plain), TTL |
| **Publish Documents (Pweb)** | Create Pweb + load to DA + return Purl | Pweb Store + Template resources, generate Purl (signed/plain), TTL |
| **Enrich Analytics (Pvideo)** | Consolidate Pvideo analytics across channels | Channel: SMS/Email/FTP; requires "Assign lot" on branch |
| **Enrich Analytics (Pweb)** | Consolidate Pweb analytics across channels | Channel: SMS/Email/FTP; requires "Assign lot" on branch |
| **Generate Purl** | Generate signed Purl for DA document | DA Store resource, document identifier attribute, generated Purl attribute, duration, custom domain |
| **Shorten Links** | Book/assign/confirm short URLs | Modes: Assign (long->short), Book (reserve short IDs), Confirm (bind short to long); domain, SID length (7-255), retention (soft/hard) |
| **Load Contacts (Booster)** | Create/update contacts on Doxee Booster | Identifier attribute, update existing toggle; input XML with CONTACTS/CONTACT elements |

#### DA3 Loader Index File Structure
```xml
<documents lotId="..." scope="PRODUCTION|TEST" useCase="BATCH">
  <document id="1" classCode="..." title="..." file="..." attachment="false" shipmentId="...">
    <indexes>
      <index code="..." value="..."/>
    </indexes>
    <pURL type="0" hostName="..." docGuid="..." />
  </document>
</documents>
```
- Update operations: `<documents_update>` with `<indexes_update>`, `<file_update>`, `<attachment_update>`
- Operators in queries: `=`, `!=`, `>`, `<`, `>=`, `<=`
- Scaling to 0 not allowed; `$MIN`/`$MAX` placeholders for extraction queries

---

## 5. On-Demand Workflows

### 5.1 Overview
Real-time single-request processing workflows. Every workflow starts with **Receive Content (HTTP)** and ends with **Respond Content (HTTP)**.

### 5.2 On-Demand Workflow Task Reference

| Task | Purpose | Key Differences from Batch |
|------|---------|---------------------------|
| **Receive Content (HTTP)** | Receive input via HTTP (initial task of all OD workflows) | Output file named "origin" |
| **Respond Content (HTTP)** | Deliver output via HTTP (final task) | Multiple branches can end in separate Respond tasks; supports file/folder filters |
| **Compose Documents (DC)** | Generate documents via Document Composition | Same as batch version |
| **Create Documents (BD)** | Generate PDF/PDF-A/PDF-UA via ITX templates | Same as batch; supports error toggle for continue-on-error |
| **Transform Content (DT)** | Process data via Data Transformation | Same config; readers, catalogs (file/resource with optional toggle), writers |
| **Produce Indexes (OM)** | Create indexes via Output Management | Same as batch version |
| **Compress Files** | Compress response content | Output: ZIP; optional dynamic filename (full name/base name from previous task) |
| **Convert Request** | Convert DP2 ODP request format to DP3 | Legacy migration; outputs data.xml + bom.xml; not required if backward compatibility enabled (since 3.25) |
| **Convert Response** | Convert DP3 response to DP2 ODP format | Legacy migration; not required if backward compatibility enabled (since 3.25) |
| **Process Content** | Execute custom Java/Python code | On-Demand Program resource + variables |
| **Rename Files** | Rename files with transformations | Same syntax as batch; RENAME ALL/MATCHING with transformations |
| **Archive Documents (DA/DA-hotspot/LEA)** | Same as batch variants | Same configuration |
| **Extract Documents (DA/DA-hotspot/LEA)** | Same as batch variants | Same configuration |
| **Deliver Emails** | Send emails | Same as batch; Email Template resource or LOTXML |
| **Deliver Files (FTP)** | Deliver via FTP | Must be parallel to Respond Content (HTTP); same config |
| **Deliver SMS** | Send SMS | Same as batch |
| **Deliver PEC** | Send certified email | Same as batch |
| **Publish Documents (Pvideo)** | Create/publish Pvideo + Purl | Same as batch; output branches: Default (mandatory) + Discard |
| **Publish Documents (Pweb)** | Create/publish Pweb + Purl | Same as batch; output branches: Default (mandatory) + Discard |
| **Enrich Analytics (Pvideo/Pweb)** | Consolidate analytics | Same as batch |
| **Generate Purl** | Generate signed Purl for DA document | Same as batch |
| **Shorten Links** | Book/assign/confirm short URLs | Same as batch; max 100 IDs per on-demand call |
| **Sign Documents** | Sign with CAdES/XAdES/PAdES | Same as batch |
| **Load Contacts (Booster)** | Create/update Doxee Booster contacts | On-demand task fails immediately on error (batch discards communication) |

### 5.3 Key Differences: Batch vs On-Demand
| Aspect | Batch | On-Demand |
|--------|-------|-----------|
| Input | ZIP/file upload via Batch Jobs UI | HTTP request |
| Output | ZIP download / FTP / email | HTTP response |
| Parallelism | Multi-job, multi-task concurrency | Single request processing |
| Error handling | Discard communication, continue | Fail immediately |
| Shorten Links limit | No explicit limit | Max 100 IDs |
| Workflow start/end | First production task | Receive Content (HTTP) / Respond Content (HTTP) |

---

## 6. Batch Jobs

### 6.1 Overview
Batch Jobs manage the execution of batch workflow instances. A job progresses through **production** and **delivery** phases.

### 6.2 Job Lifecycle

| Status | Description |
|--------|-------------|
| **Queued** | Job created, waiting for resources |
| **Running** | Job executing (production or delivery phase) |
| **Suspended** | Job paused (manual or error) |
| **Completed** | All tasks finished successfully |
| **Failed** | Job ended with error |
| **Canceled** | Job canceled by user |

### 6.3 Job Operations

| Action | Description |
|--------|-------------|
| **Create job** | Select account, workflow, upload input file; Create button only enabled with no jobs selected |
| **Resume** | Continue a suspended job from where it stopped |
| **Restart** | Re-execute from the beginning (removes partial outputs) |
| **Approve** | Manual approval for tasks with approval configured |
| **Cancel** | Cancel running/suspended job; uploaded DA documents auto-removed |
| **Download content** | Download input/output as ZIP (organized in folders) |
| **Download logs** | Download job logs as plain text |
| **Inspect** | View tasks table (task ID, started time, duration), job properties |
| **Labels** | Add/remove labels for organization |

### 6.4 Job Inputs & Outputs
- **Inputs**: Uploaded files for job processing; table shows input number, filename, created date, labels
- **Outputs**: Generated files from completed tasks; downloadable individually or as batch

### 6.5 Status Housekeeping
Configurable automatic cleanup of completed/failed/canceled jobs.

---

## 7. On-Demand Jobs

### 7.1 Overview
Single-request jobs created via HTTP call or UI.

### 7.2 Job Operations

| Action | Description |
|--------|-------------|
| **Create job** | Select account, on-demand workflow, upload input file |
| **Download content** | Request + response + intermediate task outputs as ZIP |
| **Download logs** | Job logs in plain text |
| **Inspect** | Tasks table (task ID, started, duration); workflow details |

### 7.3 Inspect Panel
- Tasks table shows execution timeline
- Duration = actual execution time (excludes wait/scheduling time)
- Intermediate task outputs available if configured in deployment (enabled by default)
- Malformed request: downloaded as "malformed request" file

---

## 8. Batch Workloads (Resource Scaling)

### 8.1 Overview
Scale Doxee Platform Batch processes at tenant, workflow, and component levels.

### 8.2 Sections

#### Tenant Resources
| Resource | Description |
|----------|-------------|
| **Jobs** | Max parallel jobs for tenant |
| **Production tasks** | Max parallel production tasks |
| **Delivery tasks** | Max parallel delivery tasks |
| **Memory** | Allocated memory (GiB) |

#### Workflow Resources
| Column | Description |
|--------|-------------|
| **Account** | Account associated with tenant |
| **Workflow** | Workflow name |
| **Jobs** | Max parallel jobs per workflow |
| **Production tasks** | Max parallel production tasks per workflow |
| **Delivery tasks** | Max parallel delivery tasks per workflow |

#### Component Resources
| Column | Description |
|--------|-------------|
| **Component** | Batch workflow component name |
| **Tasks** | Max parallel tasks for component |

### 8.3 Constraints
- All scaling fields are optional
- **Scaling to 0 is not allowed**
- Filterable by: All, Custom (at least one custom resource)
- Searchable by account/workflow/component name (exact or partial match)

---

## 9. Cross-Reference: Resource Types Used by Tasks

| Resource Type | Used By |
|---------------|---------|
| **Document Composition Program/Project** | Compose DC, Count Pages DC, Compose Invoices DC, Produce Indexes OM |
| **Document Templates** | Create Documents BD, Create Layout BD |
| **Output Management** | Create Layout BD |
| **Data Transformation Program/Project** | Transform Files/Content DT |
| **Digital Archiving Store** | Archive Documents DA, Extract Documents DA, Generate Purl |
| **Digital Archiving Hotspot** | Archive/Extract Documents DA-hotspot (legacy) |
| **Email Template** | Deliver Emails |
| **SMS Template** | Deliver SMS |
| **FTP Endpoint** | Deliver Files FTP |
| **Pvideo Store + Template** | Publish Documents Pvideo |
| **Pweb Store + Template** | Publish Documents Pweb |
| **Batch/On-Demand Program** | Process Content, Combine Flows |
| **Asset** | Input catalogs for DT tasks |

---

## 10. Common Configuration Patterns

### Output Formats (DC-based tasks)
PDF, AFP, PCL, PS, TIFF, XLSX, CSV, Web (Pvideo/Pweb), Email, FOP (XML embedded IF)

### Layouts
Duplex, Simplex, Mixplex

### Image Sources
- **Static/Predefined**: Default path
- **Dynamic**: From previous task output
- **Shared/Custom**: Shared volume at `/mnt/doxee/repository/document_composition_om/external_image/{path}`

### Custom Attributes (up to 10)
Available placeholders: `{{Account name}}`, `{{Account alias}}`, `{{Input filename}}`, `{{Job name}}`, `{{Job number}}`, `{{Job scope}}`, `{{Step name}}`, `{{Step alias}}`, `{{Task name}}`, `{{Tenant name}}`, `{{Tenant alias}}`, `{{Tenant stage}}`

### LOTXML
Delivery Channel Option File -- XML produced by DC task containing metadata for materials to deliver. Used by Deliver Emails, Deliver Files FTP, and Deliver PEC tasks.

### Backward Compatibility (since DP3 build 3.25)
On-demand workflows can enable backward compatibility at deployment time, removing the need for Convert Request/Convert Response tasks when migrating from DP2.
