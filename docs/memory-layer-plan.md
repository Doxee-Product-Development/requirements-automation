# Doxee Memory Layer Implementation Plan

> **Optimized with Context Engineering Best Practices**

## Overview

Build a **Memory Layer** in Markdown for Doxee that enables a multi-agent swarm to create roadmap ideas, prioritize features, build development plans, and generate high-quality stories with UX prototypes.

---

## Architecture

### Three-Tier Memory Model

Based on context-engineering best practices, the memory layer uses a **three-tier model**:

| Tier | Purpose | Retention |
|------|---------|-----------|
| **CAPTURE (Hot)** | Active work items, real-time traces | Per-session |
| **SYNTHESIS (Warm)** | Aggregated learnings by phase | Curated weekly |
| **APPLICATION (Cold)** | Archived history, decisions | Permanent |

### Memory Layer Structure

```
.specify/
├── memory/
│   ├── constitution.md               # EXISTING - fill with Doxee principles
│   ├── agents/                       # NEW - Agent definitions
│   │   ├── _registry.md              # Agent catalog, traits, handoff protocols
│   │   ├── analyst.md                # Market analysis, competitor scan
│   │   ├── planner.md                # Roadmap design, sprint planning
│   │   ├── storyteller.md            # Story creation, ACs
│   │   ├── validator.md              # Quality gates, DoD checks
│   │   └── ux-designer.md            # Figma-based UX prototyping
│   ├── context/                      # Shared knowledge base (SYNTHESIS tier)
│   │   ├── doxee-platform.md         # Platform context (synthesized from existing docs)
│   │   ├── market-intelligence.md    # Competitor/trend data
│   │   ├── tech-stack.md             # CCM/CXM technology context
│   │   └── user-personas.md          # Target user definitions
│   ├── patterns/                     # Learned patterns database (SYNTHESIS tier)
│   │   ├── story-templates.md        # Successful story patterns
│   │   ├── acceptance-criteria.md    # AC pattern library
│   │   └── quality-gates.md          # DoD checklist patterns
│   ├── decisions/                    # NEW - Decision log (APPLICATION tier)
│   │   ├── _index.md                 # Decision registry
│   │   └── [DATE]-[topic].md         # Individual ADRs
│   ├── signals/                      # NEW - Pattern detection (from context-engineering)
│   │   ├── failures.jsonl            # Validation failures with context
│   │   ├── loopbacks.jsonl           # Feedback loop occurrences
│   │   └── patterns.jsonl            # Weekly aggregated patterns
│   └── sessions/                     # Agent session logs (CAPTURE tier)
│       └── [DATE]-[session-id]/
│           ├── work.md               # Goal, result, signal tracking
│           ├── trace.jsonl           # Decision trace (theory of mind)
│           └── output/               # Deliverables produced
├── workflows/                        # Multi-agent workflows
│   ├── idea-to-story.md              # Full pipeline workflow
│   ├── ux-prototype.md               # UX Designer workflow
│   └── feedback-loop.md              # NEW - Validator feedback protocol
└── templates/
    ├── agent-prompt-template.md      # Agent invocation template
    └── handoff-template.md           # NEW - Agent handoff format

.claude/commands/
├── doxee.analyst.md                  # NEW
├── doxee.planner.md                  # NEW
├── doxee.storyteller.md              # NEW
├── doxee.validator.md                # NEW
├── doxee.ux-designer.md              # NEW
└── doxee.swarm.md                    # NEW - Supervisor/Orchestrator

doxee/
└── specs/
    └── ideas/
        └── [idea-slug]/
            ├── _idea.md                      # → Jira Product Discovery: Idea
            └── epics/
                └── [epic-slug]/
                    ├── _epic.md              # → Jira Software: Epic
                    ├── plan.md               # Technical implementation plan
                    ├── research.md           # Research & discovery
                    └── stories/
                        └── [story-slug]/
                            ├── _story.md     # → Jira Software: Story
                            └── attachments/
                                └── *.png, *.pdf, *.fig, user-flows/
```

### Artifact Schema Definitions

#### `_idea.md` (Jira Product Discovery: Idea)

