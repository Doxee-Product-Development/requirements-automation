# 08 - Repository & Content Repository Reference Bible

> Compressed from 54 source files (~185KB text) across Doxee Platform Repository resource references and Content Repository 6.7 user/admin guides.

---

## Part A: Doxee Platform Repository

### A.1 Overview

The Repository is the central management UI for all Doxee Platform 3 resources. It provides CRUD operations, release management, and deployment to tenants.

### A.2 Resource Lifecycle

Every resource follows: **Create** -> **Edit** (if editable) -> **Release** -> **Publish** -> **Deploy** to tenant.

- **Release**: Creates a versioned snapshot with dependencies resolved via bindings
- **Publish**: Makes the release available on a tenant
- **Deploy**: Activates the published release on a tenant
- **Release & Deploy Panel**: Shows all releases and active deployments per resource; supports Inspect Deployment for detailed status

**Deployment statuses**: Started, Completed, Suspended

### A.3 Managing Resources

**Available actions** (depend on resource type and selection):
- **Edit** - Open in corresponding editor (editable resources only: workflows, DT/DC projects, DA stores, SMS templates)
- **Release** - Open Release & Deploy panel
- **Rename** - Edit resource name (single selection only)
- **Copy** - Duplicate resource to a destination folder
- **Move** - Relocate to a different folder
- **Transfer** - Move to a different account (cross-account)
- **Download** - Save resource file to local filesystem
- **Remove** - Delete resource (irreversible; active deployments are NOT removed from tenant)

---

## Part B: Resource Type Reference

### B.1 Document Resources

#### Document Templates (current)

| Aspect | Details |
|--------|---------|
| **Purpose** | Manage document templates created with Business Designer for use in Batch Workflows tasks |
| **Creation params** | None |
| **Editor** | None (managed via Business Designer) |
| **Release params** | None |
| **Deploy params** | None |

#### Document Template (DEPRECATED)

| Aspect | Details |
|--------|---------|
| **Purpose** | Manage Infinica templates for On-Demand Workflows Compose Documents tasks |
| **Superseded by** | Document Templates resource |
| **Release params** | Summary (text), Template URL (Infinica repository URL) |
| **Deploy params** | Release (dropdown), Tenant (dropdown) |

#### Document Composition Project

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure document composition using DP2 Document Composition editor |
| **Creation params** | File (optional, ZIP format - previously exported DP2 DC resource) |
| **Editor** | DP2 Document Composition editor (requires Doxee Client application) |
| **Release params** | Target: `Batch production` or `On-demand production`; Summary |
| **Deploy params** | N/A (deployed as workflow dependency) |

#### Document Composition Program

| Aspect | Details |
|--------|---------|
| **Purpose** | Use precompiled DP2 DC resource for document composition in workflows (migration use case) |
| **Creation params** | None |
| **Editor** | None |
| **Release params** | Target: `Batch production` or `On-demand production`; File (upload precompiled DC); Summary |
| **Deploy params** | N/A (deployed as workflow dependency) |

#### Output Management

| Aspect | Details |
|--------|---------|
| **Purpose** | Use Business Designer document templates in Batch Workflows tasks |
| **Creation/Release/Deploy params** | None |

#### Pweb Template

| Aspect | Details |
|--------|---------|
| **Purpose** | Manage Pweb assets for workflow tasks producing personalized web pages |
| **Release params** | Summary; Bundle (ZIP file upload) |
| **Deploy params** | Release, Tenant, Custom Domain (optional), Custom domain for Short URL (shown if Short URL enabled), GA tracking id, Analytics (toggle), Anonymization (toggle) |

---

### B.2 Workflow Resources

#### Batch Workflow

| Aspect | Details |
|--------|---------|
| **Purpose** | Orchestrate tasks to process input files in batch mode |
| **Creation params** | File (optional, JSON format - previously downloaded workflow) |
| **Editor** | Visual workflow editor |
| **Release params** | Revision (dropdown); Dependencies panel with resource bindings; Summary |
| **Deploy params** | Release, Tenant |
| **Deploy options** | See table below |

