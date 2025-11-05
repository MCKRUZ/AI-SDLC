# Interview 5: Kevin Martinez - Infrastructure Manager

**Date**: Thursday, November 7, 2024  
**Duration**: 78 minutes  
**Interviewer**: Discovery Facilitator  
**Interviewee**: Kevin Martinez, Infrastructure Manager (15 years tenure)  
**Location**: Conference room, 2:00 PM

---

## Executive Summary

Kevin Martinez revealed critical infrastructure constraints that fundamentally challenge the feasibility of an 18-month Azure migration timeline. His detailed analysis shows:

- **$4.2M infrastructure debt** (requested, received only $800K) that cannot be deferred
- **Hardware crisis**: 247 servers averaging 8.4 years old (3+ years past industry standard), exponential failure rates
- **Network capacity bottleneck**: Current circuits require 6-7 months just for data transfer
- **$1.4-2M Year 1 staffing gap**: Team lacks Azure expertise, needs contractors and new hires
- **$1-2M annual hidden costs**: Data egress, Azure services tax, DR, management tools
- **Parallel running costs**: $800K-1.2M for 8-10 critical systems
- **Cloud cost reality**: May not save money vs. on-prem for 3+ years

**Critical Finding**: Infrastructure investment of $2.5M minimum required in Year 1 even WITH Azure migration. Cannot defer all $4.2M and maintain stability during 12-24 month migration.

**Confidence Assessment**: Kevin rates success at 3/10 on current path, 8/10 if four-way alignment happens (Michael-Jennifer-Robert-Sarah).

---

## Part 1: Infrastructure Reality Check

### Current State
- **247 physical servers** across 3 data centers
- **Average age: 8.4 years** (industry standard: 5 years before exponential failure)
- **Q4 hardware failures**: 14 (up from 8 in Q3, 4 in Q2) - exponential trend
- **Mitigation**: Cannibalizing parts from older servers, begging vendors for EOL hardware

### Storage Crisis
- **Primary SAN**: 2014 vintage
- **Secondary SAN**: 2016 vintage  
- **Current capacity**: 87% (will hit 90% by Q2 2025)
- **Impact at 90%**: Cannot backup properly, cannot failover, crisis mode

### The $4.2M Infrastructure Request (FY2024)

**Breakdown**:
- $1.8M - SAN replacement/expansion (need 3-5 year runway, not 6 months)
- $1.2M - Server refresh (critical systems: MES, ERP, database)
- $700K - Network infrastructure (switches, firewalls, load balancers 10+ years old)
- $300K - Backup infrastructure (one failure from losing DR capability)
- $200K - Monitoring/security tools (blind to modern threats)

**Approved**: $800K (only covers maintenance contracts and emergency replacements)

**Jennifer's Rationale for Cut**: "Can't justify capital on infrastructure we're moving to cloud anyway" (18 months ago under previous CTO)

**Result**: Infrastructure aged another 18 months without investment, problem compounded.

### Five Whys: Why Backups Are Questionable

1. **Why are backups questionable?** → Backup infrastructure is as old as primary (SAN from 2014/2016)
2. **Why hasn't SAN been upgraded?** → No budget - requested $4.2M, got $800K
3. **Why was request cut?** → CFO said we're "moving to cloud anyway" so can't justify capital
4. **Why did cloud initiative stall?** → No real plan, all hand-waving, no answers to hard questions
5. **Why no real plan?** → Nobody understood that cloud requires infrastructure to run DURING migration

**Root Cause**: Circular dependency - can't get infrastructure investment because "we're going to cloud," can't go to cloud without infrastructure investment.

---

## Part 2: Infrastructure Costs Don't Disappear in Cloud

### Kevin's Comparison: 5-Year Total Cost

**Status Quo (No Cloud)**:
- $4.2M infrastructure refresh (buys 3-5 years)
- $4.5M/year ongoing run costs
- **5-year total: $26.7M**

**Azure Migration (Realistic)**:
- Year 1: $2.5M infrastructure stabilization (minimum viable, cannot defer all $4.2M)
- Year 1-2: $6-8M cloud migration costs (licenses, network, tools, consulting)
- Year 1-2: $4.5M/year on-prem run costs (parallel running both environments)
- Year 3: $3.5M cloud run costs (if efficient)
- Year 4-5: $3M/year cloud run costs (optimized)