```yaml
---
jira_key: null                    # Set after sync (e.g., PROJ-100)
jira_project: null                # Configurable at sync time
title: "Idea Title"
status: draft | ready | synced
summary: "One-line description"
insights:                         # JPD fields
  - "Customer feedback insight 1"
  - "Market research insight 2"
impact: low | medium | high       # JPD scoring
effort: low | medium | high
confidence: low | medium | high
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

#### `_epic.md` (Jira Software: Epic)

```yaml
---
jira_key: null
jira_project: null
title: "Epic Title"
status: draft | ready | in_progress | done | synced
summary: "One-line description"
parent_idea: "../_idea.md"
priority: P1 | P2 | P3
labels: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

#### `_story.md` (Jira Software: Story)

```yaml
---
jira_key: null
jira_project: null
title: "Story Title"
status: draft | ready | in_progress | done | synced
parent_epic: "../../_epic.md"
priority: P1 | P2 | P3
story_points: null
labels: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### Jira Mapping

| Local Artifact | Jira Type | Project |
|----------------|-----------|---------|
| `_idea.md` | Idea (Product Discovery) | Configurable |
| `_epic.md` | Epic (Software) | Configurable |
| `_story.md` | Story (Software) | Configurable |
| Tasks in story | Sub-task (Software) | Linked to Story |

**Connection**: Jira Product Discovery Ideas link to delivery Epics via "Delivery tickets".

---

## Agent Swarm Design

### Architecture Pattern: Hybrid Supervisor + Swarm

Based on multi-agent-patterns best practices, we use a **hybrid architecture**:

1. **Supervisor (`doxee.swarm`)** - Central orchestrator for workflow coordination
2. **Peer Handoffs** - Direct agent-to-agent transfers for specialized flows
3. **Parallel Execution** - UX Designer + Storyteller run concurrently

```
                         ┌──────────────────────┐
                         │   doxee.swarm        │
                         │   (Supervisor)       │
                         │   model: sonnet      │
                         └──────────┬───────────┘
                                    │
        ┌───────────────────────────┼───────────────────────────┐
        ▼                           ▼                           ▼
┌───────────────┐          ┌───────────────┐          ┌───────────────┐
│   ANALYST     │          │   PLANNER     │          │   VALIDATOR   │
│   model:      │─────────▶│   model:      │          │   model:      │
│   haiku       │          │   sonnet      │          │   haiku       │
└───────────────┘          └───────┬───────┘          └───────────────┘
                                   │                          ▲
                    ┌──────────────┴──────────────┐           │
                    ▼                              ▼           │
           ┌───────────────┐              ┌───────────────┐    │
           │ UX DESIGNER   │              │ STORYTELLER   │────┘
           │ model: sonnet │─────────────▶│ model: sonnet │
           └───────────────┘  (handoff)   └───────────────┘
```

### Model Selection Strategy (Critical for Performance)

From PAI delegation patterns - **always specify model** to avoid Opus overhead:

| Agent | Model | Rationale |
|-------|-------|-----------|
| Analyst | `haiku` | Simple lookups, document scanning |
| Planner | `sonnet` | Moderate complexity, roadmap design |
| UX Designer | `sonnet` | Design reasoning, component selection |
| Storyteller | `sonnet` | Standard story creation |
| Validator | `haiku` | Checklist validation, quick checks |
| Swarm (Supervisor) | `sonnet` | Orchestration, routing decisions |

**Token Economics**: Multi-agent systems consume ~15× baseline tokens. Using `haiku` for grunt work reduces this significantly.

### Agent Trait System

Each agent has defined traits (from Agent System patterns):

```yaml
analyst:
  traits: [analytical, research-oriented, thorough]
  behaviors:
    - "Always cites sources from analyst reports"
    - "Quantifies market opportunity size"
    - "Compares against competitor positioning"

planner:
  traits: [methodical, strategic, dependency-aware]
  behaviors:
    - "Maps dependencies before sequencing"
    - "Applies RICE scoring for prioritization"
    - "Identifies parallel execution opportunities"

ux-designer:
  traits: [user-focused, design-minded, detail-oriented]
  behaviors:
    - "References Figma design system components"
    - "Documents all interaction states"
    - "Ensures WCAG 2.1 AA compliance"

storyteller:
  traits: [creative, structured, user-centric]
  behaviors:
    - "Uses Given-When-Then for acceptance criteria"
    - "Includes UX artifact references"
    - "Writes for non-technical stakeholders"

validator:
  traits: [critical, thorough, quality-focused]
  behaviors:
    - "Applies DoD checklist systematically"
    - "Provides specific, actionable feedback"
    - "Maximum 2 feedback loops before escalation"
