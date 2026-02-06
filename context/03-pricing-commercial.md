# Context Bible: Pricing & Commercial Model

> Compressed from: `doxee-pricing-2025.md` (Price Book 2025) + `Doxee-SaaS-ServiceTerms-Exhibit-4-KPI.md` (KPI Exhibit v1.0 2024-04-17)
> Sources: Salesforce_Listino-Prototipo-x-New-PriceBook-Doxee-Group-2025.xlsx; Service Terms Exhibit 4

---

## 1. Pricing Philosophy

**Platform + Consumption model**: fixed annual platform subscription + tiered degressive volume pricing (per-unit cost decreases with volume). Every volume product includes a Free tier (EUR 0) as placeholder.

**Three Business Models**:

| Code | Model | Billing |
|------|-------|---------|
| TE | Technology (Platform) | Annual subscription |
| ES | Embedded Services | Annual subscription (often % of total) |
| PS | Professional Services | One-shot (per day) |

**Deployment-model price hierarchy** (lowest to highest): On-Premise < Doxee-Cloud Shared (multi-tenant) < Public-Cloud Shared (multi-tenant) < Doxee-Cloud Dedicated (single-tenant) < Public-Cloud Dedicated (single-tenant).

**Percent-of-Total add-ons**: Sandbox, Premium Support, 24/7 Support, Premium KPI -- priced as % of net subscription total, scaling with contract size.

**Uniform pricing across regions**: IT/AT/DE share identical list prices. Only differences: company name, country code, and AT/DE have intercompany line items.

---

## 2. Product Code Structure

```
{LANG}-{COUNTRY}-{MODEL}-{PRODUCT}{TIER}.{VERSION}
```

| Segment | Values | Notes |
|---------|--------|-------|
| LANG | `EN` | Always English |
| COUNTRY | `IT`, `AT`, `DE` | Legal entity |
| MODEL | `TE`, `ES`, `PS`, `GE` | Business model |
| PRODUCT | `DPBS`, `DPUL`, `DPPD`, `DPCS`, `DPDA`, `DPOS`, `TPDS`, `TPPR`, `ESES`, `PSPS`, `GEIC` | See catalog below |
| TIER | Number | Clause/tier identifier |
| VERSION | `1` | Always 1 |

**Clause numbering**: 1=On-Premise; 10-11=Doxee-Cloud (10=Dedicated, 11=Shared); 20-22=Public-Cloud (20=Dedicated, 21=Shared); 30=Sandbox/Special; 50-63=pURL tiers; 100-101=SERC/SERCQ; 200=Physical Delivery.

**Example**: `EN-IT-TE-DPPD3.1` = Italy, Technology, Production, tier 3 (5M pages), v1.

---

## 3. Regional Entities

| Entity | Company Code | Country | Notes |
|--------|-------------|---------|-------|
| Doxee SpA | DOXEE | IT | HQ, master price list |
| Infinica | INFINICA | AT | +intercompany PS (EUR 340/day) + royalties |
| Doxee DE | DOXEE-DE | DE | +intercompany PS (EUR 340/day) + royalties |

---

## 4. Product Catalog

### 4.1 Base-system (DPBS) -- TE/DP

Mandatory platform subscription. Qty fixed at 1. Annual. Cost: C-LIC.

<!-- SENSITIVE: Commercial list prices -->

| Deployment | EUR/year | Code Suffix |
|-----------|----------|-------------|
| On-Premise | 15,000 | 1.1 |
| Doxee-Cloud Dedicated (ST) | 100,000 | 10.1 |
| Doxee-Cloud Shared (MT) | 20,000 | 11.1 |
| Public-Cloud Dedicated (ST) | 125,000 | 20.1 |
| Public-Cloud Shared (MT) | 45,000 | 21.1 |
| Sandbox | **10% of Net** | 30.1 |

### 4.2 User Licenses (DPUL) -- TE/DP

Per-user annual. Cost: C-LIC.

<!-- SENSITIVE: Commercial list prices -->

| Role | EUR/user/year | Qty Range | Suffix |
|------|--------------|-----------|--------|
| Process Designer | 3,000 | 1-9,999 | 1.1 |
| Communication Designer | 2,000 | 1-9,999 | 10.1 |
| Workplace/Composer/Archive 1-50 | 650 | 1-50 | 20.1 |
| Workplace/Composer/Archive 51-250 | 550 | 51-250 | 21.1 |
| Workplace/Composer/Archive 251-999 | 450 | 251-999 | 22.1 |
| Free (placeholder) | 0 | 1-9,999 | 23.1 |

