# Risk Register - Azure Modernization Initiative

**Last Updated**: 2025-11-06 (After Interviews 10-11)  
**Total Risks**: 55  
**Status**: ACTIVE TRACKING

---

## Risk Summary Statistics

### By Severity
- **CRITICAL (20-25)**: 11 risks
- **HIGH (15-19)**: 17 risks
- **MODERATE (10-14)**: 21 risks
- **LOW (1-9)**: 6 risks

### By Category
- **Timeline Risks**: 9 risks
- **Capacity Risks**: 11 risks
- **Technical Risks**: 8 risks
- **Organizational Risks**: 12 risks
- **Financial Risks**: 7 risks
- **Operational Risks**: 8 risks

### Risk Velocity
- **Worsening**: 8 risks (getting worse without intervention)
- **Stable**: 31 risks (understood but not improving)
- **Improving**: 5 risks (mitigation in progress)

---

## CRITICAL RISKS (Score 20-25) - Top Priority

### RISK-001: Timeline Compression Impossibility
**Score**: 25/25 (CRITICAL)  
**Category**: Timeline  
**Status**: WORSENING

**Description**: Michael's 18-month timeline is mathematically impossible due to Sunday window constraint. Only 12 Sunday maintenance windows per year (4 hours each = 48 hours/year total) for ALL IT changes, shared with mechanical/electrical maintenance. Sequential dependencies (ERP → warehouse → MES) mean systems cannot be migrated in parallel. This single constraint alone proves 3-5 year minimum timeline.

**Impact**: 
- Project will miss all commitments
- Board expectations completely misaligned
- Credibility loss when timeline slips
- Potential project cancellation when reality becomes clear

**Likelihood**: 100% (certain to occur)

**Root Cause**: 
- Physical constraint (Sunday windows)
- Mathematical reality (48 hours/year inadequate)
- Sequential dependencies cannot be overcome
- Michael's timeline based on optimism, not physics

**Mitigation**:
- Reset board expectations immediately with mathematical proof
- Accept 36-60 month (3-5 year) timeline
- Phase gates every 6-12 months with go/no-go decisions
- Use Christmas shutdown for tactical upgrades (additional windows)

**Owner**: Michael + Jennifer + Board  
**Mitigation Cost**: $0 (acceptance of reality)  
**First Identified**: Interview 2 (Sarah), Interview 8 (Maria - mathematical proof)

---

### RISK-002: Team Capacity Collapse
**Score**: 24/25 (CRITICAL)  
**Category**: Capacity  
**Status**: WORSENING

**Description**: IT team already underwater with BAU work (300+ open tickets, brutal on-call, 3-4 pages/night). Cannot absorb migration workload without additional capacity. Support team had 30% attrition in 18 months (3 of 10 people left). If people pulled for migration, BAU work stops. If migration added to current workload, people will quit due to burnout.

**Impact**:
- BAU work fails (production support suffers)
- Migration work fails (inadequate resources)
- Attrition accelerates (lose institutional knowledge)
- Project collapses under its own weight

**Likelihood**: 95% (almost certain without mitigation)

**Root Cause**:
- Team already at capacity (no slack)
- On-call rotation brutal (3-4 pages/night)
- No plan for backfill or contractors
- Burnout already happening (3 left in 18 months)

**Mitigation**:
- Hire 10-15 contractors minimum for migration work
- Hire 6-9 contractors for support backfill
- Address burnout BEFORE migration starts
- Reduce on-call burden (shared with contractors)
- Realistic timeline allows capacity to scale

**Owner**: Sarah + Jennifer  
**Mitigation Cost**: $4-6M over 3 years (contractors)  
**First Identified**: Interview 2 (Sarah), Interview 9 (Tom - 30% attrition)

---

### RISK-008: MES Production Disruption
**Score**: 22/25 (CRITICAL)  
**Category**: Operational  
**Status**: STABLE (high risk but well understood)

**Description**: MES migration could disrupt 24/7 production operations costing $150K/hour when lines are down. 180 operators with 10-15 years muscle memory must learn new system. 30-35% of current support tickets are MES-related (most problematic system). Even with perfect execution, expect 20-30% productivity drop for 2-3 months.

**Impact**:
- Production revenue loss ($150K/hour per line)
- Operator frustration and resistance
- Quality issues during learning curve
- Potential safety incidents from operator confusion
- Customer order fulfillment delays

**Likelihood**: 85% (very likely without proper approach)

**Root Cause**:
- MES is mission-critical (production stops without it)
- 180 operators across 3 shifts must all transition
- Muscle memory from 10-15 years usage
- System already problematic (30-35% of support tickets)
- No room for error in 24/7 operation

**Mitigation**:
- Migrate MES LAST (after proving approach on other systems)
- Pilot program (one line, 3-6 months)
- Parallel running (6-12 months minimum)
- Four-phase training (2 weeks + 3 months + gradual rollout + 6 months support)
- Floor-level support (all shifts, manufacturing background)
- Rollback capability and clear decision criteria

**Owner**: Robert + Maria + Sarah  
**Mitigation Cost**: $1.5-1.8M for MES migration alone  
**First Identified**: Interview 2 (Sarah), Interview 4 (Robert), Interview 8 (Maria)

---

### RISK-012: Validation Timeline Inadequacy
**Score**: 22/25 (CRITICAL)  
**Category**: Compliance  
**Status**: STABLE (not in current timeline)

**Description**: 8 systems require GMP validation (3-6 months each = 24-48 months total if sequential). Validation cannot be compressed without regulatory violations. Patricia estimates 18-24 months minimum even with risk-based approach. This timeline not reflected in Michael's 18-month plan.

**Impact**:
- Regulatory violations if systems deployed without validation
- FDA warning letters or consent decrees
- Customer audit failures (aerospace, medical device)
- Product recalls if quality systems not properly validated
- Reputation damage and potential loss of key customers

**Likelihood**: 100% (certain if timeline not adjusted)

**Root Cause**:
- GMP systems require formal validation (regulatory requirement)
- 8 systems need validation (not 1 or 2)
- Each system: 3-6 months validation timeline
- Validation must be in critical path (cannot be parallel)
- Michael's timeline doesn't account for this

**Mitigation**:
- Integrate validation into critical path (not parallel)
- Start validation planning immediately
- Risk-based approach (focus on highest-risk systems)
- Patricia has veto authority on readiness
- External validators if needed to increase capacity

**Owner**: Patricia + David  
**Mitigation Cost**: $1.5-2.5M for validation work  
**First Identified**: Interview 5 (David), Interview 7 (Patricia)

---

### RISK-020: Union Relationship Breakdown
**Score**: 20/25 (CRITICAL)  
**Category**: Organizational  
**Status**: WORSENING (not yet engaged)

**Description**: Union requires 120-day notice before any floor system changes. Michael hasn't engaged union yet. Late engagement becomes adversarial fight rather than partnership. 180+ union members can passively resist adoption, making project fail regardless of technical success.

**Impact**:
- 4-6 month delay for 120-day notice period
- Adversarial relationship (late engagement = fight)
- Passive resistance from 180+ floor workers
- Grievances and work slowdowns
- Project failure despite technical success

**Likelihood**: 90% (very likely given current trajectory)

**Root Cause**:
- Union not engaged yet (late = adversarial)
- 120-day notice requirement not in timeline
- No partnership approach designed
- History of top-down imposition (SAP trauma)
- Jimmy already defensive about being left out

**Mitigation**:
- Immediate Michael-Jimmy meeting (within 7 days)
- Bargaining committee session (present partnership approach)
- Floor workers involved in UAT and design
- Training commitment ($9M+ for operators)
- No layoffs commitment (visible actions not words)
- Early involvement = partnership, late = fight

**Owner**: Michael + Jimmy + Robert  
**Mitigation Cost**: $0 (engagement), but delays timeline 4-6 months  
**First Identified**: Interview 4 (Robert), Interview 6 (Jimmy)

---

### RISK-028: Budget Inadequacy
**Score**: 20/25 (CRITICAL)  
**Category**: Financial  
**Status**: WORSENING (gaps growing with each interview)

**Description**: Current budget allocation $3M vs. realistic need $18.5-26.5M (520-780% gap). Training alone $12-15M (largest single cost). Support contractors $2-3M. Validation $1.5-2.5M. Infrastructure $3-5M. Parallel running $1-2M. Hidden costs $1-2M/year. No adequate contingency.

