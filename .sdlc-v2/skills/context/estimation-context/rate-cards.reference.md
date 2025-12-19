# Rate Cards Reference

## Overview

Rate cards define standard billing rates for cost estimation and resource
planning. All rates are placeholder examples - customize for your organization.

---

## Standard Hourly Rates

### United States - Tier 1 Metro (Default)

Base rates for major markets (SF, NYC, Seattle, Boston).

| Level | Title | Hourly Rate | Annual Capacity | Loaded Cost |
|-------|-------|-------------|-----------------|-------------|
| **L1** | Staff Consultant | $150 | 1,800 hrs | $270,000 |
| **L2** | Consultant | $175 | 1,850 hrs | $323,750 |
| **L3** | Senior Consultant | $225 | 1,900 hrs | $427,500 |
| **L4** | Manager | $275 | 1,600 hrs | $440,000 |
| **L5** | Senior Manager | $325 | 1,400 hrs | $455,000 |
| **L6** | Director | $400 | 1,200 hrs | $480,000 |
| **L7** | Senior Director | $475 | 1,000 hrs | $475,000 |
| **L8** | Managing Director | $600 | 800 hrs | $480,000 |

**Rate Components** (Example L3 @ $225/hr):
- Direct Labor: ~40% ($90)
- Benefits & Overhead: ~31% ($70)
- Margin: ~29% ($65)

---

## Geographic Adjustments

Apply multipliers to base rates for different markets.

| Geography | Multiplier | L3 Example | Notes |
|-----------|------------|------------|-------|
| **US - Tier 1 Metro** | 1.00× | $225 | SF, NYC, Seattle, Boston |
| **US - Tier 2 Metro** | 0.85× | $191 | Austin, Denver, Chicago |
| **US - Tier 3/Regional** | 0.75× | $169 | Smaller markets |
| **US - Remote** | 0.80× | $180 | Location-independent |
| **Canada - Major** | 0.90× | $203 | Toronto, Vancouver |
| **UK - London** | 1.05× | $236 | Premium market |
| **Western Europe** | 0.95× | $214 | Germany, France, NL |
| **Eastern Europe** | 0.55× | $124 | Poland, Czech, Romania |
| **India - Metro** | 0.35× | $79 | Bangalore, Pune, Hyderabad |
| **Latin America** | 0.45× | $101 | Mexico, Brazil, Argentina |

### Blended Team Example

US Lead + India Team:
```
1 L4 Manager (US): $275/hr
2 L3 Senior (India): $79/hr × 2 = $158/hr
3 L2 Staff (India): $61/hr × 3 = $183/hr

Total: $616/hr for 6 people
Blended Rate: $103/hr per person
```

---

## Specialty Premiums

Add to base rate for specialized skills.

| Specialty | Premium | L3 w/Premium | Justification |
|-----------|---------|--------------|---------------|
| **AI/ML Engineering** | +25% | $281 | Scarce talent, high demand |
| **Cloud Architecture** | +15% | $259 | Platform expertise |
| **Security/AppSec** | +20% | $270 | Compliance, risk |
| **Data Engineering** | +15% | $259 | Pipeline expertise |
| **Legacy Systems** | +10% | $248 | Mainframe, COBOL |
| **Performance Engineering** | +15% | $259 | Optimization skills |
| **Mobile (iOS/Android)** | +10% | $248 | Platform-specific |

**Stacking Rule**: Maximum one specialty premium per resource.

---

## Blended Pod Rates

Pre-calculated rates for standard pod compositions.

### Core Delivery Pod (6 people)

| Role | Level | Rate | FTE | Extended |
|------|-------|------|-----|----------|
| Tech Lead | L4 | $275 | 1.0 | $275 |
| Senior Dev | L3 | $225 | 2.0 | $450 |
| Developer | L2 | $175 | 2.0 | $350 |
| QA Engineer | L3 | $225 | 1.0 | $225 |
| **Total** | | | **6.0** | **$1,300/hr** |
| **Blended** | | | | **$217/hr** |

Monthly Cost (700 hrs): **$151,900**

### Architecture Pod (3 people)

| Role | Level | Rate | FTE | Extended |
|------|-------|------|-----|----------|
| Lead Architect | L5 | $325 | 0.75 | $244 |
| Solution Architect | L4 | $275 | 1.0 | $275 |
| Senior Dev | L3 | $225 | 1.0 | $225 |
| **Total** | | | **2.75** | **$744/hr** |
| **Blended** | | | | **$271/hr** |

Monthly Cost (400 hrs): **$108,400**

### Platform/DevOps Pod (4 people)

| Role | Level | Rate | FTE | Extended |
|------|-------|------|-----|----------|
| Platform Lead | L4 | $275 | 1.0 | $275 |
| DevOps Engineer | L3 | $225 | 1.5 | $338 |
| Cloud Engineer | L3 | $259* | 1.0 | $259 |
| SRE | L2 | $175 | 0.5 | $88 |
| **Total** | | | **4.0** | **$960/hr** |
| **Blended** | | | | **$240/hr** |

*Includes cloud specialty premium

Monthly Cost (500 hrs): **$120,000**

### Leadership Pod (3 people)

