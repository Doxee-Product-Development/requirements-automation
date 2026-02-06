# Context Bible: Doxee Platform Release Notes

> Compressed from 27 release note files (~119KB), 6 getting-started files (~13KB), and user-guide index files.
> Source: doxee/official-product-documentation/doxee-platform/
> Generated: 2026-02-06

---

## Product Lines Overview

Doxee Platform ships as two parallel product lines plus integration apps:

| Product Line | Description | Versioning |
|---|---|---|
| **DP3** (Doxee Platform 3.x) | Cloud-native CCM/CXM platform: Batch/On-Demand production, Digital Archive, Output Management, Cloud Analytics, Headlight, Pvideo, Pweb, Electronic Invoicing, Data Transformation, Staging & Aggregation | 3.MAJOR.MINOR.PATCH |
| **i-Edition** | On-premise document composition suite: Business Designer, Composer, Process Engine, Template Designer, Workplace, Task Manager, Resource Explorer, Content Repository | 6.MAJOR (+ SPn service packs) |
| **Integration Apps** | Doxee App for Salesforce, SAP, Microsoft Dynamics 365 | Independent versioning |

---

## Section 1: Doxee Platform 3.x (DP3) Release Notes

### DP3 3.49.2.1 -- January 23, 2026

**Fixes:**
- Cloud Analytics: `doxee_platform_id` max character length standardized to 255 chars across dp-message-publisher and ca-aws-infrastructure tables

### DP3 3.49.2 -- January 19, 2026

**Improvements:**
- Cloud Analytics: Track Documents Batch/On-Demand Workflow tasks now include media format `520 - TXT with PURL`
- Staging & Aggregation: Cloud Analytics reports now available on sftp-eu9.cloud.doxee.com

### DP3 3.49.1.1 -- January 7, 2026

**Fixes:**
- Batch Production: Send Emails task with scheduled emails using template bundles incorrectly populated `ATTACHMENTS` field with absolute path instead of relative `bp3-outbound` path, causing dispatcher failure

### DP3 3.49.1 -- December 1, 2025

**New Features:**
- Output Management: New "Simplify tag structure" flag under PDF options to simplify XML structure of accessibility tags in Intermediate Format before sending to FOP, reducing memory usage

### DP3 3.49.0.1 -- December 19, 2025

**Improvements:**
- Headlight: `scene_selection` action of `document_session_monitoring` events now included in `dp3_engagement_monitoring` dataset aggregation (supports Babelee Pvideo Document Rating Solution)

### DP3 3.48.1 -- November 2, 2025

**Improvements:**
- Headlight: `hl.facility.loader` more resilient to user inputs; no longer discards messages with values in different format

### DP3 3.48.0.6 -- October 22, 2025

**New Features:**
- Pvideo: Analytics tracking for Pvideos generated through Babelee interface

**Improvements:**
- Pvideo: Request caching for performance

**Fixes:**
- Pvideo: GUIDs not passed properly to workflow branches with Send Email/SMS tasks when workflow also contained Transform Files (DT) task

### DP3 3.48.0.5 -- October 13, 2025

**Fixes:**
- Electronic Invoicing: Infinite loops on extraction queries from Digital Archive when exporting CSV/Excel with >1 custom aggregate filter
- Headlight: Incorrect `communication_sent` metric count in `dp3_engagement_monitoring` dataset

### DP3 3.48.0.4 -- October 6, 2025

**Fixes:**
- Digital Archiving: Index type drop-down in Store configuration showed fewer options than available; indexes used across multiple document categories now counted once toward limits

### DP3 3.48.0.3 -- October 1, 2025

**Fixes:**
- Electronic Invoicing: Documents portal could not read fields with CDATA tags; incoming CDATA now sanitized

### DP3 3.48.0.2 -- October 19, 2025

**Fixes:**
- Batch Production: Resumed jobs failing quickly
- Batch Production: "Production without Outcome" status logic corrected (production completed without delivery and without terminal components like stores)

### DP3 3.48.0.1 -- September 24, 2025

**Fixes:**
- On-Demand Production: Regression from 3.48 -- On-Demand jobs for workflows released before 3.48 were broken (required rollback)
- Pvideo: Publish Documents Batch/On-Demand tasks ignored attachments from input file (missing properties in input mapping class)
- Pweb: Same attachment issue as Pvideo (missing properties in input mapping class)

