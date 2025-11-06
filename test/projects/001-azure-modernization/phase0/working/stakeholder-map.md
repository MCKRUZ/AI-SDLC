# Stakeholder Map - Azure Cloud Modernization Project

**Project**: Precision Manufacturing Inc. - Azure Cloud Migration  
**Document Version**: 1.9  
**Last Updated**: 2025-11-05  
**Interview Progress**: 9 of 11 complete (82%)

---

## Executive Summary

**Total Stakeholders Identified**: 11  
**Interviews Complete**: 9  
**Interviews Remaining**: 2 (IT Manager, HR Director)

**Stance Distribution**:
- 🟢 SUPPORTIVE: 2 (Michael, James)
- 🟡 CONDITIONAL: 4 (Sarah, Linda, David, Tom)
- 🔴 OPPOSED: 1 (Robert)
- 🟠 SKEPTICAL: 2 (Jennifer, Maria)
- ⚪ UNKNOWN: 2 (Not yet interviewed)

**Key Finding**: Every floor-level stakeholder (Robert, Maria) is either opposed or skeptical. Support team already burned out before migration begins.

---

## Stakeholder Details

### 1. Michael Chen - CEO

**Role**: Chief Executive Officer  
**Reports to**: Board of Directors  
**Authority**: Final decision maker  
**Tenure**: 2 years at company (from tech industry)  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟢 SUPPORTIVE (Driving Initiative)

**Key Concerns**:
1. Competitiveness - Falling behind competitors
2. Speed - Wants 18-month timeline
3. Customer experience - Modern systems = better service
4. Innovation - Current systems can't support new capabilities
5. Cost - Needs to understand total investment

**What They Need**:
1. Clear ROI and business case
2. Risk mitigation strategy
3. Realistic timeline with milestones
4. Confidence the company can execute
5. Stakeholder alignment (especially floor operations)

**Success Vision**:
- Company becomes technology leader in precision manufacturing
- Faster time-to-market for customers
- Real-time visibility across operations
- Modern, cloud-based systems
- Competitive advantage through technology

**Failure Fear**:
- Falling further behind competitors
- Losing key customers to more agile competitors
- Being unable to support modern manufacturing demands
- Company becomes obsolete

**Power/Influence**:
- Direct: All executive decisions, budget allocation
- Indirect: Sets company vision and culture
- Veto: Absolute (can stop or proceed regardless of other input)

**Relationship to Project**:
- Project sponsor and champion
- Has tech industry background (understands cloud benefits)
- Willing to invest significant resources
- Open to feedback about timeline
- Concerned about stakeholder alignment

**Key Quote**:
> "If we don't modernize now, we won't be here in five years. Our competitors are eating our lunch."

**Open to Feedback**: YES - Specifically asked about realistic timeline

---

### 2. Sarah Kim - IT Director

**Role**: IT Director  
**Reports to**: Michael Chen (CEO)  
**Team**: ~30 people across infrastructure, applications, support  
**Tenure**: 12 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟡 CONDITIONAL SUPPORT (If Done Properly)

**Key Concerns**:
1. Team capacity - Already stretched thin
2. Skills gap - Team has zero cloud experience
3. SAP trauma - Team still recovering from failed SAP implementation
4. Realistic timeline - 18 months feels aggressive
5. Vendor lock-in risk
6. Legacy system dependencies
7. Support during transition

**What They Need**:
1. 8-12 months just for skills building (Azure, DevOps, cloud architecture)
2. External consulting help (not trying to do it alone)
3. Realistic timeline (24-36 months more realistic)
4. Proof of concept before full commitment
5. Clear fallback/rollback plans
6. Budget for training and contractors
7. Stakeholder buy-in (especially from floor operations)

**Success Vision**:
- Modern, reliable systems that are easier to maintain
- Team upskilled in cloud technologies
- Better support for manufacturing operations
- Reduced on-call burden (current systems page them constantly)

