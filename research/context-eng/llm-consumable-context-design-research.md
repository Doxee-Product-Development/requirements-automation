# Designing LLM-Consumable Reference Documents and Project Context Files

**Research Report: Best Practices 2024-2025**
**Date:** February 6, 2026
**Scope:** AI-native context file patterns, RAG optimization, constitutional AI design, emerging frameworks

---

## Table of Contents

1. [AI-Native Project Context File Patterns](#1-ai-native-project-context-file-patterns)
2. [RAG and Context Window Optimization](#2-rag-and-context-window-optimization)
3. [Constitutional AI Context Design](#3-constitutional-ai-context-design)
4. [Emerging AI-Native Product Ops Frameworks](#4-emerging-ai-native-product-ops-frameworks)
5. [Cross-Cutting Findings and Synthesis](#5-cross-cutting-findings-and-synthesis)

---

## 1. AI-Native Project Context File Patterns

The AI coding assistant ecosystem has converged on a common pattern: a markdown file in the project root that provides persistent instructions to the AI agent. However, the implementations differ significantly in structure, scoping mechanisms, and loading strategies.

### 1.1 Cursor: `.cursor/rules/` Directory

**Status:** `.cursorrules` (root file) is deprecated. The current standard is `.cursor/rules/` directory with individual markdown files.

**Source:** Cursor official documentation (cursor.com/docs/context/rules)

#### Rule Types

Cursor supports four distinct rule categories:

| Type | Storage | Scope |
|------|---------|-------|
| **Project Rules** | `.cursor/rules/*.md` or `.cursor/rules/*.mdc` | Version-controlled, per-project |
| **User Rules** | Cursor Settings UI | Global, all projects |
| **Team Rules** | Dashboard (Team/Enterprise) | Organization-wide |
| **AGENTS.md** | Project root | Simple markdown alternative |

#### Rule Application Modes

Rules use YAML frontmatter to control when they activate:

| Application Type | Behavior |
|-----------------|----------|
| **Always Apply** | Injected into every chat session |
| **Apply Intelligently** | Agent decides based on the `description` field |
| **Apply to Specific Files** | Activated when file matches `globs` patterns |
| **Apply Manually** | Only via explicit `@`-mention in chat |

#### File Anatomy

```markdown
---
description: "REST API design conventions for our services"
alwaysApply: false
globs: ["src/api/**/*.ts"]
---

# API Conventions

- Use kebab-case for URL paths
- Use camelCase for JSON properties
- Always include pagination for list endpoints
```

The `.mdc` extension enables frontmatter metadata. Standard `.md` files are also supported.

#### Community-Converged Patterns

From the `awesome-cursorrules` community repository (600+ examples):

1. **Technology stack definition** dominates -- most rules specify exact frameworks (Next.js + React + TypeScript + Tailwind is the most common combination)
2. **Specialized rules per tech stack** significantly outnumber generic guidelines
3. **Granular, context-specific instructions** prove more valuable than broad principles
4. **Anti-patterns explicitly called out** by Cursor docs:
   - Do NOT duplicate entire style guides (use linters instead)
   - Do NOT document every command (the agent already knows common tools)
   - Do NOT cover rare edge cases
   - Do NOT replicate codebase documentation

#### Key Design Principle

> "Start simple. Add rules only when you notice Agent making the same mistake repeatedly."
> -- Cursor documentation

**Recommended limit:** Keep individual rule files under 500 lines. Split large rules into composable pieces. Reference files rather than copying contents.

---

### 1.2 Claude Code: `CLAUDE.md`

**Source:** Anthropic official documentation (code.claude.com/docs/en/memory, code.claude.com/docs/en/best-practices)

Claude Code has the most mature hierarchical memory system among AI coding tools.

#### Memory Hierarchy (Precedence Order)

| Memory Type | Location | Purpose | Shared With |
|-------------|----------|---------|-------------|
| Managed Policy | OS-level paths (`/Library/Application Support/ClaudeCode/CLAUDE.md` on macOS) | Organization-wide IT/DevOps instructions | All users |
| Project Memory | `./CLAUDE.md` or `./.claude/CLAUDE.md` | Team-shared project instructions | Team via source control |
| Project Rules | `./.claude/rules/*.md` | Modular, topic-specific rules | Team via source control |
| User Memory | `~/.claude/CLAUDE.md` | Personal preferences for all projects | Just you |
| Local Project Memory | `./CLAUDE.local.md` | Personal project-specific preferences (auto-gitignored) | Just you |

#### Recursive Discovery

Claude Code reads `CLAUDE.md` files recursively -- starting from the current working directory, it walks up to the root, loading every `CLAUDE.md` and `CLAUDE.local.md` it finds. Child directory `CLAUDE.md` files are loaded on-demand when Claude works with files in those subtrees.

#### Import Syntax

CLAUDE.md supports file imports using `@path/to/file` syntax:

```markdown
See @README.md for project overview and @package.json for available npm commands.

# Additional Instructions
- Git workflow: @docs/git-instructions.md
- Personal overrides: @~/.claude/my-project-instructions.md
```

Imports resolve relative to the file containing the import. Max recursion depth is 5 hops.

#### Path-Specific Rules

`.claude/rules/*.md` files support YAML frontmatter with glob patterns:

```markdown
---
paths:
  - "src/api/**/*.ts"
  - "lib/**/*.ts"
---

# API Development Rules
- All API endpoints must include input validation
- Use the standard error response format
```

Rules without a `paths` field are loaded unconditionally.

#### Modular Organization Pattern

```
.claude/
  CLAUDE.md              # Main project instructions
  rules/
    frontend/
      react.md           # React-specific guidelines
      styles.md          # CSS/styling conventions
    backend/
      api.md             # API design rules
      database.md        # Database conventions
    general.md           # Universal project rules
```

#### Skills System

Beyond static context, Claude Code supports `.claude/skills/` for domain knowledge and reusable workflows:

```markdown
---
name: fix-issue
description: Fix a GitHub issue
disable-model-invocation: true
---

Analyze and fix the GitHub issue: $ARGUMENTS.

1. Use `gh issue view` to get the issue details
2. Understand the problem described in the issue
3. Search the codebase for relevant files
4. Implement the necessary changes
5. Write and run tests to verify the fix
6. Create a descriptive commit message
7. Push and create a PR
```

#### Effective CLAUDE.md Conventions (from Anthropic's Best Practices)

**Include:**
- Bash commands Claude cannot guess
- Code style rules that differ from defaults
- Testing instructions and preferred test runners
- Repository etiquette (branch naming, PR conventions)
- Architectural decisions specific to your project
- Developer environment quirks (required env vars)
- Common gotchas or non-obvious behaviors

**Exclude:**
- Anything Claude can figure out by reading code
- Standard language conventions Claude already knows
- Detailed API documentation (link to docs instead)
- Information that changes frequently
- Long explanations or tutorials
- File-by-file descriptions of the codebase
- Self-evident practices like "write clean code"

**Critical insight from Anthropic:**
> "If Claude keeps doing something you don't want despite having a rule against it, the file is probably too long and the rule is getting lost. If Claude asks questions answered in CLAUDE.md, the phrasing might be ambiguous. Treat CLAUDE.md like code: review it when things go wrong, prune it regularly, and test changes by observing whether Claude's behavior actually shifts."

**Emphasis mechanism:** Add "IMPORTANT" or "YOU MUST" to improve adherence for critical rules.

---

### 1.3 GitHub Copilot: Custom Instructions

**Source:** GitHub official documentation (docs.github.com)

GitHub Copilot supports three types of repository custom instructions:

#### Repository-Wide Instructions

File: `.github/copilot-instructions.md`

Written in natural language markdown. No required structure. Whitespace between instructions is ignored.

GitHub provides an official prompt for auto-generating this file via Copilot Coding Agent. The recommended structure from that prompt covers:

1. **Repository summary** -- what it does, languages, frameworks
2. **Build instructions** -- bootstrap, build, test, lint commands with exact steps
3. **Project layout** -- architecture, key directories, config file locations
4. **Validation steps** -- CI/CD workflows, pre-commit checks

#### Path-Specific Instructions

Files: `.github/instructions/*.instructions.md`

```markdown
---
applyTo: "src/api/**/*.ts"
excludeAgent: "code-review"  # Optional: exclude from specific agents
---

# API Development Rules
- All endpoints must include input validation
- Use standard error response format
```

Supports glob patterns in `applyTo` frontmatter. Multiple patterns can be comma-separated.

#### Agent Instructions (AGENTS.md)

GitHub Copilot also supports `AGENTS.md` files stored anywhere in the repository. The nearest `AGENTS.md` in the directory tree takes precedence. Additionally supports `CLAUDE.md` or `GEMINI.md` files in the project root.

#### Priority Hierarchy

1. Personal instructions (highest)
2. Repository instructions
3. Organization instructions (lowest)

All relevant instruction sets are provided to Copilot simultaneously, with the hierarchy determining conflict resolution.

---

### 1.4 Devin (Cognition): Knowledge System

**Source:** Devin official documentation (docs.devin.ai)

Devin uses a fundamentally different approach: a **trigger-based knowledge retrieval** system rather than static file loading.

#### Knowledge Architecture

Knowledge in Devin consists of:
- **Trigger Description:** A phrase that determines when the knowledge is recalled
- **Content:** The actual instructions (a handful of sentences)
- **Pinning:** Controls scope -- no repo, specific repo, or all repos

Key behaviors:
- Devin **auto-generates** repo knowledge from READMEs, file structure, and code contents
- Knowledge is **retrieved based on relevance** to the current task, not loaded all at once
- Devin **auto-imports** from: `.rules`, `.mdc`, `.cursorrules`, `.windsurf`, `CLAUDE.md`, and `AGENTS.md`
- Devin **suggests knowledge** based on user feedback in chat sessions

#### AGENTS.md Support

Devin treats AGENTS.md as its primary static context file:

```markdown
# AGENTS.md

## Setup Commands
- Install dependencies: `npm install`
- Start development server: `npm run dev`
- Run tests: `npm test`

## Code Style
- Use TypeScript strict mode
- Prefer functional components in React
- Follow conventional commit format

## Testing Guidelines
- Write unit tests for all new functions
- Use Jest for testing framework
- Aim for >80% code coverage

## Project Structure
- `/src` - Main application code
- `/tests` - Test files
- `/docs` - Documentation

## Development Workflow
- Create feature branches from `main`
- Use pull requests for code review
- Squash commits before merging
```

#### Best Practices from Cognition

1. **Keep knowledge items small and specific** -- one workflow or action per item
2. **Make trigger descriptions highly relevant** -- specific phrases improve retrieval
3. **Review auto-generated knowledge** for completeness and accuracy
4. **Pin knowledge appropriately** -- all-repos for universal rules, specific-repo for contextual rules
5. **Split large instructions** into multiple knowledge items -- Devin retrieves multiple items per session

---

### 1.5 Windsurf (Codeium): Memories and Rules

**Source:** Windsurf documentation sidebar navigation (docs.windsurf.com)

Windsurf supports:
- **Global Rules:** User-level settings applied to all projects
- **Workspace Rules:** `.windsurfrules` file in project root (similar to `.cursorrules`)
- **AGENTS.md:** Standard agent instructions file
- **Memories:** Persistent facts Windsurf learns during sessions

Windsurf's Cascade feature maintains "memories" -- persistent facts about the project that survive across sessions. These are automatically learned from interactions and can be manually managed.

The tool is evolving toward supporting the cross-tool `AGENTS.md` standard alongside its native `.windsurfrules` format.

---

### 1.6 Aider: CONVENTIONS.md

**Source:** Aider official documentation (aider.chat/docs/usage/conventions.html)

Aider takes the simplest approach: a plain markdown file loaded as read-only context.

#### Usage Pattern

```bash
# Load as read-only (recommended -- enables prompt caching)
aider --read CONVENTIONS.md

# Or add during session
/read CONVENTIONS.md
```

#### Configuration for Auto-Loading

In `.aider.conf.yml`:
```yaml
# Single file
read: CONVENTIONS.md

# Multiple files
read: [CONVENTIONS.md, anotherfile.txt]
```

#### Example CONVENTIONS.md

```markdown
- Prefer httpx over requests for making HTTP requests.
- Use types everywhere possible.
- Use pytest for all test files.
- Follow Google-style docstrings.
```

#### Key Insight

Aider's approach demonstrates that **simpler is often better**. The read-only flag means the file is:
1. Never modified by the AI
2. Eligible for prompt caching (reducing costs)
3. Always loaded before any task

Community-contributed conventions are shared via a dedicated `aider-conventions` repository.

---

### 1.7 OpenAI Codex: AGENTS.md

**Source:** OpenAI Codex repository (github.com/openai/codex)

OpenAI's Codex CLI uses `AGENTS.md` as its project context file. The OpenAI example from the Codex repository itself demonstrates an advanced, heavily detailed pattern:

```markdown
# Rust/codex-rs

- Crate names are prefixed with `codex-`
- When using format! and you can inline variables into {}, always do that.
- Install any commands the repo relies on before running instructions here.
- Never add or modify any code related to `CODEX_SANDBOX_NETWORK_DISABLED_ENV_VAR`
- Always collapse if statements per clippy rules
- Always inline format! args when possible
- Use method references over closures when possible
- When possible, make `match` statements exhaustive and avoid wildcard arms.

Run `just fmt` automatically after you have finished making Rust code changes;
do not ask for approval to run it. Additionally, run the tests:

1. Run the test for the specific project that was changed.
2. Once those pass, if any changes were made in common, core, or protocol,
   run the complete test suite with `cargo test --all-features`.
```

#### Notable Patterns from OpenAI's AGENTS.md

1. **Imperative instructions** -- "Always do X", "Never do Y", "Run Z automatically"
2. **Conditional behaviors** -- "if changes were made in common/core, THEN run full suite"
3. **Explicit tool usage** -- exact commands to run, with flags
4. **Safety boundaries** -- "do not ask for approval" vs "do ask the user before running"
5. **Convention references** -- links to external style guides (clippy rules)
6. **Detailed subsections** for different domains (TUI styling, test conventions, API patterns)

This is one of the most detailed public AGENTS.md files and demonstrates the pattern of treating the context file as a comprehensive "new employee onboarding document."

---

### 1.8 Convergence: The Cross-Tool Standard

A clear convergence is emerging across all tools:

| Feature | Cursor | Claude Code | Copilot | Devin | Windsurf | Aider | Codex |
|---------|--------|-------------|---------|-------|----------|-------|-------|
| Root context file | .cursor/rules/ | CLAUDE.md | copilot-instructions.md | AGENTS.md | .windsurfrules | CONVENTIONS.md | AGENTS.md |
| AGENTS.md support | Yes | No (uses CLAUDE.md) | Yes | Yes | Yes | No | Yes |
| Path-specific rules | Yes (globs) | Yes (paths) | Yes (applyTo) | No | No | No | No |
| Hierarchical loading | User + Project | Managed + User + Project + Local | Org + Repo + Personal | Trigger-based retrieval | Global + Workspace | Config file | Directory tree |
| Frontmatter metadata | Yes (.mdc) | Yes (paths) | Yes (applyTo) | N/A | No | No | No |
| Auto-generation | No | /init command | Copilot agent prompt | Auto from READMEs | Memories | No | No |
| Import/reference | No | @path/to/file | No | No | No | --read flag | No |

**AGENTS.md** is emerging as the closest thing to a cross-tool standard. Devin, Windsurf, Cursor, and GitHub Copilot all support it. Claude Code uses CLAUDE.md but shares the same philosophy. The pattern is converging toward: **a markdown file in the project root with sections for setup, style, testing, structure, and workflow.**

---

## 2. RAG and Context Window Optimization

### 2.1 The "Lost in the Middle" Problem

**Source:** Liu et al., "Lost in the Middle: How Language Models Use Long Contexts" (TACL 2023, arXiv:2307.03172)

The foundational research finding that shapes all context design:

> "Performance is often highest when relevant information occurs at the **beginning or end** of the input context, and significantly degrades when models must access relevant information in the **middle** of long contexts."

This U-shaped attention curve has three practical implications:

1. **Front-load critical instructions** -- put the most important rules at the top
2. **Repeat key constraints at the end** -- leverage the recency effect
3. **Minimize mid-document noise** -- every token in the middle competes for attention

### 2.2 Anthropic's Official Long Context Guidance

**Source:** Anthropic prompt engineering documentation

#### Document Positioning

> "Put longform data at the top. Place your long documents and inputs (~20K+ tokens) near the top of your prompt, above your query, instructions, and examples. This can significantly improve Claude's performance across all models."

> "Queries at the end can improve response quality by up to 30% in tests, especially with complex, multi-document inputs."

**Optimal layout:**
```
[LONG REFERENCE DOCUMENTS]   <-- Top: bulk data
[INSTRUCTIONS]                <-- Middle: rules and constraints
[SPECIFIC QUERY/TASK]         <-- Bottom: what to do now
```

#### Multi-Document Structure

Anthropic recommends XML tags for multi-document contexts:

```xml
<documents>
  <document index="1">
    <source>annual_report_2023.pdf</source>
    <document_content>
      {{ANNUAL_REPORT}}
    </document_content>
  </document>
  <document index="2">
    <source>competitor_analysis_q2.xlsx</source>
    <document_content>
      {{COMPETITOR_ANALYSIS}}
    </document_content>
  </document>
</documents>

Analyze the annual report and competitor analysis.
Identify strategic advantages and recommend Q3 focus areas.
```

#### Quote Grounding

For long documents, instruct the model to quote relevant sections first:

> "Ask Claude to quote relevant parts of the documents first before carrying out its task. This helps Claude cut through the 'noise' of the rest of the document's contents."

### 2.3 Structured Delimiters: XML vs Markdown vs YAML

Based on research and documentation from Anthropic, the delimiter effectiveness hierarchy is:

#### XML Tags (Highest Reliability for Claude)

**Source:** Anthropic prompt engineering documentation

> "XML tags can be a game-changer. They help Claude parse your prompts more accurately, leading to higher-quality outputs."

Benefits:
- **Clarity:** Clearly separate different parts of a prompt
- **Accuracy:** Reduce errors caused by misinterpreting prompt sections
- **Flexibility:** Easy to add, remove, or modify sections
- **Parseability:** Enable programmatic extraction of response parts

Best practices:
- Be consistent with tag names throughout prompts
- Nest tags for hierarchical content: `<outer><inner></inner></outer>`
- Reference tags by name in instructions: "Using the contract in `<contract>` tags..."
- No canonical "best" tag names -- use names that make semantic sense

#### Markdown Headers (Good for Human-Readable Documents)

Markdown headers work well for:
- Project context files (CLAUDE.md, AGENTS.md)
- Documents that need to be both human-readable and AI-consumable
- Hierarchical organization with `#`, `##`, `###` levels

Limitations:
- Less precise boundary definition than XML
- Ambiguous nesting (is this content under the H2 or the H3?)
- Cannot be used for programmatic extraction

#### YAML Frontmatter (Good for Metadata Only)

Works well for:
- File-level metadata (paths, descriptions, flags)
- Configuration that tools parse before sending to LLM
- Cursor `.mdc` files, Copilot `.instructions.md` files

Not suitable for:
- Inline content structuring
- Complex nested data within instructions

### 2.4 Information Compaction Techniques

#### Bullet Points Over Prose

Every tool's documentation and community converges on this: **bullet points and short declarative statements maximize semantic density per token.**

Compare:
```
# Bad (verbose prose)
When you are writing code for this project, you should make sure that you
always use ES modules syntax, which means using import and export statements
rather than the CommonJS require() function. Additionally, whenever it is
possible to destructure imports, you should prefer to do so.

# Good (compact bullets)
- Use ES modules (import/export), not CommonJS (require)
- Destructure imports when possible: `import { foo } from 'bar'`
```

The compact version is approximately 60% fewer tokens with identical semantic content.

#### Code Examples Over Descriptions

```
# Bad
The function should accept a string parameter and return a boolean

# Good
validate(email: string): boolean
```

#### Reference Rather Than Include

From Cursor's documentation:
> "Reference files rather than copying contents."

From Claude Code:
> "Link to docs instead of including detailed API documentation."

Pattern: Use `@path/to/file` (Claude Code) or "see `src/patterns/example.ts` for reference" instead of inlining large code blocks.

### 2.5 Progressive/Layered Loading Patterns

The most sophisticated tools implement tiered context loading:

#### Claude Code's Three-Tier System

1. **Always loaded:** `CLAUDE.md` files in the directory hierarchy (project root, parent dirs, user home)
2. **Conditionally loaded:** `.claude/rules/*.md` with `paths` frontmatter -- loaded only when matching files are in scope
3. **On-demand:** Child directory `CLAUDE.md` files -- loaded only when Claude reads files in those subdirectories
4. **Imported:** `@path` references -- resolved recursively up to 5 levels

#### Cursor's Application-Type System

1. **Always Apply:** Every session
2. **Apply Intelligently:** Agent decides based on description field
3. **Apply to Specific Files:** File glob matching
4. **Apply Manually:** Only when explicitly invoked

#### Devin's Trigger-Based Retrieval

1. **Pinned to all repos:** Always loaded
2. **Pinned to specific repo:** Loaded when working in that repo
3. **Trigger-based:** Retrieved when current task matches trigger description

#### Pattern: Pyramid of Specificity

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

**Key insight:** The most effective systems load the least amount of context needed for the current task, not everything at once.

### 2.6 Context Window Management Strategies

#### Auto-Compaction (Claude Code)

When approaching context limits, Claude Code automatically compacts conversation history:
- Preserves important code, file states, and key decisions
- Summarizes less critical conversation
- Users can customize: `/compact Focus on the API changes`
- CLAUDE.md can include: "When compacting, always preserve the full list of modified files"

#### Subagent Delegation (Claude Code)

> "Since context is your fundamental constraint, subagents are one of the most powerful tools available."

Subagents run in separate context windows and report back summaries, preventing investigation from consuming the main context.

#### Session Hygiene

From Anthropic's best practices:
- `/clear` between unrelated tasks
- After two failed corrections, start fresh with a better prompt
- "A clean session with a better prompt almost always outperforms a long session with accumulated corrections"

---

## 3. Constitutional AI Context Design

### 3.1 Imperative vs. Declarative Instruction Styles

Based on analysis of effective context files across all tools, two instruction styles emerge:

#### Imperative Style (Commands)

```markdown
- ALWAYS run `npm install` before building
- NEVER use `any` type in TypeScript
- Run `just fmt` automatically after making code changes; do not ask for approval
```

**Effectiveness:** High for hard constraints. The model treats these as non-negotiable rules.

**When to use:** Safety boundaries, formatting requirements, required verification steps.

#### Declarative Style (Descriptions)

```markdown
- This project uses ES modules (import/export), not CommonJS
- The API follows RESTful conventions with kebab-case URLs
- Tests use Jest with react-testing-library
```

**Effectiveness:** Good for context-setting. The model infers appropriate behavior.

**When to use:** Architecture descriptions, technology choices, pattern documentation.

#### Hybrid Style (Most Effective)

The best context files combine both:

```markdown
# Architecture (declarative)
This is a Next.js 14 app with App Router. The API layer uses tRPC.

# Code Style (imperative)
- ALWAYS use `satisfies` over `as` for type assertions
- NEVER mutate function parameters

# Workflow (imperative with context)
- Run `pnpm test` before committing (the pre-commit hook validates this)
```

### 3.2 Hard Constraints vs. Soft Preferences

#### Marking Hard Constraints

Patterns that work across all LLMs:

```markdown
# Using emphasis words
IMPORTANT: Never commit .env files
YOU MUST run tests before creating a PR
ALWAYS use the standard error format

# Using explicit constraint markers
## Hard Constraints (non-negotiable)
- [ ] All API responses must include request_id
- [ ] Database migrations must be reversible

## Preferences (follow unless there's a good reason not to)
- Prefer functional components over class components
- Use named exports over default exports
```

From Claude Code's documentation:
> "You can tune instructions by adding emphasis (e.g., 'IMPORTANT' or 'YOU MUST') to improve adherence."

#### The OpenAI Codex Pattern

OpenAI's own AGENTS.md demonstrates explicit permission scoping:

```markdown
# Automatic (no approval needed)
Run `just fmt` automatically after making code changes;
do not ask for approval to run it.

# Requires approval
Do ask the user before running the complete test suite.

# Forbidden
Never add or modify any code related to CODEX_SANDBOX_NETWORK_DISABLED_ENV_VAR.
```

This three-tier permission model (automatic / requires-approval / forbidden) is a powerful pattern for agentic systems.

### 3.3 Cross-Referencing Patterns

#### Claude Code Import Chain

```markdown
# CLAUDE.md
See @README.md for project overview
See @package.json for available npm commands
- Git workflow: @docs/git-instructions.md
- API conventions: @docs/api-standards.md
```

Max depth: 5 recursive hops. Files resolve relative to the importing file.

#### Copilot Tiered Files

```
.github/
  copilot-instructions.md          # Global project context
  instructions/
    api.instructions.md            # API-specific (applyTo: "src/api/**")
    frontend.instructions.md       # Frontend-specific (applyTo: "src/ui/**")
    testing.instructions.md        # Test-specific (applyTo: "**/*.test.*")
```

#### Cursor Composable Rules

```
.cursor/rules/
  always-on.md          # alwaysApply: true
  react-patterns.md     # globs: ["src/**/*.tsx"]
  api-design.md         # globs: ["src/api/**"]
  security.md           # description: "Security review rules"
```

### 3.4 Token Budget Management

#### The Context Budget Hierarchy

Based on patterns from Claude Code and Cursor:

1. **System prompt / tool instructions** (fixed cost, highest priority)
2. **Always-on rules** (fixed cost per session)
3. **Conditional rules** (loaded based on file context)
4. **Conversation history** (grows over session, compacted when full)
5. **File contents** (loaded on demand)
6. **Search results** (loaded on demand)

#### Practical Budget Guidelines

From Claude Code best practices:
- Track context usage continuously with a custom status line
- Use `/clear` between unrelated tasks
- Use subagents for investigation to avoid consuming main context
- Keep CLAUDE.md concise -- "for each line, ask: would removing this cause Claude to make mistakes? If not, cut it"

From Cursor:
- Keep individual rule files under 500 lines
- Split large rules into composable pieces

### 3.5 Multi-Level Conflict Resolution

When multiple context sources disagree, tools use implicit priority hierarchies:

**Claude Code:** Managed Policy > Project Memory > Project Rules > User Memory > Local Project Memory
(Higher in hierarchy takes precedence; loaded first)

**GitHub Copilot:** Personal > Repository > Organization
(Personal overrides repository overrides organization)

**Cursor:** User Rules provide baseline; Project Rules override for specific contexts

**Devin:** Pinned-to-all > Pinned-to-repo > Trigger-based retrieval

The consistent pattern: **more specific context overrides more general context**, with organizational/managed policies as the exception (they always win).

---

## 4. Emerging AI-Native Product Ops Frameworks

### 4.1 Factory.ai: Agent-Native Software Development

**Source:** factory.ai

Factory.ai describes itself as providing "Agent-Native Software Development" with "Droids" -- autonomous agents that embed into existing workflows.

#### Architecture

Factory's approach is tool-agnostic and interface-agnostic:
- **Terminal/IDE:** VS Code, JetBrains, Vim, Zed
- **Web Browser:** Direct web interface
- **CLI:** Scriptable for CI/CD, migrations
- **Slack/Teams:** Natural language task delegation
- **Project Manager:** Auto-triggers from issue assignment (Linear, Jira)

#### Key Concepts

1. **Skills:** Domain-specific capabilities (similar to Claude Code's skills)
2. **Custom Droids (Subagents):** Specialized agents for specific domains
3. **Hooks:** Automated triggers at specific workflow points
4. **Plugins:** Bundled extensions
5. **Mixed Models:** Different models for different tasks
6. **Agent Readiness:** A framework for measuring how well a codebase supports autonomous development, evaluating repositories across eight technical pillars and five maturity levels

#### "Agent Readiness" Framework

Factory introduced the concept of **Agent Readiness** -- evaluating how well a codebase supports autonomous AI development. This is a significant emerging pattern: treating the codebase itself as an interface for AI agents, and measuring/improving its "agent-friendliness."

The concept includes:
- Repository evaluation across technical pillars
- Maturity levels for agent adoption
- Specific recommendations for improving agent effectiveness

### 4.2 Harper Reed's Spec-Plan-Execute Workflow

**Source:** harper.blog/2025/02/16/my-llm-codegen-workflow-atm/

A widely-shared practitioner workflow that demonstrates the "spec-driven development" pattern:

#### Three-Phase Process

**Phase 1: Idea Honing (Conversational LLM)**

```
Ask me one question at a time so we can develop a thorough,
step-by-step spec for this idea. Each question should build on
my previous answers, and our end goal is to have a detailed
specification I can hand off to a developer. Let's do this
iteratively and dig into every relevant detail. Remember,
only one question at a time.

Here's the idea: <IDEA>
```

Output: `spec.md`

**Phase 2: Planning (Reasoning Model)**

```
Draft a detailed, step-by-step blueprint for building this project.
Then break it down into small, iterative chunks that build on each
other. Go another round to break into small steps. Review and ensure
steps are small enough for safe implementation with strong testing,
but big enough to move the project forward.

From here, provide a series of prompts for a code-generation LLM
that will implement each step in a test-driven manner.
```

Output: `prompt_plan.md` + `todo.md`

**Phase 3: Execution (Code-Generation LLM)**

Feed prompts sequentially to aider, Claude, or Cursor. Check off `todo.md` items as completed.

#### Key Pattern: Discrete Loops

> "Brainstorm spec, then plan a plan, then execute using LLM codegen. Discrete loops."

This separation of concerns -- using different models for different phases, with human review between phases -- mirrors the Speckit architecture and is emerging as a best practice.

### 4.3 Anthropic's Building Effective Agents Framework

**Source:** Anthropic engineering blog, December 2024

This is the most authoritative framework for agentic system design, published by Anthropic based on work with dozens of production teams.

#### Core Architectural Patterns

1. **Prompt Chaining:** Task decomposed into sequential steps, each LLM call processes previous output
2. **Routing:** Input classified and directed to specialized handlers
3. **Parallelization:** Sectioning (parallel subtasks) or Voting (multiple perspectives)
4. **Orchestrator-Workers:** Central LLM dynamically delegates to worker LLMs
5. **Evaluator-Optimizer:** Generator + Evaluator in a feedback loop

#### Three Core Principles

1. **Maintain simplicity** in agent design
2. **Prioritize transparency** by showing planning steps
3. **Carefully craft the Agent-Computer Interface (ACI)** through thorough tool documentation

#### Key Insight: ACI Over Prompt Engineering

> "We actually spent more time optimizing our tools than the overall prompt."

The "Agent-Computer Interface" concept -- treating tool definitions with the same care as Human-Computer Interfaces -- is a fundamental shift. Tool documentation, parameter naming, and error handling matter more than clever prompting.

### 4.4 The "Requirements as Code" Movement

Several patterns are emerging around treating product requirements as machine-readable artifacts:

#### Gherkin / BDD Specifications

```gherkin
Feature: User Authentication
  Scenario: Successful login
    Given a registered user with email "user@example.com"
    When they submit valid credentials
    Then they receive a session token
    And are redirected to the dashboard
```

This format is both human-readable and machine-executable, making it ideal for AI consumption.

#### Structured Spec Templates

The pattern of using markdown templates with specific sections (as in Speckit, Harper Reed's workflow, and Factory's approach) is converging on:

1. **Problem statement** (what and why)
2. **User stories** with acceptance criteria
3. **Technical constraints** (architecture, APIs, data model)
4. **Edge cases** and error handling
5. **Test plan** with specific scenarios
6. **Non-functional requirements** (performance, security)

#### Machine-Readable Metadata

Adding structured metadata to human-readable documents:

```markdown
---
feature: user-authentication
priority: P1
status: approved
dependencies: [user-service, session-store]
estimated_tokens: 5000
---
```

### 4.5 Linear AI and Issue Management

Linear has integrated AI features that auto-generate issue descriptions, suggest labels, and create sub-issues. The pattern relevant here is **issue templates that serve both humans and AI agents** -- structured enough for machine parsing but readable enough for human review.

### 4.6 Repomix and Context Packing

The emergence of tools like **repomix** (referenced by Harper Reed) represents a pattern of "context packing" -- bundling an entire codebase into a single file optimized for LLM consumption. This is relevant for non-interactive use cases (pasting into Claude.ai, ChatGPT) and demonstrates demand for codebase-to-context transformation tools.

---

## 5. Cross-Cutting Findings and Synthesis

### 5.1 The Seven Universal Patterns

Across all tools, frameworks, and practices researched, seven universal patterns emerge:

#### Pattern 1: Markdown as the Universal Format

Every tool uses markdown. Not JSON, not YAML, not custom formats. Markdown is the lingua franca of AI context files because:
- LLMs were trained extensively on markdown
- It is human-readable and editable
- It supports hierarchical structure via headers
- It supports code blocks for examples
- It can embed YAML frontmatter for metadata

#### Pattern 2: Hierarchical Override (Specific Beats General)

All tools implement some form of context hierarchy where more specific rules override more general ones:
- Organization < Project < Path-specific < Session-specific
- The one exception: managed/security policies always win

#### Pattern 3: Conditional Loading (Load Less, Not More)

The trend is away from "load everything" toward "load what's relevant":
- Path-based rules (Cursor, Claude Code, Copilot)
- Trigger-based retrieval (Devin)
- On-demand loading (Claude Code child directories)
- Application-type control (Cursor's four modes)

#### Pattern 4: Imperative for Constraints, Declarative for Context

- **Hard rules:** Use imperative commands -- "ALWAYS", "NEVER", "YOU MUST"
- **Soft context:** Use declarative descriptions -- "This project uses...", "The API follows..."
- **Permissions:** Use explicit three-tier -- automatic / requires-approval / forbidden

#### Pattern 5: Concrete Over Abstract

Every best practice guide converges on: **specific, concrete instructions outperform abstract guidance.**

| Abstract (weak) | Concrete (strong) |
|-----------------|-------------------|
| "Write clean code" | "Use 2-space indentation, max 100 chars per line" |
| "Test thoroughly" | "Run `pytest -x` after changes; aim for >80% coverage" |
| "Follow best practices" | "Use `satisfies` over `as` for type assertions" |

#### Pattern 6: Separation of Phases

The spec-plan-execute separation appears in:
- Harper Reed's workflow (spec.md -> prompt_plan.md -> execution)
- Anthropic's building effective agents (prompt chaining, orchestrator-workers)
- Speckit's own workflow (specify -> plan -> tasks -> implement)
- Claude Code's recommended workflow (Plan Mode -> Normal Mode)

This is converging as a fundamental best practice: **use different models and contexts for different phases.**

#### Pattern 7: Treat Context Files as Code

Emerging universal practice:
- **Version control** context files alongside code
- **Review and prune** regularly (treat like code review)
- **Test effectiveness** by observing behavior changes
- **Iterate based on failure** -- add rules only when you see repeated mistakes

### 5.2 Optimal Document Structure for LLM Consumption

Based on all research, the optimal structure for an LLM-consumable reference document follows this template:

```markdown
# [Document Title]

## Critical Rules (MUST follow)
- [Imperative constraints -- highest priority, fewest items]
- NEVER [forbidden action]
- ALWAYS [required action]

## Project Context
[Declarative description of architecture, stack, and conventions]

## Commands
- Build: `command here`
- Test: `command here`
- Lint: `command here`

## Code Patterns
[Short code examples showing preferred patterns]

## Directory Structure
[Key paths and what lives where]

## Workflow
[Steps for common operations: branching, PR, deployment]

## [Domain-Specific Sections]
[Only when needed -- keep focused]
```

Key structural principles:
1. **Most important rules first** (front-loading for the primacy effect)
2. **Imperative constraints before declarative context** (commands are more reliably followed)
3. **Code examples inline** (models parse code blocks with high fidelity)
4. **Bullet points over prose** (higher semantic density per token)
5. **Flat hierarchy preferred** (2 levels of headers max for most documents)
6. **Total length: under 500 lines** per file (split into multiple files if longer)

### 5.3 Recommendations for Speckit

Based on this research, specific recommendations for the Speckit framework:

1. **Add AGENTS.md support:** Generate an AGENTS.md file alongside CLAUDE.md for cross-tool compatibility. Devin, Copilot, Windsurf, and Cursor all read it.

2. **Implement path-specific rules:** Use `.claude/rules/` with `paths` frontmatter for domain-specific instructions (e.g., separate rules for spec generation vs. code implementation).

3. **Restructure constitution.md:** Follow the imperative-first, declarative-second pattern. Front-load hard constraints. Use emphasis markers ("IMPORTANT", "MUST") for non-negotiable rules.

4. **Add `@import` references:** Use Claude Code's `@path/to/file` import syntax in CLAUDE.md to pull in the constitution, domain context, and workflow rules without bloating a single file.

5. **Implement progressive loading:** Move domain-specific knowledge (Doxee product docs) into child directories with their own CLAUDE.md files, loaded only when relevant.

6. **Adopt the three-tier permission model:** Explicitly mark which actions are automatic, which require approval, and which are forbidden in context documents.

7. **Use XML tags for structured spec sections:** When generating specifications, use XML-tagged sections for data that will be programmatically parsed downstream (e.g., `<acceptance_criteria>`, `<technical_constraints>`).

8. **Add "Agent Readiness" assessment:** Following Factory.ai's pattern, create a tool that evaluates how well a feature spec supports autonomous implementation.

---

## Sources

### Official Documentation
- Cursor Rules Documentation: cursor.com/docs/context/rules
- Claude Code Memory Management: code.claude.com/docs/en/memory
- Claude Code Best Practices: code.claude.com/docs/en/best-practices
- GitHub Copilot Custom Instructions: docs.github.com/en/copilot/customizing-copilot
- Devin Knowledge Documentation: docs.devin.ai/onboard-devin/knowledge-onboarding
- Devin AGENTS.md: docs.devin.ai/onboard-devin/agents-md
- Anthropic Prompt Engineering (XML Tags): platform.claude.com/docs/en/build-with-claude/prompt-engineering/use-xml-tags
- Anthropic Long Context Tips: platform.claude.com/docs/en/build-with-claude/prompt-engineering/long-context-tips
- Aider Conventions: aider.chat/docs/usage/conventions.html

### Research Papers
- Liu et al., "Lost in the Middle: How Language Models Use Long Contexts," TACL 2023 (arXiv:2307.03172)

### Community and Industry Sources
- PatrickJS/awesome-cursorrules (GitHub repository, 600+ community-contributed rule examples)
- OpenAI Codex AGENTS.md (github.com/openai/codex/blob/main/AGENTS.md)
- Harper Reed, "My LLM codegen workflow atm" (harper.blog, February 2025)
- Anthropic, "Building Effective Agents" (anthropic.com/research, December 2024)
- Factory.ai Agent Readiness Framework (factory.ai, 2025)

### Tool Websites
- Factory.ai: factory.ai
- Windsurf: docs.windsurf.com
- Sweep: docs.sweep.dev

---

**Document Version:** 1.0
**Last Updated:** February 6, 2026
**Author:** Research compilation for Doxee Speckit framework