### DP3 3.48 -- September 22, 2025 (MAJOR RELEASE)

**Key New Features:**

1. **Digital Archive Portal -- Upload, Edit, Delete Documents**
   - Complete document lifecycle management from portal UI
   - Configurable interface: designers control which indexes are editable, their visibility and order
   - Enhanced search: configured operators shown as visual icons in search panel
   - Granular permissions: independent upload/edit/delete permissions
   - Full audit trail: every operation logged with user, timestamp, affected resources

2. **Batch Jobs -- "Production without Outcome" Status**
   - New status when job completes without delivery and without terminal components
   - Auto-transitions to "Production Cancelled" after system timeout

3. **Batch & On-Demand Jobs -- Creator Tracking**
   - New "User" field across Batch and On-Demand Job portals
   - Auto-captures from portal sessions and BOM XML metadata
   - Searchable with case-insensitive filtering

4. **Route Files -- Default Branch & Error Prevention**
   - Jobs no longer fail when input files don't match any conditions
   - New "All other files" catch-all branch configuration

5. **Batch Jobs -- Resume in Relaxed Mode**
   - Resume failed Document Composition or Data Transformation tasks with relaxed processing from portal
   - All relaxed mode actions tracked in job history

**Changelog Details:**

*Platform:*
- Updated third-party Redis

*Batch Production:*
- Added "Production without outcome" error status
- Added resume in relaxed mode for DC/DT task failures
- Added invoicing dataset for production volume tracking; lots monitoring enabled by default
- Added "User" field for job creator tracking
- Improved `troubleshoot-activities` permission split into 4 granular permissions: `-logs`, `-content`, `-inputs`, `-outputs`
- Improved Batch Workloads scheduler to prevent resource saturation
- Fixed missing automatic retry for Batch Workflow upload/extract tasks (transient errors)
- Fixed missing tooltips on long dependency names in workflow task details
- Fixed large file downloads causing system instability
- Fixed Kafka event timestamp using consumption time instead of event time (skewed duration metrics)
- Fixed Archive Documents (DA) Batch Workflows task errors

*On-Demand Production:*
- Improved: PDF/UA Document Composition support with upgraded Java for FOP 2.10 compatibility
- Added "User" field for job creator tracking
- Fixed missing tooltips on long dependency names

*Digital Archive:*
- Portal: document upload (files + metadata), metadata updates, document removal from UI
- Dedicated permissions for upload/update/delete with audit logging
- Editability option for DA Stores: select which indexes available in upload/edit actions
- Improved search UX: search operator icons in left-hand panel
- Improved index type drop-down: shows only options with available slots (String max 50, Number max 10, Date max 10, Time max 25, Clob max 5)

*Repository:*
- Granular account-level permissions for Document Templates visibility
- Character validation for Archive Key resource password field

*Document Composition:*
- Changed PDF parser for PDF inclusion to non-sequential
- Fixed processing shipments with >50 page sections
- Fixed build errors on disabled rulesets
- Fixed missing first page section state for foreground back

*Output Management:*
- Improved color conversion for SVG charts from Business Designer Intermediate Format

*Data Transformation:*
- CSV Reader: mandatory/optional field validation; non-strict field ordering; superfluous fields ignored
- Improved application stability and UI responsiveness
- Fixed cloning previously-cloned elements

*Electronic Invoicing:*
- Updated signing library (pu3.facility.sign)

---

## Section 2: i-Edition Release Notes

### i-Edition 6.7 -- December 19, 2025 (MAJOR RELEASE)

**Key New Features:**

1. **Business Designer -- Complete UX Redesign**
   - Refreshed UI with reorganized left sidebar (general config) and right sidebar (context-specific settings)
   - Preview options and page view settings grouped in top toolbar

2. **Interactive Form Fields** (Template Designer, Business Designer, Composer)
   - Create interactive form documents with dynamic field interactions
   - XPath expression-based logic between fields
   - Dedicated configuration view in Business Designer/Template Designer
   - Form Fields tab in Composer sidebar
   - Replaces legacy JavaScript logic from previous Composer

3. **Composer -- Full WCAG Accessibility Compliance**
   - Full assistive technology and alternative navigation support
   - Improved readability with button labels

