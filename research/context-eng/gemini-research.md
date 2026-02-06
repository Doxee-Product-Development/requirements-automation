# Gemini Research Report: Doxee Company Constitution for AI Requirements Automation

## 1. Executive Summary

This report outlines the optimal structure and content for a "Doxee Company Constitution" designed specifically for consumption by Large Language Models (LLMs) to autonomously generate high-quality product requirements.

The core finding is that **LLMs require a fundamentally different document architecture than humans.** While humans scan for narrative flow, LLMs optimized for RAG (Retrieval Augmented Generation) or long-context windows require:
1.  **High Semantic Density:** Maximum information per token.
2.  **Explicit Structure:** Heavy use of delimiters, JSON/YAML blocks, and hierarchical tagging.
3.  **Imperative Instruction:** "Do X" instead of "We tend to do X".
4.  **Layered Context:** A concentric architecture allowing agents to load only the necessary depth (Layer 0, 1, or 2) to save tokens and reduce "context rot".

---

## 2. Best Practices for AI-Readable Constitutions

Research into AI-native development environments (like Cursor, Devin) and RAG optimization strategies reveals the following best practices:

### 2.1 Information Compaction & Density
*   **Token Economics:** Every token must "buy" understanding. Remove corporate fluff ("world-class," "cutting-edge") unless it defines a specific brand tone constraint.
*   **Canonical References:** Define entities once with a unique ID or alias (e.g., `[P:Pvideo]`) and use that alias throughout. This reduces token count and prevents entity resolution ambiguity.
*   **Tabular Data:** LLMs grasp complex relationships better in Markdown tables or JSON structures than in paragraphs.
    *   *Bad:* "Our pricing model varies. For enterprise, we charge per transaction, but for SMBs..."
    *   *Good:* JSON block defining `pricing_tier: { enterprise: "transaction_volume", smb: "flat_rate" }`.

### 2.2 Progressive Discovery / Layered Loading
To optimize context window usage and retrieval accuracy, the document should be segmented:

*   **Layer 0: Executive Kernel (~2k tokens):** The "Hologram" of the company. If an agent only sees this, it can't write code, but it can write a directionally correct email or epic summary.
    *   *Contents:* Identity, Top 3 Pillars, Top 3 Personas (names only), Core Differentiator, Top 5 "Never" Guardrails.
*   **Layer 1: Working Context (~10k tokens):** The standard operating context for a Product Manager agent.
    *   *Contents:* Full Persona details (JTBD), Competitive Parity Matrix, Strategic Themes, Pricing Logic.
*   **Layer 2: Deep Reference (~18k+ tokens):** The "Law Library." Only loaded when specific checks are needed.
    *   *Contents:* Regulatory specs (GDPR articles), API limits, Full Feature Inventory, Edge-case Brand Guidelines.

### 2.3 Context Window Efficiency & Formatting
*   **Front-Loading:** Put the most critical instructions (Guardrails, Output Format) at the very beginning and very end of the prompt context. LLMs suffer from "lost in the middle" phenomenon.
*   **Structured Delimiters:** Use XML-style tags to help the LLM parse sections without ambiguity.
    ```markdown
    <section id="competitive_landscape" layer="1">
    ...
    </section>
    ```
*   **Imperative vs. Descriptive:**
    *   *Human:* "We try to ensure all our videos are accessible."
    *   *AI:* `[HARD CONSTRAINT] All video output MUST generate VTT sub-tracks.`

---

## 3. Doxee S.p.A. Context Research

### 3.1 Company Identity
*   **Name:** Doxee S.p.A.
*   **Type:** Multinational High-Tech Vendor (CCM/CXM)
*   **Core Offering:** Cloud-native Doxee Platform® for managing mission-critical customer interactions (billing, statements, onboarding).
*   **Key Sectors:** Utilities, Telecom, Banking, Insurance, Public Administration.

### 3.2 Product Portfolio
1.  **Doxee Platform®:** The foundation. Cloud-native, scalable, API-first.
2.  **Doxee Pvideo® (Personalized Video):** Interactive Experience line. Data-driven video generation where every frame is personalized based on user data.
3.  **Doxee Pweb® (Personalized Micro-sites):** Interactive Experience line. Personal web pages generated on the fly for customers (e.g., a dynamic digital bill).
4.  **Doxee dx™ (Document Experience):** Enterprise-grade document generation, batch processing, and archiving.
5.  **Doxee px™ (Paperless Experience):** Electronic invoicing, digital preservation, regulatory compliance tools.

### 3.3 Competitive Landscape
*   **Primary Competitors (CCM/CXM):**
    *   **Quadient (Inspire):** Major legacy player, shifting to cloud.
    *   **OpenText (Exstream):** Enterprise heavyweight, complex integration.
    *   **Smart Communications:** Pure-cloud CCM rival.
    *   **Messagepoint:** Content hub focus.
    *   **Precisely:** Data integrity focus.
*   **Differentiation Strategy:**
    *   **Doxee:** "Interactive Experience" (Pvideo/Pweb) is a stronger differentiator than traditional static CCM. Deep focus on regulated industries (utilities/telco) in Europe/LATAM.

---

## 4. Competitive Intelligence Structure for AI