### 4.3 Production (DPPD) -- TE/DP

#### Page Production (EUR per M pages/year) -- UDM: Pages, Cost: C-PPAG

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/M | Suffix |
|------|--------|-------|--------|
| 1 | 0-1M | 14,000 | 1.1 |
| 2 | 1.01-2M | 9,500 | 2.1 |
| 3 | 2.01-5M | 6,400 | 3.1 |
| 4 | 5.01-10M | 4,200 | 4.1 |
| 5 | 10.01-15M | 3,267 | 5.1 |
| 6 | 15.01-20M | 2,950 | 6.1 |
| 7 | 20.01-30M | 2,633 | 7.1 |
| 8 | 30.01-50M | 2,400 | 8.1 |
| 9 | 50.01-75M | 2,200 | 9.1 |
| 10 | 75.01-100M | 2,100 | 10.1 |
| 11 | 100.01-150M | 1,967 | 11.1 |
| 12 | 150.01-200M | 1,875 | 12.1 |
| 13 | 200.01-300M | 1,850 | 13.1 |
| 14 | 300.01-500M | 1,840 | 14.1 |
| Free | 0 | 0 | 15.1 |

~86% price degression tier 1 to 14.

#### pURL Production (EUR per K pURLs/year) -- UDM: pURL, Cost: C-PURL

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/K | Suffix |
|------|--------|-------|--------|
| 1 | 0-10K | 700 | 50.1 |
| 2 | 10.01-50K | 300 | 51.1 |
| 3 | 50.01-100K | 225 | 52.1 |
| 4 | 100.01-200K | 165 | 53.1 |
| 5 | 200.01-500K | 80 | 54.1 |
| 6 | 500.01-1,000K | 50 | 55.1 |
| 7 | 1,000.01-2,000K | 30 | 56.1 |
| 8 | 2,000.01-5,000K | 18 | 57.1 |
| 9 | 5,000.01-10,000K | 14 | 58.1 |
| 10 | 10,000.01-20,000K | 11 | 59.1 |
| 11 | 20,000.01-30,000K | 8 | 60.1 |
| 12 | 30,000.01-50,000K | 6 | 61.1 |
| 13 | 50,000.01-100,000K | 5 | 62.1 |
| Free | 0 | 0 | 63.1 |

~99% price degression tier 1 to 13.

### 4.4 Community Size (DPCS) -- TE/DP

pURL impressions (EUR per K impressions/year). UDM: pURL, Cost: C-PURL.

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/K | Suffix |
|------|--------|-------|--------|
| 1 | 0-150K | 100 | 1.1 |
| 2 | 150.01-300K | 75 | 2.1 |
| 3 | 300.01-600K | 55 | 3.1 |
| 4 | 600.01-1,500K | 27 | 4.1 |
| 5 | 1,500.01-3,000K | 17 | 5.1 |
| 6 | 3,000.01-6,000K | 10 | 6.1 |
| 7 | 6,000.01-15,000K | 6 | 7.1 |
| 8 | 15,000.01-30,000K | 5 | 8.1 |
| 9 | 30,000.01-60,000K | 4 | 9.1 |
| 10 | 60,000.01-90,000K | 3 | 10.1 |
| 11 | 90,000.01-150,000K | 2 | 11.1 |
| 12 | 150,000.01-300,000K | 2 | 12.1 |
| Free | 0 | 0 | 13.1 |

### 4.5 Digital Archiving (DPDA) -- TE/DP

EUR per GB/year. UDM: GB, Cost: C-DAGB. Ratio: ~40 GB per 1M pages.

<!-- SENSITIVE: Commercial list prices -->