4. **Workplace 2 -- Expanded Human Tasks & Customization**
   - New Human Tasks: Generic Search, Excel Input, Data List
   - Navigation button customization (position, text, direction)
   - Dynamic localization based on language setting
   - Sidebar step visibility control
   - Third-party CRM integration (Salesforce, SAP)
   - Dark theme option

**Pre-Installation Requirements:**
- Storage format changed: export storages with Storage Manager, run through Migrator, reimport
- Task queries changed and must be adjusted

**Backward Compatibility:**
- User right `RIGHT_V_EXTERNAL_RESOURCES_MANAGEMENT` renamed to `RIGHT_V_EXTERNAL_RESOURCES`
- `ROLE_BUSINESS_USER` received new rights: `RIGHT_E_FORMS`, `RIGHT_V_GLOBAL_FORM_FIELDS`, `RIGHT_O_CREATE_GLOBAL_FORM_FIELDS_PACKAGE`

**Changelog Details:**

*Platform:*
- Added OIDC confidential client login for technical access
- Improved Resource Access Layer (RAL) for date-time properties without milliseconds
- Replaced Task Manager queries with generic Query API
- Fixed DnfQueryBuilder incorrectly handling nested and/or structures

*Security -- Library Updates:*
- activemq-client to 6.1.6, commons-lang3 to 3.18.0, jackson to 2.20.1, jackson-annotations to 2.20, jaxb-core to 4.0.5, jersey to 3.1.11, netty-codec-http2 to 4.1.124.Final, netty-codec-http to 4.1.125.Final, netty-codec to 4.1.125.Final, nimbus-oauth to 11.30.1, netty to 4.2.7.Final, undertow-core to 2.3.20.Final

*Business Designer:*
- Interactive Form Fields with predefined content options and field interactions
- STPC editability support (header/footer/side sections)
- Instream Foreign Object elements for inline graphics
- Inline block containers (itx:inline-block-container)
- XSL Code element (consolidation from Template Designer)
- Apply Templates element (consolidation from Template Designer)
- Number formatting logic
- Complex page masters can use simple page masters (consolidation from TD)
- Complete UI redesign
- Filepicker: copy/cut/paste on files and folders
- Table column/row reordering via drag-and-drop in Outline (limitation: complex tables may produce unexpected results)
- Multiple bug fixes: Problems & Events tab, clicking behavior, preview issues, filepicker, tooltips

*Composer:*
- User comments: location-specific and document-wide, with indicators and Comments tab
- STPC editability support
- Inline block containers
- Full WCAG accessibility mode
- Composer Human Task inherits Workplace language setting
- Composer Human Task supports refreshing XML data (Refreshables)
- Multiple fixes: Insertion Points coloring, scrolling, toggle behavior, tooltips, template loading

*Process Engine:*
- New `PdfBoxFormCreator` activity (replaces deprecated `PdfFormCreator`, supports newer PDF versions)
- Fixed: process instantiation with OpenID/Salesforce engines
- Fixed: `readPrincipals` incorrectly requiring technical user ID
- Fixed: TechnicalCredentialsManager logging debug messages on WARN
- Fixed: volatile process deletion only removing `pv~` prefix (should also remove `*v~`)
- Fixed: volatile process instances unknown to proxy storage returning null
- Fixed: `disposeProcesses` without query disposing all processes instead of throwing exception
- Fixed: thread pool configuration for service processes being ignored

*Task Manager:*
- Replaced queries with generic Query API
- Query API can terminate multiple tasks
- Task checkout restricted to supervisors/admins

*Template Designer:*
- Added interactive Form Fields support
- Fixed indexing dependencies in Dependency Analyzer
- Fixed rendering errors for templates with images/text fields/text areas

*Workplace 2:*
- Full/partial CRM integration (Salesforce, SAP) -- modular and configurable
- Generic Search Human Task
- Excel Input Human Task (file displayed as HTML, formulas retained)
- Data List Human Task (external data source display)
- Extensive branding and label customization
- Dark theme
- Navigation button customization
- File List Human Task: sorting and file preview
- Composer Human Task: language inheritance, XML data refresh, multiple templates, save changes on exit
- Business Cases launchable via HTTP requests
- Business Case definitions downloadable in XML
- Limitation: multi-template Composer Human Tasks must be finished to save edits
- Multiple fixes: breadcrumbs, Problems & Events refresh, table selection, records per page, login in Chromium, Email Human Task spacing, File List/HTML/Summary Human Task issues

