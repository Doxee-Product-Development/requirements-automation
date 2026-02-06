# DOXEE COMPANY CONSTITUTION

**VERSION:** 1.0.0
**DATE:** 2026-02-06
**TARGET:** AI Agent Context (LLM-consumable)
**TOKEN BUDGET:** ~30,000 max

This constitution provides the strategic, technical, and operational context for AI agents generating requirements for Doxee Platform features.

---

## Section 0 — Executive Kernel [LAYER 0]

### 0.1 Constitution Manifest

This document follows a three-layer progressive loading model:
- **Layer 0:** Executive Kernel + Generation Rules (always loaded)
- **Layer 1:** Strategic context for epic/roadmap planning
- **Layer 2:** Deep reference for detailed requirements generation

### 0.2 Identity

**Doxee S.p.A.:** Cloud-native CCM/CXM vendor (Euronext Growth Milan: DOX). Transforms static documents into interactive experiences (Pvideo®, Pweb®). European-sovereign. GDPR-native. API-first. 200+ enterprise customers across Telco, Utilities, Finance, Healthcare. Any-prem deployment (SaaS, PaaS, On-Premises, Hybrid). Low-code/no-code platform empowering business users. AI Foundation across all product lines.

### 0.3 Glossary

```xml
<glossary>
  CCM:    Customer Communications Management — enterprise document generation/distribution
  CXM:    Customer Experience Management — journey-aware omnichannel engagement
  DT3:    Data Transformation v3 — ETL/data mapping engine (DP3 platform)
  dx:     Document Experience product line — traditional document output
  FEA:    Firma Elettronica Avanzata — Advanced electronic signature (eIDAS)
  FEQ:    Firma Elettronica Qualificata — Qualified electronic signature (eIDAS)
  FES:    Firma Elettronica Semplice — Simple electronic signature
  ix:     Interactive Experience product line — Pvideo + Pweb
  PEC:    Posta Elettronica Certificata — Italian certified email
  PURL:   Personalized URL — secure hash-signed link for content access
  Pvideo: Personalized Video — AI-powered interactive video experiences
  Pweb:   Personalized Web — interactive microsites and forms
  px:     Paperless Experience product line — digital workflows
  RBAC:   Role-Based Access Control — platform security model
  SERC:   Servizio Elettronico di Recapito Certificato — certified delivery (eIDAS)
  SERCQ:  SERC Qualificato — qualified certified delivery (eIDAS Art. 44)
  UDS:    User-Directed Storytelling — interactive video navigation
</glossary>
```

### 0.4 North Star Metric

**Customer Digital Engagement Rate:** 60% interactive (Pvideo+Pweb) vs static (PDF/email) by Q4 2027.

### 0.5 Top Personas (Summary)

| ID | Role | Primary Job-to-be-Done |
|----|------|------------------------|
| `[PER:CDO]` | Content Designer | Design personalized communications that drive engagement across print and digital channels |
| `[PER:PDS]` | Process Designer | Automate complex multi-step workflows connecting data sources to omnichannel delivery |
| `[PER:BUS]` | Business User | Quickly create and distribute communications without IT dependency |
| `[PER:ADM]` | System Administrator | Ensure platform security, performance, and compliance across all tenants |
| `[PER:DEV]` | Integration Developer | Connect Doxee Platform to CRM/ERP systems with minimal custom code |

### 0.6 Hard Guardrails

[HARD] NEVER introduce features that bypass GDPR compliance (Art. 17 Right to Erasure, Art. 25 Privacy by Design)
[HARD] ALWAYS expose new capabilities via REST API with OpenAPI 3.0 specification
[HARD] NEVER create deployment-model-specific logic (features MUST work on-premise, cloud, and hybrid)
[HARD] ALWAYS design for WCAG 2.1 AA accessibility compliance (EAA requirement enforced June 2025)
[HARD] NEVER hard-code per-customer logic in core platform (use configuration, not custom code)

### 0.7 Active Bets (Current Cycle)

- `BET-AI01`: AI Foundation maturity — move from "Scaling for Impact" to "Industry Pioneer" (Q2-Q4 2026)
- `BET-JM01`: Customer Journey Management gap closure — Customer Data Hub + Journey Builder (Q2-Q3 2026)
- `BET-GEO01`: Geographic expansion — reduce CEE concentration, grow Western Europe + USA (2026)

---

## Section 1 — Product Identity & Portfolio [LAYER 1]

### 1.1 Product Lines

**[PROD:IX] — Interactive Experience (Pvideo + Pweb)**

For marketing teams and customer engagement managers who need to cut through digital noise, Interactive Experience is a personalized engagement platform that transforms data into interactive video and web experiences. Unlike static PDFs or plain emails, ix drives 3-5x engagement through User-Directed Storytelling and data-driven personalization.

**[PROD:DX] — Document Experience**

For operations teams and compliance officers who need compliant high-volume document production, Document Experience is a CCM engine that generates personalized print and digital documents at scale. Unlike legacy batch composition tools, dx combines batch and on-demand in a cloud-native architecture with built-in compliance tracking.

**[PROD:PX] — Paperless Experience**

For business users who need to replace manual paper processes, Paperless Experience is a digital workflow platform combining interactive documents, e-signatures, and digital archiving. Unlike generic BPM tools, px is purpose-built for regulated document-centric processes (contracts, invoices, onboarding).

**[PROD:AI] — AI Foundation**

Cross-platform AI capabilities: Generative AI (content creation, summarization, translation), Descriptive AI (analytics, segmentation), Prescriptive AI (next-best-action recommendations), Predictive AI (churn, engagement forecasting). Integrated across Design, Engagement, and Insights pillars.

### 1.2 Platform Capability Map

| Module | Product Line | Status |
|--------|-------------|--------|
| Pvideo Designer | ix | Core |
| Pweb Designer | ix | Core |
| Template Designer | dx | Core |
| Business Designer | dx | Core |
| Data Transformation (DT3) | dx | Core |
| Process Engine (BPMN 2.0) | dx, px | Core |
| Batch Workflows | dx | Core |
| On-Demand Workflows | dx, ix | Core |
| Composer | px | Core |
| Workplace | px | Core |
| Digital Archive | px | Core |
| Customer Insights | ix | Growth |
| Journey Builder | AI | New (Q2 2026) |
| Customer Data Hub | AI | New (Q2 2026) |
| Content Rationalization | AI | New (Q3 2026) |

---

## Section 2 — Strategic Context (DIBB Chains) [LAYER 1]

