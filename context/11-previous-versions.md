# i-Edition 6.6 Previous Version Reference

<meta>
type: context-bible
domain: i-edition-6.6-previous-versions
source_files: 488 markdown files from product-guides-previous-versions/i-edition-docs-6-6/
compression_ratio: ~90%
compression_date: 2026-02-06
purpose: historical-reference-delta-from-6.7
</meta>

---

## Overview

i-Edition 6.6 (module version 6.6.2.0) is the previous release of the Doxee Platform. This document captures **only the delta and historical context** not already covered by the current 6.7 documentation. The core architecture, concepts, and component relationships remain fundamentally the same between 6.6 and 6.7; differences are noted per component below.

**Components in 6.6:** Process Engine, Business Designer, Composer, Template Designer, Process Designer, Content Repository, Workplace 2, Resource Explorer, Task Manager, Security Configuration, Third-Party Integration Guide

---

## 1. Process Engine 6.6

### Core Architecture (unchanged in 6.7)
- Graph-based process execution engine; processes defined in Infinica Process Definition (IPD) files
- Processes composed of: Start/End elements, Mapping elements, Activities, Groups, Loops, Decisions, Wait Elements, Tasks, Scripts, Includes
- Pipeline-based data flow with typed data stores (standard format and simple format)
- Access via: CLI, SOAP, REST, embedded Java interfaces
- Persistence via save points; supports JPA (SQL), MongoDB, Redis storage backends

