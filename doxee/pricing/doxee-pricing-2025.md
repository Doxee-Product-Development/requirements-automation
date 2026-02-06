# Doxee Group - Price Book 2025

> Reconstructed from `Salesforce_Listino-Prototipo-x-New-PriceBook-Doxee-Group-2025.xlsx`

---

## Table of Contents

1. [Pricing Philosophy](#pricing-philosophy)
2. [Spreadsheet Architecture](#spreadsheet-architecture)
3. [Product Code System](#product-code-system)
4. [Regional Entities](#regional-entities)
5. [Product Catalog](#product-catalog)
   - [Base-system](#1-base-system)
   - [User Licenses](#2-user-licenses)
   - [Production (Pages & pURLs)](#3-production)
   - [Community Size (Impressions)](#4-community-size)
   - [Digital Archiving](#5-digital-archiving)
   - [Other Solutions](#6-other-solutions)
   - [Distribution](#7-distribution)
   - [Printing](#8-printing)
   - [Embedded Services](#9-embedded-services)
   - [Professional Services](#10-professional-services)
   - [Intercompany](#11-intercompany)
6. [Pricing Mechanics](#pricing-mechanics)
7. [Salesforce CPQ Integration](#salesforce-cpq-integration)

---

## Pricing Philosophy

Doxee's pricing model is built around these core principles:

### 1. Platform + Volume-Based Consumption
The pricing separates the **platform license** (fixed annual subscription for the base system and deployment model) from **volume-based consumption** (pages, emails, SMS, pURLs, storage) that uses **tiered degressive pricing** — the per-unit cost decreases as volume increases.

### 2. Deployment-Model-Driven Base Pricing
The same platform functionality has different base prices depending on where it runs:
- **On-Premise**: Lowest cost (customer provides infrastructure)
- **Doxee-Cloud Shared (Multi-Tenant)**: Mid-range SaaS pricing
- **Doxee-Cloud Dedicated (Single Tenant)**: Premium cloud pricing
- **Public-Cloud Dedicated (Single Tenant)**: Highest cost (AWS/Azure dedicated)
- **Public-Cloud Shared (Multi-Tenant)**: Between shared and dedicated

### 3. Three Business Models
| Code | Model | Billing Pattern |
|------|-------|-----------------|
| **TE** | Technology (Platform) | Annual subscription |
| **ES** | Embedded Services | Annual subscription (often % of total) |
| **PS** | Professional Services | One-shot (per day) |

### 4. Tiered Volume Pricing (Block Pricing)
Volume-based products (pages, emails, SMS, pURLs, storage, signatures) use **cumulative tiered pricing**:
- Each tier covers a volume range (e.g., 0–1M pages, 1.01–2M pages, etc.)
- The per-unit price decreases at each higher tier
- Each tier is a separate line item; the customer selects the quantity of units falling within each tier
- Every volume product includes a **"Free" tier** (€0) as a placeholder for zero-consumption scenarios

### 5. Percent-of-Total Add-ons
Some services (Sandbox environment, Premium Support, 24/7 Support, Premium KPI) are priced as a **percentage of the net subscription total** rather than a fixed price — ensuring they scale with contract size.

### 6. Uniform Pricing Across Regions
All three entities (Italy, Austria, Germany) share **identical list prices**. The only differences are:
- The **company name** in the code (DOXEE, INFINICA, DOXEE-DE)
- The **country code** in the product code (IT, AT, DE)
- AT and DE have extra **Intercompany** line items for intra-group services

---

## Spreadsheet Architecture

### Sheets
| Sheet | Entity | Company | Country Code |
|-------|--------|---------|--------------|
| Listino-Prototipo - Doxee SpA | Doxee SpA (Italy) | DOXEE | IT |
| Listino-Prototipo - Doxee-AT | Infinica (Austria) | INFINICA | AT |
| Listino-Prototipo - Doxee-DE | Doxee DE (Germany) | DOXEE-DE | DE |

### Row Structure
- **Rows 1–4**: Salesforce field mappings (API names, labels, object types)
- **Row 5**: Italian labels for the price list
- **Row 6**: Column role hints (`(feature)` for Category, `(option)` for Description)
- **Rows 7+**: Product data organized in **parent/child groups**

### Column Layout (52 columns, A–AZ)

| Column | Field | Purpose |
|--------|-------|---------|
| A | Role | `Prodotto Padre: <...>` for parents, `figlio` for children |
| B | IsActive | Always `TRUE` for active items |
| C | PriceEditable | Whether price can be changed in quotes |
| D | QuantityEditable | Whether quantity can be changed in quotes |
| E | Ad Hoc | Custom item flag |
| F | Contratto | Contract code base (e.g., `EN-IT-TE-DPBS`) |
| G | Clausole | Clause number (child tier identifier) |
| H | Versione | Version number (always `1`) |
| I | Lingua | Language code (e.g., `EN-`) |
| J | Company | Entity name (DOXEE, INFINICA, DOXEE-DE) |
| K | Product Code | **Computed**: `=F` (parents) or `=CONCATENATE(F,G,".",H)` (children) |
| L | Business Model | TE, ES, PS, or GEN |
| M | Product Line | DP (Doxee Platform), 3P (Third Party), ES, PS, GEN |
| N | Product Parent Name | Groups children under parent |
| O | Prodotto | Product family name |
| P | Product Category | Feature/deployment grouping |
| Q | Product Name | Display name |
| R | Product Item | Item name |
| S | Product Description | Variant/deployment description |
| T | Default Quantity | Default quantity |
| U | Min Quantity | Minimum allowed quantity |
| V | Max Quantity | Maximum allowed quantity |
| W | UDM | Unit of measure (No, Pages, Mail, SMS, pURL, GB, Document, Signature, Days) |
| X | Tipo | Subscription, Pay Per Use, or One Shot |
| Y | List Price | Price in EUR |
| Z | Percent Of Total Category | `Base` for subscription items |
| AA | Pricing Method | `List` or `Percent Of Total` |
| AB | Percent Of Total Base | `Net` (when pricing method is Percent Of Total) |
| AC | Percent Of Total (%) | The percentage value (e.g., 0.10 = 10%) |
| AD | Exclude From Percent Of Total | Whether this item is excluded from % calculations |
| AE | Max Discount 1 | Maximum discount for direct sales |
| AF | Max Discount 2 | Maximum discount for reseller/partner |
| AG | Periodicità | `Annual` or `One Shot` |
| AH | CodArtCosto | Cost article code for accounting |
| AI–AZ | Salesforce CPQ fields | Configuration, features, options, record types, etc. |

### Key Formulas

| Formula | Used In | Purpose |
|---------|---------|---------|
| `=F7` (parent row) | Column K (parents) | Parent product code = contract code |
| `=CONCATENATE(F,G,".",H)` | Column K (children) | Child code = contract + clause + version |
| `=F<parent_row>` | Column F (children) | Inherit contract code from parent |
| `=L<prev_row>`, `=M<prev_row>`, etc. | Columns L, M, N, O | Inherit business model, line, parent from row above |
| `=IF(A="figlio","Accessory","")` | Column AO | Mark children as Accessories in CPQ |
| `=$J$7` | Column J (parents) | All parents reference the company from row 7 |

---

## Product Code System

Product codes follow the pattern:

```
EN-{COUNTRY}-{BIZ_MODEL}-{PRODUCT_LINE}{PRODUCT}{CLAUSE}.{VERSION}
```

### Segments

| Segment | Values | Meaning |
|---------|--------|---------|
| Language | `EN` | English (all products) |
| Country | `IT`, `AT`, `DE` | Legal entity / market |
| Business Model | `TE`, `ES`, `PS`, `GE` | Technology, Embedded Services, Professional Services, General |
| Product Line | `DP`, `3P` (as `TP`), `ES`, `PS`, `GE` (as `GE`) | Doxee Platform, Third Party, Embedded Svc, Prof Svc, General |
| Product | `BS`, `UL`, `PD`, `CS`, `DA`, `OS`, `DS`, `PR`, `ES`, `PS`, `IC` | See product table below |
| Clause | Number | Tier/variant identifier |
| Version | `1` | Always 1 |

### Product Abbreviations

| Code | Product |
|------|---------|
| DPBS | Doxee Platform - Base-system |
| DPUL | Doxee Platform - User Licenses |
| DPPD | Doxee Platform - Production |
| DPCS | Doxee Platform - Community Size |
| DPDA | Doxee Platform - Digital Archiving |
| DPOS | Doxee Platform - Other Solutions |
| TPDS | Third Party - Distribution |
| TPPR | Third Party - Printing |
| ESES | Embedded Services |
| PSPS | Professional Services |
| GEIC | General - Intercompany |

### Clause Numbering Convention

Clauses group deployment models or tiers within a product:

| Clause Range | Meaning |
|-------------|---------|
| 1 | On-Premise |
| 10–11 | Doxee-Cloud (10=Dedicated, 11=Shared) |
| 20–22 | Public-Cloud (20=Dedicated, 21=Shared, etc.) |
| 30 | Sandbox / Special |
| 1–15 | Sequential tiers (for volume products) |
| 50–63 | pURL production tiers |
| 100–101 | SERC/SERCQ |
| 200 | Physical Delivery |

**Example**: `EN-IT-TE-DPPD3.1` = English, Italy, Technology, Doxee Platform Production, clause 3 (5M pages tier), version 1

---

## Regional Entities

| Entity | Company | Country | Specifics |
|--------|---------|---------|-----------|
| **Doxee SpA** | DOXEE | IT (Italy) | HQ. Master price list. |
| **Infinica** | INFINICA | AT (Austria) | Same prices. Has intercompany PS items + Royalties. |
| **Doxee DE** | DOXEE-DE | DE (Germany) | Same prices. Has intercompany PS items + Royalties. |

AT and DE additionally have:
- **Intercompany Professional Services** (PS product family) — with a €340/day rate for Italy-based resources
- **Intercompany Royalties** (GEN product family) — for EU intra-group royalties

---

## Product Catalog

### 1. Base-system

**Parent**: `EN-{CC}-TE-DPBS` | Business Model: TE | Product Line: DP

The mandatory platform subscription — every customer needs exactly one base-system.

| Category | Description | Price (€/year) | Code Suffix |
|----------|-------------|----------------|-------------|
| On-Premise | Customer-hosted | 15,000 | 1.1 |
| Doxee-Cloud Dedicated | Single Tenant | 100,000 | 10.1 |
| Doxee-Cloud Shared | Multi Tenant | 20,000 | 11.1 |
| Public-Cloud Dedicated | Single Tenant | 125,000 | 20.1 |
| Public-Cloud Shared | Multi Tenant | 45,000 | 21.1 |
| Sandbox | Dev/Test environment | **10% of Net** | 30.1 |

- Quantity: Fixed at 1 (min=1, max=1)
- UDM: No (not volume-based)
- Type: Subscription (Annual)
- Sandbox uses **Percent Of Total** pricing (10% of the Net subscription value)
- Cost Code: C-LIC

---

### 2. User Licenses

**Parent**: `EN-{CC}-TE-DPUL` | Business Model: TE | Product Line: DP

Per-user annual licenses for platform roles. Quantity is editable.

| Category | Role | Price (€/user/year) | Qty Range | Code Suffix |
|----------|------|---------------------|-----------|-------------|
| Process Designer | Process Designer User | 3,000 | 1–9,999 | 1.1 |
| Communication Designer | Communication Designer User | 2,000 | 1–9,999 | 10.1 |
| Workplace/Composer/Archive | 1 to 50 users | 650 | 1–50 | 20.1 |
| Workplace/Composer/Archive | 51 to 250 users | 550 | 51–250 | 21.1 |
| Workplace/Composer/Archive | 251 to 999 users | 450 | 251–999 | 22.1 |
| Workplace/Composer/Archive | Free | 0 | 1–9,999 | 23.1 |

- UDM: No (per user)
- Type: Subscription (Annual)
- The Free tier (23.1) has both Price and Quantity editable and is marked Ad Hoc
- Cost Code: C-LIC

**Volume discount**: Workplace/Composer/Archive users get cheaper per-seat pricing at higher tiers (€650 -> €550 -> €450).

---

### 3. Production

**Parent**: `EN-{CC}-TE-DPPD` | Business Model: TE | Product Line: DP

Volume-based document and pURL production, priced per million pages or per thousand pURLs.

#### 3a. Page Production (in millions of pages)

| Tier | Volume Range | Price (€/M pages/year) | Code Suffix |
|------|-------------|------------------------|-------------|
| 1 | 0 – 1M | 14,000 | 1.1 |
| 2 | 1.01 – 2M | 9,500 | 2.1 |
| 3 | 2.01 – 5M | 6,400 | 3.1 |
| 4 | 5.01 – 10M | 4,200 | 4.1 |
| 5 | 10.01 – 15M | 3,267 | 5.1 |
| 6 | 15.01 – 20M | 2,950 | 6.1 |
| 7 | 20.01 – 30M | 2,633 | 7.1 |
| 8 | 30.01 – 50M | 2,400 | 8.1 |
| 9 | 50.01 – 75M | 2,200 | 9.1 |
| 10 | 75.01 – 100M | 2,100 | 10.1 |
| 11 | 100.01 – 150M | 1,967 | 11.1 |
| 12 | 150.01 – 200M | 1,875 | 12.1 |
| 13 | 200.01 – 300M | 1,850 | 13.1 |
| 14 | 300.01 – 500M | 1,840 | 14.1 |
| Free | 0 (placeholder) | 0 | 15.1 |

- UDM: Pages
- Cost Code: C-PPAG
- Price degression: ~86% reduction from tier 1 to tier 14

#### 3b. Personalized URL (pURL) Production (in thousands)

| Tier | Volume Range | Price (€/K pURLs/year) | Code Suffix |
|------|-------------|------------------------|-------------|
| 1 | 0 – 10K | 700 | 50.1 |
| 2 | 10.01 – 50K | 300 | 51.1 |
| 3 | 50.01 – 100K | 225 | 52.1 |
| 4 | 100.01 – 200K | 165 | 53.1 |
| 5 | 200.01 – 500K | 80 | 54.1 |
| 6 | 500.01 – 1,000K | 50 | 55.1 |
| 7 | 1,000.01 – 2,000K | 30 | 56.1 |
| 8 | 2,000.01 – 5,000K | 18 | 57.1 |
| 9 | 5,000.01 – 10,000K | 14 | 58.1 |
| 10 | 10,000.01 – 20,000K | 11 | 59.1 |
| 11 | 20,000.01 – 30,000K | 8 | 60.1 |
| 12 | 30,000.01 – 50,000K | 6 | 61.1 |
| 13 | 50,000.01 – 100,000K | 5 | 62.1 |
| Free | 0 (placeholder) | 0 | 63.1 |

- UDM: pURL
- Cost Code: C-PURL
- Price degression: ~99% reduction from tier 1 to tier 13

---

### 4. Community Size

**Parent**: `EN-{CC}-TE-DPCS` | Business Model: TE | Product Line: DP

Personalized URL impressions (views/visits), priced per thousand impressions.

| Tier | Volume Range | Price (€/K impressions/year) | Code Suffix |
|------|-------------|------------------------------|-------------|
| 1 | 0 – 150K | 100 | 1.1 |
| 2 | 150.01 – 300K | 75 | 2.1 |
| 3 | 300.01 – 600K | 55 | 3.1 |
| 4 | 600.01 – 1,500K | 27 | 4.1 |
| 5 | 1,500.01 – 3,000K | 17 | 5.1 |
| 6 | 3,000.01 – 6,000K | 10 | 6.1 |
| 7 | 6,000.01 – 15,000K | 6 | 7.1 |
| 8 | 15,000.01 – 30,000K | 5 | 8.1 |
| 9 | 30,000.01 – 60,000K | 4 | 9.1 |
| 10 | 60,000.01 – 90,000K | 3 | 10.1 |
| 11 | 90,000.01 – 150,000K | 2 | 11.1 |
| 12 | 150,000.01 – 300,000K | 2 | 12.1 |
| Free | 0 (placeholder) | 0 | 13.1 |

- UDM: pURL
- Cost Code: C-PURL
- Price degression: 98% reduction from tier 1 to tier 12

---

### 5. Digital Archiving

**Parent**: `EN-{CC}-TE-DPDA` | Business Model: TE | Product Line: DP

Cloud storage for digital archives, priced per GB with equivalent page counts.

| Tier | Storage Range | Equiv. Pages | Price (€/GB/year) | Code Suffix |
|------|--------------|--------------|---------------------|-------------|
| 1 | 0 – 40 GB | 1M | 2,000 | 1.1 |
| 2 | 40.01 – 80 GB | 2M | 1,750 | 2.1 |
| 3 | 80.01 – 200 GB | 5M | 1,100 | 3.1 |
| 4 | 200.01 – 400 GB | 10M | 750 | 4.1 |
| 5 | 400.01 – 600 GB | 15M | 600 | 5.1 |
| 6 | 600.01 – 800 GB | 20M | 550 | 6.1 |
| 7 | 800.01 – 1,200 GB | 30M | 433 | 7.1 |
| 8 | 1,201.01 – 2,000 GB | 50M | 300 | 8.1 |
| 9 | 2,001.01 – 3,000 GB | 75M | 240 | 9.1 |
| 10 | 3,001.01 – 4,000 GB | 100M | 210 | 10.1 |
| 11 | 4,001.01 – 6,000 GB | 150M | 200 | 11.1 |
| 12 | 6,001.01 – 8,000 GB | 200M | 190 | 12.1 |
| 13 | 8,001.01 – 12,000 GB | 300M | 180 | 13.1 |
| 14 | 12,001.01 – 20,000 GB | 500M | 172 | 14.1 |
| Free | 0 (placeholder) | — | 0 | 15.1 |

- UDM: GB
- Cost Code: C-DAGB
- Approximate ratio: ~25 pages per KB, or ~40 GB per 1M pages

---

### 6. Other Solutions

**Parent**: `EN-{CC}-TE-DPOS` | Business Model: TE | Product Line: DP

Italy-specific compliance solutions. All are **Free** line items (priced separately or included).

| Category | Description | UDM | Code Suffix |
|----------|-------------|-----|-------------|
| Legal Electronic Archive | Conservazione digitale (in thousands) | GB | 1.1 |
| Electronic Invoicing | Fatturazione Elettronica - send/receive XML (in thousands) | Document | 30.1 |
| Electronic Ordering | Ordine Elettronico - receive XML (in thousands) | Document | 60.1 |

- All prices: €0 (Free placeholder)
- Cost Codes: C-DAGB (archive), C-PDOC (invoicing, ordering)

---

### 7. Distribution

**Parent**: `EN-{CC}-TE-TPDS` | Business Model: TE | Product Line: 3P (Third Party)

Multi-channel distribution services covering email, SMS, electronic signatures, certified mail, and physical delivery.

#### 7a. Email Distribution (in millions of sendings)

| Tier | Volume Range | Price (€/M emails/year) | Code Suffix |
|------|-------------|-------------------------|-------------|
| 1 | 0 – 1M | 4,500 | 1.1 |
| 2 | 1.01 – 2M | 2,500 | 2.1 |
| 3 | 2.01 – 5M | 1,400 | 3.1 |
| 4 | 5.01 – 10M | 1,100 | 4.1 |
| 5 | 10.01 – 15M | 1,000 | 5.1 |
| 6 | 15.01 – 20M | 910 | 6.1 |
| 7 | 20.01 – 30M | 830 | 7.1 |
| 8 | 30.01 – 50M | 758 | 8.1 |
| 9 | 50.01 – 75M | 693 | 9.1 |
| 10 | 75.01 – 100M | 645 | 10.1 |
| 11 | 100.01 – 150M | 600 | 11.1 |
| 12 | 150.01 – 200M | 575 | 12.1 |
| 13 | 200.01 – 300M | 550 | 13.1 |
| 14 | 300.01 – 500M | 540 | 14.1 |
| Free | 0 (placeholder) | 0 | 15.1 |

- UDM: Mail
- Cost Code: C-MAIL

#### 7b. SMS Distribution (in thousands of sendings)

| Tier | Volume Range | Price (€/K SMS/year) | Code Suffix |
|------|-------------|----------------------|-------------|
| 1 | 0 – 100K | 80.00 | 30.1 |
| 2 | 100.01 – 200K | 62.50 | 31.1 |
| 3 | 200.01 – 500K | 55.00 | 32.1 |
| 4 | 500.01 – 1,000K | 52.00 | 33.1 |
| 5 | 1,000.01 – 2,000K | 50.00 | 34.1 |
| 6 | 2,000.01 – 5,000K | 47.00 | 35.1 |
| 7 | 5,000.01 – 10,000K | 45.00 | 36.1 |
| 8 | 10,000.01 – 15,000K | 43.33 | 37.1 |
| 9 | 15,000.01 – 20,000K | 42.50 | 38.1 |
| 10 | 20,000.01 – 30,000K | 41.67 | 39.1 |
| 11 | 30,000.01 – 50,000K | 41.00 | 40.1 |
| 12 | 50,000.01 – 75,000K | 40.67 | 41.1 |
| 13 | 75,000.01 – 100,000K | 40.00 | 42.1 |
| Free | 0 (placeholder) | 0 | 43.1 |

- UDM: SMS
- Cost Code: C-SMS

#### 7c. Electronic Signatures — Scrive (in thousands)

| Tier | Volume Range | Price (€/K signatures/year) | Code Suffix |
|------|-------------|----------------------------|-------------|
| 1 | 0 – 1K | 1.33 | 60.1 |
| 2 | 1.01 – 3K | 1.21 | 61.1 |
| 3 | 3.01 – 6K | 1.10 | 62.1 |
| 4 | 6.01 – 15K | 0.81 | 63.1 |
| 5 | 15.01 – 30K | 0.72 | 64.1 |
| 6 | 30.01 – 60K | 0.61 | 65.1 |
| 7 | 60.01 – 120K | 0.52 | 66.1 |
| 8 | 120.01 – 180K | 0.52 | 67.1 |
| Free | 1+ (placeholder) | 0 | 68.1 |

- UDM: Signature
- Cost Code: C-MAIL (shared with email)

#### 7d. Certified Mail (SERC / SERCQ)

| Type | Description | Price (€/unit) | UDM | Code Suffix |
|------|-------------|----------------|-----|-------------|
| SERC | Tnotice (standard certified) | 1.23 | Mail | 100.1 |
| SERCQ | TnoticeQ (qualified certified) | 1.94 | Mail | 101.1 |

- Type: **Pay Per Use** (not subscription)
- Cost Code: C-TNOTICE

#### 7e. Physical Delivery

| Type | Description | Price | Code Suffix |
|------|-------------|-------|-------------|
| Physical Delivery | Physical mail delivery | €0 (Free) | 200.1 |

- Type: Pay Per Use
- Cost Code: C-PORTO1AM

---

### 8. Printing

**Parent**: `EN-{CC}-TE-TPPR` | Business Model: TE | Product Line: 3P

| Type | Description | Price | UDM | Code Suffix |
|------|-------------|-------|-----|-------------|
| Physical Printing | Physical printing (in pages) | Free | Pages | 1.1 |

- Type: Pay Per Use
- Cost Code: C-STCOL
- This is a placeholder — physical printing is priced via separate arrangements

---

### 9. Embedded Services

**Parent**: `EN-{CC}-ES-ESES` | Business Model: ES | Product Line: ES

Support, managed services, and training bundled with the platform.

| Category | Description | Price | Pricing Method | Code Suffix |
|----------|-------------|-------|----------------|-------------|
| Premium Support | Premium Support Plan | **10% of Net** | Percent Of Total | 1.1 |
| 24/7 Support | 24/7 Support incl. Premium | **20% of Net** | Percent Of Total | 10.1 |
| Managed Services | Per FTE | €100,000/FTE/year | List | 20.1 |
| Premium Production KPI | Premium KPI | **25% of Net** | Percent Of Total | 30.1 |
| Customer-Specific KPI | Custom KPI | €0 (Free) | List | 40.1 |
| Doxee University | e-Learning | €3,000/year | List | 50.1 |

- Record Type: Support Service
- Cost Code: C-PS (except Doxee University: C-LIC)
- Percent Of Total items calculate on the **Net** subscription base

---

### 10. Professional Services

**Parent**: `EN-{CC}-PS-PSPS` | Business Model: PS | Product Line: PS

One-time project delivery services, billed per day.

| Category | Level | Price (€/day) | Code Suffix |
|----------|-------|---------------|-------------|
| Professional Services | Free (placeholder) | 0 | 40.1 |
| Professional Services Custom | Level 1 (Junior) | 350 | 50.1 |
| Professional Services Custom | Level 2 (Mid) | 400 | 51.1 |
| Professional Services Custom | Level 3 (Senior) | 500 | 52.1 |
| Professional Services Custom | Level 4 (Expert) | 650 | 53.1 |

- UDM: Days
- Type: One Shot
- Period: One Shot (not recurring)
- Record Type: Professional Services
- Cost Code: C-PS

---

### 11. Intercompany

**Parent**: `EN-{CC}-GE-GEIC` | Business Model: GEN | Product Line: GEN

Internal group transfers. Present in all sheets, but AT and DE have additional items.

#### All Entities
| Category | Description | Price | Code Suffix |
|----------|-------------|-------|-------------|
| Royalties | Intercompany Royalties for EU | Free | 1.1 |

#### AT and DE Only (Intercompany Professional Services)

**Parent**: `EN-{CC}-PS-PSIC`

| Category | Description | Price (€/day) | Code Suffix |
|----------|-------------|---------------|-------------|
| Intercompany PS | Free (placeholder) | 0 | 1.1 |
| Intercompany PS | For EU (only for Italy resources) | 340 | 2.1 |

---

## Pricing Mechanics

### How Tiered Volume Pricing Works

For volume products (pages, emails, SMS, pURLs, storage, signatures), the pricing uses a **block/tiered model**:

1. **Customer estimates annual volume** (e.g., 8 million pages)
2. **Multiple tiers are selected** to cover the full volume:
   - Tier 1 (0–1M): 1 unit x €14,000 = €14,000
   - Tier 2 (1.01–2M): 1 unit x €9,500 = €9,500
   - Tier 3 (2.01–5M): 3 units x €6,400 = €19,200
   - Tier 4 (5.01–10M): 3 units x €4,200 = €12,600
   - **Total**: €55,300 for 8M pages
3. Each tier is a **separate line item** in the Salesforce quote

### Percent-of-Total Pricing

Some services are priced as a percentage of the total subscription value:

```
Service Price = Net Subscription Total × Percentage
```

| Service | Percentage | Base |
|---------|-----------|------|
| Sandbox Environment | 10% | Net |
| Premium Support | 10% | Net |
| 24/7 Support | 20% | Net |
| Premium Production KPI | 25% | Net |

These items have:
- `Pricing Method = Percent Of Total`
- `Percent Of Total Base = Net`
- `Percent Of Total (%) = 0.10` (or 0.20, 0.25)

### Subscription vs. Pay-Per-Use vs. One-Shot

| Type | Billing | Period | Examples |
|------|---------|--------|----------|
| **Subscription** | Recurring annual fee | Annual | Base-system, licenses, production tiers, distribution |
| **Pay Per Use** | Per-transaction billing | Annual (commitment period) | SERC, SERCQ, physical delivery, printing |
| **One Shot** | One-time fee | One Shot | Professional services |

---

## Salesforce CPQ Integration

The spreadsheet is designed as a direct import template for **Salesforce CPQ (Steelbrick/SBQQ)**:

### Product Hierarchy
- **Parent Products** (`RecordType = Parent Product`): Grouping containers, always €0 price
- **Child Products** (`Component = TRUE`): Actual sellable items, configured as **Accessories** (`Type = Accessory`)

### CPQ Configuration
| Field | Value | Meaning |
|-------|-------|---------|
| SBQQ__ConfigurationType__c | — | Bundle configuration |
| SBQQ__ConfigurationEvent__c | — | When to configure |
| SBQQ__OptionSelectionMethod__c | — | How options are selected |
| SBQQ__Component__c | TRUE/FALSE | Whether item is a bundle component |
| SBQQ__PriceEditable__c | TRUE/FALSE | Can sales modify price |
| SBQQ__QuantityEditable__c | TRUE/FALSE | Can sales modify quantity |
| SBQQ__ExcludeFromMaintenance__c | TRUE/FALSE | Exclude from % of total calculations |
| SBQQ__BlockPricingField__c | — | Field used for block pricing |
| SBQQ__Hidden__c | — | Hide from quote output |

### Price Books
Each entity has its own Salesforce Price Book:
- `Pricebook2Id` (Real PriceBook) — the entity-specific price book
- `Pricebook2Id` (Standard) — the Salesforce standard price book
- `UseStandardPrice` — whether to inherit from standard

### Record Types
| Record Type | Used For |
|-------------|----------|
| Parent Product | Product bundle containers |
| License (On-Premise) | On-premise software licenses |
| Managed Services (Cloud) | Cloud/SaaS subscriptions |
| Support Service | Embedded services (support, KPI, training) |
| Professional Services | One-time project delivery |

### Cost Article Codes (for ERP/Accounting)

| Code | Category |
|------|----------|
| C-LIC | Software licenses & base-system |
| C-PPAG | Page production |
| C-PURL | pURL production & community |
| C-DAGB | Digital archive storage |
| C-PDOC | Document processing (e-invoicing, e-ordering) |
| C-MAIL | Email distribution & signatures |
| C-SMS | SMS distribution |
| C-TNOTICE | Certified mail (SERC/SERCQ) |
| C-PORTO1AM | Physical delivery |
| C-STCOL | Physical printing |
| C-PS | Professional services & support |
