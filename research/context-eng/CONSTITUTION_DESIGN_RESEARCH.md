# AI-Consumable Constitution: Unified Design Research

**Version:** 1.0
**Date:** 2026-02-06
**Synthesized from:** `gemini-research.md` (Gemini), `claude-research.md` (Claude)
**Purpose:** Authoritative reference for building the Doxee Speckit constitution — a machine-optimized context document that enables LLM agents to autonomously generate high-quality product requirements.

---

## Critical Review of Source Material

### What Gemini Got Right

1. **The "Hologram" metaphor for Layer 0.** The idea that an agent seeing only the executive kernel should produce "directionally correct" output (even if shallow) is a powerful design test. If the kernel fails this test, it is too sparse.
2. **Canonical reference IDs** (`[P:Pvideo]`, `[PER:CDO]`). Compact, unambiguous entity aliases that save tokens on every subsequent mention. Gemini introduced this; Claude adopted it.
3. **Feature Parity Matrix with requirement-type classification** (Table Stakes / Differentiation / Neutralization). This three-way split directly guides agent prioritization logic. Gemini's schema is cleaner than Claude's expanded version.
4. **Brevity.** At 175 lines, Gemini is concise. The template in Section 5 is immediately actionable — a PM could fill it in today.

### What Gemini Got Wrong or Missed

1. **No research citations.** Claims about "lost in the middle" and RAG optimization are stated as fact without sources. The document reads as expert opinion, not verifiable research.
2. **Shallow constitution template.** Only 10 sections. Missing: prioritization framework, no-go lists, rabbit holes, traceability schema, few-shot examples, correction loop. A constitution built from this template would underspecify the agent's behavior.
3. **No tooling analysis.** No mention of how Cursor, Claude Code, Copilot, Aider, Windsurf, or Codex implement context files. The constitution must work within these tools' loading mechanisms.
4. **No PM framework depth.** Mentions personas and JTBD in passing but doesn't encode DIBB, PR/FAQ, Shape Up appetite, or any evidence-based reasoning chain. The agent would generate requirements without strategic justification.
5. **No validation framework.** No metrics, no correction loop, no way to measure whether the constitution is working.
6. **Doxee competitive intelligence is surface-level.** Lists competitors by name but doesn't provide the structured gap analysis (with threat levels, response strategies, and analyst positioning) that an agent needs for competitive-aware prioritization.

### What Claude Got Right

1. **Deep research foundation.** 39 cited sources across tool documentation, academic papers, PM frameworks, and industry analysis. Every design decision is traceable to evidence.
2. **"Lost in the Middle" application.** Correctly identifies the U-shaped attention curve (Liu et al., 2023) and designs the document layout to exploit primacy and recency effects — kernel at front, generation rules at back, reference material in the middle.
3. **20-section blueprint with token budgets.** Each section has an estimated token count and layer tag. The 30K token budget is treated as a hard constraint with 31% headroom for growth.
4. **PM framework synthesis.** DIBB chains, PR/FAQ statements, Shape Up appetite levels, and no-go lists are all encoded as constitution-ready structures. The evidence-based reasoning chain (Data → Insight → Belief → Bet → Requirement → Acceptance Criteria) is the strongest contribution.
5. **Traceability schema.** Required metadata per AI-generated requirement (source sections, persona ID, DIBB chain, confidence score, constraint refs, constitution version). This enables auditing and debugging.
6. **Cross-tool analysis.** Maps how 6 major AI coding tools implement layered loading, proving the three-layer model works across platforms.
7. **Competitive intelligence depth.** Three-tier feature classification with specific gaps, threat levels, and response strategies. Directly usable in a constitution.
8. **Validation framework and correction loop.** Defines quantitative metrics and a feedback process for continuous improvement.

### What Claude Got Wrong or Missed

