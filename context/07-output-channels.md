# 07 - Output Channels & Engagement

> Context Bible: Doxee Platform output channels, delivery methods, and engagement tools.
> Sources: output-management (44 files), pweb (10 files), pvideo-designer (57 files), pvideo (1 file), workplace-2-6-7 (26 files), digital-archiving (10 files)

---

## 1. Output Management (Document Composition)

### 1.1 Overview

Output Management is Doxee's Variable Data Printing (VDP) and TransPromo document composition system. It transforms raw data into formatted, personalized multi-channel output through a visual design environment.

**Core Workflow**: Data Input -> Template Design -> Document Composition -> Multi-Format Output -> Multi-Channel Delivery

### 1.2 Editor Views

| View | Purpose |
|------|---------|
| **Project View** | Entry point; lists all output configuration projects |
| **Output View** | Configure targets, serializers, custom fields, fonts, colors, and output settings |
| **Data View** | Define data sources and field mappings for document composition |
| **Page Masters** | Design page layouts with reusable page master templates |
| **Families** | Group related document templates into families |
| **Documents/Rules/Layout** | Define document structure, business rules, and layout composition |
| **Contents** | Manage content elements (text blocks, images, barcodes, dynamic fields) |
| **Preview** | Real-time document preview with test data, zoom, navigation, field highlighting |

### 1.3 Preview View Features

- Page-by-page navigation with current/total page display
- Zoom in/out controls
- Field highlighting to show dynamic data insertion points
- Preview of composed documents with actual or test data
- Supports all output formats for visual verification

### 1.4 Output Configuration (Output View)

The Output View is the central configuration hub for all output settings.

#### Configuration Structure (XML-based)

```
<outputConfiguration>
  <targets>           <!-- Output format/channel definitions -->
    <target>
      <serializers>   <!-- Format-specific output processors -->
      <customFields>  <!-- User-defined metadata fields -->
      <fonts>         <!-- Font mappings and substitutions -->
      <colors>        <!-- Color definitions and mappings -->
    </target>
  </targets>
</outputConfiguration>
```

#### Export/Import

- Full configuration export to XML for backup, migration, versioning
- Import from XML to restore or replicate configurations
- Supports configuration sharing between environments

### 1.5 Supported Output Formats

| Format | Type | Key Capabilities |
|--------|------|-----------------|
| **PDF** | Electronic | Full-featured document output with fonts, images, barcodes, bookmarks |
| **AFP** | Print Stream | IBM Advanced Function Presentation for high-volume print |
| **Raster** | Print Stream | Bitmap-based output for label/industrial printers |
| **PCL** | Print Stream | HP Printer Command Language for laser printers |
| **PostScript** | Print Stream | Adobe PostScript for typesetting-quality output |
| **Excel** | Electronic | Spreadsheet output with data tables |
| **Email** | Electronic/Delivery | HTML email with embedded content and attachments |
| **HTML** | Electronic | Web-ready document output |
| **CSV** | Data | Comma-separated data export |
| **Interactive Communication** | Electronic | Dynamic interactive document experiences |

### 1.6 Target Settings

Targets define the output destination and format configuration.

#### General Target Properties

| Setting | Description |
|---------|-------------|
| Target name | Unique identifier for the output target |
| Output format | PDF, AFP, Raster, PCL, PostScript, Excel, Email, HTML, CSV, Interactive |
| Output path | File system path for generated output files |
| Naming pattern | Dynamic file naming with system variables |

#### Font Management (Font Tab)

- Font mapping: Map logical font names to physical fonts
- Font substitution rules for cross-format compatibility
- Font embedding control (embed/reference/subset)
- TrueType, OpenType, Type1 font support
- Font resolution and fallback chain configuration

#### Color Management (Color Tab)

- Named color definitions (CMYK, RGB, Spot colors)
- Color mapping between formats (screen vs. print)
- ICC color profile support
- Spot color library management

#### External Image Library

- Central image repository for shared assets
- Image resolution settings (DPI control per target)
- Image format conversion (TIFF, JPEG, PNG, BMP, SVG)
- Image path resolution (absolute vs. relative)

#### Electronic Invoicing

- Compliance with electronic invoicing standards
- XML/Peppol format generation
- Digital signature integration
- Regulatory metadata embedding

#### Composer Options

- Document composition engine settings
- Memory allocation and performance tuning
- Parallel processing configuration
- Error handling and recovery settings