**5-year total: $23-25M** (saves $2-4M over 5 years, but Years 1-2 cost MORE)

### Year 1-2 Cost Reality
- $2.5M infrastructure stabilization
- $6-8M migration
- $9M on-prem parallel (2 years × $4.5M)
- **Total Year 1-2: $17.5-19.5M** ($8.75-9.75M per year)

**Key Insight**: Year 1-2 costs are DOUBLE current run rate ($4.5M → $8.75-9.75M), aligning with Jennifer's assessment.

### Why You Can't Defer the Full $4.2M

**Kevin's Analysis**:
> "You STILL need most of that investment during migration. You're running BOTH on-prem and cloud simultaneously for 12-24 months. That means you need on-prem infrastructure stable enough to run while you migrate."

**Minimum Required During Migration** ($2.5M):
- SAN expansion to 3-year runway (can't migrate with 6 months runway left) - $1.2M
- Critical server refresh (MES, ERP, DB servers can't fail mid-migration) - $800K
- Network capacity upgrades (see Part 5) - $350K
- Monitoring for hybrid environment - $150K

**Can Defer** ($1.7M):
- Non-critical server refresh (can migrate those directly to Azure)
- Some backup infrastructure (Azure Backup can replace some)
- Some security tools (Azure Security Center provides baseline)

---

## Part 3: Robert's Parallel Running Requirement - Infrastructure Impact

### MES System Parallel Running (90+ days)

**Compute**:
- Old MES: 8 servers (app + DB + integration)
- New MES: Equivalent Azure resources
- Paying for BOTH simultaneously

**Storage**:
- Both systems writing production data
- Data synchronization old ↔ new (complex, error-prone)
- Rollback capability if new system fails

**Network**:
- Production floor devices talking to BOTH systems
- Network segregation (test traffic cannot hit production MES)
- Bandwidth for continuous data sync

**People**:
- 24/5 monitoring of BOTH systems
- Daily data reconciliation
- Standby team for failback if issues

**Cost Estimate (MES alone)**: $150-200K for 90-day parallel window

### Scaling to All Critical Systems

**Systems Requiring Parallel Running** (8-10 total):
- MES (manufacturing execution)
- ERP (enterprise resource planning)
- Quality Management System
- Inventory Management
- Plus 4-6 others Robert considers "critical"

**Parallel Window**: 30-90 days depending on system criticality

**Total Parallel Running Infrastructure Cost**: $800K-1.2M

**Critical Gap**: Michael has not budgeted for parallel running infrastructure (per Kevin's knowledge).

---

## Part 4: The Christmas Cutover Myth

### Factory Shutdown Window
- **Dates**: December 23 → January 2 (10 calendar days)
- **Reality**: 6-7 usable work days
  - Dec 23-24: Shutdown procedures, backups, prep
  - Dec 25: Christmas (nobody available)
  - Dec 26-31: Work window (6 days, skeleton crew)
  - Jan 1: New Year (nobody available)
  - Jan 2: Startup procedures, testing before Jan 3 production

### Last Christmas: ERP Database Upgrade

**Planned**: 48 hours  
**Actual**: 92 hours

**Why?**: Discovered incompatible stored procedures not caught in testing (test environment isn't exact production copy - can't afford $600-800K to duplicate at scale).

**Result**: Barely made January 3rd production startup.

### Why Christmas Is HIGH RISK for Major Changes

1. **Limited staff**: Skeleton crew, not 24/7 coverage
2. **Vendor unavailability**: Closed Dec 24 → Jan 2
3. **Contractor unavailability**: On vacation
4. **Rollback risk**: If can't start production Jan 3, lose $240K/day
5. **Robert's constraint**: Max 4 hours unplanned downtime acceptable

**Kevin's Assessment**: 
> "Christmas window is great for tactical upgrades, not strategic transformation. It's POSSIBLE for one system, maybe two. But not for 'Azure migration' - that's dozens of systems, complex interdependencies, massive data moves."

**Appropriate Use**: Single-system upgrades you're confident in, not experiments or complex migrations.

---

## Part 5: Network Capacity Crisis

### Current Network Infrastructure

**Three Locations**:
- Main plant (Elkhart) - production
- Corporate office (South Bend, 15 miles) - Michael/Jennifer
- DR colo (Chicago, 90 miles) - disaster recovery

**Current Circuits**:
- Elkhart ↔ South Bend: 100 Mbps fiber (2015)
- Elkhart ↔ Chicago DR: 50 Mbps fiber (2013)
- Elkhart → Internet: 200 Mbps (2018)

**Adequate For**: Email, file transfers, remote desktop, web apps

**NOT Adequate For**:
- Migrating 50+ TB to Azure
- Hybrid apps (on-prem users hitting Azure)
- Modern video conferencing (Zoom killing bandwidth)
- Security monitoring (modern tools are "chatty")

### Data Transfer Math

**Migration Volume**: 50 TB = 50,000 GB

**At 200 Mbps Internet Circuit**:
- Real-world throughput: ~23 Mbps = 2.9 MB/s
- 50,000 GB ÷ 2.9 MB/s = 4,780 hours = **199 days = 6-7 months**

**Reality**: Cannot saturate circuit 24/7 (business needs it), so actual timeline: **6-8 months for initial transfer** + ongoing replication.

### Solutions

**Option A: Upgrade Internet Circuit**
- 1 Gbps circuit
- $60K upfront + $4K/month increase ($48K/year)
- Reduces transfer to ~30-40 days

**Option B: Azure Data Box**
- Microsoft ships physical storage device
- Copy data locally, ship back to Microsoft who uploads to Azure
- $3K per box, need ~3 boxes = $9K total
- Timeline: 2-3 weeks

**Kevin's Recommendation**: Data Box for initial bulk transfer, upgraded circuit for ongoing hybrid operations.

### Five Whys: Why Michael Doesn't Grasp Network Constraint

1. **Why doesn't Michael grasp the constraint?** → He's from software background
2. **Why does software background matter?** → Thinks about applications/code, infrastructure is invisible
3. **Why is infrastructure invisible?** → Network is like plumbing - nobody thinks about it until it breaks
4. **Why was Michael hired from software?** → Board wanted someone to "modernize" and "innovate"
5. **Why aren't infrastructure people seen as innovators?** → Always talking about risk and cost, sounds negative

**Root Cause**: Infrastructure leaders perceived as blockers ("no guys") rather than enablers, so not given leadership roles. Results in leadership blind spots on infrastructure constraints.

---

## Part 6: The Expertise Gap

### Current Team Structure (9 people)
- Kevin (Infrastructure Manager)
- 2 senior systems engineers (Mark, Priya - 8+ years tenure, solid)
- 3 mid-level engineers (decent, not deep experts)
- 2 junior engineers (entry-level, learning)
- 1 contractor DBA (3 years, effectively staff)

**Current Workload**: 247 servers, 3 data centers, network, storage, backup, DR, security infrastructure - already underwater.

### Skill Gap Analysis

**Current Team Strengths**:
- Windows Server: Strong (80% of environment)
- VMware: Strong (heavily virtualized)
- SQL Server: Strong (excellent DBA contractor)

**Current Team Weaknesses**:
- Linux: Weak (only 15% of servers, never prioritized)
- Azure: VERY weak (only Mark has training, never at scale)
- DevOps/IaC: Basically zero (manage everything through GUIs)
- Cloud networking: Weak (SDN, hybrid connectivity unfamiliar)
- Cloud security: Traditional only (firewalls, AV), weak on modern

**Required for Azure Migration**:
- Azure architecture (PaaS vs IaaS, cost optimization)
- Azure networking (VNets, ExpressRoute, NSGs, Azure Firewall)
- Identity (Azure AD, hybrid identity, conditional access)
- Infrastructure as Code (ARM templates, Terraform, Bicep)
- DevOps (CI/CD pipelines for infrastructure)
- Cloud security (Zero Trust, Azure Security Center, Sentinel)
- Cost management (entire discipline)

### Can You Train Existing Team?

**Kevin's Assessment**: "Some, but not all, not fast enough."

**Constraints**:
- Team already firefighting daily hardware failures (no time for deep training)
- Some don't WANT to reskill (Priya, 55, retiring in 5 years - excellent at current job, not interested in cloud)
- Training takes months to years for deep expertise
- Cloud is constantly changing (new services monthly)

### Staffing Requirements

**Contractors (12-18 months)**:
- 2 senior cloud architects @ $200/hour × 2000 hours = $800K-1.2M
- 1 Azure security specialist (6-12 months) = $250-500K

**FTE Hires (Permanent)**:
- 2 cloud engineers @ $120K + benefits ($150K fully loaded) = $300K/year ongoing

**Training**:
- Azure certifications, workshops for existing team = $50K

**Total**:
- Year 1: $1.4-2M (contractors + FTEs + training)
- Year 2+: $300K/year ongoing (FTE hires)

**Critical Gap**: Kevin has no visibility into Michael's budget. Has sent estimates to Sarah, but hasn't seen project budget yet.

---

## Part 7: The "Free" Cloud Licenses Trap

### Azure Hybrid Benefit (Sounds Great)

**Promise**: Reuse existing Windows Server and SQL Server licenses in Azure, save ~40% on compute.

**Reality**:
- Only works if you have active **Software Assurance** (ongoing maintenance)
- Contoso let SA lapse on **60% of servers** (budget cuts 3 years ago)
- Must buy NEW licenses FIRST (Windows Server Datacenter + SQL Server Enterprise)
- **Cost to catch up**: ~$800K
- THEN can migrate to get the benefit

### Microsoft EA (Enterprise Agreement) Incentives

**Promise**: "Free" Azure credits if you commit to 3-year spend.

**Reality**:
- Locked into spending $X/year for 3 years
- Overspend one year? Great, credits roll over
- UNDER-spend? Still pay (use it or lose it)
- Most orgs overprovision initially (insurance), waste credits

### Real Cost Comparison

**Current State (On-Prem)**:
- $4.5M annual run costs (hardware, power, cooling, maintenance, staff)
- $500K annual licensing (Microsoft, VMware, etc.)
- **Total: $5M/year**

**Azure "Optimistic" Scenario**:
- $3M/year consumption (VMs, storage, network, PaaS)
- $800K one-time license catch-up
- $300K/year new cloud staff
- $200K/year cloud management tools
- **Year 1: $4.3M, then $3.5M/year ongoing**

**Azure "Realistic" Scenario**:
- $4.5M/year consumption (overprovisioning, inefficiency, learning curve)
- $800K one-time license catch-up
- $300K/year cloud staff
- $200K/year tools
- **Year 1: $5.8M, then $5M/year ongoing**

**Key Finding**: Realistic Azure scenario costs THE SAME as on-prem ($5M/year), and we've spent $10-15M on migration with no savings.

### What Would It Take to Hit Optimistic Scenario?

1. **Rigorous architecture** - Right-size everything, use PaaS where possible, reserved instances
2. **Cost management discipline** - Weekly cost reviews, auto-shutdown non-prod, strict tagging/chargeback
3. **Continuous optimization** - Don't set-and-forget, constantly review and adjust
4. **Expertise** - People who know Azure cost optimization, not just "how to build"

**Kevin's Confidence**: 50/50

**Why?**: "We're good at capital budgeting (Jennifer watches every dollar). We're TERRIBLE at operational discipline. We build, accumulate, never clean up. If we bring that culture to cloud, we'll have 600 underutilized VMs running 24/7 costing $300/month each because 'we might need it someday.'"

---

## Part 8: Hidden Costs Nobody Talks About

### Data Egress ($200-500K/year)
- **Moving data OUT of Azure costs money** (ingress is free)
- If we keep on-prem backup/DR (likely), paying to replicate out of Azure daily
- Large file downloads (reports, CAD drawings) cost per GB
- Most orgs don't realize until $50K surprise bill

### Azure Services "Tax" ($150K/year)
- Load balancers: $20 each/month
- Public IP addresses: $4 each/month
- VPN Gateways: $140/month each
- Azure Firewall: $1.25/hour = $900/month
- **Log Analytics: $2.30/GB ingested**
  - Generate ~100 GB/month = $230/month = **$2.76K/year just for logs**

These "little charges" accumulate to $150-200K annually.

### Disaster Recovery ($300K/year)
- Azure Site Recovery costs money (replication, storage, compute on failover)
- Replicating 50TB for DR: $1,000/TB/month = $50K/month = $600K/year
- Can optimize with lifecycle policies, but still $300K+

### Management Tools ($100-150K/year)
- Azure Monitor is basic; need third-party (Datadog, Splunk, etc.)
- Cost management tools (CloudHealth, Cloudability)
- Security tools beyond Azure Security Center
- Enterprise-grade backup tools

### Training & Certifications ($50K/year ongoing)
- Azure constantly changing (new services monthly)
- Certs expire every 2-3 years, need renewal
- Ongoing education or skills decay

### Consulting & Support ($200-500K Year 1-2)
- WILL need help from Microsoft or partners
- Premier Support: $50K/year minimum
- Architecture reviews, migration assistance: $200/hour × hundreds of hours

**Total Hidden Costs**: $1-2M/year most people don't budget.

**Current Visibility**: Sarah knows some, Jennifer probably suspects, Michael unknown.

### Jobs-to-be-Done: Why Kevin Is Waiting for "Right Time"

**What Kevin Hopes to Achieve**:
> "I don't want to be seen as the guy who kills ideas before they start. I've seen this pattern: new executive, big vision, infrastructure guy raises concerns, executive thinks infrastructure guy is 'resistant to change' or 'protecting his turf,' infrastructure guy gets sidelined."

**Kevin's Dilemma**:
- If he speaks up too early → Seen as blocker, gets sidelined
- If he waits too long → Costs surprise everyone, blamed for "should have known"
- Either way, he loses

**Mitigation**: Documenting everything to Sarah - paper trail that issues were raised.

**Risk**: If surprises hit 6 months in, Kevin is still the "guy who should have warned us" despite documentation.

---

## Part 9: What Success Looks Like (Kevin's Vision)

### If We Do This RIGHT - 3 Years Out

**Operationally**:
- No more 2am hardware failure calls (cloud is redundant by design)
- No more "can't do that, no capacity" (cloud scales)
- Provision new environment in hours, not weeks
- DR actually WORKS (can test without disrupting production)
- Team spends 80% innovation / 20% firefighting (currently reversed)

**Strategically**:
- Support Robert's real-time production analytics (IoT → Azure)
- Give Sarah's developers modern DevOps pipelines
- Give Jennifer better cost visibility (tagged resources, chargeback)
- Support growth without $5M capital every 3 years

**Personally**:
- Recruit talent (people want modern stack, not ancient servers)
- Retain good people (Mark gets daily LinkedIn recruiter pings)
- Sleep at night knowing systems are reliable
- Focus on strategy instead of firefighting

### Seven Requirements for Success

1. **Realistic timeline** - 3 years minimum, not 18 months
2. **Adequate budget** - $10-15M over 3 years with contingency
3. **Phased approach** - Start non-critical, prove it works, THEN migrate critical
4. **Invest in people** - Hire/contract expertise, train existing team
5. **Operational discipline** - Cost management Day 1, not "optimize later"
6. **Executive alignment** - Michael, Jennifer, Robert, Sarah agree on timeline/cost/approach
7. **Incremental funding** - Don't need all $15M upfront, but need commitment over 3 years

**If Kevin Could Only Get ONE**: Executive alignment

**Rationale**: 
> "If Michael, Jennifer, and Robert are aligned on reality - costs, timeline, risks - everything else becomes possible. We can find budget, hire people, phase the work. But if they're not aligned, we're dead in the water."

**Current State**: "I think Michael has one vision, Jennifer has concerns, Robert has requirements, and they haven't really talked it through. That scares me."

---

## Part 10: Kevin's Advice to Michael

### The Message Kevin Would Give (If Asked Directly)

> "Michael, you were hired to modernize us. That's great - we desperately need it. But modernization isn't magic, and it isn't fast. It requires investment before returns, realism about costs and timeline, and alignment with the people who hold veto power - Jennifer, Robert, and frankly, Sarah.
>
> Before you promise anything to the board, sit down with the four of us - Sarah, Jennifer, Robert, and me. Not separately, TOGETHER. Put all the constraints on the table:
> - Jennifer's budget reality
> - Robert's operational requirements  
> - Sarah's technical debt reality
> - My infrastructure reality
>
> Then build a plan that addresses ALL of those constraints, not just the ones that fit your vision. It will take longer and cost more than you want. But it will actually WORK, and you'll have our support.
>
> If you try to do this alone or promise things we can't deliver, you'll lose credibility fast. You've got 60 days of goodwill. Use it to build a coalition, not to make commitments you can't keep."

**Would Kevin Say This to Michael's Face?**: Yes, if asked directly.

**Why Hasn't He Said It Yet?**: "He hasn't asked yet. He's still in 'vision' mode, not 'execution' mode. When he shifts to execution, he'll need infrastructure reality. I'm hoping Sarah will facilitate that conversation - she's the bridge between all of us."

### What Happens If That Conversation Never Happens?

> "Then we repeat the pattern from 18 months ago. Big vision, mounting costs, reality hits, initiative stalls, Michael leaves, new person comes in, cycle repeats. I've seen it three times in 15 years here. I'd really like this time to be different."

---

## Confidence Assessment

**Facilitator**: On a scale of 1-10, how confident are you this Azure modernization will succeed if we continue on the current path?

**Kevin**: Current path - meaning Michael driving solo without full alignment? **3 out of 10**.

**Why**: "We'll start strong, hit surprises around month 4-6, costs will escalate, timeline will slip, and either we'll scale way back or cancel."

**What Would Get to 8/10?**:

The four-way conversation:
- Michael + Jennifer + Robert + Sarah + Kevin
- Full transparency on constraints
- Agreement on phased approach
- Realistic budget with contingency
- 3-year timeline with milestones
- Commitment to operational discipline in cloud

**Kevin's Closing Thought**:
> "We've got good people, real need, and finally a CFO (Jennifer) who understands you have to invest before you save. We just need everyone aligned."

---

## Key Quotes

**On Infrastructure Reality**:
> "Our infrastructure is held together with duct tape and prayers. I've been screaming about this for three years, but there's never budget."

**On Cloud Migration Myth**:
> "Everyone thinks cloud is this magic switch you flip. It's not. It's actually MORE expensive in the short term."

**On Budget Cuts**:
> "I requested $4.2 million for infrastructure refresh. You know what I got? $800,000. Jennifer said we couldn't justify capital expenditure on infrastructure we're 'planning to move to the cloud anyway.' That was 18 months ago."

**On Hidden Costs**:
> "Most orgs don't realize [data egress costs] until they get a $50K surprise bill."

**On Operational Discipline**:
> "We're good at capital budgeting. We're TERRIBLE at operational discipline. We build, we accumulate, we never clean up. If we bring that culture to cloud, we'll have 600 underutilized VMs running 24/7."

**On Being Seen as the "No Guy"**:
> "I'm not trying to block progress. I WANT us to modernize. I want to work on interesting problems, not baby ancient hardware. But I also can't let us walk into disaster with our eyes closed. Someone has to be the adult in the room."

**On Executive Alignment**:
> "Right now, I think Michael has one vision, Jennifer has concerns, Robert has requirements, and they haven't really talked it through. That scares me."

**On Pattern Recognition**:
> "Big vision, mounting costs, reality hits, initiative stalls, Michael leaves, new person comes in, cycle repeats. I've seen it three times in 15 years here. I'd really like this time to be different."

---

## Interviewer Observations

### Methodology Notes

**Five Whys Effectiveness**: 
- Uncovered root cause of infrastructure debt (circular "moving to cloud" logic)
- Revealed Kevin's personal dilemma (damned if speaks up, damned if doesn't)
- Exposed leadership perception gap (infrastructure as blocker vs. enabler)

**Jobs-to-be-Done Insights**:
- Kevin's job: Balance being supportive vs. honest without being sidelined
- Underlying need: Be heard and respected as strategic partner, not just "plumbing guy"
- Success metric: See ONE modernization initiative succeed in his tenure

### Emotional Tone
- Started defensive ("held together with duct tape and prayers")
- Shifted to data-driven (pulled out detailed spreadsheets, did math)
- Became reflective when discussing leadership perception ("someone has to be the adult")
- Ended hopeful but cautious (wants THIS time to be different)

### Trust & Credibility Signals
- **High**: Extensive documentation, detailed cost models, historical data
- **High**: Self-aware about perception challenges
- **High**: Genuinely wants success, not just protecting territory
- **High**: Defers to Sarah as "bridge" between stakeholders

### Contradictions with Prior Interviews
- **Confirms** Sarah's technical debt assessment (if anything, adds more detail)
- **Confirms** Jennifer's Year 1 cost doubling (Kevin shows $8.75-9.75M vs. current $4.5M)
- **Confirms** Robert's parallel running requirement (Kevin quantifies at $800K-1.2M)
- **Contradicts** Michael's 18-month timeline (Kevin says 3 years minimum)
- **Contradicts** Michael's 50% cost savings promise (Kevin shows cloud may not save money for 3+ years)

### Power & Influence
- **Formal power**: LOW (manager, not director or VP)
- **Informal power**: MEDIUM-HIGH (holds infrastructure keys, veto via failure)
- **Veto mechanism**: Passive (infrastructure collapses if not addressed, vs. active veto by Jennifer/Robert)
- **Trust network**: Strong with Sarah, unknown with Jennifer/Robert, building with Michael

### Critical Risks Identified
1. Hardware failure spiral before migration completes (probability increasing exponentially)
2. Network capacity bottleneck delays migration by 6-8 months
3. Hidden costs cause budget overrun, trigger Jennifer's kill criteria
4. Lack of Azure expertise causes quality issues, Robert loses confidence
5. Operational indiscipline in cloud causes costs to match/exceed on-prem, eliminating ROI
6. Four-way alignment never happens, initiative fails like predecessor 18 months ago

---

## Recommended Follow-Up Questions

### For Michael
1. What is your current project budget estimate?
2. Have you budgeted for parallel running infrastructure ($800K-1.2M)?
3. Have you budgeted for cloud expertise staffing ($1.4-2M Year 1)?
4. Are you aware of the $4.2M infrastructure debt and $2.5M minimum required during migration?
5. What is your plan for the network capacity bottleneck?

### For Jennifer
1. Are you aware Kevin requested $4.2M infrastructure refresh and received $800K?
2. In your Year 1 cost doubling estimate, did you include Kevin's infrastructure requirements?
3. What are your criteria for evaluating "adequate contingency budget"?

### For Sarah
1. Kevin has shared his infrastructure estimates with you - have you shared them with Michael?
2. Do you agree with Kevin's assessment that the team lacks Azure expertise?
3. What is your assessment of the "operational discipline" needed for cloud cost management?

### Cross-Stakeholder Alignment Session
**Recommended Attendees**: Michael, Jennifer, Robert, Sarah, Kevin
**Purpose**: Put all constraints on table, build unified plan
**Timing**: BEFORE board presentation (30-day deadline from Interview 3)

---

## Discovery Progress Update

**Interviews Completed**: 5 of 11 (45%)

**Critical Themes Emerging**:
1. ✅ **Timeline misalignment** - Confirmed across all 5 interviews (Michael: 18 months, Everyone else: 3+ years)
2. ✅ **Cost reality** - Infrastructure adds $2.5M+ to Year 1, plus $1-2M hidden costs
3. ✅ **Three veto powers** - Jennifer (budget), Robert (operations), now Kevin (infrastructure collapse as passive veto)
4. ✅ **Trust hierarchy** - All four trust Sarah > Michael (Kevin is 4th to confirm this)
5. ✅ **Parallel running requirements** - Now quantified at $800K-1.2M infrastructure costs
6. ⚠️ **NEW: Hardware crisis** - Exponential failure rates, may force immediate action regardless of cloud plans
7. ⚠️ **NEW: Network bottleneck** - 6-8 months just for data transfer, needs immediate resolution
8. ⚠️ **NEW: Expertise gap** - $1.4-2M staffing needs not yet budgeted

**Next Priorities**:
1. Interview Jimmy Garcia (Union) - Robert's #1 requirement for early engagement
2. Interview remaining technical/operational staff
3. Facilitate four-way alignment session BEFORE board presentation
4. Update feasibility assessment with infrastructure constraints

---

**End of Interview Transcript**

*Transcript prepared by Discovery Facilitator*  
*Phase 0 - Discovery & Ideation*  
*Contoso Manufacturing Azure Modernization Initiative*