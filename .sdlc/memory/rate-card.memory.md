# Rate Card Context

**Purpose**: Defines standard billing rates, cost structures, and pricing models used by Cost Estimator and Resource Planner agents.

**Last Updated**: 2025-11-07  
**Owner**: Finance/Delivery Leadership  
**Review Cycle**: Quarterly

---

## 🔧 CONFIGURATION GUIDE

This file is **your primary cost configuration point**. To customize:

1. **Update Geography Rates** - Adjust the rate tables for your market
2. **Modify Level Definitions** - Change titles or add/remove levels
3. **Set Specialty Premiums** - Define markups for specialized skills
4. **Configure Blended Rates** - Set standard pod blending formulas
5. **Add Custom Rate Types** - Include fixed-price, value-based, or other models

**All agents reference this file** - changes here cascade throughout the system.

---

## Rate Structure Overview

### Rate Types

**Hourly Rates** - Standard billing model
- Used for time-and-materials contracts
- Applied to pod-based estimates
- Includes direct labor + overhead + margin

**Blended Rates** - Averaged across pod levels
- Simplifies client billing
- Used for budget-level estimates
- Calculated from pod mix

**Fixed Price** - Project-level pricing
- Derived from estimated hours × rates
- Includes risk contingency
- Used for firm commitments

---

## 🔧 PRIMARY CONFIGURATION: Standard Hourly Rates

### United States - Major Metro Markets

**Default Geography**: Used when location not specified

| Level | Title | Hourly Rate | Annual Capacity | Notes |
|-------|-------|-------------|-----------------|-------|
| **L1** | Staff Consultant | $150 | 1,800 hrs | Entry-level, mentored |
| **L2** | Consultant | $175 | 1,850 hrs | Autonomous on tasks |
| **L3** | Senior Consultant | $225 | 1,900 hrs | Leads work streams |
| **L4** | Manager | $275 | 1,600 hrs | Client-facing, 20% admin |
| **L5** | Senior Manager | $325 | 1,400 hrs | Manages workstreams, 30% admin |
| **L6** | Director | $400 | 1,200 hrs | Program oversight, 40% admin |
| **L7** | Senior Director | $475 | 1,000 hrs | Portfolio management, 50% admin |
| **L8** | Managing Director | $600 | 800 hrs | Strategic oversight, 60% admin |

**Billable Hour Assumptions:**
- 2,080 hours/year total (40 hrs/week × 52 weeks)
- Reduced capacity at higher levels accounts for:
  - Business development
  - People management
  - Internal initiatives
  - Client relationship management

**Rate Components** (Example: L3 Senior Consultant @ $225/hr):
- Direct Labor: $90/hr (40%)
- Overhead (Benefits, Facilities, Tools): $70/hr (31%)
- Margin: $65/hr (29%)

---

### 🔧 Geographic Rate Adjustments

Apply these multipliers to base rates for different markets:

| Geography | Multiplier | Example: L3 Rate | Notes |
|-----------|------------|------------------|-------|
| **US - Tier 1 Metro** | 1.00× | $225 | SF, NYC, Seattle, Boston |
| **US - Tier 2 Metro** | 0.85× | $191 | Austin, Denver, Chicago |
| **US - Tier 3 Metro** | 0.75× | $169 | Regional markets |
| **US - Remote** | 0.80× | $180 | Location-independent |
| **Canada - Major Metro** | 0.90× | $203 | Toronto, Vancouver |
| **UK - London** | 1.05× | $236 | Pound sterling conversion |
| **Western Europe** | 0.95× | $214 | Germany, France, Netherlands |
| **Eastern Europe** | 0.55× | $124 | Poland, Czech Republic |
| **India - Metro** | 0.35× | $79 | Bangalore, Pune, Hyderabad |
| **Latin America** | 0.45× | $101 | Mexico, Brazil, Argentina |

**How to Use**:
1. Choose base rate from US Major Metro table
2. Apply geography multiplier
3. Round to nearest $5

**Example**: L4 Manager in Austin
- Base rate: $275/hr
- Tier 2 multiplier: 0.85×
- Adjusted rate: $275 × 0.85 = $234/hr → **$235/hr**

---

### 🔧 Specialty Skill Premiums