```

### Agent Definitions with Context Isolation

#### 1. Analyst Agent
- **Role**: Market analysis, competitor scan, trend detection
- **Model**: `haiku` (simple document scanning)
- **Inputs**: `doxee/analysts/`, X-One RAG queries
- **Outputs**: Opportunity assessments → `doxee/specs/ideas/[idea-slug]/_idea.md`
- **Context Isolation**: Instruction passing (minimal context)
- **Handoff**: Planner (via Task with structured output)

#### 2. Planner Agent
- **Role**: Roadmap design, sprint planning, dependency mapping
- **Model**: `sonnet` (strategic reasoning)
- **Inputs**: Analyst outputs (Ideas), existing backlog
- **Outputs**: Epics → `doxee/specs/ideas/[idea-slug]/epics/[epic-slug]/_epic.md`
- **Context Isolation**: Full context delegation (needs complete picture)
- **Handoff**: UX Designer AND Storyteller (parallel Tasks)

#### 3. UX Designer Agent
- **Role**: User experience design using Figma MCP tools
- **Model**: `sonnet` (design decisions)
- **Inputs**: Feature briefs, user personas
- **Outputs**:
  - UX specifications with Figma component references
  - Screenshots → `doxee/specs/ideas/[idea]/epics/[epic]/stories/[story]/attachments/`
  - User flow documentation
- **Context Isolation**: Instruction passing + file system coordination
- **Handoff**: Storyteller (direct handoff with `forward_message` pattern)

#### 4. Storyteller Agent
- **Role**: Story creation with acceptance criteria
- **Model**: `sonnet` (content creation)
- **Inputs**: Feature briefs, UX artifacts (screenshots, flows)
- **Outputs**: Story files → `doxee/specs/ideas/[idea]/epics/[epic]/stories/[story]/_story.md`
- **Context Isolation**: Full context from UX Designer
- **Handoff**: Validator

#### 5. Validator Agent
- **Role**: Quality gates, Definition of Done checking
- **Model**: `haiku` (checklist validation)
- **Inputs**: Stories, DoD criteria from patterns
- **Outputs**: Approval or feedback loop back to Storyteller
- **Context Isolation**: Instruction passing (minimal)
- **Feedback Loop**: Max 2 iterations, then escalation

---

## Context Isolation Patterns

### File System Coordination (Recommended for Multi-Agent)

From context-engineering patterns - agents coordinate via shared files:

```
.specify/memory/sessions/[session-id]/
├── work.md                    # Shared state: goal, current status
├── analyst-output.json        # Analyst → Planner handoff
├── planner-output.json        # Planner → UX/Storyteller handoff
├── ux-artifacts/              # UX Designer → Storyteller
│   ├── spec.md
│   └── screenshots/
├── stories/                   # Storyteller → Validator
│   └── [story-id].md
└── validation/                # Validator feedback
    └── [story-id]-feedback.md
```

**Why**: Avoids context bloat from shared state passing. Each agent reads only what it needs.

### Handoff Protocol

```markdown
## Handoff Document Template

### From: [Agent Name]
### To: [Next Agent Name]
### Session: [session-id]

## Summary
[1-2 sentence summary of completed work]

## Artifacts Produced
- [File path 1]: [description]
- [File path 2]: [description]

## Context for Next Agent
[Specific information the next agent needs]

## Constraints/Decisions Made
- [Decision 1]: [rationale]
- [Decision 2]: [rationale]

## Success Criteria for Next Step
- [ ] [Criterion 1]
- [ ] [Criterion 2]
```

---

## Failure Modes and Mitigations

From multi-agent-patterns skill:

| Failure Mode | Mitigation |
|--------------|------------|
| **Supervisor Bottleneck** | Output schema constraints - agents return distilled summaries |
| **Telephone Game** | Use `forward_message` pattern - UX Designer passes directly to Storyteller |
| **Feedback Loop Divergence** | Max 2 iterations, then escalate to human |
| **Context Drift** | Shared memory files, explicit handoff documents |
| **Error Propagation** | Circuit breaker pattern - 3 failures = agent unavailable |

### Circuit Breaker Configuration

```yaml
circuit_breaker:
  failure_threshold: 3
  timeout_seconds: 60
  agents:
    - analyst
    - planner
    - ux-designer
    - storyteller
    - validator
