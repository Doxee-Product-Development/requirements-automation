<!-- ================================================================== -->
<!-- DOXEE COMPANY CONSTITUTION                                         -->
<!-- TARGET: AI Agent Context (LLM-consumable)                          -->
<!-- VERSION: 0.0.0-template                                            -->
<!-- TOKEN BUDGET: ~30,000 max                                          -->
<!-- STATUS: TEMPLATE — all [PLACEHOLDER] fields require Doxee data     -->
<!--                                                                    -->
<!-- DESIGN PRINCIPLES:                                                 -->
<!--   1. Three-layer progressive loading (Layer 0/1/2)                 -->
<!--   2. U-shaped attention layout (kernel front, rules back)          -->
<!--   3. Telegraphic style (max semantic density per token)            -->
<!--   4. Define once, reference everywhere (glossary + IDs)            -->
<!--   5. [HARD]/[SOFT] constraint markers                              -->
<!--   6. Read-only for agents (enables prompt caching)                 -->
<!--   7. Versioned in git; SHA embedded in every generated artifact    -->
<!--                                                                    -->
<!-- RESEARCH BASIS: context/CONSTITUTION_DESIGN_RESEARCH.md            -->
<!-- ================================================================== -->

<!--
  LOADING PROTOCOL — agent must select layers based on task:

  Task: Quick validation / triage
    Load: Section 0 only

  Task: Epic definition / roadmap planning
    Load: Sections 0 + 1-9

  Task: User story + acceptance criteria generation
    Load: Sections 0 + 1-9 + 10-18

  Section 19 (generation rules) is ALWAYS loaded regardless of task type.
-->

<!-- ================================================================== -->
<!-- TOKEN BUDGET LEDGER                                                -->
<!-- Update estimates after filling each section.                       -->
<!-- ================================================================== -->
<!--
  SECTION  LAYER  TITLE                                    BUDGET   ACTUAL
  ──────── ───── ──────────────────────────────────────── ──────── ──────
    0       0    Executive Kernel                           2,000    ____
    1       1    Product Identity & Portfolio                 800    ____
    2       1    Strategic Context (DIBB Chains)            1,000    ____
    3       1    User Personas (JTBD)                       1,500    ____
    4       1    Competitive Landscape                      1,200    ____
    5       1    Prioritization Framework                     800    ____
    6       1    No-Go Lists & Scope Boundaries               500    ____
    7       1    Architecture & Technical Constraints          800    ____
    8       1    Business Model & Market Segments              600    ____
    9       1    Brand Voice & UX Principles                   400    ____
   10       2    Regulatory & Compliance                     1,500    ____
   11       2    Existing Feature Inventory                  2,000    ____
   12       2    Italian Market-Specific Features              800    ____
   13       2    Rabbit Hole Registry                          600    ____
   14       2    Success Metrics & KPIs                        500    ____
   15       2    Sustainability (Hyperion)                     300    ____
   16       2    European Sovereignty Context                  400    ____
   17       2    Analyst Recognition & Market Position         400    ____
   18       2    Requirements Examples (Few-Shot Corpus)     5,000    ____
   19       0    Requirements Generation Rules               1,500    ____
                                                          ────────
                                                  BUDGET   22,600
                                                HEADROOM    7,400 (25%)
                                                   TOTAL   30,000
-->


<!-- ================================================================== -->
<!-- SECTION 0 — EXECUTIVE KERNEL [LAYER 0] (~2,000 tokens)             -->
<!-- CRITICAL: If context window is full, keep ONLY this + Section 19.  -->
<!-- HOLOGRAM TEST: An agent seeing only this section must produce       -->
<!-- directionally correct output — right persona, right constraints,   -->
<!-- right competitive category.                                        -->
<!-- ================================================================== -->

<section_0 layer="0">

## 0. Executive Kernel

### 0.1 Constitution Manifest

```xml
<constitution_toc>
  <section id="0"  layer="0" tokens="~2000">Executive Kernel</section>
  <section id="1"  layer="1" tokens="~800">Product Identity & Portfolio</section>
  <section id="2"  layer="1" tokens="~1000">Strategic Context (DIBB Chains)</section>
  <section id="3"  layer="1" tokens="~1500">User Personas (JTBD)</section>
  <section id="4"  layer="1" tokens="~1200">Competitive Landscape</section>
  <section id="5"  layer="1" tokens="~800">Prioritization Framework</section>
  <section id="6"  layer="1" tokens="~500">No-Go Lists & Scope Boundaries</section>
  <section id="7"  layer="1" tokens="~800">Architecture & Technical Constraints</section>
  <section id="8"  layer="1" tokens="~600">Business Model & Market Segments</section>
  <section id="9"  layer="1" tokens="~400">Brand Voice & UX Principles</section>
  <section id="10" layer="2" tokens="~1500">Regulatory & Compliance</section>
  <section id="11" layer="2" tokens="~2000">Existing Feature Inventory</section>
  <section id="12" layer="2" tokens="~800">Italian Market-Specific Features</section>
  <section id="13" layer="2" tokens="~600">Rabbit Hole Registry</section>
  <section id="14" layer="2" tokens="~500">Success Metrics & KPIs</section>
  <section id="15" layer="2" tokens="~300">Sustainability (Hyperion)</section>
  <section id="16" layer="2" tokens="~400">European Sovereignty Context</section>
  <section id="17" layer="2" tokens="~400">Analyst Recognition & Market Position</section>
  <section id="18" layer="2" tokens="~5000">Requirements Examples (Few-Shot Corpus)</section>
  <section id="19" layer="0" tokens="~1500">Requirements Generation Rules</section>
</constitution_toc>
```

