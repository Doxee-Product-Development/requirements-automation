# Product Management Frameworks for AI-Driven Constitution Design
## Research Report: Structural Patterns for Agent-Consumable Product Context

**Prepared for:** Doxee Speckit Requirements Automation Framework
**Date:** February 6, 2026
**Purpose:** Identify concrete structural patterns from established PM frameworks that can be adapted for an AI-consumable company constitution document
**Research Method:** Web research, Henrik Kniberg's Spotify writings, Basecamp Shape Up documentation, Amazon Working Backwards resources, Linear Method documentation, Notion product development process analysis, and cross-framework synthesis

---

## Table of Contents

1. [Spotify DIBB Framework](#1-spotify-dibb-framework)
2. [Notion Product Briefs and Modern Tech Product Spec Patterns](#2-notion-product-briefs-and-modern-tech-product-spec-patterns)
3. [Amazon PR/FAQ / Working Backwards](#3-amazon-prfaq--working-backwards)
4. [Emerging AI-Native Product Ops Frameworks (2024-2025)](#4-emerging-ai-native-product-ops-frameworks-2024-2025)
5. [Shape Up (Basecamp) -- Deep Dive](#5-shape-up-basecamp----deep-dive)
6. [Requirements Generation Traceability](#6-requirements-generation-traceability)
7. [Cross-Framework Synthesis: Constitution Design Patterns](#7-cross-framework-synthesis-constitution-design-patterns)
8. [Actionable Recommendations for Speckit Constitution](#8-actionable-recommendations-for-speckit-constitution)

---

## 1. Spotify DIBB Framework

### 1.1 What is DIBB?

DIBB is Spotify's strategic decision-making framework that creates a logical cascade from raw evidence to committed action. Introduced as part of Spotify's "Rhythm" system by Henrik Kniberg, it structures how the company moves from observation to investment.

**The four elements:**

| Element | Definition | Question Answered |
|---------|-----------|-------------------|
| **Data** | Quantitative or qualitative facts gathered from the real world | "What do we observe?" |
| **Insight** | The interpretation or understanding derived from analyzing that data | "What does it mean?" |
| **Belief** | The conviction or hypothesis formed from the insight | "What do we think will happen?" |
| **Bet** | The committed initiative or investment based on the belief | "What will we do about it?" |

### 1.2 How the Cascade Works

The DIBB cascade enforces intellectual rigor by requiring each element to flow from the previous one. No bet is made without a traceable chain of reasoning:

```
DATA: 40% of enterprise utility clients request real-time billing dashboards
  |
  v
INSIGHT: Enterprises are shifting from monthly batch billing to continuous engagement
  |
  v
BELIEF: Providing real-time interactive billing will reduce churn by 15% in the utility vertical
  |
  v
BET: Build Pweb real-time billing dashboard (6-week cycle, 2 engineers)
```

**Key properties of the cascade:**
- **Multiple Insights from one Data point:** A single dataset can produce different interpretations
- **Multiple Beliefs from one Insight:** Teams may disagree on implications
- **One Bet per Belief (at a time):** Forces prioritization -- you bet on the belief you have highest confidence in
- **Bets are stack-ranked:** Spotify uses company-level beliefs and a North Star goal to rank bets on a kanban board (Now / Next / Later)

### 1.3 Connection to Company-Level Alignment

At Spotify, DIBB operates within a broader rhythm:

1. **North Star Goal:** A single company-wide metric (e.g., "grow monthly active users")
2. **Company Beliefs:** 3-5 high-level beliefs derived from strategic data (e.g., "personalized discovery drives retention")
3. **Company Bets:** Major initiatives stack-ranked against beliefs
4. **Squad Bets:** Individual teams translate company bets into their own DIBB chains

This creates a **fractal alignment model** -- every squad's work can be traced back through its DIBB chain to the company North Star.

### 1.4 Mapping DIBB to AI Constitution Sections

| DIBB Element | Constitution Section | Purpose for AI Agent |
|-------------|---------------------|---------------------|
| **Data** | Market Context, Analytics, Customer Research | Raw evidence the agent can reference when justifying requirements |
| **Insight** | Strategic Analysis, Competitive Position | Interpreted patterns the agent uses to understand "why" |
| **Belief** | Strategic Hypotheses, Product Principles | Convictions that guide prioritization decisions |
| **Bet** | Current Initiatives, Roadmap Commitments | Active investments that constrain what gets built |

**Constitution design principle from DIBB:** Every requirement the AI generates should be traceable through a DIBB chain. The constitution should explicitly encode the Data, Insight, and Belief layers so the agent can construct the logical thread from evidence to feature.

### 1.5 Structural Pattern for Constitution

```yaml
strategic_context:
  north_star: "metric_name"
  dibb_chains:
    - id: "DIBB-001"
      data: "40% of utility clients request real-time dashboards (Q3 2025 survey)"
      insight: "Shift from batch to continuous customer engagement"
      belief: "Real-time interactivity reduces churn 15% in utilities"
      active_bets:
        - "BET-012: Pweb Real-time Billing (Q1 2026)"
      status: "ACTIVE"
    - id: "DIBB-002"
      data: "Quadient launched cloud orchestration in Q2 2025"
      insight: "CCM market moving to cloud-native orchestration as table stakes"
      belief: "Failing to match Quadient's orchestration will lose 3 enterprise deals/quarter"
      active_bets:
        - "BET-015: Workflow Orchestration Parity (Q2 2026)"
      status: "ACTIVE"
```

**Why this matters for AI:** When the agent generates a requirement, it can reference a specific DIBB chain ID, providing automatic traceability from requirement to strategic rationale.

---

## 2. Notion Product Briefs and Modern Tech Product Spec Patterns

### 2.1 Notion's Product Development Process

Based on Lenny Rachitsky's analysis of Notion's internal process, Notion uses a **four-stage asynchronous check-in model** rather than rigid document templates:

| Stage | Name | Purpose | Format |
|-------|------|---------|--------|
| 1 | **User Problem Statement** | Define what users need and why it matters | Written doc (async via email) |
| 2 | **Directional Exploration** | Present 3+ possible approaches with a recommended direction | Synchronous Figma session (~30 min) |
| 3 | **Full Solution** | High-fidelity design with complete scope definition | Written doc with Figma links |
| 4 | **Ship Candidate** | Final quality review before launch | Live review |

**Key characteristics:**
- **Predominantly asynchronous** -- most review happens via written documents in email
- **Synchronous only for design trade-offs** -- recognizing that visual/directional discussions need real-time conversation
- **No mandated company-wide templates** -- teams have autonomy in how they execute within the four-stage structure
- **Twice-yearly planning cycles** with two-week sprints aligned organization-wide

### 2.2 The Notion Philosophy: Structure Over Templates

Notion intentionally avoids prescriptive templates. Instead, they enforce:
1. **Strategic alignment** -- all work ties to company goals
2. **Cross-functional coordination** -- engineering, design, data, research, and security sit under one leader
3. **Variable sprint implementation** -- some teams track commitments rigorously; infrastructure teams treat sprints as time units only

**Constitution design principle from Notion:** The constitution should define the **stages and checkpoints** for requirement generation, not rigid templates. An AI agent should know what quality bar each stage demands, not what exact fields to fill.

### 2.3 Figma Product Spec Template (Yuhki Yamashita)

Figma's VP of Product, Yuhki Yamashita, popularized a product spec template that has become widely adopted across the industry. The core sections are:

| Section | Purpose | Key Content |
|---------|---------|-------------|
| **Problem** | Why are we doing this? | User pain, data supporting the problem, who is affected |
| **Principles** | What guides our decisions? | 3-5 design/product principles for this specific feature |
| **Solution** | What are we building? | Detailed solution with mockups, flows, edge cases |
| **Non-Goals** | What are we NOT building? | Explicit scope exclusions to prevent scope creep |
| **Milestones** | How do we break this down? | Phased delivery plan with clear ship dates |
| **Open Questions** | What do we still not know? | Unresolved items requiring investigation |

**Key innovation:** The "Principles" section is feature-specific, not company-wide. It forces teams to articulate the trade-off philosophy for each project (e.g., "Prefer simplicity over completeness" or "Optimize for power users").

### 2.4 Stripe Product Brief Structure

Stripe's approach to product briefs emphasizes **rigor in problem definition** before solution exploration:

1. **Context** -- Background, market situation, related prior work
2. **Problem Statement** -- Precise definition of the user problem (who, what, impact)
3. **Proposed Solution** -- Technical approach with architecture considerations
4. **Alternatives Considered** -- What else was evaluated and why it was rejected
5. **Metrics** -- How success will be measured
6. **Risks and Mitigations** -- What could go wrong and contingency plans
7. **Dependencies** -- External systems, teams, or timelines that constrain delivery
8. **Timeline** -- Phased plan with milestones

### 2.5 Cross-Company Pattern Synthesis

Across Notion, Figma, Stripe, and other leading companies, product specs converge on a common structural skeleton:

```
1. PROBLEM DEFINITION (Why)
   - Who is affected
   - What pain they experience
   - Data supporting the problem's importance

2. PRINCIPLES / CONSTRAINTS (Guardrails)
   - Feature-specific decision principles
   - Explicit non-goals and scope boundaries

3. SOLUTION DESCRIPTION (What)
   - Core approach
   - Key interactions / flows
   - Edge cases considered

4. ALTERNATIVES REJECTED (What else)
   - Options considered
   - Reasons for rejection

5. SUCCESS CRITERIA (How we know)
   - Measurable outcomes
   - Leading and lagging indicators

6. OPEN QUESTIONS (What we don't know)
   - Unresolved items
   - Required investigations
```

### 2.6 Mapping to AI Constitution

The product spec pattern suggests the AI constitution should contain:
- **Persona-Problem pairings** (structured like Notion's Stage 1) so the agent always starts from a user need
- **Feature-level principles** as override layers on top of company principles (like Figma's Principles section)
- **Explicit non-goals** at both company and product levels (preventing the agent from generating requirements in forbidden areas)
- **Open questions registry** -- a living list of unresolved strategic questions that should trigger escalation rather than autonomous generation

---

## 3. Amazon PR/FAQ / Working Backwards

### 3.1 Overview and Origin

Amazon's "Working Backwards" method, formalized under Jeff Bezos, requires teams to write a hypothetical press release and FAQ document **before any code is written**. The core insight: if you cannot write a compelling press release for the customer, the product is not worth building.

Key rules:
- **No PowerPoint** -- Amazon banned slide decks in favor of narrative 6-page memos
- **Narrative format** -- forces clear thinking (you cannot hide behind bullet points)
- **Customer-first framing** -- the press release is written from the customer's perspective
- **Iterative refinement** -- PR/FAQs go through multiple drafts until the narrative is crisp

### 3.2 Press Release Structure (Detailed)

The press release section is a 1-1.5 page document with the following components:

| Component | Length | Purpose | Content |
|-----------|--------|---------|---------|
| **Heading** | 1 line | Product identification | Product name in a way the customer would understand |
| **Subheading** | 1 line | Target audience + benefit | Who the product is for and the primary benefit they receive |
| **Summary Paragraph** | 3-4 sentences | Overview | City, date, and a summary of the product's key benefits |
| **Problem Paragraph** | 3-5 sentences | Customer pain | Describes the problem from the customer's perspective; must demonstrate sufficient market demand |
| **Solution Paragraph(s)** | 5-8 sentences | How it works | Details how the product addresses the problem; acknowledges existing alternatives and explains differentiation |
| **Company Leader Quote** | 2-3 sentences | Internal endorsement | Why the company built this, framed as commitment to the customer |
| **Customer Quote** | 2-3 sentences | External validation | Hypothetical customer describing how the product solved their problem |
| **Call to Action** | 1-2 sentences | Next step | How the customer can get started |

**Critical constraints:**
- The product must be "better, cheaper, or faster" than alternatives
- No "laundry list of features" -- focus on the primary customer benefit
- "Great products are tailored to the specific needs of a specific customer segment"

### 3.3 FAQ Section Structure

The FAQ section is divided into two distinct parts:

**External FAQ (Customer/Press-Facing):**
- How does the product work?
- What does it cost?
- What existing solutions does it replace or complement?
- How do customers get support?
- When and where is it available?
- What data/privacy considerations apply?

**Internal FAQ (Stakeholder-Facing):**
- What is the total addressable market (TAM)?
- What are unit economics (cost to serve, margin)?
- What competing solutions exist and how do we differentiate?
- What capabilities do we need to build vs. buy?
- What are the major technical risks?
- What regulatory or legal concerns exist?
- What is the projected P&L for years 1-3?
- What is the hiring plan required?

### 3.4 The 6-Page Narrative Memo

Beyond the PR/FAQ, Amazon uses 6-page narrative memos for major decisions:
- **First 20 minutes of meetings are silent reading** of the memo
- Forces the author to think rigorously -- prose writing exposes logical gaps that bullet points hide
- No skipping ahead -- everyone reads the same document
- Questions and discussion follow the reading period

### 3.5 Mapping PR/FAQ to AI Constitution Sections

| PR/FAQ Component | Constitution Mapping | AI Agent Usage |
|-----------------|---------------------|----------------|
| **Press Release Heading/Sub** | Product Identity, Value Proposition | Agent uses as the "elevator pitch" constraint for all generated user stories |
| **Problem Paragraph** | Persona Pain Points, Market Context | Agent checks generated requirements against documented customer pains |
| **Solution Paragraphs** | Product Capabilities, Differentiation Strategy | Agent ensures requirements align with documented solution approach |
| **Customer Quote** | Success Narratives, Desired Outcomes | Agent generates acceptance criteria that would make the hypothetical customer's statement true |
| **External FAQ** | User-Facing Requirements, Pricing Model, Data/Privacy | Agent generates functional requirements, pricing-related constraints |
| **Internal FAQ** | Business Model, TAM, Unit Economics, Technical Constraints | Agent generates non-functional requirements, architectural constraints, compliance rules |

**Constitution design principle from PR/FAQ:** The constitution should contain a concise "press release" for each major product line -- a 1-paragraph statement of who the customer is, what problem it solves, and how. This gives the AI agent a north star for every feature it generates within that product.

### 3.6 Structural Pattern for Constitution

```markdown
## Product: Doxee Pvideo

### Press Release (Internal Reference)
**For** enterprise marketing teams in utilities and telecom
**who** need to reduce customer churn through personalized engagement,
**Doxee Pvideo** is a real-time personalized video generation platform
**that** transforms static billing data into interactive video experiences.
**Unlike** generic email campaigns or PDF statements,
**Pvideo** delivers 3x higher engagement through data-driven personalization
where every frame is unique to the individual customer.

### Customer Pain (External FAQ)
- "I send 2M bills/month but only 3% of customers read them"
- "My churn rate is 12% and marketing campaigns don't move the needle"
- "I need to prove ROI to the board within 6 months"

### Business Constraints (Internal FAQ)
- TAM: EUR 450M European utility CCM market
- Unit economics: EUR 0.003 per rendered video minute
- Margin target: 70% gross margin on SaaS subscription
- Build vs buy: All rendering is proprietary (competitive moat)
- Regulatory: GDPR Art 17 data erasure applies to all stored customer data
```

---

## 4. Emerging AI-Native Product Ops Frameworks (2024-2025)

### 4.1 The AI-Native PM Landscape

The period from 2024-2025 has seen a rapid emergence of AI-integrated product management practices across several dimensions:

#### Tool-Level AI Integration

| Tool | AI Features (2024-2025) | PM Impact |
|------|------------------------|-----------|
| **Linear** | Auto-triage issues, suggest priorities, generate project updates, AI-powered search across issues | Reduces PM triage time; surfaces patterns in bug reports |
| **Productboard** | AI-generated feature summaries, insight clustering, automated prioritization scoring, customer feedback synthesis | Scales feedback processing from hundreds to thousands of inputs |
| **Jira (Atlassian Intelligence)** | Natural language to JQL queries, AI-suggested story points, automated sprint summaries, smart issue linking | Reduces Jira administration burden; faster reporting |
| **Notion AI** | AI-assisted doc writing, meeting summary generation, database property auto-fill, Q&A over workspace | Knowledge retrieval and synthesis across product documentation |
| **GitHub Copilot Workspace** | Spec-to-implementation planning, task decomposition from issues, code generation from descriptions | Bridges PM specs to engineering execution |
| **Cursor / Claude Code** | Full-context codebase understanding, spec-driven implementation, autonomous task execution | Executes against structured specifications |

#### Key Pattern: "Context as Code"

The most significant emerging practice is treating product context like source code:
- **Version-controlled** -- product context documents live in git alongside code
- **Machine-readable** -- structured formats (YAML, JSON, Markdown with semantic headers) replace prose-heavy documents
- **Testable** -- specifications include machine-executable validation criteria
- **Composable** -- context is modular and can be loaded selectively based on task needs

### 4.2 Agentic Product Management Practices

The concept of "agentic PM" describes a workflow where AI agents perform PM tasks semi-autonomously:

**Level 1: AI-Assisted PM (2023-2024)**
- AI helps write specs, summarize feedback, draft user stories
- Human PM reviews and edits all outputs
- Tools: Notion AI, ChatGPT, Copilot

**Level 2: AI-Augmented PM (2024-2025)**
- AI generates first drafts of complete specifications from natural language descriptions
- AI performs consistency checks across documents
- AI suggests prioritization based on strategic context
- Human PM approves, rejects, or redirects
- Tools: Speckit, GitHub Copilot Workspace, Cursor Agent Mode

**Level 3: Agentic PM (2025-2026, emerging)**
- AI agents autonomously generate requirements, validate them against a constitution, and produce implementation-ready artifacts
- Human PM operates as "orchestrator" -- setting context, reviewing outputs, making strategic decisions
- AI agents escalate only when confidence is below threshold
- Tools: Multi-agent systems, Speckit (target state), Devin

### 4.3 Frameworks for AI-Driven Product Development

#### The "Context Package" Pattern
Teams structure their product context into modular packages that agents can consume:

```
context/
  company/
    constitution.md       # Company-level principles and guardrails
    personas.yaml         # Machine-readable persona definitions
    competitive.yaml      # Feature parity matrix
  product/
    pvideo/
      press-release.md    # PR/FAQ for this product line
      constraints.yaml    # Technical and business constraints
      feature-inventory/  # Existing features (prevents duplication)
  current-cycle/
    active-bets.yaml      # What we're betting on this cycle
    non-goals.md          # What we're explicitly not doing
```

#### The "Agent-Ready Definition of Ready"
An emerging checklist for whether a specification is ready for autonomous agent execution:

1. **Visual Target:** Screenshot, mockup, or design system component reference
2. **Technical Toolset:** Specified API endpoints, libraries, components to use
3. **Machine-Executable Tests:** Gherkin scenarios or similar executable validation
4. **Context References:** Links to relevant constitution sections, prior art, constraints
5. **Confidence Score:** PM's assessment of specification completeness (0-100)
6. **Escalation Triggers:** Conditions under which the agent should stop and ask a human

#### The "Correction Loop" Pattern
Rather than trying to get specifications perfect upfront, AI-native teams implement a feedback cycle:

```
Generate Spec → Agent Self-Review → Human Spot-Check → Implement →
  Measure Outcomes → Update Constitution → Generate Next Spec (improved)
```

The constitution is treated as a **living document** that improves based on empirical feedback from generated requirements.

### 4.4 AI Product Ops vs Traditional Product Ops

| Dimension | Traditional Product Ops | AI Product Ops |
|-----------|------------------------|----------------|
| **Core Function** | Process optimization, tool administration, reporting | Context curation, agent performance monitoring, prompt maintenance |
| **Key Metric** | Velocity, cycle time, feature throughput | Spec quality score, agent confidence, human escalation rate |
| **Daily Work** | Updating dashboards, facilitating ceremonies, managing tooling | Monitoring agent outputs, updating knowledge base, tuning retrieval |
| **Skill Set** | Project management, data analysis, tooling | Prompt engineering, RAG optimization, LLM evaluation |
| **Success Criteria** | Smooth process execution | High-quality autonomous artifact generation |

### 4.5 Linear Method: Issues Over User Stories

Linear's methodology represents an important philosophical shift relevant to AI constitution design:

**Core argument:** User stories ("As a user, I want...") are an anti-pattern. Instead:
- Write issues in **plain language** with clear, defined outcomes
- People doing the work should write the issues, not separate stakeholders
- Descriptions are **optional** -- provide only necessary context
- **Quote user feedback directly** rather than summarizing into user story format
- Focus on **product-level thinking** during planning, then delegate execution

**Constitution design principle from Linear:** The constitution should define product-level intent and context, not prescribe issue-level formatting. The AI agent should understand the "why" deeply enough to write issues in whatever format the team prefers.

---

## 5. Shape Up (Basecamp) -- Deep Dive

### 5.1 Overview

Shape Up is Basecamp's project management methodology built around **fixed time with variable scope**. Work is organized in six-week cycles with two-week cool-down periods. The methodology emphasizes that scope should flex to fit the time box, rather than time extending to accommodate scope.

### 5.2 The Pitch Document Structure

A pitch is the formal proposal for work to be considered at the betting table. It contains five essential ingredients:

#### Ingredient 1: Problem

The problem definition must be:
- **Specific:** Tied to a real use case or customer scenario, not abstract
- **Grounded:** Based on observed behavior, support requests, or data
- **Bounded:** Scoped enough that the team can see a path to resolution

Example: "Customers creating recurring invoices must manually duplicate each field every month, leading to errors and a 23% support ticket rate for billing corrections."

#### Ingredient 2: Appetite

Appetite is the **time budget** the team is willing to invest, not an estimate of how long the work will take. This inversion is fundamental:

| Concept | Traditional Estimation | Shape Up Appetite |
|---------|----------------------|-------------------|
| **Question asked** | "How long will this take?" | "How much time is this worth?" |
| **Variable** | Time (adjusts to scope) | Scope (adjusts to time) |
| **Effect** | Scope creep, deadline pressure | Forced trade-offs, creative constraints |
| **Sizes** | Story points, t-shirt sizes | Small Batch (2 weeks) or Big Batch (6 weeks) |

"Stating the appetite and embracing it as a constraint turns everyone into a partner in that process."

**Appetite as prioritization:** If a problem is real but the appetite is only 2 weeks, the team must find a 2-week solution. If no 2-week solution exists, the project either waits for a cycle where 6 weeks is justified, or the problem is re-framed to a solvable scope.

#### Ingredient 3: Solution

The solution is presented as **concrete design elements** sufficient for the team to understand the approach without constraining implementation details. Key tools:

**Fat Marker Sketches:**
- Drawn with intentionally thick lines (as if using a fat marker on a whiteboard)
- Show **affordances** (what a UI element does) and **connections** (how elements relate)
- Deliberately omit visual details like colors, fonts, exact spacing
- Leave designers freedom to refine aesthetics during implementation
- May be redrawn more neatly on iPad using different colors to separate labels from content

**Breadboarding:**
- Text-based description of flows showing places (screens), affordances (buttons/fields), and connection lines (navigation)
- No visual design at all -- pure interaction architecture
- Example:
  ```
  Invoice List --> [New Recurring] --> Recurring Setup
    - Frequency dropdown
    - Template selector
    - [Preview] --> Preview Screen
    - [Save] --> Confirmation
  ```

**Why rough is better:** "If the idea is too specific early on, the team won't have room to make trade-offs and adjustments when real complexity emerges during implementation."

#### Ingredient 4: Rabbit Holes

Rabbit holes are **identified complexities** that could consume disproportionate time if not addressed in the pitch. The shaper calls them out proactively:

- Technical challenges with proposed mitigations
- Design decisions that could spiral into bike-shedding
- Integration points with unpredictable behavior
- "We decided to use X instead of Y because Y would require Z, which blows the appetite"

#### Ingredient 5: No-Gos

Explicit statements about what is **intentionally excluded** from the project scope:

- Features that are related but not essential
- Quality levels that are not required (e.g., "no WYSIWYG editing -- plain markdown is sufficient")
- Platforms or environments not targeted
- Perfection that can wait for a future cycle

### 5.3 The Betting Table

The betting table is a **decision meeting** held during the cool-down period between cycles.

**Participants:** At Basecamp, the CEO (Jason Fried), CTO (David Heinemeier Hansson), a senior programmer, and a product strategist. "The highest people in the company are there. There's no 'step two' to validate the plan or get approval."

**Process:**
1. Pitches are shared before the meeting for pre-reading
2. Participants establish context through brief conversations
3. Decisions are made based on available capacity, business priorities, and appetite
4. Meeting lasts 1-2 hours
5. Output: a concrete cycle plan -- which pitches are "bet on" and which teams are assigned

**No backlogs:** Shape Up explicitly rejects backlogs. If a pitch is not bet on, it is not carried forward. If the problem is still important next cycle, someone can re-pitch it (possibly reshaped with new context).

### 5.4 The Circuit Breaker

The circuit breaker is a **risk management policy**: if a project does not ship within its allocated cycle (2 or 6 weeks), it does **not** automatically receive an extension.

- Prevents runaway projects
- Forces teams to make tough scope decisions early
- If a project fails to ship, the team does a retrospective but the work is not automatically continued
- The problem can be re-pitched at the next betting table, but the solution may need reshaping

### 5.5 Hill Charts

Hill charts visualize progress along two phases:

```
    /\
   /  \
  /    \
 /      \
/ Uphill \ Downhill \
  (figuring    (getting
   it out)      it done)
```

- **Uphill:** Uncertainty, unknowns, problem-solving. The team is exploring approaches and validating solutions.
- **Downhill:** Certainty, confidence, execution. All major unknowns are resolved and work is predictable.

Each scope (sub-project) is represented as a dot on the hill. Managers track movement of dots over time:
- **Moving dot:** Healthy progress
- **Stagnant dot:** Potential problem requiring attention (serves as an automatic "raised hand")
- **Dot retreating uphill:** Scope was larger or more complex than anticipated

### 5.6 Mapping Shape Up to AI Constitution Design

| Shape Up Concept | Constitution Mapping | Agent Usage |
|-----------------|---------------------|-------------|
| **Appetite** | Token/time budgets per requirement type | Agent constrains solution complexity to match declared investment level |
| **Fat Marker Sketches** | Abstract solution patterns, not detailed designs | Agent generates at appropriate abstraction level -- not too specific |
| **Rabbit Holes** | Known technical risks, integration complexity notes | Agent flags when generated requirements touch documented rabbit holes |
| **No-Gos** | Company-level and product-level exclusion lists | Agent checks generated requirements against no-go list before output |
| **Circuit Breaker** | Confidence thresholds, escalation triggers | Agent stops and escalates rather than continuing on uncertain ground |
| **Hill Charts (Uphill/Downhill)** | Requirement maturity levels | Agent tags requirements with maturity: "exploring" vs "defined" vs "ready" |

**Constitution design principle from Shape Up:** The constitution should include explicit **appetite levels** for different categories of work and **no-go boundaries** that act as hard constraints. This prevents the agent from generating elaborate requirements for problems the organization has decided are only worth a small investment.

### 5.7 Structural Pattern for Constitution

```yaml
appetite_levels:
  - level: "micro"
    time_budget: "2 days"
    description: "Bug fixes, minor UX improvements"
    spec_depth: "Issue title + 1-paragraph description"
  - level: "small_batch"
    time_budget: "2 weeks"
    description: "Small features, workflow improvements"
    spec_depth: "Problem + solution sketch + acceptance criteria"
  - level: "big_batch"
    time_budget: "6 weeks"
    description: "Major features, new capabilities"
    spec_depth: "Full spec with data model, API contracts, test scenarios"

no_gos:
  permanent:
    - "On-premise-only features (everything must be cloud-first)"
    - "Custom per-client logic in the core platform"
    - "Features requiring manual operational intervention at scale"
  current_cycle:
    - "Mobile native app (deferred to H2 2026)"
    - "AI-generated video content (exploring, not committing)"

rabbit_holes:
  - area: "Real-time rendering at scale"
    risk: "WebSocket connection management above 10K concurrent"
    mitigation: "Use CDN edge caching; fallback to async delivery"
  - area: "GDPR data erasure"
    risk: "Cascading deletes across video personalization data"
    mitigation: "Implement soft-delete with scheduled hard purge"
```

---

## 6. Requirements Generation Traceability

### 6.1 What is Requirements Traceability?

Requirements traceability is the ability to track a requirement from its origin (business need, regulation, user research) through specification, design, implementation, and testing. For AI-generated requirements, traceability becomes critical because:

1. **Accountability:** Humans need to verify that an AI-generated requirement is justified
2. **Auditability:** Regulated industries require evidence that requirements derive from legitimate sources
3. **Debugging:** When a generated requirement is incorrect, traceability enables root cause analysis (was the constitution wrong, the agent's interpretation wrong, or the generation logic wrong?)
4. **Iteration:** Traceability enables feedback loops -- updating the constitution section that produced a bad requirement

### 6.2 Requirements Traceability Matrix (RTM) -- Traditional Structure

A traditional RTM links requirements across lifecycle stages:

| Field | Description | Example |
|-------|-------------|---------|
| **Requirement ID** | Unique identifier | REQ-PV-042 |
| **Source** | Where the requirement originated | DIBB-001, Persona CDO, GDPR Art 17 |
| **Description** | What the requirement states | "Video rendering must complete within 30 seconds per minute of output" |
| **Priority** | Importance ranking | P1 (Must Have) |
| **Rationale** | Why this requirement exists | "Belief: Real-time rendering is competitive differentiator (DIBB-001)" |
| **Design Artifact** | Where it is reflected in design | data-model.md Section 3.2, API contract /render |
| **Implementation** | Where it is coded | src/rendering/engine.ts |
| **Test Case** | How it is validated | TC-PV-042: "Given a 1-min video template, when rendered, then completes in < 30s" |
| **Status** | Current state | Specified / Designed / Implemented / Verified |

### 6.3 Metadata Fields for AI-Generated Requirements Traceability

For requirements generated by an AI agent from a constitution, additional metadata is needed:

| Field | Purpose | Example Value |
|-------|---------|---------------|
| `requirement_id` | Unique identifier | `REQ-PV-042` |
| `generated_by` | Agent identifier and version | `speckit-v2.1/claude-opus-4` |
| `generated_at` | Timestamp | `2026-02-06T14:30:00Z` |
| `constitution_version` | Version of constitution used | `constitution-v1.3` |
| `source_sections` | Which constitution sections were consulted | `["executive_kernel", "dibb_chains.DIBB-001", "personas.CDO"]` |
| `source_type` | Category of the justification | `strategic_belief` / `regulatory` / `competitive_parity` / `user_research` |
| `dibb_chain_id` | Link to strategic rationale | `DIBB-001` |
| `persona_id` | Which persona benefits | `PER:CDO` |
| `constraint_refs` | Which constraints apply | `["GDPR-Art17", "TECH-PAYLOAD-10MB"]` |
| `confidence_score` | Agent's self-assessed confidence | `0.87` |
| `human_approver` | Who approved this requirement | `null` (pending) / `marcello.generali` |
| `approval_status` | Current approval state | `draft` / `reviewed` / `approved` / `rejected` |
| `rejection_reason` | If rejected, why | `"Appetite exceeded for this cycle"` |
| `derived_from` | Parent requirement (for decomposition) | `REQ-PV-040` |
| `supersedes` | Replaces a previous requirement | `REQ-PV-038` |

### 6.4 Bidirectional Traceability

Bidirectional traceability means every link works in both directions:

**Forward Traceability (Source to Artifact):**
```
Constitution Section → Requirement → Design → Implementation → Test
"Why does this exist?"
```

**Backward Traceability (Artifact to Source):**
```
Test → Implementation → Design → Requirement → Constitution Section
"Where did this come from?"
```

**Impact Analysis (Change Propagation):**
```
Constitution Change → Which requirements are affected → Which implementations need updating
```

For AI-generated artifacts, backward traceability is the most critical -- when a stakeholder questions a generated requirement, the system must produce the chain: "This requirement exists because of DIBB chain X, which references data point Y, which supports belief Z, which is an active bet W."

### 6.5 Standards and Tools

**ISO/IEC/IEEE 29148:2018 (Systems and Software Engineering -- Life Cycle Processes -- Requirements Engineering):**
- Defines requirements management processes
- Mandates traceability as a core practice
- Specifies that requirements should have: unique ID, source, rationale, priority, stakeholder, status
- Requires bidirectional traceability matrices

**IBM DOORS / DOORS Next:**
- Enterprise requirements management tool
- Supports rich linking between requirements and artifacts
- Uses OSLC (Open Services for Lifecycle Collaboration) standard for cross-tool linking
- Attributes per requirement: ID, description, rationale, source, priority, status, owner, verification method

**OSLC (Open Services for Lifecycle Collaboration):**
- Open standard for linking lifecycle artifacts across tools
- Defines link types: `implementedBy`, `validatedBy`, `satisfies`, `trackedBy`, `affectedBy`
- Enables cross-tool traceability (e.g., requirement in DOORS linked to test in Jira linked to code in Git)

### 6.6 Emerging Practices for AI-Generated Artifact Traceability

**Pattern 1: Inline Source Attribution**
```markdown
## REQ-PV-042: Video Rendering Performance
<!-- source: constitution/dibb_chains/DIBB-001 -->
<!-- persona: PER:CDO -->
<!-- constraint: TECH-RENDER-LATENCY -->
<!-- confidence: 0.87 -->
<!-- generated: 2026-02-06T14:30:00Z -->

Video rendering MUST complete within 30 seconds per minute of output for all
standard templates.

**Rationale:** Real-time rendering is identified as the primary competitive
differentiator (DIBB-001: "Real-time rendering speed is our moat"). Enterprise
CDOs require demonstrable performance metrics to justify platform investment
to their boards.
```

**Pattern 2: Sidecar Metadata Files**
```yaml
# requirements/REQ-PV-042.meta.yaml
requirement_id: REQ-PV-042
generated_by: speckit-v2.1/claude-opus-4
constitution_version: v1.3
source_sections:
  - path: "dibb_chains.DIBB-001"
    relevance: "primary"
  - path: "personas.CDO.pain_points[2]"
    relevance: "supporting"
  - path: "competitive_landscape.OpenText.strategy"
    relevance: "contextual"
confidence_score: 0.87
traceability:
  forward:
    design: "data-model.md#rendering-engine"
    api: "contracts/render-api.yaml"
    test: "specs/001-video-perf/checklists/performance.md#TC-042"
  backward:
    dibb: "DIBB-001"
    persona: "PER:CDO"
    regulation: null
```

**Pattern 3: Constitution Section Backreference Registry**
The constitution itself maintains a registry of which requirements have been generated from each section, enabling impact analysis when sections change:

```yaml
# In constitution, appended automatically
section_usage_registry:
  dibb_chains.DIBB-001:
    generated_requirements: ["REQ-PV-042", "REQ-PV-043", "REQ-PV-044"]
    last_generated: "2026-02-06"
    change_impact: "HIGH"  # Many derived requirements
  personas.CDO:
    generated_requirements: ["REQ-PV-042", "REQ-DX-015", "REQ-PW-008"]
    last_generated: "2026-02-05"
    change_impact: "HIGH"
```

### 6.7 Structural Pattern for Constitution Traceability

```yaml
traceability_config:
  # Every generated requirement must include these fields
  required_metadata:
    - requirement_id       # Unique ID (auto-generated: REQ-{product}-{seq})
    - source_sections      # Array of constitution section paths
    - source_type          # Enum: strategic_belief | regulatory | competitive | user_research
    - persona_id           # Must map to a defined persona
    - confidence_score     # Float 0.0-1.0
    - generated_at         # ISO timestamp
    - constitution_version # Git SHA or version tag of constitution

  # Escalation rules based on traceability gaps
  escalation_rules:
    - condition: "No persona_id mapped"
      action: "BLOCK - every requirement must serve a defined persona"
    - condition: "confidence_score < 0.7"
      action: "ESCALATE to human PM for review"
    - condition: "source_type == 'regulatory' and no constraint_ref"
      action: "BLOCK - regulatory requirements must cite specific regulation"
    - condition: "No DIBB chain linkable"
      action: "WARN - requirement may not align with strategic priorities"
```

---

## 7. Cross-Framework Synthesis: Constitution Design Patterns

### 7.1 Converging Patterns Across Frameworks

Analyzing all six frameworks reveals recurring structural patterns that should inform the AI constitution design:

| Pattern | DIBB | Notion | PR/FAQ | AI-Native | Shape Up | Traceability |
|---------|------|--------|--------|-----------|----------|-------------|
| **Evidence-based reasoning** | Core (Data layer) | Problem Statement stage | Problem Paragraph | Context packages | Problem ingredient | Source attribution |
| **Explicit prioritization** | Stack-ranked bets | Twice-yearly planning | TAM in Internal FAQ | Appetite levels | Appetite + Betting table | Priority field |
| **Scope boundaries** | North Star focus | Non-goals in specs | "Not a feature list" | No-go lists | No-Gos ingredient | Exclusion validation |
| **Customer centricity** | Beliefs about users | User Problem stage | Press release format | Persona-driven context | Problem grounding | Persona linkage |
| **Progressive disclosure** | Company → Squad cascade | 4-stage depth | PR → FAQ → 6-pager | Layer 0/1/2 model | Pitch → Build → Ship | Detail levels |
| **Risk identification** | Implicit in beliefs | Open Questions section | Internal FAQ risks | Escalation triggers | Rabbit Holes | Confidence scores |

### 7.2 The Five Constitution Pillars

From this synthesis, the AI constitution should be organized around five pillars:

**Pillar 1: Strategic Context (from DIBB + PR/FAQ)**
- North Star metric
- Active DIBB chains with evidence-to-bet traceability
- Product press releases (one per product line)
- Current cycle bets and their status

**Pillar 2: User Context (from Notion + PR/FAQ + Figma)**
- Persona definitions with Jobs-to-be-Done
- Customer pain points (quoted directly, not summarized)
- Success narratives (what "solved" looks like for each persona)
- User research data references

**Pillar 3: Decision Boundaries (from Shape Up + Linear)**
- Appetite levels for different work categories
- No-go lists (permanent and cycle-specific)
- Rabbit holes (known risk areas with documented mitigations)
- Feature-level principles (trade-off guidance)

**Pillar 4: Competitive and Market Context (from DIBB + PR/FAQ Internal FAQ)**
- Feature parity matrix
- Requirement type classification (table stakes / differentiation / neutralization)
- Market data references
- Business model constraints (pricing, unit economics)

**Pillar 5: Compliance and Technical Constraints (from Traceability standards)**
- Regulatory requirements with specific article/clause references
- Technical constraints with hard limits
- Existing feature inventory (prevents duplication)
- Traceability configuration (required metadata, escalation rules)

### 7.3 Information Architecture: Layered Loading

Combining the Gemini research's Layer 0/1/2 model with DIBB's fractal cascade and Shape Up's progressive disclosure:

```
LAYER 0: Executive Kernel (~2K tokens)
  - Company identity (1 paragraph)
  - North Star metric
  - Top 3 product pillars
  - Top 3 personas (names + 1-line JTBD)
  - Top 5 guardrails (hard constraints)
  - Active cycle bets (names only)

LAYER 1: Working Context (~10K tokens)
  - Full DIBB chains (Data → Insight → Belief → Bet)
  - Product press releases (per product line)
  - Full persona profiles (pain points, gains, JTBD)
  - Competitive parity matrix
  - Appetite levels and no-go lists
  - Business model and pricing logic
  - Feature-level principles

LAYER 2: Deep Reference (~20K+ tokens)
  - Regulatory specifics (GDPR articles, WCAG criteria)
  - Technical constraints (API limits, payload sizes, latency targets)
  - Existing feature inventory
  - Rabbit hole registry with mitigations
  - Historical requirement data and outcome tracking
  - Traceability configuration and escalation rules
```

---

## 8. Actionable Recommendations for Speckit Constitution

### 8.1 Immediate Structural Changes

Based on this research, the Speckit constitution template should be restructured to incorporate:

1. **Add a DIBB Chain section** that encodes strategic reasoning as structured data (YAML or JSON), enabling the agent to cite specific evidence when generating requirements.

2. **Add Product Press Releases** -- one concise PR/FAQ-style statement per product line that serves as the north star for all generated features in that product.

3. **Add Appetite Levels** from Shape Up, so the agent can calibrate the depth and complexity of generated requirements to match the declared investment.

4. **Add Explicit No-Go Lists** (permanent and cycle-specific) that the agent checks before generating any requirement.

5. **Add a Traceability Metadata Schema** that every generated requirement must comply with, including source_sections, persona_id, dibb_chain_id, and confidence_score.

6. **Restructure into three layers** (Executive Kernel, Working Context, Deep Reference) so agents can load only the context depth needed for the task at hand.

### 8.2 Template Structure Recommendation

```markdown
# Company Constitution
## Version: {git_sha}

# LAYER 0: EXECUTIVE KERNEL
## 0.1 Identity
## 0.2 North Star
## 0.3 Top Personas (names + 1-line JTBD)
## 0.4 Guardrails (hard constraints)
## 0.5 Active Cycle Bets (names only)

# LAYER 1: WORKING CONTEXT
## 1.1 DIBB Chains (structured YAML)
## 1.2 Product Press Releases (per product)
## 1.3 Full Persona Profiles (JTBD + pains + gains)
## 1.4 Competitive Parity Matrix
## 1.5 Appetite Levels
## 1.6 No-Go Lists (permanent + cycle)
## 1.7 Business Model and Pricing
## 1.8 Feature-Level Decision Principles

# LAYER 2: DEEP REFERENCE
## 2.1 Regulatory Specifics
## 2.2 Technical Constraints
## 2.3 Feature Inventory
## 2.4 Rabbit Hole Registry
## 2.5 Traceability Configuration
## 2.6 Requirements Generation Rules
```

### 8.3 Key Design Principles

1. **Every section should be citable** -- use section IDs that generated requirements can reference (e.g., `constitution.dibb_chains.DIBB-001`)

2. **Structured data over prose** -- use YAML/JSON blocks for data the agent needs to process programmatically; use prose only for nuanced strategic context

3. **Imperative voice** -- "MUST", "NEVER", "ALWAYS" for constraints; "SHOULD", "PREFER" for guidance; "MAY" for optionality

4. **Front-load and back-load critical content** -- per the "lost in the middle" finding, place guardrails and generation rules at the very beginning (Layer 0) and very end (Layer 2) of the document

5. **Version everything** -- the constitution version must be recorded in every generated artifact for reproducibility and impact analysis

6. **Treat the constitution as a living document** -- establish a correction loop where rejected requirements trigger constitution reviews

---

## Appendix A: Research Sources

### Successfully Fetched Web Sources
1. Henrik Kniberg, "Spotify Rhythm" (blog.crisp.se) -- DIBB framework and Spotify alignment system
2. Lenny Rachitsky, "How Notion Builds Product" (lennysnewsletter.com) -- Notion's four-stage product review process
3. Working Backwards resource (workingbackwards.com) -- Amazon PR/FAQ detailed structure
4. Basecamp, "Shape Up" (basecamp.com/shapeup) -- Chapters 6, 8, 13: Pitch structure, Betting table, Hill charts
5. Linear Method (linear.app/method) -- Issues over user stories, Linear's PM philosophy

### Existing Project Research Referenced
6. `gemini-constitution-research.md` -- Layered architecture for AI-consumable constitutions
7. `enterprise-agentic-pm-research-2024-2026.md` -- Agentic PM patterns and practices
8. `RESEARCH_INDEX.md` -- Prior research inventory and recommendations
9. `CLAUDE.md` -- Current Speckit architecture and workflow

### Domain Knowledge Applied
10. Amazon Working Backwards / PR/FAQ -- from "Working Backwards" by Colin Bryar and Bill Carr (2021)
11. Figma Product Spec Template -- from Yuhki Yamashita's widely shared product spec format
12. Stripe Product Brief -- from public descriptions of Stripe's internal product development process
13. ISO/IEC/IEEE 29148:2018 -- Requirements engineering standard
14. OSLC (Open Services for Lifecycle Collaboration) -- Cross-tool traceability standard
15. IBM DOORS -- Enterprise requirements management tool capabilities

---

## Appendix B: Framework Comparison Matrix

| Dimension | DIBB | Notion 4-Stage | PR/FAQ | Shape Up | Linear | RTM |
|-----------|------|---------------|--------|----------|--------|-----|
| **Origin** | Spotify | Notion | Amazon | Basecamp | Linear | IEEE/ISO |
| **Primary goal** | Strategic alignment | Quality gates | Customer clarity | Scope control | Execution speed | Audit compliance |
| **Key artifact** | DIBB chain | Check-in docs | Press release + FAQ | Pitch document | Plain-language issue | Traceability matrix |
| **Time horizon** | Quarter/year | 2-week sprints | Product lifetime | 6-week cycle | 1-2 week cycles | Full lifecycle |
| **Scope model** | Bets (variable) | Fixed stages | Fixed narrative | Fixed time, variable scope | Minimal overhead | N/A |
| **Customer voice** | Data layer | Problem Statement | Press release | Problem ingredient | Quoted feedback | Source field |
| **Risk handling** | Implicit | Open Questions | Internal FAQ | Rabbit Holes | N/A | Impact analysis |
| **AI-readiness** | High (structured) | Medium (process) | High (narrative) | High (structured) | Medium (minimal) | High (metadata) |
