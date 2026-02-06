# Doxee Knowledge Base Manifest

**Version:** 1.1
**Last Updated:** February 6, 2026
**Purpose:** AI-navigable index of all Doxee domain knowledge for context-aware feature development

---

## Overview

This manifest catalogs all Doxee-related documentation, context materials, and knowledge resources available in the `doxee/` directory. It serves as a quick reference guide for AI agents to locate relevant domain knowledge when generating product specifications, plans, and implementations.

**Total Assets:**
- Core company/product documents: 4
- Pricing & commercial documents: 2
- Analyst reports: 3
- Official product documentation: 1,477 files across 171+ directories
- Total markdown files: 1,487
- Documentation format: Markdown (converted from PDFs where applicable)

---

## 1. Core Company & Product Documents

### 1.1 Doxee Company Profile
**File:** `doxee/official-product-documentation/Doxee-profile.md`
**Size:** 126 lines
**Last Updated:** October 10, 2025

**Purpose:**
Official company profile with business overview, market positioning, and product summary.

**Key Contents:**
- **Company Identity**
  - Founded: 2001
  - Legal: Società Benefit (Italian PMI innovativa)
  - Stock: Euronext Growth Milan (DOX:IM, ISIN IT0005394413)
  - Headquarters: Modena, Italy
  - International offices: Milan, Rome, Catanzaro (Italy); Austria, Germany, Czech Republic, Slovakia, USA

- **Market Position**
  - Leader in Customer Communications Management (CCM)
  - Leader in Customer Experience Management (CXM)
  - Leader in Document Dematerialization
  - Recognition: Aspire CCS, QKS Group analysts

- **Product: Doxee Platform®**
  - European cloud-native AI-powered platform
  - Combines CCM + CXM in unified environment
  - Omnichannel delivery: print, digital, interactive, trusted channels
  - Core capabilities: Design, Engagement, Insights, Integration, Automation, Administration, AI Foundation

- **Customer Base**
  - 200+ large enterprises
  - Key sectors: Telco, Utility, Finance, Healthcare, Public Administration
  - Major clients: Fastweb, Sky Italia, Sorgenia, Engie Italia, Crédit Agricole, Gruppo Enel, Hera, Wind Tre (50% of revenue)

- **Technical Differentiators**
  - Enterprise-ready cloud-native any-prem architecture
  - Low-code/no-code tools for business users
  - Omnichannel automation (print, SMS, email, forms, microsites, video, PEC, SERC, SERCQ, AppIO)
  - Native CRM/ERP integrations (Salesforce, SAP, Microsoft Dynamics 365)
  - Open standards: BPM, BPMN, XSLT, XSL-FO
  - AI Foundation: generative, descriptive, prescriptive, predictive AI
  - Compliance: GDPR, EAA, ISO, ITIL, eIDAS, ESG
  - Regulatory recognition: AgID, ACN

- **R&D Investment**
  - 25%+ of revenue invested in R&D
  - National and European innovation projects
  - Strategic partnerships: Postel, RGI Group, Zuora, Capgemini, AWS, Salesforce, SAP

**When to Use:**
- Understanding Doxee's market positioning and competitive advantages
- Writing executive summaries or business-facing documentation
- Identifying key technical capabilities and architectural principles
- Understanding compliance and regulatory requirements
- Identifying integration partners and ecosystem

---

### 1.2 Doxee Platform Functional Architecture & Components
**File:** `doxee/official-product-documentation/Doxee Platform functional architecture and components.md`
**Size:** 166.9 KB (large document, persisted output)
**Last Updated:** June 10, 2025

**Purpose:**
Comprehensive technical architecture reference documenting all platform components, functional capabilities, and system integration patterns.

**Key Contents:**
- **Platform Architecture Overview**
  - Cloud-native design principles
  - Component interaction model
  - Data flow patterns
  - Deployment models (SaaS, on-premise, hybrid)

- **Component Categories:**

  **DESIGN (Content Creation & Modeling)**
  - Data Designer: Data schema and model definition
  - Data Transformation (DP3): ETL and data mapping
  - Template Designer: Document template creation (print & digital)
  - Business Designer: Business rules and decision logic
  - Video Designer: Interactive video template authoring
  - Process Designer: Workflow and process orchestration
  - Batch Workflows: High-volume batch document production
  - On-Demand Workflows: Real-time triggered document generation
  - Output Management: Multi-channel delivery configuration

  **ENGAGEMENT (Interactive Experiences)**
  - Interactive Documents: Dynamic, clickable PDFs and documents
  - Workplace: Collaborative document workspace
  - Composer: Ad-hoc document composition interface
  - Personalized Forms & Microsites (Pweb): Web-based interactive forms
  - Interactive Videos (Pvideo): Personalized video experiences
  - Digital Archive: Long-term document storage and retrieval

  **INSIGHTS (Analytics & Intelligence)**
  - Communication analytics
  - Customer engagement metrics
  - Journey tracking
  - Performance dashboards

  **INTEGRATION (System Connectivity)**
  - REST APIs
  - CRM connectors (Salesforce, SAP, Dynamics 365)
  - ERP integrations
  - Marketing automation platforms
  - Data sources and sinks

  **AUTOMATION (Process Execution)**
  - Batch processing engine
  - Event-driven triggers
  - Workflow orchestration
  - Channel routing and failover

  **ADMINISTRATION (Platform Management)**
  - User management
  - Role-based access control
  - Security configuration
  - Audit logging
  - System monitoring

  **AI FOUNDATION (Cross-Platform AI)**
  - Generative AI for content creation
  - Descriptive AI for analytics
  - Prescriptive AI for recommendations
  - Predictive AI for next-best actions