### 0.2 Identity

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Write a single telegraphic paragraph. No marketing language.
     Format: [Name]: [Type]. [Core offering]. [Key differentiators].
     Example: "Doxee S.p.A.: Cloud-native CCM/CXM vendor. Transforms
     static documents into interactive experiences (Pvideo, Pweb).
     European-sovereign. GDPR-native. API-first."
-->

[PLACEHOLDER — Company identity paragraph. One paragraph, telegraphic style.]

### 0.3 Glossary

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Define every domain term ONCE here. Use short IDs in brackets.
     Reference these IDs throughout the rest of the constitution.
     All subsequent sections should use the abbreviation, never the full term.
     Keep alphabetical for agent lookup.
-->

```xml
<glossary>
  CCM:    [PLACEHOLDER — definition]
  CXM:    [PLACEHOLDER — definition]
  DT3:    [PLACEHOLDER — definition]
  dx:     [PLACEHOLDER — definition]
  FEA:    [PLACEHOLDER — definition]
  FEQ:    [PLACEHOLDER — definition]
  FES:    [PLACEHOLDER — definition]
  ix:     [PLACEHOLDER — definition]
  PEC:    [PLACEHOLDER — definition]
  PURL:   [PLACEHOLDER — definition]
  Pvideo: [PLACEHOLDER — definition]
  Pweb:   [PLACEHOLDER — definition]
  px:     [PLACEHOLDER — definition]
  RBAC:   [PLACEHOLDER — definition]
  SERC:   [PLACEHOLDER — definition]
  SERCQ:  [PLACEHOLDER — definition]
  UDS:    [PLACEHOLDER — definition]
</glossary>
```

<!-- Add more terms as needed. Remove any that aren't referenced. -->

### 0.4 North Star Metric

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     A single measurable goal that all product decisions orient toward.
     Format: "[Metric name]: [Target] by [Date]"
     Example: "Customer Digital Engagement Rate: 60% interactive
     (Pvideo+Pweb) vs static (PDF/email) by Q4 2027."
-->

**North Star:** [PLACEHOLDER — single measurable metric with target and date]

### 0.5 Top Personas (Summary)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     List 3-5 primary personas. One line each: ID, role title, core JTBD.
     Full persona details go in Section 3.
     Use [PER:XXX] IDs that will be referenced in requirements metadata.
-->

| ID | Role | Primary Job-to-be-Done |
|----|------|------------------------|
| `[PER:???]` | [PLACEHOLDER — Role title] | [PLACEHOLDER — 1-sentence JTBD] |
| `[PER:???]` | [PLACEHOLDER — Role title] | [PLACEHOLDER — 1-sentence JTBD] |
| `[PER:???]` | [PLACEHOLDER — Role title] | [PLACEHOLDER — 1-sentence JTBD] |
| `[PER:???]` | [PLACEHOLDER — Role title] | [PLACEHOLDER — 1-sentence JTBD] |
| `[PER:???]` | [PLACEHOLDER — Role title] | [PLACEHOLDER — 1-sentence JTBD] |

### 0.6 Hard Guardrails

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     5-7 non-negotiable constraints. Use [HARD] marker + imperative voice.
     These are restated in Section 19 (end of document) for recency effect.
     If an agent violates any of these, it MUST abort and escalate.
     Think: "What rules, if broken, would cause a production incident,
     a compliance violation, or a strategic misalignment?"
-->

[HARD] [PLACEHOLDER — guardrail 1. Format: "NEVER..." or "ALWAYS..."]
[HARD] [PLACEHOLDER — guardrail 2]
[HARD] [PLACEHOLDER — guardrail 3]
[HARD] [PLACEHOLDER — guardrail 4]
[HARD] [PLACEHOLDER — guardrail 5]

### 0.7 Active Bets (Current Cycle)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     List active strategic bets by ID and name only.
     Full DIBB chains go in Section 2.
     Format: BET-{seq}: {name} ({target quarter})
-->