### 1.7 Serializer Settings

Serializers are output processors that transform composed documents into specific formats.

#### Serializer Properties

| Property Category | Settings |
|------------------|----------|
| **General** | Output encoding, compression, page size defaults |
| **Print Job** | Job ticket settings, printer-specific options |
| **Spool Management** | Spool file creation, naming, splitting rules |
| **Custom Fields** | User-defined metadata attached to output |

#### Lots (Batching)

- Group documents into logical lots for batch processing
- Lot-based sorting and sequencing
- Lot-level metadata and tracking
- Dynamic lot assignment based on document attributes
- Lot splitting rules (by count, by attribute value, by size)

#### Envelope Settings

- Envelope format definitions (C4, C5, DL, custom sizes)
- Inserter control marks for automated envelope stuffing
- Multi-piece mail assembly rules
- Window envelope alignment settings
- Address block positioning

#### Tray Management

- Printer tray assignment per page/section
- Tray selection based on paper type, size, color
- Tray fallback chains
- Dynamic tray switching within documents

#### Overprint Settings

- Pre-printed form overlay configuration
- Electronic overlay positioning
- Overprint merge order (background/foreground)
- Conditional overprint based on document rules

### 1.8 Files & Metadata Settings

#### Print Job Settings

| Setting | Description |
|---------|-------------|
| Job name pattern | Dynamic naming with system variables |
| Job priority | Priority level for print queue management |
| Job metadata | Custom fields attached to the print job |
| Notification settings | Job completion/error notification rules |

#### Spool Set Settings

- Spool file grouping and organization
- Spool set naming conventions
- Spool set-level metadata
- Spool file format selection per set

#### Multichannel Distribution

- Route documents to multiple channels simultaneously
- Channel selection rules (print + email + archive)
- Per-channel format optimization
- Channel-specific metadata enrichment
- Conditional channel routing based on document data

#### Error Management

- Error handling policies (stop, skip, log)
- Error notification configuration
- Retry policies for transient failures
- Error document quarantine

### 1.9 Data View

- Define data sources (XML, CSV, database, flat file)
- Field mapping between data sources and document templates
- Data transformation rules
- Data validation and default values
- Hierarchical data structure support (master-detail)

### 1.10 Integration with Business Designer

- Templates designed in Business Designer are consumed by Output Management
- Round-trip editing between design and composition
- Shared resource libraries (images, fonts, styles)
- Version management of templates

### 1.11 System Attributes (524 Total)

System attributes provide metadata at every level of the output hierarchy.

| Category | Count | Key Attributes |
|----------|-------|---------------|
| **Print Job** | ~65 | PJJobId, PJDocumentsCounter, PJTotalPages, PJLotId, PJTimestamp, PJePublishCustomField1-10, PJPersonCoverExtraPagesCounter |
| **Shipment** | ~30 | SHShipmentId, SHDocumentCount, SHTotalPages, SHAddress fields |
| **Envelope** | ~25 | ENEnvelopeId, ENTotalSheets, ENPageCount, ENFormat, ENTrayId |
| **Lot** | ~20 | LOLotId, LODocumentCount, LOTotalPages, LOStartPage, LOEndPage |
| **Spool Set** | ~15 | SSSpoolSetId, SSFileCount, SSFormat, SSTotalPages |
| **Spool File** | ~40 | SFFileName, SFFileSize, SFSpoolfilesAbsPath, SFPageCount, SFFormat |
| **Document** | ~200+ | DODocumentId, DOTotalPages, DOTotalTemplates, DOTotalPersCoverPages, DOTotalFillPages, DOTotalPersCoverExtraSheets, DOTimestamp, DODatafileStartPos, DOAddress fields, DOCustom1-50 |
| **Page** | ~60 | PAPageNumber, PAPageSize, PATrayId, PADuplex, PAOrientation |
| **Section** | ~70 | SECSectionId, SECPageCount, SECTemplateId, SECFamily |

These attributes can be referenced in:
- Custom field expressions for dynamic metadata
- Conditional rules for document processing
- File naming patterns
- Lot/envelope/tray assignment rules
- Serializer record generation (TR550/TR560 packager formats)

### 1.12 Sample Output Configuration (Key Elements)