**When to Use:**
- Designing features that integrate with existing platform components
- Understanding component dependencies and data flows
- Planning technical architectures for new capabilities
- Identifying integration points and APIs
- Writing technical specifications that align with platform patterns
- Understanding deployment and operational models

---

### 1.3 Doxee Company Context Research
**File:** `doxee/official-product-documentation/doxee-context-research.md`
**Size:** 932 lines
**Last Updated:** February 6, 2026

**Purpose:**
Comprehensive company context research synthesizing corporate identity, product portfolio, target markets, competitive landscape, and strategic direction. Developed for Speckit constitution and feature alignment.

**Key Contents:**
- **Corporate Identity** — Legal structure (Società Benefit), stock listing (Euronext Growth Milan), geographic footprint (Italy, Austria, Germany, Czech Republic, Slovakia, USA)
- **Product Portfolio** — Full Doxee Platform® capabilities across all seven pillars (Design, Engagement, Insights, Integration, Automation, Administration, AI Foundation)
- **Target Markets** — Enterprise verticals: Telco, Utilities, Finance/Insurance, Healthcare, Public Administration
- **Competitive Landscape** — Positioning vs. Quadient, OpenText, Smart Communications, Messagepoint, and others
- **Strategic Direction** — AI Foundation investment, CXM evolution, European sovereignty focus
- **CCM Domain Context** — Industry evolution from document generation to experience orchestration

**When to Use:**
- Building context for new feature specifications
- Understanding Doxee's strategic priorities and market position
- Aligning feature development with company vision and competitive strategy
- Developing constitution and project principles

---

### 1.4 Product Management Framework (Product Summary)
**File:** `doxee/official-product-documentation/product-summary.md`
**Size:** 898 lines
**Last Updated:** July 17, 2024

**Purpose:**
Defines Doxee's product management framework including vision, prioritization methodology (extended RICE model), user personas, UX strategy, and innovation roadmap.

**Key Contents:**
- **Product Vision & Strategy** — Strategic pillars: Self-Service Platform, Enterprise Focus, Content Design Excellence, Process Automation, Multi-Channel Delivery, Flexibility, Innovation
- **Prioritization Framework** — Customized RICE scoring model (Reach × Impact × Confidence / Effort) extended with Cost Reducing, Cofinancing, and strategic weighting factors; implemented in Jira Product Discovery
- **User Personas** — Detailed personas for business users, designers, developers, and administrators
- **Product Positioning & Architecture** — Deployment models (SaaS Multi-Cloud, PaaS, On-Premises)
- **UX Strategy** — Unified portal experience direction for all Doxee applications
- **Future Innovation Opportunities** — AI integration, interactive content, analytics roadmap

**When to Use:**
- Understanding how features get prioritized (RICE scoring)
- Aligning new features with product vision and strategic pillars
- Identifying target user personas for feature specifications
- Understanding deployment model implications for feature design
- Planning UX patterns consistent with platform direction

---

## 1B. Pricing & Commercial Documents

### 1B.1 Doxee Group Price Book 2025
**File:** `doxee/pricing/doxee-pricing-2025.md`
**Size:** 649 lines
**Source:** Reconstructed from Salesforce CPQ price list (`Salesforce_Listino-Prototipo-x-New-PriceBook-Doxee-Group-2025.xlsx`)

**Purpose:**
Complete product pricing catalog with product codes, tiered pricing, deployment model pricing, and Salesforce CPQ integration mappings.

**Key Contents:**
- **Pricing Philosophy**
  - Platform + Volume-Based Consumption model
  - Deployment-model-driven base pricing (On-Premise, Doxee-Cloud Shared/Dedicated, Public-Cloud Shared/Dedicated)
  - Three business models: Technology (TE), Embedded Services (ES), Professional Services (PS)
  - Tiered degressive pricing for volume products

- **Product Code System**
  - Structure: `{LANG}-{COUNTRY}-{MODEL}-{PRODUCT}{TIER}.{VERSION}`
  - Regional entities: Italy (DOXEE/IT), Austria (INFINICA/AT), Germany (DOXEE-DE/DE)

- **Product Catalog Categories:**
  - Base System (platform licenses by deployment model)
  - User Licenses (named users, concurrent users)
  - Production (pages, pURLs by volume tier)
  - Community Size (impressions)
  - Digital Archiving (storage tiers)
  - Other Solutions (PWeb, PVideo, Workplace, Process Engine)
  - Distribution (email, SMS, PEC, SERC, SERCQ, file delivery)
  - Printing (physical print services)
  - Embedded Services (sandbox, premium support, 24/7 support)
  - Professional Services (per-day rates)
  - Intercompany (intra-group services for AT/DE)

- **Salesforce CPQ Integration** — Field mappings, product hierarchy, quote configuration

**When to Use:**
- Understanding pricing structure for features affecting product packaging
- Designing features that map to specific product SKUs
- Planning monetization for new capabilities
- Understanding deployment model cost implications
- Aligning feature scope with pricing tiers

**⚠️ Note:** Contains sensitive commercial pricing data — use internally only.

---

### 1B.2 SaaS Service Terms — KPI Definitions (Exhibit 4)
**File:** `doxee/pricing/Doxee-SaaS-ServiceTerms-Exhibit-4-KPI.md`
**Size:** 224 lines
**Version:** 1.0 (April 17, 2024)

**Purpose:**
Official KPI and SLA definitions for Doxee Platform SaaS services, establishing performance benchmarks and capacity limits.