*Workplace 1:*
- Replaced Task Manager queries with generic Query API

---

### i-Edition 6.6 -- July 18, 2025 (MAJOR RELEASE)

**Key New Features:**

1. **Workplace 2 -- New Application**
   - Complete redesign from Workplace 1: new technology stack, UX, backend, Human Tasks
   - Tailored for B2C communications
   - Business Case Instances view for supervisors/admins
   - Backward compatibility note: project analysis required before transitioning; Workplace 1 receives maintenance-only support going forward

2. **Composer -- Major UX/Performance on Insertion Points & Building Blocks**
   - Categories and subcategories for organization
   - Labels and tooltips on mouseover
   - Search bar for Building Blocks
   - Major performance improvements

3. **Apache Tomcat 10 Support** (MANDATORY)
   - Enhanced performance, scalability, latest Servlet specifications
   - **Breaking change:** incompatible with previous Tomcat versions

**Pre-Installation Requirements:**
- Update to Tomcat 10 before deploying
- Database migration with Migrator/Storage Manager requires manual action: manually delete old sequence before import

**Backward Compatibility:**
- Tomcat 10 update mandatory
- Roles `owner`, `potential_owner`, `watcher_owner` can no longer be assigned globally (causes auth errors)
- IPD version updated to `5` (new optional `priority` flag); migrated IPDs assume credentials registry default of `0`
- Deleting individual table cells may cause surrounding cells to shift unexpectedly
- XPath validation errors in condition branches now cause PDF preview to fail (previously ignored)
- Iteration targets on start elements in included processes fixed (reverts to 6.4 behavior, addressing 6.5 regression)

**Changelog Details:**

*Platform:*
- Added Tomcat 10 support
- Updated Apache FOP to 2.10
- Added custom `IRoleManager` configuration for flexible access control
- Added OIDC `state`/`nonce` validation against replay/CSRF attacks
- Updated IPD to version `5` with `priority` flag
- Fixed credential registry priority resolution
- Fixed impersonation error messages (swapped usernames in audit log)
- Fixed SOAP server compiling for wrong Java version
- Fixed caches without timeout not triggering removal listeners
- Fixed Storage Manager exports with empty Process Watchers
- Fixed execution cache clearing closing resources of running processes

*Library Updates:*
- commons-configuration to 2.12.0, jackrabbit to 2.22.0, mina-core to 2.2.4, mochito to 5.17.5, bytebuddy to 1.17.5, mysql-connector-j to 9.3, pdfbox to 2.0.34, poi-ooxml to 5.4.1, tika to 2.9.4

*Business Designer:*
- AI Assistance: Azure OpenAI engine (text + image generation)
- Signature element support
- Optional Content element (fills leftover page space)
- `element-label` property for all elements (displayed in Outline)
- `border-radius` shown in editor
- Wrapper element (propagates properties to children, requires POWER_USER/ADMIN)
- `shrink-to-fit` overflow option for dynamic content
- Rotated elements support (`reference-orientation`, not shown in editor, visible in preview)
- Form Field configuration dialog
- Refreshable naming dialog
- Building Blocks: infinite nested categories
- External Document improvements: `element-label`, double-click filepicker, dedicated submenu
- Image handling: loading indicators, TIFF rendering, uppercase extensions
- Test Data Management redesign
- Preview: configurable user rights for FOP Intermediate/IF; test case toggle; Composer Next requires BUSINESS_USER+
- Filepicker: XSL import, IF preview type, tile mode, improved thumbnails
- Multiple fixes across editor, styles, tables, template parts, images, data management

*Composer:*
- Disable continuous page break calculation (configurable default)
- Edit indicator with timestamp and author
- Image loading indicators
- Numbered and bulleted lists support
- Optional Content element rendering
- Rotated elements rendering (preview only)
- Font size in pt (replacing relative sizes)
- Signature element
- External links (Link element)
- Wrapper element
- AI Assistance: Azure OpenAI engine
- Insertion Points & Building Blocks: floating toolbar for reorder, search highlighting, category/subcategory organization, drag-and-drop reorder, tooltip labels, Refreshable improvements (auto-compare, change highlighting, non-blocking re-check)
- Removed: unused `document/validate` API endpoint
- Multiple fixes: page breaks, editor area, Insertion Points, Building Blocks, Refreshables (dozens of specific fixes)