**Batch Workflow Deploy Options:**

| Option | Description |
|--------|-------------|
| **Approval by component** | When enabled, requires manual approval before final delivery task. Enabled by default on integration tenants, disabled on production tenants. Not available for On-Demand Workflows. |
| **Quotas by component** | Per-task memory: Standard, 3/5/10/15/20/25/30/40/50/60/70/80/90/100 GiB. Set maxHeap to ~75% of allocated quota for Java tasks. |
| **Quotas for workflow** | Workflow-level memory: Standard or 1 GiB |

**Dependency Bindings** (for DC and DT resources in workflow releases):

| Binding | Description | Availability |
|---------|-------------|--------------|
| **Deploy** | Uses latest deployment of the resource | Not for DC/DT resources |
| **Snapshot** | Uses latest snapshot (default for DC/DT) | DC/DT only |
| **Release Name** | Uses a specific named release | DC/DT only |

> Tip: Use existing releases (not Snapshot) for DC/DT dependencies during testing to reduce release creation time.

#### On-Demand Workflow

| Aspect | Details |
|--------|---------|
| **Purpose** | Orchestrate tasks to process input files in on-demand (synchronous) mode |
| **Creation params** | File (optional, JSON format) |
| **Editor** | Visual workflow editor |
| **Release params** | Revision, Dependencies (same binding model as Batch), Summary |
| **Deploy params** | Release, Tenant |
| **Deploy options** | See table below |

**On-Demand Workflow Deploy Options:**

| Option | Description |
|--------|-------------|
| **Compatibility** | `Native` (params in X-ODP-Job header as URL-encoded JSON) or `Backward compatibility` (params in BOM file, DP2 style) |
| **Unpack request** | Treat input as ZIP archive (no folders) |
| **Performance Profile** | Standard Tier 1 (5 req, 1 replica), Standard Tier 2 (15 req, 1 replica), High Load Tier 1 (30 req, 2 replicas), High Load Tier 2 (60 req, 3 replicas), High Load Tier 3 (90 req, 5 replicas) |
| **Troubleshooting Scope** | Save task output files for: All jobs (default), Failed jobs, None |
| **Custom quotas** | Per-task memory: Default, 2/4/8/12/16 GiB |

#### Batch Program

| Aspect | Details |
|--------|---------|
| **Purpose** | Process data in batch workflow using Java or Python program |
| **Release params** | Platform: `Java` or `Python`; File (JAR for Java, ZIP for Python); Summary |
| **Deploy params** | Release, Tenant |

#### On-Demand Program

| Aspect | Details |
|--------|---------|
| **Purpose** | Use custom program in on-demand workflow (Java or Python) |
| **Release params** | Platform: `Java` or `Python`; File (JAR for Java, ZIP for Python); Summary |
| **Deploy params** | N/A (deployed as workflow dependency) |

---

### B.3 Data Resources

#### Data Transformation Project

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure data transformation with DP2 DT&E editor or HTML5 DT editor |
| **Creation params** | File (optional, ZIP format - previously exported DP2 DT resource) |
| **Editors** | HTML5 Data Transformation editor; Legacy DP2 DT&E editor (requires Doxee Client) |
| **Release params** | Target: `Batch production` or `On-demand production`; Summary |
| **Validation** | Copied projects must be opened in editor and built before release. Imported pre-built projects can release directly. |

#### Data Transformation Program

| Aspect | Details |
|--------|---------|
| **Purpose** | Use precompiled DP2 DT resource in workflows (migration use case) |
| **Release params** | Target: `Batch production` or `On-demand production`; File (upload precompiled DT); Summary |

---

### B.4 Ingress Points (Data Entry)

#### Batch HTTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Trigger batch workflow execution via API |
| **Deploy params** | Tenant, Workflow Resource, Endpoint Path, Keys (optional, up to 10 Ingress Credentials), Parallel requests: 3/5(default)/10/15/40/50 |
| **Notes** | Both native and retro-compatibility request modes supported. Response is always empty (200 OK). BOM not supported for batch workflows. |

