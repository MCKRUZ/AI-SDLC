# Risk Register - Contoso Manufacturing Azure Modernization

**Project**: Azure Modernization Initiative  
**Phase**: Phase 0 - Discovery & Ideation  
**Last Updated**: After Interview 5 (Kevin Martinez)  
**Total Risks**: 29  
**Risk Distribution**: 8 Critical, 14 High, 7 Medium

---

## Risk Summary Dashboard

### By Severity
- **Critical (Show-stopper)**: 8 risks
- **High (Major Impact)**: 14 risks  
- **Medium (Moderate Impact)**: 7 risks

### By Category
- **Financial**: 8 risks
- **Technical**: 7 risks
- **Organizational**: 9 risks
- **Operational**: 3 risks
- **Compliance/Legal**: 2 risks

### By Phase
- **Pre-Migration/Phase 0-1**: 12 risks
- **Phase 1 (Migration)**: 10 risks
- **Post-Migration (Year 2+)**: 5 risks
- **All Phases**: 2 risks

### Critical Path Risks (Must Resolve Before Proceeding)
1. R01 - Timeline Misalignment
2. R02 - Executive Alignment Gap
3. R07 - Budget Realism Gap
4. R21 - Hardware Failure Cascade
5. R22 - Network Capacity Bottleneck
6. R10 - Union Negotiation Failure
7. R14 - Three Veto Powers Uncoordinated
8. R23 - Cloud Cost Spiral (No ROI)

---

## CRITICAL RISKS (Show-stopper Impact)

## Risk 01: Timeline Misalignment