- `BET-???`: [PLACEHOLDER — Bet name] ([PLACEHOLDER — target quarter])
- `BET-???`: [PLACEHOLDER — Bet name] ([PLACEHOLDER — target quarter])
- `BET-???`: [PLACEHOLDER — Bet name] ([PLACEHOLDER — target quarter])

</section_0>


<!-- ================================================================== -->
<!-- SECTIONS 1-9 — LAYER 1: WORKING CONTEXT (~7,600 tokens)            -->
<!-- Loaded for epic/roadmap planning tasks.                            -->
<!-- ================================================================== -->

<section_1 layer="1">

## 1. Product Identity & Portfolio

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     For each product line, write a PR/FAQ-style positioning statement:
       "For [target user] who [need], [product] is a [category]
        that [key benefit]. Unlike [alternative], [product] [differentiator]."
     Then list key modules/capabilities in a table.
     Use glossary terms (ix, px, dx, etc.) — no need to redefine.
-->

### 1.1 Product Lines

**[PROD:IX] — Interactive Experience (Pvideo + Pweb)**

[PLACEHOLDER — PR/FAQ positioning statement for ix product line]

**[PROD:DX] — Document Experience**

[PLACEHOLDER — PR/FAQ positioning statement for dx product line]

**[PROD:PX] — Paperless Experience**

[PLACEHOLDER — PR/FAQ positioning statement for px product line]

**[PROD:AI] — AI Foundation**

[PLACEHOLDER — PR/FAQ positioning statement for AI capabilities]

### 1.2 Platform Capability Map

<!-- Format as table: Module | Product Line | Status (Core/Growth/New) -->

| Module | Product Line | Status |
|--------|-------------|--------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

</section_1>


<section_2 layer="1">

## 2. Strategic Context (DIBB Chains)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Encode 3-5 active DIBB chains. Each chain provides the strategic
     rationale that the agent uses to justify generated requirements.

     Chain structure:
       Data    → observed fact (with source and date)
       Insight → interpretation of data
       Belief  → hypothesis about what will happen
       Bet     → committed initiative (links to Section 0.7)
       Status  → ACTIVE | PAUSED | COMPLETED

     The agent constructs requirements FROM these chains. If a requirement
     can't trace back to a DIBB chain, it gets a WARN escalation.
-->

```yaml
dibb_chains:

  - id: DIBB-001
    data: "[PLACEHOLDER — quantitative or qualitative observation with source and date]"
    insight: "[PLACEHOLDER — what does the data mean?]"
    belief: "[PLACEHOLDER — what do we think will happen?]"
    active_bets:
      - "BET-???: [PLACEHOLDER]"
    status: ACTIVE

  - id: DIBB-002
    data: "[PLACEHOLDER]"
    insight: "[PLACEHOLDER]"
    belief: "[PLACEHOLDER]"
    active_bets:
      - "BET-???: [PLACEHOLDER]"
    status: ACTIVE

  - id: DIBB-003
    data: "[PLACEHOLDER]"
    insight: "[PLACEHOLDER]"
    belief: "[PLACEHOLDER]"
    active_bets:
      - "BET-???: [PLACEHOLDER]"
    status: ACTIVE
```

### 2.1 Company-Level Beliefs

<!-- 3-5 max. These are the overarching convictions that shape all product decisions. -->

1. [PLACEHOLDER — belief statement]
2. [PLACEHOLDER — belief statement]
3. [PLACEHOLDER — belief statement]

</section_2>


<section_3 layer="1">

## 3. User Personas (JTBD)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     5-7 personas. Use the IDs from Section 0.5.
     For each persona:
       - Role: title and context
       - Jobs (prioritized): what they are trying to accomplish
       - Pains (severity: HIGH/MED/LOW): what blocks them
       - Gains (impact: HIGH/MED/LOW): what success looks like
     Keep telegraphic. No narrative filler.

     Every AI-generated requirement MUST map to a [PER:XXX].
     If the agent cannot map a requirement, it triggers a BLOCK escalation.
-->

### `[PER:???]` — [PLACEHOLDER — Role Title]

- **Jobs:** [PLACEHOLDER — prioritized list]
- **Pains:** [PLACEHOLDER — with severity ratings]
- **Gains:** [PLACEHOLDER — with impact ratings]

### `[PER:???]` — [PLACEHOLDER — Role Title]

- **Jobs:** [PLACEHOLDER]
- **Pains:** [PLACEHOLDER]
- **Gains:** [PLACEHOLDER]

### `[PER:???]` — [PLACEHOLDER — Role Title]

- **Jobs:** [PLACEHOLDER]
- **Pains:** [PLACEHOLDER]
- **Gains:** [PLACEHOLDER]

### `[PER:???]` — [PLACEHOLDER — Role Title]

- **Jobs:** [PLACEHOLDER]
- **Pains:** [PLACEHOLDER]
- **Gains:** [PLACEHOLDER]

### `[PER:???]` — [PLACEHOLDER — Role Title]