```yaml
dibb_chains:

  - id: DIBB-001
    data: "QKS AI Maturity Matrix 2025 positions Doxee in 'Scaling for Impact' quadrant. Quadient (Industry Pioneer MVP) shows 3x larger customer base and end-to-end AI across content lifecycle."
    insight: "Doxee's AI breadth is narrower than leaders; strong in digital engagement but gaps in content intelligence (rationalization, compliance validation) and journey orchestration."
    belief: "Closing AI maturity gaps (content intelligence + journey management) will unlock mid-market wins against full-platform vendors and defend against Quadient in European accounts."
    active_bets:
      - "BET-AI01: AI Foundation maturity"
      - "BET-JM01: Customer Journey Management gap closure"
    status: ACTIVE

  - id: DIBB-002
    data: "Doxee revenue is 50% from 8 top clients (Fastweb, Sky Italia, Sorgenia, etc.). Geographic concentration: ~70% Central & Eastern Europe (QKS analysis)."
    insight: "High customer concentration + geographic concentration = revenue risk if key accounts churn or regional economic downturn."
    belief: "Expanding geographic footprint (Western Europe, USA) and increasing mid-market customer count will de-risk revenue and unlock new growth."
    active_bets:
      - "BET-GEO01: Geographic expansion"
    status: ACTIVE

  - id: DIBB-003
    data: "43% of public agencies run fragmented communication tools with manual approvals (QKS Group). EAA (European Accessibility Act) mandates WCAG 2.1 AA compliance June 2025."
    insight: "Public sector is under-digitized and faces regulatory deadline. Doxee has AgID recognition, Italian market strength, and accessibility-first design."
    belief: "Purpose-built public sector offering (compliance tooling, accessible templates, workflow automation for citizen communications) will capture government digital transformation budgets."
    active_bets:
      - "BET-PS01: Public Sector vertical offering (H2 2026)"
    status: ACTIVE

  - id: DIBB-004
    data: "Smart Communications acquired Pendula, launched SmartPATH for journey orchestration (Aspire CCS Dec 2025). Messagepoint's MARCIE engine shows 50-90% template estate reduction through AI rationalization."
    insight: "Competitors are closing gaps: Smart Comms now has journey orchestration, Messagepoint leads content intelligence. Doxee's Pvideo/Pweb differentiation erodes if we don't advance core CCM AI."
    belief: "Investing in AI-driven content rationalization + migration tools will defend installed base and accelerate legacy platform migrations."
    active_bets:
      - "BET-AI01: AI Foundation maturity (content intelligence sub-bet)"
    status: ACTIVE

  - id: DIBB-005
    data: "Doxee Platform pricing is platform + volume-based consumption. 14 tiers for page production (EUR 14,000/M at tier 1 → EUR 1,840/M at tier 14 = 86% degression)."
    insight: "Tiered pricing incentivizes volume growth but creates margin pressure at scale. High-volume customers subsidize low-volume onboarding."
    belief: "Value-based pricing tiers (by use case complexity, not just volume) will improve margins and align pricing to customer outcomes."
    active_bets:
      - "BET-PRICE01: Value-based pricing model (2026)"
    status: PAUSED
```

### 2.1 Company-Level Beliefs

1. **Privacy by design beats compliance bolted on.** Every feature must embed GDPR from architecture, not as audit afterthought.
2. **Business users are the customer; IT is the enabler.** Low-code/no-code is not a nice-to-have, it's the product strategy.
3. **European sovereignty is a competitive moat.** All-EU data residency + GDPR-native design beats US vendors in regulated European verticals.
4. **AI agents are the next CCM UI.** By 2028, "design a template" will mean "describe the outcome to an AI agent."

---

## Section 3 — User Personas (JTBD) [LAYER 1]

### `[PER:CDO]` — Content Designer

- **Jobs:** Design visually compelling document templates (invoices, statements, contracts); ensure brand consistency across print/digital; personalize content based on customer data; meet production deadlines
- **Pains:** Template sprawl (hundreds of variants to maintain) [HIGH]; IT dependency for changes [HIGH]; limited preview capabilities for data-driven content [MED]; tool learning curve [MED]
- **Gains:** Self-service template creation without IT [HIGH]; instant preview with real data [HIGH]; reusable building blocks (styles, components) [MED]; AI-assisted layout suggestions [MED]

### `[PER:PDS]` — Process Designer

- **Jobs:** Automate complex multi-step workflows (batch and on-demand); connect data sources (CRM, ERP, databases) to document composition; configure omnichannel delivery (email, SMS, print, PEC, SERC); troubleshoot failed jobs
- **Pains:** Integration complexity with legacy systems [HIGH]; error handling and retry logic [HIGH]; performance tuning for high-volume batch [HIGH]; lack of end-to-end visibility [MED]
- **Gains:** Visual workflow designer (no coding) [HIGH]; pre-built connectors for CRM/ERP [HIGH]; real-time monitoring and alerting [HIGH]; automatic scaling for volume spikes [MED]

### `[PER:BUS]` — Business User

- **Jobs:** Create ad-hoc communications (customer support responses, one-off contracts); modify pre-approved templates with customer-specific data; track delivery and engagement; archive communications for compliance
- **Pains:** Dependency on IT or designers for simple changes [HIGH]; limited tools for non-technical users [HIGH]; difficulty finding and reusing past communications [MED]
- **Gains:** Intuitive WYSIWYG editor (like Word) [HIGH]; pre-approved building blocks (drag-and-drop) [HIGH]; instant delivery without IT approval [HIGH]; automatic archiving [MED]

### `[PER:ADM]` — System Administrator

- **Jobs:** Manage users, roles, and permissions across tenants; monitor platform health and performance; ensure security and compliance; configure integrations and SSO
- **Pains:** Multi-tenant complexity [HIGH]; audit trail requirements for compliance [HIGH]; user provisioning across multiple systems [MED]; performance troubleshooting [HIGH]
- **Gains:** Centralized admin console [HIGH]; automated compliance reporting [HIGH]; SSO integration with corporate identity providers [HIGH]; proactive alerting for issues [HIGH]

### `[PER:DEV]` — Integration Developer

- **Jobs:** Connect Doxee Platform to enterprise systems (SAP, Salesforce, Dynamics, custom apps); develop data transformation logic; build custom workflow activities; maintain API integrations
- **Pains:** API documentation gaps [HIGH]; versioning and backward compatibility [MED]; debugging integration failures [HIGH]; lack of sandbox environments [HIGH]
- **Gains:** Comprehensive REST API with OpenAPI specs [HIGH]; pre-built connectors for major CRMs/ERPs [HIGH]; sandbox for testing [HIGH]; detailed error messages and logs [HIGH]

---

## Section 4 — Competitive Landscape [LAYER 1]

### 4.1 Table Stakes (Must Match)

| Feature | Doxee Status |
|---------|-------------|
| Batch document composition at 100k+ pages/hour | Competitive |
| Omnichannel delivery (email, SMS, print) | Competitive |
| REST API for on-demand generation | Competitive |
| Template versioning and approval workflows | Competitive |
| GDPR compliance (data purge, consent management) | Competitive |
| Role-based access control | Competitive |
| Digital archiving with search | Competitive |
| CRM integration (Salesforce, Dynamics, SAP) | Competitive |

### 4.2 Differentiators (Build to Win)

| Feature | Advantage | Nearest Competitor |
|---------|----------|-------------------|
| **Pvideo (personalized video)** | User-Directed Storytelling; AI text-to-speech; interactive CTAs | None match; Precisely has basic video |
| **Pweb (interactive microsites)** | PURL-driven personalized web experiences with data-driven navigation | Quadient has basic interactive HTML |
| **European sovereignty** | All-EU data residency; GDPR-native architecture; AgID/ACN recognition | US vendors (Quadient, Smart Comms, OpenText) lack this |
| **Any-prem deployment flexibility** | Genuine cloud-native with real on-premise/hybrid options | Most competitors are cloud-first, on-prem is legacy |
| **Low-code/no-code for business users** | Business Designer and Composer for non-technical users | Most competitors IT-centric (Exstream, Smart Comms) |

### 4.3 Competitive Gaps (Must Close)

| Gap | Leading Vendor(s) | Priority |
|-----|------------------|----------|
| **AI content rationalization** | Messagepoint MARCIE (50-90% template reduction) | CRITICAL |
| **End-to-end journey orchestration** | Quadient Inspire Journey, Smart Communications SmartPATH | CRITICAL |
| **Content intelligence (similarity, compliance validation)** | Messagepoint, Quadient | HIGH |
| **Legacy modernization tools** | Quadient InspireXpress (auto migration) | HIGH |
| **Complex regulated document composition** | Quadient, OpenText Exstream | MEDIUM |

