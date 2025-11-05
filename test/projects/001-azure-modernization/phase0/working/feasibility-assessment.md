# Feasibility Assessment - Azure Modernization Initiative

**Last Updated**: 2025-11-05 (After Interview 9)  
**Assessment Based On**: 9 stakeholder interviews (82% complete)  
**Overall Feasibility Score**: 36/100 (High Risk, Conditional)

---

## Executive Summary

**Current Assessment**: **CONDITIONAL GO** with **10 critical conditions** that must ALL be met

**Probability of Success**:
- **IF all 10 conditions met**: 70% (High confidence with proper execution)
- **IF conditions NOT met**: 10% (SAP 2.0 - virtually certain failure)

**Key Finding**: Project is feasible BUT requires fundamental reset of timeline (36-60 months vs. 18 months), budget ($18.5-26.5M vs. $3M), and approach (partnership vs. top-down).

---

## Overall Feasibility Score: 36/100

### Score Breakdown by Dimension

| Dimension | Score | Change | Status | Weight |
|-----------|-------|--------|--------|--------|
| **Timeline Feasibility** | 25/100 | - | 🔴 CRITICAL RISK | 25% |
| **Financial Feasibility** | 37/100 | ⬇️ -3 | 🔴 HIGH RISK | 25% |
| **Technical Feasibility** | 45/100 | - | 🟠 MODERATE-HIGH RISK | 20% |
| **Operational Feasibility** | 45/100 | ⬇️ -5 | 🟠 MODERATE-HIGH RISK | 20% |
| **Organizational Feasibility** | 35/100 | - | 🔴 HIGH RISK | 10% |
| **OVERALL** | **36/100** | ⬇️ -2 | 🔴 **HIGH RISK** | 100% |

**Trend**: ⬇️ Declining (38 → 36 after Interview 9)

---

## DIMENSION 1: Timeline Feasibility (25/100) - CRITICAL RISK

**Score**: 25/100 (CRITICAL)  
**Change**: No change (already at critical level)  
**Status**: 🔴 CRITICAL RISK

