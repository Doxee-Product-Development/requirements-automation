# Agent-Ready Checklist (DoR)

**Feature**: [FEATURE NAME]
**PM**: [NAME]
**UX**: [NAME]
**QA**: [NAME]

---

## 1. Visual & UI Clarity (PM + UX)
- [ ] **Visual Target Attached**: Does the spec contain a screenshot or interactive prototype (v0/Bolt/Figma)?
- [ ] **Component Audit**: Are all UI elements used in the mockups available in our Design System library?
- [ ] **State Transitions**: Are all loading, empty, and error states visually defined?

## 2. Technical Context (PM + Architect)
- [ ] **API Contracts Defined**: Are the endpoint URLs, methods, and payload schemas documented?
- [ ] **Data Entities**: Have the key entities and their relationships been defined (ignoring DB implementation)?
- [ ] **Tooling Boundaries**: Does the spec explicitly list which internal functions/tools the agent *should* and *should not* use?

## 3. Knowledge Base Alignment (Curator/Scrum Master)
- [ ] **Context Links**: Does the spec link to the exact files (READMEs, ADRs) the agent needs to read?
- [ ] **Stale Docs Flagged**: Have we explicitly warned the agent about any outdated documentation in the codebase?

## 4. Verification & Evals (QA)
- [ ] **Deterministic Scenarios**: Are acceptance criteria written in "Given/When/Then" format?
- [ ] **Executable Evals**: Can the scenarios be translated into machine-runnable tests (e.g., status code checks, DB counts)?
- [ ] **Edge Cases**: Are at least 3 boundary conditions (e.g., null data, network timeout) defined?

## 5. Security & Safety (CISO/PM)
- [ ] **PII Review**: Does this feature handle sensitive data? If so, are masking rules defined?
- [ ] **Step Limit**: Have we set a maximum "Chain of Thought" step limit for this agentic run?

---

### Final Sign-off
> [ ] **I certify that this requirement is "Agent-Ready" and requires ZERO human clarification for execution.**