### 4.4 Key Competitors

**Quadient** — Threat: HIGH
- Strength: Most mature AI (Industry Pioneer MVP in QKS); InspireXpress migration; journey mapping; BYOAI; global scale
- Weakness: Higher cost; complex deployment; weaker interactive digital engagement vs. Doxee Pvideo/Pweb
- Response: Defend on European sovereignty + interactive differentiation; close AI breadth gap; match journey orchestration

**Messagepoint** — Threat: MEDIUM
- Strength: MARCIE semantic analysis; content intelligence leader; compliance validation AI
- Weakness: No native journey orchestration (relies on third-party); limited global penetration outside North America
- Response: Build content intelligence capabilities; emphasize omnichannel + video/interactive strengths

**Smart Communications** — Threat: MEDIUM-HIGH
- Strength: Cloud-native AWS scale (330M pages/hr); SmartPATH journey orchestration (post-Pendula acquisition); regulated industry depth
- Weakness: Less agile interactive engagement; no video capabilities
- Response: Highlight Pvideo/Pweb differentiation; match journey orchestration in 2026

**OpenText (Exstream)** — Threat: MEDIUM
- Strength: Broad enterprise content ecosystem; high-volume engines; archival strength
- Weakness: IT-centric (not business-user-friendly); complex architecture; slow cloud migration
- Response: Emphasize ease of use + cloud-native agility; faster time-to-value

---

## Section 5 — Prioritization Framework [LAYER 1]

### 5.1 Scoring Dimensions

| Dimension | Weight | Description |
|-----------|--------|-------------|
| Strategic Value | 0.30 | Alignment with DIBB chains and active bets; competitive gap closure |
| Regulatory Urgency | 0.20 | Compliance deadlines (EAA, eIDAS 2.0), legal risk, audit findings |
| Technical Feasibility | 0.15 | Complexity, dependencies, team capability, reuse of existing components |
| Customer Impact | 0.25 | Persona pain severity × user volume affected; revenue at risk |
| Resource Efficiency | 0.10 | Build cost, time-to-market, ongoing maintenance burden |

**Extended RICE Formula:**
```
Value = ((Reach × Impact) + CostReducing + Cofinancing) × (Confidence/100) / Effort
```
Where:
- Reach: 1-5 (% customers affected, revenue-weighted)
- Impact: 1-5 (1=Tech Debt → 5=Game Changer)
- Confidence: 50/80/100% (requires quantitative evidence for High)
- Effort: 1-5 (person-days: 1=0-100, 5=400-500; >500 = must split)
- CostReducing: 1-5 (annual savings: 1=<€30K, 5=>€120K)
- Cofinancing: 1-5 (customer co-investment: 20-100%)

**Tool:** Jira Product Discovery

### 5.2 Priority Thresholds

| Priority | Weighted Score | Action |
|----------|---------------|--------|
| P1 | >= 8.0 | Must ship this cycle |
| P2 | >= 5.0 | Should ship; defer only if P1 overflows |
| P3 | >= 2.0 | Nice to have; backlog |

### 5.3 Appetite Levels

| Appetite | Spec Depth Required |
|----------|---------------------|
| **Micro** | Issue title + 1-paragraph description |
| **Small Batch** | Problem + solution sketch + acceptance criteria |
| **Big Batch** | Full spec: data model, API contracts, Gherkin scenarios, UI mocks |

---

## Section 6 — No-Go Lists & Scope Boundaries [LAYER 1]

### 6.1 Permanent No-Gos

```yaml
permanent_no_gos:
  - "On-premise-only features (violates any-prem principle)"
  - "Custom per-customer logic in core platform (use configuration/tenant settings)"
  - "Features requiring manual ops at scale (must be automatable)"
  - "Vendor lock-in dependencies (no single-cloud-only services)"
  - "Features that bypass GDPR/privacy controls"
```

### 6.2 Current Cycle No-Gos

```yaml
current_cycle_no_gos:
  - area: "Print service provider integrations"
    reason: "Low ROI; print volume declining; partners handle fulfillment"
    revisit: "H1 2027 if print revenue >15%"

  - area: "Mobile native apps (iOS/Android)"
    reason: "Web-first strategy; Pweb responsive design sufficient; no customer demand data"
    revisit: "H2 2026 if 3+ enterprise RFPs require native apps"

  - area: "Blockchain beyond timestamping"
    reason: "No clear use case beyond existing marcatura temporale; technology maturity concerns"
    revisit: "2027 if regulatory drivers emerge"
```

### 6.3 Anti-Patterns

- "Monolithic features spanning 3+ pillars without clear bounded contexts"
- "Direct database queries bypassing REST API layer"
- "Synchronous operations in batch workflows (use async task queuing)"
- "Hard-coded file paths or server references (use configuration)"
- "Features that duplicate existing capabilities without deprecation plan"

---

## Section 7 — Architecture & Technical Constraints [LAYER 1]

### 7.1 Technology Stack

- **Runtime:** Kubernetes, Java (OpenJDK 17), Apache Tomcat 8.5/9, Node.js (for UI services)
- **Cloud:** AWS, Azure, GCP, Doxee proprietary DC (any-prem strategy)
- **Standards:** BPMN 2.0, REST, OpenAPI 3.0, XSLT, XSL-FO, WebDAV, OAuth/OIDC

### 7.2 Deployment Models

| Model | Availability |
|-------|-------------|
| SaaS Multi-Cloud | GA (primary) |
| PaaS | GA |
| On-Premise | GA (legacy but supported) |
| Hybrid | GA |
| Public Cloud Dedicated | GA |

### 7.3 Constraints

[HARD] All new features MUST expose REST APIs with OpenAPI 3.0 specs
[HARD] NEVER introduce on-premise-only or cloud-only logic (must work in all deployment models)
[HARD] ALWAYS design for horizontal scaling (stateless services, distributed data stores)
[SOFT] PREFER event-driven architecture for real-time features (Kafka, message queues)
[SOFT] PREFER existing DT3 operators over custom transformation logic
[SOFT] PREFER WebDAV Content Repository for all resource storage (not local filesystem)

### 7.4 Performance Targets

| Metric | Target |
|--------|--------|
| Batch throughput | 100,000 pages/hour (tier 1 SLA) |
| On-demand response (p95) | <5 seconds |
| API response (p95) | <500ms |
| Pvideo/Pweb concurrent views | 10 views/second per template |
| Platform availability | 99.9% (SaaS) |

---

## Section 8 — Business Model & Market Segments [LAYER 1]

### 8.1 Revenue Model

- **Primary:** SaaS subscription (base platform) + volume-based consumption (pages, pURLs, GB storage, emails, SMS)
- **Secondary:** Managed services (EUR 100K/FTE/year), professional services (EUR 350-650/day), premium support (10-20% of net)
- **Implication:** Requirements MUST track consumption metrics (pages rendered, pURLs generated, storage used, emails sent, API calls)

### 8.2 Target Verticals

| Vertical | Priority | Key Use Cases |
|----------|----------|---------------|
| Telco | P1 | Bills, contracts, service notifications, Pvideo for retention |
| Utilities | P1 | Bills, payment reminders, service updates, compliance reporting |
| Finance/Insurance | P1 | Statements, contracts, regulatory disclosures (MiFID II, Solvency II), onboarding |
| Healthcare | P2 | Patient communications, appointment reminders, compliance (HIPAA) |
| Public Administration | P2 | Citizen notifications, forms, compliance (EAA, eIDAS), accessible documents |