To allow the AI to generate "Competitive Response" vs. "Differentiation" requirements, the competitive section must be a structured **Feature Parity Matrix** rather than prose profiles.

**Recommended Schema:**

| Competitor | Feature/Area | Doxee Status | Strategy |
| :--- | :--- | :--- | :--- |
| Quadient | Cloud Orchestration | Parity | **Match**: Ensure we have equivalent workflow visualizers. |
| SmartComm | SaaS UX | Lagging | **Response**: Prioritize "Self-Service" epics to close gap. |
| OpenText | Video Personalization | Leading | **Differentiate**: Double down on real-time rendering speed (our moat). |

**Requirement Types:**
1.  **Table Stakes:** "Competitor X has this, we MUST have it to sell." (Priority: High, Innovation: Low)
2.  **Differentiation:** "No one does this well. We build it to win." (Priority: Strategic, Innovation: High)
3.  **Neutralization:** "Competitor Y is winning deals with this niche feature. We need a 'good enough' version." (Priority: Med, Innovation: Low)

---

## 5. Recommended Constitution Template

This template uses the "Layered" approach. Each section is tagged.

```markdown
<!-- DOXEE COMPANY CONSTITUTION -->
<!-- TARGET: AI AGENT CONTEXT -->
<!-- VERSION: 1.0 -->

# 0. META & MANIFEST [LAYER 0]
<!-- TOC with token counts and layer tags -->
*   [0.1 Executive Kernel](#kernel) (2k tokens)
*   [1.0 Strategic Direction](#strategy) (Layer 1)
...

# 0.1 EXECUTIVE KERNEL [LAYER 0]
<!-- CRITICAL: If context is full, DROP EVERYTHING ELSE and keep this. -->
*   **Identity:** Doxee is a cloud-native CCM/CXM provider transforming static docs into interactive experiences (Pvideo, Pweb).
*   **Top 3 Pillars:**
    1.  **Cloud-Native:** Scalability & API-first.
    2.  **Interactivity:** Turning "dead" PDFs into conversations.
    3.  **Compliance:** Absolute trust in regulated markets (GDPR, AgID).
*   **Top 3 Personas:**
    1.  `[PER:CDO]` **Enterprise CDO:** Wants CX transformation, reduced churn.
    2.  `[PER:IT_DIR]` **IT Director:** Wants reliability, security, easy integration.
    3.  `[PER:LOB_MGR]` **Line of Business Manager:** Wants autonomy, fast time-to-market.
*   **Top 5 Guardrails:**
    1.  NEVER compromise PII/GDPR data segregation.
    2.  ALWAYS default to Async/Batch for high-volume operations.
    3.  No "On-Premise" only features; everything must be Cloud-First.

# 1. STRATEGIC DIRECTION [LAYER 1]
<!-- 3-year goals, "Bets" vs "Non-Goals" -->

# 2. PRODUCT PORTFOLIO & INVENTORY [LAYER 1]
<!-- Structured list of Products and Modules -->
*   `[PROD:PVIDEO]`
    *   *Status:* Mature / Cash Cow
    *   *Focus:* Real-time rendering, interactive overlays.
*   `[PROD:DX]`
    *   *Status:* Core
    *   *Focus:* High-volume batch performance.

# 3. USER PERSONAS (DEEP DIVE) [LAYER 1]
<!-- JTBD (Jobs to be Done) format -->
*   **Persona:** `[PER:CDO]`
    *   *Job:* "Demonstrate ROI of digital transformation to the board."
    *   *Pain:* "Vendors are too slow to implement; Data silos."
    *   *Gain:* "Measurable increase in NPS; Reduction in call center volume."

# 4. COMPETITIVE LANDSCAPE (PARITY MATRIX) [LAYER 1]
<!-- The Table defined in Section 4 of this report -->

# 5. BUSINESS MODEL & PRICING [LAYER 1]
<!-- How we make money. Critical for "Monetization" requirements. -->
*   *Model:* SaaS Subscription + Volume (Transactions/Minutes rendered).
*   *Implication:* Requirements must track consumption metrics.

# 6. BRAND, TONE & UX PRINCIPLES [LAYER 1]
*   *Voice:* Professional, Authoritative, but Innovative.
*   *UX:* "Complexity made simple." Hide the batch processing complexity behind clean dashboards.

# 7. REGULATORY & COMPLIANCE [LAYER 2]
<!-- Deep reference for detailed acceptance criteria -->
*   **GDPR:** Article 17 (Right to Erasure) implies all data entities must have a 'purge' API.
*   **Accessibility:** WCAG 2.1 AA for all Pweb outputs.

# 8. TECHNICAL CONSTRAINTS [LAYER 2]
*   *Stack:* AWS, Microservices.
*   *Limits:* Max payload size 10MB (example).

# 9. EXISTING FEATURE INVENTORY [LAYER 2]
<!-- Full list of what exists to prevent re-inventing the wheel -->

# 10. REQUIREMENTS GENERATION RULES [LAYER 0]
<!-- Instructions for the AI -->
1.  **Check Parity:** Before writing a feature, check Section 4. Is this a "Catch-up" or "Innovation"?
2.  **Check Persona:** Every user story must explicitly map to a `[PER:XXX]`.
3.  **Check Guardrails:** If it violates Executive Kernel guardrails, abort.
```