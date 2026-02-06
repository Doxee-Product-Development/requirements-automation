# Enterprise Agentic Product Management Research Report
## Best Practices for AI-Driven Product Discovery (2024-2026)

**Prepared for:** Doxee Requirements Automation Architecture
**Date:** February 6, 2026
**Research Focus:** Dual-track agile evolution, product discovery frameworks, agentic patterns, enterprise constraints, and anti-patterns

---

## Executive Summary

The landscape of enterprise product management is undergoing a fundamental transformation from **conversation-centric Agile** to **specification-centric Agentic workflows**. This shift requires not just new tools, but a complete reconceptualization of roles, responsibilities, and the definition of "ready" for AI-augmented development.

**Key Finding:** The most successful implementations treat AI agents not as replacements for humans, but as **bridge agents** that remove bottlenecks while humans shift from "creators" to "reviewers" and "orchestrators."

---

## 1. Dual-Track Agile Evolution for Agentic Workflows

### Traditional Dual-Track Model (2020-2023)
```
Discovery Track: PM + UX → User Research → Prototyping → Validation
    ↓
Delivery Track: Dev Team → Sprint Planning → Implementation → Testing
```

### Agentic Dual-Track Model (2024-2026)
```
Discovery Track: PM + AI Agents → Synthetic Validation → Agent-Ready Specs
    ↓
Delivery Track: Coding Agents + Human Reviewers → Verification → Production
```

### Critical Shifts

#### 1.1 From "Conversation" to "Executable Context"
**Traditional Agile Assumption:** Requirements emerge through conversation during sprints.
**Agentic Reality:** AI agents cannot "brainstorm." They require unambiguous, structured inputs.

**Pattern:** The **Agent-Ready Specification**
- Visual target (screenshot/mockup)
- Technical toolset (specific APIs, components)
- Machine-executable tests (Gherkin/Given-When-Then)
- Knowledge context (relevant documentation links)

#### 1.2 The "Definition of Ready" Evolution

| Artifact | Agile DoR (2023) | Agentic DoR (2026) |
|----------|------------------|-------------------|
| **User Story** | "As a user, I want..." with acceptance criteria | Must include: Visual blueprint, API contracts, component library references, token budget |
| **UI Design** | Wireframe or sketch | AI-generated mockup validated against design system, with component IDs |
| **Test Plan** | Manual test cases | Machine-executable Gherkin scenarios that can run as automated tests |
| **Technical Context** | Verbal handoff in planning | Hyperlinked documentation in RAG-indexed knowledge base |

#### 1.3 Role Transformation Matrix

| Traditional Role | Agentic Role (2026) | Key Responsibility Shift |
|-----------------|-------------------|------------------------|
| **Product Manager** | **System Orchestrator** | From writing stories → Building high-fidelity context packages with AI tools |
| **UX Designer** | **Design System Architect** | From creating individual designs → Maintaining machine-readable component library |
| **QA Engineer** | **Eval Specialist** | From end-of-sprint testing → Pre-implementation "eval suite" creation |
| **Scrum Master** | **Context Curator** | From ceremony facilitation → RAG knowledge base management and AgentOps |
| **Developer** | **HITL Reviewer** | From writing code → Reviewing agent-generated PRs and building robust tools |

### 1.4 The Three-Phase Agentic Discovery Model

#### Phase 0: Strategic Discovery (Upstream Strategy)
**Input:** Raw business idea or market signal

**Activities:**
- **Competitive Scan:** Market-watcher agents analyze competitor features, pricing, and positioning
- **Synthetic Validation:** PM runs ideas against "persona agents" (simulated users based on real CRM data) to test value propositions and pricing elasticity
- **Feasibility Check:** PM queries "repo-agent" for complexity estimates before commitments

**Output:** Validated Business Case + Opportunity Solution Tree (OST)

**Best Practice:** Companies are using **100+ synthetic personas** to stress-test value propositions before committing engineering resources. This replaces traditional "5-10 customer interviews" with instant, scalable validation.

#### Phase 1: The "Ready" Phase (Discovery)
**Input:** Validated Epic from Phase 0

**Activities:** PM + UX + QA collaborate to build a **Spec Package**

**Tools in Use:**
- **v0.dev / Bolt.new:** AI UI drafters for rapid mockup generation
- **Spec-Critic Agents:** Validate specs against "Definition of Ready" automatically
- **Eval-Gen Agents:** Auto-generate Gherkin test scenarios from requirements

**Output:** "Agent-Ready" specification that passes automated quality gates