**Category**: Organizational  
**Probability**: Very High (95%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Fundamental disconnect between Michael's 18-month promise and reality understood by Sarah (years not quarters), Jennifer (3-5 years), Robert (2-3 years per system), and Kevin (3 years minimum). Michael promised board 50% cost reduction in 18 months. All four other stakeholders independently state this is impossible.

**Impact**:
- Board presentation in 30 days with unrealistic timeline
- Lost credibility when timeline slips (Q1-Q2 FY2025)
- Budget shortfall (18 months underfunds vs. 3-year need)
- Rushed decisions causing quality/safety issues
- Initiative cancellation when reality becomes apparent
- Michael's departure, repeat of 18-month-ago failed attempt

**Root Cause**: Michael hired to deliver fast results (board pressure), hasn't reconciled with operational reality yet.

**Mitigation Strategy**:
- Four-way alignment meeting (Michael + Jennifer + Robert + Sarah + Kevin) BEFORE board presentation
- Present realistic 3-year timeline with phase gates
- Year 1: Non-critical systems migration + infrastructure stabilization
- Year 2: Critical systems migration with parallel running
- Year 3: Optimization, decommissioning on-prem
- Build credibility through honesty, not optimism

**Owner**: Michael Chen  
**Status**: Open - URGENT (board presentation in ~15 days from Interview 3)

---

## Risk 02: Executive Alignment Gap

**Category**: Organizational  
**Probability**: Very High (90%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Michael, Jennifer, Robert, Sarah, and Kevin have not sat down TOGETHER to reconcile their different perspectives. Each stakeholder has been interviewed separately and has concerns/requirements, but no unified plan exists. Michael has vision, Jennifer has budget concerns, Robert has operational requirements, Sarah has technical reality, Kevin has infrastructure constraints. All five have mentioned lack of alignment.

**Impact**:
- Decisions made without full context
- Budget approved by Jennifer doesn't match operational needs
- Robert vetoes via CEO when operational constraints ignored
- Infrastructure collapse (Kevin's passive veto) if not addressed
- Contradictory messages to board
- Initiative stalls when forced to reconcile (same as 18 months ago)

**Root Cause**: Stakeholders interviewed separately, no facilitated session to build unified understanding.

**Mitigation Strategy**:
- **Four-way alignment session within 2 weeks**:
  - Attendees: Michael + Jennifer + Robert + Sarah + Kevin
  - Duration: Half-day workshop
  - Facilitator: External or trusted internal
  - Agenda: Put ALL constraints on table
    - Jennifer's budget reality ($3-5M over 3-5 years, Year 1 doubling)
    - Robert's operational requirements (parallel running, no layoffs, union engagement)
    - Sarah's technical debt (847 reports, black box code, team underwater)
    - Kevin's infrastructure ($ 2.5M minimum, network bottleneck, expertise gap)
  - Output: Unified plan all five can support publicly
  - Success criteria: All five say "yes, this can work"

**Owner**: Michael Chen (must convene and facilitate)  
**Status**: Open - URGENT (must happen before board presentation)

---

## Risk 07: Budget Realism Gap

**Category**: Financial  
**Probability**: High (80%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Major gap between Michael's expectations and financial reality:
- Michael's promise: 50% cost reduction ($2.25M/year savings) in 18 months
- Jennifer's analysis: Year 1 costs DOUBLE to $9-11M, savings Year 4+
- Kevin's analysis: Year 1-2 costs $8.75-9.75M/year, long-term maybe $1.5M/year savings IF disciplined (50/50 chance of zero savings)
- Michael appears unaware of: $2.5M infrastructure, $1.4-2M staffing, $800K-1.2M parallel running, $1-2M hidden costs

**Current State**: $4.5M annual IT run costs  
**Michael's Implied Budget**: Unknown, but promises 50% reduction to $2.25M  
**Jennifer's Realistic Budget**: $3-5M over 3-5 years, with Year 1 doubling  
**Kevin's Detailed Analysis**:
- Year 1-2: $17.5-19.5M total ($8.75-9.75M/year)
- Year 3+: $3.5M/year optimistic, $5M/year realistic

**Gap**: $5-7M Year 1, unclear if Michael understands this

**Impact**:
- Jennifer publicly challenges Michael at board presentation if not aligned
- Budget approval withheld or insufficient
- Triggers Jennifer's 20% variance kill criteria mid-project
- Initiative scaled back or cancelled when money runs out
- Damages Michael's credibility permanently

**Mitigation Strategy**:
- Kevin + Sarah + Jennifer build comprehensive 5-year cost model including ALL costs
- Present to Michael BEFORE board presentation
- Include: Infrastructure ($2.5M), staffing ($1.4-2M Year 1), parallel running ($800K-1.2M), hidden costs ($1-2M/year), licensing catch-up ($800K)
- Scenario planning: Optimistic ($3.5M/year long-term) vs. Realistic ($5M/year)
- Michael presents REALISTIC budget to board, not aspirational
- Build contingency (Jennifer's requirement)

**Owner**: Jennifer Walsh + Kevin Martinez + Sarah Mitchell  
**Status**: Open - URGENT (cost model needed within 15 days)

---

## Risk 10: Union Negotiation Failure

**Category**: Operational/Legal  
**Probability**: Medium-High (60%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: 180 UAW workers, union steward Jimmy Garcia has NOT been engaged yet. Robert explicitly requires early union engagement. If automation/efficiency gains threaten jobs, union can trigger work stoppage. Lost contract negotiation 2019 (wages/benefits) created tension. If union surprised by layoffs or job changes, guaranteed problems.

**Impact**:
- Work stoppage = $240K/day in lost production
- 1-week strike = $1.68M loss
- Contract grievances delay implementation
- Negative publicity, worker morale
- Robert vetoes initiative via CEO if union not on board
- Safety issues if workers resist new systems

**Root Cause**: Technology modernization often leads to efficiency (fewer people needed). Union contract protects against layoffs without negotiation.

**Mitigation Strategy**:
- Interview Jimmy Garcia NEXT (Robert's #1 priority)
- Engage union early (before finalizing plans)
- Frame as "enabling growth" not "reducing headcount"
- Commit to: No layoffs (attrition only), retraining programs, new roles (MES operators → data analysts)
- Involve union in system design (UAT, training development)
- Timeline: Union negotiation adds 3-6 months, plan accordingly
- Have Robert sponsor union engagement (his relationship, his requirement)

**Owner**: Robert Turner + Michael Chen  
**Status**: Open - Interview Jimmy Garcia as Interview 6 (URGENT per Robert)

---

## Risk 14: Three Veto Powers Uncoordinated

**Category**: Organizational/Political  
**Probability**: Very High (85%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Three independent veto powers identified, none coordinated:
1. **Jennifer (CFO)** - Controls budget, will publicly challenge if unrealistic
2. **Robert (VP Ops)** - CEO's best friend, can veto via CEO relationship
3. **Kevin (Infrastructure)** - Passive veto (infrastructure collapses if not addressed)

Each can independently kill the initiative, and they haven't aligned on requirements yet.

**Impact**:
- Michael gains Jennifer's budget approval, but Robert vetoes via CEO
- Or: Michael gains Robert's support, but Jennifer withholds budget
- Or: Both approve, but infrastructure fails (Kevin's passive veto)
- Initiative stalls, Michael loses credibility with all three
- Repeat of pattern from 18 months ago (and 3x prior per Kevin)

**Root Cause**: Power structure not mapped, stakeholders engaged separately, no coalition building.

**Mitigation Strategy**:
- Recognize all three must say "yes" for initiative to succeed
- Four-way alignment meeting includes all three (+ Sarah + Kevin)
- Address each veto power's concerns explicitly:
  - Jennifer: Realistic budget, contingency, kill criteria, honest assessment
  - Robert: Parallel running, no downtime, union engagement, operational benefits
  - Kevin: Infrastructure investment, network resolution, staffing, operational discipline
- Build coalition where all three support publicly
- Create "Steering Committee" with all three (+ Michael + Sarah) for ongoing alignment

**Owner**: Michael Chen (must orchestrate)  
**Status**: Open - URGENT (board presentation approaching)

---

## Risk 21: Hardware Failure Cascade

**Category**: Technical  
**Probability**: High (80%)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Infrastructure experiencing exponential hardware failure rates. Q2: 4 failures, Q3: 8 failures, Q4: 14 failures. 247 servers averaging 8.4 years old (3+ years past industry standard of 5 years). Storage at 87% capacity, will hit 90% crisis by Q2 2025. Trend indicates continued exponential growth.

**Impact**:
- Critical system failure during migration could derail entire initiative
- May force emergency $1M+ spending on hardware replacement
- Could extend timeline by 3-6 months if major system fails
- Loss of data if storage hits capacity before backup infrastructure upgraded
- Team distracted by constant firefighting instead of migration work

**Root Cause**: $4.2M infrastructure refresh requested, only $800K approved. Jennifer cut budget 18 months ago citing "moving to cloud anyway." Infrastructure aged another 18 months without investment.

**Mitigation Strategy**:
- **Immediate**: Allocate $2.5M for infrastructure stabilization in Year 1 budget
  - $1.2M SAN replacement/expansion (get 3-5 year runway)
  - $800K critical server refresh (MES, ERP, DB servers)
  - $300K backup infrastructure
  - $150K monitoring tools
- **Short-term**: Identify and replace highest-risk servers before migration starts
- **Contingency**: Emergency hardware budget of $500K for unexpected failures

**Owner**: Kevin Martinez  
**Status**: Open - Urgent action required  
**Dependencies**: Jennifer's budget approval

**Notes**: Cannot defer all $4.2M, but must address $2.5M minimum to maintain stability during 12-24 month migration.

---

## Risk 22: Network Capacity Bottleneck

**Category**: Technical  
**Probability**: High (100% if not addressed)  
**Impact**: Show-stopper  
**Severity**: CRITICAL

**Description**: Current 200 Mbps internet circuit requires 6-7 MONTHS just to transfer 50TB of data to Azure. Cannot saturate circuit 24/7 as business requires it for operations. This adds 6-8 months to ANY migration timeline unless resolved.

**Impact**:
- Adds minimum 6-8 months to migration timeline
- Delays entire Phase 1 (cannot start until data transfer complete)
- Michael's 18-month timeline becomes impossible (network alone is 6-8 months)
- Ongoing replication during parallel running consumes bandwidth
- User experience degraded if hybrid apps (on-prem users hitting Azure) share limited bandwidth

**Root Cause**: Network infrastructure adequate for current operations, not for cloud migration. 200 Mbps circuit installed 2018, sized for pre-cloud needs.

**Mitigation Strategy**:
- **Option A - Circuit Upgrade** (Kevin's recommendation for long-term):
  - Upgrade to 1 Gbps circuit
  - Cost: $60K upfront + $4K/month ($48K/year ongoing)
  - Timeline: 30-60 days to provision
  - Benefit: Reduces data transfer to 30-40 days + adequate for hybrid operations
  
- **Option B - Azure Data Box** (for initial bulk transfer):
  - Microsoft ships physical storage device, copy data locally, ship back
  - Cost: $3K per box × 3 boxes = $9K
  - Timeline: 2-3 weeks total
  - Limitation: Only for initial bulk transfer, doesn't help hybrid operations

- **Recommended**: Data Box for initial bulk transfer + circuit upgrade for ongoing hybrid operations

**Owner**: Kevin Martinez + Michael Chen  
**Status**: Open - Decision required within 30 days

**Notes**: This is a hard constraint - no amount of planning can overcome physics of data transfer. Must be resolved before migration starts or accept 6-8 month delay.

---

## Risk 23: Cloud Cost Spiral (No ROI)

**Category**: Financial  
**Probability**: Medium-High (50%)  
**Impact**: Major  
**Severity**: CRITICAL

**Description**: Kevin assesses 50/50 chance cloud costs will match on-prem ($5M/year) with NO savings, eliminating entire business case. Root cause: Organizational culture of "build, accumulate, never clean up" (847 Crystal Reports, 30+ Access databases). If this culture transfers to cloud, will result in 600+ underutilized VMs running 24/7 at $300/month each.

**Impact**:
- Eliminates expected $2.25M/year (50%) cost savings
- Spent $10-15M on migration with zero ROI
- Triggers Jennifer's kill criteria (benefits not materializing)
- Damages credibility of IT leadership
- Board loses confidence, future initiatives blocked

**Root Cause**: Organizational culture - "We're good at capital budgeting, terrible at operational discipline." No cleanup culture, accumulate without deprecating.

**Mitigation Strategy**:
- **Pre-Migration**: Rationalize current environment (reduce 847 reports to 200, eliminate unused databases)
- **Day 1 Cloud Operations**: Weekly cost reviews, auto-shutdown non-prod, strict tagging/chargeback
- **Governance**: Approval required for new resources, 90-day review cycle, reserved instances
- **Cultural Change**: Training on cost optimization, KPIs include cost efficiency, celebrate savings

**Owner**: Kevin Martinez + Sarah Mitchell + Finance  
**Status**: Open - Requires organizational change management plan

**Notes**: This is THE risk to ROI. Kevin's confidence only 50/50 that organization can maintain discipline.

---

## HIGH RISKS (Major Impact)

## Risk 03: Short-term Cost Increase

**Category**: Financial  
**Probability**: Very High (95%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Jennifer's analysis shows Year 1 costs DOUBLE to $9-11M (from $4.5M current). Kevin's analysis confirms: Year 1-2 costs $8.75-9.75M/year. Includes infrastructure ($2.5M), migration ($6-8M), parallel running ($4.5M/year on-prem). Michael may not understand this reality yet.

**Impact**:
- Sticker shock when full costs revealed
- Budget insufficient if Michael only planned for $4.5M ongoing
- Jennifer withholds approval or forces scale-back
- CFO skepticism damages initiative momentum

**Root Cause**: Cloud requires investment BEFORE returns. Must run both environments during 12-24 month migration.

**Mitigation Strategy**:
- Present honest Year 1-2 cost doubling to Michael NOW
- Get Jennifer's buy-in on multi-year budget ($10-15M over 3 years)
- Frame as "investment thesis" not "run-rate cost"
- Show breakeven in Year 3-4
- Contingency budget for overruns (Jennifer's requirement)

**Owner**: Jennifer Walsh + Kevin Martinez  
**Status**: Open - Cost model needed before board presentation

---

## Risk 04: SAP Trauma Influence

**Category**: Organizational/Political  
**Probability**: High (75%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: 2018 SAP implementation failure ($2.3M write-off) still influences all stakeholder thinking. Jennifer keeps memo in drawer. All four stakeholders (Michael, Sarah, Jennifer, Robert) referenced SAP failure unprompted. Organizational trauma creates skepticism toward ANY large technology initiative.

**Impact**:
- Higher burden of proof for Michael
- Jennifer's veto trigger-ready ("not another SAP")
- Board skeptical of IT promises
- Conservative approach may under-resource initiative
- Past failure creates self-fulfilling prophecy

**Root Cause**: Previous CTO over-promised, under-delivered, created $2.3M loss and operational disruption.

**Mitigation Strategy**:
- Acknowledge SAP failure explicitly
- Show what was learned ("honest assessment, realistic timeline")
- Differentiate this initiative (proven technology, phased approach, kill criteria)
- Leverage Jennifer's four non-negotiables (she learned from SAP)
- Build trust through small wins before big commitments

**Owner**: Michael Chen  
**Status**: Open - Must be addressed in board presentation

---

## Risk 05: Cyber Insurance Crisis (90 Days)

**Category**: Compliance/Legal  
**Probability**: Very High (90%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Cyber insurance expires in 90 days, renewal requires MFA implementation. Cost jumps from $180K to $340K without MFA ($160K increase). Michael promised to deliver MFA in 90 days as a "quick win."

**Impact**:
- $160K annual cost increase if MFA not delivered
- Loss of cyber insurance coverage (unacceptable risk)
- Damages Michael's credibility if first promise fails
- Distracts from Azure migration if firefighting insurance crisis

**Root Cause**: Years of security underinvestment, now forced by insurance market.

**Mitigation Strategy**:
- Prioritize MFA implementation (before Azure migration)
- Use proven solution (Azure AD MFA already licensed)
- Pilot with IT team, then roll out company-wide
- Training and communication plan for 200 users
- Have Plan B for insurance if MFA delayed

**Owner**: Michael Chen + Sarah Mitchell  
**Status**: Open - 90 day clock ticking

---

## Risk 08: Cost Savings Timeline Mismatch

**Category**: Financial  
**Probability**: Very High (90%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: 
- Michael's promise: 50% savings ($2.25M/year) in 18 months
- Jennifer's analysis: Savings Year 4+ (3-5 years out)
- Kevin's analysis: Maybe $1.5M/year IF disciplined, by Year 4+ (50/50 chance of zero savings)

Board expects savings in 18 months, but reality is 3-5 years minimum (if at all).

**Impact**:
- Board disappointed in Year 2 when costs still high
- Pressure to show ROI before benefits materialize
- Initiative cancelled mid-stream ("not delivering promised savings")
- Michael's credibility damaged, possibly terminated

**Root Cause**: Cloud requires upfront investment, savings come from decommissioning on-prem (which happens LAST).

**Mitigation Strategy**:
- Reset board expectations to 3-5 year timeframe
- Show investment curve: Year 1-2 costs up, Year 3 breakeven, Year 4+ savings
- Quantify non-financial benefits (reliability, security, agility)
- Define intermediate success metrics (not just cost savings)
- Be honest: "This is investment, not immediate cost reduction"

**Owner**: Michael Chen + Jennifer Walsh  
**Status**: Open - Must be addressed at board presentation

---

## Risk 09: Sarah's Team Capacity

**Category**: Organizational/Technical  
**Probability**: Very High (85%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Sarah's team already underwater (80% maintenance, 20% innovation), best people leaving. Cannot absorb Azure migration on top of current workload. Team exhausted, low morale. Kevin's infrastructure team similarly underwater (9 people supporting 247 servers, firefighting daily).

**Impact**:
- Migration stalls due to lack of capacity
- Quality issues due to rushed work
- More people quit (brain drain accelerates)
- Burnout leads to mistakes, security issues
- Timeline extends indefinitely

**Root Cause**: Years of underinvestment, technical debt accumulated, no capacity for strategic work.

**Mitigation Strategy**:
- Hire contractors for Azure migration (don't burden existing team)
- Kevin's plan: $1.4-2M Year 1 for cloud architects and engineers
- Create separate "Cloud Migration Team" (don't add to BAU workload)
- Address technical debt in parallel (rationalize 847 reports, etc.)
- Celebrate and retain good people (Sarah's trust is critical)

**Owner**: Sarah Mitchell + Kevin Martinez + Michael Chen  
**Status**: Open - Staffing plan needed

---

## Risk 11: Parallel Running Complexity

**Category**: Operational/Technical  
**Probability**: Very High (90%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Robert requires 3+ month parallel running for MES and other critical systems. Kevin quantifies infrastructure cost at $800K-1.2M for 8-10 systems. Must run old and new simultaneously, sync data, monitor both 24/5, have rollback capability. Complexity often underestimated.

**Impact**:
- Cost overrun if not budgeted ($800K-1.2M infrastructure alone)
- Data synchronization failures cause data loss or corruption
- Production disruption if cutover goes wrong
- Extended parallel running if issues found (months become years)
- Robert loses confidence if production impacted

**Root Cause**: Critical systems cannot tolerate downtime, must prove new system works before decommissioning old.

**Mitigation Strategy**:
- Budget explicitly for parallel running ($1M+ line item)
- Phase systems (not all parallel at once)
- MES last (highest risk, longest parallel window)
- Invest in data sync tools and monitoring
- Practice cutover (rehearsal in test environment)
- Define rollback criteria and process

**Owner**: Robert Turner + Kevin Martinez + Sarah Mitchell  
**Status**: Open - Parallel running plan needed

---

## Risk 12: Lost Source Code / Black Box Components

**Category**: Technical  
**Probability**: Medium-High (70%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Sarah revealed: Lost source code for COM+ components, 30+ undocumented Access databases, 847 Crystal Reports with unknown dependencies. Cannot migrate what you don't understand. Reverse engineering required, may discover showstoppers.

**Impact**:
- Migration blocked for critical systems
- Forced to rebuild from scratch (months of work)
- Dependency mapping takes longer than expected
- Hidden functionality lost in migration
- Robert's "zero downtime" impossible if don't understand systems

**Root Cause**: 15+ years of technical debt, turnover, no documentation.

**Mitigation Strategy**:
- Discovery phase: Inventory and document all systems FIRST
- Prioritize systems with source code for early migration
- Reverse engineer black box components (time and budget required)
- Accept some systems may need rebuild vs. migrate
- Engage original developers if possible (Sarah's institutional knowledge)
- Add 30-50% contingency time for unknown unknowns

**Owner**: Sarah Mitchell  
**Status**: Open - Technical discovery workstream needed

---

## Risk 15: Michael's Trust Deficit

**Category**: Organizational/Political  
**Probability**: High (75%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Consistent pattern across all interviews: Sarah, Jennifer, and Robert all trust Sarah more than Michael. Michael only 60 days in, hasn't earned trust yet. If conflict arises between Michael's vision and Sarah's reality, stakeholders will believe Sarah.

**Impact**:
- Michael's proposals questioned or rejected
- Sarah's assessment carries more weight with Jennifer and Robert
- Michael seen as "outsider who doesn't understand us"
- Coalition forms against Michael if he's not aligned with Sarah
- Initiative stalls due to trust deficit

**Root Cause**: Michael is new (60 days), Sarah has 15 years tenure and institutional knowledge.

**Mitigation Strategy**:
- Michael must align WITH Sarah, not against her
- Leverage Sarah's credibility (she supports the plan publicly)
- Joint presentations (Michael + Sarah) to board and stakeholders
- Michael listens and incorporates Sarah's feedback
- Sarah becomes Michael's "sponsor" to other stakeholders
- Michael earns trust through delivering 90-day wins (MFA)

**Owner**: Michael Chen  
**Status**: Open - Trust building ongoing

---

## Risk 16: Robert's Five Unanswered Questions

**Category**: Organizational/Political  
**Probability**: High (80%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Robert has five questions Michael must answer before Robert supports to CEO:
1. What operational benefits, not just cost savings?
2. How will you ensure zero downtime?
3. What's your union engagement strategy?
4. How will you earn my team's trust?
5. What happens if this fails?

Michael hasn't answered these yet. Robert is CEO's confidant and holds effective veto power.

**Impact**:
- Robert doesn't support to CEO, initiative stalls
- Michael proceeds without Robert, operations resists
- CEO sides with Robert (his best friend) over Michael
- Michael's authority undermined
- Plant floor sabotages new systems if not on board

**Root Cause**: Michael focused on technical/cost story, not operational/people story.

**Mitigation Strategy**:
- Michael answers all five questions explicitly (in writing)
- Present to Robert for feedback/iteration
- Incorporate into board presentation
- Operational benefits: Real-time analytics, predictive maintenance, better quality data
- Zero downtime: Parallel running, phased approach, 4-hour maintenance windows
- Union: Early engagement with Jimmy, no layoffs commitment
- Trust: Factory floor immersion (Robert's requirement), operational partnership
- Failure plan: Phase gates, kill criteria, rollback capability

**Owner**: Michael Chen  
**Status**: Open - Robert waiting for answers

---

## Risk 18: Lost Institutional Knowledge

**Category**: Organizational/Technical  
**Probability**: Medium-High (60%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Sarah holds critical institutional knowledge (15 years). If she leaves or isn't engaged, knowledge walks out the door. Best people already leaving Sarah's team. Brain drain accelerates if people see "another failed initiative."

**Impact**:
- Lost understanding of why systems work the way they do
- Unable to answer "why" questions during migration
- Dependency mapping impossible without Sarah's knowledge
- Migration quality suffers without her insight
- If Sarah leaves, initiative nearly impossible

**Root Cause**: Knowledge concentrated in few people, not documented.

**Mitigation Strategy**:
- Retain Sarah at all costs (pay, recognition, influence)
- Document Sarah's knowledge (system inventory, dependency maps, business rules)
- Cross-train team (Sarah mentors, knowledge spreads)
- Celebrate and retain other key people (Mark, Priya from Kevin's team)
- Make Sarah co-owner of initiative (not just Michael's initiative)
- Success of initiative boosts Sarah's team morale (reduces attrition)

**Owner**: Michael Chen + Sarah Mitchell  
**Status**: Open - Retention and knowledge capture plan needed

---

## Risk 24: Azure Expertise Gap

**Category**: Organizational  
**Probability**: High (90%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Current team of 9 lacks Azure expertise. Strong in Windows/VMware/SQL, very weak in Azure/Linux/DevOps/IaC/cloud networking/cloud security. Only Mark has Azure training, never at scale. Cannot train fast enough while firefighting daily hardware failures. Need $1.4-2M Year 1 for contractors and new hires.

**Impact**:
- Poor architecture decisions (inefficient, not cost-optimized, not secure)
- Quality issues during migration (data loss, downtime, functionality breaks)
- Cost overruns (don't know how to optimize)
- Security vulnerabilities (cloud security different from on-prem)
- Slow migration pace (learning on the job)
- Robert loses confidence if quality issues hit production

**Root Cause**: Team hired/trained for on-prem Windows environment, no time to retrain while firefighting failures.

**Mitigation Strategy**:
- **Contractors (12-18 months)**:
  - 2 senior cloud architects @ $200/hour × 2000 hours = $800K-1.2M
  - 1 Azure security specialist (6-12 months) = $250-500K
- **FTE Hires**: 2 cloud engineers @ $150K fully loaded = $300K/year ongoing
- **Training**: Existing team Azure certifications = $50K
- **Knowledge Transfer**: Contractors must document and train, not just do

**Owner**: Kevin Martinez + Sarah Mitchell + Michael Chen  
**Status**: Open - Staffing plan and budget required

---

## Risk 25: Licensing Cost Trap

**Category**: Financial  
**Probability**: High (80%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Azure Hybrid Benefit promises 40% compute savings by reusing existing Windows/SQL licenses. BUT requires active Software Assurance (SA). Contoso let SA lapse on 60% of servers during budget cuts 3 years ago. Must pay $800K to catch up on licensing BEFORE getting any benefit.

**Impact**:
- $800K unexpected cost in Year 1
- Without catch-up, Azure compute costs 40% higher than planned
- Over 3 years, no SA means $2-3M higher Azure costs
- Triggers Jennifer's kill criteria if budget variance >20%

**Root Cause**: Budget cuts 3 years ago eliminated SA renewals (short-term savings), decision made without considering future cloud migration impact.

**Mitigation Strategy**:
- **Year 1 Budget**: Add $800K line item for license catch-up
- **Alternative**: Migrate to Linux where possible (no Windows licensing)
- **Future**: Maintain SA going forward (penny-wise, pound-foolish to let lapse)

**Owner**: Kevin Martinez + Jennifer Walsh  
**Status**: Open - Budget allocation needed

---

## Risk 26: Hidden Cloud Costs Surprise

**Category**: Financial  
**Probability**: High (70%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: $1-2M/year in hidden Azure costs that most people don't budget: data egress ($200-500K), Azure services "tax" ($150K for load balancers, IPs, firewall, logging), DR ($300K), management tools ($100-150K), training ($50K), consulting/support ($200-500K in Years 1-2).

**Impact**:
- Budget variance of 20-40% in Year 1
- Triggers Jennifer's 20% variance kill criteria
- Surprise bills cause budget crisis mid-migration
- Forces cuts to other areas or initiative cancellation

**Root Cause**: Focus on "compute" costs (VMs), ignore "plumbing" costs. Data egress not intuitive (ingress free, egress costs money).

**Mitigation Strategy**:
- **Comprehensive Cost Model**: Build detailed 5-year TCO including ALL costs (Kevin + Sarah + Jennifer)
- **Monitoring**: Set up cost alerts from Day 1, weekly cost reviews
- **Specific Line Items**: Compute, storage, networking, security, management, backup/DR, tools, support, training, consulting

**Owner**: Kevin Martinez + Sarah Mitchell + Jennifer Walsh  
**Status**: Open - Comprehensive cost model needed by board presentation (15 days)

---

## Risk 27: Parallel Running Budget Gap

**Category**: Financial  
**Probability**: High (90%)  
**Impact**: Major  
**Severity**: HIGH

**Description**: Robert requires 3+ month parallel running for critical systems (MES, ERP, quality, inventory, plus 4-6 others = 8-10 total). Kevin estimates infrastructure costs alone at $800K-1.2M. Michael appears unaware of this cost (per Kevin's knowledge), so likely not budgeted.

**Impact**:
- $800K-1.2M budget overrun mid-migration
- Triggers Jennifer's 20% variance kill criteria
- Cannot meet Robert's parallel running requirement without budget
- Quality/safety risk if forced to cut corners on parallel running

**Root Cause**: Parallel running requirement clear (Robert stated), but cost not quantified until Kevin's interview.

**Cost Breakdown** (Kevin's estimates):
- MES: $150-200K for 90-day parallel window
- ERP: $100-150K for 60-day window
- Quality Management: $80-100K for 60-day window
- Inventory: $60-80K for 45-day window
- 4-6 other critical systems: $400-600K combined
- Total: $800K-1.2M

**Mitigation Strategy**:
- **Budget**: Add explicit $1M line item for "Parallel Running Infrastructure"
- **Phasing**: Stagger migrations to reduce peak parallel cost
- **Optimization**: Use Azure Dev/Test pricing, auto-scale, shut down if rollback

**Owner**: Kevin Martinez + Robert Turner + Michael Chen  
**Status**: Open - Budget allocation and phasing plan needed

---

## MEDIUM RISKS (Moderate Impact)

## Risk 06: SOC 2 Timeline Pressure (12 Months)

**Category**: Compliance  
**Probability**: High (80%)  
**Impact**: Moderate  
**Severity**: MEDIUM

**Description**: $90M revenue dependent on SOC 2 compliance by month 12-18. Michael promised this as forcing function. Realistic timeline is 12-24 months with focused effort. Azure migration may distract from compliance work.

**Impact**:
- Miss SOC 2 deadline, lose $90M revenue opportunity
- Forced to choose: Azure migration or SOC 2 (can't do both simultaneously)
- Michael's credibility damaged if misses forcing function promise
- Business growth blocked without SOC 2

**Root Cause**: Competing priorities, limited team capacity.

**Mitigation Strategy**:
- Prioritize SOC 2 over Azure migration if necessary
- Separate teams for compliance vs. migration
- Leverage Azure for compliance (many controls built-in)
- External consultant for SOC 2 audit prep
- Phase 0 Azure discovery doesn't conflict with SOC 2 work

**Owner**: Michael Chen + Compliance Lead  
**Status**: Open - Prioritization decision needed

---

## Risk 13: Christmas Cutover Myth

**Category**: Operational  
**Probability**: Medium (50%)  
**Impact**: Moderate  
**Severity**: MEDIUM

**Description**: Michael mentioned "Christmas cutover window" (Dec 23-Jan 2). Robert clarified this is 10 calendar days but only 6-7 usable work days with skeleton crew. Kevin agrees: Great for tactical upgrades, not strategic transformation. Last Christmas ERP upgrade: Planned 48 hours, actual 92 hours (barely made Jan 3 startup).

**Impact**:
- Over-reliance on Christmas window for major changes
- Insufficient time for complex cutovers
- Skeleton crew if something goes wrong
- Vendors/contractors unavailable Dec 24-Jan 2
- If can't start production Jan 3: $240K/day loss
- Sets unrealistic expectations for timeline compression

**Root Cause**: Christmas is only long shutdown window, tempting to use for big changes.

**Mitigation Strategy**:
- Use Christmas for single-system tactical upgrades only
- Do NOT plan Azure migration major milestones for Christmas
- Phase cutover over multiple maintenance windows (not all at once)
- If using Christmas: Practice in test environment first, have full rollback plan
- Budget for 4-hour Sunday maintenance windows throughout year (Robert provides)

**Owner**: Robert Turner + Kevin Martinez  
**Status**: Open - Realistic cutover strategy needed

---

## Risk 17: Maintenance Window Scarcity

**Category**: Operational  
**Probability**: Medium-High (65%)  
**Impact**: Moderate  
**Severity**: MEDIUM

**Description**: Factory runs 24/5 (Mon-Fri), $10K/minute downtime cost. Maintenance windows are Sunday only, 4-hour max. Robert must coordinate with production planning. Cannot take downtime casually. Limits migration pace and testing opportunities.

**Impact**:
- Slow migration pace (can only make changes Sundays)
- Limited testing windows (pressure to "get it right first time")
- Production impact if maintenance overruns 4 hours
- Difficult to troubleshoot issues (pressure to complete quickly)

**Root Cause**: 24/5 production schedule is business requirement, not optional.

**Mitigation Strategy**:
- Plan maintenance windows 6 months in advance (Robert coordinates with production)
- Multiple 4-hour windows for single migration (not force completion)
- Practice in test environment until confident (don't learn in production)
- Parallel running reduces pressure (can rollback)
- Christmas window for larger changes (but not full migration)

**Owner**: Robert Turner + Kevin Martinez  
**Status**: Open - Maintenance window calendar needed

---

## Risk 19: Customer-Facing System Downtime

**Category**: Operational/Financial  
**Probability**: Medium (50%)  
**Impact**: Moderate  
**Severity**: MEDIUM

**Description**: Customer portal, order entry, and tracking systems are customer-facing. Downtime or quality issues directly impact customer experience and revenue. Must be more careful with these than internal systems.

**Impact**:
- Customer complaints and frustration
- Lost sales if order entry down
- Support call volume spikes
- Damaged reputation with key accounts
- Revenue impact if sustained issues

**Root Cause**: Customers have zero tolerance for poor experience.

**Mitigation Strategy**:
- Migrate customer-facing systems LAST (after proving competence)
- Longer parallel running for customer systems (6+ months)
- Gradual traffic cutover (not all-at-once)
- Enhanced monitoring and support for customer systems
- Communication plan to customers before changes
- Rollback plan immediately available

**Owner**: Sarah Mitchell + Sales/Support Leaders  
**Status**: Open - Customer system migration plan needed

---

## Risk 20: GMP/Validation Requirements

**Category**: Compliance  
**Probability**: Medium (50%)  
**Impact**: Moderate  
**Severity**: MEDIUM

**Description**: Some systems may have Good Manufacturing Practice (GMP) or validation requirements (pharmaceutical/medical device manufacturing). These systems require extensive documentation, testing, and qualification before changes. Migration complexity and cost much higher.

**Impact**:
- Migration timeline 2-3x longer for validated systems
- Extensive testing and documentation required
- Regulatory risk if validation inadequate
- High cost (validation consultants expensive)

**Root Cause**: Regulatory requirements for manufacturing systems (if applicable).

**Mitigation Strategy**:
- Inventory systems with GMP/validation requirements
- Budget additional time and cost for validated systems
- Engage validation consultants early
- Migrate validated systems LAST (most complex)
- Consider cloud validation frameworks (Azure offers guidance)
- Interview Quality Manager to understand requirements

**Owner**: Quality Manager + Sarah Mitchell  
**Status**: Open - Interview Quality Manager to assess

---

## Risk 28: Operational Discipline Failure

**Category**: Organizational  
**Probability**: Medium (50%)  
**Impact**: Major  
**Severity**: MEDIUM-HIGH

**Description**: Organizational culture of "build, accumulate, never clean up" (847 Crystal Reports when probably need 200, 30+ Access databases). If this culture transfers to cloud, will accumulate underutilized resources costing $300/month each. 600 such VMs = $2.16M/year wasted, eliminating ROI.

**Impact**:
- Cloud costs match on-prem ($5M/year) with no savings
- Spent $10-15M on migration for zero ROI
- Missed opportunity for $1.5M/year savings (optimistic scenario)
- Damages IT credibility with board and executives

**Root Cause**: Current environment - capital already spent, no ongoing cost accountability. Cloud makes accumulation easier ("I'll spin up a VM" vs. requesting hardware).

**Mitigation Strategy**:
- **Pre-Migration Culture Change**: Rationalize BEFORE migrating (reduce 847 reports to 200, eliminate unused databases)
- **Cloud Governance from Day 1**: Tagging policy, chargeback model, auto-shutdown non-prod, 90-day review cycle
- **Cultural Reinforcement**: KPIs include cost efficiency, celebrate optimization
- **Leadership Commitment**: Michael must model and reward discipline

**Owner**: Michael Chen + Sarah Mitchell + All Business Unit Leaders  
**Status**: Open - Requires organizational change management plan

**Notes**: Kevin rates confidence at 50/50. This is an ORGANIZATIONAL challenge, not technical.

---

## Risk 29: Repeated Failure Pattern (Organizational Trauma)

**Category**: Organizational  
**Probability**: Medium (40%)  
**Impact**: Show-stopper  
**Severity**: MEDIUM-HIGH

**Description**: Kevin has seen this pattern THREE times in 15 years: "Big vision, mounting costs, reality hits, initiative stalls, leader leaves, cycle repeats." SAP failure 2018 ($2.3M write-off) still remembered by all stakeholders. Organization has PTSD from failed transformation attempts.

**Impact**:
- Organization loses faith in IT leadership
- Board stops funding transformation initiatives
- Talent leaves (best people tired of false starts)
- Company falls further behind competitors
- Next attempt in 3-5 years starts with even lower trust

**Root Cause**: Pattern recognition by Kevin - previous CTO's cloud initiative stalled 18 months ago, SAP failed 2018, other failed initiatives.

**Common factors**:
- Big promises to board without ground truth
- Costs escalate beyond budget
- Timeline slips
- Executive leaves (voluntary or forced)
- Initiative cancelled or scaled back

**Mitigation Strategy**:
- **THIS TIME: DIFFERENT APPROACH**:
  - Ground truth BEFORE board promises (Phase 0 discovery)
  - Four-way alignment (Michael + Jennifer + Robert + Sarah + Kevin) BEFORE committing
  - Realistic budget with contingency
  - 3-year timeline with phased milestones
  - Kill criteria defined upfront (Jennifer's approach)
  
- **Acknowledge Trauma Explicitly**:
  - "We know previous attempts failed"
  - "Here's what we learned from SAP"
  - "Here's how this time is different"
  
- **Build Coalition of Credible Voices**: Sarah (15 years), Jennifer (learned from SAP), Robert (CEO's confidant), Kevin (infrastructure reality)
  
- **Incremental Validation**: Phase gates, prove it works before scaling

**Owner**: Michael Chen (must break the pattern)  
**Status**: Open - Requires different leadership approach than predecessors

**Notes**: This is the META-RISK that encompasses many others. If Michael repeats the pattern, organizational trauma deepens. The four-way alignment meeting is the key intervention to break the cycle.

---

## Risk Summary by Category

### Financial Risks (8)
- R03: Short-term Cost Increase (HIGH)
- R07: Budget Realism Gap (CRITICAL)
- R08: Cost Savings Timeline Mismatch (HIGH)
- R23: Cloud Cost Spiral (CRITICAL)
- R25: Licensing Cost Trap (HIGH)
- R26: Hidden Cloud Costs Surprise (HIGH)
- R27: Parallel Running Budget Gap (HIGH)
- R19: Customer-Facing System Downtime (MEDIUM)

### Technical Risks (7)
- R12: Lost Source Code / Black Box Components (HIGH)
- R21: Hardware Failure Cascade (CRITICAL)
- R22: Network Capacity Bottleneck (CRITICAL)
- R11: Parallel Running Complexity (HIGH)
- R24: Azure Expertise Gap (HIGH)
- R06: SOC 2 Timeline Pressure (MEDIUM)
- R20: GMP/Validation Requirements (MEDIUM)

### Organizational Risks (9)
- R01: Timeline Misalignment (CRITICAL)
- R02: Executive Alignment Gap (CRITICAL)
- R04: SAP Trauma Influence (HIGH)
- R09: Sarah's Team Capacity (HIGH)
- R15: Michael's Trust Deficit (HIGH)
- R18: Lost Institutional Knowledge (HIGH)
- R28: Operational Discipline Failure (MEDIUM-HIGH)
- R29: Repeated Failure Pattern (MEDIUM-HIGH)
- R14: Three Veto Powers Uncoordinated (CRITICAL)

### Operational Risks (3)
- R10: Union Negotiation Failure (CRITICAL)
- R13: Christmas Cutover Myth (MEDIUM)
- R17: Maintenance Window Scarcity (MEDIUM)

### Compliance/Legal Risks (2)
- R05: Cyber Insurance Crisis (HIGH)
- R20: GMP/Validation Requirements (MEDIUM)

---

## Critical Path to Success

### Must Resolve Before Board Presentation (15 days):
1. ✅ **Four-way alignment meeting** (Michael + Jennifer + Robert + Sarah + Kevin)
2. ✅ **Comprehensive cost model** ($10-15M over 3 years, including ALL costs)
3. ✅ **Realistic timeline** (3 years with phase gates, not 18 months)
4. ✅ **Michael-Jennifer budget alignment** (prevent public challenge)
5. ✅ **Answer Robert's five questions** (get his support to CEO)

### Must Resolve Before Phase 1 Start:
6. ✅ **Network capacity resolution** (1 Gbps upgrade or Azure Data Box)
7. ✅ **Infrastructure stabilization budget** ($2.5M secured)
8. ✅ **Cloud expertise staffing** ($1.4-2M contractors/hires approved)
9. ✅ **Union engagement** (Interview Jimmy, no layoffs commitment)
10. ✅ **Parallel running budget** ($1M line item approved)

### Must Maintain Ongoing:
11. ✅ **Operational discipline** (weekly cost reviews, cleanup culture)
12. ✅ **Trust building** (deliver 90-day wins, align with Sarah)
13. ✅ **Coalition management** (keep Jennifer, Robert, Kevin aligned)

---

**End of Risk Register**

*Last Updated: After Interview 5 (Kevin Martinez)*  
*Total Risks: 29 (8 Critical, 14 High, 7 Medium)*  
*Next Update: After Interview 6 (Jimmy Garcia - Union Steward)*  
*Phase 0 - Discovery & Ideation*  
*Contoso Manufacturing Azure Modernization Initiative*