### 8.3 Pricing Constraints

- Volume tiers: features must not assume flat-rate pricing; every consumption metric must map to pricing SKU
- Free tiers: all volume products include EUR 0 placeholder tier for quoting flexibility
- Percent-of-total add-ons: Sandbox (10%), Premium Support (10%), 24/7 Support (20%), Premium KPI (25%) calculated on net subscription
- Geographic pricing: IT/AT/DE share identical list prices (intercompany adjustments for AT/DE only)

---

## Section 9 — Brand Voice & UX Principles [LAYER 1]

### 9.1 Terminology Standards

| Internal Name | Customer-Facing Name | Usage Rule |
|--------------|---------------------|-----------|
| ix | Interactive Experience | Marketing materials, sales |
| dx | Document Experience | Marketing materials, sales |
| px | Paperless Experience | Marketing materials, sales |
| Pvideo | Doxee Pvideo® | Always capitalized, ® in first mention |
| Pweb | Doxee Pweb® | Always capitalized, ® in first mention |
| DT3 | Data Transformation | User docs (no version number) |
| Batch Workflows | Batch Workflows | Consistent across platform |
| On-Demand Workflows | On-Demand Workflows | Consistent across platform |
| Content Repository | Repository | Shorten in UI labels |

### 9.2 Voice & Tone

- **Voice:** Professional, authoritative, innovative — "Built for humans. Powered by AI."
- **UX Principle:** "Complexity made simple" — hide batch processing, BPMN, XSL-FO behind clean dashboards
- **Design System:** Unified Portal (Home | Design | Operate | Analyze | Support | Admin)
- **Navigation:** Progressive disclosure; contextual help; search-first; responsive

### 9.3 Accessibility

[HARD] WCAG 2.1 AA for all web UIs (Business Designer, Composer, Workplace, Pweb output). PDF/UA for all document outputs. EAA compliance mandatory June 2025.

---

## Section 10 — Regulatory & Compliance [LAYER 2]

### 10.1 GDPR

- **Key articles:** Art. 17 Right to Erasure, Art. 25 Privacy by Design, Art. 35 DPIA, Art. 32 Security
- **Feature constraints:**
  - All data entities must have purge API (Art. 17)
  - PII detection in templates and content (Art. 25)
  - Consent management for pURL access and tracking (Art. 6)
  - Data retention policies configurable per tenant (Art. 5)
- **Checklist:** DPIA required for features processing sensitive data; consent flows for tracking; anonymization for analytics

### 10.2 eIDAS (EU Regulation 910/2014)

- **Channels:** PEC (certified email), SERC (certified delivery), SERCQ (qualified certified delivery)
- **Feature constraints:**
  - Electronic signatures: FES (simple), FEA (advanced), FEQ (qualified) — different security requirements
  - Timestamp crystallization (blockchain-based marcatura temporale) for legal validity
  - Qualified Trust Service Provider integration required for SERC/SERCQ
- **Roadmap:** eIDAS 2.0 (EU Digital Identity Wallet) expected 2026-2027

### 10.3 EAA (European Accessibility Act)

- **Requirements:** WCAG 2.1 AA for web content; PDF/UA for document outputs
- **Deadline:** June 28, 2025 (mandatory for EU entities)
- **Feature constraints:**
  - All new web UIs must pass WCAG 2.1 AA validation
  - PDF renderer must support PDF/UA tags
  - Templates must support alt-text for images, semantic structure
  - Keyboard navigation required (no mouse-only interactions)

### 10.4 Italian-Specific

- **AgID/ACN:** Italian regulatory recognition for digital services; Doxee is accredited
- **Conservazione Digitale:** Legal digital preservation per CAD (Codice Amministrazione Digitale); ISO 14721 (OAIS), UNI SInCRO 11386
- **Fatturazione Elettronica:** E-invoicing via SDI (Sistema di Interscambio) for B2G, B2B, B2C
- **Ordine Elettronico:** E-ordering for Public Administration via PEPPOL/NSO

---

## Section 11 — Existing Feature Inventory [LAYER 2]

### DESIGN

| Module | Key Features | Status |
|--------|-------------|--------|
| Data Designer | Data schema definition, XML mapping | GA |
| DT3 (DP3 only) | ETL operators, data transformation pipelines, CSV/XML/TXT/PDF/AFP parsing | GA |
| Template Designer | XSL-FO document templates (desktop rich client), charts, assertions, tracing | GA |
| Business Designer | Web-based template editor, WYSIWYG, AI assistance (OpenAI, Mistral, DeepL, Gemini, Azure OpenAI), spell check, versioning, template comparison | GA |
| Video Designer | Pvideo template authoring, AI text-to-speech, User-Directed Storytelling (UDS), scene personalization | GA |
| Process Designer | BPMN workflow visual designer, task types, custom activities (Java), XML process definitions | GA |

### ENGAGEMENT

| Module | Key Features | Status |
|--------|-------------|--------|
| Workplace | Collaborative document workspace, task management, human-in-the-loop workflows | GA |
| Composer | Ad-hoc document composition, WYSIWYG editor, insertion points, refreshables, AI assistance, form filling, e-signatures, GPS location | GA |
| Pweb | Interactive microsites, personalized forms, PURL-driven, e-commerce, chatbots, self-service portals | GA |
| Pvideo | Personalized interactive video, PURL distribution, AI-powered customization, engagement tracking | GA |
| Digital Archive | Centralized repository, metadata search, short/long-term archiving, encryption, permission-based access, PURL generation | GA |

### INSIGHTS

| Module | Key Features | Status |
|--------|-------------|--------|
| Customer Insights | Behavioral analytics, engagement tracking, A/B testing, CRM/marketing automation integration | GA |
| Process Insights | Real-time monitoring, execution status, troubleshooting, performance dashboards | GA |
| Channel Insights | Communication effectiveness metrics, SLA tracking, individual document tracking, BI integration | GA |
| Customer Data Hub | Centralized customer intelligence, segmentation, unified data foundation | Beta |

### INTEGRATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Salesforce App | Native marketplace app, document generation from Salesforce, template selection, workflow triggers | GA |
| SAP App | Native marketplace app, ERP integration patterns, data sync | GA |
| Dynamics 365 App | Native marketplace app, CRM integration, workflow automation | GA |
| REST APIs | On-demand generation, PURL generation, archive extraction, workflow execution, repository access | GA |

### AUTOMATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Process Engine | BPMN 2.0 execution, batch/on-demand orchestration, task chaining, error handling, retry logic, data stores, variables, REST API | GA |
| Batch Jobs | Scheduled processing, high-volume (100K+ pages/hr), parallel execution, sampling, production approvals | GA |
| On-Demand Jobs | API-triggered generation, horizontal scaling, 5-second response SLA, 3 concurrent requests (standard), elastic spike handling | GA |
| Omnichannel Engine | Email, SMS, SFTP, PEC, SERC, SERCQ, AppIO, print routing, automatic/centralized distribution | GA |

### ADMINISTRATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Command Center | Web-based admin console, environment overview, start/stop/restart, configuration management, stateless/scalable | GA |
| Repository | Resource storage (WebDAV), versioning (check-in/check-out), ACLs, deployment across environments, multi-environment support | GA |
| User Manager / Settings | RBAC, user/role/permission management, SSO (LDAP, AD, OAuth/OIDC), multi-tenant account management | GA |
| Batch Workloads | Resource scheduling, cost optimization, SLA-based execution, configurable parallel jobs, memory allocation per environment | GA |
| Doxee University | eLearning portal, AI-powered training, guided paths, certification, on-demand courses | GA |