- **Jobs:** [PLACEHOLDER]
- **Pains:** [PLACEHOLDER]
- **Gains:** [PLACEHOLDER]

</section_3>


<section_4 layer="1">

## 4. Competitive Landscape

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Three-tier classification. The agent uses this to classify every
     generated requirement as Table Stakes / Differentiation / Neutralization.

     TABLE STAKES: Competitor has it; must match to sell.
       → Agent generates with: Priority HIGH, Innovation LOW
     DIFFERENTIATION: No one does it well; build to win.
       → Agent generates with: Priority STRATEGIC, Innovation HIGH
     NEUTRALIZATION: Competitor winning deals; need "good enough."
       → Agent generates with: Priority MEDIUM, Innovation LOW
-->

### 4.1 Table Stakes (Must Match)

| Feature | Doxee Status |
|---------|-------------|
| [PLACEHOLDER] | [Competitive / Lagging / Gap] |

### 4.2 Differentiators (Build to Win)

| Feature | Advantage | Nearest Competitor |
|---------|----------|-------------------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### 4.3 Competitive Gaps (Must Close)

| Gap | Leading Vendor(s) | Priority |
|-----|------------------|----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [CRITICAL / HIGH / MEDIUM] |

### 4.4 Key Competitors

<!-- 3-5 lines per competitor max. Format:
     Name — Threat: HIGH/MEDIUM/LOW
     - Strength: [what they do best]
     - Weakness: [where they are vulnerable]
     - Response: [Doxee counter-strategy]
-->

**[PLACEHOLDER — Competitor 1]** — Threat: [PLACEHOLDER]
- Strength: [PLACEHOLDER]
- Weakness: [PLACEHOLDER]
- Response: [PLACEHOLDER]

**[PLACEHOLDER — Competitor 2]** — Threat: [PLACEHOLDER]
- Strength: [PLACEHOLDER]
- Weakness: [PLACEHOLDER]
- Response: [PLACEHOLDER]

</section_4>


<section_5 layer="1">

## 5. Prioritization Framework

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Define how the agent scores and prioritizes requirements.
     Multi-dimensional scoring avoids single-axis bias.
-->

### 5.1 Scoring Dimensions

| Dimension | Weight | Description |
|-----------|--------|-------------|
| Strategic Value | [PLACEHOLDER — 0.0-1.0] | Alignment with DIBB chains and active bets |
| Regulatory Urgency | [PLACEHOLDER] | Compliance deadlines, legal risk |
| Technical Feasibility | [PLACEHOLDER] | Complexity, dependencies, team capability |
| Customer Impact | [PLACEHOLDER] | Persona pain severity, user volume affected |
| Resource Efficiency | [PLACEHOLDER] | Reuse of existing components, build cost |

### 5.2 Priority Thresholds

| Priority | Weighted Score | Action |
|----------|---------------|--------|
| P1 | >= [PLACEHOLDER] | Must ship this cycle |
| P2 | >= [PLACEHOLDER] | Should ship; defer if P1 overflows |
| P3 | >= [PLACEHOLDER] | Nice to have; backlog |

### 5.3 Appetite Levels

<!-- From Shape Up. Controls spec depth, not time estimates. -->

| Appetite | Spec Depth Required |
|----------|-------------------|
| **Micro** | Issue title + 1-paragraph description |
| **Small Batch** | Problem + solution sketch + acceptance criteria |
| **Big Batch** | Full spec: data model, API contracts, Gherkin scenarios |

</section_5>


<section_6 layer="1">

## 6. No-Go Lists & Scope Boundaries

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Explicit exclusions that prevent the agent from generating
     requirements in forbidden areas. Two categories:
       - Permanent: never, regardless of cycle
       - Current cycle: deferred, not abandoned
-->

### 6.1 Permanent No-Gos

```yaml
permanent_no_gos:
  - "[PLACEHOLDER — e.g., On-premise-only features]"
  - "[PLACEHOLDER — e.g., Custom per-client logic in core platform]"
  - "[PLACEHOLDER — e.g., Features requiring manual ops at scale]"
```

### 6.2 Current Cycle No-Gos

```yaml
current_cycle_no_gos:
  - area: "[PLACEHOLDER]"
    reason: "[PLACEHOLDER — why deferred]"
    revisit: "[PLACEHOLDER — when to reconsider, e.g., H2 2026]"
```

### 6.3 Anti-Patterns

<!-- Explicitly forbidden implementation approaches. -->

- [PLACEHOLDER — e.g., "Monolithic features spanning 3+ modules"]
- [PLACEHOLDER — e.g., "Direct database queries bypassing API layer"]

</section_6>


<section_7 layer="1">

## 7. Architecture & Technical Constraints

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Factual statements about the technology stack, deployment models,
     API principles, and performance targets. Declarative style for
     context; imperative [HARD]/[SOFT] markers for constraints.
-->

### 7.1 Technology Stack