The XML output configuration includes:
- **Target definitions** with format-specific serializer chains
- **Custom field expressions** using system attribute references, concatenation, replacement, and conditional logic
- **Font maps** with physical-to-logical font mapping
- **Color maps** for named color definitions
- **Spool format flags** controlling output structure
- **Email lot XML templates** with HTML body, dynamic field replacement ($NAME, $EMAIL), and base64-encoded content
- **Packager records** (TR550/TR560) for postal/logistics integration with header and detail records containing lot, document, address, and tracking information

---

## 2. PWeb (Personalized Web)

### 2.1 Overview

PWeb creates HTML5 interactive personalized web pages delivered via personalized URLs (pURLs). Pages are data-driven, one-to-one communications combining personalization with interactivity.

**Key Differentiator**: Unlike static PDF documents, PWeb pages are dynamic HTML5 experiences with charts, tables, forms, animations, and real-time data binding.

### 2.2 Architecture

| Deployment Model | Description |
|-----------------|-------------|
| **Embedded Dependencies** | All resources (CSS, JS, images) bundled within the HTML page; fully self-contained |
| **Linked Dependencies** | Resources loaded from external CDN/server; smaller page size, shared caching |

### 2.3 Distribution Channels

| Channel | Mechanism |
|---------|-----------|
| **Email** | HTML email with link to personalized page |
| **pURL (Direct)** | Unique URL resolves directly to the personalized content |
| **pURL (Indirect)** | Unique URL triggers server-side data lookup, then renders content dynamically |
| **Web Embedding** | Pages embedded in portals, CRM, or customer-facing websites |

### 2.4 Platform Integration

| Component | Role |
|-----------|------|
| **DT (Document Template)** | HTML template with placeholders for personalized data |
| **DA (Digital Archiving)** | Store and serve generated pages; pURL document resolution |
| **DC (Document Composition)** | Merge data with templates to produce personalized pages |
| **Batch Production** | Bulk generation of personalized pages from data files |
| **T&R (Tracking & Reporting)** | Track page views, interactions, conversions, engagement metrics |

### 2.5 Authoring & Template Structure

#### Template Sections (5 Mandatory)

| Section | Purpose |
|---------|---------|
| **Data** | JSON data model defining personalization variables and data structures |
| **Template** | HTML structure with AngularJS binding expressions (`{{variable}}`) |
| **Styles** | CSS stylesheets for layout and responsive design |
| **Components** | JavaScript libraries, charts, tables, interactive widgets |
| **Static** | Static assets (images, fonts, icons) |

#### Data Binding

- JSON data model with hierarchical structure
- AngularJS expressions for dynamic content: `{{customer.name}}`
- Conditional rendering with `ng-if`, `ng-show`
- List rendering with `ng-repeat` for tables and dynamic lists
- Data transformations and filters

#### Interactive Features

| Feature | Technology |
|---------|-----------|
| **Charts** | Chart.js, D3.js integration for data visualization |
| **Tables** | Dynamic sortable/filterable data tables |
| **Forms** | Input forms with validation for data collection |
| **Tabbed Navigator** | Multi-tab content organization |
| **Animations** | CSS3 and JavaScript animations |
| **Responsive Design** | Bootstrap-based responsive layouts |

### 2.6 Advanced Topics

- AngularJS controllers for complex interaction logic
- Bootstrap grid system for responsive layouts
- Custom JavaScript modules for specialized functionality
- Cross-browser compatibility (Chrome, Firefox, Safari, Edge)
- Performance optimization (lazy loading, minification)

### 2.7 Limitations

- AngularJS 1.x based (legacy framework)
- Single-page architecture per pURL
- Template size limits for embedded dependency mode
- JavaScript execution dependent on client browser capabilities

### 2.8 Comparison: PWeb vs PDF

| Aspect | PWeb (HTML5) | PDF |
|--------|-------------|-----|
| Interactivity | Full (charts, forms, animations) | Limited (static) |
| Responsiveness | Fully responsive | Fixed layout |
| Tracking | Real-time engagement metrics | Download tracking only |
| Personalization | Dynamic, real-time | Static at generation time |
| File size | Variable (linked mode: small) | Fixed at generation |
| Offline access | Requires connectivity | Fully offline |

---

## 3. PVideo (Personalized Video)

### 3.1 Overview

PVideo creates personalized, interactive videos for one-to-one customer engagement. Videos are composed using PVideo Designer and can be either static (pre-rendered) or dynamic (rendered on-demand).