**Failure Fear**:
- "SAP 2.0" - Repeating the failed SAP implementation
- Team burnout and attrition
- Systems go down during migration
- Losing credibility with floor operations (already strained relationship)
- Being blamed for Michael's aggressive timeline

**Power/Influence**:
- Direct: IT team execution, technical decisions
- Indirect: Can influence Michael's understanding of technical reality
- Veto: Soft veto (can make Michael reconsider if timeline/approach is unrealistic)

**Relationship to Project**:
- Key execution leader (project fails without IT team)
- Wants to succeed but needs realistic conditions
- Protective of team (won't sacrifice them for unrealistic deadline)
- Credibility at stake after SAP failure

**Key Quote**:
> "I want to do this right. I don't want to do SAP 2.0. My team is still traumatized from that."

**Critical Condition**: Will only proceed if timeline and resources are realistic

---

### 3. James Wilson - CFO

**Role**: Chief Financial Officer  
**Reports to**: Michael Chen (CEO)  
**Authority**: Budget approval, financial oversight  
**Tenure**: 8 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟢 SUPPORTIVE (But Needs Business Case)

**Key Concerns**:
1. Total cost of ownership - What's the real number?
2. Hidden costs - Migration, training, parallel running, support
3. ROI timeline - How long until payback?
4. Cash flow impact - Can't spend $10M in 18 months
5. Opportunity cost - What else could we invest in?
6. Risk to operations - Production downtime = lost revenue

**What They Need**:
1. Detailed cost breakdown across all categories
2. ROI analysis with conservative assumptions
3. Cash flow model showing phased spending
4. Risk quantification (what happens if things go wrong)
5. Comparison to alternatives (cloud vs. on-prem upgrade)
6. Validation of Michael's $3M estimate (seems low)

**Success Vision**:
- Lower TCO over 5 years
- Reduced infrastructure maintenance costs
- Better financial visibility and forecasting
- Systems that support business growth
- Predictable cloud spending vs. unpredictable maintenance

**Failure Fear**:
- Cost overruns (like SAP, which went 3x over budget)
- Paying for both old and new systems for extended period
- Production downtime causing revenue loss
- Hidden costs emerging mid-project
- Poor ROI - spent $20M for minimal benefit

**Power/Influence**:
- Direct: Budget approval, cost control
- Indirect: Can influence Board's perception
- Veto: Strong veto (can block if business case doesn't close)

**Relationship to Project**:
- Financial gatekeeper
- Wants project to succeed but needs compelling business case
- Burned by SAP cost overruns ($10M vs. $3M budgeted)
- Will ask hard questions about costs

**Key Quote**:
> "I'm not writing a blank check. SAP went three times over budget. We need a realistic number before we commit."

**Critical Condition**: Needs realistic cost estimates and solid ROI

---

### 4. Robert Garcia - Floor Supervisor (3rd Shift)

**Role**: Floor Supervisor, 3rd Shift (10 PM - 6 AM)  
**Reports to**: Jennifer Martinez (VP Operations)  
**Team**: 12 operators on 3rd shift  
**Tenure**: 22 years at company (started as operator)  
**Interview Status**: ✅ COMPLETE

**Stance**: 🔴 OPPOSED (Deep Skepticism, Will Resist)

**Key Concerns**:
1. MES system absolutely cannot fail during production
2. SAP trauma - Still dealing with fallout (workarounds, slower processes)
3. Operators will rebel against more change
4. 3rd shift always gets worst support (2-3 AM issues = wait until morning)
5. "Tech people" don't understand floor reality
6. Training will be inadequate (like SAP was)
7. Zero tolerance for downtime

**What They Need**:
1. Guarantee that MES works as well or better than current system
2. Real training for operators (not 2-hour sessions)
3. 24/7 support for 3rd shift (not "submit a ticket and wait")
4. Prove new system works BEFORE forcing switch
5. Operators' input valued in design decisions
6. Respect for floor expertise
7. Michael to work 3rd shift for a week (understand floor reality)

**Success Vision**:
- Faster, more reliable systems
- Better support during 3rd shift
- Operators don't have to fight systems to do their jobs
- Real partnership between IT and floor operations

**Failure Fear**:
- "SAP 2.0" - Another disaster pushed by people who don't understand manufacturing
- MES goes down during production = scrap, missed shipments, chaos
- Operators quit because of more badly-implemented change
- Being blamed when systems fail ("user error")
- Career ends dealing with another tech failure

**Power/Influence**:
- Direct: 12 operators on 3rd shift
- Indirect: Respected voice among ALL floor supervisors/operators
- Veto: Soft veto through non-cooperation (can make adoption fail through resistance)

**Relationship to Project**:
- Critical stakeholder (MES adoption fails without floor buy-in)
- Institutional knowledge (22 years - knows every workaround, every issue)
- Influential voice (other supervisors listen to Robert)
- Trust must be earned (IT broke trust with SAP)

**Key Quote**:
> "You know what I think? I think Michael should work third shift for a week. See what it's like when the system goes down at 2 AM and you can't make your morning shipments."

**Trust Rebuilding Required**: IT must earn back trust lost during SAP implementation

---

### 5. Jennifer Martinez - VP of Operations

**Role**: Vice President of Operations  
**Reports to**: Michael Chen (CEO)  
**Authority**: Operations decisions, production oversight  
**Team**: 3 shift supervisors + ~50 floor operators  
**Tenure**: 15 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟠 SKEPTICAL BUT PRAGMATIC (Scarred by SAP)

**Key Concerns**:
1. SAP disaster still affecting operations (slower order processing)
2. Floor workers' trust in IT is broken
3. MES is mission-critical (touches every aspect of production)
4. Training must be comprehensive (not 2-hour "training" like SAP)
5. Timeline feels aggressive given complexity
6. Fear of another top-down tech initiative
7. Operators already dealing with SAP workarounds

**What They Need**:
1. Floor workers involved from day one (not informed at the end)
2. Comprehensive training (weeks, not hours)
3. Parallel running period with both systems (6-12 months)
4. Prove new MES works before forcing switch
5. 24/7 support during transition (especially 3rd shift)
6. Realistic timeline that allows proper validation
7. Clear rollback plan if things go wrong

**Success Vision**:
- Faster order processing and quoting
- Better visibility into production status
- Fewer system issues for floor workers
- Modern systems that support growth
- Restored trust between IT and operations

**Failure Fear**:
- "SAP 2.0" - Another forced tech change that makes jobs harder
- MES failure causing production chaos
- More operators quit due to poorly-implemented change
- Operations blamed for IT's failures
- Company loses key customers during transition

**Power/Influence**:
- Direct: All production operations, operator assignments
- Indirect: Strong voice with Michael and Board
- Veto: Strong veto (can convince Michael that risks outweigh benefits)

**Relationship to Project**:
- Critical gatekeeper (manufacturing is the company)
- Pragmatic - willing to support if done properly
- Protective of floor workers
- Damaged trust from SAP must be rebuilt

**Key Quote**:
> "I'm not going to let IT break my floor again. If this is going to be SAP 2.0, I'll tell Michael it's not worth the risk."

**Critical Condition**: Floor workers must be involved from start, not informed at the end

---

### 6. Linda Park - HR Director

**Role**: HR Director  
**Reports to**: Michael Chen (CEO)  
**Authority**: Hiring, retention, training, culture  
**Tenure**: 5 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟡 CONDITIONAL SUPPORT (If People Aspects Addressed)

**Key Concerns**:
1. Training costs massively underestimated ($50K vs. $12-15M reality)
2. Retention risk - People will leave if change managed poorly
3. Workload during transition - IT already burned out
4. Skills gaps across multiple roles
5. Change fatigue - SAP still causing stress
6. Culture impact - Another top-down initiative
7. Union implications (operators are unionized)

**What They Need**:
1. Realistic training budget ($12-15M minimum)
2. Change management resources (proper change management team)
3. Retention strategy (bonuses, career development, workload relief)
4. Mental health support (people are already stressed)
5. Union partnership approach (not adversarial)
6. Hiring plan for additional support staff
7. Timeline that allows proper preparation

**Success Vision**:
- Workforce upskilled and confident
- Change managed properly (not forced)
- Retention of key people
- Culture of partnership (not us-vs-them)
- People feel valued and supported

**Failure Fear**:
- Key people quit (especially institutional knowledge holders)
- Another traumatic change like SAP
- Union grievances and labor issues
- Toxic culture develops
- "People problem" blamed on individuals vs. bad process

**Power/Influence**:
- Direct: Hiring, retention programs, training delivery
- Indirect: Influence on culture and morale
- Veto: Soft veto (can highlight people risks to Michael)

**Relationship to Project**:
- Critical for people aspects (technology fails without people)
- Realistic about challenges (not sugar-coating)
- Partner to operations and IT
- Concerned about retention of key staff

**Key Quote**:
> "Training isn't $50K. It's $12 million to $15 million minimum. And if we don't address retention, we'll lose the people who know how things actually work."

**Critical Condition**: Training and change management must be funded properly

---

### 7. David Foster - CTO

**Role**: Chief Technology Officer  
**Reports to**: Michael Chen (CEO)  
**Authority**: Technical strategy, architecture decisions  
**Tenure**: 18 months at company (from tech industry)  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟡 CONDITIONAL SUPPORT (Needs Proper Architecture)

**Key Concerns**:
1. MES-ERP integration complexity (massive data flows, real-time requirements)
2. Custom MES components must be recreated (can't just lift-and-shift)
3. Validation infrastructure not designed yet
4. Network architecture inadequate for cloud
5. Security model completely different
6. No POC to validate approach
7. Timeline doesn't account for discovery work

**What They Need**:
1. 3-6 months for proper architecture and POC
2. Integration architecture designed properly (not figure out later)
3. Network infrastructure upgraded ($500K-1M)
4. Security model designed (zero-trust, identity management)
5. Validation environment designed (can't validate in production)
6. Migration sequencing strategy (what moves when)
7. External architecture expertise (Sarah's team not experienced enough)

**Success Vision**:
- Modern, scalable, cloud-native architecture
- Proper separation of concerns
- API-driven integration
- Observable systems (proper monitoring)
- Infrastructure as code
- Security built-in from start

**Failure Fear**:
- "Lift and shift" disaster (moving problems to cloud)
- Integration failures causing production issues
- Security breaches (manufacturing = IP risk)
- Technical debt built into new systems
- Having to redo work because architecture was wrong

**Power/Influence**:
- Direct: Technical architecture decisions, technology strategy
- Indirect: Influence Michael's understanding of technical reality
- Veto: Strong technical veto (can block bad technical approaches)

**Relationship to Project**:
- Critical for technical success
- Wants to build things properly (not quick-and-dirty)
- Concerned about Sarah's team capacity
- Aligned with Sarah on timeline reality

**Key Quote**:
> "We're not just moving servers to the cloud. We're rearchitecting the entire technical foundation of this company. That takes time and expertise."

**Critical Condition**: Architecture phase must happen before migration commits

---

### 8. Maria Santos - Floor Operator (2nd Shift)

**Role**: Floor Operator, 2nd Shift (2 PM - 10 PM)  
**Reports to**: 2nd Shift Supervisor (reports to Jennifer Martinez)  
**Tenure**: 8 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟠 SKEPTICAL (From Hard Experience)

**Key Concerns**:
1. SAP training was terrible (2 hours for system used daily)
2. MES runs her job - Any issues = can't do work
3. Management makes changes without asking operators
4. Second shift gets worst support (issues wait until morning)
5. System failures = stress, blame, performance issues
6. Previous changes never made job easier
7. "Training" usually means "figure it out yourself"

**What They Need**:
1. Real training (weeks, not hours, with practice environment)
2. Input into design (operators know what works on floor)
3. Proof new system works BEFORE forced to use it
4. Adequate support during transition (especially 2nd/3rd shift)
5. System that's actually better (not just different)
6. Recognition that operators are experts (not "users who don't get it")
7. Michael should work a floor shift (understand operator reality)

**Success Vision**:
- Systems that work reliably
- Training that actually prepares her to use systems
- Support available when needed (not "wait until morning")
- Management values operator expertise
- Changes make job easier, not harder

**Failure Fear**:
- SAP 2.0 - Another poorly-implemented change
- Training inadequate (like always)
- Support inadequate during transition
- Performance suffers due to system issues
- Gets blamed for "not adapting" when systems are bad

**Power/Influence**:
- Direct: Her own adoption/resistance
- Indirect: Voice for all floor operators (shares experiences)
- Veto: Soft veto through non-cooperation (can influence adoption success)

**Relationship to Project**:
- Representative of floor operator perspective
- Institutional knowledge of floor workflows
- Credibility with other operators
- Willing to support IF done properly

**Key Quote**:
> "They gave us two hours of SAP training for a system we use every single day. Two hours! And then they wondered why we were struggling. It wasn't us—it was them."

**Trust Rebuilding Required**: Must demonstrate this time will be different

**NOTE**: Maria echoed Robert and Tom's suggestion that Michael should work 2nd shift for a week to understand support challenges during afternoon/evening.

---

### 9. Tom Bradley - Support Team Lead

**Role**: Support Team Lead  
**Reports to**: Sarah Kim (IT Director)  
**Team**: 10 people (6 Level 1, 3 Level 2, 1 lead)  
**Tenure**: 6 years at company  
**Interview Status**: ✅ COMPLETE

**Stance**: 🟡 CONCERNED BUT WILLING (If Done Properly)

**Key Concerns**:
1. Support team already burned out (3-4 pages/night, every night)
2. Ticket volume will double during migration (80-100 → 150-200/day)
3. Zero consultation on migration plans (heard "third-hand")
4. Help desk model won't work for floor systems during transition
5. Team has zero cloud skills (need 3-6 months Azure training)
6. MES migration terrifying (most problematic system to support)
7. Fear of SAP 2.0 (200-300 tickets/day, 10-15 pages/night)
8. 30% attrition in 18 months (3 people left due to burnout)

**What They Need**:
1. 4-6 more support staff to handle increased load
2. $2-3M for support contractors (backfill + migration support)
3. Floor-level support model for MES (not remote help desk)
4. 3-6 months Azure/cloud training for team (before migration starts)
5. Address burnout BEFORE migration starts
6. Realistic timeline (support needs 12-18 months to prepare)
7. Better documentation and knowledge base
8. Immediate engagement in planning (not third-hand information)

**Success Vision**:
- Modern cloud systems that are faster and more reliable
- Better for operators, easier for support team
- Reduced on-call burden
- Company more competitive
- Support team properly staffed and trained

**Failure Fear**:
- SAP 2.0 (repeat of chaos: 200-300 tickets/day, 10-15 pages/night)
- Support team buried in tickets and burns out
- People quit (operators and support staff)
- Further damage to IT-floor relationship
- "I don't know if this company can survive another SAP"

**Power/Influence**:
- Direct: Support team operations (10 people)
- Indirect: Floor workers depend on support (inadequate support = adoption failure)
- Veto: Can't veto but inadequate support guarantees adoption failure

**Relationship to Project**:
- Critical stakeholder (migration fails without adequate support)
- Not consulted yet (needs immediate engagement)
- Willing to support if done properly
- Echoes Maria and Robert on Michael floor shift suggestion
- Only 1 person (Steve) has manufacturing background on team

**Key Quote**:
> "If they steamroll ahead with the 18-month timeline and inadequate resources? It'll be SAP 2.0. And I don't know if this company can survive another SAP."

**Critical Support Facts**:
- **Current Tickets**: 80-100/day, 300-350 backlog
- **During Migration**: 150-200/day expected
- **MES Tickets**: 30-35% of current volume (most problematic)
- **On-Call Burden**: 3-4 pages/night, 1 week per 5 weeks rotation
- **SAP On-Call**: 10-15 pages/night (one person had breakdown)
- **Attrition**: 30% in 18 months (3 people)
- **Manufacturing Background**: Only Steve (1 of 10)
- **Support Contractors Needed**: 2-3 backfill, 4-6 migration = $2-3M

**Trust Rebuilding Required**: Must engage support in planning, not inform after decisions made

**NOTE**: Tom strongly echoed Maria's (Interview 8) and Robert's (Interview 4) suggestion that Michael should work a 2nd shift week to understand support response challenges during afternoon/evening hours.

---

### 10. Alex Kumar - IT Manager

**Role**: IT Manager (Infrastructure & Applications)  
**Reports to**: Sarah Kim (IT Director)  
**Team**: ~20 people (servers, networking, database, applications)  
**Tenure**: Unknown  
**Interview Status**: ⏳ PENDING

**Preliminary Assessment**:
- Direct report to Sarah Kim
- Manages most of IT team execution
- Critical for understanding:
  - Overall IT team capacity and workload
  - Skills inventory beyond what Sarah described
  - Team morale and retention risk
  - Infrastructure readiness
  - Application dependencies

**Questions to Explore**:
1. How does the team feel about this initiative?
2. What's the current workload and capacity?
3. What skills gaps exist beyond cloud/Azure?
4. How many people are at flight risk?
5. What are the biggest technical concerns?
6. How does infrastructure team view timeline?
7. What lessons from SAP should inform this project?
8. What's the maintenance window reality? (Weekend-only constraint)
9. How does team capacity/workload compare to support team?
10. What's retention risk if migration starts without addressing burnout?

---

### 11. Patricia Williams - HR Director (Placeholder - May be same as Linda Park)

**Role**: HR Director  
**Reports to**: Michael Chen (CEO)  
**Tenure**: Unknown  
**Interview Status**: ⏳ PENDING

**Note**: This may be the same person as Linda Park (Interview 6). Need to verify if there's a second HR stakeholder or if Linda Park should be the final interview.

**If Different Person - Questions to Explore**:
1. What's realistic cost to hire 4-6 new support staff?
2. How long to recruit support people with manufacturing background?
3. What's retention strategy to prevent more support attrition?
4. How to address support team burnout and morale?
5. Validate Tom's $50K/operator training estimate?
6. Manufacturing-experienced trainer sourcing strategy?
7. Union implications of major technology change?
8. Change management resources available?

**If Same as Linda Park**:
- Interview 11 becomes follow-up with Linda to explore:
  - Support team hiring and retention specifically
  - Manufacturing trainer sourcing
  - Union partnership strategy details
  - Change management team composition

---

## Stakeholder Relationship Map

### Power Structure

```
Board of Directors
        |
    Michael Chen (CEO)
    /     |      \
Sarah   James   Jennifer   Linda   David
(IT)    (CFO)   (Ops)     (HR)    (CTO)
  |                |
Tom              Robert
(Support)        (Floor Supervisor)
  |                |
Support Team     Maria + 50 Operators
(10 people)      (All shifts)
```

### Trust Hierarchies

**Institutional Knowledge (High Trust)**:
- Robert Garcia (22 years) - Floor operations authority
- Sarah Kim (12 years) - IT reality authority
- Jennifer Martinez (15 years) - Operations authority
- James Wilson (8 years) - Financial authority
- Maria Santos (8 years) - Operator perspective authority
- Tom Bradley (6 years) - Support reality authority

**New Leadership (Lower Trust Initially)**:
- Michael Chen (2 years) - Vision but floor skeptical
- David Foster (18 months) - Tech knowledge but unproven
- Linda Park (5 years) - Middle ground

**Trust Dynamic**: Floor and support trust institutional knowledge holders over new tech-focused leadership. Michael and David must earn trust.

---

## Coalition Patterns

### "Make It Work" Coalition (Pragmatic)
- Sarah Kim (IT Director) - "Do it right or don't do it"
- Jennifer Martinez (VP Ops) - "Floor must be involved"
- Linda Park (HR Director) - "People aspects must be addressed"
- David Foster (CTO) - "Architecture must be proper"
- Tom Bradley (Support Lead) - "Support must be adequate"

**Stance**: Will support IF conditions are met (realistic timeline, proper resources, floor involvement, adequate support)

### "Floor Reality" Coalition (Skeptical)
- Robert Garcia (Floor Supervisor) - Active resistance
- Maria Santos (Operator) - Skeptical from experience
- Tom Bradley (Support Lead) - Concerned about support capacity

**Stance**: Deeply skeptical due to SAP trauma; needs trust rebuilding; will resist if forced

### "Drive Forward" Coalition (Optimistic)
- Michael Chen (CEO) - Pushing initiative
- James Wilson (CFO) - Supportive if business case closes

**Stance**: Want to proceed but will listen to concerns

---

## Critical Veto Powers

### Absolute Veto
- **Michael Chen**: Can stop or proceed regardless of input
- **James Wilson**: Can block if business case doesn't close

### Strong Veto (Can Convince Michael)
- **Jennifer Martinez**: Can convince Michael risks outweigh benefits
- **Sarah Kim**: Can make Michael reconsider if timeline unrealistic
- **David Foster**: Can block bad technical approaches

### Soft Veto (Through Non-Cooperation)
- **Robert Garcia**: Can make adoption fail through resistance (floor influence)
- **Support Team**: Inadequate support guarantees adoption failure
- **Floor Operators**: Collective resistance makes adoption impossible

**Key Insight**: Michael has absolute authority but floor-level soft vetoes can make project fail through non-cooperation.

---

## Stakeholder Alignment Status

### Aligned Stakeholders: 2 of 11
- ✅ Michael Chen (CEO) - Driving initiative
- ✅ James Wilson (CFO) - Supportive if business case closes

### Conditional Stakeholders: 4 of 11
- ⚠️ Sarah Kim - IF timeline realistic and team supported
- ⚠️ Jennifer Martinez - IF floor involved from start
- ⚠️ Linda Park - IF people aspects funded properly
- ⚠️ David Foster - IF architecture phase happens
- ⚠️ Tom Bradley - IF support adequately resourced

### Opposed/Skeptical: 3 of 11
- ❌ Robert Garcia - Active resistance (SAP trauma)
- ⚠️ Maria Santos - Skeptical (poor past experience)
- ⚠️ Tom Bradley - Concerned (burnout + capacity crisis)

### Unknown: 2 of 11
- ❓ Alex Kumar (IT Manager)
- ❓ Patricia Williams (HR Director - may be Linda Park)

**CRITICAL**: No floor-level or support stakeholders are aligned. All are conditional, skeptical, or opposed.

---

## Key Findings

### 1. Trust Must Be Rebuilt
- SAP broke trust between IT and floor operations
- IT seen as "people who don't understand manufacturing"
- Floor workers feel ignored and disrespected
- Support team traumatized by SAP chaos
- "Management makes changes without asking us"

**Implication**: Partnership approach required, not top-down implementation

### 2. Institutional Knowledge Holders Are Gatekeepers
- Robert Garcia (22 years) - Respected floor voice
- Sarah Kim (12 years) - IT reality check
- Jennifer Martinez (15 years) - Operations gatekeeper
- Tom Bradley (6 years) - Support reality
- Their opposition/skepticism is informed by hard experience

**Implication**: Must address their concerns or project fails

### 3. Support Team Crisis
- Already burned out before migration starts
- 30% attrition in 18 months
- 3-4 pages every night
- Ticket volume will double during migration
- Zero cloud skills
- Only 1 person with manufacturing background
- Help desk model breaks down during major changes
- $2-3M support contractors not budgeted

**Implication**: Support adequacy is existential risk

### 4. Timeline Is Primary Conflict Point
- Michael wants 18 months
- Sarah/David say 24-36 months minimum
- Robert/Maria/Tom need adequate time for training and support prep
- Rushing = guaranteed failure (SAP proved this)

**Implication**: Timeline negotiation is critical early decision

### 5. Training Budget Massively Underestimated
- Michael estimated $50K
- Linda calculated $12-15M realistic
- 240x difference
- Tom needs $2-3M just for support contractors

**Implication**: Budget reality check needed immediately

### 6. MES Is Most Critical (And Most Complex)
- Every stakeholder cited MES as highest risk
- Robert: "MES goes down = chaos"
- Jennifer: "MES touches everything in production"
- Tom: "MES is most problematic system to support"
- David: "MES integration is most complex"

**Implication**: MES migration strategy is project-critical

### 7. Three Stakeholders Suggest Michael Work Floor Shift
- Robert (Interview 4): "Michael should work third shift for a week"
- Maria (Interview 8): "Management should see what operators deal with"
- Tom (Interview 9): "Second shift ideal - support challenges worst after 3 PM"

**Implication**: Consistent theme - leadership needs floor reality experience

---

## Recommendations for Engagement

### Immediate Actions Required

1. **Engage Tom Bradley Immediately**
   - Support Lead heard about migration "third-hand"
   - Needs to be at planning table
   - Support strategy must be designed NOW

2. **Engage Robert Garcia Early**
   - Most influential floor voice
   - Most opposed stakeholder
   - Trust rebuilding required
   - If Robert is convinced, others will follow

3. **Complete Remaining Interviews**
   - Alex Kumar (IT Manager) - 80% of way through interviews
   - HR Director (if different from Linda)

4. **Floor Reality Experience**
   - Michael working floor shift (2nd shift suggested)
   - David working floor shift
   - Build empathy and understanding

### Partnership Approach

1. **Floor Workers as Experts**: Value their input, don't override it
2. **Support Team Engagement**: Design support model together
3. **Transparent Communication**: No more third-hand information
4. **Realistic Commitments**: Admit SAP failures, commit to different approach
5. **Adequate Resources**: Fund training, support, change management properly

### Success Conditions

For project to succeed, must achieve:
- ✅ Sarah Kim conditional support → Full support
- ✅ Jennifer Martinez conditional support → Full support
- ✅ Robert Garcia opposition → Cautious support
- ✅ Linda Park conditional support → Full support
- ✅ David Foster conditional support → Full support
- ✅ Tom Bradley concerns → Adequate support confidence
- ✅ Maria Santos skepticism → Willing to try

**Current State**: 2 of 11 aligned, 4 conditional, 3 opposed/skeptical, 2 unknown  
**Target State**: 9-11 of 11 aligned (some skepticism acceptable if conditions met)

---

## Next Steps

1. ✅ Complete Interview 10 (Alex Kumar - IT Manager)
2. ✅ Complete Interview 11 (HR Director or Linda Park follow-up)
3. ✅ Conduct Phase 0 synthesis
4. ✅ Create comprehensive problem statement
5. ✅ Present findings to Michael with realistic timeline and budget
6. ✅ Develop stakeholder engagement strategy
7. ✅ Design trust-rebuilding approach for floor operations
8. ✅ Design adequate support model with Tom

---

**Document Status**: Artifact updated through Interview 9 (Tom Bradley)  
**Next Update**: After Interviews 10-11 complete