```

---

## Signal Tracking (From Memory System)

Track patterns across sessions for continuous improvement:

### failures.jsonl
```json
{"timestamp": "...", "agent": "validator", "story_id": "...", "criterion": "ACs not testable", "feedback": "..."}
```

### loopbacks.jsonl
```json
{"timestamp": "...", "from_agent": "validator", "to_agent": "storyteller", "reason": "...", "iteration": 2}
```

### patterns.jsonl (Weekly aggregation)
```json
{"week": "2026-W06", "pattern": "Missing error states in UX specs", "frequency": 4, "recommendation": "Add error state checklist to UX Designer"}
```

---

## UX Designer Agent - Figma MCP Integration

### Workflow Steps

1. **Extract Design Context**
   - Use `mcp__plugin_figma_figma__get_design_context` to understand existing patterns
   - Load user personas from `memory/context/user-personas.md`
   - Identify relevant design system components

2. **Get Design Specifications**
   ```
   Tools:
   - mcp__plugin_figma_figma__get_screenshot (capture existing designs)
   - mcp__plugin_figma_figma__get_metadata (extract component specs)
   - mcp__plugin_figma_figma__get_variable_defs (design tokens)
   - mcp__plugin_figma_figma__get_code_connect_map (component mappings)
   ```

3. **Generate UX Specifications**
   - Create detailed UX requirements document
   - Reference existing Figma components
   - Define user flows with screen states

4. **Capture Screenshots**
   - Use `mcp__plugin_figma_figma__get_screenshot` for design references
   - Store in `doxee/specs/ideas/[idea]/epics/[epic]/stories/[story]/attachments/`

5. **Document User Flows**
   - Annotate screenshots with interaction points
   - Create step-by-step user journey documentation
   - Store in story's `attachments/` folder

6. **Direct Handoff to Storyteller** (forward_message pattern)
   - Package all screenshots, flows, and component specs
   - Pass directly to Storyteller without supervisor synthesis

### UX Specification Template

```markdown
# UX Specification: [Feature Name]