**Key Contents:**
- **Key Definitions & Limits:**
  - Paginated Document: max 75 KB or 5 pages
  - Standard Page: max 15 KB
  - pURL: personalized URLs for secure resource access
  - PVideo/PWeb: max 10 concurrent views/second per template
  - Input File: max 400 files/day, max 200 MB each
  - On-Demand Request: max 1 MB payload

- **Production Process Types & Limits:**
  - **Batch Production:** Max 4 distribution channels, monthly cap = annual ÷ 12, max 2 peak days/month at 35% of monthly volume
  - **On-Demand Production:** Max 2 distribution channels, max 3 output types, 3 concurrent requests with 5-second response
  - **Interactive Production:** Human-in-the-loop workflows

- **KPI Formulas:**
  - Batch: documents or pURLs produced / hours
  - On-Demand: concurrent requests / response time in seconds
  - Interactive: human workflow executions / hours

**When to Use:**
- Designing features with performance requirements (understanding platform limits)
- Writing non-functional requirements and SLA specifications
- Understanding capacity constraints for batch vs. on-demand processing
- Defining acceptance criteria involving throughput or response time
- Planning features that need to operate within documented SLA boundaries

---

## 2. Market Intelligence & Analyst Reports

### 2.1 QKS Group AI Maturity Matrix for CCM 2025
**File:** `doxee/analysts/EN-US_ANRP_CXM_QKS AI Maturity Matrix for CCM 2025_Final (2).md`
**Size:** 45 KB, 23 pages, 6,288 words
**Source:** QKS Group (Quadrant Knowledge Solutions) research report
**Date:** 2025
**Authors:** Saurabh Raj (Principal Analyst), Amandeep Singh (Practice Director & Principal Analyst)

**Purpose:**
Independent analyst evaluation of AI maturity in CCM vendors, with strategic guidance for technology buyers. Positions Doxee in competitive landscape.

**Key Contents:**

- **Market Analysis Framework: QKS AI Maturity Matrix**
  - **Dimensions:**
    - Vertical Axis: AI Vision & Roadmap
    - Horizontal Axis: AI-First Productization & Execution Maturity
    - Bubble Size: Market Impact
  - **Maturity Stages:**
    - Industry Pioneers (top-right)
    - Scaling for Impact (middle-right)
    - Building Momentum (lower-middle)
    - AI Explorers (lower-left)

- **Doxee's Position:**
  - **Quadrant:** Scaling for Impact
  - **Strengths:**
    - Strong digital engagement focus
    - Personalized video and interactive experiences
    - AI-driven content tailoring and next-best interactions
    - Production scale in European markets
    - Integrated analytics for journey improvement
  - **Relative Positioning:**
    - Scope narrower for complex regulated document composition vs. full-platform leaders
    - Strong execution but not yet "Industry Pioneer" status
    - Positioned alongside vendors like Intense, Newgen (similar quadrant)

- **Competitive Landscape (Other Vendors):**

  **Industry Pioneers:**
  - **Quadient** (Most Valuable Pioneer): AI-assisted authoring, sentiment tuning, automated translation, event-driven orchestration, AnyPrem deployment, journey mapping

  **Scaling for Impact:**
  - **Doxee**: Digital engagement, video, interactive experiences
  - **Messagepoint**: MARCIE semantic analysis engine, content intelligence
  - **Smart Communications**: AWS cloud-native, regulated industries, volume scale
  - **OpenText**: Broad enterprise content estate, Exstream engine
  - **Intense**: UniServe CCM, telecom/banking APAC/Middle East
  - **Newgen**: Process/content blend, onboarding, compliance
  - **Precisely**: EngageOne, data quality heritage

  **Building Momentum:**
  - **Elixir**: Print-centric batch composition
  - **Sefas**: High-volume print/postal
  - **Nintex**: Workflow automation, Microsoft environments

  **AI Explorers:**
  - **Kwsoft**: Structured forms, public sector

- **Market Trends & Insights:**
  - **From CCM to CXM:** Shift from document generation to experience orchestration
  - **AI-Orchestrated Experiences:** AI as persistent communication layer connecting events, data, and channels
  - **Agentic AI:** Systems that perceive context, decide next action, execute with safeguards
  - **Challenges:** Template sprawl, fragmented data, static rules, governance gaps, deployment complexity
  - **Success Patterns:** Content rationalization + event-driven delivery = fastest value

- **Technology Buyer Guidance:**

  **Large Enterprises:**
  - Prioritize AI maturity and innovation roadmap
  - Composable architecture for complex IT landscapes
  - Governance, compliance, security (BYOAI models)
  - Align CCM with CX strategy (CoE model)

  **Mid-Market:**
  - Cloud-first, SaaS for agility
  - Empower business users (low-code/no-code)
  - Out-of-box integrations (CRM, core systems)
  - Cost/ROI focus with phased implementation

  **Public Sector:**
  - Compliance, security, accessibility as core requirements
  - Legacy modernization with minimal disruption
  - Omnichannel citizen experience
  - AI ethics and explainability

- **Future Outlook (2026-2028):**
  - **2026:** Generative AI mainstream, AI-led journey orchestration, ~50% of processes with AI content generation
  - **2027:** Autonomous communication agents managing end-to-end workflows with minimal human oversight
  - **2028:** Self-optimizing, self-healing systems; reinforcement learning; closed-loop adaptation; CCM → CXM transition complete
  - **Beyond 2028:** Goal-oriented orchestration; autonomous customer experience management; "self-driving" communications

