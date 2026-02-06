# AI-Consumable Company Constitution: Consolidated Research Report
## Best Practices for LLM-Driven Requirements Automation

**Research Date:** February 6, 2026
**Author:** Claude Code Research Agent
**Version:** 2.0.0
**Purpose:** Authoritative reference for designing a 20-section AI-consumable constitution template
**Target Application:** Doxee Speckit constitution development
**Classification:** Internal Use -- Strategic

---

## Executive Summary

This document consolidates all research findings from three specialized research reports into a single authoritative reference for designing the Speckit constitution template. The constitution is a machine-optimized context document that enables an LLM agent to autonomously generate high-quality product requirements for the Doxee Platform.

**Design targets for the constitution:**
- Section 0: Machine-readable header and executive kernel (~2K tokens)
- Sections 1-18: Full constitution body with LAYER tags (~28K tokens)
- Section 19: Requirements generation rules (~2K tokens)
- Total budget: ~30K tokens maximum

**Key design constraints:**
1. **Information compaction** -- Maximum semantic density per token
2. **Progressive discovery** -- Layer 0 / Layer 1 / Layer 2 loading tiers
3. **Context window efficiency** -- Front-loading, deduplication, structured delimiters
4. **Prompt-friendly conventions** -- Imperative statements, explicit enumeration, [HARD]/[SOFT] markers

**Research sources synthesized:**
- `docs/llm-consumable-context-design-research.md` -- AI-native document architecture
- `docs/competitive-landscape-research.md` -- Doxee and competitor analysis
- `docs/pm-frameworks-constitution-research.md` -- PM frameworks, traceability, strategic reasoning

---

## Table of Contents