**Impact**:
- Project underfunded by $15.5-23.5M
- Will run out of money mid-stream
- Forced to cut corners (quality, training, validation)
- Partial implementation worse than no implementation
- Board loses confidence, may cancel project

**Likelihood**: 100% (certain without budget revision)

**Root Cause**:
- Michael's budget expectations too optimistic (50% of need)
- Training costs grossly underestimated ($12-15M discovered)
- Support contractors not budgeted ($2-3M)
- Validation costs not included ($1.5-2.5M)
- No realistic contingency (need $1.5-3M minimum)

**Mitigation**:
- Jennifer update budget model immediately
- Board presentation with realistic costs
- Phased funding over 3-5 years
- External validator to confirm estimates
- PE firm engagement and approval

**Owner**: Jennifer + Michael + Board + PE firm  
**Mitigation Cost**: N/A (need $15.5-23.5M additional funding)  
**First Identified**: Interview 2 (Sarah), Interview 3 (Jennifer), Interviews 7-9 (growing)

---

### RISK-033: MES Floor Adoption Resistance
**Score**: 20/25 (CRITICAL)  
**Category**: Organizational  
**Status**: WORSENING (Michael has zero floor credibility)

**Description**: 180 operators with 10-15 years muscle memory must unlearn habits and learn new system. Operator capability range: 1/3 tech-comfortable, 1/3 okay, 1/3 struggle. Michael has zero credibility on floor ("just another corporate guy with PowerPoint"). Without floor partnership, operators will passively resist through compliance without commitment.