**When to Use:**
- Understanding Doxee's competitive positioning in AI-driven CCM
- Identifying AI feature priorities aligned with market trends
- Benchmarking Doxee capabilities against industry leaders
- Writing strategic roadmaps or product vision documents
- Understanding buyer personas and their evaluation criteria
- Identifying gaps to close for moving from "Scaling" to "Pioneer" status
- Referencing industry trends (agentic AI, experience orchestration, etc.)

---

### 2.2 Aspire CCS Expert Session (December 2025)
**File:** `doxee/analysts/Doxee Expert Session December 2025.md`
**Size:** 101 lines (short presentation)
**Source:** Aspire CCS consultancy
**Date:** December 2, 2025
**Presenters:** Kaspar Roos (Founder & CEO), George Parapadakis (Research Director)

**Purpose:**
Competitive intelligence briefing on key CCM/CXM vendors and emerging "Agentic Communications Platforms" trend.

**Key Contents:**

- **Competitive Vendor Snapshots:**
  - **Quadient:** (visual competitive analysis)
  - **OpenText:** (visual competitive analysis)
  - **SmartComms:** Acquired Pendula, now offering SmartPATH
  - **CSG xPonent:** (visual competitive analysis)

- **Emerging Concept: Agentic Communications Platforms**
  - **Tagline:** "From siloed documents to integrated dialogue"
  - **Implication:** Industry shift toward continuous, context-aware communication vs. one-time document output
  - **Relevance:** Aligns with agentic AI trend in QKS report

- **Aspire CCS Team:**
  - Kaspar Roos: Netherlands/CET, kaspar.roos@aspireccs.com, +31 6 41 77 86 74
  - George Parapadakis: UK/GMT
  - Will Morgan: USA/Central Time

**When to Use:**
- Understanding competitor movements (acquisitions, product pivots)
- Referencing "Agentic Communications" as emerging market category
- Competitive positioning discussions
- Strategic roadmap planning (what competitors are doing)

---

### 2.3 QKS Group SPARK Matrix CCM 2025
**File:** `doxee/analysts/QKS Group_ SPARKMATRIXCCM25_not for distribution.md`
**Size:** 100 KB
**Source:** QKS Group
**Date:** 2025
**Status:** Not for public distribution (internal research)

**Purpose:**
Broader CCM market evaluation using QKS SPARK Matrix methodology (separate from AI Maturity Matrix).

**Key Contents:**
- Vendor evaluations across Technology Excellence and Customer Impact
- Market dynamics and trends
- Strategic recommendations

**When to Use:**
- Additional competitive intelligence (use with caution due to distribution restriction)
- Cross-reference with AI Maturity Matrix for complete picture
- Understanding QKS methodology and evaluation criteria

**⚠️ Note:** This document is marked "not for distribution" — use insights internally only, do not quote externally.

---

## 3. Official Product Documentation

**Location:** `doxee/official-product-documentation/doxee-platform/`
**Scale:** 1,477 markdown files across 171 directories
**Version Coverage:** Doxee Platform 3.x (3.48, 3.49), i-Edition 6.5-6.7
**Years:** 2025-2026 releases

### 3.1 Documentation Catalog Structure

#### 3.1.1 User Guides (40% of documentation)

