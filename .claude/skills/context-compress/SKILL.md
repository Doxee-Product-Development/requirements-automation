---
name: context-compress
description: "Compress documentation into a token-efficient, layered Context Bible optimized for LLM consumption. Use when (1) compressing large doc corpuses into dense context files, (2) creating LLM-optimized reference material from scattered documentation, (3) building layered knowledge artifacts (L0/L1/L2) for progressive context loading, (4) deduplicating and synthesizing information across multiple documents. Triggers on requests like 'compress these docs', 'create a context bible', 'optimize this documentation for LLM context', 'summarize docs into a context file'."
---

# Context Compress

Compress documentation into a structured, layered Context Bible with 60-85% token reduction and 95%+ semantic preservation.

## Input

**Input paths**: `$ARGUMENTS` (first argument or space-separated paths)
**Output file**: Last argument if multiple provided, else `CONTEXT_BIBLE.md`

Parse rules:
- Single arg: input path(s), output to `CONTEXT_BIBLE.md`
- Multiple args: last = output file, rest = input paths
- Paths can be files, directories, or glob patterns (e.g., `docs/**/*.md`)

## Workflow

### Step 1: Load Persona Reference

Read `references/persona.md` (relative to this skill directory). It defines:
- 10 compression techniques with examples
- Quality framework (5 metrics, 40+ checks)
- Content type templates (API, component, persona, integration)
- Self-assessment rubric (100 points)

### Step 2: Discover Input Documents

1. Expand paths with Glob tool
2. Validate all files exist and are readable
3. Estimate total token count
4. Report discovery to user and confirm before proceeding:

```
Discovered 47 files across 3 directories (~145K tokens)
Target: ~24K tokens (83% compression)
Proceed? [Y/n]
```

### Step 3: Execute 5-Pass Compression

#### Pass 1: Discovery and Inventory (10-15%)

- Read all input files
- Categorize by type (API docs, specs, strategy, etc.)
- Build initial entity list
- Flag potential conflicts and duplications
- Output: file manifest, category breakdown, entity inventory

#### Pass 2: Extraction and Normalization (25-30%)

- Extract all entities with canonical IDs:
  - Products: `[P:Name]`, Personas: `[PER:Role]`, Features: `[F:Name]`
  - APIs: `[API:Name]`, Constraints: `[C:ID]`, Integrations: `[INT:Name]`
- Build glossary with unified definitions
- Normalize terminology (choose canonical terms, document aliases)
- Document conflicts with source references
- Build relationship map

#### Pass 3: Synthesis and Conflict Resolution (30-35%)

- Merge related content across documents (synthesize, don't concatenate)
- Resolve conflicts using strategies:
  - Version conflicts: use latest unless deprecated
  - Feature conflicts: verify with authoritative source
  - Constraint conflicts: use most restrictive
  - Terminology conflicts: use glossary standard
- Build technical indexes (API, Data Model, Integration, File Format, Constraint)
- Map cross-references between sections

#### Pass 4: Layering and Token Optimization (20-25%)

Assign content to three layers:

- **Layer 0 (max 2K tokens)**: Executive Kernel - vision, core products (1-2 sentences each), top personas, critical constraints, active strategic bets. Must pass Hologram Test.
- **Layer 1 (max 10K tokens)**: Core Foundation - complete glossary, all personas with JTBD, architecture overview, key features, common workflows, integration overview.
- **Layer 2 (max 18K tokens)**: Detailed Specs - complete API docs, data models, integrations with protocols/versions, regulatory details, few-shot examples.

Apply compression:
- Strip marketing fluff, preserve all constraints/versions/limits
- Prose -> tables/YAML/XML (structured formats)
- Use canonical references (define once, reference by ID)
- Add XML-style semantic tags (`<layer-0>`, `<component>`, `<persona>`, etc.)
- Optimize for attention curve (critical info at top/bottom)

Run Hologram Test on Layer 0:
- Load ONLY L0 and verify 5 basic questions produce directionally correct answers
- If fails, promote essential content from L1 to L0

#### Pass 5: Validation and QA (10-15%)

Run quality gates (ALL must pass before delivery):
- Compression ratio >= 60%
- Semantic preservation >= 95% (spot-check 20 random facts)
- Token budgets met (L0 <= 2K, L1 <= 10K, L2 <= 18K, total <= 30K)
- Zero unresolved conflicts
- Hologram Test passed
- Self-assessment score >= 75/100
- Zero orphan references (all canonical IDs defined)
- Tag consistency >= 95%

Calculate self-assessment score (100 points across 4 dimensions: compression, structural, synthesis, usability - 25 each). See `references/persona.md` section "Meta-Instructions for Self-Assessment" for scoring rubric.

If any gate fails: document failure, identify root cause, iterate on Pass 4/5 until all pass.

### Step 4: Generate Output

Write Context Bible to specified output file:

```markdown
# Context Bible

<meta>
  creation_date: YYYY-MM-DD
  source_files: N
  source_tokens: N
  output_tokens: N
  compression_ratio: N%
  git_sha: (if in git)
</meta>

<validation-report>
  semantic_preservation: N%
  entity_resolution: N%
  deduplication: N%
  conflicts_resolved: N/N
  hologram_test: PASSED/FAILED
  self_assessment: N/100
  token_budgets:
    layer_0: N / 2,000
    layer_1: N / 10,000
    layer_2: N / 18,000
    total: N / 30,000
</validation-report>

---

## Table of Contents
[Layer-annotated TOC]

---

<layer-0>
[Executive Kernel: vision, products, personas, constraints, bets]
</layer-0>

<layer-1>
[Glossary, architecture, capabilities, workflows, integrations]
</layer-1>

<layer-2>
[APIs, data models, detailed integrations, regulatory, examples]
</layer-2>

## Indexes
[API Index, Data Model Index, Integration Index, File Format Index, Constraint Index]
```

### Step 5: Report Results

Provide summary with: input/output token counts, compression ratio, quality metrics, self-assessment score, Hologram Test result, layer breakdown.

## Critical Anti-Patterns

1. **Concatenation instead of synthesis** - Never join docs end-to-end. Merge overlapping content into unified sections.
2. **Prose creep** - Prefer YAML > tables > tagged lists > bullets > prose.
3. **Lost constraints** - Never drop version numbers, limits, deprecations, or technical rules.
4. **Orphan references** - Every canonical ID must be defined in the dictionary.
5. **Flat structure** - Always use three-layer architecture with semantic tags.

## Error Handling

- **Paths not found**: Report missing paths, ask user to verify
- **Token budget exceeded**: Offer options - increase budget, prioritize L0/L1 only, or split into multiple Context Bibles by domain
- **Compression < 60%**: Content may be inherently dense. Offer to accept lower ratio or remove peripheral content
- **Unresolved conflicts**: Present conflicts to user for manual resolution
- **Hologram Test failed**: Auto-fix by promoting essential content from L1 to L0

## References

- **Compression techniques, templates, quality rubric**: See [references/persona.md](references/persona.md) - complete Context Engineer specification with 10 compression techniques, content type templates, and 100-point scoring rubric
- For large inputs (>100 files): use Task tool with `subagent_type=general-purpose` for parallel processing

## Notes

- Prioritize semantic preservation over token reduction when uncertain
- Layer 0 must ALWAYS pass Hologram Test
- Hard constraints appear at both start and end of output (intentional redundancy for attention curve)
- Progress updates between passes keep user informed