## User Context
- Persona: [from user-personas.md]
- Goal: [user's objective]
- Context: [where in the platform this appears]

## Screen States
1. **Default State**: [description + screenshot ref]
2. **Active/Hover State**: [description + screenshot ref]
3. **Error State**: [description + screenshot ref]
4. **Success State**: [description + screenshot ref]

## Design References
- Figma Component: [component name from get_code_connect_map]
- Design Tokens: [relevant tokens from get_variable_defs]

## User Flow
1. User lands on [screen]
2. User [action]
3. System [response]
4. [continue flow...]

## Accessibility Requirements
- WCAG 2.1 AA compliance
- Keyboard navigation support
- Screen reader compatibility
```

---

## Integration Points

### Figma MCP - Design System & Screenshots
- `figma:implement-design` skill for design-to-code
- `mcp__plugin_figma_figma__get_screenshot` for capturing designs
- `mcp__plugin_figma_figma__get_design_context` for pattern extraction
- Store screenshots in Git-tracked folder

### Atlassian (Jira) - Bidirectional Sync

**Jira Product Discovery + Jira Software Integration:**

| Local Artifact | Jira Type | Sync Direction |
|----------------|-----------|----------------|
| `_idea.md` | Idea (Product Discovery) | Bidirectional |
| `_epic.md` | Epic (Software) | Bidirectional |
| `_story.md` | Story (Software) | Bidirectional |
| Tasks in story | Sub-task (Software) | Local → Jira |

**Tools:**
- `mcp__MCP_DOCKER__jira_create_issue` - Create issues
- `mcp__MCP_DOCKER__jira_update_issue` - Update issues
- `mcp__MCP_DOCKER__jira_search` - Search for duplicates
- `/speckit.sync` - Bidirectional sync command

**Sync Workflow:**
1. Local artifacts have `jira_key: null` until synced
2. On sync, create/update Jira issues and populate `jira_key`
3. Conflict resolution: local wins by default, `--force-jira` for Jira wins
4. Product Discovery Ideas link to delivery Epics via "Delivery tickets"

**MVP**: Stories stored locally as Markdown, Jira sync added in Phase 5

### X-One RAG - Large Document Queries
- Query large analyst reports
- Search product documentation corpus

### Claude Code Task Tool - Orchestration
- TaskCreate/TaskUpdate for agent handoffs
- Dependency chains via blockedBy
- **Always specify model parameter** to control performance

---

## Implementation Phases

### Phase 1: MVP (Week 1-2)

**Files to Create:**

1. **`.specify/memory/agents/_registry.md`**
   - Agent catalog with all 5 agents
   - Trait definitions
   - Model assignments
   - Invocation protocol

2. **`.specify/memory/agents/analyst.md`**
   - Full agent definition with workflow
   - X-One RAG integration

3. **`.specify/memory/agents/storyteller.md`**
   - Local story file creation
   - AC pattern references

4. **`.specify/memory/context/doxee-platform.md`**
   - Synthesize from `doxee/Doxee Platform functional architecture and components.md`

5. **`.claude/commands/doxee.analyst.md`**
   - Following existing speckit.specify.md pattern
   - Model: haiku
   - Handoff to planner

**Validation:**
- `/doxee.analyst [topic]` returns opportunity assessment
- Creates handoff task for next agent
- Output stored in `doxee/roadmap/ideas/`

### Phase 2: Core Agents (Week 3-4)

**Files to Create:**
- `.specify/memory/agents/planner.md`
- `.specify/memory/agents/validator.md`
- `.claude/commands/doxee.planner.md`
- `.claude/commands/doxee.validator.md`
- `.specify/memory/patterns/quality-gates.md`
- `.specify/workflows/idea-to-story.md`
- `.specify/workflows/feedback-loop.md`

**Validation:**
- Full pipeline: Analyst → Planner → Storyteller → Validator
- Stories saved as local Markdown files
- Feedback loop working (max 2 iterations)

### Phase 3: UX Designer Agent (Week 5-6)

**Files to Create:**
- `.specify/memory/agents/ux-designer.md`
- `.claude/commands/doxee.ux-designer.md`
- `.specify/memory/context/user-personas.md` (drafted from existing product docs)
- `.specify/workflows/ux-prototype.md`
- `doxee/prototypes/` folder structure
- `.specify/templates/handoff-template.md`

**Validation:**
- UX specifications generated from feature briefs
- Screenshots captured via Figma MCP tools
- User flows documented with Figma component references
- Direct handoff to Storyteller (forward_message pattern)

### Phase 4: Orchestration & Signals (Week 7-8)

**Files to Create:**
- `.claude/commands/doxee.swarm.md`
- `.specify/memory/sessions/` structure
- `.specify/memory/signals/` tracking
- `.specify/memory/patterns/story-templates.md`
- `.specify/memory/patterns/acceptance-criteria.md`
- `.specify/memory/decisions/_index.md`

**Validation:**
- Single command triggers full multi-agent workflow
- Session logs capture agent interactions
- Signal files populated
- Circuit breaker tested

### Phase 5: Jira Integration & Learning (Week 9+)

**Files to Create:**
- Jira integration for Storyteller agent
- Weekly pattern aggregation script
- Decision log templates

**Validation:**
- Stories sync to Jira
- Pattern insights generated weekly
- Decisions documented

---

## Critical Files to Modify/Create

| File | Action | Purpose |
|------|--------|---------|
| `.specify/memory/constitution.md` | **Edit** | Fill with Doxee-specific principles |
| `.specify/memory/agents/_registry.md` | **Create** | Central agent catalog with traits |
| `.specify/memory/agents/*.md` | **Create** | 5 agent definition files |
| `.specify/memory/context/*.md` | **Create** | 4 shared context files |
| `.specify/memory/signals/` | **Create** | Pattern detection files |
| `.specify/templates/idea-template.md` | **Create** | Idea artifact template |
| `.specify/templates/epic-template.md` | **Create** | Epic artifact template |
| `.specify/templates/story-template.md` | **Create** | Story artifact template |
| `.specify/config/jira-sync.yaml` | **Create** | Jira project configuration |
| `.claude/commands/doxee.*.md` | **Create** | 6 new agent commands |
| `.claude/commands/speckit.idea.md` | **Create** | Create/update idea command |
| `.claude/commands/speckit.epic.md` | **Create** | Create/update epic command |
| `.claude/commands/speckit.story.md` | **Create** | Create/update story command |
| `.claude/commands/speckit.sync.md` | **Create** | Jira sync command |
| `.specify/scripts/migrate-specs.ts` | **Create** | Migration script for existing specs |
| `doxee/specs/ideas/` | **Create** | Hierarchical artifact structure |

---

## Design Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Architecture | Hybrid Supervisor + Swarm | Best of both: central control + direct handoffs |
| Agent orchestration | Claude Code Task tool | Native, no dependencies, already available |
| Memory storage | Markdown in Git | Version controlled, diffable, human-readable |
| Memory model | Three-tier (Hot/Warm/Cold) | Prevents context bloat, enables learning |
| Context isolation | File system coordination | Avoids state passing overhead |
| Artifact structure | Idea → Epic → Story hierarchy | Maps directly to Jira Product Discovery + Software |
| UX prototyping | **Figma MCP tools** | Leverage existing design system, store in story attachments |
| Jira integration | **Bidirectional sync** | Product Discovery (Ideas) + Software (Epics/Stories) |
| Jira project key | **Configurable** | Not hardcoded, set at sync time |
| User personas | **Draft from product docs** | Financial Services, Utilities, Insurance, Telco |
| Model selection | **Per-agent optimization** | Haiku for grunt work, Sonnet for reasoning |
| Failure handling | Circuit breaker + max iterations | Prevents infinite loops |

---

## Verification Plan

1. **Unit Test Each Agent**
   - Invoke each `/doxee.[agent]` command individually
   - Verify outputs match expected format
   - Check handoff tasks created correctly
   - Verify model parameter respected

2. **Integration Test Pipeline**
   - Run `/doxee.swarm` with sample feature
   - Verify full flow: Analyst → Planner → UX Designer + Storyteller → Validator
   - Confirm local story files created with UX screenshots
   - Test feedback loop (intentionally fail validation)

3. **UX Designer Specific**
   - Generate UX specification from feature brief
   - Test Figma MCP screenshot capture
   - Verify screenshot storage in `doxee/prototypes/`
   - Test direct handoff to Storyteller

4. **Signal Tracking**
   - Verify failures.jsonl populated on validation failures
   - Verify loopbacks.jsonl populated on feedback loops
   - Test weekly pattern aggregation

5. **Circuit Breaker**
   - Simulate agent failures
   - Verify circuit opens after threshold
   - Test recovery after timeout

---

## Confirmed Decisions

- **Artifact Structure**: Hierarchical `doxee/specs/ideas/[idea]/epics/[epic]/stories/[story]/` for Jira sync
- **Jira Integration**: Jira Product Discovery (Ideas) + Jira Software (Epics/Stories), bidirectional sync in Phase 5
- **Jira Project Key**: Configurable per-project, not hardcoded
- **Technical Artifacts**: `plan.md` and `research.md` at epic level, tasks embedded in `_story.md`
- **User Personas**: Draft from existing product documentation (Financial Services, Utilities, Insurance, Telco verticals)
- **UX Prototyping**: Use Figma MCP tools - screenshots stored in story `attachments/` folder
- **Model Selection**: Haiku for Analyst/Validator (grunt work), Sonnet for others (reasoning)
- **Context Isolation**: File system coordination to avoid state passing overhead
- **Feedback Loops**: Max 2 iterations before escalation to prevent divergence
- **Migration**: Create script to convert existing `specs/[###-feature]/` to new hierarchy

---

## SpecKit Restructuring: Agentic Skills Architecture

> **Analysis Date**: 2026-02-05
> **Source**: GitHub spec-kit + current `.claude/commands/speckit.*.md` implementation

### Current SpecKit Pain Points

| Issue | Impact | Root Cause |
|-------|--------|------------|
| No shared context | Re-reads artifacts each command | Flat command structure |
| No state persistence | Can't resume workflows | No state management |
| Sequential only | Slow plan + implement | No parallel dispatch |
| Duplicated logic | Path resolution × 9 commands | No shared utilities |
| No background validation | Sync analysis blocks | No async patterns |

### Proposed Consolidated Skill Architecture

Move from 9 scattered command files to a unified skill at `.claude/skills/speckit/`:

```text
.claude/skills/speckit/
├── SKILL.md                    # Skill manifest (auto-discovery)
├── README.md                   # Documentation
│
├── orchestrator/               # Supervisor agent layer
│   ├── workflow.md             # Main workflow orchestration
│   ├── state-machine.md        # State transitions
│   └── handoffs.md             # Phase transition rules
│
├── phases/                     # Phase-specific sub-skills
│   ├── specify/
│   │   ├── SKILL.md            # Sub-skill manifest
│   │   ├── prompt.md           # Core prompt
│   │   └── validators/
│   │       └── spec-quality.md
│   ├── clarify/
│   │   ├── SKILL.md
│   │   └── prompt.md
│   ├── plan/
│   │   ├── SKILL.md
│   │   ├── prompt.md
│   │   └── agents/
│   │       ├── researcher.md   # Phase 0 research agent
│   │       └── designer.md     # Phase 1 design agent
│   ├── tasks/
│   │   ├── SKILL.md
│   │   └── prompt.md
│   └── implement/
│       ├── SKILL.md
│       ├── prompt.md
│       └── agents/
│           ├── story-worker.md # Parallel story implementation
│           └── validator.md    # Background validation
│
├── support/                    # Support sub-skills
│   ├── analyze/
│   ├── checklist/
│   ├── export-issues/
│   └── constitution/
│
├── context/                    # Context management
│   ├── loader.md               # Progressive artifact loading
│   ├── compressor.md           # Context compression rules
│   └── memory.md               # Persistent state handling
│
├── templates/                  # Moved from .specify/
│   └── *.md
│
├── tools/                      # Shared tool definitions
│   ├── artifact-reader.md      # Unified artifact access
│   ├── path-resolver.md        # Feature path resolution
│   ├── git-ops.md              # Git operations
│   └── validation-gates.md     # Quality gate checks
│
└── hooks/                      # Claude Code hooks
    ├── pre-implement.md        # Validate before implementation
    └── post-implement.md       # Run tests after changes
```

### SpecKit Workflow State Machine

```text
INIT → SPECIFYING → CLARIFYING → PLANNING → TASKING → ANALYZING → IMPLEMENTING → COMPLETE
         ↑             ↓            ↓          ↓           ↓
         └─────────────┴────────────┴──────────┴───────────┘
                    (can return to earlier phases)
```

**State Persistence Schema** (`.specify/state/[feature-id].json`):

```json
{
  "featureId": "005-user-auth",
  "currentPhase": "planning",
  "phaseStatus": {
    "specify": "complete",
    "clarify": "skipped",
    "plan": "in_progress",
    "tasks": "pending",
    "implement": "pending"
  },
  "artifacts": {
    "spec": "specs/005-user-auth/spec.md",
    "plan": "specs/005-user-auth/plan.md",
    "tasks": null
  },
  "gateResults": {
    "constitution": "pass",
    "specQuality": "pass"
  },
  "lastUpdated": "2026-02-05T21:00:00Z"
}
```

### Progressive Context Loading Strategy

| Phase | Load | Skip | Rationale |
|-------|------|------|-----------|
| specify | templates only | all artifacts | None exist yet |
| clarify | spec.md | plan, tasks | Only need spec |
| plan | spec.md + constitution | tasks, source | Need full requirements |
| tasks | plan.md + spec (compressed) | research, contracts | Summaries in plan |
| implement | tasks.md (current phase) + source | full spec, plan | Progressive loading |

**Context Compression Rules**:

- **Spec → Tasks**: Keep user story IDs + one-line summaries, remove detailed ACs
- **Plan → Implement**: Keep tech stack + structure, remove rationale
- **Tasks → Workers**: Split by phase, each worker gets Setup + Foundational + One Story

### Parallel Agent Patterns for SpecKit

#### Plan Phase - Dual Agent Dispatch

```text
┌─────────────────────────────────────────┐
│           Supervisor (plan)             │
│                  │                      │
│     ┌────────────┴────────────┐        │
│     ▼                         ▼        │
│ ┌─────────┐             ┌──────────┐   │
│ │Researcher│             │ Designer │   │
│ │ Agent   │             │  Agent   │   │
│ │ (haiku) │             │ (sonnet) │   │
│ └────┬────┘             └────┬─────┘   │
│      │                       │         │
│      ▼                       ▼         │
│ research.md            data-model.md   │
│                        contracts/      │
└─────────────────────────────────────────┘
```

#### Implement Phase - Worker Pool

```text
┌────────────────────────────────────────────────────┐
│              Supervisor (implement)                │
│                      │                             │
│   ┌──────────────────┼──────────────────┐         │
│   ▼                  ▼                  ▼         │
│ ┌────────┐      ┌────────┐        ┌────────┐     │
│ │Worker 1│      │Worker 2│        │Worker N│     │
│ │ US-001 │      │ US-002 │   ...  │ US-00N │     │
│ │(sonnet)│      │(sonnet)│        │(sonnet)│     │
│ └────────┘      └────────┘        └────────┘     │
│                      │                            │
│                      ▼                            │
│            ┌─────────────────┐                    │
│            │Background       │                    │
│            │Validator (haiku)│                    │
│            └─────────────────┘                    │
└────────────────────────────────────────────────────┘
```

### Quality Gates (Shared Tool)

| Gate | Phase | Blocking | Criteria |
|------|-------|----------|----------|
| spec-quality | post-specify | Yes | All checklist items pass |
| constitution | post-plan | Yes | No unjustified violations |
| task-coverage | post-tasks | No | All requirements mapped |
| implementation | post-implement | Yes | Tests pass, no errors |

### Integration with Memory Layer

The SpecKit skill architecture integrates with the Memory Layer:

| SpecKit Component | Memory Layer Component | Integration |
|-------------------|------------------------|-------------|
| `context/loader.md` | `memory/context/` | Loads doxee-platform.md, tech-stack.md |
| `context/memory.md` | `memory/sessions/` | Stores workflow state |
| `tools/validation-gates.md` | `memory/patterns/quality-gates.md` | References DoD patterns |
| `orchestrator/workflow.md` | `workflows/idea-to-story.md` | Shared orchestration patterns |
| `phases/implement/validator.md` | `memory/agents/validator.md` | Same validation logic |

### Key Improvements Over Current State

| Metric | Current | Proposed | Improvement |
|--------|---------|----------|-------------|
| Command files | 9 separate | 1 skill | Single maintenance point |
| Context per phase | Full reload | Progressive | 60% token reduction |
| Plan execution | Sequential | Parallel (2 agents) | 2× faster |
| Implement execution | Sequential stories | Worker pool | 3× faster |
| State persistence | None | JSON per feature | Resume workflows |
| Validation | Sync blocking | Background async | Non-blocking |
| Path resolution | Duplicated × 9 | Shared tool | DRY principle |

### Migration Path

**Phase A (Week 1)**: Create skill structure

- Create `.claude/skills/speckit/SKILL.md`
- Move templates
- Create orchestrator shell

**Phase B (Week 2)**: Migrate commands

- Convert `speckit.*.md` → `phases/*/prompt.md`
- Add sub-skill manifests
- Test individual commands

**Phase C (Week 3)**: Add orchestration

- Implement supervisor pattern
- Add state persistence
- Enable progressive loading

**Phase D (Week 4)**: Enable parallelism

- Implement worker pool for implement
- Add background validators
- Create hooks

**Backward Compatibility**: Old `/speckit.specify` etc. continue working during migration by routing to new structure.

---

## Unified Architecture: Memory Layer + SpecKit Skills

### Combined Directory Structure

```text
.claude/
├── commands/
│   └── doxee.*.md              # Doxee agent commands (Phase 1-5)
│
└── skills/
    └── speckit/                # SpecKit skill (restructured)
        ├── SKILL.md
        ├── orchestrator/
        ├── phases/
        ├── support/
        ├── context/
        ├── templates/
        ├── tools/
        └── hooks/

.specify/
├── memory/                     # Shared memory layer
│   ├── constitution.md
│   ├── agents/                 # Doxee agent definitions
│   ├── context/                # Shared context (warm tier)
│   ├── patterns/               # Learned patterns
│   ├── decisions/              # ADRs
│   ├── signals/                # Pattern detection
│   └── sessions/               # Session logs (hot tier)
│
├── state/                      # NEW: SpecKit workflow state
│   └── [feature-id].json       # Per-feature state persistence
│
├── workflows/                  # Orchestration workflows
│   ├── idea-to-story.md        # Doxee pipeline
│   ├── ux-prototype.md
│   └── speckit-workflow.md     # NEW: SpecKit phase orchestration
│
├── templates/                  # Shared templates (or move to skill)
│   └── *.md
│
└── scripts/
    └── bash/                   # Utility scripts

doxee/
└── specs/
    └── ideas/                  # Hierarchical artifacts
        └── [idea-slug]/
            └── epics/
                └── [epic-slug]/
                    └── stories/
```

### Agent-to-Skill Mapping

| Doxee Agent | SpecKit Skill Phase | Shared Context |
|-------------|---------------------|----------------|
| Analyst | - | `memory/context/market-intelligence.md` |
| Planner | `phases/plan/` (researcher + designer) | `memory/context/tech-stack.md` |
| UX Designer | - | `memory/context/user-personas.md` |
| Storyteller | `phases/specify/` | `memory/patterns/story-templates.md` |
| Validator | `phases/implement/validator.md` | `memory/patterns/quality-gates.md` |

### Token Optimization Summary

| Component | Strategy | Savings |
|-----------|----------|---------|
| SpecKit phases | Progressive loading | 60% |
| Doxee agents | File system coordination | 40% |
| Shared context | Three-tier memory | 50% |
| Validation | Background async | 30% latency |
| Implementation | Worker pool parallelism | 3× throughput |