**Design Tools & Composers (156 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Business Designer 6.7** | 36 | Visual interface for business logic, rules, decision tables | Designing rule-based content personalization, conditional logic, data-driven decisions |
| **Template Designer 6.7** | 34 | Document template creation (print & digital) | Creating/modifying document layouts, designing output formats, understanding template structure |
| **Composer 6.7** | 33 | Ad-hoc document composition interface | Understanding user-facing composition workflows, designing self-service document creation |
| **Process Designer 6.7** | 17 | Workflow and process orchestration | Designing multi-step processes, workflow automation, event-driven triggers |
| **PVideo Designer** | 57 | Interactive video template authoring | Designing personalized video experiences, video-based communications |
| **Resource Explorer 6.7** | 7 | Repository resource browsing | Understanding resource organization, repository navigation patterns |
| **Task Manager 6.7** | 6 | Task execution monitoring | Understanding task lifecycle, monitoring workflows |
| **Command Center 0.3** | 5 | Centralized control/monitoring | Designing admin dashboards, system monitoring features |

**Batch & Workflow Processing (113 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Batch Workflows** | 61 | Complex multi-step batch processing | Designing high-volume document production, batch automation, scheduled jobs |
| **On-Demand Workflows** | 36 | Real-time triggered workflows | Designing event-driven communications, API-triggered document generation |
| **Batch Jobs** | 6 | Legacy batch job management | Understanding legacy patterns, migration planning |
| **On-Demand Jobs** | 5 | Real-time job execution | Real-time document generation use cases |
| **Batch Workloads** | 3 | High-volume processing | Capacity planning, performance optimization |

**Key Task Types Documented (in Batch Workflows):**
- Compose Documents (document composition engine)
- Extract Documents (digital archiving retrieval)
- Archive Documents (long-term storage)
- Distribute Digitals (email, SMS, file delivery)
- Distribute Hybrids (mixed print/digital)
- Generate PURL (Persistent URL for tracking)
- Track Documents (engagement tracking)
- Load Events (event ingestion)
- Rename Invoices (document transformation)
- Unpack Files (archive extraction)

**Data & Content Management (176 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Data Transformation (DT3)** | 122 | ETL, data mapping, format conversion | Designing data ingestion, transformation pipelines, system integrations |
| **Content Repository** | 39 | Repository operations, resource management | Understanding content organization, versioning, lifecycle management |
| **Digital Archiving** | 10 | Document archival, retrieval, compliance storage | Designing archival features, compliance requirements, long-term storage |
| **Content Repository Legacy** | 5 | Older repository documentation | Legacy system understanding |

**Engagement & Output Channels (111 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Output Management** | 44 | Multi-channel delivery configuration | Designing omnichannel delivery, channel routing, output formats |
| **Workplace 2.6.7** | 26 | Collaborative document workspace | Designing collaboration features, team workflows |
| **PWeb** | 10 | Web-based interactive forms/microsites | Designing web experiences, interactive forms, customer self-service |
| **PVideo** | 1 | Video delivery and management | Video distribution, playback features |

**Configuration & Administration (34 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Security Configuration** | 21 | Security policies, authentication, authorization | Designing security features, access control, compliance requirements |
| **Settings** | 9 | Account, user, role, profile, company management | Designing admin interfaces, tenant configuration |
| **Third-Party Integrations** | 4 | External system integrations (generic) | Designing integrations beyond CRM (APIs, webhooks, etc.) |

**Process Engine (313 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Process Engine 6.7** | 313 | BPMN-based process execution engine — user guides, developer guides, REST API reference, process definition reference, and examples | Designing workflow execution, understanding BPMN process lifecycle, API integrations, task orchestration, exception handling, data stores, and process variables |

**Key Topics Covered (in Process Engine 6.7):**
- Process lifecycle and anatomy of a process
- Process definition reference (BPMN elements, activities, gateways, events)
- Developer guide (API reference, man pages, credentials handling)
- REST API reference (process execution, monitoring, management endpoints)
- Data stores and persistence
- Variables and the pipeline
- Wait states and exception handling
- Logging and resource access layer
- Worked examples

**Platform User Interface Documentation (12 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **Platform UI Documentation** | 12 | Platform home page, navigation, access pages, UI conventions | Understanding platform UX patterns, designing consistent UI experiences, onboarding flows |

**General Platform Reference (6 root-level files)**

| File | Purpose | When to Use |
|------|---------|-------------|
| `what-is-doxee-platform.md` | Platform overview and introduction | Feature context, onboarding content |
| `release-history-and-supported-versions.md` | Version history and support matrix | Version compatibility planning |
| `known-vulnerabilities.md` | Security vulnerability disclosures | Security assessments, compliance checks |
| `third-party-software-requirements-6-7.md` | Third-party dependencies and requirements | Infrastructure planning, dependency management |
| `dd-111125-1349-1304.md` | Internal reference document | Internal documentation reference |

**Product Guides — Previous Versions (489 files)**

| Component | Files | Purpose | When to Use |
|-----------|-------|---------|-------------|
| **i-Edition 6.6 Documentation** | 489 | Complete documentation archive for i-Edition 6.6 including all major modules (Process Engine, Process Designer, Business Designer, Template Designer, Composer, Workplace, Security Configuration, Content Repository, Resource Explorer, Task Manager, Third-Party Integration) | Understanding version evolution, migration planning, backward compatibility research, historical feature reference |

**Note:** This is a comprehensive archive of the previous version's documentation. Prefer current 6.7 documentation for active development. Use previous version docs when investigating version-specific behavior or planning migrations.

---

#### 3.1.2 Reference Guides (35% of documentation)

**Repository Resource Reference (33 guides)**

Complete API-style specifications for all resource types:

**Document & Composition Resources:**
- Document Templates
- Document Template Compositions
- Document Composition Programs
- Batch Programs

**Workflow Resources:**
- Batch Workflows
- On-Demand Workflows
- On-Demand Programs

**Data Resources:**
- Data Transformation Programs
- Data Transformation Projects

**Ingress Points (Data Entry):**
- Batch HTTP Ingress
- FTP Endpoint
- Email Ingress
- On-Demand HTTP Ingress
- Digital Archiving HTTP Ingress
- Digital Archiving PURL Ingress

**Store Resources (Output/Storage):**
- PVideo Store
- PWeb Store
- Digital Archiving Store

**Communication Templates:**
- Email Templates
- SMS Templates

**Security & Keys:**
- Archive Keys
- Store Keys
- Ingress Credentials

**Organizational:**
- Folders
- Assets

**When to Use Reference Guides:**
- Designing APIs or integrations
- Understanding data models and schemas
- Writing technical specifications with precise field definitions
- Planning resource provisioning and configuration
- Understanding input/output formats and constraints

---

#### 3.1.3 Integration Guides (14 files)

**CRM/ERP Integration Documentation:**

| Product | Files | Coverage | When to Use |
|---------|-------|----------|-------------|
| **Salesforce** | 5 | Installation, configuration, Lightning components, query builder | Designing Salesforce integrations, understanding CRM data sync patterns |
| **SAP** | 5 | Installation, configuration, SAP system patterns | Designing SAP integrations, ERP data models |
| **Dynamics 365** | 4 | Installation, configuration, setup | Designing Microsoft ecosystem integrations |

**Key Integration Patterns:**
- Data synchronization (CRM ↔ Doxee Platform)
- Document generation triggers (workflow → communication)
- Template selection based on CRM data
- Delivery status feedback (communication → CRM activity)

**When to Use:**
- Designing features that integrate with CRM/ERP systems
- Understanding data models from external systems
- Planning authentication and authorization flows
- Designing user experiences within CRM UIs (embedded apps)

---

#### 3.1.4 Release Notes (10% of documentation, 26 files)

**Doxee Platform 3 Releases (16 files)**

**Versions Documented:**
- **3.48.x series (2025):**
  - 3.48 (initial release)
  - 3.48.0.1, 3.48.0.2, 3.48.0.3, 3.48.0.4 (patch releases)
  - 3.48.1 (minor release)
  - Bug fix releases: doxee-platform-34805, doxee-platform-34806

- **3.49.x series (2025-2026):**
  - 3.49 (initial release)
  - 3.49.0.1 (patch)
  - 3.49.1, 3.49.1.1 (minor releases)
  - 3.49.2, 3.49.2.1 (latest, 2026)

**i-Edition Releases (7 files)**

**Versions Documented:**
- i-Edition 6.5 SP2 (Service Pack 2)
- i-Edition 6.5 SP3 (Service Pack 3)
- i-Edition 6.6
- i-Edition 6.7
- Future release indexes: 2025-1, 2026-1

**Integration App Releases (3 files)**
- Doxee App for Salesforce 1
- Doxee App for SAP 1
- Doxee App for Microsoft Dynamics 365

**When to Use Release Notes:**
- Understanding feature evolution and roadmap
- Identifying recent capabilities for new feature alignment
- Checking for known issues or deprecations
- Planning version compatibility
- Understanding bug fix history for related features

---

#### 3.1.5 Getting Started & Support (6 files)

| Topic | Purpose | When to Use |
|-------|---------|-------------|
| **Home Navigation** | Documentation portal structure | Understanding doc organization |
| **Browsing Articles** | Search and navigation patterns | Finding specific documentation |
| **AI-Powered Search** | Semantic documentation search | Understanding AI-assisted help features |
| **Support Resources** | Contact info, support channels | Planning support/help features |
| **Documentation Roadmap** | Future documentation plans | Anticipating doc updates |
| **Getting Support** | Help request procedures | Designing in-app support flows |

---

#### 3.1.6 Developer Guides

**Status:** Minimal (1 index file only)
**Implication:** Developer documentation may be sparse; rely more on reference guides and architecture docs
**Recommendation:** When designing developer-facing features, may need to create new documentation or expand this section

---

### 3.2 Documentation by User Role

**Business Users (Content Authors, Marketers):**
- Output Management (44 files)
- Workplace (26 files)
- Composer (33 files)
- Getting Started (6 files)
- PWeb (10 files)

**Designers (Document/Template Authors):**
- Business Designer (36 files)
- Template Designer (34 files)
- Composer (33 files)
- Process Designer (17 files)
- PVideo Designer (57 files)

**Developers & Integration Specialists:**
- Data Transformation (122 files)
- Process Engine (313 files)
- Repository Resources (33 reference guides)
- Integration Guides (14 files)
- Security Configuration (21 files)
- Third-Party Integration (4 files)

**System Administrators:**
- Settings (9 files)
- Security Configuration (21 files)
- Task Manager (6 files)
- Command Center (5 files)

**Architects & Platform Engineers:**
- Functional Architecture document
- Process Engine (313 files)
- Process Designer (17 files)
- Repository model documentation
- Batch Workflows (61 files)
- On-Demand Workflows (36 files)

**Product Managers & Business Stakeholders:**
- Product Management Framework (product-summary.md)
- Pricing documentation (doxee-pricing-2025.md)
- KPI definitions (Exhibit 4)
- Analyst reports (QKS, Aspire)

---

### 3.3 Key Technical Concepts Documented

**Data Flow Patterns:**
- Ingress (batch HTTP, FTP, email, on-demand HTTP, archiving HTTP/PURL)
- Transformation (DT3 mapper operators, ETL pipelines)
- Composition (template + data → document)
- Distribution (email, SMS, print, web, video)
- Archiving (long-term storage, compliance retention)
- Tracking (engagement metrics, delivery status)

**Process Orchestration:**
- Batch workflows (scheduled, high-volume)
- On-demand workflows (event-triggered, real-time)
- Task chains (multi-step execution)
- Conditional branching (business rules)
- Error handling and retry logic

**Content Model:**
- Templates (design-time artifacts)
- Compositions (template + data bindings)
- Programs (executable composition logic)
- Resources (reusable assets: images, fonts, snippets)
- Folders (organizational hierarchy)

**Security Model:**
- Authentication mechanisms
- Authorization (roles, permissions)
- Encryption (at rest, in transit)
- Audit logging
- Compliance controls (GDPR, retention policies)

---

### 3.4 Documentation Format & Metadata

All files converted to Markdown from original formats:
- Source: Hugo static site generator (documentation portal)
- Structure: Hierarchical directories mapping to site navigation
- Naming: `_index.md` for category indexes, descriptive names for articles
- Cross-references: Internal links between related documents

---

## 4. Usage Guide for AI Agents

### 4.1 Search Strategy by Task Type

**When writing a feature specification:**

1. **Start with:** Company Profile (market positioning, key differentiators)
2. **Then review:** Functional Architecture (component alignment)
3. **Then search:** Relevant user guides (similar features, UX patterns)
4. **Finally check:** Release notes (recent capabilities, avoid duplication)

**When designing a technical plan:**

1. **Start with:** Functional Architecture (components, integration points)
2. **Then review:** Repository Resource Reference (data models, APIs)
3. **Then search:** Integration guides (if external systems involved)
4. **Then check:** Data Transformation docs (if ETL needed)

**When understanding competitive positioning:**

1. **Start with:** QKS AI Maturity Matrix (detailed positioning)
2. **Then review:** Aspire CCS Expert Session (competitor moves)
3. **Then check:** Company Profile (Doxee strengths to emphasize)

**When designing for specific user roles:**

1. **Business users:** Output Management, Workplace, Composer docs
2. **Designers:** Business Designer, Template Designer, Process Designer
3. **Developers:** Data Transformation, Repository Reference, Integration Guides
4. **Admins:** Settings, Security Configuration

**When planning AI/ML features:**

1. **Start with:** QKS AI Maturity Matrix (industry trends, buyer expectations)
2. **Then review:** Company Profile (AI Foundation capabilities)
3. **Then check:** Functional Architecture (AI integration points)

### 4.2 Search Keywords by Domain

**For document composition features:**
- Keywords: "Template Designer", "Composer", "Document Template", "Composition Program"
- Files: Template Designer (34), Composer (33), Document Templates reference

**For workflow/automation features:**
- Keywords: "Process Designer", "Process Engine", "Batch Workflow", "On-Demand Workflow", "Task", "BPMN"
- Files: Process Engine (313), Process Designer (17), Batch Workflows (61), On-Demand Workflows (36)

**For data integration features:**
- Keywords: "Data Transformation", "DT3", "Ingress", "Integration"
- Files: Data Transformation (122), Ingress references (7), Integration Guides (14)

**For omnichannel delivery features:**
- Keywords: "Output Management", "Distribute", "Email", "SMS", "PWeb", "PVideo"
- Files: Output Management (44), PWeb (10), PVideo (58)

**For archival/compliance features:**
- Keywords: "Digital Archiving", "Archive", "Retention", "Compliance"
- Files: Digital Archiving (10), Security Configuration (21)

**For user management/security features:**
- Keywords: "Settings", "Security", "Authentication", "Authorization", "Roles"
- Files: Settings (9), Security Configuration (21)

**For CRM/ERP integrations:**
- Keywords: "Salesforce", "SAP", "Dynamics", "CRM", "ERP"
- Files: Salesforce (5), SAP (5), Dynamics 365 (4)

**For AI/ML features:**
- Keywords: "AI", "Machine Learning", "Generative", "Predictive", "Analytics"
- Files: QKS AI Maturity Matrix, Functional Architecture (AI Foundation section)

**For pricing/commercial features:**
- Keywords: "Pricing", "SKU", "License", "Tier", "Volume", "SaaS", "KPI", "SLA"
- Files: Price Book 2025, KPI Exhibit 4, Product Summary (RICE framework)

**For process execution/BPMN features:**
- Keywords: "Process Engine", "BPMN", "Process Lifecycle", "Pipeline", "Data Store", "Wait State"
- Files: Process Engine 6.7 (313 files), Process Designer (17 files)

### 4.3 Context Layering Strategy

When building context for a feature, layer information in this order:

**Layer 1: Business Context (Why)**
- Company Profile → Market positioning, customer needs
- Analyst Reports → Industry trends, competitive landscape
- Product Summary → Product vision, RICE prioritization, strategic pillars

**Layer 2: Product Context (What)**
- Functional Architecture → Platform capabilities, component model
- Release Notes → Recent features, current state
- Pricing & KPIs → Commercial packaging, performance limits, SLA boundaries

**Layer 3: Technical Context (How)**
- User Guides → UX patterns, user workflows
- Reference Guides → Data models, APIs, schemas
- Integration Guides → External system patterns
- Process Engine → BPMN execution, workflow orchestration

**Layer 4: Implementation Context (Details)**
- Specific component documentation
- Task reference guides
- Configuration guides
- Context Research → Synthesized domain context for feature alignment

### 4.4 Document Quality & Coverage

**High-Quality, Comprehensive Coverage (>30 files):**
- Product Guides Previous Versions (489 files) ✅
- Process Engine (313 files) ✅
- Data Transformation (122 files) ✅
- Batch Workflows (61 files) ✅
- PVideo Designer (57 files) ✅
- Output Management (44 files) ✅
- On-Demand Workflows (36 files) ✅
- Business Designer (36 files) ✅
- Template Designer (34 files) ✅
- Composer (33 files) ✅

**Moderate Coverage (10-30 files):**
- Workplace (26 files)
- Security Configuration (21 files)
- Process Designer (17 files)
- Integration Guides (14 files)
- Platform UI Documentation (12 files)
- Digital Archiving (10 files)
- PWeb (10 files)

**Light Coverage (<10 files):**
- Settings (9 files)
- Resource Explorer (7 files)
- General Platform Reference (6 root-level files)
- Task Manager (6 files)
- Getting Started (6 files)
- Command Center (5 files)
- Third-Party Integration (4 files)
- PVideo delivery (1 file)

**Gap Areas (minimal/no documentation):**
- Developer Guides (only index)
- API specifications (scattered in reference guides, but Process Engine REST API is now documented)
- Mobile app integration
- Real-time analytics/insights

**Recommendation:** For features in gap areas, rely more heavily on Functional Architecture doc and analogous patterns from well-documented components.

---

## 5. Version & Update Tracking

**Manifest Version:** 1.1
**Manifest Date:** February 6, 2026

**Content Freshness:**
- Company Profile: October 10, 2025 (current)
- Functional Architecture: June 10, 2025 (6 months old, likely still accurate)
- Context Research: February 6, 2026 (current)
- Product Summary: July 17, 2024 (strategic framework, still relevant)
- Price Book: 2025 (current year pricing)
- KPI Definitions: April 17, 2024 (SLA terms, contractual)
- QKS AI Maturity Matrix: 2025 (current year, recent)
- Aspire CCS Session: December 2, 2025 (2 months old, recent)
- Product Documentation: Versions 3.48-3.49 (2025-2026 releases, current)

**Next Review Recommended:** August 2026 (6 months from manifest creation)

**Update Triggers:**
- New major platform release (e.g., 3.50 or 4.0)
- New analyst report publication
- Significant company announcements (acquisitions, partnerships)
- Competitive landscape changes
- New product capabilities (AI features, integrations)

---

## 6. Quick Reference: File Paths by Category

### Core Documents
```
doxee/official-product-documentation/Doxee-profile.md
doxee/official-product-documentation/Doxee Platform functional architecture and components.md
doxee/official-product-documentation/doxee-context-research.md
doxee/official-product-documentation/product-summary.md
```

### Pricing & Commercial Documents
```
doxee/pricing/doxee-pricing-2025.md
doxee/pricing/Doxee-SaaS-ServiceTerms-Exhibit-4-KPI.md
```

### Analyst Reports
```
doxee/analysts/EN-US_ANRP_CXM_QKS AI Maturity Matrix for CCM 2025_Final (2).md
doxee/analysts/Doxee Expert Session December 2025.md
doxee/analysts/QKS Group_ SPARKMATRIXCCM25_not for distribution.md
```

### Official Documentation Root
```
doxee/official-product-documentation/doxee-platform/
```

### Key Documentation Paths
```
user-guides/
  process-engine-6-7/              ← 313 files (BPMN engine, REST API, developer guide)
  product-guides-previous-versions/ ← 489 files (i-Edition 6.6 archive)
  business-designer-6-7/
  template-designer-6-7/
  composer-6-7/
  process-designer-6-7/
  pvideo-designer/
  output-management-6-7/
  workplace-2-6-7/
  repository/
  data-transformation-6-7/
  doxee-platform-user-interface-documentation-1/
  settings/
  security-configuration-guide-6-7/
  third-party-integration-guide-6-7/
  doxee-app-for-salesforce/
  (+ more...)

release-notes/
  doxee-platform-3/
  i-edition/
  doxee-app-for-salesforce-1/
  doxee-app-for-sap-1/
  doxee-app-for-microsoft-dynamics-365/

developer-guides/

getting-started/
```

---

## 7. Contact & Analyst Relationships

**Internal Doxee:**
- Documentation source: Doxee Platform official documentation portal

**External Analysts:**

**Aspire CCS:**
- Kaspar Roos (Founder & CEO): kaspar.roos@aspireccs.com, +31 6 41 77 86 74
- George Parapadakis (Research Director): george.parapadakis@aspireccs.com
- Will Morgan (Sr. Research Analyst): will.morgan@aspireccs.com

**QKS Group:**
- Citation contact: info@qksgroup.com
- Website: www.qksgroup.com

---

## 8. Appendix: Document Statistics

**Total Markdown Files:** 1,487
- Core documents: 4
- Pricing & commercial documents: 2
- Analyst reports: 3
- Official product documentation: 1,477
- Manifest: 1

**Documentation by Type:**
- User Guides: ~1,400+ files (including previous versions)
- Reference Guides: ~518 files
- Release Notes: ~148 files
- Administration Guides: ~148 files
- Getting Started: ~74 files
- Context & Strategy: 4 files (context research, product summary, pricing, KPIs)

**Documentation by Component (Top 15):**
1. Product Guides Previous Versions: 489 files
2. Process Engine 6.7: 313 files
3. Data Transformation: 122 files
4. Batch Workflows: 61 files
5. PVideo Designer: 57 files
6. Output Management: 44 files
7. Repository (all sections): 39 files
8. On-Demand Workflows: 36 files
9. Business Designer: 36 files
10. Template Designer: 34 files
11. Composer: 33 files
12. Repository Resources (references): 33 files
13. Workplace: 26 files
14. Security Configuration: 21 files
15. Process Designer: 17 files

**Coverage by Version:**
- Doxee Platform 3.x: Extensive (primary focus)
- i-Edition 6.6-6.7: Comprehensive (including 6.6 archive with 489 files)
- i-Edition 6.5: Documented via release notes
- Integration Apps v1: Complete

---

## 9. AI Agent Instructions

**When invoked for context lookup:**

1. **First, understand the task type** (spec, plan, implementation, competitive analysis)
2. **Then, identify the domain** (workflows, data, UI, integration, security, etc.)
3. **Then, locate relevant documents** using the search strategy (Section 4.1)
4. **Then, layer context** from business → product → technical → implementation (Section 4.3)
5. **Finally, synthesize insights** relevant to the specific task

**Prioritize documents by:**
1. **Relevance:** Exact domain match > adjacent domain > general reference
2. **Freshness:** 2025-2026 > 2024 > older
3. **Authority:** Official product docs > analyst reports > internal notes
4. **Specificity:** Reference guides (precise specs) > user guides (workflows) > overview docs

**When synthesizing:**
- Extract key facts, not full text
- Provide file path references for traceability
- Highlight conflicts or gaps across documents
- Note version-specific information
- Call out "not for distribution" restrictions where applicable

**When context is insufficient:**
- Explicitly state what information is missing
- Suggest analogous areas to extrapolate from
- Recommend asking the user for clarification
- Flag assumptions being made

---

## 10. Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-02-06 | AI Agent (Claude Code) | Initial manifest creation; cataloged all 1,482 documents |
| 1.1 | 2026-02-06 | AI Agent (Claude Code) | Added: pricing documents (2), context research, product summary, Process Engine 6.7 (313 files), Platform UI docs (12 files), Product Guides Previous Versions (489 files), root user-guides files (6); fixed core document file paths; updated statistics to 1,487 total files |

---

**End of Manifest**