1. [AI-Native Document Architecture Patterns](#1-ai-native-document-architecture-patterns)
2. [Context Window Optimization and the "Lost in the Middle" Problem](#2-context-window-optimization-and-the-lost-in-the-middle-problem)
3. [Progressive Discovery and Layered Loading](#3-progressive-discovery-and-layered-loading)
4. [Information Compaction Techniques](#4-information-compaction-techniques)
5. [Structured Delimiters and Prompt-Friendly Conventions](#5-structured-delimiters-and-prompt-friendly-conventions)
6. [AI Coding Tool Context File Patterns](#6-ai-coding-tool-context-file-patterns)
7. [PM Frameworks for Strategic Context Encoding](#7-pm-frameworks-for-strategic-context-encoding)
8. [Requirements Traceability and Metadata Schema](#8-requirements-traceability-and-metadata-schema)
9. [Doxee Competitive Intelligence for Constitution Encoding](#9-doxee-competitive-intelligence-for-constitution-encoding)
10. [20-Section Constitution Blueprint](#10-20-section-constitution-blueprint)
11. [Validation Framework](#11-validation-framework)

---

## 1. AI-Native Document Architecture Patterns

### 1.1 Context as Code Philosophy

Modern AI coding tools treat project context as first-class infrastructure. The constitution must follow the same principles:

| Principle | Implication for Constitution |
|-----------|------------------------------|
| **Versioned** | Constitution tracked in git; version SHA embedded in every generated artifact |
| **Modular** | Independently loadable sections with `<LAYER>` tags |
| **Token-optimized** | Every word maximizes semantic value per token consumed |
| **Testable** | Constitution effectiveness measured through output quality metrics |
| **Composable** | Sections can be selectively loaded based on task type |

**Source:** Cursor documentation, Claude Code CLAUDE.md convention, Aider CONVENTIONS.md, Anthropic best practices

### 1.2 The Universal File Format

All major AI coding tools converge on **Markdown** as the base format:
- LLMs were trained extensively on Markdown
- Human-readable and editable
- Supports hierarchical structure via headers
- Supports code blocks for examples
- Accepts YAML frontmatter for metadata
- Can embed XML tags for machine-precise boundaries

The constitution uses Markdown as the outer container with XML-style section tags (`<SECTION_0>`, `<LAYER_1>`, etc.) for machine-precise boundaries within sections.

### 1.3 Structure Over Prose: Quantified

| Format | Token Count | Semantic Density |
|--------|-------------|------------------|
| Narrative prose | 52 tokens | Low (filler words, articles, conjunctions) |
| Telegraphic bullets | 18 tokens | High (65% reduction, 0% information loss) |
| XML-tagged structured data | 18 tokens | Highest (machine-parseable, self-describing) |

**Example:**

```
PROSE: "The Doxee platform is designed to be a comprehensive solution that enables
large enterprises to manage their customer communications across multiple channels
including email, SMS, print, and web while ensuring compliance with various
regulatory requirements such as GDPR."

STRUCTURED: Doxee Platform: Enterprise CCM/CXM. Multi-channel (email, SMS, print,
web). Cloud-native. GDPR-compliant. API-first.
```

---

## 2. Context Window Optimization and the "Lost in the Middle" Problem

### 2.1 The Foundational Research Finding

**Source:** Liu et al., "Lost in the Middle: How Language Models Use Long Contexts" (TACL 2023, arXiv:2307.03172)

> "Performance is often highest when relevant information occurs at the **beginning or end** of the input context, and significantly degrades when models must access relevant information in the **middle** of long contexts."

This U-shaped attention curve has three practical implications for the constitution:

1. **Front-load critical instructions** -- Section 0 (executive kernel) and Section 1 (guardrails) go at the top
2. **Repeat key constraints at the end** -- Section 19 (requirements generation rules) restates critical guardrails
3. **Minimize mid-document noise** -- Layer 2 deep reference goes in the middle where attention is lowest, because it is consulted by explicit reference rather than needing ambient awareness

### 2.2 Anthropic's Long Context Guidance

**Source:** Anthropic prompt engineering documentation

Optimal layout for Claude models:

```
[LONG REFERENCE DOCUMENTS]   <-- Top: bulk data (Layer 2 reference material)
[INSTRUCTIONS]                <-- Middle: rules and constraints (Layer 1 working context)
[SPECIFIC QUERY/TASK]         <-- Bottom: what to do now (Layer 0 kernel + generation rules)
```

However, for a constitution that IS the instruction set (not a reference document + query), the adapted layout is:

```
SECTION 0:  Executive Kernel + Guardrails          <-- FRONT (primacy effect)
SECTIONS 1-9:  Layer 1 Working Context             <-- UPPER-MIDDLE (strategic context)
SECTIONS 10-17: Layer 2 Deep Reference             <-- LOWER-MIDDLE (consulted on demand)
SECTION 18: Examples / Few-Shot Corpus             <-- NEAR-END (pattern learning)
SECTION 19: Requirements Generation Rules          <-- END (recency effect)
```

### 2.3 Anthropic's XML Multi-Document Pattern

For multi-document contexts, Anthropic recommends:

```xml
<documents>
  <document index="1">
    <source>constitution.md</source>
    <document_content>{{CONSTITUTION}}</document_content>
  </document>
</documents>
```

This pattern applies when the constitution references external documents. Within the constitution itself, use XML section tags to achieve the same boundary clarity.

### 2.4 Quote Grounding

For long documents, instruct the model to quote relevant sections first:

> "Ask Claude to quote relevant parts of the documents first before carrying out its task."

The constitution's generation rules (Section 19) should instruct the agent to cite specific constitution sections before generating each requirement.

---

## 3. Progressive Discovery and Layered Loading

### 3.1 The Three-Layer Model

Inspired by OS kernel architecture and validated across all researched frameworks:

| Layer | Token Budget | When Loaded | Contents |
|-------|-------------|-------------|----------|
| **Layer 0: Executive Kernel** | ~2K tokens | Every interaction | Identity, North Star, top personas (1-line), hard guardrails, active bets (names only), glossary |
| **Layer 1: Working Context** | ~10K tokens | Epic/roadmap planning | DIBB chains, product press releases, full personas, competitive matrix, appetite levels, no-go lists, business model |
| **Layer 2: Deep Reference** | ~18K tokens | User story generation | Regulatory specifics, technical constraints, feature inventory, rabbit holes, traceability config, examples |

### 3.2 How Each AI Tool Implements Layered Loading

| Tool | Always Loaded | Conditionally Loaded | On-Demand |
|------|--------------|---------------------|-----------|
| **Claude Code** | `CLAUDE.md` in directory hierarchy | `.claude/rules/*.md` with `paths` frontmatter | Child directory `CLAUDE.md` files; `@path` imports (max 5 hops) |
| **Cursor** | Rules with `alwaysApply: true` | Rules with `globs` patterns or agent-decided via `description` | Rules with `@`-mention only |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `.github/instructions/*.instructions.md` with `applyTo` globs | `AGENTS.md` in subdirectories |
| **Devin** | Knowledge pinned to all repos | Knowledge pinned to specific repo | Trigger-based retrieval by relevance |
| **Windsurf** | `.windsurfrules` + global rules | N/A | Memories (auto-learned facts) |
| **Aider** | `CONVENTIONS.md` via `--read` flag | N/A | N/A |

**Key insight:** The most effective systems load the least amount of context needed for the current task. The constitution must support partial loading via LAYER tags.

### 3.3 Constitution Loading Protocol

```
Task Type: "Generate roadmap epic"
  Load: SECTION 0 (kernel) + SECTIONS 1-9 (Layer 1)
  Skip: SECTIONS 10-17 (Layer 2)
  Load: SECTION 19 (generation rules)

Task Type: "Generate user story with acceptance criteria"
  Load: SECTION 0 (kernel) + SECTIONS 1-9 (Layer 1) + SECTIONS 10-18 (Layer 2)
  Load: SECTION 19 (generation rules)

Task Type: "Quick validation check"
  Load: SECTION 0 (kernel) only
```

### 3.4 The Pyramid of Specificity

```
                    /\
                   /  \
                  / On \          <-- Invoked for specific tasks
                 / Demand\
                /----------\
               /Conditional \     <-- Loaded when file patterns match
              /--------------\
             /   Always On    \   <-- Loaded every session
            /------------------\
```

The constitution maps onto this pyramid: Layer 0 is always on, Layer 1 is conditional on task scope, Layer 2 is on-demand for deep-dive generation.

---

## 4. Information Compaction Techniques

### 4.1 Telegraphic Style Rules

1. Remove articles (the, a, an) where meaning remains clear
2. Use colons and periods instead of conjunctions
3. Prefer noun phrases over full sentences
4. Employ abbreviations after first definition in glossary
5. Use tables and structured data over paragraph explanations

### 4.2 Glossary-First Pattern

Define domain terms once in Section 0, reference everywhere:

```xml
<glossary>
  CCM: Customer Communication Management
  CXM: Customer Experience Management
  Pvideo: Doxee Personalized Video (ix product)
  Pweb: Doxee Personalized Web Microsites (ix product)
  ix: Interactive Experience (product line)
  px: Paperless Experience (product line)
  dx: Document Experience (product line)
  UDS: User-Directed Storytelling
  DT3: Data Transformation v3
</glossary>
```

**Benefits:**
- LLM tokenizes defined terms as distinct semantic units
- Reduces ambiguity (CCM vs. CXM distinction explicit)
- Enables consistent vocabulary across all outputs
- Saves tokens on every subsequent reference

### 4.3 Reference by ID Pattern

```xml
<strategies>
  <strategy id="STRAT-01">Cloud-Native First: All features API-driven. No on-premise-only logic.</strategy>
  <strategy id="STRAT-02">European Sovereignty: Data residency, GDPR, eIDAS mandatory.</strategy>
</strategies>

<!-- In requirements generation: "This requirement follows [STRAT-01]." -->
```

### 4.4 Bullets Over Prose

Every tool's documentation and community converges on this: **bullet points and short declarative statements maximize semantic density per token.**

```
BAD (verbose prose):
When you are writing requirements for this project, you should make sure that you
always target cloud-native deployment, which means using Kubernetes-based orchestration
and ensuring that all services are containerized.

GOOD (compact bullets):
- Target: Cloud-native deployment (Kubernetes)
- All services containerized
- No on-premise-only logic
```

The compact version is ~60% fewer tokens with identical semantic content.

### 4.5 Code Examples Over Descriptions

```
BAD: "The API endpoint should accept a customer ID and return their communication preferences"
GOOD: GET /v2/customers/{id}/preferences -> { channels: [...], frequency: "..." }
```

### 4.6 Reference Rather Than Include

From both Cursor and Claude Code documentation:
> "Reference files rather than copying contents."
> "Link to docs instead of including detailed API documentation."

The constitution should reference external documents (e.g., `@doxee/official-product-documentation/`) rather than inlining their full content.

---

## 5. Structured Delimiters and Prompt-Friendly Conventions

### 5.1 XML Tags for Machine Precision

**Source:** Anthropic prompt engineering documentation

> "XML tags can be a game-changer. They help Claude parse your prompts more accurately, leading to higher-quality outputs."

Benefits for constitution design:
- Clear section boundaries (no ambiguous nesting)
- Programmatic extraction of response parts
- Self-documenting structure
- Works particularly well with Claude models

Best practices:
- Consistent tag names throughout
- Nest tags for hierarchical content
- Reference tags by name in instructions
- Use semantic tag names (not `<section1>` but `<competitive_landscape>`)

### 5.2 Constraint Markers: [HARD] vs [SOFT]

Patterns that work across all LLMs for marking constraint severity:

```markdown
## Guardrails

[HARD] All features MUST support cloud-native deployment. No on-premise-only logic.
[HARD] GDPR Article 17 data erasure compliance is non-negotiable.
[HARD] PDF/UA output for accessibility (EAA mandate).

[SOFT] PREFER functional decomposition over monolithic features.
[SOFT] PREFER OpenAPI 3.0 specs for API contracts.
[SOFT] TARGET 80% automated test coverage.
```

The three-tier permission model (from OpenAI Codex AGENTS.md):
- **MUST / NEVER** -- Non-negotiable hard constraints
- **SHOULD / PREFER** -- Strong preferences, override with documented reason
- **MAY / CONSIDER** -- Optional guidance

### 5.3 Emphasis Mechanisms

From Claude Code documentation:
> "You can tune instructions by adding emphasis (e.g., 'IMPORTANT' or 'YOU MUST') to improve adherence."

For critical rules that must never be violated, use:
- `IMPORTANT:` prefix
- `YOU MUST` phrasing
- ALL CAPS for keywords: `ALWAYS`, `NEVER`, `REQUIRED`

### 5.4 Machine-Readable Table of Contents

The constitution should begin with a structured TOC that enables the agent to understand document layout before reading content:

```xml
<constitution_toc>
  <section id="0" layer="0" tokens="~2000">Executive Kernel</section>
  <section id="1" layer="1" tokens="~800">Product Identity and Portfolio</section>
  <section id="2" layer="1" tokens="~600">Strategic Context (DIBB Chains)</section>
  ...
  <section id="19" layer="0" tokens="~1500">Requirements Generation Rules</section>
</constitution_toc>
```

### 5.5 Imperative vs Declarative Instructions

The hybrid style is most effective:

```markdown
# Architecture (declarative -- context setting)
Doxee Platform is cloud-native, Kubernetes-based, with microservices on Java Spring Boot.

# Constraints (imperative -- hard rules)
[HARD] ALWAYS generate API-first requirements. NEVER propose on-premise-only features.
[HARD] ALWAYS include GDPR compliance consideration for features handling personal data.

# Preferences (imperative with softer language)
[SOFT] PREFER event-driven architecture for real-time features.
[SOFT] PREFER existing DT3 operators over custom data transformation logic.
```

---

## 6. AI Coding Tool Context File Patterns

This section distills the patterns most relevant to constitution design from each major AI coding tool.

### 6.1 Cursor: `.cursor/rules/` Directory

**Source:** Cursor official documentation (cursor.com/docs/context/rules)

Key innovations relevant to constitution:

1. **Application modes via frontmatter:**
   - `alwaysApply: true` -- analogous to Layer 0 (always loaded)
   - `globs: ["src/api/**"]` -- analogous to Layer 2 (loaded for specific contexts)
   - `description: "..."` -- agent decides relevance (intelligent retrieval)

2. **Anti-patterns from Cursor docs:**
   - Do NOT duplicate entire style guides (use references)
   - Do NOT document every command (the agent knows common tools)
   - Do NOT cover rare edge cases (diminishing returns)
   - Do NOT replicate codebase documentation

3. **Recommended limit:** Individual rule files under 500 lines. Split large rules into composable pieces.

4. **Community pattern (600+ examples):** Granular, context-specific instructions outperform broad principles. Technology stack definition is the most common content.

**Design principle:** "Start simple. Add rules only when you notice Agent making the same mistake repeatedly."

### 6.2 Claude Code: CLAUDE.md Hierarchical Memory

**Source:** Anthropic official documentation (code.claude.com/docs/en/memory, code.claude.com/docs/en/best-practices)

The most mature hierarchical memory system:

| Memory Type | Location | Purpose |
|-------------|----------|---------|
| Managed Policy | OS-level paths | Organization-wide IT/DevOps instructions |
| Project Memory | `./CLAUDE.md` or `./.claude/CLAUDE.md` | Team-shared project instructions |
| Project Rules | `./.claude/rules/*.md` | Modular, path-specific rules |
| User Memory | `~/.claude/CLAUDE.md` | Personal preferences (all projects) |
| Local Project Memory | `./CLAUDE.local.md` | Personal project-specific (auto-gitignored) |

**Recursive discovery:** Claude Code reads CLAUDE.md files recursively from CWD to root. Child directory CLAUDE.md files loaded on-demand when Claude works with files in those subtrees.

**Import syntax:** `@path/to/file` resolves relative to importing file. Max recursion depth: 5 hops.

**Critical insight from Anthropic:**
> "If Claude keeps doing something you don't want despite having a rule against it, the file is probably too long and the rule is getting lost."

**Implication for constitution:** The ~30K token budget is a genuine constraint. Every section must earn its inclusion.

### 6.3 Windsurf: AGENTS.md and Memories

**Source:** Windsurf documentation (docs.windsurf.com)

Supports `.windsurfrules` (workspace), global rules, AGENTS.md, and persistent "memories" learned during sessions. The memories feature -- persistent facts automatically learned from interactions -- is relevant to the constitution's correction loop: the agent should learn from rejected requirements.

### 6.4 GitHub Copilot: Custom Instructions

**Source:** GitHub official documentation

Three types of instructions:
1. `.github/copilot-instructions.md` -- repository-wide
2. `.github/instructions/*.instructions.md` -- path-specific with `applyTo` frontmatter
3. `AGENTS.md` -- directory-tree precedence

GitHub provides an official auto-generation prompt. Recommended structure: repository summary, build instructions, project layout, validation steps.

### 6.5 Aider: CONVENTIONS.md

**Source:** Aider official documentation (aider.chat/docs/usage/conventions.html)

The simplest approach: a plain markdown file loaded as read-only context via `--read CONVENTIONS.md`.

**Key insight:** The read-only flag means the file is:
1. Never modified by the AI
2. Eligible for prompt caching (reducing costs)
3. Always loaded before any task

This is directly applicable to the constitution: it should be **read-only** for the agent. The agent generates requirements FROM the constitution but never modifies it.

### 6.6 OpenAI Codex: AGENTS.md

**Source:** OpenAI Codex repository (github.com/openai/codex)

Notable patterns from OpenAI's own AGENTS.md:
1. **Imperative instructions** -- "Always do X", "Never do Y"
2. **Conditional behaviors** -- "if changes were made in common/core, THEN run full suite"
3. **Explicit permission scoping** -- automatic / requires-approval / forbidden
4. **Convention references** -- links to external style guides

This three-tier permission model is directly applicable to constitutional guardrails.

### 6.7 Convergence: The Cross-Tool Standard

**AGENTS.md** is emerging as the closest thing to a cross-tool standard. Devin, Windsurf, Cursor, GitHub Copilot, and OpenAI Codex all support it. Claude Code uses CLAUDE.md but shares the same philosophy. The constitution should be compatible with this emerging standard.

---

## 7. PM Frameworks for Strategic Context Encoding

### 7.1 Spotify DIBB Framework

**Source:** Henrik Kniberg, "Spotify Rhythm" (blog.crisp.se)

DIBB creates a logical cascade from evidence to action:

| Element | Definition | Question Answered |
|---------|-----------|-------------------|
| **Data** | Quantitative or qualitative facts | "What do we observe?" |
| **Insight** | Interpretation derived from data | "What does it mean?" |
| **Belief** | Conviction formed from insight | "What do we think will happen?" |
| **Bet** | Committed initiative based on belief | "What will we do about it?" |

**Application to constitution:** Every AI-generated requirement should be traceable through a DIBB chain. The constitution encodes Data, Insight, and Belief layers so the agent can construct the logical thread from evidence to feature.

```yaml
strategic_context:
  north_star: "metric_name"
  dibb_chains:
    - id: "DIBB-001"
      data: "40% of utility clients request real-time dashboards (Q3 2025)"
      insight: "Shift from batch to continuous customer engagement"
      belief: "Real-time interactivity reduces churn 15% in utilities"
      active_bets:
        - "BET-012: Pweb Real-time Billing (Q1 2026)"
      status: "ACTIVE"
```

**Fractal alignment:** Company-level beliefs cascade to squad-level bets. The constitution encodes the company level; individual feature specs derive squad-level DIBB chains.

### 7.2 Amazon PR/FAQ (Working Backwards)

**Source:** Working Backwards (workingbackwards.com); "Working Backwards" by Bryar & Carr (2021)

The PR/FAQ method requires a hypothetical press release + FAQ before any code is written.

**Press Release structure (1-1.5 pages):**
1. Heading -- product name as customer would understand it
2. Subheading -- target audience + primary benefit
3. Summary paragraph -- overview of key benefits
4. Problem paragraph -- customer pain from their perspective
5. Solution paragraph(s) -- how product addresses the problem
6. Company leader quote -- why the company built this
7. Customer quote -- hypothetical customer describing value
8. Call to action -- how to get started

**FAQ sections:**
- **External FAQ:** How it works, cost, replacements, support, availability, data/privacy
- **Internal FAQ:** TAM, unit economics, competitors, build vs buy, technical risks, regulatory, P&L, hiring

**Application to constitution:** Each product line (Pvideo, Pweb, dx, px) should have a concise PR/FAQ-style statement serving as the north star for all generated features:

```markdown
## Product: Doxee Pvideo

**For** enterprise marketing teams in utilities and telecom
**who** need to reduce churn through personalized engagement,
**Doxee Pvideo** is a real-time personalized video platform
**that** transforms billing data into interactive video experiences.
**Unlike** generic email campaigns or PDF statements,
**Pvideo** delivers 3x higher engagement through data-driven personalization.
```

### 7.3 Shape Up: Appetite Levels and No-Go Lists

**Source:** Basecamp, "Shape Up" (basecamp.com/shapeup)

**Appetite** is the time budget the organization is willing to invest, not an estimate of how long work will take. This inversion prevents scope creep:

| Appetite Level | Time Budget | Spec Depth Required |
|---------------|-------------|---------------------|
| **Micro** | 2 days | Issue title + 1-paragraph description |
| **Small Batch** | 2 weeks | Problem + solution sketch + acceptance criteria |
| **Big Batch** | 6 weeks | Full spec: data model, API contracts, test scenarios |

**No-Go Lists** are explicit exclusions that prevent the agent from generating requirements in forbidden areas:

```yaml
no_gos:
  permanent:
    - "On-premise-only features (everything cloud-first)"
    - "Custom per-client logic in core platform"
    - "Features requiring manual operational intervention at scale"
  current_cycle:
    - "Mobile native app (deferred to H2 2026)"
    - "AI-generated video content (exploring, not committing)"
```

**Rabbit Holes** are identified complexities to flag proactively:

```yaml
rabbit_holes:
  - area: "Real-time rendering at scale"
    risk: "WebSocket management above 10K concurrent"
    mitigation: "CDN edge caching; fallback to async delivery"
  - area: "GDPR data erasure"
    risk: "Cascading deletes across video personalization data"
    mitigation: "Soft-delete with scheduled hard purge"
```

**Fat Marker Sketches** principle: provide enough detail for clarity but avoid premature precision that constrains AI creativity. The constitution should define boundaries, not blueprints.

### 7.4 Notion 4-Stage Product Review

**Source:** Lenny Rachitsky, "How Notion Builds Product" (lennysnewsletter.com)

Notion uses four asynchronous stages rather than rigid templates:

1. **User Problem Statement** -- define what users need and why
2. **Directional Exploration** -- present 3+ approaches with recommendation
3. **Full Solution** -- high-fidelity design with complete scope
4. **Ship Candidate** -- final quality review

**Constitution design principle:** Define stages and quality bars, not rigid templates. The agent should know what quality each stage demands.

### 7.5 Cross-Company Product Spec Convergence (Figma, Stripe, Linear)

Across Notion, Figma, Stripe, and Linear, product specs converge on a common skeleton:

1. **Problem Definition** (who, what pain, supporting data)
2. **Principles / Constraints** (feature-specific decision guardrails, non-goals)
3. **Solution Description** (core approach, flows, edge cases)
4. **Alternatives Rejected** (options considered, reasons for rejection)
5. **Success Criteria** (measurable outcomes)
6. **Open Questions** (unresolved items requiring escalation)

**Linear's contribution:** User stories ("As a user, I want...") are an anti-pattern. Write issues in plain language with clear outcomes. Quote user feedback directly rather than summarizing into story format.

### 7.6 Evidence-Based Reasoning Chains

The DIBB framework combined with PR/FAQ and Shape Up creates a requirement justification chain:

```
DATA (observed fact)
  -> INSIGHT (interpretation)
    -> BELIEF (hypothesis)
      -> BET (commitment)
        -> REQUIREMENT (specific need)
          -> ACCEPTANCE CRITERIA (testable outcome)
```

Every AI-generated requirement should be traceable backward through this chain. The constitution must encode enough of each layer for the agent to construct the justification.

---

## 8. Requirements Traceability and Metadata Schema

### 8.1 Why Traceability Matters for AI-Generated Requirements

1. **Accountability** -- Humans verify that AI-generated requirements are justified
2. **Auditability** -- Regulated industries require evidence of legitimate sources
3. **Debugging** -- When a requirement is incorrect, traceability enables root cause analysis
4. **Iteration** -- Traceability enables feedback loops (update the constitution section that produced a bad requirement)

### 8.2 Standards Foundation

**ISO/IEC/IEEE 29148:2018** -- Requirements engineering standard mandating:
- Unique requirement IDs
- Source attribution
- Rationale documentation
- Priority assignment
- Bidirectional traceability matrices

**OSLC (Open Services for Lifecycle Collaboration)** -- Open standard defining link types:
- `implementedBy`, `validatedBy`, `satisfies`, `trackedBy`, `affectedBy`

These standards inform the metadata schema that Section 19 of the constitution must define.

### 8.3 Required Metadata Schema for AI-Generated Requirements

```yaml
traceability_config:
  required_metadata:
    - requirement_id       # Auto-generated: REQ-{product}-{seq}
    - source_sections      # Array of constitution section paths
    - source_type          # Enum: strategic_belief | regulatory | competitive_parity | user_research
    - persona_id           # Must map to a defined persona
    - dibb_chain_id        # Link to strategic rationale (if applicable)
    - confidence_score     # Float 0.0-1.0
    - constraint_refs      # Array of constraint IDs applied
    - generated_at         # ISO 8601 timestamp
    - constitution_version # Git SHA or version tag

  escalation_rules:
    - condition: "No persona_id mapped"
      action: "BLOCK -- every requirement must serve a defined persona"
    - condition: "confidence_score < 0.7"
      action: "ESCALATE to human PM for review"
    - condition: "source_type == 'regulatory' and no constraint_ref"
      action: "BLOCK -- regulatory requirements must cite specific regulation"
    - condition: "No DIBB chain linkable"
      action: "WARN -- requirement may not align with strategic priorities"
```

### 8.4 Inline Source Attribution Pattern

```markdown
## REQ-PV-042: Video Rendering Performance
<!-- source: constitution.dibb_chains.DIBB-001 -->
<!-- persona: PER:CDO -->
<!-- constraint: TECH-RENDER-LATENCY -->
<!-- confidence: 0.87 -->

Video rendering MUST complete within 30 seconds per minute of output.

**Rationale:** Real-time rendering identified as primary competitive differentiator
(DIBB-001). Enterprise CDOs require demonstrable performance metrics for board
justification.
```

### 8.5 Bidirectional Traceability

**Forward:** Constitution Section -> Requirement -> Design -> Implementation -> Test
**Backward:** Test -> Implementation -> Design -> Requirement -> Constitution Section
**Impact Analysis:** Constitution Change -> Affected requirements -> Implementations needing update

For AI-generated artifacts, backward traceability is most critical -- when a stakeholder questions a generated requirement, the system must produce the chain from evidence to feature.

---

## 9. Doxee Competitive Intelligence for Constitution Encoding

This section synthesizes the competitive landscape research into constitution-ready structures.

### 9.1 Doxee Platform Overview (Constitution-Ready)

```xml
<company_profile>
  <name>Doxee S.p.A.</name>
  <founded>2001</founded>
  <hq>Modena, Italy</hq>
  <stock>Euronext Growth Milan (DOX:IM)</stock>
  <status>Societa Benefit (2021), B Corp Certified (2023)</status>
  <customers>200+ enterprise and public-sector organizations</customers>
  <target_verticals>Telecommunications, Utilities, Finance, Insurance, Healthcare, PA</target_verticals>
  <key_clients>Fastweb, Sky Italia, Wind Tre, Sorgenia, Engie, Enel, Hera, Credit Agricole, BayernLB</key_clients>
  <expansion>DACH region (Infinica GmbH acquisition 2024), Central/Eastern Europe</expansion>
</company_profile>
```

**Product lines:**
- **ix (Interactive Experience):** Pvideo (personalized interactive video + UDS), Pweb (microsites/forms)
- **px (Paperless Experience):** Digital archiving, e-invoicing, certified delivery (PEC/SERC/SERCQ)
- **dx (Document Experience):** End-to-end document composition, production, delivery
- **AI Foundation:** GenAI content creation, template migration, Composer Copilot, engagement scoring

**Technology stack:** Cloud-native, Kubernetes, Java Spring Boot, Angular, BPMN 2.0, REST APIs, W3C open standards (XML, XSLT, XSL-FO)

### 9.2 Three-Tier Feature Classification

The competitive intelligence must be encoded in the constitution to guide the agent's prioritization:

**TABLE STAKES (everyone has / must have):**

| Feature | Status |
|---------|--------|
| Template design (print + digital) | Competitive |
| Batch + on-demand generation | Competitive |
| Omnichannel delivery (email, SMS, print, web) | Competitive |
| REST APIs | Competitive |
| RBAC and audit logging | Competitive |
| GDPR compliance | Competitive |
| Cloud deployment | Competitive |
| Content versioning and approval | Competitive |
| PDF/UA accessibility | Competitive (EAA advantage) |

**DIFFERENTIATORS (unique Doxee advantages):**

| Feature | Advantage | Closest Competitor |
|---------|----------|-------------------|
| Pvideo with User-Directed Storytelling | Only vendor with native interactive video + UDS | Precisely EngageOne Video (less interactive) |
| Pweb (personalized microsites) | No direct equivalent in market | N/A |
| Hyperion sustainability measurement | Only vendor with ISO 14064-2 CO2 tracking | None |
| Italian e-invoicing (20%+ market) | PEC/SERC/SERCQ/AppIO channels | None at this depth |
| European data sovereignty | All-European, GDPR-native platform | Quadient (France-based) closest |
| B Corp + Societa Benefit status | Only B Corp certified CCM vendor | None |
| BPMN 2.0 native process engine | Open standard workflow | OpenText comparable |
| Visual ETL / DT3 (122 operators) | Advanced data transformation | OpenText comparable |

**COMPETITIVE GAPS (must close):**

| Gap | Leading Vendor(s) | Priority |
|-----|------------------|----------|
| Journey mapping & orchestration | Quadient (Inspire Journey, 2+ year lead), Smart Comms (SmartPATH, new) | CRITICAL |
| AI authoring co-pilot (in-editor) | Quadient (production-grade in-editor AI) | HIGH |
| Content rationalization / template reduction | Messagepoint (MARCIE Rationalizer), Quadient (InspireXpress: 50-90%) | HIGH |
| Sentiment analysis | Quadient (in-editor + journey-linked) | MEDIUM |
| BYOAI (bring your own AI model) | Quadient (Azure OpenAI support) | MEDIUM |
| PII detection in authoring | Quadient (native), Messagepoint (sensitive terms) | MEDIUM |
| Automated multilingual translation | Quadient (150+ languages), Messagepoint (MARCIE) | MEDIUM |
| Headless CCM / API-first distribution | Messagepoint (headless APIs for mobile, web, chatbots) | MEDIUM |

### 9.3 Key Competitor Profiles (Constitution Summary)

**Quadient** -- Threat level: HIGH
- QKS AI Maturity: **Most Valuable Pioneer** (Industry Pioneer)
- QKS SPARK Matrix: **Leader** (top position)
- Key strengths: Comprehensive AI, InspireXpress migration (50-90% template reduction), native journey mapping, AnyPrem deployment, BYOAI
- Key weaknesses: Complex pricing, higher TCO, US-headquartered (EU data concerns)
- Doxee response: Attack on simplicity/agility, emphasize European sovereignty, highlight sustainability

**Messagepoint** -- Threat level: MEDIUM
- QKS: **Leader** (SPARK Matrix), **Scaling for Impact** (AI Maturity)
- Key strength: MARCIE engine -- deepest content intelligence in CCM market
- Key weakness: Narrower scope (content-focused, no video, no microsites, no journey orchestration)
- Doxee response: Differentiate via interactive experiences (Pvideo/Pweb), position as full platform

**Smart Communications** -- Threat level: MEDIUM
- QKS: **Leader** (SPARK Matrix), **Scaling for Impact** (AI Maturity)
- Key strength: Cloud-native (AWS), 330M+ pages/hour, SmartPATH journey orchestration (new, via Pendula acquisition)
- Key weakness: Content intelligence not as deep, no video capability
- Doxee response: Compete on interactive engagement, match journey capabilities

**OpenText** -- Threat level: MEDIUM
- QKS: **Leader** (SPARK Matrix), **Scaling for Impact** (AI Maturity)
- Key strength: Broadest enterprise content estate, massive install base
- Key weakness: Complex architecture, legacy migration challenges, AI depth less pervasive
- Doxee response: Compete on agility, cloud-native modernization, time-to-value

**Precisely (EngageOne)** -- Threat level: LOW-MEDIUM
- Key strength: EngageOne Video (competes with Pvideo), chatbot (Converse)
- Key weakness: Module cohesion varies, limited journey orchestration
- Doxee response: Maintain Pvideo differentiation through UDS innovation

### 9.4 Market Context

- **Global CCM Market:** USD 1.8-2.1B (2024), projected USD 3.5-4.5B by 2030, CAGR 11-14%
- **Market shift:** CCM -> CXM -> Agentic Communications Platforms
- **QKS prediction (2025):** By 2026, ~50% of new communication processes include AI-driven content generation. By 2027, first autonomous "communication agents." By 2028, CCM becomes self-optimizing CXM.

### 9.5 Analyst Positioning

| Report | Doxee Position |
|--------|---------------|
| QKS SPARK Matrix CCM Q2 2025 | **Leader** |
| QKS AI Maturity Matrix CCM 2025 | **Scaling for Impact** (target: Industry Pioneer) |
| Aspire IXM Leaderboard 2025 | **Leader** |

**Path from "Scaling for Impact" to "Industry Pioneer":**
1. Deepen AI across entire content lifecycle (not just generation)
2. Articulate 3-5 year AI-orchestrated communication vision
3. Prove enterprise scale with measurable outcomes
4. Connect CCM to customer journey programs with native journey mapping

---

## 10. 20-Section Constitution Blueprint

### 10.1 Design Principles

1. **Every section is citable** -- use section IDs that generated requirements can reference (e.g., `constitution.section_3.persona.CDO`)
2. **Structured data over prose** -- YAML/JSON for programmatic data; prose only for nuanced strategic context
3. **Imperative voice for constraints** -- MUST/NEVER/ALWAYS for [HARD]; SHOULD/PREFER for [SOFT]
4. **Front-load and back-load critical content** -- per "lost in the middle" finding
5. **Version everything** -- constitution version recorded in every generated artifact
6. **Treat as living document** -- correction loop where rejected requirements trigger constitution reviews

### 10.2 Section Layout with Layer Tags

```
SECTION 0  [LAYER 0]  Machine-Readable Header & Executive Kernel (~2K tokens)
  - TOC with section IDs, layer tags, and token estimates
  - Identity (company, role, mission -- 1 paragraph)
  - Glossary (all domain terms defined once)
  - North Star metric
  - Top 3-5 personas (name + 1-line JTBD)
  - Top 5-7 hard guardrails ([HARD] constraints)
  - Active cycle bets (names and IDs only)

SECTION 1  [LAYER 1]  Product Identity & Portfolio (~800 tokens)
  - Product lines: ix, px, dx, AI Foundation
  - Per-product PR/FAQ statement (2-3 sentences each)
  - Platform capabilities summary (table format)

SECTION 2  [LAYER 1]  Strategic Context: DIBB Chains (~1000 tokens)
  - North Star metric (expanded)
  - Active DIBB chains (YAML: data, insight, belief, bet, status)
  - Company-level beliefs (3-5 max)

SECTION 3  [LAYER 1]  User Personas (JTBD) (~1500 tokens)
  - Full persona profiles: role, JTBD (prioritized), pains (severity), gains (impact)
  - 5-7 personas covering: Enterprise Admin, API Developer, End-Customer,
    Compliance Officer, Marketing Manager, IT Operations

SECTION 4  [LAYER 1]  Competitive Landscape (~1200 tokens)
  - Three-tier feature classification (table stakes / differentiators / gaps)
  - Competitor profiles (Quadient, Messagepoint, Smart Comms -- 3-4 lines each)
  - Decision logic for competitive-aware prioritization

SECTION 5  [LAYER 1]  Prioritization Framework (~800 tokens)
  - Multi-dimensional scoring (strategic value, regulatory urgency,
    technical feasibility, customer impact, resource efficiency)
  - Priority mapping: P1 (>=8.0), P2 (>=6.0), P3 (>=4.0)
  - Appetite levels (micro/small_batch/big_batch with spec depth requirements)

SECTION 6  [LAYER 1]  No-Go Lists & Scope Boundaries (~500 tokens)
  - Permanent no-gos
  - Current cycle no-gos
  - Anti-patterns (explicitly forbidden approaches)

SECTION 7  [LAYER 1]  Architecture & Technical Constraints (~800 tokens)
  - Technology stack (cloud-native, Kubernetes, Spring Boot, Angular)
  - Deployment models (SaaS, on-prem, public cloud, hybrid)
  - API design principles (REST, OpenAPI 3.0, versioning)
  - Performance targets (latency, throughput, availability)

SECTION 8  [LAYER 1]  Business Model & Market Segments (~600 tokens)
  - Revenue model (SaaS subscriptions, managed services, professional services)
  - Target verticals (utilities, telco, finance, insurance, healthcare, PA)
  - Pricing implications for feature design
  - Unit economics constraints

SECTION 9  [LAYER 1]  Brand Voice & UX Principles (~400 tokens)
  - Terminology standards (consistent naming for platform components)
  - Communication tone (professional, clear, European)
  - UX principles (accessibility-first, mobile-responsive, self-service)

SECTION 10 [LAYER 2]  Regulatory & Compliance Requirements (~1500 tokens)
  - GDPR specifics (articles 17, 25, 35 most relevant)
  - eIDAS (PEC, SERC, SERCQ channels)
  - EAA / European Accessibility Act (PDF/UA, WCAG 2.1 AA)
  - Italian-specific: AgID/ACN, Conservazione Digitale, Fatturazione Elettronica
  - Per-regulation: what it requires, how it constrains features, compliance checklist

SECTION 11 [LAYER 2]  Existing Feature Inventory (~2000 tokens)
  - DESIGN scope: Data Designer, DT3, Template Designer, Business Designer,
    Video Designer, Process Designer
  - ENGAGEMENT scope: Workplace, Composer, Pweb, Pvideo, Digital Archive
  - INSIGHTS scope: Customer/Process/Channel Insights, Tracking & Reporting
  - INTEGRATION scope: Marketplace Apps (Salesforce, SAP, Dynamics 365), APIs
  - AUTOMATION scope: Process Engine, Omnichannel Engine, Batch/On-Demand Jobs
  - ADMINISTRATION scope: Command Center, Repository, User Manager, Doxee University
  - AI FOUNDATION: Template & Content Generation, Migration, Copilot, Scoring

SECTION 12 [LAYER 2]  Italian Market-Specific Features (~800 tokens)
  - Conservazione Digitale a Norma, Fatturazione Elettronica (20%+ market),
    Portale Fatture, Document Cockpit, Ordine Elettronico, Recapito Certificato,
    Firma Elettronica
  - Relevance: only load for features targeting Italian market

SECTION 13 [LAYER 2]  Rabbit Hole Registry (~600 tokens)
  - Known technical risks with documented mitigations
  - Integration complexity notes
  - Areas where the agent should flag rather than assume

SECTION 14 [LAYER 2]  Success Metrics & KPIs (~500 tokens)
  - Per-persona success metrics
  - Platform-level KPIs (template consolidation %, time-to-market, throughput)
  - Requirements quality metrics (clarity score, feasibility rate, duplication rate)

SECTION 15 [LAYER 2]  Sustainability (Hyperion) (~300 tokens)
  - Hyperion environmental impact measurement (ISO 14064-2 validated)
  - 2024 impact: 56,126 tons avoided CO2, 310,849 trees saved
  - Requirement: all features must consider digital-vs-print environmental impact

SECTION 16 [LAYER 2]  European Sovereignty Context (~400 tokens)
  - Data sovereignty positioning (all-European platform, GDPR-native)
  - Geographic expansion strategy (DACH region, Central/Eastern Europe)
  - Competitive advantage over US-headquartered vendors

SECTION 17 [LAYER 2]  Analyst Recognition & Market Position (~400 tokens)
  - QKS Group, Aspire CCS positions
  - Path to "Industry Pioneer" (AI Maturity Matrix)
  - Key battlegrounds (2025-2027)

SECTION 18 [LAYER 2]  Requirements Examples (Few-Shot Corpus) (~3000 tokens)
  - 6-12 examples spanning variation:
    - Simple CRUD feature (Enterprise Admin)
    - API integration feature (Developer)
    - Compliance feature (Compliance Officer)
    - Interactive experience feature (Marketing Manager)
    - Batch processing enhancement (IT Operations)
    - Accessibility feature (End-Customer)
  - Each example: title, persona, user story, acceptance criteria (Given/When/Then),
    relevant constraints, traceability metadata

SECTION 19 [LAYER 0]  Requirements Generation Rules (~1500 tokens)
  - Output format rules (Gherkin Given/When/Then, INVEST criteria)
  - Required metadata per requirement (traceability schema)
  - Escalation triggers (confidence < 0.7, no persona mapped, regulatory without citation)
  - Guardrail restatement (critical [HARD] constraints repeated for recency effect)
  - Quality gates (existing feature check, competitive classification, persona validation)
  - Example output template
```

### 10.3 Token Budget Summary

| Layer | Sections | Estimated Tokens | % of Budget |
|-------|----------|-----------------|-------------|
| Layer 0 | 0, 19 | ~3,500 | 12% |
| Layer 1 | 1-9 | ~7,600 | 25% |
| Layer 2 | 10-18 | ~9,600 | 32% |
| **Headroom** | -- | ~9,300 | 31% |
| **Total Budget** | -- | **~30,000** | 100% |

The 31% headroom accommodates:
- Doxee-specific data that will expand sections beyond estimates
- Few-shot examples that may need more tokens
- Future constitution growth as the correction loop identifies gaps

---

## 11. Validation Framework

### 11.1 Constitution Effectiveness Metrics

**Quantitative:**
- Requirements clarity score (1-10 from Engineering review)
- Feasibility rate (% implementable without clarification)
- Duplication rate (% reinventing existing features)
- Compliance pass rate (% passing validation gates)
- Token efficiency (semantic value per 1K tokens of constitution)
- Agent confidence distribution (histogram of confidence_score values)
- Escalation rate (% of requirements requiring human intervention)

**Qualitative:**
- Engineering satisfaction with generated requirement quality
- Product team confidence in outputs
- Reduction in clarification rounds
- Terminology consistency across generated artifacts

### 11.2 The Correction Loop

```
Generate Requirement
  -> Agent Self-Review (check against constitution guardrails)
    -> Human Spot-Check (PM reviews sample)
      -> Accept or Reject
        -> If rejected: identify constitution gap
          -> Update constitution section
            -> Re-generate (improved)
```

The constitution is a living document that improves based on empirical feedback. Monthly review:
1. Aggregate quality metrics
2. Identify failure patterns
3. Propose constitution amendments
4. Version and release (semantic versioning)

### 11.3 Agent Readiness Assessment

Following Factory.ai's "Agent Readiness" pattern, evaluate each feature spec for autonomous execution readiness:

1. **Context completeness** -- Does the constitution cover all domain knowledge needed?
2. **Constraint clarity** -- Are guardrails unambiguous?
3. **Persona coverage** -- Is the target user well-defined?
4. **Competitive context** -- Is the feature classified (table stakes / differentiator / gap closure)?
5. **Traceability** -- Can every requirement be traced to a constitution section?
6. **Escalation paths** -- Are confidence thresholds and escalation triggers clear?

---

## References

### Research Reports (Internal)

1. `docs/llm-consumable-context-design-research.md` -- AI-native document architecture, tool comparison, RAG optimization
2. `docs/competitive-landscape-research.md` -- Doxee and competitor analysis, feature matrices, market context
3. `docs/pm-frameworks-constitution-research.md` -- DIBB, PR/FAQ, Shape Up, Notion, traceability standards

### Official Tool Documentation

4. Cursor Rules: cursor.com/docs/context/rules
5. Claude Code Memory: code.claude.com/docs/en/memory
6. Claude Code Best Practices: code.claude.com/docs/en/best-practices
7. GitHub Copilot Custom Instructions: docs.github.com/en/copilot/customizing-copilot
8. Devin Knowledge: docs.devin.ai/onboard-devin/knowledge-onboarding
9. Aider Conventions: aider.chat/docs/usage/conventions.html
10. Anthropic Prompt Engineering (XML Tags): platform.claude.com/docs/en/build-with-claude/prompt-engineering/use-xml-tags
11. Anthropic Long Context Tips: platform.claude.com/docs/en/build-with-claude/prompt-engineering/long-context-tips
12. OpenAI Codex AGENTS.md: github.com/openai/codex/blob/main/AGENTS.md

### Research Papers

13. Liu et al., "Lost in the Middle: How Language Models Use Long Contexts," TACL 2023 (arXiv:2307.03172)

### PM Frameworks and Methods

14. Henrik Kniberg, "Spotify Rhythm" -- DIBB framework (blog.crisp.se)
15. Working Backwards / PR/FAQ -- Amazon method (workingbackwards.com)
16. Basecamp, "Shape Up" (basecamp.com/shapeup)
17. Lenny Rachitsky, "How Notion Builds Product" (lennysnewsletter.com)
18. Linear Method (linear.app/method)
19. Figma Product Spec Template -- Yuhki Yamashita
20. Stripe Product Brief structure

### Standards

21. ISO/IEC/IEEE 29148:2018 -- Requirements Engineering
22. OSLC (Open Services for Lifecycle Collaboration) -- Cross-tool traceability standard

### Industry and Community Sources

23. PatrickJS/awesome-cursorrules (GitHub, 600+ community rules)
24. Harper Reed, "My LLM codegen workflow atm" (harper.blog, February 2025)
25. Anthropic, "Building Effective Agents" (anthropic.com, December 2024)
26. Factory.ai Agent Readiness Framework (factory.ai, 2025)
27. Eugene Yan, Prompting Techniques (eugeneyan.com/writing/prompting/)
28. Simon Willison, Prompt Engineering (simonwillison.net)
29. NN/g Information Chunking and Scent (nngroup.com)

### Analyst Reports

30. QKS Group SPARK Matrix CCM Q2 2025
31. QKS Group AI Maturity Matrix for CCM 2025
32. Aspire IXM Leaderboard 2025
33. Aspire CCS Expert Session December 2025

### Internal Doxee Documents

34. `doxee/Doxee-profile.md`
35. `doxee/Doxee Platform functional architecture and components.md`
36. `doxee/official-product-documentation/` (complete product docs)
37. `doxee/analysts/` (market analysis documents)
38. `doxee-context-research.md`
39. `gemini-constitution-research.md`

---

**Research Compiled by:** Claude Code Research Agent
**Total Sources:** 39 (12 official docs, 1 research paper, 7 PM frameworks, 2 standards, 7 industry sources, 4 analyst reports, 6 internal docs)
**Document Version:** 2.0.0
**Supersedes:** Version 1.0.0 (Phase 1 research only)
**Classification:** Internal Use -- Strategic