*Process Engine:*
- Process messages in end states
- Task element parameter to block users from completing own tasks
- Volatile processes no longer lost after ~17 minutes
- Iteration targets fix (reverts to 6.4 behavior)
- Deprecated activity warning handling improved
- JDBC drivers in extension directory
- Extra module directories via `-a`/`-b` CLI options
- `getMetadata` API endpoint
- IPD version `5` with priority flag
- Wait state result XML namespace fix
- Bundler scripts namespace updated

*Template Designer:*
- Optional Content element
- Chart formatting validation (invalid `justify` mapped to `center`)
- List prefix/suffix dynamic distance values
- Multiple fixes: startup, text element addition, PDF errors, dynamic values, dependencies, navigation

*Task Manager:*
- Default 5-minute timeout for REST client

*Resource Explorer:*
- Fixed language selection during installation
- Fixed host configuration save warning

*Workplace 1:*
- Fixed template name encoding with special characters
- Fixed duplicate library entries in WAR file

---

### i-Edition 6.5 SP3 -- November 20, 2025

**Fixes:**

*Business Designer:*
- Fixed Base64-encoded images not rendering correctly

*Process Designer:*
- Fixed redirect callback server errors when setting up new OpenID Process Engine

*Process Engine -- Security:*
- Updated: org.eclipse.jetty:jetty-http to 10.0.26, io.netty:netty-codec to 4.1.126.Final
- Fixed prober services starting before warmup phase
- Fixed missing `processEngineId` tag in process responses
- Fixed processes stuck in ready status after waking from wait state during resource registration

*Template Designer -- Security:*
- Updated: org.verapdf:core to 1.26.5, commons-io to 2.14.0
- Fixed word overflow in dynamically inserted HTML tables with CSS
- Fixed errors when including PDF as image or external document element

---

### i-Edition 6.5 SP2 -- August 22, 2025

**Pre-Installation Requirements:**
- Database migration with Migrator/Storage Manager requires manual action: check clear action completed successfully; remove generated objects manually if needed

**Changelog:**

*Platform:*
- Updated Apache FOP to 2.10
- Improved LDAP security configuration: multiple subconfigurations supported
- Updated libraries: commons-configuration to commons-configuration2 2.12.0, commons-fileupload to 1.6.0, commons-lang3 to 3.18.0
- Removed commons-lang (replaced with infinica-inner-core and commons-lang3)
- Fixed SOAP server compiling for wrong Java version
- Fixed ActiveMQ vulnerabilities across web components
- Fixed Storage Manager exports with empty Process Watchers
- Fixed execution cache clearing closing resources of running processes

*Business Designer & Composer:*
- Improved UI with rebranding

*Process Engine:*
- Updated commons-beanutils to 1.11.0
- Fixed iteration targets on start elements (reverts to 6.4 behavior, addresses 6.5 regression)
- Improved deprecated activity warnings (now in diagnostic-log and application-log)
- Reduced log level for ProcessTerminateException
- Fixed sub-pipeline variable inheritance from parent pipeline homonyms (caused corrupted PDFs)
- Added `getMetadata` API endpoint

*Resource Explorer:*
- Improved UI with rebranding

*Workplace 1:*
- Fixed duplicate library entries in WAR file

---

## Section 3: Integration Apps

Release notes directories exist for the following integration apps but contain no versioned release content at this time:

- **Doxee App for Salesforce** -- no release notes published
- **Doxee App for SAP** -- no release notes published
- **Doxee App for Microsoft Dynamics 365** -- no release notes published

---

## Vulnerabilities & Security Summary

### Library Updates Across Releases