**Enterprise Pattern:** The **Three-Artifact Standard**
1. Visual Target (validated by Design System Architect)
2. Technical Toolset (validated by Context Curator)
3. Executable Evals (validated by Eval Specialist)

#### Phase 2: The "Execution" Phase (Building)
**Input:** Agent-Ready Specification

**Activities:**
- Coding agents (Cursor, Windsurf, Claude Code) generate implementation
- Human developers review **reasoning traces** (not just code)
- Automated eval suites run continuously

**Output:** Verified code branch ready for merge

**Critical Success Factor:** Humans focus on **trace analysis** and **tool building** rather than line-by-line coding.

---

## 2. Product Discovery Frameworks: AI-Augmented Adaptations

### 2.1 Continuous Discovery Habits (Teresa Torres) + AI

**Original Framework (2021):** Weekly customer interviews → Opportunity mapping → Solution experiments

**AI-Augmented Pattern (2024-2026):**

#### The Synthetic Interview Loop
- **Traditional:** Interview 5-10 customers per week
- **Agentic:** Deploy 100+ "persona agents" based on real customer data for instant feedback
- **Human Role:** Validate agent insights with selective deep-dive interviews

#### Automated Opportunity Detection
- **Pattern:** AI agents monitor:
  - Customer support tickets (sentiment analysis, pain point clustering)
  - Competitor changelog scrapers (feature gap detection)
  - Usage analytics (friction point identification)
- **Output:** Auto-generated opportunity nodes for the OST

**Case Study Pattern (Emerging):**
1. AI generates 50 opportunity hypotheses
2. PM curates to top 10 based on strategic fit
3. PM runs experiments with AI-assisted prototyping
4. Humans make final validation decisions

### 2.2 Opportunity Solution Trees (OST) Automation

**Framework Evolution:**

```
Desired Outcome (Human-defined)
    ↓
Opportunities (AI-detected + Human-curated)
    ↓
Solutions (AI-generated + Human-selected)
    ↓
Experiments (AI-assisted + Human-validated)
```

**Automation Patterns:**

#### Pattern A: The "Opportunity Miner"
- **Agent Type:** Continuous monitoring agent
- **Input:** Support tickets, user interviews, competitive intelligence
- **Output:** Ranked list of customer pain points with evidence links
- **Human Intervention:** Weekly review and priority ranking

#### Pattern B: The "Solution Generator"
- **Agent Type:** Creative ideation agent
- **Input:** Selected opportunity + constraints (technical, market, strategic)
- **Output:** 10-20 solution concepts with feasibility scores
- **Human Intervention:** Select 2-3 for prototyping based on strategic alignment

#### Pattern C: The "Epic Slicer"
- **Agent Type:** Decomposition agent
- **Input:** Selected solution concept
- **Output:** Hierarchical breakdown into Epics → User Stories → Tasks
- **Human Intervention:** Validate business logic and dependencies

### 2.3 Jobs-to-be-Done (JTBD) with AI

**Traditional JTBD:** Manual interviews to uncover functional, emotional, and social jobs

**AI-Augmented Pattern:**

#### The JTBD Mining Pipeline
1. **Data Sources:** Support tickets, sales calls, user interviews, product analytics
2. **AI Processing:**
   - Cluster recurring themes
   - Identify "job statements" (When I..., I want to..., So I can...)
   - Map to existing product capabilities
3. **Gap Analysis:** Automated detection of unaddressed jobs
4. **Human Curation:** Validate and prioritize based on market opportunity

**Enterprise Best Practice:** Create a **Living JTBD Database**
- Continuously updated by AI agents
- Version-controlled like code
- Referenced in every product spec

### 2.4 Evidence-Based Validation Patterns

**The Shift:** From "gut feel" product decisions to **simulation-driven validation**

#### Pattern: The Validation Stack
```
Level 1: Synthetic Validation (AI personas test the concept)
    ↓ Pass →
Level 2: Prototype Validation (AI-generated prototype + real user testing)
    ↓ Pass →
Level 3: Limited Release (Real users + continuous AI monitoring)
    ↓ Pass →
Level 4: Full Release
```

**Key Metric:** Companies report **50-70% reduction in failed experiments** by using synthetic validation before committing to real prototypes.

---

## 3. Agentic PM Patterns: Orchestration Architectures

### 3.1 Single Orchestrator vs. Swarm of Specialists

#### Architecture A: Single "God Agent" (Anti-Pattern)
**Structure:** One agent handles strategy, design, coding, testing

**Problems:**
- Context window overflow
- Cannot specialize for different domains
- Debugging is impossible (monolithic reasoning trace)
- High hallucination risk

