# Agentic Feature Specification: [FEATURE NAME]

**Status**: [AGENT-READY | DRAFT | NEEDS-CLARIFICATION]
**Context Curator**: [SCRUM MASTER NAME]
**Eval Lead**: [QA NAME]
**Visual Target**: [LINK TO AI-GENERATED UI / SCREENSHOT]

---

## 1. Executive Intent (PM Domain)
*Describe the 'Why' and the business value. This provides the Agent with the "Spirit" of the requirement to handle edge cases.*

> [Description of business intent]

---

## 2. Visual Blueprint & Interaction (PM + AI Domain)
*Agents need a visual target. Attach a screenshot or a v0.dev/Bolt.new link here.*

- **Layout Concept:** [e.g., Two-column layout, Sidebar navigation]
- **Key Components:** [e.g., DataGrid, DateRangePicker, SubmitButton]
- **Interaction Flow:** [e.g., Click 'Filter' -> Opening Modal -> Apply -> Toast Success]

---

## 3. Technical Toolset (Architecture Domain)
*Define the "Tools" the Agent is allowed to use. This prevents the Agent from inventing APIs.*

- **Existing APIs:** 
    - `GET /api/v1/[resource]`: Used for [purpose]
    - `POST /api/v1/[resource]`: Schema: `{[fields]}`
- **Design System Components:**
    - `<DoxeeButton>`: Primary action
    - `<DoxeeInput>`: Validation rules: [regex]
- **State Management:** [e.g., Update local state via React Query cache]

---

## 4. Knowledge Context (Curator Domain)
*Which documentation should the Agent read before starting?*

- **Relevant Docs:** [e.g., docs/architecture/auth-flow.md, docs/api/invoice-schema.md]
- **Legacy Context:** [e.g., "Note: This module uses the old SQL schema, do not use the GraphQL endpoint yet."]

---

## 5. Machine-Executable Evals (QA Domain)
*This is the "Definition of Done". Replace vague text with deterministic scenarios.*

### Scenario 1: [Critical Path]
- **Pre-condition:** User is logged in as `Admin`.
- **Action:** User submits the form with `$DATA`.
- **Verification (The Eval):**
    - [ ] `response.status === 201`
    - [ ] `database.records.count` increased by 1
    - [ ] UI shows success toast with message "Saved Successfully"

### Scenario 2: [Error Handling]
- **Action:** Submit empty form.
- **Verification:**
    - [ ] Input fields show red border.
    - [ ] API call is NOT triggered.

---

## 6. Constraints & Safety Guardrails
- **Max Steps:** [e.g., 20 steps before pausing for human review]
- **Cost Limit:** [e.g., $1.50 in tokens]
- **PII Guardrail:** NEVER log user email or password to the console.

---
*Generated via Doxee Agentic Transition Framework.*