| Release | Key Library Updates |
|---|---|
| i-Edition 6.7 | activemq-client 6.1.6, commons-lang3 3.18.0, jackson 2.20.1, jaxb-core 4.0.5, jersey 3.1.11, netty 4.2.7.Final, netty-codec-http2 4.1.124, nimbus-oauth 11.30.1, undertow-core 2.3.20 |
| i-Edition 6.6 | Tomcat 10 (mandatory), commons-configuration 2.12.0, jackrabbit 2.22.0, mina-core 2.2.4, mysql-connector-j 9.3, pdfbox 2.0.34, poi-ooxml 5.4.1, tika 2.9.4 |
| i-Edition 6.5 SP3 | jetty-http 10.0.26, netty-codec 4.1.126, verapdf-core 1.26.5, commons-io 2.14.0 |
| i-Edition 6.5 SP2 | FOP 2.10, commons-configuration2 2.12.0, commons-fileupload 1.6.0, commons-lang3 3.18.0, commons-beanutils 1.11.0; ActiveMQ fixes |
| DP3 3.48 | Redis updated, Electronic Invoicing signing library updated |

### Deprecations

| Release | Deprecation |
|---|---|
| i-Edition 6.7 | `PdfFormCreator` activity deprecated; replaced by `PdfBoxFormCreator` |
| i-Edition 6.6 | Workplace 1 enters maintenance-only mode (critical fixes + security patches only) |

---

## Third-Party Software Requirements

| Component | Requirement | Since |
|---|---|---|
| Application Server | Apache Tomcat 10 (mandatory) | i-Edition 6.6 |
| Rendering | Apache FOP 2.10 | i-Edition 6.5 SP2 / 6.6 |
| Java | Upgraded version required for PDF/UA with FOP 2.10 | DP3 3.48 |
| Cache | Redis (updated in 3.48) | DP3 3.48 |
| IPD | Version 5 (credentials registry `priority` flag) | i-Edition 6.6 |

---

## Supported Versions Matrix

| Product | Active Releases | Status |
|---|---|---|
| DP3 | 3.49.x (current), 3.48.x (maintenance) | Cloud-managed |
| i-Edition | 6.7 (current), 6.6 (supported), 6.5 SPx (maintenance) | On-premise |
| Workplace 1 | Maintenance only since 6.6 | Security/critical fixes only |
| Workplace 2 | 6.6+ (new), 6.7 (current) | Active development |

---

## Documentation Availability (from Getting Started Roadmap)

**i-Edition components** (English & German): Workplace 2, Composer, Process Engine, Process Designer, Business Designer, Template Designer, Content Repository, Resource Explorer, Task Manager, Security Config, Third-Party Integration, API

**DP3 components** (English): Batch Jobs, Batch Workflows, Batch Workloads, Data Transformation, Digital Archive, Home, On-Demand Jobs, On-Demand Workflows, Output Management, Repository, Settings

**Planned Q2 2026**: API (DP3), Staging & Aggregation, Tracking & Reporting

**Getting Started**: Documentation portal at docs.doxee.com features AI-powered search (natural language queries), traditional keyword search with filters, and category browsing. Support available through service contract contacts.

---

## Key Terminology

- **DP3**: Doxee Platform 3 (cloud-native CCM/CXM)
- **i-Edition**: On-premise document composition suite
- **Batch Production**: High-volume document processing pipeline
- **On-Demand Production**: Single/small batch document generation
- **Headlight**: Analytics and engagement monitoring
- **Pvideo**: Personalized video generation
- **Pweb**: Personalized web page generation
- **Composer**: Web-based template editing application
- **Business Designer**: Web-based template creation/management
- **Template Designer**: Desktop template design tool
- **Workplace**: Interactive document workflow execution (Business Cases)
- **Process Engine**: Framework for defining/executing activity-based processes
- **Digital Archive**: Document storage with legal compliance
- **Cloud Analytics**: Data analytics and reporting
- **Output Management**: Document rendering pipeline configuration
- **Data Transformation (DT)**: Input data transformation engine
- **Route Files**: Conditional file routing in batch workflows
- **Staging & Aggregation**: Data aggregation and staging services
- **Human Tasks**: Interactive workflow steps in Workplace
- **Building Blocks**: Reusable content components in Composer
- **Insertion Points**: Document locations where Building Blocks can be placed
- **Refreshables**: Auto-updating content elements in Composer
- **IPD**: Infinica Process Definition (process configuration format)
- **BOM**: Bill of Materials (XML metadata for job ingress)