| Tier | GB Range | Equiv Pages | EUR/GB | Suffix |
|------|----------|-------------|--------|--------|
| 1 | 0-40 | 1M | 2,000 | 1.1 |
| 2 | 40.01-80 | 2M | 1,750 | 2.1 |
| 3 | 80.01-200 | 5M | 1,100 | 3.1 |
| 4 | 200.01-400 | 10M | 750 | 4.1 |
| 5 | 400.01-600 | 15M | 600 | 5.1 |
| 6 | 600.01-800 | 20M | 550 | 6.1 |
| 7 | 800.01-1,200 | 30M | 433 | 7.1 |
| 8 | 1,201.01-2,000 | 50M | 300 | 8.1 |
| 9 | 2,001.01-3,000 | 75M | 240 | 9.1 |
| 10 | 3,001.01-4,000 | 100M | 210 | 10.1 |
| 11 | 4,001.01-6,000 | 150M | 200 | 11.1 |
| 12 | 6,001.01-8,000 | 200M | 190 | 12.1 |
| 13 | 8,001.01-12,000 | 300M | 180 | 13.1 |
| 14 | 12,001.01-20,000 | 500M | 172 | 14.1 |
| Free | 0 | -- | 0 | 15.1 |

### 4.6 Other Solutions (DPOS) -- TE/DP (Italy-specific)

All EUR 0 (Free placeholder, priced separately).

| Solution | UDM | Cost Code | Suffix |
|----------|-----|-----------|--------|
| Legal Electronic Archive (Conservazione) | GB | C-DAGB | 1.1 |
| Electronic Invoicing (Fatturazione) | Document | C-PDOC | 30.1 |
| Electronic Ordering (Ordine) | Document | C-PDOC | 60.1 |

### 4.7 Distribution (TPDS) -- TE/3P

#### Email (EUR per M emails/year) -- UDM: Mail, Cost: C-MAIL

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/M | Suffix |
|------|--------|-------|--------|
| 1 | 0-1M | 4,500 | 1.1 |
| 2 | 1.01-2M | 2,500 | 2.1 |
| 3 | 2.01-5M | 1,400 | 3.1 |
| 4 | 5.01-10M | 1,100 | 4.1 |
| 5 | 10.01-15M | 1,000 | 5.1 |
| 6 | 15.01-20M | 910 | 6.1 |
| 7 | 20.01-30M | 830 | 7.1 |
| 8 | 30.01-50M | 758 | 8.1 |
| 9 | 50.01-75M | 693 | 9.1 |
| 10 | 75.01-100M | 645 | 10.1 |
| 11 | 100.01-150M | 600 | 11.1 |
| 12 | 150.01-200M | 575 | 12.1 |
| 13 | 200.01-300M | 550 | 13.1 |
| 14 | 300.01-500M | 540 | 14.1 |
| Free | 0 | 0 | 15.1 |

#### SMS (EUR per K SMS/year) -- UDM: SMS, Cost: C-SMS

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/K | Suffix |
|------|--------|-------|--------|
| 1 | 0-100K | 80.00 | 30.1 |
| 2 | 100.01-200K | 62.50 | 31.1 |
| 3 | 200.01-500K | 55.00 | 32.1 |
| 4 | 500.01-1,000K | 52.00 | 33.1 |
| 5 | 1,000.01-2,000K | 50.00 | 34.1 |
| 6 | 2,000.01-5,000K | 47.00 | 35.1 |
| 7 | 5,000.01-10,000K | 45.00 | 36.1 |
| 8 | 10,000.01-15,000K | 43.33 | 37.1 |
| 9 | 15,000.01-20,000K | 42.50 | 38.1 |
| 10 | 20,000.01-30,000K | 41.67 | 39.1 |
| 11 | 30,000.01-50,000K | 41.00 | 40.1 |
| 12 | 50,000.01-75,000K | 40.67 | 41.1 |
| 13 | 75,000.01-100,000K | 40.00 | 42.1 |
| Free | 0 | 0 | 43.1 |

#### Electronic Signatures -- Scrive (EUR per K signatures/year) -- UDM: Signature, Cost: C-MAIL

<!-- SENSITIVE: Commercial list prices -->

| Tier | Volume | EUR/K | Suffix |
|------|--------|-------|--------|
| 1 | 0-1K | 1.33 | 60.1 |
| 2 | 1.01-3K | 1.21 | 61.1 |
| 3 | 3.01-6K | 1.10 | 62.1 |
| 4 | 6.01-15K | 0.81 | 63.1 |
| 5 | 15.01-30K | 0.72 | 64.1 |
| 6 | 30.01-60K | 0.61 | 65.1 |
| 7 | 60.01-120K | 0.52 | 66.1 |
| 8 | 120.01-180K | 0.52 | 67.1 |
| Free | 1+ | 0 | 68.1 |