- **Runtime:** [PLACEHOLDER — e.g., Kubernetes, Java Spring Boot, Angular]
- **Cloud:** [PLACEHOLDER — e.g., AWS, Azure, GCP, proprietary DC]
- **Standards:** [PLACEHOLDER — e.g., BPMN 2.0, REST, OpenAPI 3.0, XSLT, XSL-FO]

### 7.2 Deployment Models

| Model | Availability |
|-------|-------------|
| SaaS | [PLACEHOLDER] |
| On-Premise | [PLACEHOLDER] |
| Hybrid | [PLACEHOLDER] |
| Public Cloud | [PLACEHOLDER] |

### 7.3 Constraints

[HARD] [PLACEHOLDER — e.g., "All new features MUST expose REST APIs with OpenAPI specs."]
[HARD] [PLACEHOLDER — e.g., "NEVER introduce on-premise-only logic."]
[SOFT] [PLACEHOLDER — e.g., "PREFER event-driven architecture for real-time features."]
[SOFT] [PLACEHOLDER — e.g., "PREFER existing DT3 operators over custom transformation."]

### 7.4 Performance Targets

| Metric | Target |
|--------|--------|
| Page load | [PLACEHOLDER — e.g., <2s] |
| API response (p95) | [PLACEHOLDER — e.g., <500ms] |
| Batch throughput | [PLACEHOLDER — e.g., 100k docs/hr] |
| Availability | [PLACEHOLDER — e.g., 99.9%] |

</section_7>


<section_8 layer="1">

## 8. Business Model & Market Segments

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     How Doxee makes money. Critical for "monetization" requirements.
     The agent needs this to generate features that track consumption
     metrics and align with pricing logic.
-->

### 8.1 Revenue Model

- **Primary:** [PLACEHOLDER — e.g., SaaS subscription + volume-based (transactions, minutes rendered)]
- **Secondary:** [PLACEHOLDER — e.g., managed services, professional services]
- **Implication:** [PLACEHOLDER — e.g., "Requirements MUST track consumption metrics."]

### 8.2 Target Verticals

| Vertical | Priority | Key Use Cases |
|----------|----------|--------------|
| [PLACEHOLDER] | [P1/P2/P3] | [PLACEHOLDER] |

### 8.3 Pricing Constraints

<!-- Rules that affect how features are designed. -->

- [PLACEHOLDER — e.g., "Volume tiers: features must not assume flat-rate pricing."]

</section_8>


<section_9 layer="1">

## 9. Brand Voice & UX Principles

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Short section. Terminology standards, tone, UX principles.
     The agent uses this for naming, copy, and interaction patterns.
-->

### 9.1 Terminology Standards

<!-- Define the canonical names for platform components.
     The agent must use these exact names in generated requirements. -->

| Internal Name | Customer-Facing Name | Usage Rule |
|--------------|---------------------|-----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### 9.2 Voice & Tone

- **Voice:** [PLACEHOLDER — e.g., "Professional, authoritative, innovative"]
- **UX Principle:** [PLACEHOLDER — e.g., "Complexity made simple — hide batch processing behind clean dashboards"]

### 9.3 Accessibility

[HARD] [PLACEHOLDER — e.g., "WCAG 2.1 AA for all Pweb outputs. PDF/UA for all document outputs."]

</section_9>


<!-- ================================================================== -->
<!-- SECTIONS 10-18 — LAYER 2: DEEP REFERENCE (~12,000 tokens)          -->
<!-- Loaded for user story + acceptance criteria generation.             -->
<!-- These sections are in the MIDDLE of the document (lowest attention  -->
<!-- zone) because they are consulted by explicit reference, not by      -->
<!-- ambient awareness.                                                  -->
<!-- ================================================================== -->

<section_10 layer="2">

## 10. Regulatory & Compliance Requirements

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     For each regulation, document:
       - What it requires
       - How it constrains feature design
       - Compliance checklist items

     The agent generates acceptance criteria from these constraints.
     When source_type == "regulatory", the agent MUST cite a specific
     constraint_ref from this section. Otherwise → BLOCK escalation.
-->

### 10.1 GDPR

- **Key articles:** [PLACEHOLDER — e.g., Art.17 Right to Erasure, Art.25 Privacy by Design, Art.35 DPIA]
- **Feature constraints:**
  - [PLACEHOLDER — e.g., "All data entities must have a purge API (Art.17)"]
  - [PLACEHOLDER]
- **Checklist:** [PLACEHOLDER]

### 10.2 eIDAS

- **Channels:** [PLACEHOLDER — PEC, SERC, SERCQ details]
- **Feature constraints:** [PLACEHOLDER]

### 10.3 EAA (European Accessibility Act)

- **Requirements:** [PLACEHOLDER — PDF/UA, WCAG 2.1 AA]
- **Feature constraints:** [PLACEHOLDER]

### 10.4 Italian-Specific

