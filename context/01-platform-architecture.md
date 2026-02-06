# Doxee Platform -- Functional Architecture & Components

```yaml
meta:
  source: "Doxee Platform functional architecture and components.md"
  source_version: "V 1.5"
  source_date: "2025-06-10"
  compression_date: "2026-02-06"
  compression_ratio: "~70%"
  original_size: "~161KB"
```

---

## Platform Overview

| Property | Value |
|----------|-------|
| Product | Doxee Platform |
| Type | AI-powered low-code/no-code enterprise platform |
| Domain | Customer Communication Management (CCM) & Engagement |
| Deployment | SaaS, cloud-based, multi-environment or single-environment |
| Scalability | Elastic, horizontal scaling for spike handling |
| Functional Scopes | 6 core (Design, Engagement, Insights, Integration, Automation, Administration) + AI Foundation |

**Core Capabilities:** Data-driven personalized/interactive communications across every customer touchpoint. Template/video/workflow design, customer interaction, digital archive, customer insights, omnichannel process automation, platform administration.

**Marketplace Integrations:** Salesforce, SAP, Microsoft Dynamics 365 (out-of-the-box apps).

**Architecture:** Ecosystem of interoperable software components within a single platform. Standard installation includes out-of-the-box components; optional add-ons available at client request.

---

## 1. DESIGN

```
Scope: Collaborative communication design
Purpose: Design personalized interactive communications
Tools: AI-powered, low-code/no-code
```

### 1.1 Data Designer

| Property | Detail |
|----------|--------|
| Type | Visual low-code designer for data management |
| Users | Data management specialists |
| Interface | Web UI (intuitive, minimal training) |
| Input Formats | CSV, XML, Flat Files, TXT, PDF, AFP |
| Capabilities | Parsing, transformation, business logic mapping, data enrichment, data quality, data sampling, data formatting, data anonymization |
| Variable Support | Infinite variable relationships |
| Integration | Cross-domain data combination, breaks down silos |
| Platform Version Note | Data Transformation is DP3 only |

### 1.2 Template Designer

Two editions exist:

#### Business Designer (Web Edition)

| Property | Detail |
|----------|--------|
| Type | Web-based component |
| Model | Element-based, W3C standards |
| Output Formats | PDF, PDF/A, PDF/UA, PostScript, AFP, Word, static HTML, interactive HTML, responsive email, Text, Formatting Objects XML |
| Features | Static/dynamic content, layouts, pagination flows, conditional formatting, business logic, test cases |
| Reusability | Centralized styles, dynamic variables, page masters, reusable template parts (shared across templates) |
| Building Blocks | Reusable components with logic and parameters; local to template or shared as collections |
| Use Cases | Communications, contracts, invoices, bank statements, personalized advertising |
| AI | AI-powered tools for content generation |

#### Template Designer Desktop Edition (Rich Client)

| Property | Detail |
|----------|--------|
| Type | Rich-client application (installed locally) |
| Functionality | Identical to Business Designer for on-demand document generation |
| Users | Business users (marketing, operations, customer support, HR) |
| Import | Word files can be imported directly to minimize manual recreation |
| No-Code | No specialized knowledge required |

### 1.3 Video Designer

| Property | Detail |
|----------|--------|
| Type | AI-powered web-based non-linear video editor |
| Output | Personalized and interactive HTML5 videos |
| Composition | Visual timeline using stock content + dynamic templates |
| Personalization | Text, banners, images, voice (text-to-speech + audio libraries), tailored scenes per recipient data |
| Interactivity | In-depth pop-ups, links to data collection landing pages, CTAs (purchases, payments) |
| UDS Feature | User-Directed Storytelling -- recipients navigate their own storytelling paths; bi-directional communication |
| Distribution | Omnichannel via PURLs |

### 1.4 Process Designer