### 3.2 PVideo Designer

#### Key Capabilities

| Capability | Description |
|-----------|-------------|
| **No-Code Composition** | Drag-and-drop video creation without programming |
| **AI Script Generation** | AI-assisted script writing for text-to-speech narration |
| **Enriched Personalization** | Dynamic text, images, and data overlays in video content |
| **Interactive Elements** | Clickable CTAs (Call-to-Action) within videos |
| **User-Directed Storytelling** | Branching video paths based on viewer choices |
| **AI Text-to-Speech** | Multiple voices, languages, and speech styles |
| **Renderless HTML5** | Browser-native playback without plugins |

#### Core Concepts

| Concept | Description | Identifier |
|---------|-------------|-----------|
| **Project** | Top-level container for a video composition | UUID |
| **Storyboard** | Ordered sequence of scenes defining the video narrative | UUID |
| **Scene** | Individual video segment with media, text, audio, and interactions | Ordered within storyboard |
| **Pop-up** | Overlay content triggered by CTA interactions | Linked to scenes via CTA |
| **Mapping** | Data-to-scene binding configuration for personalization | Per-scene |
| **Production** | Output generation (static pre-render or dynamic on-demand) | Triggered from Designer/Platform/API |

#### Project Settings

| Setting | Options |
|---------|---------|
| **Name** | Project display name |
| **Thumbnail** | Project preview image |
| **UUID** | Unique identifier (auto-generated) |
| **Aspect Ratio** | 16:9, 9:16, 1:1, 4:5 |
| **Color Palette** | Brand colors for consistent styling |
| **Fonts** | Custom font library for text overlays |
| **Soundtrack** | Background audio track |
| **Analytics** | Tracking and engagement measurement configuration |

#### Scene Editor

| Component | Features |
|-----------|----------|
| **Media** | Video clips + images; layered composition |
| **Layouts** | Info overlays (text boxes, data fields) + visual filters |
| **Audio** | Sound effects + AI Text-to-Speech (TTS) with script editor |
| **Interactions** | CTA elements with configurable event types |
| **Text** | Dynamic text elements with personalization variables |

#### CTA Event Types

| Event | Action |
|-------|--------|
| **Open Link** | Navigate to external URL |
| **Open Video** | Play another video |
| **Mail To** | Open email client with pre-filled address |
| **Call To** | Initiate phone call |
| **Open Popup** | Display pop-up overlay within video |
| **Go To Scene** | Jump to specific scene (branching narrative) |

#### Text-to-Speech (TTS)

- AI-powered voice synthesis
- AI script generation from prompts
- Multiple languages and voice options
- Speech rate and style controls
- Per-scene audio narration

#### Storyboard Management

- Create/connect/remove scenes in sequence
- Drag-and-drop scene reordering
- Scene duplication for rapid iteration
- Pop-up integration via CTA elements
- Preview entire storyboard flow

#### Mapping Editor

- Sidebar with per-scene data tabs
- Playback area for preview with mapped data
- Advanced tab for analytics, pURL, and dynamic storyboard configuration
- Map data fields to scene elements (text, images, audio scripts)
- Dynamic storyboard rules for conditional scene inclusion

#### Productions

| Type | Description |
|------|-------------|
| **Static** | Pre-rendered video files; higher quality, fixed content |
| **Dynamic** | Rendered on-demand per viewer; real-time personalization, lower latency |

Production triggers:
- **From Designer**: Manual production for testing/preview
- **From Platform**: Batch production via Doxee Platform workflows
- **From API**: Programmatic production via REST API integration

---

## 4. Workplace 2

### 4.1 Overview

Workplace 2 is a web portal for end-to-end execution of interactive and collaborative document workflows. Users initiate "Business Cases" and perform all necessary actions within a unified interface.

**Key Use Cases**: CRM enhancement, system integration (Salesforce, SAP, Microsoft Dynamics), personalized customer service, document creation and approval workflows.

### 4.2 Key Capabilities

| Capability | Description |
|-----------|-------------|
| **CRM Enhancement** | Manage support tickets, billing, notifications |
| **System Integration** | Connect ERP/CRM systems for document preview and validation |
| **Personalized Service** | Enrich communications with custom data and offers |
| **Customizable Portal** | Configure forms, data sources, and approval workflows |
| **Granular Access Control** | Precise privilege and responsibility mapping |

### 4.3 Core Concepts