#### Certified Mail -- Pay Per Use, Cost: C-TNOTICE

| Type | Description | EUR/unit | UDM | Suffix |
|------|-------------|----------|-----|--------|
| SERC | Tnotice (standard) | 1.23 | Mail | 100.1 |
| SERCQ | TnoticeQ (qualified) | 1.94 | Mail | 101.1 |

#### Physical Delivery -- Pay Per Use, EUR 0 (Free), Cost: C-PORTO1AM, Suffix: 200.1

### 4.8 Printing (TPPR) -- TE/3P

EUR 0 placeholder (priced via separate arrangements). UDM: Pages, Pay Per Use, Cost: C-STCOL. Suffix: 1.1.

### 4.9 Embedded Services (ESES) -- ES/ES

<!-- SENSITIVE: Commercial list prices -->

| Service | Price | Method | Suffix |
|---------|-------|--------|--------|
| Premium Support | **10% of Net** | Percent Of Total | 1.1 |
| 24/7 Support (incl. Premium) | **20% of Net** | Percent Of Total | 10.1 |
| Managed Services | EUR 100,000/FTE/year | List | 20.1 |
| Premium Production KPI | **25% of Net** | Percent Of Total | 30.1 |
| Customer-Specific KPI | EUR 0 (Free) | List | 40.1 |
| Doxee University (e-Learning) | EUR 3,000/year | List | 50.1 |

Record Type: Support Service. Cost: C-PS (except University: C-LIC).

### 4.10 Professional Services (PSPS) -- PS/PS

One-shot, per day. UDM: Days. Cost: C-PS.

<!-- SENSITIVE: Commercial list prices -->

| Level | EUR/day | Suffix |
|-------|---------|--------|
| Free (placeholder) | 0 | 40.1 |
| L1 Junior | 350 | 50.1 |
| L2 Mid | 400 | 51.1 |
| L3 Senior | 500 | 52.1 |
| L4 Expert | 650 | 53.1 |

### 4.11 Intercompany (GEIC) -- GEN/GEN

**All entities**: Royalties for EU -- EUR 0 (Free). Suffix: 1.1.

**AT/DE only** (Parent: `EN-{CC}-PS-PSIC`): Intercompany PS -- Free placeholder (1.1), EUR 340/day for Italy resources (2.1).

---

## 5. Pricing Mechanics

### Tiered Volume (Block Pricing)

Cumulative tiered: each tier = separate SF line item. Customer volume fills tiers bottom-up.

**Example** (8M pages): T1(1M)=EUR14,000 + T2(1M)=EUR9,500 + T3(3M)=EUR19,200 + T4(3M)=EUR12,600 = **EUR 55,300**.

### Percent-of-Total

`Service Price = Net Subscription Total x Percentage`

| Service | % | SF Fields |
|---------|---|-----------|
| Sandbox | 10% | PricingMethod=PercentOfTotal, Base=Net, %=0.10 |
| Premium Support | 10% | PricingMethod=PercentOfTotal, Base=Net, %=0.10 |
| 24/7 Support | 20% | PricingMethod=PercentOfTotal, Base=Net, %=0.20 |
| Premium KPI | 25% | PricingMethod=PercentOfTotal, Base=Net, %=0.25 |

### Billing Types

| Type | Pattern | Examples |
|------|---------|----------|
| Subscription | Recurring annual | Base-system, licenses, production tiers, distribution |
| Pay Per Use | Per-transaction | SERC, SERCQ, physical delivery, printing |
| One Shot | One-time | Professional services |

---

## 6. Salesforce CPQ Integration

### Product Hierarchy

- **Parent Products** (RecordType=Parent Product): grouping containers, EUR 0 price
- **Child Products** (Component=TRUE, Type=Accessory): actual sellable items

### Key CPQ Fields

| Field | Purpose |
|-------|---------|
| SBQQ__Component__c | Bundle component flag |
| SBQQ__PriceEditable__c | Sales can modify price |
| SBQQ__QuantityEditable__c | Sales can modify quantity |
| SBQQ__ExcludeFromMaintenance__c | Exclude from % of total |
| SBQQ__BlockPricingField__c | Block pricing config |
| SBQQ__ConfigurationType__c | Bundle configuration |
| SBQQ__Hidden__c | Hide from quote output |