| Role | Level | Rate | FTE | Extended |
|------|-------|------|-----|----------|
| Engagement Lead | L7 | $475 | 0.25 | $119 |
| Program Manager | L5 | $325 | 0.75 | $244 |
| Delivery Manager | L4 | $275 | 1.0 | $275 |
| **Total** | | | **2.0** | **$638/hr** |
| **Blended** | | | | **$319/hr** |

Monthly Cost (300 hrs): **$95,700**

---

## Project Cost Models

### Time & Materials (T&M)

Standard billing model - bill actual hours at agreed rates.

```
Monthly Cost = Σ (Actual Hours × Hourly Rate)
```

**Advantages**: Flexibility, scope changes easy
**Disadvantages**: Client budget uncertainty

### Fixed Price

Project-level price based on estimated effort + risk contingency.

```
Fixed Price = (Estimated Hours × Blended Rate) × (1 + Risk Factor)

Risk Factors:
- Low risk: 1.10 (10% contingency)
- Medium risk: 1.20 (20% contingency)
- High risk: 1.35 (35% contingency)
```

**Example**:
```
Estimated: 10,000 hours
Blended Rate: $220/hr
Base Cost: $2,200,000
Risk Factor: 1.20 (medium)
Fixed Price: $2,640,000
```

### Capped T&M

T&M with a not-to-exceed ceiling.

```
Cap = Estimated Cost × 1.15
Bill at T&M rates up to cap
```

---

## ROM Cost Estimation

### Quick Estimate Formula

For Phase 0 rough order of magnitude:

```
ROM Cost = Hours × Blended Rate × Uncertainty Factor

Uncertainty Factors:
- High confidence: 1.0 - 1.25
- Medium confidence: 1.25 - 1.50
- Low confidence: 1.50 - 2.00
```

### ROM by Project Size

| Size | Hours Range | Blended Rate | Cost Range |
|------|-------------|--------------|------------|
| Small | 2,000-4,000 | $200-220 | $400K-$880K |
| Medium | 5,000-10,000 | $210-230 | $1.05M-$2.3M |
| Large | 15,000-30,000 | $220-240 | $3.3M-$7.2M |
| Enterprise | 40,000+ | $230-250 | $9.2M+ |

---

## Cost Breakdown Structure

### Standard Cost Categories

| Category | % of Total | Description |
|----------|------------|-------------|
| **Development** | 45-55% | Core feature build |
| **Architecture/Design** | 10-15% | Technical design, ADRs |
| **Testing/QA** | 15-20% | Test development, execution |
| **DevOps/Platform** | 8-12% | CI/CD, infrastructure |
| **Project Management** | 8-12% | Coordination, governance |
| **Contingency** | 10-20% | Risk buffer |

### Phase Distribution

| Phase | % of Total | Typical Duration |
|-------|------------|------------------|
| Phase 0 (Discovery) | 3-5% | 2-4 weeks |
| Phase 1 (Design) | 10-15% | 4-8 weeks |
| Phase 2 (Planning) | 5-8% | 2-4 weeks |
| Phase 3 (Build) | 55-65% | Varies |
| Phase 4+ (Stabilize) | 15-20% | 4-8 weeks |

---

## Non-Billable Factors

Include in internal cost calculations (not billed to client):

| Factor | % of Billable | Notes |
|--------|---------------|-------|
| Sales/BD | 8-12% | Pursuit, proposals |
| Delivery Management | 5-8% | PMO, QA (projects >$1M) |
| Risk Reserve | 3-5% | Scope growth buffer |
| Tools/Licenses | 2-4% | Software, platforms |
| Travel | Variable | Usually 5-10% if onsite |

---

## Rate Card Customization

### To Adapt for Your Organization

1. **Update Base Rates** (Section 1)
   - Replace L1-L8 rates with your actuals
   - Adjust titles to match your levels

2. **Modify Geography Multipliers** (Section 2)
   - Add/remove geographies
   - Update multipliers for your markets

3. **Set Specialty Premiums** (Section 3)
   - Define which specialties warrant premiums
   - Set premium percentages

4. **Recalculate Pod Rates** (Section 4)
   - Update pod compositions
   - Recalculate blended rates

5. **Adjust Cost Models** (Section 5)
   - Set risk factors for your risk tolerance
   - Define contingency policies

---

## Quick Reference

### Rate Lookup

| Level | US Tier 1 | US Tier 2 | India |
|-------|-----------|-----------|-------|
| L1 Staff | $150 | $128 | $53 |
| L2 Consultant | $175 | $149 | $61 |
| L3 Senior | $225 | $191 | $79 |
| L4 Manager | $275 | $234 | $96 |
| L5 Sr Manager | $325 | $276 | $114 |
| L6 Director | $400 | $340 | $140 |

### Quick Cost Calc

```
Project Cost ≈ Team Size × $200/hr × Hours

Example: 8 people × 6 months × 160 hrs/month
= 8 × 200 × 960 = $1,536,000
```

### Pod Monthly Costs

| Pod Type | Monthly Cost |
|----------|--------------|
| Core Delivery (6) | $140K-160K |
| Architecture (3) | $100K-120K |
| Platform (4) | $110K-130K |
| Leadership (3) | $90K-110K |
