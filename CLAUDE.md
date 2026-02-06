# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **Speckit**, a requirements automation framework built on Claude Code slash commands. It provides a structured workflow for transforming natural language feature descriptions into implementation-ready specifications, plans, and tasks.

## Workflow Architecture

The system follows a linear progression through these stages:

```
specify → clarify → plan → tasks → analyze → implement
    ↓         ↓        ↓       ↓        ↓          ↓
 spec.md   (updates)  plan.md tasks.md report  execution
           spec.md   research.md
                    data-model.md
                    contracts/
```

Each stage produces artifacts in `specs/<###-feature-name>/`.

## Slash Commands

All commands are prefixed with `/speckit.`:

| Command | Purpose | Key Outputs |
|---------|---------|-------------|
| `/speckit.specify <description>` | Create feature branch and spec from natural language | Branch, `spec.md`, `checklists/requirements.md` |
| `/speckit.clarify` | Reduce ambiguity in spec via interactive Q&A | Updated `spec.md` with clarifications |
| `/speckit.plan` | Generate technical implementation plan | `plan.md`, `research.md`, `data-model.md`, `contracts/` |
| `/speckit.tasks` | Break plan into executable, dependency-ordered tasks | `tasks.md` organized by user story |
| `/speckit.analyze` | Read-only consistency check across all artifacts | Analysis report (no file writes) |
| `/speckit.checklist <domain>` | Create "unit tests for requirements" quality checklist | `checklists/<domain>.md` |
| `/speckit.implement` | Execute tasks.md phase-by-phase | Implementation + task completion tracking |
| `/speckit.constitution` | Update project principles in constitution.md | Updated `.specify/memory/constitution.md` |
| `/speckit.taskstoissues` | Convert tasks to GitHub issues | GitHub issues (requires GitHub remote) |

## Key Scripts

Located in `.specify/scripts/bash/`:

- `create-new-feature.sh` - Creates feature branch (###-name format) and initializes spec directory
- `check-prerequisites.sh` - Validates context and returns JSON with paths (used by most commands)
- `setup-plan.sh` - Initializes plan.md from template
- `update-agent-context.sh` - Updates agent-specific context files after planning

Run scripts with `--json` flag when parsing output programmatically.

## Directory Structure

```
.claude/commands/          # Slash command definitions (speckit.*.md)
.specify/
├── templates/             # Markdown templates for all artifacts
│   ├── spec-template.md   # Feature specification structure
│   ├── plan-template.md   # Implementation plan structure
│   ├── tasks-template.md  # Task list structure with phases
│   └── checklist-template.md
├── scripts/bash/          # Helper scripts
└── memory/
    └── constitution.md    # Project principles (customize per project)

specs/                     # Generated feature artifacts (created at runtime)
└── ###-feature-name/
    ├── spec.md
    ├── plan.md
    ├── tasks.md
    ├── research.md
    ├── data-model.md
    ├── contracts/
    └── checklists/
```

## Task Format

Tasks in `tasks.md` follow strict format:
```
- [ ] T### [P?] [Story?] Description with file path
```

- `T###` - Sequential task ID
- `[P]` - Parallelizable (different files, no dependencies)
- `[US#]` - User story mapping (for traceability)

## Constitution

The constitution at `.specify/memory/constitution.md` defines project principles. It ships as a template with placeholders. Use `/speckit.constitution` to fill in project-specific principles before starting work. The `/speckit.plan` command validates against constitution gates.

## Checklist Philosophy

Checklists created by `/speckit.checklist` are "unit tests for requirements" - they validate that specifications are complete, clear, consistent, and measurable. They do NOT test implementation behavior.

- Correct: "Are loading state requirements defined?"
- Wrong: "Verify loading spinner displays correctly"

## Script Architecture

All bash scripts in `.specify/scripts/bash/` follow a common pattern:

- `common.sh` - Shared functions for repository detection, branch validation, and path resolution
- Scripts support both git and non-git workflows (checks for `.git` or `.specify` directories)
- `--json` flag: All scripts support JSON output for programmatic parsing
- `SPECIFY_FEATURE` environment variable: Can override git branch detection for non-git workflows

Branch naming convention: `###-feature-name` where `###` is a zero-padded 3-digit number that auto-increments based on existing branches and specs directories.

## Template System

All artifacts are generated from templates in `.specify/templates/`:

- **spec-template.md**: Feature specifications with mandatory/optional sections, user stories with priorities (P1, P2, P3), acceptance scenarios in Given/When/Then format
- **plan-template.md**: Technical implementation plans with Constitution gates, phase structure, and source code organization
- **tasks-template.md**: Task lists organized by user story for independent implementation, using format `- [ ] T### [P?] [US#] Description with file path`
- **checklist-template.md**: Quality validation checklists

Templates use placeholder syntax like `[FEATURE_NAME]`, `[DATE]`, `$ARGUMENTS` that are replaced during generation.

## Workflow Phases

The linear workflow is strictly ordered to prevent rework:

1. **specify**: Creates feature branch and generates spec.md from natural language description. Auto-generates requirements checklist for validation.
2. **clarify** (optional): Interactive Q&A to resolve [NEEDS CLARIFICATION] markers in spec (max 3 clarifications per spec).
3. **plan**: Generates plan.md, research.md, data-model.md, and contracts/ after validating against constitution gates.
4. **tasks**: Breaks plan into tasks.md organized by user story with dependencies and parallelization markers.
5. **analyze**: Read-only consistency check across all artifacts (no file modifications).
6. **implement**: Executes tasks phase-by-phase with completion tracking.
7. **taskstoissues**: Exports tasks to GitHub issues with dependency ordering.

Each phase produces artifacts in `specs/###-feature-name/` and validates prerequisites before proceeding.

## Git Integration

This is a work account repository (`~/Documents/projects/doxee/`), so use standard `git` and `gh` commands (NOT `git-me` or `gh-me`). The SSH key is `~/.ssh/id_ed25519_work` with account `magenerali@doxee.com`.

## Context Documents

The `doxee/` directory contains rich domain context:

- `Doxee-profile.md`: Company and product overview
- `Doxee Platform functional architecture and components.md`: Platform architecture
- `official-product-documentation/`: Complete product documentation for Doxee Platform components
- `analysts/`: Market analysis and competitive positioning documents

These documents provide domain knowledge for generating features aligned with Doxee's CCM (Customer Communications Management) platform.