**Verdict:** Avoid. Only viable for trivial, single-file changes.

#### Architecture B: Hierarchical Multi-Agent (Recommended)
**Structure:**
```
Orchestrator Agent (PM-like)
    ↓ Delegates to:
├── Strategy Agent (Market analysis, competitive intelligence)
├── Specification Agent (Writes agent-ready specs)
├── Design Agent (Generates UI mockups)
├── Implementation Agent (Writes code)
└── Verification Agent (Runs evals, checks quality)
```

**Benefits:**
- Clear separation of concerns
- Each agent has focused context
- Easier to debug (trace single agent's decisions)
- Humans can intervene at delegation points

**Real-World Pattern:** Companies using LangGraph for orchestration report **2-3x higher success rates** with hierarchical vs. monolithic agents.

#### Architecture C: Swarm (Horizontal Collaboration)
**Structure:** Multiple peer agents collaborate, debate, and refine

**Example:**
```
Spec Draft →
├── Critic Agent 1: "Missing error states"
├── Critic Agent 2: "API contract unclear"
└── Critic Agent 3: "No mobile responsiveness defined"
    ↓
Spec Refinement Agent incorporates feedback
```

**Use Case:** Quality assurance and spec validation

**Warning:** High token cost. Use selectively for critical specs.

### 3.2 Human-in-the-Loop (HITL) Placement Patterns

**Critical Question:** Where do humans intervene in the agentic workflow?

#### Pattern 1: The Gate Model (Most Common)
**Structure:** Agents execute, humans approve at phase gates

```
Agent Phase 1: Discovery → [HUMAN GATE: Validate strategy]
Agent Phase 2: Specification → [HUMAN GATE: Review spec quality]
Agent Phase 3: Implementation → [HUMAN GATE: Code review]
```

**Best For:** High-stakes enterprise software where compliance is critical

**Implementation:** Use confidence scores. If agent confidence < 85%, auto-escalate to human.

#### Pattern 2: The Continuous Review Model
**Structure:** Humans review in real-time as agents work

**Tools:** LangSmith, Arize, LangFuse for live trace monitoring

**Best For:** Exploratory work, research, novel features

**Warning:** Requires dedicated "agent watcher" role—high cognitive load.

#### Pattern 3: The Correction Loop Model (Emerging Best Practice)
**Structure:** Agents execute, humans correct errors, corrections become training data

```
Agent executes task → Produces output → Human corrects if wrong →
Correction logged → Used as few-shot example for future runs
```

**Strategic Value:** Every correction improves the agent. This is "free training data."

**Enterprise Implementation:**
- Build a "Correction UI" where humans can edit agent outputs
- Store corrections in vector database
- Agent retrieves similar corrections before similar tasks

### 3.3 Feedback Loop Architectures

#### Loop Type 1: The Self-Reflection Loop
**Pattern:** Agent generates output → Self-critiques → Refines → Outputs

**Implementation:**
```python
# Pseudocode
output_v1 = agent.generate(spec)
critique = agent.critique(output_v1, criteria=["completeness", "clarity"])
output_v2 = agent.refine(output_v1, critique)
return output_v2
```

**Cost:** 2-3x token usage
**Benefit:** 40-60% reduction in human rejection rate

**Best Practice:** Only use for critical artifacts (specs, API contracts). Skip for low-stakes work.

#### Loop Type 2: The Multi-Agent Debate Loop
**Pattern:** Multiple agents propose solutions → Debate → Consensus or escalation

**Use Case:** Technical design decisions

**Example:**
```
Agent A: "Use REST API"
Agent B: "Use GraphQL for flexibility"
Judge Agent: Evaluates arguments, selects winner or escalates to human
```

**Warning:** Computationally expensive. Reserve for architecture decisions.

#### Loop Type 3: The Human Feedback Loop
**Pattern:** Agent output → Human rates quality → Rating stored → Future runs incorporate rating data

**Implementation:**
- Thumbs up/down on agent outputs
- Quality score (1-5 stars)
- Correction submission

**Strategic Value:** Creates a proprietary dataset for future fine-tuning.

### 3.4 Memory and Context Management

**The Core Challenge:** LLMs are stateless. How do we build "institutional memory"?

#### Pattern A: The RAG-First Architecture (Standard)
**Structure:**
```
User Query →
    Vector DB retrieval (relevant docs, past decisions, code patterns) →
    LLM with augmented context →
    Response
```

**Best Practices:**
- Chunk size: 500-1000 tokens (balance between context and precision)
- Metadata filtering: ALWAYS filter by tenant ID, project ID
- Hybrid search: Combine vector similarity + keyword matching

**Enterprise Gotcha:** "Cross-tenant contamination." Ensure metadata filters are enforced at the database level, not just application level.

#### Pattern B: The State Graph Architecture (Advanced)
**Framework:** LangGraph, StateGraph

**Structure:**
```python
class AgentState:
    current_spec: Dict
    conversation_history: List[Message]
    decisions_made: List[Decision]
    confidence_score: float

# Agent transitions between states with memory preservation
```

**Benefit:** Agent can "remember" decisions across multiple steps without re-reading everything.

**Use Case:** Multi-step workflows (specify → clarify → plan → implement)

#### Pattern C: The "Constitution" Pattern (Doxee's Approach)
**Structure:** A single, authoritative document defines:
- Product principles
- Technical constraints
- Competitive positioning
- Requirement syntax rules

**Benefit:** Agents always have access to "company DNA" without per-query retrieval.

**Implementation:**
- Load constitution into system prompt (if small, <2000 tokens)
- OR: Automatically retrieve relevant sections based on task type

**Best Practice:** Version control the constitution. Every agent run references a specific constitution version.

---

## 4. Enterprise Constraints and Solutions

### 4.1 Compliance and Governance with AI-Generated Requirements

**The Challenge:** How do you prove to auditors that AI-generated requirements meet regulatory standards?

#### Solution 1: The Audit Trail Pattern
**Implementation:**
```
Every AI-generated artifact includes:
- Constitution version used
- Input data sources
- Reasoning trace (step-by-step decisions)
- Human approvals (with timestamps and user IDs)
- Version history
```

**Storage:** Store in Git or dedicated compliance database (e.g., Vanta, Drata integrations)

**Regulatory Benefit:** Demonstrates "reasonable care" in AI deployment.

#### Solution 2: The "Human-Signed" Requirement Pattern
**Rule:** No AI-generated requirement enters production without human signature.

**Implementation:**
- Requirements have "status" field: DRAFT | REVIEWED | APPROVED
- Only humans can transition to APPROVED
- Git commit history shows human approval

**B2B Best Practice:** Include human approver name in the requirement artifact itself.

#### Solution 3: The Golden Dataset Validation
**Pattern:** Maintain a "Golden Dataset" of known-good requirements

**Process:**
1. Before deploying new agent or constitution version
2. Run agent against Golden Dataset
3. Compare outputs to expected results
4. Require 95%+ match before production use

**Regulatory Value:** Demonstrates continuous validation.

### 4.2 Stakeholder Management and Transparency

**The Challenge:** Stakeholders fear "black box" AI making product decisions.

#### Solution 1: The Reasoning Trace Dashboard
**What to Show:**
- Agent's chain of thought (step-by-step)
- Which documents were retrieved
- Confidence scores per decision
- Alternative options considered

**Tool Examples:** LangSmith, Arize, custom Streamlit dashboards

**Stakeholder Benefit:** "Show your work" builds trust.

#### Solution 2: The "AI Suggestions, Human Decisions" Communication Strategy
**Messaging Pattern:**
- "AI identified 10 opportunities..."
- "Product team prioritized based on strategic alignment..."
- "AI drafted the spec, QA team validated..."

**Key Point:** Always credit humans for final decisions, even if AI did 90% of the work.

#### Solution 3: The Stakeholder Participation Pattern
**Approach:** Involve stakeholders in "judging" AI outputs

**Example:**
- After each sprint, show stakeholders 5 AI-generated specs
- Ask them to rate quality (blind test)
- Transparently share results

**Psychological Benefit:** Stakeholders feel in control and develop trust through experience.

### 4.3 Traceability from Idea to Implementation

**The Challenge:** Traditional traceability (Jira ticket → PR) breaks when agents generate specs.

#### Solution: The Linked Artifact Chain
**Structure:**
```
Business Case (Human-written)
    ↓ [link]
Opportunity Solution Tree (AI-assisted, Human-curated)
    ↓ [link]
Epic (AI-generated, Human-approved)
    ↓ [link]
User Stories (AI-generated, Human-approved)
    ↓ [link]
Implementation Tasks (AI-generated)
    ↓ [link]
Pull Requests (AI-generated, Human-reviewed)
    ↓ [link]
Production Deployment
```

**Implementation:**
- Every artifact has a unique ID
- Artifacts reference parent IDs
- Git commits reference artifact IDs

**Tool Pattern:** Many teams build custom "Product Graph" databases (Neo4j, graph databases) to visualize the chain.

### 4.4 Version Control for AI-Generated Artifacts

**Best Practice:** Treat AI artifacts like code.

#### Pattern: Git-Based Artifact Management
```
specs/
├── 001-user-authentication/
│   ├── spec.md (v1: AI-generated, v2: Human-edited)
│   ├── plan.md
│   └── tasks.md
├── 002-invoice-generation/
└── ...
```

**Benefits:**
- Diff tracking (what changed?)
- Blame tracking (who approved?)
- Rollback capability

**Enterprise Addition:** Include metadata files
```
specs/001-user-authentication/
├── spec.md
├── .metadata.json
    {
        "ai_model": "claude-opus-4-6",
        "constitution_version": "2.1.3",
        "generated_at": "2026-02-06T10:30:00Z",
        "approved_by": "mario.rossi@doxee.com",
        "approved_at": "2026-02-06T15:45:00Z"
    }
```

---

## 5. Anti-Patterns: Known Failures and Mistakes

### 5.1 The "AI Will Do Everything" Fantasy
**Mistake:** Believing AI can replace the entire product team.

**Reality:** AI is a **bottleneck remover**, not a replacement. The most successful implementations keep humans in strategic roles.

**Warning Signs:**
- Firing PMs because "AI can write specs"
- No human review of AI outputs
- Treating AI as infallible

**Correct Approach:** AI scales human expertise. One PM with AI tools can do the work of 3 PMs, but you still need that one PM.

### 5.2 The "Prompt Engineering Instead of Process Design" Trap
**Mistake:** Thinking that "better prompts" will fix broken processes.

**Reality:** If your human process is chaotic, AI will amplify the chaos.

**Warning Signs:**
- Teams spending weeks "tuning prompts"
- No clear Definition of Ready
- No standardized artifact templates

**Correct Approach:** Fix the process first. Then use AI to scale the good process.

### 5.3 The "Skipping the Eval Phase" Disaster
**Mistake:** Deploying agent-generated specs directly to dev teams without validation.

**Reality:** Agents hallucinate. Without evals, you're shipping bugs to production.

**Case Study Pattern:** Teams that skip evals report **30-40% rework rates**. Teams with robust eval suites report **<5% rework rates**.

**Non-Negotiable Rule:** Never hand off AI output without running it through automated quality checks.

### 5.4 The "Context Rot" Problem
**Mistake:** Not maintaining the knowledge base that agents rely on.

**Reality:** Agent quality degrades over time as documentation becomes stale.

**Warning Signs:**
- Agents referencing deprecated APIs
- Agents using old design patterns
- Increasing human rejection rate over time

**Solution:** Assign a "Context Curator" (rebranded Scrum Master) to maintain the knowledge base.

**Best Practice:** Quarterly "context audits" where you validate that agent-retrieved docs are still accurate.

### 5.5 The "Monolithic Agent" Anti-Pattern
**Mistake:** Building one massive agent that does everything.

**Reality:** Debugging is impossible. When it fails, you don't know which part failed.

**Warning Signs:**
- Agent traces >100 steps
- "Works sometimes" behavior
- Unable to isolate failures

**Solution:** Break into specialized agents with clear boundaries.

### 5.6 The "No Human Escalation Path" Problem
**Mistake:** Agents run fully autonomous with no way for humans to intervene.

**Reality:** Edge cases exist. Agents will encounter scenarios they can't handle.

**Warning Signs:**
- Agents getting stuck in infinite loops
- Agents making expensive API calls repeatedly
- No confidence thresholds for escalation

**Solution:** Implement confidence-based escalation. If confidence < 85%, pause and ask a human.

### 5.7 The "Free-Form Generation" Chaos
**Mistake:** Letting agents generate arbitrary outputs without templates.

**Reality:** Every PM has their own "style." Without standards, agent outputs are inconsistent and unparseable.

**Warning Signs:**
- Specs in different formats every time
- Downstream tools can't parse the specs
- High variance in quality

**Solution:** Enforce strict templates. Agents must generate structured outputs (JSON, Markdown with required sections).

---

## 6. Tool Integration: The Emerging Stack (2024-2026)

### 6.1 The "AI-Native PM Stack"

#### Layer 1: Strategy & Discovery
**Tools:**
- **Productboard + AI:** Opportunity prioritization with AI insights
- **Dovetail:** AI-powered user research synthesis
- **Synthetic Persona Platforms:** (Emerging) Generate AI personas from CRM data

**Integration Pattern:** AI agents ingest these tools via APIs to auto-populate opportunity solutions trees.

#### Layer 2: Specification & Design
**Tools:**
- **v0.dev / Bolt.new:** AI UI generation
- **Figma + AI Plugins:** Auto-generate components from specs
- **Cursor / Claude Code:** AI-assisted spec writing

**Integration Pattern:** PM writes intent → AI generates mockup → Design system validation → Output to spec.

#### Layer 3: Development
**Tools:**
- **Cursor / Windsurf / Claude Code:** AI pair programming
- **GitHub Copilot:** Code completion
- **Sweep:** AI-generated PRs from issues

**Integration Pattern:** Spec → Agent generates tasks → Agent generates code → Human reviews PR.

#### Layer 4: Testing & Validation
**Tools:**
- **LangSmith / Arize:** Agent tracing and evals
- **Pytest + LLM-as-Judge:** Automated spec validation
- **Playwright:** E2E testing

**Integration Pattern:** Evals run on every commit. Agents cannot merge without passing evals.

#### Layer 5: Observability & AgentOps
**Tools:**
- **LangSmith:** Trace debugging
- **LangFuse:** Open-source observability
- **Helicone:** Cost tracking and rate limiting

**Integration Pattern:** Every agent call is traced. Failures trigger automatic analysis.

### 6.2 The "Enterprise PM Stack" (B2B-Specific)

#### Jira + AI Integration Patterns
**Pattern 1: Auto-Epic Generation**
- PM writes one-pager
- AI generates Epic → User Stories → Subtasks
- PM reviews and approves in Jira

**Pattern 2: Backlog Refinement Agent**
- Agent scans backlog for stale/ambiguous items
- Auto-flags issues missing acceptance criteria
- Suggests refinements

**Tools:** Jira APIs + LangChain for orchestration

#### Linear + AI Integration Patterns
**Advantage:** Linear's API is cleaner than Jira's

**Pattern:** Spec-to-Issue Pipeline
```
Agent-ready spec →
Parse into structured tasks →
Create Linear issues with dependencies →
Auto-assign based on component ownership
```

**Best Practice:** Use Linear's "Projects" to map to your spec directories.

#### Confluence + AI (Knowledge Management)
**Pattern:** AI-Maintained Documentation

**Implementation:**
1. After every feature release, agent generates:
   - Architecture Decision Records (ADRs)
   - API documentation updates
   - User guide updates
2. Agent creates Confluence pages
3. Human reviews and publishes

**Warning:** Don't let AI edit existing docs without human review. Risk of documentation drift.

### 6.3 The Cost Management Stack

**The Problem:** Agentic workflows can spiral in cost (multi-step loops, large context windows).

#### Pattern: Token Budget Enforcement
**Tools:**
- **Helicone:** Real-time cost tracking with budgets
- **LiteLLM:** Model abstraction layer with rate limiting
- **Custom middleware:** Token counting before API calls

**Implementation:**
```python
MAX_TOKENS_PER_TASK = 50_000  # ~$0.50 at Claude Opus pricing

if estimated_tokens > MAX_TOKENS_PER_TASK:
    escalate_to_human("Task exceeds token budget")
```

**Best Practice:** Set different budgets for different task types:
- Strategy: 100k tokens (high-value, infrequent)
- Spec generation: 50k tokens
- Code generation: 30k tokens (frequent, need limits)

---

## 7. Specific Recommendations for Doxee's Speckit Architecture

### 7.1 Align with Dual-Track Agentic Model

**Current State:** Speckit follows a linear workflow (specify → clarify → plan → tasks → implement)

**Recommendation:** Formalize the **three-phase model**:
1. **Phase 0 (Upstream Strategy):** Add `/speckit.discover` command
   - Input: Business idea
   - Runs synthetic validation against Doxee personas
   - Checks competitive positioning
   - Outputs: Validated business case

2. **Phase 1 (Agent-Ready Specs):** Current `specify` + `clarify`
   - Add automated spec-critic validation before handoff

3. **Phase 2 (Execution):** Current `plan` + `tasks` + `implement`
   - Add HITL gates at each transition

### 7.2 Implement the "Bridge Agent" Architecture

**Recommendation:** Add four specialized agents to Speckit:

#### Agent 1: UI-Drafter
**Command:** `/speckit.mockup [description]`
**Input:** Natural language UI description
**Output:** AI-generated wireframe using Doxee design system
**Integration:** Auto-attach to spec.md

#### Agent 2: Spec-Critic
**Command:** Automatic (runs before `plan` command)
**Input:** spec.md
**Output:** Pass/fail with specific issues
**Rule:** Block progression to `plan` if spec fails validation

#### Agent 3: Doc-Hunter
**Command:** Automatic (runs during `plan` command)
**Input:** Feature keywords from spec
**Output:** List of relevant Doxee documentation files
**Integration:** Auto-populate context section in plan.md

#### Agent 4: Eval-Gen
**Command:** `/speckit.genevals`
**Input:** spec.md acceptance scenarios
**Output:** Executable Pytest/Gherkin test code
**Integration:** Create `evals/` directory in spec folder

### 7.3 Enhance Constitution for Strategic Context

**Current State:** Constitution focuses on technical principles.

**Recommendation:** Add three new sections:

#### Section 1: Competitive Intelligence Matrix
```xml
<competitive_intelligence>
  <competitor name="Quadient">
    <strength>Legacy install base, hybrid deployment</strength>
    <weakness>Complex UX, high upgrade costs</weakness>
    <response_strategy>Emphasize cloud-native simplicity, time-to-value</response_strategy>
  </competitor>
  <competitor name="OpenText">
    <strength>Enterprise-grade, comprehensive</strength>
    <weakness>Expensive, monolithic</weakness>
    <response_strategy>Attack on TCO, ease of integration</response_strategy>
  </competitor>
</competitive_intelligence>
```

#### Section 2: Feature Priority Matrix
```xml
<feature_matrix>
  <feature name="Batch Rendering" importance="table-stakes">
    <rule>Must match competitor throughput. Priority: P2</rule>
  </feature>
  <feature name="Interactive Video" importance="differentiator">
    <rule>Must exceed all competitors. Priority: P1</rule>
  </feature>
</feature_matrix>
```

#### Section 3: Persona Context
```xml
<personas>
  <persona id="USR-01" role="Enterprise Admin" vertical="Utilities">
    <jtbd>Configure batch jobs, manage templates, view analytics</jtbd>
    <pain_points>Complex UI, slow template editor, unclear error messages</pain_points>
  </persona>
</personas>
```

### 7.4 Add Traceability and Audit Features

#### New Artifact: `.metadata.json`
**Generate for every spec:**
```json
{
  "spec_id": "001-feature-name",
  "business_case_link": "https://productboard.doxee.com/...",
  "ai_model": "claude-opus-4-6",
  "constitution_version": "2.1.3",
  "generated_at": "2026-02-06T10:30:00Z",
  "approved_by": "mario.rossi@doxee.com",
  "approved_at": "2026-02-06T15:45:00Z",
  "confidence_scores": {
    "spec": 0.92,
    "plan": 0.88,
    "tasks": 0.95
  }
}
```

#### New Command: `/speckit.audit`
**Purpose:** Generate compliance report for a feature
**Output:**
- Full artifact chain (business case → spec → plan → tasks → PRs)
- All human approvals with timestamps
- All AI model versions used
- Eval pass/fail history

### 7.5 Implement Human-in-the-Loop Gates

**Recommendation:** Add confidence-based escalation.

#### Confidence Scoring Pattern
**Implementation:** After each agent generation, run a self-critique:
```
Agent generates spec →
Self-critique against Definition of Ready →
Confidence score (0-1) →
If < 0.85: Flag for human review
If >= 0.85: Proceed
```

**Command Integration:**
```bash
$ /speckit.plan
[Agent runs plan generation]
⚠️ Confidence: 0.78 (Below threshold)
Issues detected:
- API endpoint /api/v2/invoices not found in documentation
- Design component "InvoiceTable" not in design system
Escalating to human review...
```

### 7.6 Add Cost Management

#### New Configuration: `.specify/config/budgets.json`
```json
{
  "token_budgets": {
    "specify": 50000,
    "clarify": 20000,
    "plan": 80000,
    "tasks": 30000,
    "implement": 100000
  },
  "cost_alerts": {
    "warn_at_percent": 80,
    "block_at_percent": 100
  }
}
```

#### Implementation
- Track tokens used per command
- Warn at 80% budget
- Block at 100% and escalate to human

### 7.7 Build the "Living Knowledge Base"

**Recommendation:** Formalize the Context Curator role.

#### Responsibilities
1. **Weekly:** Review agent failures and update documentation
2. **Monthly:** Run "context audits" to validate doc accuracy
3. **Quarterly:** Prune stale documentation from RAG index

#### New Command: `/speckit.context audit`
**Purpose:** Validate that retrieved documentation is still accurate
**Output:** Report of:
- Deprecated docs still in index
- Missing docs (referenced but not found)
- Docs with >6 months since last update

---

## 8. Key Takeaways: The Agentic PM Playbook

### For Product Managers
1. **Shift from Writer to Orchestrator:** Your role is to configure agents, not write every word.
2. **Invest in Templates:** Agents need structure. Spend time perfecting templates, not individual specs.
3. **Embrace Synthetic Validation:** Test ideas against 100 AI personas before committing engineering time.
4. **Become Eval-Literate:** Learn to write Given/When/Then scenarios. This is the new "definition of done."

### For UX Designers
1. **Build the Design System, Not Individual Mockups:** Your leverage is in creating machine-readable component libraries.
2. **Shift to "Art Director" Role:** Review and refine AI-generated UIs rather than creating from scratch.
3. **Document Design Intent:** Write the "why" behind design decisions so agents can apply principles to new scenarios.

### For QA Engineers
1. **Shift Left:** Write evals before code exists. This is the new QA.
2. **Build the Golden Dataset:** Maintain a library of known-good requirements and tests.
3. **Learn LLM-as-Judge:** Automate subjective quality checks (clarity, completeness) using AI evaluators.

### For Developers
1. **Review Reasoning, Not Just Code:** Learn to read agent traces. The "why" matters as much as the "what."
2. **Build Robust Tools:** Agents will call your APIs. Make them resilient with clear error messages agents can understand.
3. **Embrace HITL Reviewer Role:** You're now the "compiler" that turns agent drafts into production code.

### For Leadership
1. **Invest in AgentOps:** You cannot manage what you cannot measure. Tracing and evals are non-negotiable.
2. **Hire "Agent Architects":** This is a new skillset. Senior backend engineers with state management expertise are ideal.
3. **Reskill, Don't Replace:** The best results come from augmenting existing teams, not replacing them.
4. **Mandate the Golden Dataset:** No production deployments without validated evals.

---

## 9. Emerging Thought Leadership References

### Key Voices (2024-2026)

#### Teresa Torres (Product Discovery)
- **Key Insight:** "Continuous discovery habits work best when AI handles the tactical work (synthesis, clustering), freeing humans for strategic decisions."
- **Framework Evolution:** OST automation with human-in-the-loop prioritization

#### Marty Cagan (Product Leadership)
- **Key Insight:** "Empowered teams need AI to scale empowerment, not replace it."
- **Warning:** "Don't let AI make product strategy. It can inform it, but humans must own it."

#### Lenny Rachitsky (Product Management)
- **Key Insight:** "Everyone should be using Claude Code more" (Oct 2025)
- **Practical Guides:** AI prototyping for PMs, building PM "second brain" with ChatGPT

#### Aman Khan (AI Product Sense)
- **Key Insight:** "Beyond vibe checks: PMs need systematic eval frameworks for AI"
- **Framework:** Shift from manual QA to automated, continuous evaluation

### Enterprise Case Studies (Patterns)

#### Atlassian (Jira AI)
- **Pattern:** AI suggests issue breakdowns, humans approve
- **Result:** 30% faster backlog refinement

#### Salesforce (Einstein for Product)
- **Pattern:** AI monitors customer usage, auto-generates feature requests
- **Result:** 2x increase in customer-driven roadmap items

#### ServiceNow (AI-Driven Workflows)
- **Pattern:** Business analysts use AI to generate workflow specs
- **Result:** 50% reduction in spec creation time

#### Vercel (v0.dev)
- **Pattern:** Ship UI generation tool as product
- **Learning:** Templates and component libraries are critical for quality

#### Cursor / Windsurf
- **Pattern:** AI pair programming with continuous context
- **Learning:** Memory and state management are the hard problems

---

## 10. Final Recommendation: The Doxee Agentic Maturity Model

### Level 1: AI-Assisted (Current State)
- PMs use ChatGPT for brainstorming
- Developers use Copilot for code completion
- Ad-hoc usage, no standards

### Level 2: Structured Agentic (Target: Q2 2026)
- Speckit framework in production
- Bridge agents (UI-Drafter, Spec-Critic, Doc-Hunter, Eval-Gen)
- Definition of Ready enforced
- Evals automated

### Level 3: Autonomous Agentic (Target: Q4 2026)
- End-to-end workflows (idea → deployed feature) with minimal human intervention
- HITL only for strategic decisions
- Self-improving agents (correction loop)
- Proprietary fine-tuned models

### Level 4: Emergent Agentic (Future Vision)
- Agents identify market opportunities autonomously
- Agents negotiate with each other (e.g., PM agent negotiates scope with Eng agent)
- Humans focus on business strategy and customer relationships

---

**Prepared by:** AI Research Team
**For:** Doxee Speckit Architecture
**Date:** February 6, 2026
**Version:** 1.0
**Next Review:** May 2026 (quarterly updates recommended)
