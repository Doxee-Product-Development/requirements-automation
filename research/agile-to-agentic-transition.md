# Transition Plan: From Agile to Agentic AI-Driven Development

**Organization:** Doxee
**Date:** February 2026
**Current Structure:** 5 PMs, 1 UX Designer, 7 Teams (4 pax/team: 1 QA, 1 Scrum Master, 2 Developers).

---

## 1. The Core Philosophy Shift
In traditional Agile, requirements are "conversations" that are clarified during development. In **Agentic Development**, requirements must be **executable specifications**. 

An Agentic AI cannot "brainstorm" during a sprint; it requires unambiguous context, visual targets, and success criteria defined *before* execution starts.

---

## 2. Structural Role Transformation (Upstream Focus)

To support autonomous software development, the "Upstream" (Product & Design) must become more rigorous and visually descriptive.

### A. Product Managers (PMs) → "System Orchestrators"
PMs shift from writing stories to building **High-Fidelity Context Packages**.
*   **New Task:** Using AI tools (v0, Bolt.new, Screenshot-to-code) to generate visual wireframes for every requirement.
*   **New Task:** Defining strict API contracts and data schemas as part of the "Definition of Ready."
*   **Interaction:** They no longer "hand off" to Devs; they feed the **Agent Graph**.

### B. UX Designer → "Design System Architect"
With a 1:35 designer-to-staff ratio, the designer is currently a bottleneck.
*   **New Role:** Cease designing individual features. Move to maintaining a **Machine-Readable Design System**.
*   **New Task:** Creating a robust library of React/UI components that coding agents are trained to use.
*   **Output:** A "Design Constitution" that dictates how AI agents should style and layout new features.

### C. QA Engineers → "Eval Specialists" (The Shift-Left)
QA moves from the end of the pipeline to the very beginning.
*   **New Role:** Building **Evals** (Automated benchmarks). 
*   **New Task:** Translating PM requirements into Gherkin (Given/When/Then) scripts *before* a single line of code is written.
*   **Interaction:** If the Agentic AI passes the QA's "Eval Suite," the code is considered verified.

### D. Scrum Masters → "Knowledge & Context Curators"
With 7 Scrum Masters for 28 developers, this role is reskilled to remove administrative overhead and focus on **AgentOps**.
*   **New Role:** Managing the **RAG (Retrieval-Augmented Generation) Knowledge Base**.
*   **New Task:** Ensuring that technical documentation, architecture ADRs, and business rules are accurately indexed for the AI Agents to read.
*   **Impact:** If an Agent makes a mistake due to old documentation, the Context Curator is responsible for the fix.

---

## 3. The New "Definition of Ready" (DoR)

A requirement is only "Ready" for the Agentic Loop when it contains:
1.  **Visual Target:** An AI-generated screenshot or low-fidelity mockup.
2.  **Context Mapping:** Explicit mention of which components and APIs to use.
3.  **The Eval Suite:** A set of machine-runnable tests (provided by QA).
4.  **Token Budget:** An estimated cost/complexity ceiling for the agent.

---

## 4. Transition Roadmap

### Phase 1: Structured Specification (Months 1-2)
*   **Action:** Ban "User Stories." Replace them with **Gherkin Specifications**.
*   **Goal:** Force PMs and QAs to define success criteria deterministically.
*   **KPI:** Reduction in "clarification questions" asked by developers.

### Phase 2: Visual Prompting & Componentization (Months 3-4)
*   **Action:** UX Designer completes the "Design System." PMs begin using AI UI-generators.
*   **Goal:** The AI Agent should never "invent" a button; it should only use existing components from the library.

### Phase 3: The Pilot Autonomous Team (Months 5-6)
*   **Action:** Select one of the 7 teams to run a "Zero-Human-Code" sprint for a minor feature.
*   **Process:** PM/QA provides the Spec + Eval. The Developer acts as the **"Human-in-the-Loop" Reviewer**, only approving the Agent's PRs.

---

## 5. Immediate High-Impact Actions

1.  **Freeze Manual UI Design:** The UX Designer stops all "one-off" feature designs and focuses 100% on the **Design System Documentation**.
2.  **QA Re-Alignment:** Move the 7 QA Engineers into the "Product Discovery" meetings. They must sign off on the *testability* of a requirement before it hits a developer's plate.
3.  **The "Agent-Ready" Audit:** Audit the internal documentation. If a human dev needs to ask a senior "how does this work?", the AI agent will also fail. Start the Scrum Masters on a "Documentation Clean-up" sprint.

---
*Strategy proposed for Doxee to maximize its 35-person development engine through Agentic AI.*