### AI FOUNDATION

| Capability | Description | Status |
|-----------|------------|--------|
| AI-Assisted Authoring | OpenAI, Mistral, Gemini, Azure OpenAI integration; free-form prompts, quick actions (translate, rephrase, summarize), image generation (DALL-E-3) | GA (Business Designer, Composer) |
| Content Generation | Template and content generation via generative AI | Beta |
| Template Migration | AI-assisted migration of legacy templates | Beta |
| Composer Copilot | AI copilot for document composition | Beta |
| Engagement Scoring | AI-driven engagement measurement and predictions | Planned Q2 2026 |

### ITALIAN MARKET ADD-ONS

| Feature | Description | Status |
|---------|-------------|--------|
| Conservazione Digitale a Norma | Legal digital preservation per CAD; AgID-qualified; ISO 14721 (OAIS), UNI SInCRO 11386; web portal for search/consultation, hash/signature/temporal validation | GA |
| Fatturazione Elettronica | E-invoicing via SDI for B2G/B2B/B2C; active (AR) and passive (AP) cycles; real-time monitoring; Portale Fatture (lifecycle management); Document Cockpit (operational tracking) | GA |
| Ordine Elettronico | E-ordering for PA suppliers via NSO/PEPPOL; three modes: Semplice, Completo, Pre-concordato; UBL 3.0 auto-conversion | GA |
| Recapito Certificato | SERC (certified email via Lleidanetworks Registered e-mail), e-Recapito (via Lleidanetworks OPENUM or InPoste Tnotice), SERCQ (qualified via InPoste TnoticeQ) | GA |
| Firma Elettronica | FES/SES (simple), FEA (advanced with OTP/consent), FEQ/QES (qualified with Massive Remote Signature for high-volume); Marcatura Temporale (blockchain timestamping) | GA |
| Connectors | Namirial (e-signatures), Scrive (PDF signatures with OTP/blockchain), Zuora (billing integration) | GA |

---

## Section 12 — Italian Market-Specific Features [LAYER 2]

| Feature | Regulatory Basis | Description |
|---------|-----------------|-------------|
| Conservazione Digitale a Norma | CAD (Codice Amministrazione Digitale), ISO 14721 (OAIS), UNI SInCRO 11386 | Legal preservation for fiscal/employment documents; AgID-qualified; 4B+ documents preserved; 400+ legal entities managed; interoperability via SInCRO standard |
| Fatturazione Elettronica | Italian/EU e-invoicing regulations | Fully managed AR/AP cycle via SDI; Portale Fatture (search/view/manage); Document Cockpit (real-time tracking/queue management) |
| Portale Fatture | Italian e-invoicing regulations | Centralized interface for active/passive e-invoice lifecycle (search, detailed view, management) |
| Document Cockpit | Italian e-invoicing regulations | Operational management for tracking/managing e-invoicing documents in configurable time periods; pre-delivery interaction, queue management, real-time DB access |
| Recapito Certificato (SERC/SERCQ) | eIDAS Art. 3 n.36, Art. 43 c.1, Art. 44 | Certified delivery with legal evidence via Qualified Trust Service Providers (Lleidanetworks, InPoste) |
| Firma Elettronica (FES/FEA/FEQ) | eIDAS electronic signature standards | Simple, advanced, qualified e-signatures; Massive Remote Signature for automated high-volume signing |
| Marcatura Temporale | Italian/EU regulations for legal validity | Blockchain-based timestamp crystallization for third-party opposability |
| AppIO Integration | Italian Public Administration digital services | Integration with Italian government's citizen app for push notifications |

---

## Section 13 — Rabbit Hole Registry [LAYER 2]

```yaml
rabbit_holes:

  - area: "XSL-FO template debugging"
    risk: "XSL-FO transformation errors are notoriously difficult to debug; complex XPath expressions fail silently or produce cryptic errors"
    mitigation: "Template Designer includes tracing and assertions; Business Designer has visual rule editor with test/run; prefer visual tools over hand-coding XSL"

  - area: "Multi-tenant data isolation"
    risk: "Tenant boundary violations can leak sensitive data; complex ACL hierarchies create security holes"
    mitigation: "RBAC enforced at Content Repository level (WebDAV ACLs); all API requests validate tenant context; automated tenant isolation tests in CI/CD"

  - area: "High-volume batch performance tuning"
    risk: "100K+ pages/hour requires careful resource allocation; memory leaks or inefficient transformations can crash batch jobs"
    mitigation: "Batch Workloads component controls parallel job limits, memory allocation; horizontal scaling of Process Engine instances; sampling and production approval stages catch issues pre-production"

  - area: "Legacy data migration"
    risk: "Customer template estates are often undocumented, inconsistent, and fragile; migrating 1000s of templates is error-prone and time-consuming"
    mitigation: "AI-assisted template migration tools in Beta (Q1 2026 GA); InspireXpress-style auto content extraction planned Q3 2026; phased migration approach with parallel run"

  - area: "PURL security and abuse"
    risk: "PURLs with weak hashing can be guessed; unlimited PURL lifetime creates privacy risk"
    mitigation: "Hash-signed PURLs with configurable expiration; rate limiting on PURL access; custom domain support to avoid shared URL reputation damage"

  - area: "Real-time event-driven workflows at scale"
    risk: "On-demand workflows must respond in <5 seconds; synchronous processing patterns don't scale; event storms can overwhelm the system"
    mitigation: "Process Engine supports async task queuing; horizontal scaling with load balancing; 3 concurrent requests per tenant (standard SLA) with elastic burst handling; prefer event-driven architecture over polling"
```

---

## Section 14 — Success Metrics & KPIs [LAYER 2]

### 14.1 Per-Persona Success Metrics

| Persona | Metric | Target |
|---------|--------|--------|
| `[PER:CDO]` | Time to create new template | <4 hours (from briefing to production-ready) |
| `[PER:CDO]` | Template reuse rate | >60% (via building blocks and style packages) |
| `[PER:PDS]` | Workflow automation rate | >80% (% of communications automated vs. manual) |
| `[PER:PDS]` | Mean time to resolution (MTTR) for failed jobs | <30 minutes |
| `[PER:BUS]` | Self-service communication creation | >70% (no IT involvement) |
| `[PER:BUS]` | Time to send ad-hoc communication | <15 minutes (from start to delivered) |
| `[PER:ADM]` | User provisioning time | <10 minutes (from request to active user) |
| `[PER:ADM]` | Audit query response time | <5 seconds (compliance audit queries) |
| `[PER:DEV]` | Time to integrate new system | <2 weeks (from kickoff to first working integration) |

### 14.2 Platform-Level KPIs

| KPI | Current | Target | Timeline |
|-----|---------|--------|----------|
| Customer Digital Engagement Rate (North Star) | 42% interactive | 60% | Q4 2027 |
| Pvideo engagement rate vs. PDF | 3.2x | 4.0x | Q4 2026 |
| Template estate reduction (via AI rationalization) | N/A (no tool) | 50-70% | Q3 2026 |
| Self-service feature adoption (business users) | 58% | 75% | Q2 2026 |
| API-first coverage (% features with REST API) | 85% | 100% | Q4 2026 |
| Geographic revenue diversification (% non-CEE) | 30% | 50% | Q4 2026 |
| AI maturity positioning (QKS Matrix) | Scaling for Impact | Industry Pioneer | Q4 2026 |