| Property | Detail |
|----------|--------|
| Type | Platform component for workflow design |
| Purpose | Create/configure document and communication generation processes |
| Steps | Automated steps + interactive user-driven (human) tasks |
| Task Types | Predefined types + custom tasks via HTML |
| Activities | Data retrieval, form conversion, API calls, email sending, XSL transformations |
| Custom Activities | Developed in Java, added as components |
| Process Definition | XML format; supports forks, loops, and other constructs |
| Integration | Seamless with Data Designer for data mapping |
| Multilevel | Combines automated functions with manual interventions |

### 1.5 Batch Workflows

| Property | Detail |
|----------|--------|
| Purpose | Large-volume document processing and multi-channel delivery |
| Execution | Scheduled mode with intelligent parallel processes |
| Features | Logistical tracking, sampling, production approvals, fully automated |
| Deployment | Cloud-based (multi-environment or single-environment) |
| Omnichannel | SFTP, Email, SMS, PEC, AppIO |
| SLA | Compliance with service agreements |

### 1.6 On-Demand Workflows

| Property | Detail |
|----------|--------|
| Purpose | Ad-hoc/immediate requests from user interactions or external events |
| Trigger | APIs (Web Services, REST) |
| Execution | Task-based, tied to specific document templates or output types |
| Scalability | Horizontal scaling of application components for spike management |
| Integration | End-to-end orchestration including recurring billing systems |

### 1.7 Output Management

| Property | Detail |
|----------|--------|
| Purpose | Configure output parameters during print spool generation |
| Manages | File structure, accompanying indexes, overprints, format conversion, metadata production |
| Features | OMR (Optical Mark Recognition) on pre-existing print spools, indexing data for document spools |

---

## 2. ENGAGEMENT

```
Scope: Interactive customer engagement
Purpose: Enhance customer engagement with interactive experiences + smart workplace
```

### 2.1 Interactive Documents

| Property | Detail |
|----------|--------|
| Purpose | Collaborative workspace for business cases with interactive documents |
| Features | Interactive document editing with defined modification areas, predefined text components |
| Workflow | GUI for executing document workflows from Process Designer; manages human-intervention tasks |

**Key Features:**
- CRM enhancement: technical support tickets, billing, notifications
- Personalized customer service: enriched one-to-one communications with customized data, offers, financial insights
- Customizable web portal: configure templates/forms, add data, trigger approval workflows
- Seamless ERP/CRM integration: document preview, workflow validation before dispatch
- Task Manager: coordinates tasks within interactive processes
- Granular access control: per-user content block modification (configured via Business/Template Designer)
- Flexible document structure: blocks added once or multiple times, placement based on predefined rules
- Formatting customization: font size, style adjustments
- Guidance: interactive comments, mouse-over help texts
- Editable sections visually highlighted

### 2.2 Personalized Forms & Microsites

| Property | Detail |
|----------|--------|
| Purpose | Personalized, data-driven web experiences across digital channels |
| Capabilities | Real-time adaptation to customer data/behaviors, self-service actions, guided digital journeys |
| Distribution | Omnichannel via PURLs (email, SMS, social media, app notifications, chatbots) |
| Security | PURLs ensure content accessible only to intended recipient for limited time |
| Features | E-commerce, chatbots, self-service portals, data-driven personalization of content/navigation/features |

### 2.3 Interactive Videos (Personalized Videos)

| Property | Detail |
|----------|--------|
| Purpose | Transform customer data into personalized, interactive video experiences |
| Personalization | Scenes, components, text elements adjusted per recipient data |
| Audio | Text-to-speech for personalized audio (consumption data, transaction data, etc.) |
| Distribution | PURLs -- secure (hash signature), permanent or temporary, unique links; custom domain support |
| Channels | Social media, SMS, email, app notifications, chatbots |
| Integration | Multi-module integration for fully personalized multi-channel digital experience |

### 2.4 Digital Archive

| Property | Detail |
|----------|--------|
| Purpose | Integrated communication repository for storage and retrieval |
| Sources | Documents from Doxee Platform or third-party systems (any format, any channel) |
| Storage | Short-term and long-term archiving |
| Access | Web-based interface or API integration |
| Security | Encryption, permission-based access |
| PURLs | Secure hash-signature links; permanent or temporary; custom domain support |
| Scalability | Efficient handling of large document volumes |

---