1. **Too long.** At 1,110 lines, the document is itself an example of context bloat. A PM would struggle to extract actionable decisions without reading for 60+ minutes. The research paper is 3-4x longer than necessary for its conclusions.
2. **Redundancy between sections.** The competitive intelligence appears in both Section 9 (research) and Section 10 (blueprint). The layered loading concept is explained three times (Sections 3.1, 3.2, 3.3). Violates its own "define once, reference everywhere" principle.
3. **Over-specified tooling section.** Section 6 catalogs 6 tools in detail, but most of this is reference material that doesn't change the constitution design. The key insight — "all tools converge on Markdown + layered loading" — could be stated in 3 sentences.
4. **Missing practical template.** Despite 20 sections of analysis, Claude never produces a filled-in template excerpt. Gemini's Section 5, though shallow, is more immediately useful because it shows what the final artifact looks like.
5. **Token budget headroom is optimistic.** 31% headroom assumes sections won't expand. In practice, the few-shot corpus alone (Section 18, ~3K tokens estimated) will likely need 5-8K tokens for 6-12 well-formed examples. The budget will be tight.
6. **No discussion of cache-friendliness.** Aider's read-only pattern enables prompt caching (token cost savings on repeated loads). This has real cost implications for a constitution loaded on every agent invocation, but the implication isn't developed.

---

## Unified Principles

The following principles survive critical review of both sources. Each is tagged with its origin.

### 1. Three-Layer Progressive Loading [Both]

The constitution must support partial loading. An agent generating a quick epic summary needs different context than one writing detailed acceptance criteria.

| Layer | Budget | Loaded When | Contents |
|-------|--------|-------------|----------|
| **0: Kernel** | ~2K tokens | Every invocation | Identity, glossary, north star, top personas (1-line), hard guardrails, active bets (names only), generation rules |
| **1: Working** | ~10K tokens | Epic/roadmap scope | Full personas (JTBD), DIBB chains, competitive matrix, appetite levels, no-gos, architecture, business model, brand voice |
| **2: Reference** | ~18K tokens | Story/AC generation | Regulatory detail, feature inventory, Italian market, rabbit holes, KPIs, sustainability, sovereignty, analyst position, few-shot examples |

**Loading protocol:**

| Task | Layers Loaded |
|------|--------------|
| Quick validation / triage | 0 only |
| Epic definition / roadmap | 0 + 1 |
| User story + acceptance criteria | 0 + 1 + 2 |