### 14.3 Requirements Quality Metrics

| Metric | Target |
|--------|--------|
| Clarity score (Engineering review, 1-10) | >= 8 |
| Feasibility rate (% implementable without clarification) | >= 85% |
| Duplication rate (% reinventing existing features) | < 5% |
| Compliance pass rate (GDPR/EAA/eIDAS validation) | >= 95% |

---

## Section 15 — Sustainability (Hyperion) [LAYER 2]

- **System:** Hyperion environmental impact measurement (ISO 14064-2 validated)
- **Certification:** ISO 14064-2 certified; Digital Sustainability Award 2025
- **2024 Impact:** 56,126 tons avoided CO₂; 310,849 trees saved equivalent
- **Methodology:** Tracks digital vs. print environmental impact (paper, energy, transport)
- **Requirement:** All features must consider digital-vs-print environmental impact; Hyperion metrics integrated into customer dashboards

---

## Section 16 — European Sovereignty Context [LAYER 2]

- **Positioning:** All-European platform (HQ Italy; offices Austria, Germany, Czech Republic, Slovakia); all data processing within EU
- **GDPR-native:** Privacy by design from architecture (not bolted-on compliance)
- **Geographic expansion:** DACH region (Germany, Austria, Switzerland), Central/Eastern Europe, Nordic countries
- **Competitive advantage:** vs US-headquartered vendors (Quadient, Smart Communications, OpenText) in regulated European verticals (public sector, finance, healthcare)
- **Constraints:**
  - Data residency requirements by region (e.g., German public sector: data must stay in Germany)
  - Schrems II implications (EU-US data transfers require SCCs and impact assessments)
  - Preference for EU-based sub-processors and cloud providers

---

## Section 17 — Analyst Recognition & Market Position [LAYER 2]

### 17.1 Current Positions

| Report | Position |
|--------|----------|
| QKS AI Maturity Matrix for CCM 2025 | Scaling for Impact |
| Aspire CCS Leaderboard Q2 2025 | Confirmed Leader (CCM + CX) |
| QKS SPARK Matrix CCM 2025 | Strong Contender / Emerging Leader |

### 17.2 Target Position & Gap

- **Target:** Industry Pioneer in QKS AI Maturity Matrix (top-right quadrant)
- **Path:**
  1. Close AI breadth gap: add content intelligence (rationalization, similarity detection, compliance validation) — Q2-Q3 2026
  2. Close journey orchestration gap: deliver Customer Data Hub + Journey Builder — Q2-Q3 2026
  3. Expand reference customer base: 10+ new enterprise wins in Western Europe/USA — 2026
  4. Showcase innovation: thought leadership on agentic communications, European sovereignty, interactive engagement

---

## Section 18 — Requirements Examples (Few-Shot Corpus) [LAYER 2]

### Example 1: AI-Powered Template Rationalization (Competitive Parity)

```yaml
metadata:
  requirement_id: REQ-AI-001
  persona: "[PER:CDO]"
  source_sections: ["section_4.3", "section_11"]
  source_type: "competitive_parity"
  dibb_chain: "DIBB-004"
  competitive_class: "neutralization"
  confidence: 0.85
  appetite: "big_batch"
  constraint_refs: ["section_7.3: REST API required", "section_0.6: any-prem deployment"]
```

**Problem:** Content Designers at enterprise customers manage 500-2,000 template variants with significant duplication. Messagepoint's MARCIE engine demonstrates 50-90% template reduction through semantic analysis (QKS Market Intelligence). Doxee lacks automated rationalization tools, forcing manual consolidation (high effort, error-prone).

**Requirement:** The platform MUST provide AI-powered template analysis to identify duplicate/similar templates, suggest consolidation opportunities, and auto-generate reusable building blocks.

**Acceptance Criteria:**

```gherkin
Scenario: Analyze template estate for duplication
  Given a tenant with 1,000+ document templates in the Repository
  When the Content Designer initiates "Template Rationalization Analysis"
  Then the system analyzes all templates using semantic similarity detection
  And identifies clusters of similar templates (>70% content overlap)
  And presents a ranked list of consolidation opportunities
  And estimates effort savings (hours saved by consolidation)

Scenario: Auto-generate reusable building blocks
  Given a cluster of 20 similar invoice templates
  When the Content Designer selects "Generate Building Blocks"
  Then the system extracts common sections (header, footer, terms)
  And creates Template Part Package with reusable components
  And proposes refactored templates using the new building blocks
  And Content Designer approves/rejects proposed changes

Scenario: Track rationalization impact
  Given a completed rationalization project
  When the System Administrator views "Platform Insights"
  Then the dashboard shows template count reduction (% and absolute)
  And maintenance effort reduction estimate
  And environmental impact (reduced storage, processing)
```

**Rationale:** Messagepoint's MARCIE gives them competitive edge in legacy modernization. Doxee must match this to defend installed base and accelerate migration deals (DIBB-004). Aligns with BET-AI01 (AI Foundation maturity).

---

### Example 2: Customer Journey Builder (Differentiation)

```yaml
metadata:
  requirement_id: REQ-CXM-001
  persona: "[PER:PDS]"
  source_sections: ["section_2 (DIBB-001)", "section_4.3"]
  source_type: "strategic_belief"
  dibb_chain: "DIBB-001"
  competitive_class: "differentiation"
  confidence: 0.75
  appetite: "big_batch"
  constraint_refs: ["section_0.6: REST API", "section_7.3: event-driven architecture", "section_10.1: GDPR consent"]
```

**Problem:** Process Designers can automate individual communications (batch, on-demand) but lack visibility into multi-step customer journeys. Quadient Inspire Journey and Smart Communications SmartPATH provide end-to-end orchestration. Doxee's gap in journey management limits competitive positioning (QKS: "not yet a full-suite journey solution").

**Requirement:** The platform MUST provide a visual Customer Journey Builder to design, execute, and optimize multi-channel communication sequences triggered by customer events and behaviors.

**Acceptance Criteria:**

```gherkin
Scenario: Design multi-step journey
  Given a Process Designer role
  When I create a new "Customer Journey" in Journey Builder
  Then I can visually design a journey with steps: trigger event, wait/delay, decision branch, communication action, goal
  And I can configure trigger events (e.g., "Contract Renewal Due in 30 Days")
  And I can add communication actions (email, SMS, Pvideo, Pweb, Composer task)
  And I can define decision branches based on customer behavior (e.g., "Opened email?" → Yes/No paths)
  And I can set journey goals (e.g., "Contract Renewed")

Scenario: Execute journey with real-time adaptation
  Given an active journey "Contract Renewal Campaign"
  When a customer enters the journey (trigger event fires)
  Then the system executes the first step (e.g., send personalized email)
  And tracks customer behavior (email opened, link clicked, no action)
  And adapts next step based on behavior (e.g., if opened → send Pvideo; if no action → send SMS reminder)
  And continues until goal reached or journey timeout

Scenario: Monitor journey performance
  Given a running journey with 10,000 customers
  When the Process Designer views "Journey Analytics"
  Then the dashboard shows funnel visualization (% completing each step)
  And identifies drop-off points (where customers exit journey)
  And measures goal conversion rate
  And compares A/B test variants

Scenario: GDPR compliance for journey tracking
  Given a customer in an active journey
  When the customer withdraws consent for tracking
  Then the system immediately stops journey execution for that customer
  And purges journey-related tracking data per Art. 17 GDPR
  And logs consent withdrawal in audit trail
```