### Spreadsheet Import Structure

- Rows 1-4: SF field mappings (API names, labels, object types)
- Row 5: Italian labels; Row 6: role hints (`(feature)` / `(option)`)
- Rows 7+: product data in parent/child groups
- 52 columns (A-AZ)

**Key column formulas**: Parent K=F (contract code); Child K=CONCATENATE(F,G,".",H); Children inherit F/L/M/N/O from parent row.

### Record Types

| Record Type | Used For |
|-------------|----------|
| Parent Product | Bundle containers |
| License (On-Premise) | On-prem licenses |
| Managed Services (Cloud) | Cloud/SaaS subscriptions |
| Support Service | Embedded services |
| Professional Services | One-time delivery |

### Price Books

Each entity (IT/AT/DE) has its own SF Price Book. Fields: Pricebook2Id (Real/Standard), UseStandardPrice.

### Cost Article Codes (ERP)

| Code | Category |
|------|----------|
| C-LIC | Licenses & base-system |
| C-PPAG | Page production |
| C-PURL | pURL production & community |
| C-DAGB | Digital archive storage |
| C-PDOC | Document processing (e-invoicing/ordering) |
| C-MAIL | Email distribution & signatures |
| C-SMS | SMS distribution |
| C-TNOTICE | Certified mail (SERC/SERCQ) |
| C-PORTO1AM | Physical delivery |
| C-STCOL | Physical printing |
| C-PS | Professional services & support |

---

## 7. KPI Definitions & SLA (Exhibit 4)

### Object Definitions & Capacity Constraints

| Object | Max Size / Limit |
|--------|-----------------|
| Standard Document | **75 KB** or **5 pages** max |
| Standard Page | **15 KB** max |
| Pvideo/Pweb concurrent views | **10 views/second** per template |
| Batch input files per day | **400 files/day** max |
| Batch input file size | **200 MB** max per file |
| On-Demand request payload | **1 MB** max |
| Batch distribution channels | Up to **4** (email, SMS, SFTP, print) |
| On-Demand distribution channels | Up to **2** (email, SMS) |
| On-Demand output types | Max **3 applications** |
| On-Demand concurrency (standard) | **3 concurrent requests**, response within **5 seconds** |
| Monthly production capacity | Annual volume / 12 months |
| Peak days per month | Max **2 days** |
| Peak day volume | Max **35%** of monthly volume |

### KPI Formulas

| Production Type | Formula |
|----------------|---------|
| Batch | `# Documents or pURLs produced / # hours` |
| On-Demand | `# concurrent requests / response in seconds` |
| Interactive | `# human workflow executions / # hours` |
| Print Service | Days from receipt to print completion |
| Postal Delivery | Days from receipt to physical delivery |

### Production KPIs (Table 1)

| Type | Standard | Premium |
|------|----------|---------|
| Batch | Produced in **24 hours** during peak days | Produced in **12 hours** during peak days |
| On-Demand | **3 concurrent** / **5 sec** response | **6 concurrent** / **5 sec** response |
| Interactive | **200 executions/hour** (max 15 steps/process) | **1,000 executions/hour** (max 15 steps/process) |

Premium KPI is a paid add-on at **25% of Net subscription** (see Embedded Services ESES 30.1).

### Print Service KPI (Table 2)

| Receipt Time | KPI | Excluded |
|-------------|-----|----------|
| By 14:00 | **4 working days** | Sat, Sun, holidays |
| After 14:00 | **5 working days** | Sat, Sun, holidays |

### Delivery Service KPI (Table 3)

| Envelope Mode | Days |
|--------------|------|
| AM Type | **5** |
| CP Type | **7** |
| EU Type | **10** |

### KPI Limitations

KPIs do NOT apply when customer:
1. Does not comply with input file submission specs (size/format/timing)
2. Requests content changes to stored documents (evaluated case-by-case)
3. Requests production exceeding defined limits/definitions

Requests outside standard definitions: provider will attempt but is not obligated to meet goals and not required to deploy additional resources.

Customer-specific KPI levels available as paid option (extends capacity, reduces production time), documented in Order Form (Exhibit 1a).