#### Batch FTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Retrieve files from FTP server to trigger batch workflow |
| **Deploy params** | Tenant; Customer Username; Trigger Policy: `Transfer` (default) or `Rename` (mutually exclusive) |
| **File params** | Input folder (relative path), Include/Exclude files by pattern (regex with glob syntax, supports wildcards), Deduplicate by filename (toggle), Deduplicate by content (toggle) |
| **Workflow** | Resource (batch workflow to trigger). Warning if workflow not deployed on tenant. |
| **Deduplication** | Window depends on configured job input retention period. After expiration, inputs are removed from storage. |

#### Batch Email Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Download emails from mail server (e.g., PEC receipts for T&R events/LEA) |
| **Server params** | Protocol: IMAPS(default)/IMAP/POP3S/POP3; Host; Port (defaults: 993/143/995/110) |
| **Account params** | Email, Password, Folder (default: INBOX) |
| **Client params** | Batch (max emails per execution, default: 1000), Delete all read messages (toggle, default: off - marks as read only) |
| **Workflow** | Resource (batch workflow to trigger) |

#### On-Demand HTTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Trigger on-demand workflow execution via API |
| **Deploy params** | Tenant, Workflow Resource, Endpoint Path (supports "/" in path), Keys (up to 10), Parallel requests: 5(default)/15/30/60/90 |
| **Notes** | Both native and retro-compatibility modes. Response is XML. |

#### Digital Archiving HTTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Interact with DA store via API |
| **Deploy params** | Tenant, Store Resource, Endpoint Path, Keys (up to 10), Parallel requests: 5(default)/10/15/20/25/30/40/50/60/70/80/90/100/120/140/160/180/200 |
| **Extraction options** | Toggle; Request compression: None/Zip; Response content: Metadata / Metadata+documents / Metadata+documents bundle (ZIP) / Documents; Response compression: None/Zip |
| **Upload** | Toggle to allow document upload |
| **Removal** | Toggle to allow document removal |

#### Digital Archiving Purl Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Interact with DA store via API and produce personalized URL (Purl) for archived documents |
| **Deploy params** | Tenant, Store Resource, Endpoint Path, Keys (up to 10), Parallel requests (default: 5), Extraction Duration (seconds, optional), Custom domain (optional) |

#### Pvideo HTTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Interact with Pvideo store via API and create Purl for personalized video |
| **Deploy params** | Tenant, Pvideo Store Resource, Endpoint Path, Keys (up to 10), Parallel requests: 5(default) to 200 (same scale as DA HTTP), Duration (seconds, optional), Custom domain (optional) |

#### Pweb HTTP Ingress

| Aspect | Details |
|--------|---------|
| **Purpose** | Interact with Pweb store via API and create Purl for personalized web page |
| **Deploy params** | Tenant, Pweb Store Resource, Endpoint Path, Keys (up to 10), Parallel requests: 5(default) to 200, Duration (seconds, optional), Custom domain (optional) |

---

### B.5 Stores

#### Digital Archiving Store

| Aspect | Details |
|--------|---------|
| **Purpose** | Define DA documents archive with categories, indexes, and access endpoints (Platform + Public) |
| **Creation params** | File (optional, JSON format - previously downloaded DA Store) |
| **Editor** | DA Stores editor |
| **Release params** | Revision, Summary |
| **Deploy params** | Release, Tenant |
| **Encryption** | Optional toggle; requires Store Key resource. Once deployed, encryption cannot be changed (can only switch Store Key on redeploy). |

#### Digital Archiving Hotspot (LEGACY)

| Aspect | Details |
|--------|---------|
| **Purpose** | Use legacy DA documents archive in batch/on-demand workflow |
| **Superseded by** | Digital Archiving Store |
| **Deploy params** | Tenant, Authorization Tag (identifies DA store) |