| Concept | Description |
|---------|-------------|
| **Business Case** | Definition of an interactive process (template) |
| **Business Case Instance** | Running instance of a Business Case with unique ID |
| **Human Task** | Interactive step requiring user input within a Business Case |
| **Task Manager** | Backend service managing task lifecycle and assignment |
| **Process Engine** | Executes process definitions (IPD format) behind the scenes |

### 4.4 User Interface

| Tab | Purpose |
|-----|---------|
| **Dashboard** | Quick access to favorited and recently viewed Business Cases |
| **Business Cases** | Card/tile overview of all available Business Case definitions |
| **Business Case Instances** | Searchable/sortable table of running instances |
| **Tasks** | Searchable/sortable table of all Human Tasks |
| **Problems & Events** | Event/warning/error log with filtering |

**Task Editor**: Core work interface with left sidebar (navigation, workflow steps) and large workspace (Human Task editing area).

### 4.5 Business Case Lifecycle

```
Business Case Definition (template)
  |
  v  [Start]
Business Case Instance (running)
  |
  v  [Human Tasks executed sequentially]
  |
  v  [All tasks completed]
Finished
```

#### Business Case Instance States

| State | Description |
|-------|-------------|
| **Created** | Instance created, not yet started |
| **Started** | Instance is active, tasks being executed |
| **Finished** | All tasks completed successfully |
| **Failed** | Process execution encountered an error |
| **Terminated** | Manually terminated by user (irreversible) |

#### Business Case Detail Fields

| Field | Description |
|-------|-------------|
| Configuration File | XML configuration filename |
| Target Folder | Folder location within Workplace |
| Name, Summary, Full Description | Business case metadata |
| Created by, Created at, Last updated at | Audit trail |

### 4.6 Human Task Lifecycle

| State | Description |
|-------|-------------|
| **Created** | Task instantiated by Process Engine |
| **Open** | Task available for assignment |
| **Locked** | Task checked out by a specific user |
| **Completed** | Task input provided, waiting for process continuation |
| **Finished** | Task fully processed |
| **Terminated** | Task manually terminated (irreversible) |

#### Task Management Features

- **Assignment**: Auto-assigned based on BC config; manual reassignment possible
- **Potential Assignees**: Users with required privileges
- **Save & Close**: Unlock (save/discard) or keep locked for current user
- **Blacklisted Users**: Users blocked from editing specific tasks
- **Bulk Actions**: Multi-select operations from Tasks tab
- **Search/Filter**: By state, date, assignee, task ID, BC ID, process element, priority

### 4.7 Human Task Types

All Human Tasks share common configuration (General + Basic Input/Output parameters) and are configured in Process Designer.

#### Basic Input Parameters (All Types)

Configured per task in Process Designer with general task properties (name, description, assignee rules, priority).

#### Basic Output Parameters (All Types)

Standard output providing task completion status and metadata.

#### Task Type Catalog

| Human Task Type | Purpose | Key I/O |
|----------------|---------|---------|
| **Composer** | Edit document templates in embedded Composer HTML5 view | In: composerUrl, templateNames, inputXml, idxDocumentNames; Out: idxDocuments, xmlOutputData |
| **Data List** | Display external data in searchable/sortable table; user selects rows | In: dataSet (XML with columns/rows config); Out: selectedRows (XML) |
| **Email** | Write and send email from within task editor | In: to, cc, bcc, subject, text, visibility flags; Out: to, cc, bcc, subject, text |
| **Excel** | Display Excel file as HTML table; supports XLSX/XML/XML_XLSX output modes | In: excelInput (XML); Out: excelOutput (XML) |
| **File List** | Display configurable file list with select/preview actions | In: dataSet (XML with source-folder, documents); Out: dataSet (selected files XML) |
| **File Upload** | Upload files with configurable type/size constraints | In: titleMessage; Out: files (XML with base64 content) |
| **Generic** | Flexible task type accepting JSON task definition | In: definition (JSON); Out: none |
| **Get User Context** | Retrieve username of current user (no UI, auto-completes) | In: basic only; Out: userName |
| **HTML** | Display HTML page with fillable forms and pre-filled data | In: htmlContent, data (JSON); Out: data (XML with form field values) |
| **PDF Preview** | Preview one or more PDF documents | In: pdfsBase64, labels; Out: basic only |
| **Repository Browser** | Browse file repository; user selects resources | In: uri, filter (e.g., *.itx); Out: selectedResources |
| **Simple Generic Search** | Search interface triggering background process (e.g., DB query) | In: process (IPD path); Out: text (search input), selectedRows (XML) |
| **Summary** | Display predefined text/summary to user | In: summary (XML with sections/entries); Out: basic only |