- **AgID/ACN:** [PLACEHOLDER]
- **Conservazione Digitale:** [PLACEHOLDER]
- **Fatturazione Elettronica:** [PLACEHOLDER]

</section_10>


<section_11 layer="2">

## 11. Existing Feature Inventory

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     List ALL existing features by platform area. The agent checks this
     before generating a new requirement to avoid duplication.
     Keep each entry to one line: Module → Feature → Status (GA/Beta/Planned).
     Reference: doxee/Doxee Platform functional architecture and components.md
-->

### DESIGN

| Module | Key Features | Status |
|--------|-------------|--------|
| Data Designer | [PLACEHOLDER] | [PLACEHOLDER] |
| DT3 | [PLACEHOLDER] | [PLACEHOLDER] |
| Template Designer | [PLACEHOLDER] | [PLACEHOLDER] |
| Business Designer | [PLACEHOLDER] | [PLACEHOLDER] |
| Video Designer | [PLACEHOLDER] | [PLACEHOLDER] |
| Process Designer | [PLACEHOLDER] | [PLACEHOLDER] |

### ENGAGEMENT

| Module | Key Features | Status |
|--------|-------------|--------|
| Workplace | [PLACEHOLDER] | [PLACEHOLDER] |
| Composer | [PLACEHOLDER] | [PLACEHOLDER] |
| Pweb | [PLACEHOLDER] | [PLACEHOLDER] |
| Pvideo | [PLACEHOLDER] | [PLACEHOLDER] |
| Digital Archive | [PLACEHOLDER] | [PLACEHOLDER] |

### INSIGHTS

| Module | Key Features | Status |
|--------|-------------|--------|
| Customer Insights | [PLACEHOLDER] | [PLACEHOLDER] |
| Process Insights | [PLACEHOLDER] | [PLACEHOLDER] |
| Tracking & Reporting | [PLACEHOLDER] | [PLACEHOLDER] |
| Channel Insights | [PLACEHOLDER] | [PLACEHOLDER] |

### INTEGRATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Salesforce App | [PLACEHOLDER] | [PLACEHOLDER] |
| SAP App | [PLACEHOLDER] | [PLACEHOLDER] |
| Dynamics 365 App | [PLACEHOLDER] | [PLACEHOLDER] |
| REST APIs | [PLACEHOLDER] | [PLACEHOLDER] |

### AUTOMATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Process Engine | [PLACEHOLDER] | [PLACEHOLDER] |
| Batch Jobs | [PLACEHOLDER] | [PLACEHOLDER] |
| On-Demand Jobs | [PLACEHOLDER] | [PLACEHOLDER] |
| Omnichannel Engine | [PLACEHOLDER] | [PLACEHOLDER] |

### ADMINISTRATION

| Module | Key Features | Status |
|--------|-------------|--------|
| Command Center | [PLACEHOLDER] | [PLACEHOLDER] |
| Repository | [PLACEHOLDER] | [PLACEHOLDER] |
| User Manager | [PLACEHOLDER] | [PLACEHOLDER] |
| Settings | [PLACEHOLDER] | [PLACEHOLDER] |
| Doxee University | [PLACEHOLDER] | [PLACEHOLDER] |

### AI FOUNDATION

| Capability | Description | Status |
|-----------|------------|--------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

</section_11>


<section_12 layer="2">

## 12. Italian Market-Specific Features

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Only loaded when generating features targeting the Italian market.
     Document each Italian-specific capability with its regulatory basis.
-->

| Feature | Regulatory Basis | Description |
|---------|-----------------|-------------|
| Conservazione Digitale a Norma | [PLACEHOLDER] | [PLACEHOLDER] |
| Fatturazione Elettronica | [PLACEHOLDER] | [PLACEHOLDER] |
| Portale Fatture | [PLACEHOLDER] | [PLACEHOLDER] |
| Document Cockpit | [PLACEHOLDER] | [PLACEHOLDER] |
| Recapito Certificato (SERC/SERCQ) | [PLACEHOLDER] | [PLACEHOLDER] |
| Firma Elettronica (FES/FEA/FEQ) | [PLACEHOLDER] | [PLACEHOLDER] |
| Marcatura Temporale (Blockchain) | [PLACEHOLDER] | [PLACEHOLDER] |
| AppIO Integration | [PLACEHOLDER] | [PLACEHOLDER] |

</section_12>


<section_13 layer="2">

## 13. Rabbit Hole Registry

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Known technical complexities the agent should FLAG rather than assume.
     Each entry: area, risk description, known mitigation.
     When the agent generates a requirement touching one of these areas,
     it should include a risk note in the output.
-->

```yaml
rabbit_holes:

  - area: "[PLACEHOLDER]"
    risk: "[PLACEHOLDER]"
    mitigation: "[PLACEHOLDER]"

  - area: "[PLACEHOLDER]"
    risk: "[PLACEHOLDER]"
    mitigation: "[PLACEHOLDER]"

  - area: "[PLACEHOLDER]"
    risk: "[PLACEHOLDER]"
    mitigation: "[PLACEHOLDER]"
```