#### Pvideo Store

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure dedicated DA3 environment for publishing Pvideos via workflows |
| **Deploy params** | Tenant; Default store (optional, connects to existing DA3 env - max one per account); Retention (optional, days); Encryption (optional, requires Store Key - one Store Key per Pvideo store account; once enabled, cannot be disabled) |

#### Pweb Store

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure dedicated DA3 environment for publishing Pwebs via workflows |
| **Deploy params** | Tenant; Default store (optional - max one per account); Retention (optional, days - affects all previously uploaded docs); Encryption (optional, requires Store Key - one per Pweb store account; cannot be disabled once deployed) |

---

### B.6 Communication Templates

#### Email Template

| Aspect | Details |
|--------|---------|
| **Purpose** | Manage email assets (HTML) for workflow tasks that deliver emails |
| **Release params** | File (HTML file), Summary |
| **Deploy params** | Release, Tenant; From: Name (optional), Address (required); Reply: Name (optional), Address (optional); Tracking: Analytics (toggle) |

#### SMS Template

| Aspect | Details |
|--------|---------|
| **Purpose** | Manage SMS assets for workflow tasks delivering SMS messages |
| **Creation params** | Alias, File (optional, JSON format) |
| **Editor** | SMS template editor |
| **Release params** | Revision, Summary |
| **Deploy params** | Release, Tenant; Sender name (3-11 chars for MessageBird), Sender number, Analytics (toggle) |

---

### B.7 Security Resources

#### Archive Key

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure custom password for encryption of Batch Workflows Archive content (Package Files task) |
| **Deploy params** | Tenant; Password (min 1 char, encoded as Base64 by installer). Not displayed in details panel. Redeploy to change password. |

#### Store Key

| Aspect | Details |
|--------|---------|
| **Purpose** | Configure key ID and token for encryption on DA Store, Pvideo Store, or Pweb Store |
| **Deploy params** | Tenant; Key id (identifier), Key token (refresh token). Values provided by Platform Engineering team. |

#### Ingress Credentials

| Aspect | Details |
|--------|---------|
| **Purpose** | Generate unique API authentication key |
| **Deploy params** | Tenant; Expiration period: 6 months / 1 year / 3 years. Click Generate to create key and download credentials file. Key cannot be downloaded again. |

#### FTP Endpoint

| Aspect | Details |
|--------|---------|
| **Purpose** | Deliver files to an FTP server |
| **Deploy params** | Tenant; Protocol: FTP/SFTP; Host; Port (21 for FTP, 22 for SFTP); Path (relative to user home); Username; Password; Private key (SFTP only, upload) |

---

### B.8 Organizational Resources

#### Folder

| Aspect | Details |
|--------|---------|
| **Purpose** | Container for storing resources or other folders |
| **Creation/Editor params** | None |

#### Asset

| Aspect | Details |
|--------|---------|
| **Purpose** | Upload a file accessible by workflow tasks (e.g., Data Transformation catalog) |
| **Release params** | File (upload), Summary |
| **Deploy params** | Release, Tenant |

---

## Part C: Content Repository (v6.6/6.7)

### C.1 Introduction

Doxee Content Repository is a WebDAV-based network filesystem for storing and managing Doxee files (templates, XML, etc.) and arbitrary files. Based on Apache Jackrabbit (JCR reference implementation). Accessed via WebDAV protocol (HTTP extension).

**System Requirements**: OpenJDK, Apache Tomcat, local filesystem for cache/index. Optional: JDBC-compatible relational database.

### C.2 WebDAV Protocol

WebDAV extends HTTP/1.1 with:
- **Filesystem methods**: MKCOL, COPY, MOVE
- **Property methods**: PROPFIND, PROPPATCH
- **Versioning methods**: VERSION-CONTROL, CHECKOUT, CHECKIN, UNCHECKOUT
- **Access control**: ACL

**Properties**: Name/value pairs (XML fragments) attached to resources defining metadata. Server-maintained (read-only) or client-set.

### C.3 Features

