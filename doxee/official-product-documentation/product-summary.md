# Doxee Product Management Framework
*Documentation Version 1.0 | Last Updated: 2024-07-17*

## Executive Summary

This document establishes the product management framework for Doxee's Customer Communications Management (CCM) platform. It defines the product vision, prioritization methodology, user personas, and strategic initiatives that guide product development and roadmap planning.

**Key Decisions:**
- **Product Discovery Tool**: Jira Product Discovery with customized RICE scoring
- **Target Market**: Enterprise self-service CCM platform
- **Strategic Direction**: Unified portal experience for all Doxee applications
- **Pricing Model**: Volume-based and user-based metrics with add-on services

---

## Table of Contents

1. [Product Vision & Strategy](#1-product-vision--strategy)
2. [Prioritization Framework](#2-prioritization-framework)
3. [User Personas](#3-user-personas)
4. [Product Positioning & Architecture](#4-product-positioning--architecture)
5. [UX Strategy](#5-ux-strategy)
6. [Future Innovation Opportunities](#6-future-innovation-opportunities)
7. [Implementation Roadmap](#7-implementation-roadmap)
8. [Appendices](#8-appendices)

---

## 1. Product Vision & Strategy

### 1.1 Company Vision (Why)

Doxee exists to build strong relationships and loyalty between enterprise companies and their customers through meaningful, clear, and easy-to-understand communications at every interaction.

> **Vision Statement**: Ensure every communication is not just seen, but truly understood.

### 1.2 Product Vision (What & How)

> **Product Vision**: We enable enterprises to shape their communications with the right content, right timing, and right channel for each person by providing a flexible and innovative platform.

### 1.3 Strategic Pillars

The product vision is built on these core principles:

| Pillar | Description | Implementation Focus |
|--------|-------------|---------------------|
| **Self-Service Platform** | Enable customers to operate independently with minimal technical support | Intuitive UI, comprehensive documentation, in-app guidance |
| **Enterprise Focus** | Target large organizations with complex communication needs | Multi-tenant architecture, enterprise SSO, role-based access |
| **Content Design Excellence** | Provide powerful yet accessible content creation tools | Visual designers, templates, WYSIWYG editors |
| **Process Automation** | Reduce manual operations through intelligent automation | Workflow engines, triggers, scheduled jobs |
| **Multi-Channel Delivery** | Support all communication channels from a single platform | Email, SMS, PDF, Pvideo, Pweb, digital archiving |
| **Flexibility** | Adapt to diverse business requirements and workflows | Configurable processes, extensible APIs, custom integrations |
| **Innovation** | Stay ahead of market with cutting-edge capabilities | AI integration, interactive content, analytics |

### 1.4 Target Deployment Models

| Model | Description | Primary Use Case |
|-------|-------------|------------------|
| **SaaS Multi-Cloud** | Hosted on major cloud providers (AWS, Azure, GCP) and Doxee data centers | Standard enterprise customers |
| **PaaS** | Platform-as-a-Service with extensibility | Customers requiring customization |
| **On-Premises** | Customer-managed infrastructure | Highly regulated industries, data sovereignty requirements |

---

## 2. Prioritization Framework

### 2.1 Overview

Doxee uses a customized RICE prioritization model implemented in Jira Product Discovery. This framework ensures objective, data-driven decisions about which initiatives to pursue based on expected value delivery.

### 2.2 Standard RICE Formula

The traditional RICE framework evaluates initiatives across four dimensions:

**Formula**: `RICE Score = (Reach × Impact × Confidence) / Effort`

### 2.3 Doxee Extended RICE Model

Doxee has extended the standard RICE model to incorporate strategic factors specific to enterprise CCM software:

**Extended Formula**:
```
Value = ((Reach × Impact) + Cost Reducing + Cofinancing) × (Confidence / 100) / Effort
```

**Alternative Weighted Formula** (experimental):
```
Value = (R×wr + I×wi + C×wc + S×ws + F×wf + L×wl) / (Effort × we)
```

### 2.4 RICE Component Definitions

#### Reach (R)

**Definition**: Revenue-weighted reach in terms of affected customers in the first year after release.

| Score | Criteria | Customer Impact |
|-------|----------|-----------------|
| **1** | Minimal reach | 1-20% of customers affected in first year |
| **2** | Limited reach | 21-40% of customers affected |
| **3** | Moderate reach | 41-60% of customers affected |
| **4** | High reach | 61-80% of customers affected |
| **5** | Maximum reach | 81-100% of customers affected in first year |

**Data Sources**:
- Customer usage analytics
- License deployment data
- Revenue distribution by customer segment

**Best Practices**:
- Weight by revenue (e.g., 100 small customers may equal 1 enterprise customer)
- Consider indirect reach (e.g., features affecting partners who serve multiple customers)
- Measure actual usage, not just potential access

#### Impact (I)

**Definition**: The magnitude of value delivered to users and the business, assessed through product manager evaluation, customer interviews, pre-sales feedback, and CSM insights.

| Score | Category | Description | Business Outcome |
|-------|----------|-------------|------------------|
| **1** | Tech Debt | Reduces technical debt, improves maintainability | Internal efficiency, reduced future costs |
| **2** | Competitive Parity | Catches up with competition | Prevents customer churn, maintains market position |
| **3** | Significant Improvement | Meaningful enhancement to existing capabilities | Increases user satisfaction, may drive new sales |
| **4** | Huge Improvement | Major advancement in core functionality | Strong competitive advantage, drives expansion revenue |
| **5** | Game Changer | Transforms the market or creates new category | Dominant market position, significant revenue growth |

**Evaluation Process**:
1. Product Manager conducts preliminary assessment
2. CSM team provides customer feedback and satisfaction data
3. Pre-sales and Sales teams share competitive positioning insights
4. Cross-functional review session to achieve consensus

**Success Metrics by Impact Level**:
- **Revenue Impact**: New sales, expansion revenue, churn reduction
- **Customer Satisfaction**: NPS, CSAT, feature adoption rates
- **Operational Efficiency**: Support ticket reduction, time savings
- **Strategic Value**: Market differentiation, analyst recognition

#### Confidence (C)

**Definition**: The level of certainty in the Reach, Impact, and Effort estimates.

| Confidence Level | Percentage | Score | When to Use |
|-----------------|------------|-------|-------------|
| **High** | 100% | 1.0 | Validated with customer data, proven market demand, clear requirements |
| **Medium** | 80% | 0.8 | Some customer validation, comparable features exist, requirements mostly clear |
| **Low** | 50% | 0.5 | Limited validation, new territory, significant unknowns remain |

**Industry Best Practice** (Source: Intercom):
- High confidence requires quantitative evidence (usage data, surveys, A/B tests)
- Medium confidence backed by qualitative research (interviews, competitive analysis)
- Low confidence indicates need for discovery work before commitment

**Doxee Guidelines**:
- If confidence approaches 0, split the initiative into smaller, better-defined ideas
- Confidence < 50% signals the need for additional discovery or prototyping
- Document confidence assumptions and validation criteria

#### Effort (E)

**Definition**: Product Manager + Technical Lead high-level estimation in person-days, using a linear scale.

| Score | Person-Days | Typical Scope | Team Size Assumption |
|-------|-------------|---------------|---------------------|
| **1** | 0-100 | Small feature, single component | 1-2 developers, 2-4 weeks |
| **2** | 100-200 | Medium feature, multiple components | 2-3 developers, 2-3 months |
| **3** | 200-300 | Large feature, system integration | 3-4 developers, 3-4 months |
| **4** | 300-400 | Major feature, architectural changes | 4-6 developers, 4-6 months |
| **5** | 400-500 | Platform initiative, multiple systems | 6+ developers, 6+ months |

**Important Constraints**:
- **Maximum effort threshold**: Initiatives requiring > 500 person-days cannot use this formula
- **Action for large initiatives**: Break down into smaller, independently valuable releases
- **Effort includes**: Development, testing, documentation, deployment, but NOT ongoing maintenance

**Estimation Best Practices**:
- Include technical lead in estimation process
- Account for integration testing and deployment complexity
- Add buffer for cross-team dependencies
- Consider technical debt that must be addressed first

### 2.5 Extended Value Components

#### Cost Reducing (Strategic Factor)

**Definition**: Expected cost savings or operational efficiency gains.

| Score | Annual Savings | Example |
|-------|----------------|---------|
| **1** | < €30,000 | Minor efficiency improvement |
| **2** | €30,000 - €60,000 | Moderate automation, reduces manual work by 100 person-days/year |
| **3** | €60,000 - €90,000 | Significant automation or support ticket reduction |
| **4** | €90,000 - €120,000 | Major operational improvement |
| **5** | > €120,000 | Transformative efficiency gain |

**Calculation Basis**:
- Person-day cost: ~€300 (fully loaded)
- 100 person-days saved = €30,000 annually
- Consider: Support costs, infrastructure costs, delivery costs

#### Co-financing (Customer Investment)

**Definition**: Level of customer financial contribution or commitment to the feature development.

| Score | Customer Investment | Signal |
|-------|---------------------|--------|
| **1** | 20% co-financing | Moderate customer interest |
| **2** | 40% co-financing | Strong customer interest |
| **3** | 60% co-financing | Very strong customer need |
| **4** | 80% co-financing | Critical customer requirement |
| **5** | 100% co-financing | Fully funded by customer |

**Strategic Interpretation**:
- High co-financing indicates validated market demand
- Acts as risk mitigation for uncertain initiatives
- May influence prioritization for strategic accounts

### 2.6 Prioritization Process

#### Step 1: Initiative Intake
- All product ideas enter Jira Product Discovery
- Stakeholders can submit ideas via standardized template
- Ideas tagged by product area, customer segment, strategic theme

#### Step 2: Scoring
- Product Manager scores each component (R, I, C, E)
- Technical Lead validates Effort estimates
- CSM/Sales provides Reach and Impact input
- Finance validates Cost Reducing calculations

#### Step 3: Review & Calibration
- Product leadership reviews scores quarterly
- Cross-product comparison to ensure consistency
- Recalibration based on outcomes of shipped features

#### Step 4: Roadmap Planning
- Ideas visualized on Effort vs. Value matrix
- Focus on upper-left quadrant (high value, low effort)
- Balance quick wins with strategic investments

#### Step 5: Stakeholder Communication
- **Insights**: Used for collecting votes and feedback
- **Comments**: Stakeholders enrich ideas with context
- **Granularity levels**: Define visibility for Sales and Delivery teams

### 2.7 Implementation Status

**Completed**:
- ✓ Jira Product Discovery activated for all Product Managers
- ✓ RICE formula defined and documented
- ✓ Formula spreadsheet created (see Appendix)
- ✓ 2024 roadmap initiatives imported and scored

**Next Steps**:
1. **User Provisioning**: Create Jira accounts for all Product Managers in Infinica Jira instance
2. **Pilot Application**: Apply RICE scoring to current roadmap initiatives (Q1 2024)
3. **Calibration**: Evaluate results and tune value algorithm based on initial outcomes
4. **Stakeholder Training**: Train Sales, CSM, and Delivery teams on submitting and voting on ideas
5. **Integration**: Connect Jira Product Discovery to Jira Software for seamless roadmap-to-delivery workflow
6. **Quarterly Reviews**: Establish cadence for portfolio review and reprioritization

**🚨 Clarification Needed**:
- Define specific granularity levels for Sales and Delivery visibility
- Establish governance for Ideas requiring > 500 person-days of effort
- Confirm weights for experimental weighted RICE formula

---

## 3. User Personas

### 3.1 Overview

Doxee serves a diverse set of users across the customer communication lifecycle. Understanding these personas is critical for designing intuitive, role-appropriate experiences in the unified portal.

### 3.2 Persona Catalog

#### 3.2.1 Consumer

**Role**: End recipient of customer communications

**Context**: External to customer organization; interacts with Doxee-generated content

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Views and interacts with communications |
| **Channels Used** | PDF documents, Pvideo, Pweb, Email, SMS |
| **Technical Skills** | Non-technical; expects consumer-grade UX |
| **Key Needs** | Accessible, mobile-friendly, clear communications |
| **Success Metrics** | Engagement rate, time to comprehension, task completion |

**Associated Products**: All Doxee output channels

#### 3.2.2 Business User

**Role**: Day-to-day operational user (support, sales, accountants)

**Context**: Uses Doxee tools for routine tasks; not a designer or developer

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Search archives, track deliveries, access workplace tools |
| **Applications** | Digital Archiving, Tracking & Reporting, Workplace |
| **Technical Skills** | Non-technical business users; comfortable with standard enterprise software |
| **Key Needs** | Fast search, clear reporting, minimal training required |
| **Pain Points** | Complex interfaces, slow query performance |
| **Success Metrics** | Task completion time, search success rate, self-service adoption |

**Example Users**:
- ENGIE support team (Digital Archiving)
- RGIT operations team (Digital Archiving)
- Julia Pekarova and team (Workplace)

#### 3.2.3 Analyst

**Role**: Business intelligence and performance monitoring

**Context**: Creates dashboards, analyzes production metrics, measures engagement

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Build dashboards, analyze production performance, measure engagement metrics |
| **Applications** | BI Headlight Cloud, Analytics, Tracking & Reporting |
| **Technical Skills** | Technical users with reporting/SQL skills; understand data models |
| **Key Needs** | Data access, flexible visualization, export capabilities |
| **Pain Points** | Data silos, inconsistent metrics across products |
| **Success Metrics** | Dashboard usage, insight generation, data-driven decision adoption |

**Example Users**:
- **Customer Success Managers**: Ismaele Moretti
- **Project Managers**: Dondi, Plaia, Aiman, Perrone
- **Dashboard Developers**: Tagliafierro

#### 3.2.4 Billing Manager

**Role**: Financial operations and usage monitoring

**Context**: Manages billing, analyzes usage quotas, handles invoicing

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Review usage quotas, manage billing information, generate invoices, monitor costs |
| **Applications** | BI tools, volume reports, administration portal |
| **Technical Skills** | Non-technical business users; strong financial acumen |
| **Key Needs** | Accurate usage data, clear cost breakdowns, export to finance systems |
| **Pain Points** | Manual data collection, reconciliation errors |
| **Success Metrics** | Billing accuracy, time to invoice, quota utilization visibility |

**Example Users**:
- **CSM**: Ismaele Moretti
- **Commercial**: Scaccia, Aiman, Gaspari
- **Support**: Mario
- **Administration**: Finance team

#### 3.2.5 System Administrator

**Role**: Platform administration and security management

**Context**: Manages users, roles, permissions, and platform-wide settings

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | User provisioning, role assignment, security configuration, system settings |
| **Applications** | Admin console, user management, settings portal |
| **Technical Skills** | Technical; understands enterprise security, IAM concepts |
| **Key Needs** | Centralized user management, audit logs, bulk operations, SSO integration |
| **Pain Points** | Fragmented admin across multiple portals, manual user provisioning |
| **Success Metrics** | Time to provision users, security compliance, audit trail completeness |

**🚨 Clarification Needed**: Define responsibilities for multi-account vs. single-tenant administration

#### 3.2.6 Process Designer

**Role**: Technical designer responsible for workflows and automation

**Context**: Creates processes, data transformations, output management configurations

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Design workflows, configure data transformations, set up digital archiving rules, manage endpoints |
| **Applications** | Process Designer, Workflow, Data Transformation, Digital Archiving Settings, Output Management |
| **Technical Skills** | **Technical Designer** - IT-skilled user who can use all design tools |
| **Key Needs** | Integrated design environment, testing/debugging tools, version control |
| **Pain Points** | Context switching between multiple designer tools, difficult troubleshooting |
| **Success Metrics** | Time to build process, error rate in production, reusability of components |

**Subcategories**:
- Workflow Designer
- Data Transformation Developer
- Output Management Specialist

#### 3.2.7 Content Designer

**Role**: Non-technical designer focused on communication content

**Context**: Creates visual templates, videos, and interactive content

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Design email templates, create video templates, build interactive web experiences |
| **Applications** | Business Designer, Pvideo Designer |
| **Technical Skills** | **Business Designer** - Content expert without IT skills; creative professional background |
| **Key Needs** | WYSIWYG editors, template libraries, preview capabilities, brand asset management |
| **Pain Points** | Technical barriers to creativity, limited design flexibility |
| **Success Metrics** | Content creation velocity, design consistency, engagement metrics |

**Subcategories**:
- Email/Document Designer
- Video Content Designer
- Interactive Experience Designer

#### 3.2.8 Operator

**Role**: Production monitoring and first/second-level support

**Context**: Monitors job execution, investigates failures, manages production operations

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Monitor job status, view logs, track deliveries, investigate errors, escalate issues |
| **Applications** | Jobs Portal, Logs, Infrastructure Monitoring, Tracking & Reporting |
| **Technical Skills** | Technical/Support; troubleshooting skills, understands system architecture |
| **Key Needs** | Real-time alerting, comprehensive logs, error correlation, quick remediation |
| **Pain Points** | Alert fatigue, difficult log navigation, slow issue diagnosis |
| **Success Metrics** | Mean time to detection (MTTD), mean time to resolution (MTTR), SLA compliance |

#### 3.2.9 DevOps Engineer

**Role**: Infrastructure management and reliability

**Context**: Deploys infrastructure, monitors health, manages incidents, ensures uptime

| Attribute | Details |
|-----------|---------|
| **Primary Activities** | Infrastructure deployment, health checks, capacity planning, incident management, exception handling |
| **Applications** | Command Center, Infrastructure Monitoring, Deployment Tools |
| **Technical Skills** | Technical/Infrastructure; deep system knowledge, automation skills |
| **Key Needs** | Observability tools, automated deployment, runbooks, incident response procedures |
| **Pain Points** | Manual deployment steps, insufficient monitoring coverage, unclear escalation paths |
| **Success Metrics** | System uptime, deployment frequency, incident response time, infrastructure cost efficiency |

### 3.3 Persona Mapping to Workflows

| Workflow Stage | Primary Persona | Supporting Personas | Key Activities |
|----------------|----------------|---------------------|----------------|
| **Design** | Content Designer, Process Designer | System Admin | Create templates, build processes, configure workflows |
| **Test** | Process Designer, Operator | DevOps | Validate functionality, test integrations |
| **Deploy** | DevOps | System Admin | Provision infrastructure, configure environments |
| **Operate** | Operator | DevOps, System Admin | Monitor jobs, handle incidents |
| **Analyze** | Analyst, Billing Manager | Business User | Review metrics, generate reports |
| **Support** | Business User, Operator | System Admin | Respond to inquiries, troubleshoot issues |
| **Consume** | Consumer | N/A | Receive and interact with communications |

### 3.4 Persona-Based Feature Priorities

Based on the unified portal strategy, the following features are critical for each persona:

**All Personas**:
- Single sign-on (SSO) across all Doxee applications
- Multi-account selector with favorite/recent resources
- Centralized documentation and release notes
- Consistent navigation and UI patterns

**Content & Process Designers**:
- Unified design environment reducing context switching
- Direct resource linking (e.g., search data transformation from process designer)
- Integrated testing environment
- Version control and rollback capabilities

**Operators & DevOps**:
- Real-time monitoring dashboard
- Centralized logging with correlation
- Alerting and incident management
- Deployment automation

**Business Users & Analysts**:
- Fast, powerful search across all resources
- Self-service reporting and dashboards
- Data export capabilities
- Mobile-responsive interface

**System Administrators**:
- Centralized user and role management
- Multi-tenant and multi-account configuration
- Audit logging
- Enterprise SSO integration (investigate solutions - see Action Items)

---

## 4. Product Positioning & Architecture

### 4.1 Strategic Positioning Decisions

The following table captures key positioning decisions made during the product strategy summit:

| Dimension | Decision | Rationale | Action Items |
|-----------|----------|-----------|--------------|
| **Support Model** | **Doxee**: Third-level support (product bugs), First-level support (if sold separately), Technical requests<br>**Customers**: First-level support (config/user errors) | Sustainable support model; enables customer self-service | • Build comprehensive documentation<br>• Create in-app contextual help<br>• Develop FAQ pages<br>• Create onboarding tutorials<br>• Train customer support teams<br>• Implement service desk portal |
| **Documentation Access** | Public documentation portal (gradual rollout) | Increases transparency, reduces support burden, improves sales process | • Prioritize documentation for public release<br>• Establish content review process |
| **Service Model** | Both SaaS and PaaS (aim for PaaS) | Flexibility for different customer needs; PaaS enables deeper integration | • Define PaaS extensibility points<br>• Develop API-first architecture |
| **Infrastructure** | **SaaS**: Multi-cloud (AWS, Azure, GCP, Doxee DC)<br>**On-Premises**: Available for customers requiring it | Reduce vendor lock-in, meet compliance requirements, maximize market reach | • Ensure portability across cloud providers<br>• Support containerized deployments |
| **Go-to-Market** | Both partners and direct customers | Maximize market coverage | • Develop partner enablement programs<br>• Create partner portal capabilities |
| **Pricing Model** | **Volume-based**: Product-specific metrics<br>**User-based**: Role-based licensing<br>**Add-ons**: Managed support, professional services | Flexible monetization aligned with value delivery | • Define volume metrics per product<br>• Establish role hierarchy<br>• Package support tiers |
| **Customer Communication** | Application-level notifications via platform<br>Infrastructural errors managed separately | Clear communication channels; reduces alert fatigue | • Design notification center<br>• Define escalation procedures |
| **Global Navigation** | Unified portal with integrated access to all applications | Cohesive user experience; reduces training overhead | • Design global navigation (see UX Strategy) |
| **Multi-Tenancy** | **Runtime Applications**: Multi-tenant<br>**Design Applications**: To be determined (multiple proposals) | Balance resource efficiency with isolation requirements | 🚨 **Francesco Scarcelli**: Develop proposals for multi-account and multi-tenant architecture for Design apps |
| **Resource Sharing** | Projects with resource sharing capabilities | Enable collaboration and reuse | • Define sharing model and permissions<br>• Implement resource library |
| **Environments** | Flexible environment provisioning (minimum: dev, QA, prod) | Support customer testing and safe deployment practices | • Automate environment provisioning<br>• Implement environment promotion workflows |
| **Upgrade Responsibility** | Customer responsibility (with support from Doxee) | Encourage adoption of latest features; reduce support complexity | • Simplify upgrade process<br>• Provide upgrade testing tools |

### 4.2 Action Items from Positioning Decisions

**High Priority**:

1. **Enterprise SSO Investigation** (Owner: Marcello Generali)
   - Research enterprise SSO solutions for technical features and user management
   - Coordinate with Torelli, Spalla, Robert
   - Deliverable: Technical evaluation report

2. **Pricing Model Research** (Owner: Lorenzo Maselli)
   - Investigate enterprise SSO pricing models
   - Benchmark against competitors
   - Deliverable: Pricing recommendation document

3. **Multi-Tenancy Architecture Proposals** (Owner: Francesco Scarcelli)
   - Develop multiple proposals for:
     - Multi-account and multi-tenant for Runtime applications
     - Multi-account and single-account for Design applications
   - Deliverable: Architecture decision record (ADR) with trade-offs

**Medium Priority**:

4. **Enterprise Application UX Research** (Owner: Francesco Scarcelli)
   - Explore enterprise-level applications (BI solutions, BPM platforms)
   - Identify best practices for global navigation
   - Deliverable: UX benchmark report

5. **Documentation Strategy** (Owner: Product Team)
   - Prioritize content for public documentation portal
   - Establish gradual rollout plan
   - Deliverable: Documentation roadmap

6. **Support Model Implementation** (Owner: Support Team)
   - Train Doxee support agents for technical product requests
   - Develop training courses for customer first-level support
   - Implement service desk support portal
   - Deliverable: Support playbooks and training materials

---

## 5. UX Strategy

### 5.1 Unified Portal Vision

The strategic decision to create **ONE Portal** consolidates all Doxee applications into a cohesive platform experience. This is the highest priority UX initiative for the next planning cycle.

**Objectives**:
- Coherent user experience across all applications
- Reduce technical skills required to operate the platform
- Enable partners to fully operate (design → operations → monitoring → support → invoicing)
- Enable single-customer users to self-manage the platform
- Modernize UI to appeal to self-service users

### 5.2 Navigation Architecture

**Top-Level Structure**:

```
┌─────────────────────────────────────────────────────────────┐
│  Doxee Platform                          [Account ▾] [User]  │
├─────────────────────────────────────────────────────────────┤
│  Home | Design | Operate | Analyze | Support | Admin        │
└─────────────────────────────────────────────────────────────┘
```

**Home Page Components**:
- **Multi-Account Selector**: Switch between accounts/tenants
- **Quick Access**: Favorite and recent resources/portals
- **Activity Feed**: Recent changes, shared resources
- **What's New**: Release notes, feature announcements
- **Documentation**: Central access to help resources

**Application Families**:

| Family | Applications | Primary Personas |
|--------|-------------|------------------|
| **Design** | Process Designer, Data Transformation, Business Designer, Pvideo Designer, Workflow Designer, Output Management | Process Designer, Content Designer |
| **Operate** | Jobs Portal, Workplace, Digital Archiving, Endpoints | Operator, Business User |
| **Analyze** | BI Headlight Cloud, Analytics, Tracking & Reporting, Command Center | Analyst, Billing Manager, DevOps |
| **Support** | Service Desk, Logs, Documentation | Business User, Operator, Doxee Support |
| **Admin** | User Management, Settings, Billing, SSO Configuration | System Admin, Billing Manager |

### 5.3 User Journey Example: Technical Designer

This example illustrates the streamlined workflow enabled by the unified portal:

| Step | Current State (Multiple Portals) | Future State (Unified Portal) | Improvement |
|------|----------------------------------|-------------------------------|-------------|
| 1. Login | Separate login for each portal | Single SSO login | Reduced friction |
| 2. Context Selection | Implicit or unclear | Explicit account/workspace selection | Clear context |
| 3. Resource Access | Navigate to specific portal, then search | Global search or direct navigation | Faster access |
| 4. Work on Resources | Switch between disconnected tools | Integrated design environment with linked resources | Reduced context switching |
| 5. Test | Separate testing environment | Integrated test from design interface | Faster iteration |
| 6. Logout | Multiple sessions to manage | Single session | Security improvement |

**Main Steps**: Login → Select Account → Work on Resources → Test → Logout

### 5.4 Key UX Principles

1. **Progressive Disclosure**: Show complexity only when needed; prioritize common tasks
2. **Contextual Help**: In-app guidance specific to current task and user role
3. **Search-First**: Global search as primary navigation method for power users
4. **Responsive Design**: Full functionality on desktop; optimized views for tablet/mobile where appropriate
5. **Accessibility**: WCAG 2.1 AA compliance minimum
6. **Consistency**: Shared component library, design system, interaction patterns

### 5.5 Reference Materials

- **Wireframe Link**: [Whimsical - G7 Shaping the Future](https://whimsical.com/g7-shaping-the-future-JZkp7P79FEZnuZ66JisdG1)
- **Workflow Diagram**: See image in original documentation (WhatsApp Image 2024-01-18)

### 5.6 Next Steps

1. **UX Project Initiation**: Create dedicated project for unified portal wireframes and design system
2. **Senior UX Designer Hire**: Recruit experienced enterprise UX designer to lead unified portal design
3. **User Research**: Conduct usability studies with current users across all personas
4. **Design System Development**: Build shared component library in Figma and code
5. **Iterative Prototyping**: Develop high-fidelity prototypes for user testing

**🚨 Clarification Needed**:
- Phasing strategy: Which application families integrate first?
- Migration plan: How do existing users transition to unified portal?
- Mobile strategy: Which personas/workflows require native mobile apps vs. responsive web?

---

## 6. Future Innovation Opportunities

### 6.1 Overview

The following ideas represent future scenarios for product expansion, new markets, and disruptive technologies. These are exploratory concepts requiring further validation.

### 6.2 AI-Powered Capabilities

| Opportunity | Description | Potential Impact | Validation Needed |
|-------------|-------------|------------------|-------------------|
| **AI Content Generation** | Automated creation of personalized communication content using LLMs | Significantly reduce content creation time; enable hyper-personalization at scale | Customer interviews, POC with pilot customer |
| **AI Managed Processes/Channels** | Intelligent routing and optimization of communication channels based on user behavior | Improve engagement rates; reduce delivery costs | A/B testing with existing customers |
| **AI Assisted Migration Tools** | Automated migration from legacy CCM systems to Doxee | Reduce implementation time and cost; accelerate sales cycle | Partner with systems integrator for pilot |
| **AI Assisted Clustering** | Automatic segmentation of recipients based on behavior and preferences | Enable more targeted communications; improve personalization | Collaboration with analytics team; data science POC |
| **AI Data Mapping** | Intelligent mapping of data sources to Doxee data models | Simplify integrations; reduce implementation errors | Technical feasibility study |

### 6.3 New Business Models

| Opportunity | Description | Strategic Fit | Risks/Challenges |
|-------------|-------------|---------------|------------------|
| **Single Portal Selling** | Offer individual Doxee applications standalone via embedding/API/UI | Expand addressable market; lower entry price point | Potential cannibalization; architectural complexity |
| **Advertisement Network** | Provide personalized content slots for ad networks or sell anonymized engagement data | New revenue stream | Privacy concerns; brand risk; regulatory compliance |
| **E-Commerce Connectors** | Automated content generation for e-commerce product communications | Adjacent market expansion | Competitive landscape; different buyer persona |

### 6.4 Market Expansion

| Market | Rationale | Entry Strategy | Estimated Opportunity |
|--------|-----------|----------------|----------------------|
| **Marketing Automation** | Adjacent to CCM; overlapping use cases | Partner with marketing automation platforms; build connectors | Large market but highly competitive |
| **Data Transformation** | Leverage existing DT capabilities as standalone product | Offer as independent data integration tool | Niche market; potential high margins |
| **Document Collaboration** | Build on interactive document capabilities | Collaboration layer on top of Doxee documents | Competitive with established players |
| **Contract BI/Management** | Specialized application of document management for contracts | Vertical focus on legal/procurement departments | Growing market; requires domain expertise |

### 6.5 Strategic Opportunities

| Opportunity | Description | Strategic Value | Feasibility |
|-------------|-------------|----------------|-------------|
| **EU Electronic Identity Provider** | Become certified eID provider under eIDAS regulation | Strategic positioning in digital trust; regulatory compliance value | High regulatory burden; significant investment |

### 6.6 Next Steps for Innovation Pipeline

1. **Prioritization Workshop**: Apply RICE framework to innovation opportunities
2. **Technical Feasibility Studies**: Conduct POCs for AI-powered capabilities (Q2 2024)
3. **Market Research**: Validate demand for market expansion opportunities (Q2-Q3 2024)
4. **Strategic Partnerships**: Identify partners for co-development (ongoing)
5. **Innovation Budget**: Allocate R&D budget for experimentation (FY2025 planning)

---

## 7. Implementation Roadmap

### 7.1 2024 Priorities

**Q1-Q2 2024**:
- ✓ Jira Product Discovery setup and RICE formula finalization
- ✓ Current roadmap migration to Jira Product Discovery
- UX research and unified portal wireframes
- Enterprise SSO technical evaluation
- Multi-tenancy architecture proposals

**Q3-Q4 2024**:
- Unified portal design system development
- Senior UX Designer onboarding
- Public documentation portal (Phase 1)
- RICE formula calibration based on shipped features

### 7.2 2025 Roadmap (Directional)

**Timing**: Initiatives marked as "next" = 2025 (specific quarters TBD)
**Status**: Initiatives marked as "later" = still to be planned and confirmed

**Key Initiatives** (to be prioritized via RICE scoring):
- Unified portal development (multi-quarter initiative)
- Enterprise SSO implementation
- Multi-account/multi-tenant architecture refinement
- Partner portal capabilities
- AI-powered content generation (pilot)

### 7.3 Capacity Planning

**Process**:
- Roadmap managed in Jira Product Discovery
- Link column added to roadmap Excel for cross-referencing
- "Year" field in Discovery enables filtering (e.g., 2024-only view)
- RICE scoring required for current year initiatives only
- Future initiatives (2025+) captured without full scoring

**Migration from Excel to Jira Discovery**:
- ✓ 2024 initiatives migrated and scored
- 2025 initiatives captured but not scored (pending further planning)
- Collector epics (business epics, consolidation epics) not migrated to Discovery
- Excel roadmap maintained as legacy reference during transition

### 7.4 Governance & Review Cadence

| Activity | Frequency | Participants | Purpose |
|----------|-----------|--------------|---------|
| **RICE Scoring** | As needed for new ideas | PM, Tech Lead, CSM | Evaluate and score new initiatives |
| **Portfolio Review** | Quarterly | Product Leadership, CTO | Calibrate priorities; allocate capacity |
| **Roadmap Communication** | Quarterly | All stakeholders | Transparency; gather feedback |
| **Formula Calibration** | Bi-annually | Product Team | Adjust scoring based on outcomes |

---

## 8. Appendices

### 8.1 Reference Documents

| Document | Description | Link |
|----------|-------------|------|
| **RICE Formula Spreadsheet** | Excel workbook with RICE calculations and examples | [Confluence - RICE_formula.xlsx](https://code.doxee.com/confluence/download/attachments/155204967/RICE_formula.xlsx?version=1&modificationDate=1706095761258&api=v2) |
| **Extended RICE Experiment** | Weighted RICE formula experimentation | [SharePoint - dgandolfi Experiment](https://doxeemilano-my.sharepoint.com/:x:/g/personal/dgandolfi_doxee_com/ESrn7kMg35JEt-gFec_85jkBCWEvNOqhJrBtkYAJvUHsyw?e=4%3AqC8pjO&at=9&wdLOR=c31B2D16E-17C9-5640-9A4D-AD7E0D1448CA) |
| **Unified Portal Wireframes** | Whimsical board with navigation concepts | [Whimsical - G7 Shaping the Future](https://whimsical.com/g7-shaping-the-future-JZkp7P79FEZnuZ66JisdG1) |
| **Intercom RICE Article** | Industry best practice reference | [Intercom Blog - RICE Prioritization](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/) |

### 8.2 Summit Notes

**Doxee G7 Summit Agenda (January 2024)**

**Day 1 - January 17**:
- ✓ Overview of Tools (Naida)
- ✓ JIRA Product Discovery walkthrough (Naida)
- ✓ Product Management Tooling discussion (1 hour)
- ✓ Roadmapping methodology
- ✓ Prioritization definition (RICE Framework + extensions)
- ✓ Value definition process
- Meeting frequency discussion (outcome: TBD)

**Day 2 - January 18**:
- ✓ User Personas / Roles / Activities framework creation
- UX considerations discussion
- Application interconnections (e.g., data transformation searchable from process definition)
- ✓ Free brainstorming on future scenarios
  - New products, new markets, future state
  - Shaping the future of CCM/CXM
- ✓ ONE Portal (5-hour deep dive)
- ✓ Brainstorming: Doxee products in 5 years

**Day 3 - January 19**:
- ✓ Product vision definition
- Product positioning discussion
- Stakeholder engagement strategy
- Resource optimization
- Information gathering processes
- Competitive Landscape / Analyst relations (Lorenzo)
- Product Marketing approach

### 8.3 Key Contributors

**Product Management Team**:
- Monia Gazzano (multiple contributions to RICE formula, capacity planning, summit documentation)
- Naida (Jira Product Discovery lead)
- Lorenzo Maselli (competitive landscape, SSO pricing research)

**Technical Leadership**:
- Francesco Scarcelli (UX research, multi-tenancy architecture)
- Marcello Generali (SSO technical evaluation)

**Referenced Users/Stakeholders**:
- Ismaele Moretti (CSM, Analyst persona example)
- Julia Pekarova (Business User persona example)
- Multiple delivery and support team members

### 8.4 Glossary

| Term | Definition |
|------|------------|
| **CCM** | Customer Communications Management - software category for managing enterprise customer communications |
| **CXM** | Customer Experience Management - broader category encompassing all customer interactions |
| **RICE** | Reach, Impact, Confidence, Effort - prioritization framework |
| **PaaS** | Platform as a Service - deployment model with extensibility |
| **SaaS** | Software as a Service - fully managed deployment model |
| **SSO** | Single Sign-On - authentication approach using one set of credentials |
| **FLS** | First Level Support - initial customer support tier |
| **SLS** | Second Level Support - escalated technical support |
| **TLS** | Third Level Support - product engineering support for bugs |
| **IAM** | Identity and Access Management - security and access control |
| **eIDAS** | Electronic Identification, Authentication and Trust Services - EU regulation |

### 8.5 Calculation Examples

#### Standard RICE Score Example

**Feature**: Multi-language support in Business Designer

- **Reach**: 4 (60% of customers will use in first year)
- **Impact**: 3 (significant improvement; removes pain point)
- **Confidence**: 80% (0.8) (validated with customer interviews, but effort uncertain)
- **Effort**: 2 (150 person-days)

**RICE Score** = (4 × 3 × 0.8) / 2 = 9.6 / 2 = **4.8**

#### Extended RICE Score Example

**Feature**: Automated job retry mechanism

- **Reach**: 5 (all customers affected)
- **Impact**: 3 (significant improvement)
- **Confidence**: 100% (1.0) (clear requirements)
- **Effort**: 1 (80 person-days)
- **Cost Reducing**: 3 (saves 200 person-days/year in manual intervention = €60k)
- **Co-financing**: 0 (internal initiative)

**Extended Value** = ((5 × 3) + 3 + 0) × 1.0 / 1 = 18 / 1 = **18**

(Higher score due to cost reduction benefits)

---

## Document Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2024-01-19 | Summit Team | Initial notes from G7 Summit |
| 0.2 | 2024-02-02 | Monia Gazzano | Added Jira Discovery details, RICE formula refinements |
| 0.3 | 2024-02-29 | Monia Gazzano | Added cost reduction and co-financing scoring guidance |
| 0.4 | 2024-03-07 | Monia Gazzano | Added confidence percentage guidelines |
| 0.5 | 2024-03-13 | Monia Gazzano | Added experimental weighted RICE formula |
| 0.6 | 2024-04-04 | Monia Gazzano | Added capacity planning migration notes |
| 0.7 | 2024-07-17 | Monia Gazzano | Added 2025 roadmap timing clarification |
| 1.0 | 2026-02-06 | Product Team | Complete restructure: added industry best practices, detailed persona templates, section summaries, professional formatting |

---

## 🚨 Areas Requiring Stakeholder Clarification

The following items require input from leadership or cross-functional stakeholders:

1. **RICE Formula Finalization**
   - Confirm weights for experimental weighted RICE formula
   - Define process for initiatives > 500 person-days
   - Establish governance for scoring disputes

2. **Multi-Tenancy Architecture**
   - Review Francesco Scarcelli's proposals when available
   - Decide on multi-tenant vs. multi-account for Design applications
   - Define isolation requirements and trade-offs

3. **Unified Portal Phasing**
   - Prioritize which application families integrate first
   - Define migration plan for existing users
   - Clarify mobile strategy (responsive web vs. native apps)

4. **Stakeholder Visibility**
   - Define granularity levels for Sales and Delivery team access to Jira Discovery
   - Establish governance for Ideas visibility and commenting

5. **Meeting Frequency**
   - Finalize product management team meeting cadence (noted in agenda but not resolved)

6. **Pricing Model Details**
   - Define specific volume metrics per product
   - Establish role hierarchy for user-based pricing
   - Package support tiers and professional services add-ons

7. **Innovation Pipeline**
   - Prioritize AI-powered capabilities for POC
   - Allocate innovation budget for FY2025
   - Identify strategic partners for market expansion opportunities

---

*This document is maintained by the Doxee Product Management team. For questions or feedback, contact the Product Leadership team.*