Add these premiums for specialized expertise:

| Specialty | Premium | Applied To | Example: L3 Base $225 |
|-----------|---------|------------|----------------------|
| **Cloud Architecture** | +15% | L3-L6 | $259/hr |
| **Security/Compliance** | +20% | All levels | $270/hr |
| **AI/ML/Data Science** | +25% | L2-L6 | $281/hr |
| **SAP/Oracle** | +15% | L2-L5 | $259/hr |
| **Legacy Modernization** | +10% | L3-L6 | $248/hr |
| **DevOps/SRE** | +12% | L2-L5 | $252/hr |
| **Executive Advisory** | +30% | L6-L8 | $293/hr |

**Stacking Rules**:
- **Single specialty**: Apply full premium
- **Two specialties**: Apply highest + 50% of second
- **Three+ specialties**: Cap at +35% total premium

**Example**: L4 Manager with Cloud Architecture + Security
- Base: $275/hr
- Cloud (15%): +$41 = $316
- Security (20% × 50%): +$28 = $344/hr
- **Final Rate: $345/hr**

---

### 🔧 Pod Blended Rate Calculation

Standard formula for pod-level blended rates:
Blended Rate = (Σ (Level Hours × Level Rate)) / Total Hours

**Example: Standard Delivery Pod (10-person)**

| Level | Count | Hrs/Week | Total Hrs | Rate | Extended Cost |
|-------|-------|----------|-----------|------|---------------|
| L8 (MD) | 0.25 | 10 | 120 | $600 | $72,000 |
| L6 (Director) | 0.5 | 20 | 240 | $400 | $96,000 |
| L5 (Sr Mgr) | 1 | 40 | 480 | $325 | $156,000 |
| L4 (Manager) | 1 | 40 | 480 | $275 | $132,000 |
| L3 (Sr Cons) | 2 | 80 | 960 | $225 | $216,000 |
| L2 (Consultant) | 3 | 120 | 1,440 | $175 | $252,000 |
| L1 (Staff) | 2 | 80 | 960 | $150 | $144,000 |
| **Total** | **9.75** | **390** | **4,680** | — | **$1,068,000** |

**Blended Rate**: $1,068,000 / 4,680 hrs = **$228/hr**

**Typical Blended Ranges by Pod Type**:
- Delivery Pod (mixed levels): $210-$240/hr
- Architecture Pod (senior-heavy): $280-$320/hr
- Support Pod (junior-heavy): $160-$190/hr
- Leadership Pod (executives): $400-$500/hr

---

### 🔧 Role-Based Rate Ranges

When specific level isn't known, use these ranges:

| Role Category | Typical Levels | Rate Range | Median |
|---------------|----------------|------------|--------|
| **Delivery Team Member** | L1-L3 | $150-$225 | $188 |
| **Workstream Lead** | L3-L4 | $225-$275 | $250 |
| **Practice Lead** | L4-L5 | $275-$325 | $300 |
| **Technical Architect** | L3-L5 | $225-$325 | $275 |
| **Program Manager** | L5-L6 | $325-$400 | $363 |
| **Executive Sponsor** | L7-L8 | $475-$600 | $538 |

**Usage Guidelines**:
- **ROM Estimates**: Use median rate for role
- **Detailed Estimates**: Specify actual level
- **Ranges**: Use for sensitivity analysis (low/high scenarios)

---

## Fixed-Price Conversion Models

### Time-and-Materials to Fixed-Price

**Standard Conversion Formula**:

Fixed Price = (Estimated Hours × Blended Rate) × (1 + Risk Contingency)

**Risk Contingency by Confidence Level**:
- High Confidence (>80%): +10-15% contingency
- Medium Confidence (60-80%): +20-30% contingency
- Low Confidence (<60%): +35-50% contingency

**Example**: 10,000-hour project at $228/hr blended, 70% confidence
- Base: 10,000 × $228 = $2,280,000
- Contingency (25%): +$570,000
- **Fixed Price: $2,850,000**

---

### Value-Based Pricing Anchor Points

When cost-plus pricing isn't appropriate, use value-based models:

**Transformation Projects**:
- **Business Value Target**: 3-5× project investment over 3 years
- **Pricing Model**: 20-30% of anticipated value capture
- **Example**: $10M in cost savings → $2-3M project fee