### Score Breakdown
- Timeline Realism: 15/100 (18 months vs. 36-60 months reality)
- Phase Gate Planning: 40/100 (can do phased approach)
- Dependency Management: 30/100 (sequential dependencies understood)
- Schedule Buffer: 20/100 (no buffer in Michael's plan)
- Stakeholder Alignment on Timeline: 25/100 (Michael vs. everyone else)
- **Overall**: 25/100

### Reality Check

**Michael's Timeline**: 18 months total transformation

**Mathematical Reality**: 36-60 months (3-5 years) minimum

**Proof of Timeline Impossibility**:

1. **Sunday Window Constraint** (Physical Limit):
   - Only 12 Sunday maintenance windows per year
   - 4 hours each = 48 hours/year total for ALL IT changes
   - Shared with mechanical and electrical maintenance
   - Sequential dependencies: ERP → warehouse → MES (cannot parallelize)
   - Even with perfect execution, cutover windows alone prove multi-year timeline
   - **This single constraint makes 18 months impossible**

2. **Validation Timeline** (Regulatory Requirement):
   - 8 systems require GMP validation
   - 3-6 months per system minimum
   - Total: 24-48 months if sequential
   - Even with risk-based approach: 18-24 months minimum
   - Cannot be compressed without regulatory violations
   - **Not in Michael's timeline at all**

3. **Training Timeline** (Adoption Requirement):
   - Four-phase training for MES alone: 12-18 months
     - Phase 1: 2 weeks classroom
     - Phase 2: 1-2 weeks hands-on
     - Phase 3: 3-6 months pilot program
     - Phase 4: 3-4 months gradual rollout + 6 months stabilization
   - Across all systems: Training must happen sequentially
   - **Not adequately accounted for in timeline**

4. **Support Preparation** (Capacity Requirement):
   - 12-18 months just to prepare support:
     - Hire 4-6 new staff (3-6 months)
     - Train entire team on Azure/cloud (3-6 months)
     - Build documentation and procedures (6-12 months)
   - Cannot be compressed without sacrificing quality
   - **Not in Michael's timeline**

5. **Infrastructure Stabilization** (Technical Prerequisite):
   - 6-8 months network remediation
   - Must be complete before migration starts
   - Not parallel work - it's prerequisite
   - **Not accounted for as prerequisite**

6. **MES Migration Alone** (Highest Risk System):
   - Must be migrated LAST (after proving approach)
   - 18-24 months for MES alone:
     - 3-6 months pilot (one line)
     - 3-4 months gradual rollout (line by line)
     - 6-12 months parallel running
     - 6 months stabilization
   - **Could add 18-24 months to overall timeline**

**Cumulative Timeline Reality**:
- Infrastructure stabilization: 6-8 months
- Network resolution: 6-8 months (if not prioritized immediately)
- Discovery and planning: 6 months (already started)
- Validation per system: 3-6 months each × 8 systems (sequential)
- Training development and delivery: 12-18 months
- Sequential migrations: Limited by 48 hours/year cutover windows
- Training execution: 12-18 months across all systems
- Parallel running: 3-6 months per critical system
- Union notice: 120 days before floor systems
- **Total: 36-60 months (3-5 years) MINIMUM**

**Gap**: 200-300% timeline underestimate

### Impact on Feasibility

**Why This Kills Feasibility**:
- Board expects 18-month results
- PE firm wants ROI within 3-5 years
- When reality becomes clear (6-12 months in), board may:
  - Force premature go-live (SAP 2.0)
  - Cancel project (waste of investment)
  - Replace leadership (loss of continuity)

**Critical Quote** (Maria):
> "If you're migrating multiple systems, you're talking hundreds of hours of cutover work. That's years of Sunday mornings."

### Mitigation Approach

**What Must Happen**:
1. **Immediate timeline reset** (within 7 days)
   - Michael + Jennifer present to board
   - Show mathematical proof (Sunday windows)
   - Reset to 36-60 month realistic timeline

2. **Phase gate approach** (6-12 month gates)
   - Value delivered at each gate
   - Go/no-go decision at each gate
   - Board sees progress, maintains confidence

3. **Prioritize systems strategically**
   - Highest value first (early ROI)
   - Highest risk last (MES)
   - Build confidence incrementally

4. **Parallel work maximization**
   - Most work during week (prep, testing, documentation)
   - Sunday windows only for final cutover
   - Reduces cutover time, maximizes window usage

5. **Use Christmas shutdown**
   - Additional maintenance windows beyond 12 Sundays
   - Longer windows possible (not constrained to 4 hours)
   - Coordinate with mechanical/electrical

**If Timeline NOT Reset**:
- 100% probability of missing commitments
- Board will lose confidence
- Likely force premature go-live or cancel
- SAP 2.0 scenario (chaos, rollback, trust destroyed)

**Current Score Justification**: 25/100
- Only 15 points for timeline realism (impossible as stated)
- 40 points for phase gate capability (can be done)
- Low scores for dependency management, buffer, stakeholder alignment
- Critical risk - must be addressed for any chance of success

---

## DIMENSION 2: Financial Feasibility (37/100) - HIGH RISK

**Score**: 37/100 (HIGH RISK)  
**Change**: ⬇️ -3 points (down from 40/100)  
**Reason**: Interview 9 revealed support contractor costs of $2-3M not in budget

### Score Breakdown
- Budget Adequacy: 25/100 (massive gap discovered)
- ROI Clarity: 60/100 (Jennifer has model showing 3X return over 5 years)
- Cost Control: 35/100 (50/50 chance of zero savings per Kevin)
- Funding Availability: 40/100 (Jennifer supportive IF honest, but PE firm unknown)
- Contingency Planning: 35/100 (need 30% contingency on $18.5-26.5M base)
- **Overall**: 37/100

### Budget Reality Evolution

**Timeline of Budget Discovery**:
| Interview | Estimate | Key Addition |
|-----------|----------|--------------|
| Interview 1 (Michael) | $3-5M implied | "Jennifer has allocated budget" |
| Interview 2 (Sarah) | $5-8M | Infrastructure, contractors, training |
| Interview 3 (Jennifer) | $3M allocated | Board approved capital budget |
| Interview 7 (Patricia) | Add $1.5-2.5M | Validation costs |
| Interview 8 (Maria) | Add $12-15M | Training costs (largest single item!) |
| Interview 9 (Tom) | Add $2-3M | Support contractors |
| **Current Reality** | **$18.5-26.5M** | **520-780% of original $3M** |

### Detailed Cost Breakdown

**Infrastructure and Migration**:
- Base Azure infrastructure: $3-5M
- Network remediation: Included
- Application migration: Included
- Data migration: Included
- **Subtotal**: $3-5M

**Validation and Compliance**:
- GMP validation (8 systems): $1.5-2.5M
- Security audits and certifications: Included
- External validators: Included
- **Subtotal**: $1.5-2.5M

**Parallel Running**:
- On-prem + Azure simultaneously (12-36 months): $1-2M
- Dual infrastructure costs during transition
- **Subtotal**: $1-2M

**Retention and Staffing**:
- Retention bonuses (key people): $500K
- IT contractors (10-15 people, 3 years): $4-6M
- Support contractors (6-9 people, 18-36 months): $2-3M
- **Subtotal**: $6.5-9.5M

**Training** (Largest Single Cost):
- MES operators: 180 × $50K = $9M
- IT team: 45 × $11K = $500K
- Supervisors: 15 × $20K = $300K
- Support staff: 20 × $15K = $300K
- Quality team: 10 × $20K = $200K
- Contingency: $1.7M
- **Subtotal**: $12-15M

**Hidden Costs**:
- Year 1-2 parallel running overhead: $1-2M/year
- Lost productivity during learning curves: $500K
- Knowledge base and documentation: $100-200K
- Vendor support contracts: Included in Azure costs
- **Subtotal**: $1.5-2.5M

**Contingency**:
- 30% on base costs: $1.5-3M
- Always need contingency in complex projects
- **Subtotal**: $1.5-3M

**TOTAL REALISTIC COST**: $18.5-26.5M

### Year-by-Year Cash Flow

| Year | On-Prem | Azure | Migration/Training | Total Annual | Cumulative |
|------|---------|-------|-------------------|--------------|------------|
| **Year 1** | $4.5M | $3M | $2-3M | **$9.5-10.5M** | $9.5-10.5M |
| **Year 2** | $4.5M | $3.5M | $2-3M | **$10-11M** | $19.5-21.5M |
| **Year 3** | - | $4M | $500K | **$4.5M** | $24-26M |
| **Year 4** | - | $3.5M | - | **$3.5M** | $27.5-29.5M |
| **Year 5** | - | $3.5M | - | **$3.5M** | $31-33M |

**5-Year Total**: $31-33M  
**Avoided on-prem costs**: $9M (2 years)  
**Net Investment**: $22-24M  
**Projected savings Years 4-10**: $15M  
**Net ROI over 10 years**: 3X return (IF assumptions hold)

### Budget Gap Analysis

**Current Allocation**: $3M (Jennifer, Interview 3)

**Realistic Need**: $18.5-26.5M

**Gap**: $15.5-23.5M (520-780% increase)

**Breakdown of Gap**:
- Training: $12-15M (NOT in current budget)
- Support contractors: $2-3M (NOT in current budget)
- Validation: $1.5-2.5M (likely NOT in current budget)
- IT contractors: $4-6M (partially budgeted?)
- Infrastructure: $2.5M Year 1 (partially budgeted?)
- Contingency: $1.5-3M (likely NOT in current budget)

### ROI Sensitivity Analysis

**Jennifer's Base Case** (Interview 3):
- 3X return over 5 years
- Assumes cost savings materialize as projected
- Assumes timeline doesn't slip significantly
- Assumes successful adoption

**Downside Scenarios**:

1. **Timeline Slips to 5 Years** (likely):
   - Delayed ROI realization
   - Higher parallel running costs
   - 3X return becomes 2X over 8-10 years

2. **Cost Savings Don't Materialize** (Kevin's 50/50):
   - Hidden cloud costs eat savings
   - Oracle licensing higher than expected
   - Ongoing support costs higher
   - ROI becomes negative or break-even