**Impact**:
- Adoption failure (people don't use system properly)
- Workarounds and shadow processes
- Quality issues from improper usage
- Safety incidents from operator confusion
- Attrition (operators quit rather than adapt)
- Project technically successful but operationally failed

**Likelihood**: 80% (very likely without floor partnership)

**Root Cause**:
- 10-15 years muscle memory difficult to overcome
- Varied operator capability (1/3 will struggle)
- Michael has no floor credibility (hasn't done the work)
- Top-down approach breeds resistance
- SAP trauma makes operators defensive

**Mitigation**:
- Michael 8-hour floor shift (Maria's 2nd shift, within 30 days)
- Partnership approach (involve operators in design/UAT)
- Differentiated training (address capability range)
- Pilot with volunteers (build champions)
- Maria as champion (operators trust her)
- Four-phase training ($9M investment)

**Owner**: Michael + Maria + Robert  
**Mitigation Cost**: $9M for MES training + Michael's time commitment  
**First Identified**: Interview 4 (Robert), Interview 8 (Maria)

---

### RISK-034: SAP Trauma Organizational PTSD
**Score**: 20/25 (CRITICAL)  
**Category**: Organizational  
**Status**: STABLE (7 years old but still impactful)

**Description**: 2018 SAP implementation created lasting organizational trauma (3 weeks chaos, 50% production drop, 3 employees lost, $3M wasted). 7 years later, when corporate says "new system," people update resumes. Not just failed project, but PTSD that affects trust, morale, and willingness to try again.

**Impact**:
- Preemptive resistance ("here we go again")
- Attrition risk (people quit rather than go through SAP 2.0)
- Trust deficit that must be overcome
- Higher bar for proof and credibility
- Organizational memory shapes current response

**Likelihood**: 100% (trauma is real and persistent)

**Root Cause**:
- SAP was catastrophic (3 weeks chaos, 50% production drop)
- Inadequate training (2 hours for complex system)
- Top-down imposition (no floor involvement)
- 3 employees lost (2 quit, 1 transferred)
- Never properly acknowledged or addressed

**Mitigation**:
- Explicitly acknowledge SAP failure in all communications
- Document what went wrong (2 hour training, big bang, no support)
- Show what's different (pilot, real training, parallel running, support, rollback)
- Differentiate from SAP (not just "trust us")
- Build trust through early actions not promises

**Owner**: Michael + Robert + HR Director  
**Mitigation Cost**: $0 (acknowledgment) but affects every decision  
**First Identified**: Interview 2 (Sarah), Interview 4 (Robert), Interview 8 (Maria details)

---

### RISK-038: Support Team Attrition During Migration
**Score**: 20/25 (CRITICAL)  
**Category**: Capacity  
**Status**: WORSENING (already happening)

**Description**: Support team already had 30% attrition in 18 months (3 of 10 left). Team burned out from 3-4 pages/night, brutal on-call rotation, "running on fumes." Adding migration workload without addressing burnout will cause more attrition. Loss of institutional knowledge at critical time.

**Impact**:
- More people quit (accelerating attrition)
- Loss of institutional knowledge (how systems work)
- Remaining team overwhelmed (death spiral)
- BAU support suffers (production impact)
- Migration support suffers (project delay)
- Recruiting/training new people takes 6-12 months

**Likelihood**: 90% (very likely without intervention)

**Root Cause**:
- Team already burned out (3-4 pages/night every night)
- 30% attrition in 18 months (worse than typical IT)
- On-call rotation brutal (1 week every 5 weeks)
- Morale low, people "running on fumes"
- No plan to address burnout before adding migration load

**Mitigation**:
- Address burnout BEFORE migration starts
- Hire contractors to reduce on-call burden
- Improve on-call rotation (6-8 person rotation instead of 5)
- Retention bonuses for critical people
- Career development and training opportunities
- Realistic timeline allows capacity to scale properly

**Owner**: Sarah + Tom + HR Director  
**Mitigation Cost**: $500K retention bonuses + contractor costs  
**First Identified**: Interview 9 (Tom)

---

### RISK-039: Support Capacity Inadequacy
**Score**: 22/25 (CRITICAL)  
**Category**: Capacity  
**Status**: WORSENING

**Description**: Current ticket volume 80-100/day will double to 150-200/day during migration. Supporting BOTH old and new systems simultaneously for 12-36 months. Same 10 people cannot handle this load. If migration added without capacity, support collapses and both BAU and migration suffer.

**Impact**:
- Support response times degrade (operators wait longer)
- Ticket backlog explodes (300-350 → 500-600+)
- Priority system breaks (everything becomes urgent)
- BAU work suffers (production support inadequate)
- Migration support suffers (can't handle questions/issues)
- Support team quits (burnout accelerates)

**Likelihood**: 95% (almost certain without mitigation)

**Root Cause**:
- Ticket volume will double (80-100 → 150-200/day)
- Supporting old AND new systems (12-36 months)
- Same 10 people expected to handle doubled workload
- No contractors budgeted for support
- No plan for capacity scaling

**Mitigation**:
- Hire 6-9 support contractors immediately
  - 2-3 for BAU backfill ($300-450K/year)
  - 4-6 for migration support ($1.2-1.8M/18 months)
- Realistic timeline allows proper capacity planning
- Knowledge base and documentation (reduce ticket volume)
- Self-service tools where appropriate

**Owner**: Sarah + Tom + Jennifer  
**Mitigation Cost**: $2-3M for support contractors over migration period  
**First Identified**: Interview 2 (Sarah capacity), Interview 9 (Tom specifics)

---

### RISK-051: Key IT Personnel Flight Risk
**Score**: 20/25 (CRITICAL)  
**Category**: Organizational  
**Status**: WORSENING

**Description**: 25% of IT team (5 of 20 people) are at flight risk, with key personnel explicitly stating they will leave if project becomes "SAP 2.0." Kevin (infrastructure lead, 11 years tenure) explicitly said he'll leave if the approach isn't realistic. Rachel (senior developer, 8 years) is already looking at jobs. Three others at moderate risk. Losing these people during migration would be catastrophic due to lost institutional knowledge and execution capability.

**Impact**:
- Loss of critical institutional knowledge
- Project timeline delays (6-12 months per key person lost)
- Cost: $50-75K direct replacement cost per person
- Cost: $200-500K indirect per key person (timeline delays, knowledge transfer)
- Remaining team demoralized, triggering attrition cascade
- Project failure if multiple key people leave simultaneously

**Likelihood**: 85% (almost certain if project proceeds with unrealistic timeline/resources)

**Root Cause**:
- SAP trauma still affecting team psychology
- Current team already burned out (80-95% capacity)
- Fear of repeating "SAP 2.0" experience
- Perception that management doesn't understand reality
- Lack of confidence in project approach

**Mitigation**:
- Retention strategy with financial incentives ($400-500K total)
  - Tier 1 (Kevin, Tom, key leads): $15-20K each (5-7 people)
  - Tier 2 (Rachel, Steve, seniors): $10-12K each (8-10 people)
  - Tier 3 (solid contributors): $5-8K each (10-15 people)
  - Structure: 50% at 12 months, 50% at 24 months
- Career development opportunities (Azure skills, architecture exposure)
- Realistic timeline (36-48 months) reduces burnout fear
- Adequate contractor support (no 60-hour weeks for 3 years)
- Demonstrate management understands reality (Michael floor shift)
- Psychological safety and involvement in planning

**Owner**: Michael + Linda + Sarah  
**Mitigation Cost**: $400-500K (retention) + opportunity cost $1-3M if not retained  
**First Identified**: Interview 10 (Alex Kumar)

**Alex's Warning**:
> "If Kevin leaves, we're in serious trouble. He's the only one who really understands our infrastructure. And if this becomes 'SAP 2.0,' he's already told me he's out."

---

## HIGH RISKS (Score 15-19) - Urgent Attention Required

### RISK-003: Infrastructure Readiness Gap
**Score**: 19/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE (understood, not funded)

**Description**: Network infrastructure must be stabilized before migration can begin (6-8 months prerequisite work). Some segments still 100Mb (inadequate), others maxed out during shift changes. Cannot migrate without proper bandwidth. $2.5M Year 1 investment needed.

**Impact**:
- Cannot start migration until infrastructure ready (6-8 month delay)
- Poor performance if migrated on inadequate infrastructure
- User frustration and adoption resistance
- Project delays cascade

**Likelihood**: 100% (certain if not addressed)

**Mitigation**:
- $2.5M Year 1 infrastructure investment
- Network remediation before migration starts
- Treat as prerequisite, not parallel work

**Owner**: Sarah + Kevin  
**Mitigation Cost**: $2.5M Year 1  
**First Identified**: Interview 2 (Sarah)

---

### RISK-004: Knowledge Transfer Failure
**Score**: 17/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE

**Description**: Many custom applications built by developers who have since left company. Documentation is "minimal to nonexistent." Undocumented dependencies will break things during migration. Institutional knowledge exists in people's heads, not documentation.

**Impact**:
- Break systems during migration (unknown dependencies)
- Extended troubleshooting (no documentation)
- Delay while reverse-engineering systems
- Potential data loss or corruption

**Likelihood**: 70% (likely for at least some systems)

**Mitigation**:
- 6-month discovery phase to document systems
- Dependency mapping before migration
- Knowledge transfer from remaining staff
- External consultants with system expertise

**Owner**: Sarah + Application Development Team  
**Mitigation Cost**: Included in 6-month discovery phase  
**First Identified**: Interview 2 (Sarah)

---

### RISK-005: Oracle Licensing Cost Explosion
**Score**: 16/25 (HIGH)  
**Category**: Financial  
**Status**: STABLE

**Description**: Current Oracle licenses are perpetual (capex already paid). Cloud licensing is consumption-based (opex ongoing). Oracle cloud licensing notoriously expensive. May need to re-architect systems to avoid Oracle altogether, adding complexity and timeline.

**Impact**:
- Ongoing licensing costs higher than expected
- May eat all projected cost savings
- ROI case weakens or disappears
- May require system re-architecture (delay + cost)

**Likelihood**: 60% (likely to be expensive)

**Mitigation**:
- License audit and cost modeling upfront
- Consider migration away from Oracle (PostgreSQL, SQL Server)
- Negotiate volume licensing with Oracle
- Include in financial model

**Owner**: Sarah + Jennifer  
**Mitigation Cost**: TBD (depends on licensing approach)  
**First Identified**: Interview 2 (Sarah)

---

### RISK-006: Security Posture Degradation
**Score**: 18/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE

**Description**: During migration, security patches delayed, security team spread thin, attack surface increases. Cloud introduces new security concerns (misconfiguration, access management, data exposure). David's team already at capacity.

**Impact**:
- Security incidents during migration
- Data breaches or exposure
- Compliance violations
- Reputation damage
- Regulatory penalties

**Likelihood**: 65% (likely without proper security focus)

**Mitigation**:
- Prioritize security in migration planning
- Security architecture review before migration
- Dedicated security resources for cloud
- Security training for team
- Continuous security monitoring

**Owner**: David + Sarah  
**Mitigation Cost**: Included in contractor budget  
**First Identified**: Interview 2 (Sarah), Interview 5 (David)

---

### RISK-007: Disaster Recovery Testing Gap
**Score**: 15/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE

**Description**: Current DR is "basically nonexistent" per Michael. Cloud DR needs to be designed, tested, validated. DR testing will consume significant time and resources. Untested DR is no DR.

**Impact**:
- False sense of security (DR exists on paper only)
- Actual disaster reveals DR doesn't work
- Extended downtime during recovery
- Data loss
- Regulatory violations (DR required for GMP)

**Likelihood**: 50% (DR will have gaps unless thoroughly tested)

**Mitigation**:
- DR design as part of architecture
- Regular DR testing (quarterly minimum)
- DR testing integrated into project timeline
- Validation that DR meets RTO/RPO requirements

**Owner**: Sarah + David  
**Mitigation Cost**: Included in project timeline  
**First Identified**: Interview 1 (Michael), Interview 2 (Sarah)

---

### RISK-009: Data Migration Complexity
**Score**: 17/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE

**Description**: 15+ years of production data across multiple systems. Data quality issues, legacy formats, complex transformations. Data migration is 50-70% of total migration effort typically. GMP systems require validated data migration (adds 3-6 months per system).

**Impact**:
- Extended timeline (data migration takes longer than expected)
- Data quality issues (garbage in, garbage out)
- Production disruption during data cutover
- Validation failures (GMP systems)
- Potential data loss during migration

**Likelihood**: 70% (data migration always complex)

**Mitigation**:
- Data quality assessment upfront (6 months)
- Data migration strategy per system
- Extensive testing before cutover
- Parallel running to validate data accuracy
- Validated data migration for GMP systems

**Owner**: Sarah + DBAs + Patricia  
**Mitigation Cost**: Included in validation budget  
**First Identified**: Interview 2 (Sarah), Interview 7 (Patricia)

---

### RISK-010: Change Management Inadequacy
**Score**: 18/25 (HIGH)  
**Category**: Organizational  
**Status**: WORSENING (no plan yet)

**Description**: 300+ users (180 operators + 45 IT + 75 office staff) undergoing major change. No change management plan, no change management resources identified. Training budget grossly underestimated. HR Director interview pending to assess capacity.

**Impact**:
- Adoption failure (people don't change behavior)
- Resistance and workarounds
- Training inadequate (token training like SAP)
- User frustration and low morale
- Project technically successful but operationally failed

**Likelihood**: 80% (very likely without proper change management)

**Mitigation**:
- Hire change management consultants
- Comprehensive training program ($12-15M)
- Communication plan (address SAP trauma)
- Champion network (Maria, others)
- Executive sponsorship visible (Michael floor shift)

**Owner**: HR Director + Michael  
**Mitigation Cost**: $12-15M training + change management consultants  
**First Identified**: Interview 1 (Michael), Interviews 6-8 (scale of need)

---

### RISK-011: Vendor Lock-In Risk
**Score**: 15/25 (HIGH)  
**Category**: Strategic  
**Status**: STABLE

**Description**: Moving to Azure creates vendor lock-in. Difficult/expensive to migrate away if needed. Azure-specific services create dependencies. Pricing can change (typically increases over time). Exit strategy needed but not designed.

**Impact**:
- Limited negotiating power with Microsoft
- Price increases over time erode savings
- Difficult to switch vendors if needed
- Architecture decisions constrain future options

**Likelihood**: 60% (price increases likely over 5+ years)

**Mitigation**:
- Design for portability where possible
- Avoid Azure-specific services where practical
- Volume licensing negotiation
- Cloud cost monitoring and optimization
- Exit strategy documented

**Owner**: Sarah + Jennifer  
**Mitigation Cost**: $0 (design consideration)  
**First Identified**: Interview 2 (Sarah), Interview 4 (Kevin via Robert)

---

### RISK-013: Compliance Scope Creep
**Score**: 17/25 (HIGH)  
**Category**: Compliance  
**Status**: STABLE

**Description**: Current compliance: SOC 2, FDA (21 CFR Part 11), ISO 9001, CMMC (Level 2 pending). Cloud may trigger additional compliance requirements. Each new requirement adds 3-12 months timeline and $200-500K cost.

**Impact**:
- Timeline delays (3-12 months per new requirement)
- Cost increases ($200-500K per requirement)
- Regulatory audit failures
- Customer contract violations
- Loss of key customers (aerospace, medical device)

**Likelihood**: 50% (some scope creep likely)

**Mitigation**:
- Compliance assessment upfront
- Gap analysis for cloud environment
- Engage customers early (understand their requirements)
- Budget contingency for compliance work

**Owner**: David + Patricia  
**Mitigation Cost**: $500K-1M contingency  
**First Identified**: Interview 5 (David), Interview 7 (Patricia)

---

### RISK-014: Skills Gap in IT Team
**Score**: 18/25 (HIGH)  
**Category**: Capacity  
**Status**: STABLE

**Description**: IT team knows current on-premise systems but has zero Azure/cloud experience. Need 3-6 months training for entire team (45 people). Training while maintaining BAU is difficult. Support team specifically has no cloud skills and needs training.

**Impact**:
- Extended learning curve (mistakes during migration)
- Over-reliance on contractors (knowledge doesn't transfer)
- Team frustration (doing work they're not trained for)
- Quality issues during migration
- Continued dependence on contractors post-migration

**Likelihood**: 80% (certain to have skills gap)

**Mitigation**:
- Comprehensive Azure training program (3-6 months)
- Hands-on labs and sandbox environment
- Contractors work alongside employees (knowledge transfer)
- Certifications and career development
- Realistic timeline allows for training

**Owner**: Sarah + Tom  
**Mitigation Cost**: $500K training + certification costs  
**First Identified**: Interview 2 (Sarah), Interview 9 (Tom)

---

### RISK-015: Third-Party Integration Breakage
**Score**: 16/25 (HIGH)  
**Category**: Technical  
**Status**: STABLE

**Description**: Current systems integrate with customer portals, vendor systems, shipping systems, banking systems, etc. Cloud migration may break integrations. Third parties may not support cloud integration or require costly reconfiguration.

**Impact**:
- Business process disruption (can't get orders, can't ship, can't pay)
- Manual workarounds (productivity loss)
- Customer dissatisfaction
- Vendor relationship strain
- Extended timeline while fixing integrations

**Likelihood**: 70% (at least some integrations will break)

**Mitigation**:
- Integration inventory and testing upfront
- Engage third parties early (understand their requirements)
- API strategy for cloud integrations
- Fallback/rollback for critical integrations
- Parallel running to validate integrations

**Owner**: Sarah + Application Developers  
**Mitigation Cost**: Included in project scope  
**First Identified**: Interview 2 (Sarah)

---

### RISK-019: Board Impatience and Premature Go-Live
**Score**: 18/25 (HIGH)  
**Category**: Organizational  
**Status**: WORSENING

**Description**: Board expects 18-month results. PE firm pressure for ROI. If timeline extends to 36-60 months, board may lose patience and force premature go-live. Rushing leads to SAP 2.0 scenario (3 weeks chaos, rollback).

**Impact**:
- Premature go-live before ready (repeat SAP)
- Production disruption and chaos
- Rollback after wasting time and money
- Further erosion of trust
- Board loses confidence, may cancel project entirely

**Likelihood**: 60% (likely as timeline reality becomes clear)

**Mitigation**:
- Reset board expectations immediately (within 7 days)
- Show mathematical proof of timeline (Sunday windows)
- Phase gate approach with clear criteria
- Demonstrate progress at each gate
- External validation of timeline realism

**Owner**: Michael + Jennifer + Board  
**Mitigation Cost**: $0 (communication and management)  
**First Identified**: Interview 3 (Jennifer), Interview 4 (Robert)

---

### RISK-021: Key Person Dependency
**Score**: 17/25 (HIGH)  
**Category**: Capacity  
**Status**: STABLE

**Description**: Critical people: Sarah (IT Director - knows everything), Kevin (Infrastructure Lead - on fire all the time), Steve (only support person with manufacturing background), Maria (MES Supervisor - operator champion). Loss of any one person could derail project. No succession plans.

**Impact**:
- Project delay or failure if key person leaves
- Knowledge loss (documented nowhere else)
- Team morale impact (others feel burden)
- Scramble to replace or redistribute workload

**Likelihood**: 40% (one person leaves during 3-5 year project)

**Mitigation**:
- Retention bonuses for critical people ($500K total)
- Knowledge transfer and documentation
- Backup/succession planning
- Reduce workload to prevent burnout
- Career development to retain talent

**Owner**: Sarah + HR Director  
**Mitigation Cost**: $500K retention bonuses  
**First Identified**: Interview 2 (Sarah), Interview 4 (Robert), Interview 9 (Tom re: Steve)

---

### RISK-022: Cybersecurity Incident During Migration
**Score**: 19/25 (HIGH)  
**Category**: Technical  
**Status**: WORSENING

**Description**: During migration, security posture weakened (patches delayed, team distracted, misconfigurations). Attackers target companies during migrations (know defenses are down). Ransomware attack during migration could be catastrophic. Support team notes security incidents will increase during migration.

**Impact**:
- Ransomware shuts down operations (days/weeks)
- Data breach (customer data, IP, financial)
- Ransom payment ($500K-5M typical)
- Regulatory penalties and lawsuits
- Reputation damage and customer loss
- Project delay of 3-6 months

**Likelihood**: 30% (lower than other risks but high impact)

**Mitigation**:
- Security architecture review before migration
- Continuous security monitoring during migration
- Dedicated security resources (don't spread David's team thin)
- Incident response plan tested and ready
- Cyber insurance updated for cloud environment
- Clear escalation paths for security incidents

**Owner**: David + Sarah  
**Mitigation Cost**: Included in contractor budget  
**First Identified**: Interview 5 (David), Interview 9 (Tom - incidents increase)

---

### RISK-035: Safety Incidents During Transition
**Score**: 15/25 (HIGH)  
**Category**: Operational  
**Status**: STABLE (new risk)

**Description**: During SAP, operator confusion led to wrong job setups (worker safety hazard) and missed quality checks (customer safety - aerospace/medical parts). New MES interface changes could cause similar operator confusion at 2 AM when tired. Safety incidents have downstream liability implications.

**Impact**:
- Worker injury (operator sets up job wrong)
- Customer safety incidents (quality check missed → defective part → product failure)
- OSHA violations and penalties
- Workers' compensation claims
- Liability lawsuits (especially if customer safety)
- Reputation damage with customers
- Maria/Robert will halt migration if safety compromised

**Likelihood**: 40% (lower with proper mitigation but possible)

**Mitigation**:
- Patricia has explicit veto power on safety/quality systems
- Extended testing for safety-critical functions
- Operator involvement in UAT (usability under pressure at 3 AM)
- Clear error messages and confirmations for critical actions
- Rollback capability if safety incidents occur
- Safety validation as part of GMP validation

**Owner**: Maria + Patricia + Robert  
**Mitigation Cost**: Included in validation budget  
**First Identified**: Interview 8 (Maria)

---

### RISK-036: Sunday Window Capacity Constraint
**Score**: 15/25 (HIGH)  
**Category**: Timeline  
**Status**: STABLE (physical constraint)

**Description**: Only 12 Sunday windows per year (4 hours each = 48 hours/year total) for ALL IT changes. Shared with mechanical and electrical maintenance (not exclusive to IT). Sequential dependencies (ERP → warehouse → MES) prevent parallelization. This single constraint proves 3-5 year minimum timeline independent of all other factors.

**Impact**:
- Multi-year timeline (3-5 years minimum) regardless of other factors
- Cannot compress schedule without violating maintenance windows
- Competition for Sunday windows with other maintenance
- Extended parallel running costs (systems run in parallel for years)

**Likelihood**: 100% (physical constraint, cannot be overcome)

**Mitigation**:
- Accept 3-5 year timeline as reality
- Maximize parallel work (most work done during week, cutover on Sunday)
- Use Christmas shutdown for tactical upgrades (additional windows)
- Coordinate with mechanical/electrical teams for window scheduling
- Optimize cutover procedures to minimize window time

**Owner**: Sarah + Facilities + Manufacturing  
**Mitigation Cost**: $0 (reality) but extends timeline  
**First Identified**: Interview 2 (Sarah mentioned), Interview 8 (Maria mathematical proof)

---

### RISK-037: Training Budget Inadequacy
**Score**: 16/25 (HIGH)  
**Category**: Financial  
**Status**: CRITICAL (massive gap)

**Description**: Current budget likely has nominal training ($5K/person = $900K for 180 operators). Maria estimates $50K/person for four-phase training ($9M for MES operators alone). Total training across all roles (IT, supervisors, support, quality) likely $12-15M. This is 40-65% of total project budget and was grossly underestimated.

**Impact**:
- Inadequate training = adoption failure
- Token training (like SAP) leads to chaos
- Operators unprepared for new systems
- Support team unable to troubleshoot
- Quality issues from improper usage
- Safety incidents from confusion
- Project technically successful but operationally failed

**Likelihood**: 100% (certain if not addressed)

**Mitigation**:
- Approve $12-15M training investment immediately
- Four-phase training approach (Maria's framework):
  - Phase 1: 2 weeks classroom
  - Phase 2: 1-2 weeks hands-on practice
  - Phase 3: 3-6 months pilot program
  - Phase 4: 3-4 months gradual rollout + 6 months support
- Differentiated training for capability range (1/3 comfortable, 1/3 okay, 1/3 struggle)
- Manufacturing-experienced trainers (not IT reading scripts)
- HR Director to design training program

**Owner**: Jennifer + HR Director + Maria  
**Mitigation Cost**: $12-15M (largest single cost item)  
**First Identified**: Interview 6 (Jimmy real training), Interview 8 (Maria quantified)

---

### RISK-040: Help Desk Model Failure for Floor Systems
**Score**: 18/25 (HIGH)  
**Category**: Operational  
**Status**: STABLE (new risk)

**Description**: Current help desk model works for BAU but breaks down during major changes. Remote support insufficient for MES transition - operators at 2 AM can't wait 30-60 minutes when production is down. Floor workers need immediate help on the floor, not tickets and callbacks.

**Impact**:
- Operator frustration when help is too slow
- Production downtime while waiting for support
- Workarounds and shadow processes (operators fix it themselves incorrectly)
- Escalations to supervisors and executives (Robert gets called)
- Adoption resistance (system seen as unsupported)
- Quality and safety issues from operators improvising

**Likelihood**: 90% (very likely if help desk model used)

**Mitigation**:
- Design floor-level support model (not help desk)
- Support staff ON THE FLOOR, all three shifts, 6-12 months
- Manufacturing background required (understand workflows)
- Embedded with operators (walking floor, seeing issues real-time)
- Immediate response (not ticket queue)
- Cost: $260K for 6 months support (2 people × $120K + overtime)

**Owner**: Tom + Sarah + Maria  
**Mitigation Cost**: $260K-520K depending on duration  
**First Identified**: Interview 4 (Robert floor needs), Interview 9 (Tom model failure)

---

### RISK-041: Support Contractor Budget Inadequacy
**Score**: 16/25 (HIGH)  
**Category**: Financial  
**Status**: CRITICAL (not budgeted)

**Description**: Support needs 6-9 contractors for migration (2-3 backfill + 4-6 migration support). Cost $2-3M over migration period. This is separate from the 10-15 contractors Sarah mentioned for broader IT work. Support contractor costs not in anyone's budget.

**Impact**:
- Support capacity crisis (cannot scale without contractors)
- Support team burnout (trying to do everything with current staff)
- BAU work suffers (production support inadequate)
- Migration work suffers (can't handle questions/issues)
- Attrition accelerates (people quit due to overload)

**Likelihood**: 100% (certain need)

**Mitigation**:
- Budget approval for $2-3M support contractors
- Backfill contractors: 2-3 people × $75/hour × 40 hours/week × 52 weeks = $300-450K/year
- Migration support: 4-6 people × $100/hour × 40 hours/week × 18 months = $1.2-1.8M
- Add 30-50% for 24/7 coverage premiums during critical periods
- Spread costs over multiple years in budget

**Owner**: Jennifer + Sarah + Tom  
**Mitigation Cost**: $2-3M (conservative estimate)  
**First Identified**: Interview 2 (Sarah IT contractors), Interview 9 (Tom support-specific)

---

### RISK-042: Support Skills Gap for Cloud
**Score**: 15/25 (HIGH)  
**Category**: Capacity  
**Status**: STABLE (new risk)

**Description**: Support team knows current on-premise systems but has zero Azure/cloud experience. Need 3-6 months training for entire support team (10 people) on cloud troubleshooting, Azure-specific issues, new application interfaces. Training while maintaining BAU workload and brutal on-call rotation is unrealistic.

**Impact**:
- Extended learning curve (more tickets unresolved)
- Poor support quality during migration
- Operator frustration ("help desk doesn't know the system")
- Over-reliance on contractors (knowledge doesn't transfer)
- Longer resolution times (4-6 hours instead of 1-2 hours)

**Likelihood**: 80% (certain skills gap)

**Mitigation**:
- Azure training for entire support team (3-6 months)
- Hands-on labs with cloud systems before migration
- Contractors work alongside support team (knowledge transfer)
- Documentation and knowledge base built during migration
- Realistic timeline allows for proper training

**Owner**: Tom + Sarah  
**Mitigation Cost**: Included in $500K IT training budget  
**First Identified**: Interview 9 (Tom)

---

### RISK-052: Support Staff Hiring Timeline Constraint
**Score**: 17/25 (HIGH)  
**Category**: Capacity  
**Status**: WORSENING

**Description**: Takes 12-18 months to hire 4-6 support staff with manufacturing background. Manufacturing IT talent is rare (most IT contractors specialize in banks, healthcare). 20-30% decline rate on offers. 3-4 months to productivity for new hires. Cannot start migration without adequate support staffing, but hiring takes over a year. This creates a critical path constraint on project start date.

**Timeline Breakdown**:
- Months 1-3: Sourcing and screening (manufacturing experience rare)
- Months 4-6: Interviewing and offers (20-30% decline rate)
- Months 7-9: Onboarding first hires (3-4 months to productivity)
- Months 10-12: Onboarding later hires
- Months 15-18: All 4-6 people fully productive

**Impact**:
- Cannot start migration for 12-18 months (support prerequisite)
- Timeline extends by over a year from decision
- Contractor costs increase (need contractors during hiring period)
- Risk of inadequate support if rushing hiring
- Floor trust issues if support inadequate

**Likelihood**: 95% (hiring process is what it is)

**Root Cause**:
- Manufacturing IT talent pool is small
- Support requires both IT AND manufacturing knowledge
- Current 20-30% offer decline rate
- 3-4 month ramp-up time for manufacturing context

**Mitigation**:
- Start hiring IMMEDIATELY if project approved (don't wait for Phase 1)
- Use contractors during 12-18 month hiring period ($300-450K)
- Partner with manufacturing-focused recruiting firms (TEKsystems, Insight Global)
- Offer competitive compensation for scarce talent
- Realistic expectations on timeline impact

**Owner**: Linda + Tom + Recruiting  
**Mitigation Cost**: $60-110K recruiting fees + $300-450K contractors during hiring  
**First Identified**: Interview 11 (Linda Park Follow-up)

---

### RISK-053: Union Resistance to Technology Changes
**Score**: 16/25 (HIGH)  
**Category**: Organizational  
**Status**: STABLE (new risk)

**Description**: Floor operators are unionized (UAW Local 428). Technology changes that affect work rules, workflows, or job security require union negotiation. Poor union relations could result in passive resistance (work-to-rule, grievances) or active resistance (work slowdowns, potential strikes). Manufacturing cannot afford work stoppages. Union partnership approach is essential but takes 3-6 months for engagement and MOU negotiation.

**Union Concerns to Address**:
- Job security (no layoffs due to technology)
- Training adequacy (80-100 hours on paid time)
- Support availability (24/7 during transition)
- Work rules (negotiate changes collaboratively, not mandate)
- Gradual rollout (parallel running, not force-switch)

**Impact**:
- Work slowdowns could reduce productivity 20-40%
- Grievances could halt changes mid-implementation
- Union contract violation could trigger work stoppage
- Loss of union trust makes future changes impossible
- Operators refuse to use new systems (passive resistance)

**Likelihood**: 60% (moderate-high if not addressed proactively)

**Root Cause**:
- Technology changes affect union contract work rules
- History of top-down mandates without consultation
- Job security concerns with automation
- Lack of early union engagement

**Mitigation**:
- **Phase 1: Early Engagement** (before public announcements)
  - Meet with Local 428 leadership
  - Explain what's being considered (not decided)
  - Ask for input and concerns
- **Phase 2: Collaborative Planning**
  - Include union rep in planning discussions
  - Address concerns proactively
  - Negotiate contractual implications
  - Document in Memorandum of Understanding (MOU)
- **Phase 3: Member Communication**
  - Joint town halls (management + union)
  - Transparent about timeline, training, support
  - Regular updates through union channels
- **Key commitments**:
  - No layoffs due to technology change
  - Training on paid time (80-100 hours)
  - Gradual rollout with parallel running
  - Partnership approach, not mandates

**Owner**: Michael + Jennifer + Union Relations + Linda  
**Mitigation Cost**: Time and management attention (3-6 months engagement)  
**First Identified**: Interview 11 (Linda Park Follow-up)

---

### RISK-054: Contractor Sourcing Lead Time
**Score**: 15/25 (HIGH)  
**Category**: Capacity  
**Status**: STABLE (new risk)

**Description**: Manufacturing-experienced IT contractors require 2-3 month lead time to source and onboard. Good contractors are booked 3-6 months out. Most IT contractors specialize in banks, healthcare, retail - not manufacturing. The pool of contractors who understand manufacturing workflows, constraints, and culture is small. Cannot "just hire contractors" when project starts - must plan 3-6 months ahead.

**Contractor Requirements**:
- IT infrastructure specialists with manufacturing experience
- Application developers who understand MES/ERP
- Database specialists familiar with manufacturing data models
- Network architects with manufacturing floor experience
- Support staff with manufacturing background

**Impact**:
- 2-3 month delay in project start if not planned ahead
- Higher costs (premium for manufacturing experience: $150-250/hour)
- Settling for less qualified contractors (lack of manufacturing context)
- Onboarding friction (learning manufacturing domain during project)
- Timeline delays while waiting for contractor availability

**Likelihood**: 70% (likely to encounter delays)

**Root Cause**:
- Small pool of manufacturing IT contractors
- High demand for scarce talent (booked months ahead)
- Sourcing through general agencies yields wrong skill mix
- Manufacturing domain knowledge not easy to acquire quickly

**Mitigation**:
- Start contractor sourcing IMMEDIATELY if project proceeds
- Use manufacturing-focused firms (TEKsystems manufacturing practice, Insight Global, ISA)
- Build relationships with contractors during planning phase
- Book contractors 3-6 months ahead of need
- Budget for premium rates ($150-250/hour vs. $100-150/hour general IT)
- Consider hybrid model: general IT contractors + manufacturing SME consultants

**Owner**: Sarah + Alex + Linda + Procurement  
**Mitigation Cost**: $5-7M total (IT contractors $3-4M + Support contractors $2-3M)  
**First Identified**: Interview 11 (Linda Park Follow-up)

---

## MODERATE RISKS (Score 10-14) - Monitor and Manage

### RISK-016: Scope Creep During Migration
**Score**: 14/25 (MODERATE)  
**Category**: Project Management  
**Status**: STABLE

**Description**: During migration, stakeholders will request enhancements ("while we're at it..."). Scope creep adds timeline and cost. Without strong change control, project balloons beyond original scope.

**Impact**:
- Timeline delays (3-6 months)
- Cost increases (20-30%)
- Team frustration and scope confusion
- Original objectives diluted

**Likelihood**: 60% (scope creep common in long projects)

**Mitigation**:
- Formal change control process
- Phase 2 for enhancements (not during migration)
- Strong project governance
- Michael and Jennifer must enforce scope discipline

**Owner**: Project Manager + Michael  
**Mitigation Cost**: $0 (discipline)  
**First Identified**: General project management risk

---

### RISK-017: User Acceptance Testing Inadequacy
**Score**: 13/25 (MODERATE)  
**Category**: Quality  
**Status**: STABLE

**Description**: UAT typically surface-level (functional testing only). Need operators involved in UAT (not just IT). Need testing under pressure at 2 AM (not just business hours). Inadequate UAT means issues discovered after go-live.

**Impact**:
- Issues discovered post-go-live (when costly to fix)
- Operator frustration (system doesn't work for real workflows)
- Rollback or extended parallel running
- Additional costs to fix issues

**Likelihood**: 50% (if UAT not rigorous)

**Mitigation**:
- Operators involved in UAT (Maria's requirement)
- Testing under realistic conditions (night shift, production pressure)
- Test scripts based on real workflows (not just happy path)
- Adequate UAT time in schedule (not compressed)

**Owner**: Maria + Sarah + Patricia  
**Mitigation Cost**: Included in project timeline  
**First Identified**: Interview 8 (Maria - operators must be involved)

---

### RISK-018: Communication Breakdown Between IT and Operations
**Score**: 14/25 (MODERATE)  
**Category**: Organizational  
**Status**: IMPROVING (if Michael does floor shift)

**Description**: IT and Operations speak different languages. IT focuses on technical success, Operations on production continuity. Without strong communication, IT makes decisions that don't work operationally.

**Impact**:
- Technical solutions that don't work operationally
- Operator resistance (feel unheard)
- Rework and delays (fix after the fact)
- Erosion of trust between IT and Operations

**Likelihood**: 50% (if Michael doesn't bridge gap)

**Mitigation**:
- Michael floor shift (understand operations)
- Regular IT-Operations meetings during migration
- Operators on project steering committee
- Maria as bridge between IT and floor
- Robert ensures operational voice is heard

**Owner**: Michael + Robert + Maria  
**Mitigation Cost**: $0 (communication)  
**First Identified**: Interview 4 (Robert), Interview 8 (Maria)

---

### RISK-023: Customization Debt in Cloud
**Score**: 12/25 (MODERATE)  
**Category**: Technical  
**Status**: STABLE

**Description**: Temptation to customize cloud applications to match old workflows. Customizations complicate upgrades and maintenance. "Lift and shift" approach may recreate existing problems in cloud.

**Impact**:
- Upgrade challenges (customizations break)
- Vendor support issues (customizations not supported)
- Higher ongoing maintenance costs
- Miss opportunity to improve workflows

**Likelihood**: 50% (customizations common without discipline)

**Mitigation**:
- Minimize customizations (use standard functionality)
- Business process re-engineering where appropriate
- Configuration over customization
- Document and track all customizations

**Owner**: Sarah + Application Developers  
**Mitigation Cost**: $0 (design discipline)  
**First Identified**: Interview 2 (Sarah)

---

### RISK-024: Cloud Cost Optimization Failure
**Score**: 13/25 (MODERATE)  
**Category**: Financial  
**Status**: STABLE

**Description**: Cloud costs can spiral without active management. Easy to over-provision, forget to shut down resources, incur unexpected data egress charges. Without optimization, cloud may not deliver expected cost savings.

**Impact**:
- Higher than expected ongoing costs
- ROI case weakens or disappears
- Budget overruns in operational phase
- Board dissatisfaction with "savings" that don't materialize

**Likelihood**: 60% (cloud cost overruns common)

**Mitigation**:
- Cloud cost monitoring and optimization tools
- Regular cost reviews (monthly minimum)
- Right-sizing of resources
- Reserved instances where appropriate
- Chargebacks to departments (accountability)

**Owner**: Sarah + Jennifer  
**Mitigation Cost**: Included in Azure costs  
**First Identified**: Interview 2 (Sarah), Interview 4 (Kevin via Robert)

---

### RISK-025: Email and Collaboration Disruption
**Score**: 11/25 (MODERATE)  
**Category**: Operational  
**Status**: STABLE

**Description**: Moving email and collaboration to cloud (Microsoft 365) affects every user daily. If migration goes poorly, productivity suffers across organization. Smaller impact than MES but wider user base (300+ users).

**Impact**:
- Productivity loss (can't access email/files)
- User frustration across organization
- Communication breakdowns
- Negative perception of entire migration

**Likelihood**: 30% (Microsoft 365 migrations well-understood)

**Mitigation**:
- Pilot with IT team first
- Phased rollout by department
- Comprehensive training
- Adequate support during transition
- Rollback plan if major issues

**Owner**: Sarah + Tom  
**Mitigation Cost**: Included in project scope  
**First Identified**: Interview 2 (Sarah)

---

### RISK-026: Document Management System Migration Complexity
**Score**: 12/25 (MODERATE)  
**Category**: Technical  
**Status**: STABLE

**Description**: Current document management likely has 15+ years of documents. Metadata, folder structures, permissions all need migration. Documents may be referenced by other systems (integrations).

**Impact**:
- Documents lost or inaccessible
- Broken links from other systems
- Productivity loss (can't find documents)
- Compliance issues (GMP document retention)

**Likelihood**: 40% (at least some issues likely)

**Mitigation**:
- Document migration strategy and testing
- Parallel running (old and new for 3-6 months)
- Extensive validation of document migration
- GMP documents given extra scrutiny

**Owner**: Sarah + Patricia  
**Mitigation Cost**: Included in project scope  
**First Identified**: Interview 2 (Sarah)

---

### RISK-027: Custom Application Re-Architecture
**Score**: 14/25 (MODERATE)  
**Category**: Technical  
**Status**: STABLE

**Description**: 8 legacy custom applications may not work in cloud without re-architecture. Some may need complete rewrites. Adds significant timeline and cost if not planned upfront.

**Impact**:
- Timeline delays (6-12 months per app if rewrite needed)
- Cost increases ($500K-1M per app for rewrites)
- May need to defer some apps to later phase
- Functionality gaps if apps not migrated

**Likelihood**: 60% (at least 2-3 apps will need major work)

**Mitigation**:
- Application assessment upfront (discovery phase)
- Prioritize apps by business value
- Consider commercial off-the-shelf (COTS) replacements
- Phase approach (critical apps first, others later)

**Owner**: Sarah + Application Developers  
**Mitigation Cost**: $1-3M for rewrites (if needed)  
**First Identified**: Interview 2 (Sarah)

---

### RISK-029: PE Firm Skepticism or Intervention
**Score**: 14/25 (MODERATE)  
**Category**: Financial  
**Status**: UNKNOWN (PE firm position unclear)

**Description**: Private equity firm ownership means capital investment scrutiny. PE firms typically want ROI within 3-5 years. Multi-year migration with uncertain ROI may not align with PE timeline. PE could intervene or cancel project.

**Impact**:
- Project cancellation mid-stream (waste of investment)
- Pressure to cut scope or timeline (leads to failure)
- Budget constraints (can't get full funding needed)
- Management changes if PE loses confidence

**Likelihood**: 40% (depends on PE firm position)

**Mitigation**:
- Engage PE firm early (get buy-in upfront)
- Show clear ROI case (Jennifer's 3X model)
- Phase approach with value delivered at each phase
- Transparent reporting to PE on progress and ROI

**Owner**: Michael + Jennifer + Board  
**Mitigation Cost**: $0 (engagement and management)  
**First Identified**: Interview 3 (Jennifer)

---

### RISK-030: Loss of Detroit Dynamics Contract
**Score**: 13/25 (MODERATE)  
**Category**: Business  
**Status**: STABLE

**Description**: Detroit Dynamics is key customer. During SAP, production disruption almost lost this contract (Robert had to escalate to CEO). If migration disrupts production or quality, could lose contract again.

**Impact**:
- Revenue loss (significant customer)
- Reputation damage in automotive industry
- Downstream effects (other customers see disruption)
- Potential facility closure if revenue loss severe

**Likelihood**: 20% (lower with proper execution but high impact)

**Mitigation**:
- Engage Detroit Dynamics early (customer communication)
- Extra quality scrutiny on Detroit Dynamics parts
- Avoid big bang (phased approach reduces risk)
- Parallel running (fallback if issues)
- Robert monitors closely (escalate quickly if issues)

**Owner**: Robert + Sales/Account Management  
**Mitigation Cost**: $0 (attention and communication)  
**First Identified**: Interview 4 (Robert)

---

### RISK-031: Warehouse Management System Integration
**Score**: 12/25 (MODERATE)  
**Category**: Technical  
**Status**: STABLE

**Description**: WMS integrates with ERP (order fulfillment) and MES (material tracking). If WMS migration breaks integrations, shipping stops. Sequential dependencies (ERP → WMS → MES) add timeline.

**Impact**:
- Can't ship products (revenue impact)
- Manual workarounds (productivity loss)
- Customer order delays
- Inventory accuracy issues

**Likelihood**: 50% (integrations often break)

**Mitigation**:
- Integration testing before cutover
- Parallel running to validate integrations
- Sequential migration (ERP first, then WMS, then MES)
- Rollback plan if integrations fail

**Owner**: Sarah + Operations  
**Mitigation Cost**: Included in project scope  
**First Identified**: Interview 2 (Sarah)

---

### RISK-032: Quality Management System Validation
**Score**: 14/25 (MODERATE)  
**Category**: Compliance  
**Status**: STABLE

**Description**: QMS is GMP-validated system. Migration requires re-validation (3-6 months). QMS must be validated before production can use it. Cannot compress without regulatory violations.

**Impact**:
- Timeline delay if validation not in critical path
- Cannot use new QMS until validated (old system must run)
- Regulatory violations if used without validation
- Customer audit failures

**Likelihood**: 50% (if not planned properly)

**Mitigation**:
- Include QMS validation in critical path (not parallel)
- Patricia leads validation effort
- Risk-based validation approach (focus critical functions)
- Test scripts aligned with GMP requirements

**Owner**: Patricia + Sarah  
**Mitigation Cost**: Included in $1.5-2.5M validation budget  
**First Identified**: Interview 7 (Patricia)

---

### RISK-043: Knowledge Base and Documentation Gap
**Score**: 14/25 (MODERATE)  
**Category**: Operational  
**Status**: STABLE (new risk)

**Description**: Current knowledge base okay for current systems. Need to build from scratch for new systems - troubleshooting guides, FAQs, known issues, workarounds. Documentation must be created BEFORE migration, not after. Operators and support need this to be successful.

**Impact**:
- Support can't help users (no documentation)
- Users frustrated (no self-service)
- Repeat questions (support overwhelmed)
- Training gaps (no reference materials)
- Knowledge loss (tribal knowledge not captured)

**Likelihood**: 60% (documentation often afterthought)

**Mitigation**:
- Dedicated resource for documentation (6-12 months)
- Knowledge base articles written during pilot
- Operators and support review documentation
- Searchable, accessible format
- Updated continuously as issues discovered

**Owner**: Tom + Sarah + Training Team  
**Mitigation Cost**: $100-200K for dedicated documentation resource  
**First Identified**: Interview 9 (Tom)

---

### RISK-044: Vendor Support Model Unknown
**Score**: 13/25 (MODERATE)  
**Category**: Operational  
**Status**: STABLE (new risk)

**Description**: Moving to Azure and cloud applications means new vendors with unknown support models. What are their SLAs? Can we escalate 24/7? What's included in licensing vs. paid support? Need to understand vendor support BEFORE migration, not after.

**Impact**:
- Support gaps during critical issues
- Longer resolution times (waiting on vendor)
- Additional support costs (paid support contracts)
- Finger-pointing between vendors ("not our problem")
- Production impact while vendors troubleshoot

**Likelihood**: 50% (some vendor support issues likely)

**Mitigation**:
- Vendor due diligence before migration
- SLA negotiation and documentation
- 24/7 support contracts where needed
- Escalation procedures defined and tested
- Understand what's included vs. paid support

**Owner**: Sarah + Tom + Procurement  
**Mitigation Cost**: Included in Azure licensing costs  
**First Identified**: Interview 9 (Tom)

---

### RISK-055: Manufacturing Trainer Availability
**Score**: 13/25 (MODERATE)  
**Category**: Organizational  
**Status**: STABLE (new risk)

**Description**: Manufacturing-experienced trainers who can teach software in manufacturing context are specialized and rare. Generic software trainers don't understand manufacturing workflows, safety requirements, or floor culture. Takes 4-6 months lead time to source and onboard qualified trainers. Without manufacturing context, training will be ineffective and operators won't trust the training.

**Trainer Requirements**:
- Understand manufacturing workflows and terminology
- Can relate software to actual floor operations
- Credible to floor operators (not "corporate trainers")
- Available for 6-12 month training delivery period
- Can work with operators across all shifts

**Sourcing Options**:
1. **Manufacturing Training Firms** (ToolingU, MasterControl)
   - Cost: $150-250/hour (premium)
   - Lead time: 3-6 months
   - Pros: Experienced, credible
   - Cons: Expensive, limited availability

2. **Retired Manufacturing Professionals**
   - Cost: $75-150/hour (moderate)
   - Need to recruit through networks
   - Pros: Highly credible, lower cost
   - Cons: May lack training experience

3. **Hybrid Approach** (RECOMMENDED)
   - Software vendor trainers + manufacturing SME
   - Team teaching approach
   - Cost: $200-300/hour combined
   - Lead time: 4-6 months

**Impact**:
- Ineffective training if wrong trainers used
- Operator resistance ("they don't understand our work")
- Lower adoption rates due to poor training quality
- Need to retrain later (doubling training costs)
- Timeline delays waiting for qualified trainers

**Likelihood**: 50% (moderate - can be mitigated with early planning)

**Root Cause**:
- Small pool of manufacturing-experienced trainers
- Most software trainers lack manufacturing context
- 4-6 month lead time to source and vet trainers
- Need credibility with floor operators

**Mitigation**:
- Start trainer sourcing during planning phase (don't wait for Phase 1)
- Use hybrid approach (software vendor + manufacturing SME)
- Recruit retired manufacturing professionals through networks
- Budget for premium rates to secure qualified trainers
- Allow 4-6 months lead time for sourcing
- Vet trainers with floor supervisors for credibility

**Owner**: Linda + HR Training Team + Vendor Management  
**Mitigation Cost**: Included in $12.5-16M training budget  
**First Identified**: Interview 11 (Linda Park Follow-up)

---

## LOW RISKS (Score 1-9) - Monitor

### RISK-045: Network Latency Impact on MES Performance
**Score**: 8/25 (LOW)  
**Category**: Technical  
**Status**: STABLE

**Description**: MES requires <50ms latency. Cloud adds 20-30ms minimum. If network not optimized, latency could impact MES usability and operator productivity.

**Impact**:
- Operator frustration (slow system)
- Productivity loss (waiting for screens)
- Resistance to adoption
- May need to keep MES on-premise if latency unacceptable

**Likelihood**: 20% (likely manageable with proper network)

**Mitigation**:
- Network optimization (prerequisite work)
- ExpressRoute or direct connect to Azure
- Latency testing before MES migration
- Keep MES on-premise if latency unacceptable

**Owner**: Sarah + Network Engineers  
**Mitigation Cost**: Included in infrastructure budget

---

### RISK-046: Data Egress Costs
**Score**: 7/25 (LOW)  
**Category**: Financial  
**Status**: STABLE

**Description**: Transferring data out of Azure incurs charges. Manufacturing generates significant data (MES logs, quality data, production data). Data egress costs could add up over time.

**Impact**:
- Higher than expected operational costs
- Budget overruns
- ROI case weakens

**Likelihood**: 30% (will have some egress costs)

**Mitigation**:
- Understand data flows and egress patterns
- Optimize data architecture to minimize egress
- Monitor costs monthly
- Include in financial model

**Owner**: Sarah + Jennifer  
**Mitigation Cost**: Included in Azure cost estimates

---

### RISK-047: Time Zone Coordination for Global Support
**Score**: 6/25 (LOW)  
**Category**: Operational  
**Status**: STABLE

**Description**: If using global Azure resources or offshore contractors, time zone coordination becomes complex. 24/7 support requires coverage across time zones.

**Impact**:
- Communication delays
- Hand-off issues between shifts
- Cultural/language barriers
- Slower resolution times

**Likelihood**: 20% (if offshore contractors used)

**Mitigation**:
- Prefer local/regional contractors
- Clear handoff procedures if global team
- Overlap hours for communication
- Language skills assessment for contractors

**Owner**: Tom + Sarah  
**Mitigation Cost**: $0 (process design)

---

### RISK-048: Legacy Hardware End-of-Life
**Score**: 8/25 (LOW)  
**Category**: Technical  
**Status**: STABLE

**Description**: Current on-premise hardware aging. If migration timeline extends to 5 years, hardware may fail before migration complete. May need to replace hardware mid-migration.

**Impact**:
- Unplanned hardware replacement costs
- System outages during migration
- Timeline delays if critical hardware fails

**Likelihood**: 30% (some hardware may fail over 5 years)

**Mitigation**:
- Hardware assessment and lifecycle planning
- Replace critical hardware proactively
- Maintain spares for aging equipment
- Accelerate migration of systems on oldest hardware

**Owner**: Sarah + Infrastructure Team  
**Mitigation Cost**: $200-500K contingency for hardware

---

### RISK-049: Holiday Season Blackout Windows
**Score**: 7/25 (LOW)  
**Category**: Timeline  
**Status**: STABLE

**Description**: November/December are blackout period for changes (holiday season busy for manufacturing). Reduces available Sunday windows from 12 to 10 per year. Small additional timeline impact.

**Impact**:
- Fewer migration windows available
- Timeline extends by 2-3 months over project life

**Likelihood**: 100% (certain - holiday blackout is firm)

**Mitigation**:
- Plan around blackout windows
- Use Christmas shutdown if available
- Accept timeline impact
- Don't try to force changes during blackout

**Owner**: Sarah + Manufacturing  
**Mitigation Cost**: $0 (timeline acceptance)

---

### RISK-050: Social Engineering Attacks During Transition
**Score**: 9/25 (LOW)  
**Category**: Security  
**Status**: STABLE

**Description**: Users confused by new systems are vulnerable to phishing and social engineering. Attackers may impersonate support or send fake training materials. Increased risk during migration period.

**Impact**:
- Credentials compromised
- Malware infection
- Data breach
- Ransomware attack

**Likelihood**: 20% (possible but lower priority than other risks)

**Mitigation**:
- Security awareness training during migration
- Clear communication channels (how support will contact you)
- Extra vigilance from security team
- Incident response plan ready

**Owner**: David + Tom  
**Mitigation Cost**: Included in security budget

---

## Risk Mitigation Summary

### By Priority

**IMMEDIATE ACTION REQUIRED (CRITICAL RISKS)**:
1. Timeline reset to 36-48 months minimum (RISK-001)
2. Hire contractors for capacity (RISK-002, RISK-039, RISK-054)
3. Retention strategy for key personnel (RISK-051) - $400-500K
4. MES migration strategy (RISK-008, RISK-033)
5. Validation timeline integration (RISK-012)
6. Union engagement and partnership (RISK-020, RISK-053)
7. Budget revision to $22-31M (RISK-028, RISK-037, RISK-041, RISK-052)
8. SAP acknowledgment and trauma healing (RISK-034)
9. Address support burnout (RISK-038, RISK-052)
10. Floor-level support model (RISK-040)
11. Start support staff hiring immediately (RISK-052)

**URGENT (HIGH RISKS)**:
12. Infrastructure stabilization ($2.5M) (RISK-003)
13. Support contractor budget ($2-3M) (RISK-041, RISK-054)
14. Training budget ($12-15M) (RISK-037, RISK-055)
15. Skills gap training (RISK-014, RISK-042)
16. Board expectations management (RISK-019)
17. Start contractor sourcing (2-3 month lead time) (RISK-054)
18. Union partnership approach (RISK-053)
19. Manufacturing trainer sourcing (4-6 month lead time) (RISK-055)

### Total Mitigation Cost Estimate

**One-Time Costs**:
- IT contractors: $4-6M over 3 years
- Support contractors: $2-3M over 18-36 months
- Training: $12-15M over 12-18 months
- Validation: $1.5-2.5M
- Infrastructure: $2.5M Year 1
- Retention bonuses: $500K
- Documentation: $100-200K
- Contingency: $1.5-3M
**Subtotal**: $24.6-32.7M

**Ongoing Costs**:
- Azure infrastructure: Ramps from $3M to $4M/year
- Hidden costs: $1-2M/year
**Year 1-3**: Higher costs during parallel running

**Total 5-Year Budget**: $30-40M (includes mitigation costs)

---

## Document Control

**Version**: 2.0  
**Last Updated**: 2025-11-05 (After Interview 9)  
**Updated By**: Discovery Team  
**Next Review**: After Interview 10 (IT Manager)  
**Owner**: Project Risk Manager (TBD)

**Change Log**:
- v1.0 (2025-10-28): Initial risk register (25 risks)
- v1.1 (2025-10-30): Added risks 26-30 after Jennifer interview
- v1.2 (2025-11-01): Added risks 31-33 after David interview
- v1.3 (2025-11-02): Updated after Jimmy interview
- v1.4 (2025-11-04): Added risks 34-37 after Patricia/Maria interviews
- v2.0 (2025-11-05): Major update after Tom interview - added 7 new risks (38-44), now 44 total, 10 critical
- v2.1 (2025-11-06): Added 5 new risks (51-55) after Interviews 10-11 (Alex Kumar, Linda Park follow-up), now 55 total, 11 critical

---

**STATUS**: Active risk tracking, 55 risks identified, 11 critical requiring immediate action, comprehensive mitigation strategy needed before Phase 1.