### 4.8 Administration & Configuration

#### XML Configuration File (`workplace.xml`)

| Element | Description |
|---------|-------------|
| `storage` | SQL database connection for Business Case data |
| `taskManager` | Task Manager REST/SOAP API URL + credentials |
| `processEngine` | Process Engine REST/SOAP API URL + credentials; `watch="true"` for events |
| `taskDefinitions` | Custom Human Task module directory |
| `userAccessConfiguration` | User store (XML file, LDAP, etc.) |
| `security/authentication` | Auth mechanism (Basic realm, SSO, etc.) |
| `security/audit` | Audit logging (Log4j) |
| `security/roles` | Role assignments and custom role definitions |
| `documentation` | Documentation URL |

#### Standard Roles

| Role | Scope |
|------|-------|
| `businessUser` | Standard workflow user |
| `supervisor` | Oversee and manage tasks |
| `manager` | Business Case management |
| `admin` | Full administrative access |

#### Custom Role Privileges

`authenticated`, `admin`, `createBusinessCaseDefinition`, `readBusinessCaseDefinition`, `writeBusinessCaseDefinition`, `deleteBusinessCaseDefinition`, `startBusinessCase`, `terminateBusinessCaseInstance`, `deleteBusinessCaseInstance`, `readBusinessCaseInstance`, `createFolder`, `readFolder`, `writeFolder`, `deleteFolder`

### 4.9 Installation

- **Prerequisites**: OpenJDK, Apache Tomcat, Relational database
- **Deployment**: WAR file to `$TOMCAT/webapps`, config files to `$TOMCAT/infinica`
- **Custom Tasks**: Module definitions in `modules/modules.json`; optional `taskTypes.xml` for Task Manager registration
- **URL Handling**: RewriteValve required for SPA routing

### 4.10 Troubleshooting

| Problem | Possible Cause | Resolution |
|---------|---------------|------------|
| General errors | Connected apps misconfigured (Composer, Task Manager, Process Engine) | Verify app configuration and connectivity |
| General errors | External services/databases unavailable | Check service status and configuration |
| Missing images | Resources not available or improperly linked | Verify resource paths and availability |
| Human Task fails to display | Task type not configured or not registered | Check process configuration and Workplace config |
| Process execution failed | Process definition error | Check process configuration in Process Designer |

---

## 5. Digital Archiving

### 5.1 Overview

The Digital Archiving Portal provides secure document storage and retrieval through metadata-based search. It serves as the front-end to Digital Archiving Store resources.

**Key Capabilities**: Customizable metadata search, CSV batch search, multi-format export, document versioning, retention management, pURL integration.

### 5.2 Architecture

```
Document Sources (Workflows, API, Manual Upload)
  |
  v
Digital Archiving Store (storage + indexes)
  |
  v
Digital Archiving Portal (search + retrieval UI)
  |
  v
Document Consumers (Download, pURL access, Export)
```

### 5.3 Digital Archiving Stores

#### Store Configuration

| Component | Description |
|-----------|-------------|
| **Document Categories** | Logical containers grouping documents of the same type |
| **Custom Indexes** | Business metadata fields (customer ID, date, etc.) |
| **System Indexes** | Platform-generated metadata (document ID, timestamps, etc.) |
| **Access Endpoints** | Platform and Portal endpoint configurations |

#### Document Categories

| Setting | Description |
|---------|-------------|
| **Alias** | Category name (1-100 chars, case-sensitive) |
| **Custom Indexes** | Business-specific metadata fields |
| **System Indexes** | Platform-provided metadata fields |
| **Filename Index** | Override original filename with index value |
| **Versioning** | Enable with identifier index + version index; auto-increments version |
| **Retention** | Enable with retention period (days); auto-deletes expired documents |

#### Index Types & Limits

| Type | Max Indexes | Value Format |
|------|-------------|-------------|
| **String** | 50 | Alphanumeric, max 250 chars |
| **Number** | 10 | Numeric values |
| **Date** | 10 | YYYY-MM-DD |
| **Time** | 25 | YYYY-MM-DD hh:mm:ss |
| **Clob** | 5 | Large text objects |