3. **Partial Implementation Only**:
   - Budget runs out mid-stream
   - Only migrate low-risk systems
   - MES stays on-premise (highest cost system)
   - ROI case collapses (most savings from MES)

4. **Adoption Failure** (without proper training):
   - Technical migration succeeds
   - Operational adoption fails
   - Productivity loss offsets savings
   - ROI negative (spent $20M, lost productivity)

### Funding Strategy Questions

**Critical Unknown**: PE firm position

- Will PE firm approve $18.5-26.5M investment?
- Does this align with PE timeline (typically 3-5 year hold)?
- Will PE accept 3-5 year timeline with ROI in years 4-10?
- What if PE wants to sell company in Year 3?

**Funding Options**:
1. **Full upfront approval**: Get board + PE approval for $18.5-26.5M
2. **Phased funding**: Approve by phase, each 6-12 months
3. **Hybrid**: Approve $10M upfront, rest phased based on progress
4. **Cancel/defer**: If PE unwilling to fund, cancel or defer project

### Impact on Feasibility

**Why 3-Point Decrease**:
- Interview 9 revealed $2-3M additional cost (support contractors)
- Total budget gap now $15.5-23.5M (was $13.5-20.5M)
- Gap percentage now 520-780% (was 450-650%)
- Support contractors are non-optional (capacity crisis without them)

**Critical Quote** (Tom):
> "We're talking $1.5-2.5M just for support contractors over the migration period. And that's probably conservative."

### Mitigation Approach

**What Must Happen**:
1. **Jennifer update budget model** (within 7 days)
   - Incorporate all discovered costs
   - $18.5-26.5M realistic total
   - Show year-by-year cash flow
   - Demonstrate 3X ROI over 10 years (not 5)

2. **Board presentation** (within 30 days)
   - Honest assessment of costs
   - Show what happens if underfunded (partial implementation worse than none)
   - Request $18.5-26.5M approval
   - Phased funding if board prefers

3. **PE firm engagement** (within 30 days)
   - Jennifer + Michael present to PE firm
   - Understand PE timeline and constraints
   - Get PE buy-in or understand if project should be deferred

4. **External validation** (within 60 days)
   - Independent cost estimator
   - Validate $18.5-26.5M is realistic
   - Jennifer requires this (good practice)

5. **Funding source identification**
   - Capital budget vs. operational budget
   - Multi-year allocation strategy
   - Board approval process and timeline

**If Budget NOT Approved**:
- Cannot proceed with project
- Partial implementation worse than no implementation
- Should defer until funding available
- Alternative: Smaller scope (defer MES, focus on office systems only)