</section_13>


<section_14 layer="2">

## 14. Success Metrics & KPIs

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Define measurable outcomes for each persona and for the platform.
     The agent uses these to generate acceptance criteria with concrete
     targets rather than vague "should improve" language.
-->

### 14.1 Per-Persona Success Metrics

| Persona | Metric | Target |
|---------|--------|--------|
| `[PER:???]` | [PLACEHOLDER] | [PLACEHOLDER] |
| `[PER:???]` | [PLACEHOLDER] | [PLACEHOLDER] |

### 14.2 Platform-Level KPIs

| KPI | Current | Target | Timeline |
|-----|---------|--------|----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### 14.3 Requirements Quality Metrics

| Metric | Target |
|--------|--------|
| Clarity score (Engineering review, 1-10) | >= 8 |
| Feasibility rate (% implementable without clarification) | >= 85% |
| Duplication rate (% reinventing existing features) | < 5% |
| Compliance pass rate | >= 95% |

</section_14>


<section_15 layer="2">

## 15. Sustainability (Hyperion)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Doxee's environmental impact measurement. Short section.
     The agent must consider digital-vs-print environmental impact
     when generating features.
-->

- **System:** [PLACEHOLDER — e.g., Hyperion environmental impact measurement]
- **Certification:** [PLACEHOLDER — e.g., ISO 14064-2 validated]
- **2024 Impact:** [PLACEHOLDER — e.g., 56,126 tons avoided CO2, 310,849 trees saved]
- **Requirement:** [PLACEHOLDER — e.g., "All features must consider digital-vs-print environmental impact."]

</section_15>


<section_16 layer="2">

## 16. European Sovereignty Context

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Doxee's data sovereignty positioning. Used by the agent when
     generating features that handle data storage, processing location,
     or cross-border data flows.
-->

- **Positioning:** [PLACEHOLDER — e.g., All-European platform, GDPR-native]
- **Geographic expansion:** [PLACEHOLDER — e.g., DACH region, Central/Eastern Europe]
- **Competitive advantage:** [PLACEHOLDER — e.g., vs US-headquartered vendors]
- **Constraints:** [PLACEHOLDER — e.g., data residency requirements by region]

</section_16>


<section_17 layer="2">

## 17. Analyst Recognition & Market Position

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     Current analyst positioning and the path to the target position.
     The agent uses this for competitive classification and
     to generate features that advance Doxee's analyst narrative.
-->

### 17.1 Current Positions

| Report | Position |
|--------|---------|
| [PLACEHOLDER — e.g., QKS SPARK Matrix] | [PLACEHOLDER — e.g., Leader] |
| [PLACEHOLDER] | [PLACEHOLDER] |

### 17.2 Target Position & Gap

- **Target:** [PLACEHOLDER — e.g., "Industry Pioneer" in QKS AI Maturity Matrix]
- **Path:**
  1. [PLACEHOLDER — e.g., Deepen AI across content lifecycle]
  2. [PLACEHOLDER]
  3. [PLACEHOLDER]

</section_17>


<section_18 layer="2">

## 18. Requirements Examples (Few-Shot Corpus)

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     6-12 examples of IDEAL requirements output. These serve as few-shot
     patterns for the agent. Cover variation across:
       - Personas (at least 3 different)
       - Requirement types (Table Stakes, Differentiation, Compliance)
       - Complexity (Micro, Small Batch, Big Batch)

     Each example MUST include:
       - Title
       - Persona mapping
       - User story OR plain-language problem statement
       - Acceptance criteria (Given/When/Then format)
       - Traceability metadata (source section, DIBB chain, confidence)
       - Competitive classification
       - Relevant constraints

     TOKEN WARNING: This section consumes ~5,000 tokens.
     Each well-formed example is ~400-800 tokens.
     Aim for 6-8 examples to stay within budget.
-->

### Example 1: [PLACEHOLDER — Title]

```yaml
metadata:
  requirement_id: REQ-[PROD]-001
  persona: "[PER:???]"
  source_sections: ["section_?.?"]
  source_type: "[strategic_belief | regulatory | competitive_parity | user_research]"
  dibb_chain: "DIBB-???"
  competitive_class: "[table_stakes | differentiation | neutralization]"
  confidence: 0.??
  appetite: "[micro | small_batch | big_batch]"
  constraint_refs: ["[PLACEHOLDER]"]
```

**Problem:** [PLACEHOLDER — who has what pain, supported by what evidence]

**Requirement:** [PLACEHOLDER — clear, imperative statement of what is needed]

**Acceptance Criteria:**

```gherkin
Scenario: [PLACEHOLDER]
  Given [PLACEHOLDER]
  When [PLACEHOLDER]
  Then [PLACEHOLDER]
```