## 3. INSIGHTS

```
Scope: Data-driven customer analytics
Purpose: Measure, analyze, optimize customer communications
```

### 3.1 Customer Insights

| Property | Detail |
|----------|--------|
| Purpose | Behavioral communication analytics |
| Capabilities | Collect/analyze data from various endpoints; track every action within communications |
| Outputs | KPIs for conversion rate improvement, customer behavior/preferences/pain point analysis |
| Features | A/B testing, behavioral analytics; feeds CRM and Marketing Automation systems |

### 3.2 Process Insights

| Property | Detail |
|----------|--------|
| Purpose | Integrated process monitoring |
| Capabilities | Monitor/track/troubleshoot/optimize automated processes in real time |
| Scope | All process types on Doxee Platform; execution status of applications |
| Role | Essential for daily management of platform production cycle |

### 3.3 Channel Insights

| Property | Detail |
|----------|--------|
| Purpose | Platform reporting data; measure communication effectiveness and operational performance |
| Tracking | Every action within communication; SLA compliance; channel-specific; individual document level |
| BI Integration | Predefined data models, reports, dashboards; integrates with customer BI solutions |
| Data Pipeline | Extracts data from Doxee Platform, transforms to BI-compatible formats |
| Reporting | Adaptable reports, flexible querying |

### 3.4 Customer Data Hub

| Property | Detail |
|----------|--------|
| Purpose | Centralized customer intelligence; unified data foundation |
| Capabilities | Centralizes/organizes customer information (documents, communications, interactions) |
| Analysis | Segmentation, analytics-driven decision-making |
| Downstream | Can power marketing automation workflows, customer-facing business portals |

**Note:** Tracking & Reporting (DP2/DP3) and Platform Reporting (ex Infinica) also exist but are legacy/not documented.

---

## 4. INTEGRATION

```
Scope: Seamless system integration
Purpose: CRM/ERP integration through Marketplace Apps, APIs, Connectors
```

### 4.1 Marketplace Apps

| Property | Detail |
|----------|--------|
| Platforms | Salesforce, Microsoft Dynamics 365, SAP |
| Purpose | Design/automate personalized interactive communications directly within CRM/ERP |
| Features | Generate personalized documents within CRM, pre-configured templates, dynamic data fields, real-time template modification |
| Collaboration | Centralized template management, streamlined approval processes, workflow automation |
| Roles | Sales, marketing, customer service, operations |

### 4.2 APIs and Connectors

| Property | Detail |
|----------|--------|
| Type | REST APIs |
| Capabilities | On-demand workflow integration, event-triggered personalized messages, on-demand job execution, archive extraction, PURL generation |
| Integration Levels | Multiple levels for different customer experience and communication management needs |
| Scope | Interactive web content and video distribution |

---

## 5. AUTOMATION

```
Scope: Scalable process automation
Purpose: Production efficiency with omnichannel process automation
```

### 5.1 Process Engine

| Property | Detail |
|----------|--------|
| Standard | BPMN 2.0 |
| Purpose | Central automation core; orchestrator of all resources in document creation |
| Capabilities | Automates workflows, manages data processing + human tasks (from Process Designer definitions) |
| Integration | Enterprise systems via specific connectors; full data pipeline |
| Logging | Detailed process information in log database for monitoring/reporting |
| Configuration | Custom configurations to track activities and ensure compliance |
| Performance | Rapid task execution, efficient time to market |

### 5.2 Batch Jobs

| Property | Detail |
|----------|--------|
| Purpose | Management/monitoring of batch jobs, input files, output lots |
| Features | Execution status checking, issue identification for non-running processes |
| Role | Essential for daily management of platform production cycle |

### 5.3 On-Demand Jobs

| Property | Detail |
|----------|--------|
| Purpose | Monitoring of on-demand jobs and workflows |
| Features | Track document production job status |
| Limitation | Does NOT provide ability to make changes during creation/execution phases |

### 5.4 Omnichannel Engine