#### System Properties (Available as System Indexes)

| Property | Field | Type | Description |
|----------|-------|------|-------------|
| Document identifier | `id` | String | Unique document ID |
| Document category | `class` | String | Document category |
| Document title | `title` | String | Document title (always mandatory) |
| Document filename | `filename` | String | Original filename |
| Shipment identifier | `shipment` | String | Shipment ID |
| Version identifier | `version.id` | String | Version tracking ID |
| Job type | `app` | String | Application that loaded the document |
| Job identifier | `job` | String | Loading job ID |
| Created | `created` | Time | Upload timestamp |
| Updated | `updated` | Time | Last modification timestamp |
| Printed | `printed` | Time | Last print timestamp |
| Lot identifier | `segment` | String | Lot container ID |
| Purl identifier | `purl.id` | String | pURL generation identifier |

### 5.4 Portal User Interface

| Area | Function |
|------|----------|
| **Breadcrumb Bar** | Switch between available DA stores; URL-bookmarkable |
| **Criteria Area** | Search filters: category toggles + attribute value inputs |
| **Documents Area** | Results table with configurable/sortable columns |
| **Toolbar** | Download, export, clipboard, configure columns, details panel |

### 5.5 Search Capabilities

#### Manual Search

- Toggle document categories to include/exclude from search
- Enter attribute values with type-aware input (string, number, date, time)
- Number fields support Min/Max value operators
- Multiple search query boxes (up to 1000) with OR logic
- Results sorted by creation date (descending), max 1000 results

#### CSV Batch Search

- Upload CSV file with semicolon separator
- Header row must match document attribute aliases
- Each row = one search query (OR logic)
- Date format: YYYY-MM-dd; Datetime: YYYY-MM-dd HH:mm:ss
- Min/Max operators: prefix with `$MIN` / `$MAX`
- Max 1000 query rows per CSV

### 5.6 Document Operations

| Action | Description |
|--------|-------------|
| **Upload** | Select category, enter metadata, upload file; system indexes auto-populated |
| **Edit Metadata** | Update custom indexes and Document title (if editability enabled) |
| **Delete** | Select one or more documents; confirm deletion |
| **Download** | Select documents; download as files |
| **Copy to Clipboard** | Copy table page in CSV format (all or selected) |
| **Export** | Export as CSV or XLS file with custom filename |

### 5.7 Document Ingestion Methods

| Method | Use Case |
|--------|----------|
| **Workflow Tasks (Batch)** | Automated bulk archiving from composition workflows |
| **Workflow Tasks (On-Demand)** | Event-triggered single document archiving |
| **Digital Archiving API** | Programmatic integration from external systems |
| **Portal Upload** | Manual upload through the Portal UI |

---

## Cross-Channel Integration Summary

| Channel | Creation Tool | Delivery | Tracking | Archive |
|---------|--------------|----------|----------|---------|
| **Print** | Output Management | Spool files to printers/mail houses | Lot/shipment tracking | Digital Archive |
| **PDF** | Output Management | Email attachment, download, pURL | Download events | Digital Archive |
| **Email** | Output Management / Workplace | SMTP delivery | Open/click tracking | Digital Archive |
| **PWeb** | PWeb Templates | pURL (direct/indirect), web embedding | Page views, interactions | Digital Archive (DA) |
| **PVideo** | PVideo Designer | pURL, web embedding, email link | View duration, CTA clicks | Platform analytics |
| **Interactive Doc** | Output Management | Web delivery | Engagement metrics | Digital Archive |
| **Excel/CSV** | Output Management | File export | N/A | Digital Archive |
| **Workplace** | Business Designer + Workplace | Web portal | Task completion, audit | Process Engine logs |

### Shared Infrastructure

| Service | Role Across Channels |
|---------|---------------------|
| **Business Designer** | Template design for Output Management, Workplace, PWeb |
| **Content Repository** | Shared asset storage (images, fonts, templates) |
| **Process Engine** | Workflow orchestration for Workplace BCs and batch production |
| **Task Manager** | Human task lifecycle management for Workplace |
| **Digital Archive** | Universal document storage with metadata search and pURL serving |
| **Tracking & Reporting** | Cross-channel engagement metrics and analytics |
| **Platform Repository** | Resource management, versioning, access control |