**Design test (Gemini's "Hologram" test):** If an agent loads only Layer 0, it should produce directionally correct output — right persona, right constraints, right competitive category. If it fails this test, the kernel is too sparse.

### 2. Document Layout Exploits Attention Curve [Claude, citing Liu et al. 2023]

LLMs exhibit U-shaped attention: strongest at the beginning and end of context, weakest in the middle.

```
FRONT  → Section 0: Kernel + Guardrails              (primacy effect)
UPPER  → Sections 1-9: Layer 1 Working Context        (strategic context)
MIDDLE → Sections 10-17: Layer 2 Deep Reference       (consulted by explicit reference)
NEAR-END → Section 18: Few-Shot Examples              (pattern learning)
END    → Section 19: Generation Rules + Guardrail Echo (recency effect)
```

**Key implication:** Hard guardrails appear twice — in Section 0 (front) and restated in Section 19 (end). This is deliberate redundancy, not a violation of DRY.

### 3. Information Compaction [Both]

**Telegraphic style rules:**
1. Remove articles (the, a, an) where meaning survives
2. Colons and semicolons over conjunctions
3. Noun phrases over sentences
4. Tables and YAML over paragraphs
5. Abbreviations after first glossary definition

**Measured impact (Claude):**

| Format | Tokens | Density |
|--------|--------|---------|
| Narrative prose | 52 | Low |
| Telegraphic bullets | 18 | High (65% reduction, 0% info loss) |
| XML-tagged structured data | 18 | Highest (machine-parseable) |

**Canonical reference pattern (Gemini):**

Define entities once in the glossary with a short ID. Reference by ID everywhere else.

```
Glossary: Pvideo = Doxee Personalized Interactive Video (ix product line)
Usage:    "Pvideo rendering MUST complete within 30s/min of output."
```

This saves tokens and prevents ambiguity.

### 4. Structured Delimiters [Both, Claude citing Anthropic docs]

Use XML-style tags for machine-precise section boundaries:

```xml
<section id="competitive_landscape" layer="1">
  ...content...
</section>
```

Use semantic tag names (`<competitive_landscape>`, not `<section_4>`).

**Constraint markers (Claude):**

```
[HARD] MUST / NEVER — non-negotiable. Violation = abort.
[SOFT] SHOULD / PREFER — strong preference. Override with documented reason.
[INFO] MAY / CONSIDER — optional guidance.
```

### 5. Imperative Voice for Constraints, Declarative for Context [Claude]

```markdown
# Context (declarative)
Doxee Platform: Cloud-native, Kubernetes, Java Spring Boot, Angular.

# Constraints (imperative)
[HARD] ALWAYS generate API-first requirements. NEVER propose on-premise-only features.
[HARD] GDPR Article 17 data erasure compliance is non-negotiable.

# Preferences (imperative, softer)
[SOFT] PREFER existing DT3 operators over custom data transformation logic.
```

### 6. Evidence-Based Reasoning Chains [Claude, via DIBB + PR/FAQ + Shape Up]

Every AI-generated requirement must be traceable through a justification chain:

```
DATA (observed fact)
  → INSIGHT (interpretation)
    → BELIEF (hypothesis)
      → BET (commitment)
        → REQUIREMENT (specific need)
          → ACCEPTANCE CRITERIA (testable outcome)
```

The constitution encodes the upper layers (Data, Insight, Belief, Bet). The agent constructs the lower layers (Requirement, AC) from that foundation.

**DIBB chain encoding:**

```yaml
dibb_chains:
  - id: DIBB-001
    data: "40% of utility clients request real-time dashboards (Q3 2025)"
    insight: "Shift from batch to continuous customer engagement"
    belief: "Real-time interactivity reduces churn 15% in utilities"
    active_bets:
      - "BET-012: Pweb Real-time Billing (Q1 2026)"
    status: ACTIVE
```

**PR/FAQ statement per product line:**

```
For [target user] who [need], [product] is a [category] that [key benefit].
Unlike [alternative], [product] [differentiator].
```

### 7. Competitive-Aware Prioritization [Both, Gemini's schema refined by Claude]

Three-tier feature classification:

| Type | Definition | Priority | Innovation |
|------|-----------|----------|------------|
| **Table Stakes** | Competitor has it; must match to sell | High | Low |
| **Differentiation** | No one does it well; build to win | Strategic | High |
| **Neutralization** | Competitor winning deals with this; need "good enough" | Medium | Low |

The agent must classify every generated requirement into one of these tiers and cite the competitive evidence.

### 8. Scope Control: No-Go Lists + Appetite Levels [Claude, via Shape Up]

**No-gos** prevent the agent from generating requirements in forbidden areas:

```yaml
no_gos:
  permanent:
    - "On-premise-only features"
    - "Custom per-client logic in core platform"
  current_cycle:
    - "Mobile native app (deferred H2 2026)"
```

**Appetite levels** control spec depth:

| Level | Budget | Spec Depth |
|-------|--------|-----------|
| Micro | 2 days | Title + 1-paragraph |
| Small Batch | 2 weeks | Problem + solution sketch + AC |
| Big Batch | 6 weeks | Full spec: data model, APIs, tests |

**Rabbit holes** flag known complexity:

```yaml
rabbit_holes:
  - area: "Real-time rendering at scale"
    risk: "WebSocket management above 10K concurrent"
    mitigation: "CDN edge caching; fallback to async"
```

### 9. Traceability Metadata on Every AI Output [Claude, informed by ISO 29148]

Every AI-generated requirement must carry:

```yaml
required_metadata:
  requirement_id: REQ-{product}-{seq}
  source_sections: [constitution section paths]
  source_type: strategic_belief | regulatory | competitive_parity | user_research
  persona_id: PER:{id}
  dibb_chain_id: DIBB-{id} (if applicable)
  confidence_score: 0.0-1.0
  constraint_refs: [constraint IDs applied]
  constitution_version: git SHA or semver
  generated_at: ISO 8601
```

**Escalation rules:**

| Condition | Action |
|-----------|--------|
| No persona mapped | BLOCK |
| Confidence < 0.7 | ESCALATE to human PM |
| Regulatory source without constraint ref | BLOCK |
| No DIBB chain linkable | WARN |

### 10. Constitution is Read-Only + Living [Both, Aider insight from Claude]

**Read-only for agents:** The agent generates FROM the constitution but never modifies it. This enables prompt caching and cost savings.

**Living for humans:** Monthly correction loop:

```
Generate → Self-Review → Human Spot-Check → Accept/Reject
  → If rejected: identify constitution gap → amend → re-generate
```

Track: quality metrics, failure patterns, amendment proposals, semantic versioning.

### 11. Read-Only Enables Prompt Caching [Claude, via Aider]

When the constitution is loaded as read-only context, LLM providers can cache the prompt prefix across invocations. This means:
- First load: full token cost
- Subsequent loads within cache window: reduced cost (typically 90% reduction on cached portion)
- For a ~30K token constitution loaded on every agent invocation, this is a significant cost factor

**Implication:** Treat the constitution as a stable, versioned artifact. Frequent edits invalidate the cache. Batch amendments into monthly releases.

---

## Constitution Blueprint

### Section Layout (20 Sections)

```
SECTION  LAYER  TITLE                                    TOKENS (est.)
──────── ───── ──────────────────────────────────────── ─────────────
  0       0    Machine-Readable Header & Executive Kernel    2,000
  1       1    Product Identity & Portfolio                    800
  2       1    Strategic Context (DIBB Chains)               1,000
  3       1    User Personas (JTBD)                          1,500
  4       1    Competitive Landscape                         1,200
  5       1    Prioritization Framework                        800
  6       1    No-Go Lists & Scope Boundaries                  500
  7       1    Architecture & Technical Constraints             800
  8       1    Business Model & Market Segments                 600
  9       1    Brand Voice & UX Principles                     400
 10       2    Regulatory & Compliance Requirements           1,500
 11       2    Existing Feature Inventory                     2,000
 12       2    Italian Market-Specific Features                 800
 13       2    Rabbit Hole Registry                             600
 14       2    Success Metrics & KPIs                           500
 15       2    Sustainability (Hyperion)                        300
 16       2    European Sovereignty Context                     400
 17       2    Analyst Recognition & Market Position            400
 18       2    Requirements Examples (Few-Shot Corpus)        5,000
 19       0    Requirements Generation Rules                  1,500
                                                          ─────────
                                                    TOTAL   22,600
                                                 HEADROOM    7,400 (25%)
                                                   BUDGET   30,000
```

**Note on Section 18:** Claude estimated 3K tokens for few-shot examples. This is too low. Six well-formed examples with full metadata, acceptance criteria, and rationale will require ~5K tokens minimum. The budget above reflects this correction.

### Section 0: What It Must Contain

The kernel is the most critical section. Both sources agree it must include:

1. **Machine-readable TOC** with section IDs, layer tags, token estimates
2. **Identity** — 1-paragraph company definition (telegraphic)
3. **Glossary** — all domain terms defined once (CCM, CXM, Pvideo, Pweb, ix, px, dx, DT3, PURL, etc.)
4. **North Star metric** — single measurable goal
5. **Top personas** — 3-5, name + 1-line JTBD each
6. **Hard guardrails** — 5-7 [HARD] constraints (NEVER/ALWAYS)
7. **Active bets** — names and IDs only (detail in Section 2)

### Section 19: What It Must Contain

The generation rules close the document and exploit the recency effect:

1. **Output format** — Gherkin Given/When/Then, INVEST criteria
2. **Required metadata** — traceability schema (Section 9 of this research)
3. **Escalation triggers** — confidence < 0.7, no persona, regulatory without citation
4. **Guardrail echo** — critical [HARD] constraints restated from Section 0
5. **Quality gate checklist:**
   - Check existing feature inventory (Section 11) before generating
   - Classify competitively (Table Stakes / Differentiation / Neutralization)
   - Validate persona mapping
   - Verify DIBB chain traceability
6. **Example output** — one complete requirement with all metadata fields

---

## Competitive Intelligence for Constitution

### Three-Tier Feature Classification

**TABLE STAKES (match to sell):**

| Feature | Doxee Status |
|---------|-------------|
| Template design (print + digital) | Competitive |
| Batch + on-demand generation | Competitive |
| Omnichannel delivery (email, SMS, print, web) | Competitive |
| REST APIs | Competitive |
| RBAC and audit logging | Competitive |
| GDPR compliance | Competitive |
| Cloud deployment | Competitive |
| PDF/UA accessibility | Competitive (EAA advantage) |

**DIFFERENTIATORS (build to win):**

| Feature | Advantage | Nearest Competitor |
|---------|----------|-------------------|
| Pvideo + UDS | Only native interactive video + user-directed storytelling | Precisely EngageOne Video (less interactive) |
| Pweb microsites | No direct market equivalent | N/A |
| Hyperion sustainability | Only ISO 14064-2 CO2 tracking in CCM | None |
| Italian e-invoicing | PEC/SERC/SERCQ/AppIO depth (20%+ market) | None at this depth |
| European data sovereignty | All-European, GDPR-native | Quadient (France-based) |
| B Corp + Societa Benefit | Only B Corp certified CCM vendor | None |

**GAPS (must close):**

| Gap | Leading Vendor | Priority |
|-----|---------------|----------|
| Journey mapping & orchestration | Quadient (Inspire Journey, 2+ year lead) | CRITICAL |
| AI authoring co-pilot (in-editor) | Quadient (production-grade) | HIGH |
| Content rationalization | Messagepoint (MARCIE), Quadient (InspireXpress: 50-90%) | HIGH |
| Headless CCM / API-first distribution | Messagepoint (headless APIs) | MEDIUM |
| Sentiment analysis | Quadient (in-editor + journey-linked) | MEDIUM |
| BYOAI (bring your own model) | Quadient (Azure OpenAI) | MEDIUM |
| Automated multilingual translation | Quadient (150+ langs), Messagepoint | MEDIUM |

### Key Competitor Summary

| Vendor | Threat | Key Strength | Key Weakness | Doxee Response |
|--------|--------|-------------|--------------|----------------|
| Quadient | HIGH | Comprehensive AI, journey mapping, AnyPrem | Complex pricing, high TCO, US HQ | Simplicity, European sovereignty, sustainability |
| Messagepoint | MEDIUM | MARCIE content intelligence | Narrow scope (no video, no microsites) | Full-platform positioning, Pvideo/Pweb |
| Smart Comms | MEDIUM | Cloud-native, 330M+ pages/hr, SmartPATH | No video, content intelligence gap | Interactive engagement, match journey capabilities |
| OpenText | MEDIUM | Broadest enterprise estate | Legacy architecture, slow innovation | Cloud-native agility, time-to-value |
| Precisely | LOW-MED | EngageOne Video, chatbot (Converse) | Module cohesion varies | Maintain Pvideo lead via UDS |

### Market Context

- CCM market: USD 1.8-2.1B (2024) → USD 3.5-4.5B by 2030, CAGR 11-14%
- Shift trajectory: CCM → CXM → Agentic Communications Platforms
- QKS forecast: ~50% AI-driven content generation by 2026; autonomous communication agents by 2027
- Doxee position: QKS SPARK Matrix **Leader**, AI Maturity **Scaling for Impact** (target: Industry Pioneer)

---

## Validation Framework

### Constitution Effectiveness Metrics

**Quantitative:**

| Metric | Target |
|--------|--------|
| Requirements clarity score (Engineering review, 1-10) | >= 8 |
| Feasibility rate (% implementable without clarification) | >= 85% |
| Duplication rate (% reinventing existing features) | < 5% |
| Compliance pass rate (% passing validation gates) | >= 95% |
| Agent confidence distribution (median) | >= 0.85 |
| Escalation rate (% requiring human intervention) | < 20% |

**Qualitative:**
- Engineering satisfaction with requirement quality
- Reduction in clarification rounds
- Terminology consistency across artifacts

### Correction Loop

```
Generate → Agent Self-Review → Human Spot-Check → Accept/Reject
                                                       │
                                              If rejected:
                                                       │
                                    Identify constitution gap
                                              │
                                    Amend constitution section
                                              │
                                    Version + release (semver)
                                              │
                                    Re-generate (improved)
```

Monthly review cycle: aggregate metrics → identify failure patterns → propose amendments → release.

### Agent Readiness Checklist

Before deploying the constitution, verify:

1. **Context completeness** — Does the constitution cover all domain knowledge the agent needs?
2. **Constraint clarity** — Are guardrails unambiguous? No room for creative interpretation?
3. **Persona coverage** — Every target user well-defined with JTBD?
4. **Competitive context** — Features classifiable as table stakes / differentiation / gap closure?
5. **Traceability** — Every requirement traceable to a constitution section?
6. **Escalation paths** — Confidence thresholds and triggers clear?
7. **Hologram test** — Layer 0 alone produces directionally correct output?
8. **Cache-friendliness** — Constitution stable enough for prompt caching?

---

## References

### Research Papers

1. Liu et al., "Lost in the Middle: How Language Models Use Long Contexts," TACL 2023 (arXiv:2307.03172)

### Tool Documentation

2. Anthropic Prompt Engineering (XML Tags): platform.claude.com/docs/en/build-with-claude/prompt-engineering/use-xml-tags
3. Anthropic Long Context Tips: platform.claude.com/docs/en/build-with-claude/prompt-engineering/long-context-tips
4. Claude Code Memory: code.claude.com/docs/en/memory
5. Claude Code Best Practices: code.claude.com/docs/en/best-practices
6. Cursor Rules: cursor.com/docs/context/rules
7. GitHub Copilot Custom Instructions: docs.github.com/en/copilot/customizing-copilot
8. Aider Conventions: aider.chat/docs/usage/conventions.html
9. OpenAI Codex AGENTS.md: github.com/openai/codex/blob/main/AGENTS.md
10. Devin Knowledge: docs.devin.ai/onboard-devin/knowledge-onboarding

### PM Frameworks

11. Henrik Kniberg, "Spotify Rhythm" — DIBB framework (blog.crisp.se)
12. Working Backwards / PR/FAQ — Amazon method (workingbackwards.com)
13. Basecamp, "Shape Up" (basecamp.com/shapeup)
14. Lenny Rachitsky, "How Notion Builds Product" (lennysnewsletter.com)
15. Linear Method (linear.app/method)

### Standards

16. ISO/IEC/IEEE 29148:2018 — Requirements Engineering
17. OSLC (Open Services for Lifecycle Collaboration)

### Industry Sources

18. Anthropic, "Building Effective Agents" (anthropic.com, December 2024)
19. Factory.ai Agent Readiness Framework (factory.ai, 2025)
20. PatrickJS/awesome-cursorrules (GitHub, 600+ community rules)

### Analyst Reports

21. QKS Group SPARK Matrix CCM Q2 2025
22. QKS Group AI Maturity Matrix for CCM 2025
23. Aspire IXM Leaderboard 2025
24. Aspire CCS Expert Session December 2025