| Property | Detail |
|----------|--------|
| Purpose | Omnichannel communication distribution |
| Digital Channels | Email, SMS |
| Traditional Channels | Print and delivery processes |
| Protocols | SFTP, Email, SMS, Certified email (PEC), AppIO |
| Mode | Automatic and centralized |

---

## 6. ADMINISTRATION

```
Scope: Centralized platform administration
Purpose: Governance of platform resources for operations
```

### 6.1 Platform Administration / Command Center

| Property | Detail |
|----------|--------|
| Type | Web tool for managing Doxee Platform environments |
| Architecture | Stateless, easily scalable |
| Access | Web-based GUI via browser; central instance |
| Features | Overview of all environments per user; view applications, status, configuration details |
| Privileges | Stop, restart, configuration changes based on predefined parameter set |

### 6.2 Batch Workloads

| Property | Detail |
|----------|--------|
| Purpose | Advanced resource scheduling for batch jobs |
| Optimization | Cost-effectiveness based on SLA and execution time |
| Configurable | Max parallel job instances, production/delivery tasks, memory allocation per environment |
| Granularity | Configuration per workflow with per-task limits |
| Behavior | Tasks not aligned with configurations are delayed |

### 6.3 Resource Manager

| Property | Detail |
|----------|--------|
| Purpose | Centralize platform resource storage, organization, management |

#### Repository

| Property | Detail |
|----------|--------|
| Purpose | Definition/management of resources; deployment across environments |
| Features | Import pre-built resources (from data/template design), create reusable templates for multiple accounts/environments |
| Architecture | Multi-environment; centralized configuration, deployed to target environments |

#### Content Repository

| Property | Detail |
|----------|--------|
| Purpose | Store document templates, images, process definitions |
| Access | Multiple applications (Workplace, Composer, Business Designer, Template Designer) for read/write |
| Storage | SQL database |
| Type | Stateful application; workspace in local file system |

#### Resource Explorer

| Property | Detail |
|----------|--------|
| Purpose | Graphical tool for accessing files/folders on Content Repository and local file system |
| Availability | Stand-alone + embedded in Template Designer and Process Designer |
| Features | File transfer (file system <-> servers), backups, restore, deploy, version management, access rights |

### 6.4 User Manager / Settings

| Property | Detail |
|----------|--------|
| Purpose | User and access control |
| Method | RBAC (Role-Based Access Control) |
| Features | Define/manage users, access roles, accounts, companies |
| Elements | Accounts, Users, Roles with specific permissions |

### 6.5 Doxee University

| Property | Detail |
|----------|--------|
| Purpose | Official eLearning portal for Doxee Platform users |
| Users | Customers, partners, employees |
| Features | AI-powered, on-demand training, guided paths, certification programs |
| Scope | All functional areas (template creation, interactive documents, data transformation, digital archiving) |
| Delivery | Any device, self-paced |

---

## 7. AI FOUNDATION

```
Scope: AI-powered enhancement across all platform components
Purpose: Enhance customer intelligence with the power of AI
```

| Capability | Description |
|------------|-------------|
| Template & Content Generation | AI-powered generation of templates and content |
| Template Migration | AI-assisted migration of legacy templates |
| Composer Copilot | AI copilot for the Composer tool |
| Engagement Scoring | AI-driven engagement measurement |

---

## ADD-ONS (Delivery-Managed)

Installed by Doxee Professional Services team upon client request.

### Global Market Add-Ons

#### Active Connectors

| Connector | Purpose | Details |
|-----------|---------|---------|
| Namirial | Electronic signatures | Simple, advanced, qualified e-signatures; static/dynamic document signing workflows; API integration; Process Designer compatible |
| Scrive | PDF document signatures | Simple electronic signature with optional OTP; Blockchain technology for signature crystallization |
| Zuora | Billing integration | Data extraction via JQL metalanguage; CSV-to-XML conversion; Batch and On-Demand; SFTP/Doxee endpoints; PURL metadata update; batch error recovery |

#### Deprecated (NOT TO BE SOLD)