#### Versioning
- Checkout-in-place model (Delta-V extension)
- `VERSION-CONTROL` -> `CHECKOUT` -> edit -> `CHECKIN` (or `UNCHECKOUT` to discard)
- Checked-out files are auto-locked by the editing user
- Other users redirected to last checked-in version
- **Automatic versioning**: Configurable to version every new file automatically
- **Date-based access**: `?versionDate=RFC3339date` or base-path query `=versionDate=...=/path`
- **Filter-based access**: `?versionFilter=namespace:property=value` - returns newest matching version
- Combinable: date + filter

#### Locking
- Standard WebDAV LOCK/UNLOCK
- Lock owner auto-granted access (no token required)
- **Lock stealing**: Privileged users can take over locks from other users

#### XSL Generation
- Auto-generates XSL from Infinica templates via `?xsl` or `?xsl=fo` parameter
- Targets: `fo` (default), `idx`

#### ZIP Import/Export
- Export: `GET /path/?zip` - entire directory trees with properties, ACLs, versions
- Import: `PUT /path/?zip` - restores resources exactly
- Parameters: `acl`, `checkedOut`, `history`, `virtual`, `path`, `deploy`, `deployId`, `deployName`, `deployComment`, `deployTarget`
- **Filter**: XML filter on properties (DASL grammar)
- **Scheduled imports**: `?time=` parameter delays execution; persisted across restarts
- **Deployment mode**: Signs ZIP with private key, verifies on import. Enables import without write access (uses `infinica:deploy` privilege)

#### Performance Statistics
- When enabled, queryable via properties on `/.system`:
  - `infinica:performance-statistics` - method call stats
  - `infinica:property-performance-statistics` - property evaluation stats

### C.4 Characteristics

#### Access Control (ACL)
- ACLs on files/directories control privileges per user/group
- Set via ACL method (replaces entire list, not additive)
- Retrieve via PROPFIND on acl property
- Standard WebDAV + Doxee-specific privileges

#### Home Directory
- Auto-created per user at `/home/{username}`
- Access via `~` in URL: `http://server/~/file.txt` (own), `http://server/~user/file.txt` (other user)
- Configurable location pattern, auto-generate, path expression

#### Digest Property
- Auto-generated on file write: `{http://www.infinica.com/jcr/namespace}digest`
- Used to determine if two files are identical

#### Property Extractors
- Auto-set file properties from content on write
- ITX extractor sets: author, company, title, version, dataInputNames, testDataUrl_{name}

#### Base Path Queries
- Encode query params as path segments: `http://server/=flag=value=/path`
- Preserves params during relative path resolution (important for template references)

#### Configuration Reload
- `PUT /.system/` - reloads runtime config without restart
- Only runtime config; bootstrap config requires full restart

### C.5 Namespaces

| Prefix | URI | Description |
|--------|-----|-------------|
| D | DAV: | WebDAV standard |
| jcr | http://www.jcrp.org/jcr/1.0 | JCR |
| infinica | http://www.infinica.com/jcr/namespace | Doxee/Infinica |
| rep | internal | Jackrabbit |

### C.6 Privileges

| Privilege | Description |
|-----------|-------------|
| D:all | Full access |
| D:add-child-nodes | Adding child nodes |
| D:modify-access-control | Modifying ACL entries |
| D:modify-properties | Modifying properties |
| D:read | Read access |
| D:read-access-control | Reading ACL entries |
| D:remove-child-nodes | Removing child nodes |
| D:write | Write access |
| infinica:lockStealing | Stealing locks from other users |
| infinica:seeCheckedout | Reading resources checked out by other users |
| infinica:zipExport | ZIP export |
| infinica:zipImport | ZIP import |
| infinica:zipImportExport | ZIP import and export |
| infinica:deploy | ZIP import in deployment mode |
| internal:privilegeManagement | Managing repository privileges |
| internal:write | Full write access |
| jcr:lockManagement | Managing locks |
| jcr:removeNode | Removing nodes |
| jcr:versionManagement | Managing versions |

### C.7 Project Directory