**Strategic Initiatives**:
- **Market Entry**: 5-10% of revenue upside
- **Digital Platform**: 15-25% of cost avoidance
- **Risk Mitigation**: 25-40% of risk exposure reduction

**How to Calculate**:
1. Quantify business value with client (savings, revenue, risk)
2. Determine fair value share (typically 20-35%)
3. Compare to cost-based estimate
4. Use higher of: (value-based price) or (cost-based + 15%)

---

## 🔧 Non-Billable Cost Factors

Include these in total project cost (not billed to client):

### Internal Overhead (Not in Hourly Rates)

| Cost Category | % of Billable | Applied To | Notes |
|---------------|---------------|------------|-------|
| **Sales/BD** | 8-12% | All projects | Pursuit costs, proposal development |
| **Delivery Management** | 5-8% | Projects >$1M | PMO, governance, QA |
| **Risk Reserve** | 3-5% | All projects | Unanticipated scope growth |
| **Tools/Licenses** | 2-4% | All projects | Software, platforms, environments |
| **Travel** | Variable | Client sites | Actual costs, typically 5-10% |

**Example Calculation** (Client sees $2.28M billable):
- Billable Revenue: $2,280,000 (client pays)
- Sales/BD (10%): $228,000 (internal)
- Delivery Mgmt (7%): $159,600 (internal)
- Risk Reserve (4%): $91,200 (internal)
- Tools (3%): $68,400 (internal)
- Travel (estimate): $100,000 (pass-through)
- **Total Project Cost**: $2,927,200
- **Net Margin**: $2,280,000 - $2,927,200 + margin in rates = varies by deal

---

## Rate Card Maintenance

### Update Triggers

**Quarterly Review**:
- Market rate benchmarking
- Geographic adjustment validation
- Specialty premium assessment

**Annual Refresh**:
- Full rate card revision
- Level definition updates
- Capacity planning adjustments

**Ad-Hoc Updates**:
- New specialty capabilities added
- Major market shifts
- Competitive pressures

### Version Control

**Current Version**: 2025-Q4 (v4.2)  
**Previous Version**: 2025-Q3 (v4.1)  
**Next Review**: 2026-02-01

**Change Log**:
- 2025-Q4: Added AI/ML premium (+25%), increased L6-L8 rates by 8%
- 2025-Q3: New geography (Latin America), adjusted India rates
- 2025-Q2: Revised pod blended rate methodology

---

## Usage by Agents

### Cost Estimator Agent

**Uses**:
- Hourly rates by level for detailed estimates
- Blended rates for ROM estimates
- Specialty premiums for skill-based pricing
- Fixed-price conversion models

**Configuration Points**:
1. Load this context file at start of estimation session
2. Apply geography adjustments based on project location
3. Calculate blended rates from pod composition
4. Add specialty premiums as identified in requirements

### Resource Planner Agent

**Uses**:
- Rate ranges for budget constraint validation
- Blended rates for pod design options
- Level capacity hours for staffing calculations

**Configuration Points**:
1. Reference when validating "budget-first" constraints
2. Use to compare pod structure options
3. Inform skill premium decisions

---

## 🎯 Customization Quick Start

**To Adapt This Rate Card to Your Organization**:

1. **Replace Rate Tables** (30 minutes):
   - Update "Standard Hourly Rates" table with your levels/rates
   - Adjust geographic multipliers for your markets
   - Modify specialty premiums based on your capabilities

2. **Update Blended Rate Examples** (15 minutes):
   - Recalculate pod examples using your rates
   - Adjust pod composition if your structure differs

3. **Configure Capacity Assumptions** (10 minutes):
   - Update annual billable hours by level
   - Adjust for your organization's admin overhead

4. **Review Contingency Models** (10 minutes):
   - Align fixed-price conversion with your risk tolerance
   - Update value-based pricing if applicable

**Test Your Configuration**:
- Run a sample estimate using cost-estimator agent
- Verify all rate lookups work correctly
- Check blended rate calculations
- Validate fixed-price conversions

**Total Customization Time**: ~65 minutes for complete adaptation

---

**End of rate-card.context.md**