**Current Score Justification**: 37/100
- Only 25 points for budget adequacy (massive gap)
- 60 points for ROI clarity (Jennifer's model is solid IF assumptions hold)
- Low scores for cost control, funding availability, contingency
- High risk - must secure adequate funding or cancel

---

## DIMENSION 3: Technical Feasibility (45/100) - MODERATE-HIGH RISK

**Score**: 45/100 (MODERATE-HIGH RISK)  
**Change**: No change (Interview 9 focused on operational/support, not technical)  
**Status**: 🟠 MODERATE-HIGH RISK

### Score Breakdown
- Infrastructure Readiness: 40/100 (network needs 6-8 months remediation)
- Application Compatibility: 45/100 (8 custom apps, some need rework)
- Data Migration Complexity: 40/100 (15+ years data, quality issues)
- Integration Challenges: 50/100 (many integrations, some will break)
- Technical Skills Available: 35/100 (zero cloud experience, 3-6 months training needed)
- Disaster Recovery Design: 55/100 (can design, needs testing)
- **Overall**: 45/100

### Technical Challenges

**Infrastructure Prerequisites** (6-8 months):
- Network segments still 100Mb (inadequate)
- Other segments maxed during shift changes
- MES requires <50ms latency, cloud adds 20-30ms
- Cannot migrate until network ready
- $2.5M Year 1 investment needed

**Application Landscape**:
- 8 custom applications with undocumented dependencies
- Original developers mostly gone
- "Applications running that nobody knows how they work"
- May need re-architecture or rewrites ($500K-1M each)
- Commercial off-the-shelf (COTS) replacements considered

**Data Migration**:
- 15+ years production data across multiple systems
- Data quality issues (garbage in, garbage out)
- Legacy formats and complex transformations
- GMP systems require validated data migration (3-6 months per system)
- 50-70% of migration effort typically

**Integration Complexity**:
- Customer portals, vendor systems, shipping, banking integrations
- Third parties may not support cloud integration
- 70% probability at least some integrations break
- Extensive testing and fallback plans needed

**Skills Gap**:
- IT team (45 people) has zero Azure/cloud experience
- Support team (10 people) has zero cloud troubleshooting skills
- Need 3-6 months training for entire team
- Training while maintaining BAU is challenging
- Over-reliance on contractors if team not trained

**MES-Specific Technical Risks**:
- Currently 30-35% of all support tickets
- System freezes, slow performance (10-15 seconds/screen)
- Barcode scanner issues, data sync problems
- Cloud may introduce latency issues
- Most problematic system to support currently

### Technical Strengths

**What Works in Our Favor**:
- Sarah (IT Director) deeply knowledgeable
- Team knows current systems well (can document before migration)
- Kevin (Infrastructure Lead) capable despite being overwhelmed
- Steve (Level 2 support) has manufacturing background (invaluable for MES)
- Existing infrastructure works (just old and needs upgrade)

### Mitigation Approach

**What Must Happen**:
1. **6-month discovery and documentation phase**
   - Document all custom applications
   - Map dependencies and integrations
   - Data quality assessment
   - Application assessment (migrate, rewrite, or COTS replace)

2. **Infrastructure stabilization first** ($2.5M Year 1)
   - Network remediation (6-8 months)
   - Treat as prerequisite, not parallel
   - Cannot start migration until complete

3. **Comprehensive training program** (3-6 months)
   - Azure fundamentals for entire IT team
   - Hands-on labs and sandbox environment
   - Certifications for key people
   - Contractors work alongside team (knowledge transfer)

4. **Pilot approach for high-risk systems**
   - MES pilot (one line, 3-6 months)
   - Email/collaboration pilot (IT team first)
   - Learn lessons before full rollout

5. **Extensive testing at each step**
   - Integration testing before cutover
   - Data validation during parallel running
   - Performance testing (especially MES latency)
   - Disaster recovery testing (quarterly)

**Current Score Justification**: 45/100
- Moderate technical challenges (not insurmountable but significant)
- Infrastructure prerequisite adds 6-8 months
- Skills gap requires training investment
- Custom apps and integrations add complexity
- MES is technically challenging (latency, performance, reliability)
- But team is capable, just needs preparation time and training

---

## DIMENSION 4: Operational Feasibility (45/100) - MODERATE-HIGH RISK

**Score**: 45/100 (MODERATE-HIGH RISK)  
**Change**: ⬇️ -5 points (down from 50/100)  
**Reason**: Interview 9 revealed operational constraints worse than understood

### Score Breakdown
- Operational Benefits Clarity: 70/100 (Robert provided framework)
- Production Impact Mitigation: 45/100 (parallel running understood but complex)
- Union Engagement: 40/100 (not yet started, 120-day notice required)
- Floor Worker Partnership: 30/100 (Michael hasn't done floor shift yet)
- Training Capacity: 35/100 (now understand $12-15M magnitude and 12-18 months duration)
- SAP Trauma Management: 30/100 (must acknowledge and differentiate)
- **Support Capacity and Model**: 25/100 (NEW - critical constraint discovered)
- **Overall**: 45/100

### Why 5-Point Decrease

**Support Team Reality** (Interview 9):
1. **Team Already at Breaking Point**:
   - 30% attrition in 18 months (3 of 10 people left)
   - 3-4 pages per night, every night
   - "Running on fumes"
   - One person had breakdown during SAP (called in sick for week)
   - Morale low, burnout pervasive

2. **Ticket Volume Will Double**:
   - Current: 80-100 tickets/day
   - During migration: 150-200 tickets/day
   - Supporting BOTH old and new systems for 12-36 months
   - Same 10 people cannot handle this load
   - No contractors budgeted for support

3. **Help Desk Model Breaks for Floor Systems**:
   - Remote support insufficient for MES transition
   - Operators at 2 AM can't wait 30-60 minutes when production down
   - Floor workers need immediate help on floor, not tickets
   - Current model: VPN in, troubleshoot remotely, drive in if needed (30-45 min)
   - **Need floor-level support model** (not yet designed)

4. **Only 1 Person with Manufacturing Background**:
   - Steve (Level 2 tech) is invaluable for MES
   - Rest of team from traditional IT backgrounds
   - Don't understand floor workflows or operator pressures
   - "Gap" between support and operators acknowledged
   - Need more people like Steve (how to find them?)

5. **Support Contractor Costs** ($2-3M):
   - Backfill contractors: $300-450K/year (2-3 people)
   - Migration support: $1.2-1.8M (4-6 people, 18 months)
   - Total: $2-3M NOT IN BUDGET
   - Non-optional (support capacity crisis without them)

6. **MES Already Most Problematic System**:
   - 30-35% of current tickets are MES-related
   - Resolution times: 15 minutes to 6 hours
   - Common issues: freezes, slow performance, login failures, scanner issues
   - Cloud migration adds latency/connectivity/compatibility risks
   - Support team "terrified" of MES cloud migration

### Operational Constraints Summary

**SAP Trauma Organizational Impact** (Worse Than Understood):
- Not just failed project, organizational PTSD
- 3 employees lost (2 quit, 1 transferred)
- 7 years later still shapes response to change
- "When corporate says 'new system,' people update resumes"
- Support perspective: 200-300 tickets/day, 10-15 pages/night, one person breakdown
- Must be explicitly acknowledged in all communications

**Training Investment Magnitude** ($12-15M, 12-18 months):
- MES operators alone: $9M for 180 people × $50K
- Four-phase approach: classroom → hands-on → pilot → gradual rollout + support
- Differentiated for operator capability range (1/3 comfortable, 1/3 okay, 1/3 struggle)
- Manufacturing-experienced trainers required (not IT people reading scripts)
- Inadequate training = adoption failure = project failure

**MES Transition Risk Quantified**:
- 20-30% productivity drop for 2-3 months (optimistic baseline)
- Potentially 40-50% for 4-6 months if rushed
- 180 operators with 10-15 years muscle memory
- MUST be migrated LAST (after proving approach on other systems)
- 18-24 months for MES alone (pilot through stabilization)

**Sunday Window Mathematical Constraint**:
- Only 48 hours/year for ALL IT changes
- Shared with mechanical/electrical maintenance
- Sequential dependencies prove multi-year timeline
- Physical constraint that cannot be overcome

**Safety Incidents Risk**:
- During SAP: wrong job setups (worker safety), missed quality checks (customer safety)
- Operator confusion with new interfaces can cause safety incidents
- Parts for aerospace and medical devices (downstream customer safety if quality missed)
- Patricia needs explicit veto power on safety/quality systems
- Cannot rush systems that affect safety or quality

**Floor-Level Partnership Requirements**:
- "Partner with us, don't treat us like widgets to manage"
- Operators must be involved in UAT (usability under pressure at 3 AM)
- "Treat this like technical project instead of people project, it will fail"
- Michael floor shift is THE trust-building catalyst
- Floor workers are capable if given real training, support, respect

### Support Model Gap

**Current Support Model** (Works for BAU, Breaks for Migration):
- **Business Hours** (7 AM - 6 PM):
  - Full 10-person team available
  - Can send Level 2 tech to floor if needed
  - Most tickets handled within target times
  
- **After Hours** (6 PM - 7 AM) + Weekends:
  - Single person on call (5-person rotation)
  - Remote only (VPN from home)
  - Must call operator to understand issue
  - Troubleshoot remotely or drive in (30-45 min travel)
  - Average 3-4 pages per night
  - 1-2 drive-ins per week

**Why This Breaks for MES Migration**:
- Operators need immediate help during transition (not 30-60 minute wait)
- Floor-level issues require floor presence (not remote)
- System confusion at 2 AM needs human on floor to show/guide
- Production can't wait while on-call person drives in
- Help desk queue doesn't work for urgent floor issues

**Floor-Level Support Model Required** (Not Yet Designed):
- People ON THE FLOOR, all three shifts
- Not sitting at desk waiting for tickets
- Walking floor, seeing issues in real-time, helping immediately
- Manufacturing background (understand workflows, speak operator language)
- Duration: 6-12 months during and after MES transition
- Cost: $260K-520K (2 people × $120-130K + overtime, 6-12 months)
- **Currently not designed, not budgeted, not staffed**

### Mitigation Approach

**What Must Happen**:
1. **Address Support Burnout BEFORE Migration** (immediate):
   - Reduce on-call burden (hire contractors to expand rotation)
   - Retention bonuses for critical people
   - Career development opportunities
   - Realistic timeline allows capacity to scale

2. **Hire Support Contractors** ($2-3M):
   - 2-3 backfill contractors for BAU work
   - 4-6 migration support contractors for cloud expertise
   - Spread across three shifts during critical periods
   - Budget approval within 30 days

3. **Design Floor-Level Support Model** (within 60 days):
   - Define staffing (how many people, which shifts)
   - Manufacturing background requirement (how to recruit)
   - Duration (6-12 months)
   - Integration with help desk (escalation paths)
   - Budget and approval

4. **Michael Floor Shift** (within 30 days):
   - 8-hour actual shift on Maria's 2nd shift
   - Experience support challenges firsthand
   - Build credibility with 180+ operators
   - Understand why support is critical
   - Required by Robert, Maria, and Tom

5. **Four-Phase Training Program** ($12-15M, 12-18 months):
   - Classroom + hands-on + pilot + gradual rollout + support
   - Differentiated for operator capability range
   - Manufacturing-experienced trainers
   - Budget approval and HR design

6. **MES Pilot Program** (3-6 months):
   - One line (Line 2 recommended)
   - Volunteers (10-12 per shift)
   - Floor-level support embedded
   - Parallel running (old system available)
   - Success criteria defined upfront
   - Learn lessons before expanding

7. **SAP Acknowledgment** (immediate):
   - Explicit in all communications
   - Document what went wrong (2 hour training, big bang, no support)
   - Show what's different (pilot, real training, parallel, support, rollback)
   - Build trust through actions not just promises

**Current Score Justification**: 45/100
- Support capacity crisis worse than understood (-5 points)
- Help desk model inadequate for floor systems (-5 points)
- But floor partnership approach is understood (+5 points)
- Training investment magnitude understood (+5 points)
- Moderate-high risk - operational constraints are significant

---

## DIMENSION 5: Organizational Feasibility (35/100) - HIGH RISK

**Score**: 35/100 (HIGH RISK)  
**Change**: No change (Interview 9 reinforced existing concerns)  
**Status**: 🔴 HIGH RISK

### Score Breakdown
- Executive Alignment: 30/100 (Michael vs. everyone on timeline/budget)
- Change Readiness: 35/100 (SAP trauma affects willingness to try)
- Communication Effectiveness: 40/100 (can improve with right approach)
- Trust Level: 25/100 (IT-floor trust is low after SAP)
- Leadership Commitment: 45/100 (Michael committed but approach problematic)
- **Overall**: 35/100

### Organizational Challenges

**Executive Misalignment**:
- Michael: 18 months, $3-5M implied, technical focus
- Everyone else: 36-60 months, $18.5-26.5M, people focus
- Michael has zero floor credibility ("just another corporate guy with PowerPoint")
- Michael hasn't done floor shift yet (required by Robert, Maria, Tom)
- Michael hasn't engaged union yet (120-day notice required)

**SAP Organizational PTSD**:
- 7 years later still affects trust and willingness to try
- Support team: One person had breakdown during SAP
- Floor workers: "People update resumes when corporate says 'new system'"
- IT team: "That's why everyone's cautious now"
- Union: "People remember broken promises"
- Not just failed project - organizational trauma

**Trust Deficit**:
- IT-floor relationship: "complicated" (Tom)
- Operators see support as "IT people who don't understand"
- Floor doesn't trust management after SAP
- Michael has zero floor credibility (hasn't done the work)
- Actions required, not just words

**Union Defensive Posture**:
- Jimmy (union rep) already defensive about being left out
- 120-day notice not in timeline
- Early involvement = partnership, late = adversarial fight
- 180+ union members can passively resist
- "Partner with us from day one" or it becomes fight

**People Not Heard**:
- Tom (Support Lead): "I don't feel heard"
- Tom: "My team doesn't feel heard"
- Tom: "Floor workers don't feel heard"
- Tom: "We're all just... bracing for impact"
- No consultation with support on migration plans
- Floor workers excluded from planning
- Top-down approach breeds resistance

### Organizational Strengths

**What Works in Our Favor**:
- Maria (MES Supervisor) is potential champion if partnered with
- Jimmy (Union Rep) wants partnership, not opposition
- Floor workers are "smart, capable, adaptable people" if respected
- Support team committed despite burnout
- Robert (COO) understands floor perspective and requirements
- Patricia (Quality) ensures safety and quality are protected

### Mitigation Approach

**What Must Happen**:
1. **Michael Floor Shift** (within 7 days):
   - 8-hour actual shift on Maria's 2nd shift
   - Experience what operators experience
   - Build credibility with 180+ operators
   - Understand support challenges
   - Required by Robert, Maria, Tom

2. **Michael-Jimmy Union Meeting** (within 7 days):
   - Present partnership approach
   - Discuss training, no layoffs, real support
   - Get union involved early (partnership not adversarial)
   - Bargaining committee session to follow

3. **Four-Way Leadership Alignment** (within 30 days):
   - Michael + Jennifer + Sarah + Robert
   - Agree on realistic timeline (36-60 months)
   - Agree on adequate budget ($18.5-26.5M)
   - Agree on partnership approach (not top-down)
   - Unified message to organization

4. **Floor Communication** (within 7 days):
   - Address rumors about "new system"
   - Acknowledge SAP explicitly
   - Show what's different this time
   - Involve operators in design/UAT

5. **SAP Retrospective** (within 30 days):
   - Document what went wrong
   - Share with organization
   - Show learning and changes
   - Build trust through transparency

6. **Stakeholder Alignment Workshop** (within 60 days):
   - All 11 interviewees + Michael
   - Align on approach, timeline, budget
   - Surface any remaining concerns
   - Get collective buy-in before Phase 1

**Current Score Justification**: 35/100
- Executive misalignment is severe (Michael vs. everyone)
- SAP trauma is deep and pervasive
- Trust deficit between IT and floor
- Union not engaged yet (120-day notice needed)
- But willing partners exist if approached correctly
- High risk - organizational resistance can kill project

---

## OVERALL ASSESSMENT: CONDITIONAL GO

**Overall Feasibility Score**: 36/100 (HIGH RISK)

**Assessment**: Project is feasible IF and ONLY IF all 10 critical conditions are met

### The 10 Critical Conditions (ALL Must Be Met)

| # | Condition | Owner | Status | Deadline | Impact if Not Met |
|---|-----------|-------|--------|----------|-------------------|
| 1 | **Timeline Reset to 36-60 Months** | Michael + Board | ❌ NOT MET | 7 days | Project failure (forced premature go-live or cancellation) |
| 2 | **Budget Approved at $18.5-26.5M** | Jennifer + Board + PE | ❌ NOT MET | 30 days | Project runs out of money mid-stream |
| 3 | **Michael Floor Shift Completed** | Michael | ❌ NOT MET | 30 days | Zero floor credibility, adoption failure |
| 4 | **Four-Way Leadership Alignment** | Michael + Jennifer + Sarah + Robert | ❌ NOT MET | 30 days | Executive dysfunction, mixed messages |
| 5 | **Union Engagement Initiated** | Michael + Jimmy | ❌ NOT MET | 7 days | Adversarial fight, passive resistance |
| 6 | **Training Investment Approved ($12-15M)** | Jennifer + Board | ❌ NOT MET | 30 days | Token training = adoption failure |
| 7 | **Infrastructure Stabilization Funded ($2.5M Year 1)** | Jennifer | ❌ NOT MET | 30 days | Cannot migrate on inadequate infrastructure |
| 8 | **Support Capacity Plan ($2-3M Contractors)** | Sarah + Jennifer | ❌ NOT MET | 30 days | Support collapses, team quits |
| 9 | **Floor-Level Support Model Designed** | Tom + Sarah + Maria | ❌ NOT MET | 60 days | Help desk model fails, operators unsupported |
| 10 | **SAP Acknowledgment in Communications** | Michael | ❌ NOT MET | 7 days | Trust deficit continues, preemptive resistance |

**Current Status**: 0 of 10 conditions met (🔴 RED)

### Success Probability

**IF All 10 Conditions Met**: 70% probability of success
- Timeline realistic (3-5 years)
- Budget adequate ($18.5-26.5M)
- Partnership approach (floor involvement)
- Training investment ($12-15M)
- Support capacity ($2-3M contractors)
- Floor-level support model (embedded)
- SAP acknowledged and differentiated
- Michael has floor credibility (floor shift)
- Union engaged early (partnership)
- Infrastructure stabilized first

**IF Conditions NOT Met**: 10% probability of success (SAP 2.0)
- Timeline impossible (18 months)
- Budget inadequate ($3M vs. $18.5-26.5M)
- Top-down imposition (not partnership)
- Token training (hours not months)
- Support overwhelmed (no contractors)
- Help desk model (not floor-level)
- SAP ignored (trauma continues)
- Michael has zero credibility (no floor shift)
- Union adversarial (late engagement)
- Infrastructure not ready

**Key Difference**: Partnership, realistic expectations, adequate investment, proper timeline

### Recommendation

**Proceed to Phase 1 (Specification & Design) IF:**
1. Board and PE firm approve reset expectations (timeline + budget)
2. Michael completes floor shift within 30 days
3. Union engagement initiated within 7 days
4. Four-way leadership alignment achieved within 30 days
5. Adequate funding secured ($18.5-26.5M over 3-5 years)

**Otherwise:**
- **Pause** project until conditions can be met
- **Cancel** if PE firm unwilling to fund adequately
- **Defer** to later year when funding and commitment available

**Do NOT Proceed If**:
- Board unwilling to reset timeline expectations
- PE firm unwilling to fund $18.5-26.5M investment
- Michael unwilling to do floor shift
- Union not engaged (adversarial relationship guaranteed)
- Adequate support capacity not planned

**Proceeding without meeting conditions = SAP 2.0 = 90% chance of catastrophic failure**

---

## Feasibility Trend Analysis

### Score Evolution Through Interviews

| Interview | Overall Score | Change | Key Discovery |
|-----------|---------------|--------|---------------|
| Interview 1 | N/A | - | Initial optimism (18 months, manageable) |
| Interview 2 | 55/100 | - | Reality check (36-48 months, capacity crisis) |
| Interview 3 | 50/100 | ⬇️ -5 | Budget inadequate, PE firm unknown |
| Interview 4 | 48/100 | ⬇️ -2 | SAP trauma, floor requirements |
| Interview 5 | 46/100 | ⬇️ -2 | Compliance complexity |
| Interview 6 | 45/100 | ⬇️ -1 | Union requirements, 120-day notice |
| Interview 7 | 43/100 | ⬇️ -2 | Validation 24-48 months |
| Interview 8 | 38/100 | ⬇️ -5 | Training $12-15M, Sunday windows math |
| Interview 9 | 36/100 | ⬇️ -2 | Support crisis, $2-3M contractors |

**Trend**: ⬇️ Steadily declining as reality understood

**Why Declining?**:
- Each interview reveals constraints not previously understood
- Timeline impossibility proven mathematically
- Budget gap grows ($3M → $18.5-26.5M)
- Organizational challenges deepen
- Support capacity crisis discovered

**Will Trend Reverse?**:
- Only if conditions are met (timeline reset, budget approved, partnership approach)
- Interviews 10-11 may reveal more challenges (IT morale, HR capacity)
- Feasibility may drop further before stabilizing

---

## Risk Assessment Integration

### Critical Risks (Score 20-25)

**Total Critical Risks**: 10 (out of 44 total risks)

1. RISK-001: Timeline Compression Impossibility (25/25)
2. RISK-002: Team Capacity Collapse (24/25)
3. RISK-008: MES Production Disruption (22/25)
4. RISK-012: Validation Timeline Inadequacy (22/25)
5. RISK-020: Union Relationship Breakdown (20/25)
6. RISK-028: Budget Inadequacy (20/25)
7. RISK-033: MES Floor Adoption Resistance (20/25)
8. RISK-034: SAP Trauma Organizational PTSD (20/25)
9. RISK-038: Support Team Attrition During Migration (20/25)
10. RISK-039: Support Capacity Inadequacy (22/25)

**All 10 critical risks are directly related to feasibility gaps**

### Contradiction Assessment Integration

**Total Contradictions**: 18 (8 critical, 6 high, 4 moderate)

**Critical Contradictions Affecting Feasibility**:
1. Timeline (18 months vs. 36-60 months)
2. Training budget ($300-500K vs. $12-15M)
3. Total cost ($3M vs. $18.5-26.5M)
4. Approach (top-down vs. partnership)
5. MES risk assessment (manageable vs. critical)
6. SAP trauma relevance (past issue vs. ongoing PTSD)
7. Support model (help desk vs. floor-level)
8. Support contractor costs (none vs. $2-3M)

**Contradictions must be resolved for feasibility to improve**

---

## Comparison to Similar Projects

### Industry Benchmarks

**Typical Cloud Migration Timelines**:
- Small organization (<100 users): 12-18 months
- Medium organization (100-500 users): 24-36 months
- Large organization (500+ users): 36-60 months
- **Manufacturing with GMP systems**: Add 12-24 months

**Our Reality**:
- 300+ users (medium-large)
- 8+ critical systems including MES (24/7 manufacturing)
- GMP validated systems (add 18-24 months)
- SAP trauma (organizational resistance)
- **Expected Timeline**: 36-60 months (matches benchmark)

**Typical Migration Costs**:
- $50-100K per user (all-in over project life)
- Manufacturing premium: 1.5-2X (complexity + validation)
- Our estimate: $18.5-26.5M ÷ 300 users = $62-88K per user
- **Within industry norms for manufacturing with GMP**

**Typical Success Rates**:
- Cloud migrations generally: 60-70% success
- Manufacturing cloud migrations: 50-60% success
- With major organizational change (like SAP trauma): 40-50% success
- **Our estimate if conditions met: 70%** (above average due to proper planning)
- **Our estimate if conditions not met: 10%** (SAP 2.0)

---

## Recommendations

### Immediate Actions (Within 7 Days)

1. **Michael Floor Shift**:
   - Schedule 8-hour shift on Maria's 2nd shift
   - Actually work, not observe
   - Experience operator and support challenges
   - Build credibility with 180+ operators

2. **Michael-Jimmy Union Meeting**:
   - Present partnership approach
   - Discuss real training, no layoffs, early involvement
   - Get union engaged (partnership not adversarial)

3. **Board Timeline Presentation**:
   - Show mathematical proof (Sunday windows)
   - Present realistic 36-60 month timeline
   - Explain consequences of compression (SAP 2.0)

4. **Floor Communication**:
   - Address rumors about "new system"
   - Acknowledge SAP explicitly
   - Show what's different this time

### Short-Term Actions (Within 30 Days)

5. **Budget Reality Update**:
   - Jennifer update financial model to $18.5-26.5M
   - Show year-by-year cash flow
   - Demonstrate 3X ROI over 10 years (not 5)
   - Board approval request

6. **PE Firm Engagement**:
   - Michael + Jennifer present to PE firm
   - Understand PE timeline and constraints
   - Get buy-in or defer project

7. **Four-Way Leadership Alignment**:
   - Michael + Jennifer + Sarah + Robert
   - Agree on timeline (36-60 months)
   - Agree on budget ($18.5-26.5M)
   - Agree on approach (partnership)

8. **Support Capacity Plan**:
   - Design support contractor strategy
   - Budget approval ($2-3M)
   - Begin recruiting support contractors

9. **Bargaining Committee Session**:
   - Michael + Jimmy + bargaining committee
   - Present detailed partnership approach
   - Get union buy-in before proceeding

### Medium-Term Actions (Within 60 Days)

10. **External Validation**:
    - Hire independent cost/timeline estimator
    - Validate $18.5-26.5M is realistic
    - Validate 36-60 months is realistic

11. **Floor-Level Support Model Design**:
    - Define staffing, shifts, duration
    - Manufacturing background requirement
    - Integration with help desk
    - Budget and approval

12. **Training Program Design**:
    - HR Director + Maria + Jimmy
    - Four-phase approach detailed
    - Manufacturing-experienced trainer sourcing
    - Budget allocation ($12-15M)

13. **Complete Remaining Interviews**:
    - Interview 10: IT Manager
    - Interview 11: HR Director
    - Finalize Phase 0 discovery

14. **Stakeholder Alignment Workshop**:
    - All 11 interviewees + Michael
    - Align on approach, timeline, budget
    - Surface remaining concerns
    - Collective buy-in

15. **Go/No-Go Decision**:
    - After all conditions assessed
    - Board + PE firm approval
    - Proceed to Phase 1 or pause/cancel

---

## Document Control

**Version**: 2.0  
**Last Updated**: 2025-11-05 (After Interview 9)  
**Updated By**: Discovery Team  
**Next Review**: After Interview 10 (IT Manager)  
**Owner**: Project Manager (TBD)

**Change Log**:
- v1.0 (2025-10-28): Initial feasibility assessment (55/100)
- v1.1 (2025-10-30): Updated after Jennifer interview (50/100)
- v1.2 (2025-10-31): Updated after Robert interview (48/100)
- v1.3 (2025-11-01): Updated after David interview (46/100)
- v1.4 (2025-11-02): Updated after Jimmy interview (45/100)
- v1.5 (2025-11-04): Updated after Patricia interview (43/100)
- v1.6 (2025-11-05): Major update after Maria interview (38/100)
- v2.0 (2025-11-05): Updated after Tom interview (36/100) - added support dimension

---

**STATUS**: Conditional GO - project feasible IF all 10 conditions met, 70% success probability with conditions, 10% without conditions (SAP 2.0 scenario). Currently 0 of 10 conditions met. Immediate action required on timeline reset, budget approval, floor shift, union engagement, support capacity.