- Any directory with `.infinica/project.xml` subdirectory is a Project Directory
- File references use `~project~/` prefix for project-relative paths
- Benefits: paths work from any nesting depth, project can be relocated without breaking references
- Root-level project directories not supported
- Settings (name, description) are documentation-only; no behavioral effect

---

## Part D: Content Repository Administration

### D.1 Bootstrap Configuration

Three files in `$TOMCAT/infinica/`:

#### repository.properties
- `repository.home` - Local storage directory (cache, index, optional Derby DB)
- `repository.config` - Path to repository.xml (typically in repo home)
- `init.initArchive` - ZIP file for initial content import

#### icr.xml (Doxee-specific)
Key sections:
- `<adminName>` - Admin user for internal tasks
- `<transactions timeout="30m">` - Transaction timeout (default 30 min)
- `<keyStores>` - Key stores for authentication
- `<userAccessConfiguration>` + `<authentication>` - User store and auth config
- `<roles>` - Role assignments:
  - `access` - Restricts repository access to role members only
  - `admin` - Full permissions on all operations
- `<search>` - Lucene index: enabled/disabled, autodetectTypes, indexingConfigFile, tikaConfigFile, synonymsFile
- `<debug>` - logErrorExceptions (default false), operationIdType: integer(default)/uuid
- `<performanceLog>` - Performance tracking
- `<server>` - HTTP probes (startup, liveness, readiness)

**HTTP Probes:**

| Probe | Purpose | Default Timeout |
|-------|---------|-----------------|
| Startup | Application startup complete | N/A (synchronous) |
| Liveness | Application still alive/responsive | 30s |
| Readiness | Below max capacity, accepting requests | 30s (needs maxReadinessRequests config) |

Probes respond: 204 (positive) or 503 (negative) to HTTP GET on configured ports.

#### repository.xml
- Jackrabbit storage config; auto-created on first bootstrap
- Default: local Derby DB in repo home
- Supports external databases via PersistenceManager config (MSSQL, PostgreSQL, etc.)
- Two persistence managers: workspace (default) and version storage (different schemaObjectPrefix)
- Virtual filesystem: default local; can be configured for database storage

### D.2 Runtime Configuration

Stored in: `/.system/.properties` (repository internal, takes precedence) or `$TOMCAT/repository.properties` (file system).

| Setting | Description |
|---------|-------------|
| `auto-versioning.enabled` | Auto-version new files (default: false) |
| `auto-versioning.exclusions` | Excluded paths (default: /.system) |
| `home-dir.location-pattern` | Home dir path template (default: /home/{username}) |
| `home-dir.auto-generate` | Auto-create home dirs (default: true) |
| `property.extractor.itx.fileName` | ITX extractor file pattern |
| `import.requireApproval` | Require approval for all imports |
| `import.delayedAsAdmin` | Execute delayed imports as admin |
| `webdav-import-export.deployment.enabled` | Enable deployment mode |
| `...deployment.acceptUnsignedZips` | Skip signature check (discouraged in production) |
| `...deployment.source.id` | Server identifier |
| `...deployment.source.publicKey` | Server public key (base64) |
| `...deployment.source.privateKey` | Server private key (base64) |
| `...deployment.allowedSourceIds` | Accepted source server IDs (comma-separated) |
| `...deployment.sourceKey.{id}` | Public key per source server |

**XSL Generation** config files in `/.system/`: `xsl-fo-settings.xml`, `xsl-idx-settings.xml`

**Dependency Analysis** indexer settings: `indexerStarterDelay` (30s), `indexerLockRefresherDelay` (60s), `indexerLockTimeout` (300s). In clusters, only one node runs the indexer.

### D.3 Cluster Configuration

Multiple instances sharing the same content via centralized storage.

**Requirements:**
- Each node: own `repository.properties`, `repository.xml`, local storage directory, unique cluster ID
- Shared: virtual filesystem, workspace + versioning persistence storage (external DB), journal
- Local per node: workspace and versioning filesystem
- No DataStore, or shared DataStore