**Rationale:** [PLACEHOLDER — 1-2 sentences linking requirement to DIBB chain and competitive position]

---

### Example 2: [PLACEHOLDER — Title]

<!-- Repeat structure from Example 1. Choose a different persona,
     competitive class, and appetite level. -->

[PLACEHOLDER — Full example following the same structure]

---

### Example 3: [PLACEHOLDER — Title]

[PLACEHOLDER — Full example]

---

### Example 4: [PLACEHOLDER — Title]

[PLACEHOLDER — Full example]

---

### Example 5: [PLACEHOLDER — Title]

[PLACEHOLDER — Full example]

---

### Example 6: [PLACEHOLDER — Title]

[PLACEHOLDER — Full example]

</section_18>


<!-- ================================================================== -->
<!-- SECTION 19 — REQUIREMENTS GENERATION RULES [LAYER 0] (~1,500 tok)  -->
<!-- ALWAYS LOADED. Placed at END of document for recency effect.       -->
<!-- This section tells the agent HOW to generate requirements.         -->
<!-- ================================================================== -->

<section_19 layer="0">

## 19. Requirements Generation Rules

<!-- INSTRUCTIONS FOR CONTEXT ENGINEER:
     This section is mostly complete as-is. Review and adjust the
     escalation thresholds and guardrail echo to match the actual
     guardrails defined in Section 0.6.
-->

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
  persona: "[PER:???]"
  source_sections: ["section paths from this constitution"]
  source_type: "strategic_belief | regulatory | competitive_parity | user_research"
  dibb_chain: "DIBB-??? or null"
  competitive_class: "table_stakes | differentiation | neutralization"
  confidence: 0.0-1.0
  appetite: "micro | small_batch | big_batch"
  constraint_refs: ["constraint IDs from Sections 0.6, 7.3, 10"]
  constitution_version: "[PLACEHOLDER — git SHA or semver]"
  generated_at: "ISO 8601 timestamp"
```

### 19.3 Quality Gate Checklist

Before outputting any requirement, the agent MUST verify:

- [ ] **Persona mapped?** Requirement links to a `[PER:???]` from Section 3. If not → BLOCK.
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

<!-- CRITICAL: Restate the hard guardrails from Section 0.6 here.
     This exploits the recency effect — the last thing the agent reads
     before generating output. Copy them EXACTLY from Section 0.6.
-->

**IMPORTANT — RESTATEMENT OF HARD GUARDRAILS:**

[HARD] [PLACEHOLDER — copy guardrail 1 from Section 0.6]
[HARD] [PLACEHOLDER — copy guardrail 2 from Section 0.6]
[HARD] [PLACEHOLDER — copy guardrail 3 from Section 0.6]
[HARD] [PLACEHOLDER — copy guardrail 4 from Section 0.6]
[HARD] [PLACEHOLDER — copy guardrail 5 from Section 0.6]

**If any generated requirement violates these guardrails, ABORT immediately and escalate to the human PM.**

### 19.7 Citation Requirement

Before generating each requirement, quote the specific constitution sections you are drawing from. Format:

```
> Drawing from: Section 2 (DIBB-001), Section 3 (PER:CDO), Section 7.3 (HARD: API-first)
```

This enables traceability verification and debugging of incorrect outputs.

</section_19>


<!-- ================================================================== -->
<!-- END OF CONSTITUTION                                                -->
<!-- ================================================================== -->

<!--
  MAINTENANCE PROTOCOL:

  1. This document is READ-ONLY for AI agents.
     Agents generate FROM it. They never modify it.

  2. This document is a LIVING DOCUMENT for humans.
     Monthly correction loop:
       Generate → Self-Review → Human Spot-Check → Accept/Reject
       → If rejected: identify constitution gap → amend → version release

  3. Version using semantic versioning:
       MAJOR: structural changes (sections added/removed)
       MINOR: content changes (new persona, new DIBB chain)
       PATCH: corrections (typos, threshold adjustments)

  4. After each version release, update the constitution_version field
     in Section 19.2 metadata schema.

  5. Batch amendments into monthly releases to preserve prompt cache
     efficiency. Frequent edits invalidate the cache.

  AGENT READINESS CHECKLIST (verify before deployment):

  [ ] Hologram test — Layer 0 alone produces directionally correct output
  [ ] Context completeness — all domain knowledge covered
  [ ] Constraint clarity — guardrails unambiguous
  [ ] Persona coverage — every target user defined with JTBD
  [ ] Competitive context — features classifiable into 3 tiers
  [ ] Traceability — every requirement traceable to a constitution section
  [ ] Escalation paths — thresholds and triggers clear
  [ ] Cache-friendliness — constitution stable enough for prompt caching
  [ ] Token budget — total under 30,000 tokens
  [ ] Few-shot quality — examples cover persona, type, and complexity variation
-->