| Add-On | Description |
|--------|-------------|
| Booster | Marketing automation (email, SMS, mobile push, web notifications) |
| Content Hub | Headless CMS for Interactive Videos/Microsites web assets |
| Web Analytics Platform | Matomo-based analytics on Interactive Videos/Microsites with custom dimensions |
| Tracking & Reporting | Document lifecycle monitoring + behavioral analytics; SLA compliance tracking |

### Italian Market Add-Ons (Trust Services)

Doxee operates as: accredited SDI intermediary, AgID Marketplace conservation provider, PEPPOL-accredited NSO intermediary via AgID.

#### Conservazione Digitale a Norma

| Property | Detail |
|----------|--------|
| Purpose | Legal digital preservation of fiscal and employment documents |
| Compliance | Italian/EU regulations, ISO 14721 (OAIS), CAD (Codice dell'Amministrazione Digitale) |
| Accreditation | AgID-qualified; AgID Marketplace dei servizi di conservazione |
| Scale | 4+ billion documents preserved, 400+ legal entities managed, 10+ years |
| Standards | UNI SInCRO 11386 for interoperability (versamento, archiviazione, distribuzione reports) |
| Features | Web portal for search/consultation, individual document access/download, distribution package export, hash/signature/temporal validation verification, corrective/supplementary attachment management |
| Infrastructure | High logical/physical security, high-volume/peak handling, high availability, business continuity with SLA |

#### Fatturazione Elettronica (E-Invoicing)

| Property | Detail |
|----------|--------|
| Purpose | Fully managed e-invoicing for AR (active) and AP (passive) cycles |
| Compliance | Italian/EU regulations; continuous regulatory updates |
| Integration | Native with Doxee Platform; ERP, CRM, financial systems |
| Scope | B2G (Public Administration), B2B, B2C via SDI (Sistema di Interscambio) |
| Scalability | High-volume e-invoice processing |
| Monitoring | Real-time: inbound/outbound invoice counts, individual receipts, processing status, rejection reasons |

**Portale Fatture:** Centralized interface for viewing/managing full lifecycle of active and passive e-invoices (search, detailed view, management).

**Document Cockpit:** Operational management interface for tracking/managing e-invoicing documents in configurable time periods. Features: document status monitoring (pre-delivery interaction), processing queue management (remove from send queues), real-time database data access.

#### Ordine Elettronico (E-Ordering)

Three modes for PA-supplier order exchange (Italian/EU standards):

| Mode | Description |
|------|-------------|
| **Semplice** (Simple) | ODA reception from NSO, recognition/routing to supplier via Doxee, automatic PEC notification |
| **Completo** (Complete) | Includes Simple + return flows to NSO/PA; web portal for accept/reject with justification; response order transmission to NSO |
| **Pre-concordato** (Pre-agreed) | Send orders to NSO/PA in non-UBL 3.0 formats; automatic Doxee conversion to required format; PEPPOL channel transmission/validation; response order management |

#### Recapito Elettronico Certificato (Certified Electronic Delivery)

Compliant with EU Regulation 910/2014 (eIDAS). Delivered via Qualified Trust Service Provider. Legal evidence for litigation.

| Service | Type | Description | Regulation | Integration |
|---------|------|-------------|------------|-------------|
| e-Mail Certificata | SERC | Certified email with legal value; proof of content, send time, delivery time | eIDAS Art. 3 n.36, Art. 43 c.1 | Lleidanetworks (Registered e-mail) |
| e-Recapito | SERC | Certified delivery + opening of documents via personalized link (email/SMS); documentary evidence of send/receipt/opening with date/time | eIDAS Art. 3 n.36, Art. 43 c.1 | Lleidanetworks (OPENUM) or InPoste (Tnotice) |
| e-Recapito Qualificato | SERCQ | Same as e-Recapito + higher security with certain sender/recipient identification | eIDAS Art. 3 n.36/37, Art. 43, Art. 44 | InPoste (TnoticeQ) |

#### Firma Elettronica (Electronic Signature)

| Type | Acronym | Description |
|------|---------|-------------|
| Firma Elettronica Semplice | FES/SES | Point-and-click digital signature; OTP integration for security; full process dematerialization |
| Firma Elettronica Avanzata | FEA | Higher security standards; eIDAS-compliant; secure signer identification with consent collection |
| Firma Digitale (Qualificata) | FEQ/QES | Qualified certificates + cryptographic keys; maximum security/immutability/integrity; Massive Remote Signature for automated high-volume signing |

**Marcatura Temporale (Timestamping):** Blockchain-based timestamp crystallization; compliant with Italian/EU regulations for legal validity and third-party opposability.

---

## Data Flow Patterns

```
Raw Data (CSV/XML/TXT/PDF/AFP/Flat)
  --> Data Designer (parse, transform, enrich, anonymize)
    --> Template Designer / Video Designer (personalized templates)
      --> Process Designer (workflow definition: batch or on-demand)
        --> Process Engine (BPMN 2.0 orchestration)
          --> Omnichannel Engine (SFTP/Email/SMS/PEC/AppIO/Print)
            --> Digital Archive (short/long-term storage)
              --> Customer Insights (behavioral analytics, KPIs)
```

**On-Demand Path:**
```
External Event/API Call (REST/WS)
  --> On-Demand Workflow
    --> Process Engine
      --> Document Generation
        --> PURL Distribution (secure hash-signed links)
```

**Interactive Path:**
```
Workplace/Composer (user-driven)
  --> Interactive Documents (human tasks)
    --> Process Engine (approval workflows)
      --> Omnichannel Delivery
```

---

## Security Model

| Layer | Mechanism |
|-------|-----------|
| Access Control | RBAC (Role-Based Access Control) via User Manager/Settings |
| Content Access | Granular per-block permissions (configured in Business/Template Designer) |
| Document Delivery | PURLs with hash signatures; permanent or temporary; time-limited access |
| Archive | Encryption + permission-based access |
| Digital Preservation | ISO 14721 (OAIS), UNI SInCRO 11386 compliance |
| Signatures | FES (SES), FEA, FEQ (QES) -- eIDAS compliant |
| Certified Delivery | SERC/SERCQ -- eIDAS Art. 3/43/44 compliant |
| Timestamping | Blockchain-based temporal crystallization |
| Custom Domains | PURL support for branded/custom domains |

---

## Component Relationship Map

```
DESIGN                          ENGAGEMENT                    INSIGHTS
  Data Designer ----+            Interactive Documents         Customer Insights
  Template Designer-+---> Process Designer ---> Workplace     Process Insights
  Video Designer ---+                          Composer       Channel Insights
                    |                          Forms/Microsites Customer Data Hub
                    v                          Videos
              Process Engine (BPMN 2.0)        Digital Archive
                    |
                    v
            Omnichannel Engine
            (SFTP/Email/SMS/PEC/AppIO)

INTEGRATION                     AUTOMATION                    ADMINISTRATION
  Marketplace Apps              Process Engine                Command Center
    - Salesforce                Batch Jobs                    Batch Workloads
    - SAP                       On-Demand Jobs                Repository
    - MS Dynamics 365           Omnichannel Engine            Content Repository
  REST APIs & Connectors                                      Resource Explorer
                                                              User Manager / Settings
                                                              Doxee University
```

---

## Platform Editions/Variants

| Reference | Context |
|-----------|---------|
| DP2 | Referenced for Tracking & Reporting availability |
| DP3 | Data Transformation component exclusive to DP3 |

---

## Key Technical Standards

| Standard | Usage |
|----------|-------|
| BPMN 2.0 | Process Engine workflow standard |
| W3C | Template element-based model |
| HTML5 | Interactive video output |
| REST | API integration |
| XML | Process definitions, data transformation |
| XSL | Transformations in process activities |
| Java | Custom activity development |
| SQL | Content Repository storage |
| ISO 14721 (OAIS) | Digital preservation |
| UNI SInCRO 11386 | Interoperability for conservation packages |
| eIDAS (EU 910/2014) | Electronic signatures and certified delivery |
| UBL 3.0 | Electronic ordering standard (with auto-conversion) |
| PEPPOL | Electronic ordering channel |
| PDF/A, PDF/UA | Accessible/archival output formats |