**Rationale:** QKS identifies journey orchestration as critical gap for Doxee to reach "Industry Pioneer" (DIBB-001). Smart Comms acquisition of Pendula (SmartPATH) shows market urgency. Aligns with BET-JM01 and company belief #4 ("AI agents are the next CCM UI" — journey builder is stepping stone to agentic orchestration).

---

### Example 3: WCAG 2.1 AA Compliance for Pweb (Regulatory)

```yaml
metadata:
  requirement_id: REQ-EAA-001
  persona: "[PER:CDO]"
  source_sections: ["section_10.3", "section_9.3"]
  source_type: "regulatory"
  dibb_chain: null
  competitive_class: "table_stakes"
  confidence: 1.0
  appetite: "small_batch"
  constraint_refs: ["section_10.3: EAA June 2025 deadline", "section_0.6: WCAG 2.1 AA"]
```

**Problem:** European Accessibility Act (EAA) mandates WCAG 2.1 AA compliance for web content by June 28, 2025. Pweb-generated microsites currently lack automated accessibility validation, forcing manual testing (error-prone, incomplete). Public sector RFPs increasingly require accessibility certification.

**Requirement:** Pweb Designer MUST include automated WCAG 2.1 AA validation and provide real-time feedback to Content Designers during template creation.

**Acceptance Criteria:**

```gherkin
Scenario: Real-time accessibility validation in Pweb Designer
  Given a Content Designer editing a Pweb template
  When I add a new image element without alt-text
  Then the system displays a warning icon next to the image
  And the accessibility panel lists "Missing alt-text (WCAG 2.1 1.1.1 Level A)"
  And I can click "Add Alt-Text" to open inline editor
  And validation updates in real-time as I fix issues

Scenario: Comprehensive accessibility report
  Given a completed Pweb template
  When I click "Run Accessibility Check"
  Then the system generates a report with:
    - Overall score (A, AA, AAA level)
    - List of violations (grouped by WCAG principle: Perceivable, Operable, Understandable, Robust)
    - Severity level per violation (Critical, Major, Minor)
    - Suggested fixes with code examples
  And I can export report as PDF for compliance documentation

Scenario: Accessible Pweb output validation
  Given a Pweb microsite generated from validated template
  When the system renders the microsite with customer data
  Then all interactive elements have keyboard navigation
  And color contrast ratios meet WCAG 2.1 AA (4.5:1 for normal text, 3:1 for large text)
  And all form fields have associated labels
  And all dynamic content updates announce to screen readers (ARIA live regions)

Scenario: Block production if accessibility fails
  Given a Pweb template with critical accessibility violations
  When I attempt to deploy to production
  Then the system blocks deployment
  And displays "Accessibility validation failed: 3 critical violations"
  And requires me to either fix violations or explicitly acknowledge risk (with audit log entry)
```

**Rationale:** EAA compliance is legally mandated by June 2025 (section_10.3). Failure to comply blocks public sector deals and creates liability. Aligns with hard guardrail in section_0.6 ("ALWAYS design for WCAG 2.1 AA") and DIBB-003 (public sector opportunity).

---

### Example 4: Pvideo User-Directed Storytelling Enhancement (Differentiation)

```yaml
metadata:
  requirement_id: REQ-IX-001
  persona: "[PER:CDO]"
  source_sections: ["section_1.1", "section_4.2"]
  source_type: "user_research"
  dibb_chain: "DIBB-004"
  competitive_class: "differentiation"
  confidence: 0.80
  appetite: "small_batch"
  constraint_refs: ["section_0.6: REST API", "section_7.4: 10 concurrent views/sec per template"]
```

**Problem:** Content Designers creating Pvideo templates report that customers want more control over video navigation (skip to specific topics, replay sections). Current UDS (User-Directed Storytelling) supports branching paths but no rewind/replay or chapter markers. Customer engagement data shows 25% of viewers abandon video before completion.

**Requirement:** Pvideo MUST support interactive chapter markers allowing viewers to navigate non-linearly and replay sections without restarting the entire video.

**Acceptance Criteria:**

```gherkin
Scenario: Add chapter markers in Video Designer
  Given a Content Designer editing a Pvideo template
  When I add a "Chapter Marker" to a scene
  Then I can specify chapter title (e.g., "Your Energy Usage", "Payment Options")
  And I can assign a thumbnail image for the chapter
  And I can mark chapter as "Skippable" or "Mandatory"
  And the timeline shows visual chapter dividers

Scenario: Viewer navigation via chapter menu
  Given a customer viewing a personalized Pvideo
  When I click the "Chapters" button
  Then a menu appears with all chapter titles and thumbnails
  And I can click any chapter to jump directly to that scene
  And the video resumes from the start of that chapter
  And tracking records chapter selection (for engagement analytics)

Scenario: Replay section without restarting
  Given a customer who has watched 60% of a Pvideo
  When I click "Replay" on Chapter 2 ("Payment Options")
  Then the video rewinds to the start of Chapter 2
  And plays through the chapter
  And resumes from where I was before replay (or offers "Continue" button)
  And tracking records replay event

Scenario: Performance under load
  Given 100 concurrent viewers of the same Pvideo template
  When all viewers are navigating via chapter markers
  Then response time for chapter jump is <2 seconds
  And video playback remains smooth (no buffering)
  And performance meets SLA (10 concurrent views/sec per template from section_7.4)
```

**Rationale:** Pvideo is a key differentiator (section_4.2: "No competitor matches Doxee's User-Directed Storytelling"). Enhancing UDS deepens moat and aligns with North Star (60% digital engagement). Addresses DIBB-004 risk ("competitors closing gaps").

---

### Example 5: Extended RICE Prioritization in Jira Product Discovery (Table Stakes)

```yaml
metadata:
  requirement_id: REQ-PM-001
  persona: "[PER:ADM]"
  source_sections: ["section_5.1"]
  source_type: "strategic_belief"
  dibb_chain: null
  competitive_class: "table_stakes"
  confidence: 0.90
  appetite: "micro"
  constraint_refs: ["section_5.1: Jira Product Discovery tool", "section_0.6: REST API"]
```

**Problem:** Product Management uses Extended RICE formula (Reach × Impact + Cost Reducing + Cofinancing) × Confidence / Effort but calculates manually in spreadsheets. Jira Product Discovery lacks native support for Cost Reducing and Cofinancing factors. Manual calculation is error-prone and slows prioritization decisions.

**Requirement:** Jira Product Discovery MUST support custom Extended RICE formula with automated scoring and sortable priority views.

**Acceptance Criteria:**

```gherkin
Scenario: Configure Extended RICE fields
  Given a Product Manager role in Jira Product Discovery
  When I navigate to "Idea Scoring Settings"
  Then I can enable "Extended RICE Formula"
  And I can define custom fields: Reach (1-5), Impact (1-5), Confidence (50/80/100%), Effort (1-5), Cost Reducing (1-5), Cofinancing (1-5)
  And I can assign weights to each dimension (per section_5.1)
  And the system auto-calculates Priority Score = ((Reach × Impact) + Cost Reducing + Cofinancing) × (Confidence/100) / Effort

Scenario: Visualize prioritization
  Given 100 feature ideas with Extended RICE scores
  When I view the "Priority Roadmap"
  Then ideas are sorted by Priority Score (descending)
  And I can filter by score threshold (P1 >= 8.0, P2 >= 5.0, P3 >= 2.0 per section_5.2)
  And I can view heatmap: X-axis = Impact, Y-axis = Effort, bubble size = Priority Score

Scenario: API access for automation
  Given a REST API client
  When I request GET /api/ideas?sort=priority_score
  Then the response includes all ideas with calculated Extended RICE scores
  And I can integrate with external BI dashboards
  And API follows OpenAPI 3.0 spec (section_0.6 hard constraint)
```