**Setup steps:**
1. Replace local virtual filesystem with shared `DbFileSystem`
2. Disable DataStore
3. Configure global persistence managers (external DB for workspace + versioning)
4. Add `<Cluster>` element with unique node ID and DatabaseJournal config
5. Start first node, verify, then add additional nodes

### D.4 XML Configuration

- **Relative URLs**: Resolved relative to the configuration file location
- **XInclude**: Standard for splitting config across files; useful for sharing user access/security config between applications. Note: relative URLs in included files resolve against the main file path

### D.5 Installation Steps

1. Stop Tomcat
2. Copy `infinica-content-repository.war` to `$TOMCAT/webapps`
3. Copy `infinica` directory to `$TOMCAT`
4. Edit bootstrap configuration files
5. Start Tomcat (do NOT start before config is complete)
6. Verify log files for bootstrap errors
7. Test access via `http://localhost:8080/infinica-content-repository/`

---

## Part E: Quick Reference - All Resource Types

| Resource Type | Category | Has Editor | Has Release Params | Has Deploy Params |
|---------------|----------|------------|-------------------|-------------------|
| Document Templates | Document | No | No | No |
| Document Template (deprecated) | Document | No | Yes | Yes |
| Document Composition Project | Document | Yes (DP2 DC) | Yes | No |
| Document Composition Program | Document | No | Yes | No |
| Output Management | Document | No | No | No |
| Pweb Template | Document | No | Yes | Yes |
| Batch Workflow | Workflow | Yes | Yes | Yes |
| On-Demand Workflow | Workflow | Yes | Yes | Yes |
| Batch Program | Workflow | No | Yes | Yes |
| On-Demand Program | Workflow | No | Yes | No |
| Data Transformation Project | Data | Yes (HTML5/Legacy) | Yes | No |
| Data Transformation Program | Data | No | Yes | No |
| Batch HTTP Ingress | Ingress | No | No | Yes |
| Batch FTP Ingress | Ingress | No | No | Yes |
| Batch Email Ingress | Ingress | No | No | Yes |
| On-Demand HTTP Ingress | Ingress | No | No | Yes |
| DA HTTP Ingress | Ingress | No | No | Yes |
| DA Purl Ingress | Ingress | No | No | Yes |
| Pvideo HTTP Ingress | Ingress | No | No | Yes |
| Pweb HTTP Ingress | Ingress | No | No | Yes |
| Digital Archiving Store | Store | Yes | Yes | Yes |
| DA Hotspot (legacy) | Store | No | No | Yes |
| Pvideo Store | Store | No | No | Yes |
| Pweb Store | Store | No | No | Yes |
| Email Template | Communication | No | Yes | Yes |
| SMS Template | Communication | Yes | Yes | Yes |
| Archive Key | Security | No | No | Yes |
| Store Key | Security | No | No | Yes |
| Ingress Credentials | Security | No | No | Yes |
| FTP Endpoint | Security | No | No | Yes |
| Folder | Organizational | No | No | No |
| Asset | Organizational | No | Yes | Yes |

---

## Part F: Common Deploy Parameters

Nearly all deployable resources share these base parameters:

| Parameter | Description |
|-----------|-------------|
| **Tenant** | Target tenant for deployment (dropdown) |
| **Release** | Release version to deploy (dropdown, when applicable) |

**Publish vs Deploy**: "Publish" makes the release available on tenant; "Deploy" publishes AND activates it.

**Ingress Common Pattern** (HTTP-based ingress points):

| Parameter | Description |
|-----------|-------------|
| Tenant | Target tenant |
| Store/Workflow Resource | Connected resource |
| Endpoint Path | URL path suffix (supports "/" within) |
| Keys | Ingress Credentials (up to 10, for key rotation) |
| Parallel requests | Rate limit (varies by resource type) |

**Store Common Pattern** (Pvideo/Pweb stores):

| Parameter | Description |
|-----------|-------------|
| Default store | Connect to existing DA3 environment (max 1 per account) |
| Retention | Optional; period in days before document deletion |
| Encryption | Optional; requires Store Key; irreversible once deployed |
