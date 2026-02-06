# Context Engineer Persona

Reference specification for the Context Compress skill. Load this file during Pass 1 for compression techniques, templates, quality framework, and anti-patterns.

## Table of Contents

1. [Core Compression Techniques](#core-compression-techniques) (10 techniques with examples)
2. [Content Type Templates](#content-type-templates) (API, component, persona, bet, integration)
3. [Quality Assurance Framework](#quality-assurance-framework) (metrics, validation checklist)
4. [Self-Assessment Rubric](#meta-instructions-for-self-assessment) (100-point scoring)
5. [Anti-Patterns](#common-pitfalls-and-anti-patterns) (7 pitfalls with good/bad examples)
6. [Advanced Capabilities](#advanced-capabilities) (semantic graphs, version diffs, priority compression)

---

## Core Compression Techniques

### 1. Eliminate Fluff, Retain Logic

Strip marketing language and filler. Preserve 100% of constraints, versions, limits, and rules.

```markdown
BEFORE (52 tokens):
"The Doxee Platform is an innovative, easy-to-use, and highly scalable
cloud-based platform that helps enterprises optimize and streamline how
they create, manage, and deliver personalized customer communications
across multiple channels including email, SMS, print, and web."

AFTER (18 tokens):
Doxee Platform: Cloud CCM/CXM. Multi-channel (email, SMS, print, web).
API-first. Personalization engine. Enterprise SaaS.
```

**Mandatory preservation**: version constraints, hard limits, technical constraints, regulatory requirements, integration dependencies.

### 2. Structural Compression

Compression hierarchy (most to least efficient):
1. YAML/JSON blocks
2. Tables
3. Tagged lists
4. Telegraphic bullets
5. Prose paragraphs (last resort)

```markdown
BEFORE (prose):
The Campaign API allows you to create and manage marketing campaigns. It
supports both email and SMS channels. Authentication is required via OAuth2.
Rate limits are 100 requests per minute per account.

AFTER (structured):
<api name="Campaign" base="/v3/campaigns" auth="OAuth2" rate="100/min/account">
  Operations: create, read, update, delete, schedule, pause
  Channels: email, SMS
  Constraints:
    - Max recipients/batch: 10000
    - Requires: approved template + verified sender
</api>
```

### 3. Canonical Reference System

Define entities once with unique IDs, reference by ID throughout.

**Entity ID schemes:**
- Products: `[P:name]`
- Personas: `[PER:role]`
- Features: `[F:name]`
- APIs: `[API:name]`
- Constraints: `[C:id]`
- Integrations: `[INT:name]`

```markdown
<dictionary>
  [P:Pvideo]: Interactive personalized video platform. Key differentiator.
  [PER:CMO]: Chief Marketing Officer. Budget authority. CAC-focused.
  [C:GDPR17]: Right to erasure. 30-day hard delete requirement.
</dictionary>

<capability component="Campaign">
  [P:Pvideo] video campaigns target [PER:CMO]. [F:PersonalVideo] requires
  [C:GDPR17] compliance. Integrates [INT:Salesforce] for recipient lists.
</capability>
```

### 4. Cross-Document Synthesis

Synthesize across documents into unified structures. Never concatenate sequentially.

Operations: merge duplicates, resolve conflicts, map relationships, build ontologies, unify terminology.

```markdown
INPUT:
- profile.md: "Doxee is a leader in CCM/CXM..."
- product-docs/overview.md: "The Doxee Platform consists of..."
- competitive-research.md: "Doxee vs competitors..."

OUTPUT:
<platform name="Doxee" category="CCM/CXM" market="EU-leader">
  Position: #1 Italy, #3 EMEA
  Differentiators: [P:Pvideo], Italian sovereignty, GDPR-native
  Components: [P:DataDesigner], [P:BatchFlow], [P:TemplateDesigner],
              [P:CampaignMgr], [P:Pvideo], [P:SERC]
  Competitive Threats:
    - Adobe Experience Cloud (global scale, AI advantage)
    - Quadient (print heritage, enterprise install base)
</platform>
```

### 5. Layered Progressive Loading

Three tiers optimized for LLM attention curve (Liu et al., 2023: U-shaped, strongest at start/end).

- **Layer 0 (~2K tokens)**: Executive Kernel. Identity, top personas (1-line), hard guardrails, active bets, north star metric. Must pass Hologram Test.
- **Layer 1 (~10K tokens)**: Working Context. Full personas (JTBD), competitive matrix, architecture, API index, integration catalog, no-go lists.
- **Layer 2 (~18K tokens)**: Deep Reference. Regulatory details, full feature inventory, few-shot examples, edge cases.

### 6. Technical Index Extraction

Required indexes (machine-scannable):
1. **API Catalog** - endpoint, method, auth, rate limits, schemas
2. **Data Model** - entities, attributes, relationships, constraints
3. **Integration Map** - systems, protocols, auth methods, data flows
4. **File Format Registry** - supported formats, validation rules
5. **Constraint Registry** - performance limits, regulatory, technical deps

```yaml
<api_catalog>
  Campaign:
    base: /v3/campaigns
    auth: OAuth2
    rate: 100/min
    ops: [create, read, update, delete, schedule, pause]
    requires: [approved_template, verified_sender]
</api_catalog>
```

### 7. Conflict Detection and Resolution

Conflict types: version discrepancies, feature availability, terminology inconsistencies, contradictory constraints, overlapping scopes.

```markdown
<conflict id="C001" type="version" severity="medium">
  Sources:
    - api-reference.md: "Campaign API v3.2"
    - integration-guide.md: "Campaign API v3.5"
  Resolution: Use v3.5 (most recent doc timestamp)
  Status: RESOLVED
</conflict>

<conflict id="C002" type="terminology" severity="low">
  Variants: "customer", "recipient", "contact", "end-user"
  Canonical: "recipient" (aligns with API naming)
  Status: STANDARDIZED
</conflict>
```

### 8. Deduplication and Normalization

Rules: define once, single source of truth, reference don't repeat, merge similar sections.

```markdown
BEFORE (3 sources, 180 tokens):
Doc1: "Doxee supports email, SMS, print, and web delivery channels."
Doc2: "The platform can deliver via email, SMS, physical mail, and websites."
Doc3: "Available channels: email (SMTP/API), SMS (Twilio/direct), print (AFP/PostScript), web (embed)."

AFTER (45 tokens):
<channels>
  Email: SMTP/API. Providers: SendGrid, Amazon SES, custom SMTP.
  SMS: Twilio API, direct carrier. Max 160 chars/segment.
  Print: AFP, PostScript. Requires print fulfillment partner.
  Web: Embed code, PURL, hosted landing page.
</channels>
```

### 9. Semantic Chunking and Boundary Marking

Use XML-style tags for machine-precise boundaries.

```markdown
<component name="DataDesigner" layer="1" category="ETL">
  Purpose: Visual data transformation and mapping tool
  Use Cases: CSV/XML ingest -> normalize -> enrich -> export to Campaign
  Key Features: [F:VisualMapper], [F:DataValidation], [F:ScheduledImport]
  Integrations: [INT:Salesforce], [INT:SAP], [INT:SFTP], [INT:S3]
  Constraints: [C:MaxFileSize], [C:RowLimit], [C:ProcessingTime]
  Related: [See: <data_model>, <api>DataImport</api>]
</component>
```

Benefits: targeted retrieval by semantic unit, RAG-friendly chunking, partial loading.

### 10. Attention Curve Optimization

Document layout strategy:
```
[FRONT - Primacy]  Meta + Executive Kernel (L0) + hard guardrails
[UPPER THIRD]      L1 Working Context (personas, architecture, strategy)
[MIDDLE]           L2 Deep Reference (features, regulatory, edge cases)
[LOWER THIRD]      Few-Shot Examples (pattern learning)
[END - Recency]    Generation Rules + Guardrail Echo (deliberate redundancy)
```

Hard constraints appear twice (front and end) to maximize retention. This is intentional.

---

## Content Type Templates

### API Documentation

```markdown
<api name="[NAME]" base="/[version]/[resource]" layer="[0|1|2]">
  Purpose: [1-line description]
  Auth: [OAuth2 | API Key | Bearer Token]
  Rate: [N]/[min|hour]/[account|IP]
  Operations:
    create: POST /[resource] - Payload: {[key fields]} - Requires: [prerequisites]
    read: GET /[resource]/{id} - Query Params: [filters]
  Constraints: [C:*] references
  Related: [P:*], [F:*], [API:*]
</api>
```

### Product Component

```markdown
<component name="[NAME]" category="[ETL|Campaign|Analytics|...]" layer="[0|1|2]">
  Purpose: [1-line description]
  Use Cases:
    1. [Primary use case with [PER:*]]
    2. [Secondary use case]
  Key Features: [F:*] list
  Integrations: [INT:*] list
  Constraints: [C:*] with descriptions
  API: [API:*] references
  Related: [P:*] references
</component>
```

### Persona

```markdown
<persona id="[ROLE_ABBREV]" layer="1">
  Role: [Full title]
  Seniority: [C-Suite | VP | Director | Manager]
  JTBD:
    1. [Primary job with measurable outcome]
    2. [Secondary job]
  Pain Points: [friction points, cost/time drains]
  Decision Criteria: [evaluation priorities, budget constraints]
  Budget Authority: [Yes | Influencer | No]
  Success Metrics: [KPI]: [Current] -> [Target]
  Competitive Alternatives: [current solutions]
</persona>
```

### Strategic Bet

```markdown
<bet id="[ShortName]" status="[Active|Committed|Exploring]" layer="1">
  Hypothesis: [What we believe]
  Target Outcome: [Measurable impact + timeframe]
  Personas: [PER:*] list
  Required: [P:*] and [F:*] list
  Risk: [What could go wrong]
  Success Criteria: [Metric]: [Target]
</bet>
```

### Integration

```markdown
<integration id="[SystemName]" category="[CRM|ERP|ESP|...]" layer="[1|2]">
  Protocol: [REST | OData | SOAP | SFTP]
  Auth: [OAuth2 | SAML | API Key]
  Direction: [Inbound | Outbound | Bidirectional]
  Data Flows: [Source] -> [Destination]: [entities]
  Sync: [Real-time | Batch | Daily]
  Constraints: [C:*] references
  Known Issues: [quirks, workarounds]
</integration>
```

---

## Quality Assurance Framework

### Metrics

| Metric | Target | Acceptable | Poor |
|--------|--------|------------|------|
| Compression Ratio | >=60% | 50-60% | <50% |
| Semantic Preservation | 100% | >=95% | <95% |
| Entity Resolution | 100% | >=98% | <98% |
| Cross-Reference Completeness | >=90% | 80-90% | <80% |
| Deduplication Rate | >=80% | 70-80% | <70% |
| Tag Consistency | 100% | >=95% | <95% |
| Unresolved Conflicts | 0 | <=3 | >3 |

Token budgets: L0 <= 2K, L1 <= 10K, L2 <= 18K, Total <= 30K (24K target with 20% headroom).

### Validation Checklist

- [ ] Meta section: creation date, source manifest, compression stats, git SHA
- [ ] Dictionary: all canonical IDs defined, zero orphan references, aliases documented
- [ ] Layer boundaries: `<layer-0/1/2>` tags present, L0 passes Hologram Test, budgets met
- [ ] Cross-references: goals->capabilities, APIs->use cases, constraints->features, integrations->workflows
- [ ] Conflicts: all resolved with rationale documented
- [ ] Technical indexes: API catalog, integration map, constraint registry, file format registry
- [ ] Examples: few-shot for common types, anti-patterns documented, edge cases covered
- [ ] Readability: PM skims L0 in 2min, developer finds API spec in <30sec
- [ ] Token audit: no marketing fluff, no redundant phrases, minimal articles
- [ ] Guardrails echoed: hard constraints at start AND end of document

---

## Meta-Instructions for Self-Assessment

### Compression Quality (25 points)
- 5 pts: Compression ratio >=60%
- 5 pts: Zero critical facts lost
- 5 pts: All marketing fluff removed
- 5 pts: All constraints/versions/limits preserved
- 5 pts: Prose converted to structured formats

### Structural Quality (25 points)
- 5 pts: Three-layer architecture (L0/L1/L2)
- 5 pts: Layer 0 passes Hologram Test
- 5 pts: XML-style tags for all semantic chunks
- 5 pts: Deduplication >=80%
- 5 pts: Token budgets met

### Synthesis Quality (25 points)
- 5 pts: Cross-document relationships mapped
- 5 pts: All conflicts detected and resolved
- 5 pts: Canonical reference system complete (no orphans)
- 5 pts: Technical indexes built
- 5 pts: Terminology standardized

### Usability Quality (25 points)
- 5 pts: TOC with layer annotations
- 5 pts: Few-shot examples included
- 5 pts: Human readable (PM skims L0 in 2min)
- 5 pts: Searchable (API spec in <30sec)
- 5 pts: Validation report included

### Scoring
- 90-100: Excellent (production-ready)
- 75-89: Good (minor revisions)
- 60-74: Acceptable (gaps to address)
- <60: Insufficient (rework)

### Self-Reflection Questions
1. Hologram Test: L0 only -> directionally correct output?
2. Deduplication: any redundant info across sections?
3. Orphan check: all canonical IDs defined?
4. Conflict check: all resolved?
5. Usability: find API auth method in <30sec?

---

## Common Pitfalls and Anti-Patterns

### 1. Concatenation Instead of Synthesis

**Bad**: Joining docs end-to-end with "from doc1/doc2" headers.
**Good**: Merge into unified `<channel>`, `<component>`, etc. sections.

### 2. Prose Creep

**Bad**: "The Campaign API is a RESTful API that allows you to..."
**Good**: `<api name="Campaign" auth="OAuth2" rate="100/min/account">`

### 3. Lost Constraints

**Bad**: "DataDesigner imports data from various sources."
**Good**: Include [C:MaxFileSize]: 500MB, [C:RowLimit]: 1M rows, [C:ProcessingTime]: 10min.

### 4. Orphan References

**Bad**: Using `[INT:Salesforce]` without defining it in `<dictionary>`.
**Good**: Every ID used is defined. Every definition is used.

### 5. Flat Structure

**Bad**: 12K-token blob with no layers or semantic boundaries.
**Good**: `<layer-0>` / `<layer-1>` / `<layer-2>` with tagged sub-sections.

### 6. Unresolved Conflicts

**Bad**: `status: UNRESOLVED` with `Resolution: ???`
**Good**: Resolution with rationale, source dates, and verification.

### 7. Missing Few-Shot Examples

**Bad**: "Generate requirements that map to personas."
**Good**: Complete input->output example with persona, acceptance criteria, constraints, dependencies.

---

## Advanced Capabilities

### Semantic Graph Construction

For complex domains, build explicit entity-relationship graphs:
```markdown
<semantic_graph>
  [P:Pvideo] --implements--> [F:PersonalVideo]
  [F:PersonalVideo] --targets--> [PER:CMO]
  [API:Campaign] --schedules--> [P:Pvideo]
  [F:PersonalVideo] --requires--> [C:GDPR17]
</semantic_graph>
```

### Version Diff Synthesis

When ingesting multiple versions:
```markdown
<version_diff component="Campaign API" from="v3.2" to="v3.5">
  Added: POST /campaigns/{id}/pause, GET /campaigns/{id}/analytics
  Changed: New required "timezone" field, rate limit 50->100/min
  Deprecated: GET /campaigns/legacy
  Breaking: PUT /campaigns removed (use PATCH)
</version_diff>
```

### Priority-Based Compression

Under token pressure, compress by priority:
- **P0**: No compression (constraints, schemas, active bets, top personas)
- **P1**: Moderate (tables, telegraphic style for features, integrations)
- **P2**: Aggressive (bullet lists, references only for historical context, market analysis)

### Retrieval Optimization Hints

```markdown
<retrieval_hints>
  "How do I authenticate?" -> Load L1: <api_catalog> + <integrations>
  "Persona pain points?" -> Load L1: <personas>
  "Regulatory constraints?" -> Load L2: <regulatory> + relevant <component>
</retrieval_hints>
```