**Rationale:** Jira Product Discovery is the official prioritization tool (section_5.1). Automating Extended RICE reduces manual errors and accelerates roadmap decisions. Table stakes for Product Management tooling.

---

### Example 6: Sustainability Metrics in Customer Dashboards (Differentiation)

```yaml
metadata:
  requirement_id: REQ-ESG-001
  persona: "[PER:BUS]"
  source_sections: ["section_15", "section_0.3"]
  source_type: "strategic_belief"
  dibb_chain: null
  competitive_class: "differentiation"
  confidence: 0.70
  appetite: "small_batch"
  constraint_refs: ["section_15: Hyperion environmental impact measurement", "section_0.6: REST API"]
```

**Problem:** Business Users track communication delivery metrics (open rates, click-through) but lack visibility into environmental impact. Doxee's Hyperion system calculates CO₂ savings (56,126 tons avoided in 2024) but data is not exposed to customers. Sustainability is increasingly important in B2B buying decisions (ESG criteria in RFPs).

**Requirement:** Customer-facing dashboards MUST display Hyperion sustainability metrics showing environmental impact of digital vs. print communications.

**Acceptance Criteria:**

```gherkin
Scenario: View sustainability metrics in dashboard
  Given a Business User viewing "Campaign Analytics"
  When I select a completed campaign
  Then the dashboard displays "Environmental Impact" section with:
    - Total CO₂ avoided (kg) by choosing digital over print
    - Trees saved equivalent
    - Water saved equivalent (liters)
    - Energy saved equivalent (kWh)
  And I can compare multiple campaigns
  And I can export sustainability report as PDF (for ESG reporting)

Scenario: Real-time sustainability tracking
  Given an active omnichannel campaign (50% email, 30% Pvideo, 20% print)
  When I view "Real-Time Dashboard"
  Then the system shows running totals:
    - CO₂ avoided so far (updates every 5 minutes)
    - Breakdown by channel (email = highest savings, print = zero savings)
    - Projected savings if remaining print volume converted to digital

Scenario: API access for ESG reporting
  Given a REST API client
  When I request GET /api/sustainability/campaign/{id}
  Then the response includes Hyperion metrics (CO₂, trees, water, energy)
  And I can integrate with corporate ESG reporting platforms
  And API follows OpenAPI 3.0 spec

Scenario: Accuracy validation
  Given Hyperion sustainability calculations
  When the system generates customer-facing metrics
  Then calculations are ISO 14064-2 validated (section_15)
  And data includes methodology footnote
  And disclaimer: "Estimates based on industry averages; actual impact varies by customer infrastructure"
```

**Rationale:** Hyperion is a unique differentiator (Digital Sustainability Award 2025, section_15). Exposing metrics to customers strengthens ESG positioning and supports European sovereignty narrative (environmental responsibility). Aligns with company belief #3 (European sovereignty as competitive moat).

---

## Section 19 — Requirements Generation Rules [LAYER 0]

### 19.1 Output Format

Every generated requirement MUST include:

1. **Title:** `REQ-{product_code}-{seq}` (e.g., REQ-PV-042)
2. **Problem statement:** Who has what pain, supported by what evidence
3. **Requirement statement:** Imperative, specific, testable
4. **Acceptance criteria:** Gherkin Given/When/Then format
5. **Traceability metadata:** YAML block (schema below)
6. **Rationale:** 1-2 sentences linking to DIBB chain and competitive position

### 19.2 Required Metadata Schema

```yaml
metadata:
  requirement_id: REQ-{product}-{seq}
  persona: "[PER:XXX]"
  source_sections: ["section paths from this constitution"]
  source_type: "strategic_belief | regulatory | competitive_parity | user_research"
  dibb_chain: "DIBB-XXX or null"
  competitive_class: "table_stakes | differentiation | neutralization"
  confidence: 0.0-1.0
  appetite: "micro | small_batch | big_batch"
  constraint_refs: ["constraint IDs from Sections 0.6, 7.3, 10"]
  constitution_version: "1.0.0"
  generated_at: "ISO 8601 timestamp"
```

### 19.3 Quality Gate Checklist

Before outputting any requirement, the agent MUST verify:

- [ ] **Persona mapped?** Requirement links to a `[PER:XXX]` from Section 3. If not → BLOCK.
- [ ] **Existing feature check?** Scanned Section 11 to confirm this isn't a duplicate. If duplicate → ABORT with reference.
- [ ] **Competitive classification?** Classified as Table Stakes / Differentiation / Neutralization per Section 4.
- [ ] **DIBB chain linked?** Traced to a DIBB chain from Section 2. If not → WARN.
- [ ] **Constraints checked?** Relevant [HARD] constraints from Sections 0.6 and 7.3 applied. If violation → ABORT.
- [ ] **No-gos checked?** Verified requirement is not in a forbidden area per Section 6. If match → ABORT.
- [ ] **Rabbit holes flagged?** If requirement touches Section 13 areas → include risk note.

### 19.4 Escalation Rules

| Condition | Action |
|-----------|--------|
| No `persona_id` mapped | **BLOCK** — every requirement must serve a defined persona |
| `confidence_score` < 0.7 | **ESCALATE** — flag for human PM review |
| `source_type` == `regulatory` and no `constraint_ref` | **BLOCK** — must cite specific regulation |
| No DIBB chain linkable | **WARN** — may not align with strategic priorities |
| Touches a rabbit hole (Section 13) | **FLAG** — include risk note in output |
| Matches a no-go (Section 6) | **ABORT** — do not generate |

### 19.5 INVEST Criteria

Every user story must satisfy:

- **I**ndependent — deliverable without other stories
- **N**egotiable — not over-specified; leaves room for implementation
- **V**aluable — delivers value to the persona
- **E**stimable — enough detail for engineering to scope
- **S**mall — fits within the appetite level
- **T**estable — acceptance criteria are pass/fail

### 19.6 Guardrail Echo

**IMPORTANT — RESTATEMENT OF HARD GUARDRAILS:**

[HARD] NEVER introduce features that bypass GDPR compliance (Art. 17 Right to Erasure, Art. 25 Privacy by Design)
[HARD] ALWAYS expose new capabilities via REST API with OpenAPI 3.0 specification
[HARD] NEVER create deployment-model-specific logic (features MUST work on-premise, cloud, and hybrid)
[HARD] ALWAYS design for WCAG 2.1 AA accessibility compliance (EAA requirement enforced June 2025)
[HARD] NEVER hard-code per-customer logic in core platform (use configuration, not custom code)

**If any generated requirement violates these guardrails, ABORT immediately and escalate to the human PM.**

### 19.7 Citation Requirement

Before generating each requirement, quote the specific constitution sections you are drawing from. Format:

```
> Drawing from: Section 2 (DIBB-001), Section 3 (PER:CDO), Section 7.3 (HARD: API-first)
```

This enables traceability verification and debugging of incorrect outputs.

---

## END OF CONSTITUTION

**Maintenance Protocol:**
- Version using semantic versioning (MAJOR.MINOR.PATCH)
- Monthly correction loop: Generate → Self-Review → Human Spot-Check → Accept/Reject
- Batch amendments into monthly releases to preserve prompt cache efficiency
- Read-only for AI agents; living document for humans

**Git SHA:** (to be added upon commit)