### 6.6-Specific Details
- **Module version:** All modules at 6.6.2.0
- **Available modules (32 total):** base, cmd, core, database-logging, email, fo-concatenation, fop, storage-jpa, json, log4j, log-analysis, lpr, messaging, storage-mongo, openpdf, pdfa-validation, pdfbox, pdf-forms, pdf-renderer (deprecated - use pdfbox), postscript-handler, reporting, process-engine-rest-client, process-engine-soap-client, processes, storage-redis, resource-access, rest, sap, service, sftp, soap, splitter, tasks, template-conversion, users, zip4j
- **PDF Renderer module:** Already marked as deprecated in 6.6 (uses Sun's obsolete PdfRenderer library); recommendation to use pdfbox module instead

### Wait State Types (5 types, unchanged)
- **timeout:** Simple interval-based delay
- **file:** Directory monitoring with pattern matching, recursive search, limit control
- **email:** POP-based email monitoring with address/subject/content pattern filtering
- **process:** Cross-engine process monitoring; can instantiate and start processes; supports async execution (timeout=0)
- **message:** JMS message queue/topic monitoring (requires messaging module)

### Process Lifecycle States
CREATED -> READY -> RUNNING -> (WAITING | BROKEN | ENDED | TERMINATED)
- Offline mode: prevents READY->RUNNING transition; breakpoints supported
- Health states: HEALTHY, BROKEN, DISPOSED, UNDISPOSED
- Volatile processes supported (no persistence)

### API Operations (SOAP + REST)
- **Lifecycle:** disposeProcess, instantiate, reload, recoverProcess, run, setAttribute, setBreakpoint, setInstanceConstants, setLogSettings, setOnline, setOwner, setPermissions, startProcess, terminateProcess, updateCredentials
- **Queries:** getAttributes, getInstanceConstants, getProcessSnapshot, findExecutions, validate, waitForProcess
- **Watchers:** createWatcher, getWatcher, deleteWatcher
- **Administration:** clearCache, getBrokerUri, getConstants, getFeatures, getMaintenanceLevel, getModules, getNodeState, getNodeStates, getTaskManagerUrl, listProcessDefinitions, listServices, setEngineOnline, setMaintenanceLevel, uncacheProcesses, version, waitForNoRunningProcesses
- **Service Management:** getServiceSnapshot, listServices, startService
- **Cluster:** clusterConnect, clusterDisconnect
- **Diagnostics:** checkSanity, getTelemetryData, garbageCollect

### Configuration Structure (6.6)
Key configuration sections: ID, Key Store, User Access, Security (Authentication & Access Roles), HTTP Probes (Startup/Liveness/Readiness), Server (SSL), API Settings, Credentials, Technical Credentials, Logging (Common/Data/Attributes), Process Configuration, Process Watchers, Thread Pools, Service Processes, Autoexec Processes, Persistence (Storage), System Tasks, Error Handling, Debugging, Constants, Partitions, Maintenance, Startup, Shutdown, Query, Scheduler, Cache, Janitor Service, Performance Logging, Compatibility, Messaging (JNDI Message Client)

### Process Definition Reference (6.6)
Covers: Process Definitions, Elements, Connections (Standard + Exception), Mappings (Sources: Literal/Parameterized Literal/Variable/XPath/URL/Null), Value Resolution, Targets (Variable/Iteration/Keep-Variables), Null Values/Defaults, Sub Pipelines, XPath Queries, Types/Conversions, Constants/Attributes, Credentials Registry, Logging configuration within processes.

### 6.6 Examples
Hello World, Calculate, Calculate Advanced, PDF Generate, Decisions, Loop, Group with Exception Handling, Wait State, File Watcher, Human Tasks, Workplace Process

---

## 2. Business Designer 6.6

### Purpose (unchanged in 6.7)
Web-based template designer for creating document templates (.ITX files) using XSL-FO standard. Combines static content (headers, logos) with dynamic content (data fields, conditions, calculations, formatting rules). Data must be in XML format.

### 6.6 Capabilities
- **Content types:** Static text, dynamic data fields, condition elements, calculations, logical operations, formatting rules
- **Collections:** Template parts (reusable blocks), Page Masters (page settings), Style Sheets (formatting), Global Variable Packages
- **File format:** .ITX (XSL-FO based)
- **Data connection:** XML test data files; supports multiple XML data sources per template
- **Editor features:** Surface/window sections, content structure, data connection test cases, metadata, output formats, error/event window, decimal formats, styles concept extension, images, lists, numbering, tables, comments, elements, forms, static page contents (headers/footers/page numbers), page break/page settings/page master, template parts, library, Composer refreshables concept
- **AI Assistance (present in 6.6):** Integrated AI tool supporting text/image generation, translation, summarization, rephrasing. Providers: OpenAI (ChatGPT), Mistral AI, DeepL (translations only), Gemini AI, Azure OpenAI. Chat-based interface with keyboard shortcut Alt+Shift+C.
- **Other features:** Spell check, template comparison, permissions, versioning, keyboard shortcuts

### Developer Guide (6.6)
- Configuration: business-designer.properties (main config), business-designer-roles.properties (role mapping)
- AI provider configuration: OpenAI, Mistral, DeepL, Google Gemini, Azure OpenAI (each with separate config blocks)
- User access, FOP config, Content Security Policy configuration
- Installation: standard web application deployment

---

## 3. Composer 6.6

### Purpose (unchanged in 6.7)
Web application for editing and processing document templates created in Business Designer into finished documents. Supports preview, edit, approve, finalize workflow. Output: PDF, DOCX.

### 6.6 Capabilities
- **Document composition elements:** Text, Paragraph, List, Form elements, Image, Table, Link, Insertion Point, Refreshable, Page Break, Content Flipper
- **Editor features:** Library, Find & Replace, Editor View Settings, Shortcuts, Hyphenation, Page Settings, Spell Check, Editability controls, Units, Autocomplete, Change Tracking, Comments, GPS Location
- **AI Assistance (present in 6.6):** Same capabilities as Business Designer - OpenAI, Mistral, DeepL, Gemini, Azure OpenAI. Free-form prompts and range-selected context modification (summarize, rephrase, translate).

### Developer Guide (6.6)
- Overview, Installation, Configuration, User Access, Security Configuration

---

## 4. Template Designer 6.6

### Purpose (unchanged in 6.7)
Desktop application (Eclipse RCP) for creating and editing document templates. Lower-level than Business Designer; provides full control over XSL-FO template structure.

### 6.6 Capabilities
- **Installation:** Desktop application (Eclipse-based)
- **Editor:** Full template editing with multiple views
- **Document Structure:** Namespaces, Page Masters (dimensions/margins/body margins/extents/precedence/region names/complex page master), Bookmarks (references + definitions), Page Sequences, Template Parts, External Resources
- **Elements:** Full element editing capabilities
- **Features:** Access Control, Spell Check, Hyphenation, Free Texts, Tracing, Styles, Template Parts (reusable components), Internationalization, Master Templates, PDF/A Validation, Project Directory
- **Tutorial:** Step-by-step template creation tutorial included

### Developer Guide (6.6)
Standard installation and configuration documentation for Template Designer deployment.

---

## 5. Process Designer 6.6

### Purpose (unchanged in 6.7)
Desktop GUI tool (Eclipse RCP) for creating, editing, and testing IPD process definitions. Covers all features of the IPD format; eliminates need for manual XML editing.

### 6.6 Capabilities
- Installation, Quick Start guide
- **Editor:** Visual process editor with drag-and-drop elements
- **Views:** Multiple view types for process inspection
- **Actions:** Process element actions and operations
- **Properties:** Element property editing
- **Data Mode:** Data inspection and manipulation
- **Process Execution:** Test execution within designer
- **Preferences:** User preferences configuration
- **Project Directory:** Process project management
- **Glossary:** Terminology reference

### Developer Guide (6.6)
Design Tools Installation Guide: Introduction, Installation, Configuration

---

## 6. Content Repository 6.6

### Purpose (unchanged in 6.7)
Network-based filesystem (WebDAV) for storing and sharing Doxee files. Based on Apache Jackrabbit.

### 6.6 Features
- **Versioning:** Checkout-in-place (Delta-V extension); VERSION-CONTROL, CHECKOUT, CHECKIN, UNCHECKOUT methods. Automatic locking on checkout. Automatic versioning option for new files.
- **Version access:** Date-based (RFC 3339 format via URL parameter), filter-based (custom property filtering), base-path query parameters (preserving parameters in relative URL resolution)
- **Locking:** WebDAV standard LOCK/UNLOCK; automatic owner recognition; lock stealing (privilege-dependent)
- **XSL Generation:** Automatic XSL generation from .ITX templates via URL parameter (?xsl or ?xsl=fo)
- **ZIP Import/Export:** Full directory tree backup/restore with ACLs, versions. Parameters: acl, checkedOut, history, virtual, path, deploy, deployId/deployName/deployComment/deployTarget. Filter support (DASL-based property filtering). Scheduled imports (webdav-import-scheduler module).
- **Deployment Mode:** Signed ZIP packages with source verification, target verification. Uses private/public key pairs. Allows deployment without write access (infinica:deploy privilege).
- **Performance Statistics:** Queryable via properties on /.system folder (infinica:performance-statistics, infinica:property-performance-statistics)
- **Namespaces:** Custom namespace support for properties
- **Privileges:** Granular access control
- **Project Directory:** Repository organization

### Developer Guide (6.6)
Introduction, Installation, Bootstrap Configuration, Runtime Configuration, XML Configuration Files, Key Stores, Cluster Configuration

---

## 7. Workplace 2 (6.6)

### Purpose (unchanged in 6.7)
Web portal for end-to-end execution of interactive document workflows (Business Cases). Named "Workplace 2" in both 6.6 and 6.7.

### 6.6 Capabilities
- **Key capabilities:** CRM enhancement, system integration (ERP/CRM), personalized customer service, customizable web portal, granular access control
- **Core concepts:** Business Cases (IPD-based process definitions), Business Case Instances (running instances with unique IDs), Human Tasks (user input forms), Task Manager (backend coordination)
- **User interface:** Dashboard (favorites, recent), Business Cases tab (folder structure), Global search (with id: prefix), Business Case Instances view, Tasks view
- **Business Case management:** Find (search/browse/favorites), Start, View details (configuration file, target folder, name, summary, description, creator, timestamps), Favorite, Edit, Delete, Copy link
- **Business Case Instances:** Instance management and monitoring
- **Tasks:** Task list, task editing, task lifecycle management
- **Troubleshooting:** Documented troubleshooting guide

### Developer Guide (6.6)
Workplace 2 Developer Guide with Human Tasks configuration section

---

## 8. Resource Explorer 6.6

### Purpose (unchanged in 6.7)
Graphical tool for accessing files/folders on WebDAV servers and local filesystem. Available standalone and embedded in Template Designer and Process Designer.

### 6.6 Capabilities
- Introduction, Installation, Navigation, Actions, Search & Filter, Resource Access Layer configuration

---

## 9. Task Manager 6.6

### Purpose (unchanged in 6.7)
Server-side component for handling tasks. Required by Workplace 1 and Process Engine (Workplace processes). SOAP interface for communication.

### 6.6 System Requirements
- OpenJDK
- Apache Tomcat
- Relational database and/or local filesystem storage for task storage
- Optional: JDBC-enabled relational database

### 6.6 Configuration
- Introduction, Installation, Configuration, XML Configuration Files, Key Stores, Storage Configuration

---

## 10. Security Configuration 6.6

### Purpose (unchanged in 6.7)
Shared security management concepts across Doxee services (Process Engine, Content Repository, Task Manager).

### 6.6 Authentication Mechanisms
- Basic Authentication
- XML User Store
- Database User Store
- LDAP User Store
- Kerberos
- OpenID Connect (OIDC)
- Salesforce OAuth
- Generic OAuth Authentication (JWT)
- SSH Keys
- Infinica Authentication
- Impersonation
- Current Credentials

### 6.6 Security Concepts
- Authentication Mechanisms (generic configuration)
- User Stores
- Client Credentials
- Technical Credentials
- Audit Log
- XInclude support for sharing authentication configs across services

---

## 11. Third-Party Integration 6.6

### Apache FOP 2.8/2.9+
PNG image embedding behavior changed in FOP 2.8+. Fix: add penalty configuration for PreloaderRawPNG and ImageLoaderRawPNG to FOP configuration root level.

### Oracle Database
- **Automatic Sequence Generation:** Oracle doesn't correctly auto-create sequences. Must run SQL script manually before application start.
- **Query Performance (18c+):** Hibernate's `select * from all_sequences` query can be very slow. Fix: run `dbms_stats.gather_dictionary_stats` and `dbms_stats.gather_fixed_objects_stats` on Oracle server.

---

## 12. Key 6.6 vs 6.7 Observations

### What's Fundamentally the Same
- All core components exist in both versions with same basic architecture
- Process Engine IPD format, pipeline model, activity model unchanged
- Business Designer / Composer / Template Designer template model unchanged
- Content Repository WebDAV model unchanged
- Workplace 2 Business Case model unchanged
- Security authentication mechanisms same set
- AI Assistance already present in 6.6 (same providers: OpenAI, Mistral, DeepL, Gemini, Azure OpenAI)

### Version Numbering
- 6.6 modules are versioned 6.6.2.0
- All docs explicitly link to both 6.6 and 6.7 versions, confirming parallel documentation

### Deprecated in 6.6
- **PDF Renderer module** (pdf-renderer, 6.6.2.0): Uses Sun's obsolete PdfRenderer library. Recommendation: use pdfbox module instead.

### Migration Considerations (6.6 -> 6.7)
- Process definitions (IPD files) are format-compatible between versions
- Template files (.ITX) are format-compatible between versions
- Configuration file structures may have new options in 6.7 but 6.6 configs remain valid
- Content Repository data is preserved across versions (standard WebDAV/Jackrabbit)
- Third-party integration notes (FOP, Oracle) apply to both versions
