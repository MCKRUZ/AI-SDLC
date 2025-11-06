# Theme Tracking - Azure Cloud Modernization Project

**Project**: Precision Manufacturing Inc. - Azure Cloud Migration  
**Document Version**: 1.9  
**Last Updated**: 2025-11-05  
**Interview Progress**: 9 of 11 complete (82%)

---

## Executive Summary

**Total Themes Identified**: 18  
**Cross-Cutting Themes**: 12 (mentioned by 3+ stakeholders)  
**Emerging Themes**: 6 (mentioned by 1-2 stakeholders)

**Strongest Themes** (5+ mentions):
1. SAP Trauma and "Never Again" (8 mentions)
2. Trust Deficit Between IT and Floor (7 mentions)
3. Timeline Reality vs. Leadership Goals (7 mentions)
4. MES as Mission-Critical System (7 mentions)
5. Training Inadequacy Pattern (6 mentions)
6. Support Adequacy During Transition (6 mentions - NEW)

---

## Theme Definitions and Tracking

### THEME 1: SAP Trauma and "Never Again"

**Definition**: The failed SAP implementation continues to traumatize the organization and shapes all stakeholder responses to technology change initiatives.

**Mentioned by (8)**:
1. Sarah Kim (Interview 2) - "My team is still traumatized"
2. Robert Garcia (Interview 4) - "SAP disaster", "we're still dealing with it"
3. Jennifer Martinez (Interview 5) - "SAP is still affecting operations"
4. Linda Park (Interview 6) - "SAP is still causing stress"
5. David Foster (Interview 7) - Referenced SAP failures
6. Maria Santos (Interview 8) - "Two hours of SAP training for a system we use every day"
7. Tom Bradley (Interview 9) - "If they steamroll ahead? It'll be SAP 2.0. I don't know if this company can survive another SAP"
8. Tom Bradley (Interview 9) - "200-300 tickets/day during SAP, 10-15 pages/night, one person had breakdown"

**SAP Failure Facts**:
- Cost overrun: 3x budget ($10M vs. $3M)
- Training: 2 hours for system used daily
- Support chaos: 200-300 tickets/day (vs. normal 80-100)
- On-call: 10-15 pages/night (vs. normal 3-4)
- Psychological trauma: One support person had breakdown, called in sick for week
- Still impacting operations: Workarounds, slower processes
- Trust destroyed: Floor-IT relationship damaged
- Fear of repetition: "SAP 2.0" used as shorthand for disaster

**Implication**: 
- SAP is the dominant reference point for evaluating this initiative
- Every stakeholder measures this project against SAP
- "Prove this is different" is the underlying requirement
- Trauma must be acknowledged and addressed, not minimized
- Organization genuinely fears it cannot survive another SAP

**Theme Strength**: 🔴 CRITICAL - Shapes all stakeholder perspectives

---

### THEME 2: Trust Deficit Between IT and Floor

**Definition**: There is a fundamental trust breakdown between IT and floor operations, primarily caused by SAP but reinforced by ongoing support inadequacy.

**Mentioned by (7)**:
1. Robert Garcia (Interview 4) - "Trust is broken. They have to earn it back."
2. Jennifer Martinez (Interview 5) - "My floor workers don't trust IT anymore"
3. Maria Santos (Interview 8) - "Management makes changes without asking us"
4. Maria Santos (Interview 8) - Floor workers feel IT doesn't understand manufacturing
5. Tom Bradley (Interview 9) - Floor workers call support "people who don't understand manufacturing"
6. Tom Bradley (Interview 9) - Only 1 of 10 support staff has manufacturing background
7. Tom Bradley (Interview 9) - Support team heard about migration "third-hand" (not consulted)

**Evidence of Trust Deficit**:
- "Tech people don't understand floor reality" (Robert)
- IT seen as imposing solutions without understanding problems
- Floor workers feel disrespected and ignored
- Support seen as slow and unhelpful (especially 2nd/3rd shift)
- Previous initiatives made jobs harder, not easier
- Communication gap between IT and floor
- Only 1 person on 10-person support team has manufacturing background

**Implication**:
- Partnership approach required (not top-down implementation)
- Floor workers must be involved from day one
- IT must demonstrate understanding of floor reality
- Trust must be rebuilt through actions, not promises
- Support team must include manufacturing-experienced staff

**Theme Strength**: 🔴 CRITICAL - Determines adoption success/failure

---

### THEME 3: Timeline Reality vs. Leadership Goals

**Definition**: Significant gap between Michael's aggressive timeline and stakeholders' assessment of realistic timeline based on constraints.

**Mentioned by (7)**:
1. Michael Chen (Interview 1) - Wants 18 months
2. Sarah Kim (Interview 2) - "24-36 months more realistic, 8-12 months just for skills"
3. James Wilson (Interview 3) - Concerned about cash flow if too fast
4. Jennifer Martinez (Interview 5) - Timeline feels aggressive
5. Linda Park (Interview 6) - Training alone takes 6-12 months
6. David Foster (Interview 7) - Need 3-6 months for architecture/POC first
7. Tom Bradley (Interview 9) - "Support needs 12-18 months to prepare"

**Timeline Reality**:
- Michael wants: 18 months
- Minimum realistic: 36-60 months
- Breakdown:
  - Skills development: 8-12 months (IT team)
  - Architecture/POC: 3-6 months
  - Support preparation: 12-18 months
  - Training delivery: 6-12 months
  - Migration execution: 12-24 months (maintenance windows)
  - Parallel running: 6-12 months
- Mathematical constraint: Weekend-only maintenance windows
- Cannot compress without sacrificing quality

**Implication**:
- Timeline negotiation is critical early decision
- Rushing guarantees failure (SAP proved this)
- Must present mathematical proof of minimum timeline
- Leadership must accept reality vs. aspirational goals

**Theme Strength**: 🔴 CRITICAL - Physical constraints not negotiable

---

### THEME 4: MES as Mission-Critical System (Can't Fail)

**Definition**: MES (Manufacturing Execution System) is universally recognized as the highest-risk, most critical system. Failure is not acceptable.

**Mentioned by (7)**:
1. Robert Garcia (Interview 4) - "MES goes down = chaos, scrap, missed shipments"
2. Jennifer Martinez (Interview 5) - "MES touches every aspect of production"
3. Linda Park (Interview 6) - Referenced MES in operator training needs
4. David Foster (Interview 7) - "MES integration most complex, needs custom rearchitecture"
5. Maria Santos (Interview 8) - "MES runs my job - any issues = can't work"
6. Tom Bradley (Interview 9) - "MES migration terrifying - most problematic system"
7. Tom Bradley (Interview 9) - "30-35% of current tickets are MES-related"

**MES Critical Facts**:
- Touches every production workflow
- Zero tolerance for downtime
- Most problematic system to support (30-35% of tickets)
- Most complex integration architecture
- Operators cannot work if MES fails
- Custom components must be recreated
- Real-time requirements
- 2 AM failure = production chaos

**Implication**:
- MES should be separate sub-project
- Extensive validation required (6-12 months parallel)
- Floor worker testing before forced switch
- 24/7 support model essential
- Cannot rush MES migration
- Floor-level support needed during transition

**Theme Strength**: 🔴 CRITICAL - MES failure = production failure

---

### THEME 5: Skills Gap (Zero Cloud Experience)

**Definition**: IT and support teams have zero cloud experience, requiring significant time and investment for skills development.

**Mentioned by (5)**:
1. Sarah Kim (Interview 2) - "Team has zero cloud experience, need 8-12 months"
2. James Wilson (Interview 3) - Referenced skills gap concern
3. Linda Park (Interview 6) - IT training costs in $12-15M estimate
4. David Foster (Interview 7) - "Team not experienced enough for architecture"
5. Tom Bradley (Interview 9) - "Team has zero cloud skills, need 3-6 months Azure training"

**Skills Gap Reality**:
- IT team: Zero Azure/cloud experience
- Support team: Zero Azure/cloud experience
- Architecture: Insufficient experience for cloud-native design
- Timeline needed: 8-12 months for IT, 3-6 months for support
- Cost: Included in Linda's $12-15M training estimate
- Cannot learn while executing migration
- External expertise required

**Implication**:
- Skills development must precede migration
- 8-12 months training phase required
- External consulting for architecture
- Contractor augmentation during learning
- Cannot compress timeline for skills
- Support training must complete before migration starts

**Theme Strength**: 🟠 HIGH - Cannot execute what you don't understand

---

### THEME 6: Training Inadequacy Pattern

**Definition**: Historical pattern of inadequate training (particularly SAP), creating fear of repeated failure and necessitating comprehensive training approach.

**Mentioned by (6)**:
1. Robert Garcia (Interview 4) - "Training will be inadequate like SAP was"
2. Jennifer Martinez (Interview 5) - "Training must be comprehensive, not 2-hour sessions"
3. Linda Park (Interview 6) - "$12-15M for proper training" (vs. $50K estimate)
4. David Foster (Interview 7) - Referenced training needs
5. Maria Santos (Interview 8) - "Two hours of SAP training for system used daily"
6. Tom Bradley (Interview 9) - Echoed inadequate training concerns

**SAP Training Failure**:
- Duration: 2 hours total
- System usage: Daily, all day
- Result: Operators struggling, blamed for "not adapting"
- Perception: IT didn't care about floor success

**Proper Training Requirements**:
- IT team: 8-12 months Azure/cloud training
- Support team: 3-6 months Azure/cloud training
- Floor supervisors: 40-50 hours each
- Floor operators: 80-100 hours each
- Total cost: $12-15M realistic (vs. $50K estimate)
- Timeline: 6-12 months for delivery (sequential)
- Practice environments needed
- Ongoing support during adoption

**Implication**:
- Training must be comprehensive, not token
- Budget $12-15M minimum
- Allow 6-12 months for delivery
- Cannot train concurrently with migration
- Practice environments essential
- Manufacturing-experienced trainers required

**Theme Strength**: 🔴 CRITICAL - Training inadequacy = adoption failure

---

### THEME 7: "Tech People Don't Understand Manufacturing"

**Definition**: Recurring theme that IT/leadership doesn't understand floor reality, manufacturing constraints, or production pressures.

**Mentioned by (5)**:
1. Robert Garcia (Interview 4) - "Tech people don't understand what we deal with"
2. Jennifer Martinez (Interview 5) - Referenced gap between IT and operations
3. Maria Santos (Interview 8) - "Management doesn't understand what operators deal with"
4. Tom Bradley (Interview 9) - Only 1 of 10 support staff has manufacturing background
5. Tom Bradley (Interview 9) - Floor workers call support "people who don't understand manufacturing"

**Evidence**:
- IT designs solutions without floor input
- Support doesn't understand floor workflows
- Only 1 person on 10-person support team from manufacturing
- Michael from tech industry, not manufacturing
- David from tech industry, not manufacturing
- Previous tech initiatives made jobs harder
- 2 AM problems not same as office hour problems

**Michael Floor Shift Suggestion**:
- Suggested by 3 different stakeholders:
  - Robert (Interview 4): "Michael should work third shift for a week"
  - Maria (Interview 8): "Management should see what operators deal with"
  - Tom (Interview 9): "Second shift ideal - support challenges worst after 3 PM"
- Unanimous: Leadership needs floor reality experience
- Not about punishment - about understanding

**Implication**:
- Floor workers as domain experts (not just "users")
- Partnership approach essential
- Michael working floor shift recommended
- Support staff need manufacturing background
- IT must learn manufacturing reality
- Design WITH floor workers, not FOR them

**Theme Strength**: 🟠 HIGH - Determines trust and adoption

---

### THEME 8: Budget Reality Check (Massive Underestimation)

**Definition**: Michael's initial estimates are dramatically lower than realistic costs, requiring significant budget reality check.

**Mentioned by (4)**:
1. Michael Chen (Interview 1) - $3M estimate
2. James Wilson (Interview 3) - "$3M seems low for what you're describing"
3. Linda Park (Interview 6) - "$12-15M just for training" (vs. $50K)
4. Tom Bradley (Interview 9) - "$2-3M for support contractors" (not in budget)

**Budget Evolution**:
- Michael's initial: $3M
- After Sarah: $5-8M emerging
- After Linda: $16.5-23.5M realistic
- After Tom: $18.5-26.5M realistic
- **Final gap**: 6-8x initial estimate

**Breakdown of $18.5-26.5M**:
- Infrastructure/migration: $3-5M
- Validation environment: $1.5-2.5M
- Parallel running: $1-2M/year
- Retention bonuses: $500K
- IT contractors: $4-6M
- **Support contractors: $2-3M** (NEW from Interview 9)
- Training: $12-15M
- Hidden costs: $1-2M/year
- Contingency: $1.5-3M

**Implication**:
- Realistic budget discussion required immediately
- James (CFO) must evaluate ROI at real numbers
- Cash flow modeling at $18.5-26.5M, not $3M
- Michael's estimate was off by factor of 6-8x
- Cannot proceed without realistic budget commitment

**Theme Strength**: 🔴 CRITICAL - Financial feasibility depends on realistic budget

---

### THEME 9: 24/7 Manufacturing Reality

**Definition**: Manufacturing operates 24/7 across three shifts, but support and attention are primarily focused on first shift, leaving 2nd/3rd shift underserved.

**Mentioned by (5)**:
1. Robert Garcia (Interview 4) - "3rd shift always gets worst support, 2-3 AM issues wait"
2. Jennifer Martinez (Interview 5) - Need 24/7 support during transition
3. Maria Santos (Interview 8) - "Second shift - issues wait until morning"
4. Tom Bradley (Interview 9) - "Support challenges worst after 3 PM"
5. Tom Bradley (Interview 9) - "3-4 pages per night, every night"

**24/7 Reality**:
- 1st shift: 6 AM - 2 PM (best support coverage)
- 2nd shift: 2 PM - 10 PM (support thins out)
- 3rd shift: 10 PM - 6 AM (minimal support, "submit ticket and wait")
- Production: Continuous (no downtime tolerance)
- Support: Primarily day-shift focused
- On-call: Paged constantly (3-4 pages/night normal)

**Implication**:
- 24/7 support model required during transition
- Floor-level support for 2nd/3rd shift
- Cannot rely on "submit ticket" model
- Michael should experience 2nd shift (suggested by 3 stakeholders)
- Support contractors needed for adequate coverage
- Remote help desk breaks down for floor systems

**Theme Strength**: 🟠 HIGH - Manufacturing doesn't stop for support hours

---

### THEME 10: Maintenance Window Constraints

**Definition**: Weekend-only maintenance windows create physical constraint on migration timeline that cannot be negotiated away.

**Mentioned by (2)**:
1. David Foster (Interview 7) - "Weekend-only windows, mathematical constraint"
2. Implied by Robert - Production cannot stop during week

**Mathematical Reality**:
- Windows available: Friday night - Sunday (weekend only)
- Frequency: 4-5 per month
- Systems to migrate: ~50 (conservative)
- Rollback capability: Required (need 2 windows per system worst case)
- Total windows needed: 50-100
- 18 months = 78 weeks = 78 windows (insufficient)
- Realistic timeline: 36-60 months = 156-260 windows

**Implication**:
- Timeline is physically constrained
- Cannot compress below minimum
- Proves 18-month timeline impossible
- Must present mathematical proof to Michael
- Not negotiable - it's physics

**Theme Strength**: 🔴 CRITICAL - Physical constraint, not preference

---

### THEME 11: Parallel Running Necessity

**Definition**: Need to run old and new systems in parallel for extended period (6-12 months) for validation and rollback capability.

**Mentioned by (4)**:
1. James Wilson (Interview 3) - "Paying for both systems concern"
2. Jennifer Martinez (Interview 5) - "Need parallel running, 6-12 months"
3. David Foster (Interview 7) - "Validation environment and parallel running required"
4. Tom Bradley (Interview 9) - Implied by support model (supporting both old and new)

**Parallel Running Requirements**:
- Duration: 6-12 months minimum
- Cost: $1-2M/year (infrastructure, support, overhead)
- Purpose: Validation, rollback capability, gradual transition
- Support impact: Supporting TWO systems doubles load
- MES specifically: Extensive parallel needed (zero tolerance for failure)

**Implication**:
- Budget for 6-12 months parallel running
- Support contractors needed for dual system support
- Extended validation period for MES
- Cannot force-switch without parallel validation
- Adds $1-2M to budget

**Theme Strength**: 🟡 MODERATE - Required for safe migration

---

### THEME 12: Contractor Dependency

**Definition**: Project cannot succeed with internal team alone; significant contractor augmentation required across multiple areas.

**Mentioned by (5)**:
1. Sarah Kim (Interview 2) - "Need external consulting, not doing alone"
2. James Wilson (Interview 3) - Referenced contractor costs concern
3. Linda Park (Interview 6) - IT contractors in training cost model
4. David Foster (Interview 7) - "Need external architecture expertise"
5. Tom Bradley (Interview 9) - "$2-3M for support contractors" (4-6 people)

**Contractor Needs**:

**IT Contractors** ($4-6M):
- Architecture expertise
- Cloud migration specialists
- Integration specialists
- DevOps/automation experts
- Duration: 18-24 months

**Support Contractors** ($2-3M):
- Backfill during training: 2-3 people @ $300-450K
- Floor support during migration: 4-6 people @ $1.2-1.8M
- Manufacturing background preferred
- Duration: 18 months

**Training Contractors** (in $12-15M):
- Azure/cloud trainers for IT
- Manufacturing-experienced trainers for operators
- Curriculum development

**Total Contractor Costs**: $6-9M

**Implication**:
- Internal team insufficient for project
- Budget must include significant contractor costs
- Manufacturing-experienced contractors needed
- Contractor ramp-up time in schedule
- Quality/experience level matters

**Theme Strength**: 🟠 HIGH - Project size exceeds internal capacity

---

### THEME 13: Retention Risk (Key People Will Leave)

**Definition**: Significant risk that key institutional knowledge holders will leave if change is managed poorly.

**Mentioned by (3)**:
1. Sarah Kim (Interview 2) - Team already stretched, risk of burnout
2. Linda Park (Interview 6) - "People will leave if change managed poorly"
3. Tom Bradley (Interview 9) - 30% attrition in support team in 18 months (3 people)

**High-Risk Individuals**:
- Robert Garcia (22 years floor knowledge)
- Sarah Kim (12 years IT knowledge)
- Tom Bradley (6 years support knowledge)
- Jennifer Martinez (15 years operations knowledge)
- Experienced operators like Maria Santos
- Steve (only support person with manufacturing background)

**Support Team Attrition**:
- 3 people left in 18 months (30% turnover)
- Burnout-driven departures
- On-call burden (3-4 pages/night)
- Work-life balance destroyed

**Implication**:
- Retention strategy required ($500K budgeted)
- Address burnout BEFORE migration
- Career development opportunities
- Workload relief during transition
- Recognition and involvement
- If Robert or Sarah leave = project in jeopardy

**Theme Strength**: 🟠 HIGH - Losing key people = project failure

---

### THEME 14: Change Management as Discipline

**Definition**: Change management is a professional discipline requiring dedicated resources, not something done "on the side" by existing staff.

**Mentioned by (2)**:
1. Linda Park (Interview 6) - "Need proper change management team"
2. Jennifer Martinez (Interview 5) - Implied by floor involvement requirements

**Change Management Needs**:
- Dedicated change management team (can't be Linda's side job)
- Stakeholder engagement strategy
- Communication planning
- Training coordination
- Resistance management
- Culture transformation
- Cost: $300-500K estimated

**SAP Lesson**:
- Change management was absent or inadequate
- Top-down mandate created resistance
- Lack of floor involvement
- Result: Ongoing resistance and workarounds

**Implication**:
- Budget dedicated change management resources
- Cannot be "extra duty" for Linda or others
- Professional change management expertise needed
- Integration with training and support strategies

**Theme Strength**: 🟡 MODERATE - Professional discipline, not optional

---

### THEME 15: Union Implications

**Definition**: Floor operators are unionized, adding contractual and relationship dynamics to technology change.

**Mentioned by (2)**:
1. Linda Park (Interview 6) - "Operators are unionized, implications for change"
2. Implied by Robert/Maria comments about floor worker solidarity

**Union Considerations**:
- Job security concerns during major change
- Training requirements (adequate time, resources)
- Work rules and technology change
- Grievance potential if poorly managed
- Partnership approach needed (not adversarial)
- Union leadership engagement required

**Implication**:
- Engage union leadership early
- Partnership approach essential
- Adequate training commitment
- Job security addressed explicitly
- Cannot impose change without union buy-in

**Theme Strength**: 🟡 MODERATE - Legal/contractual considerations

---

### THEME 16: Support as Critical Success Factor (Not Afterthought)

**Definition**: Support isn't something to figure out after migration starts - it must be planned from day one and adequately resourced as a critical success factor.

**Mentioned by (3)**:
1. Tom Bradley (Interview 9) - "Support team needs to be at planning table, not hear third-hand"
2. Tom Bradley (Interview 9) - "Help desk model breaks down during major changes - need floor-level support"
3. Maria Santos (Interview 8) - "Support inadequate during SAP, especially 2nd shift"
4. Robert Garcia (Interview 4) - "3rd shift always gets worst support"

**Support as Success Factor**:
- Not an afterthought or "figure out later"
- Must be designed from project inception
- Floor-level support model needed (not remote help desk)
- All shifts coverage (especially 2nd/3rd)
- Manufacturing background on support team
- Adequate contractor budget ($2-3M)
- 6-12 month floor presence during MES transition

**Help Desk Model Breaks Down**:
- Remote support insufficient during major changes
- Operators learning new systems need immediate help
- 2 AM problems can't wait 30-60 minutes
- Floor systems (scanning, hardware) need physical presence
- Ticket volume doubles (80-100 → 150-200/day)
- Support team already at breaking point

**Support Team Crisis**:
- Current: 10 people (6 Level 1, 3 Level 2, 1 lead)
- Burned out: 3-4 pages/night, every night
- Attrition: 30% in 18 months (3 people left)
- Skills gap: Zero Azure/cloud experience
- Manufacturing gap: Only 1 of 10 has manufacturing background
- Not consulted: Heard about migration "third-hand"

**Implication**:
- Support must be at planning table from day one
- Design floor-level support model (not help desk only)
- Budget $2-3M for support contractors
- Address support team burnout BEFORE migration
- 3-6 months Azure/cloud training for support team
- Recruit contractors with manufacturing background
- Floor-level support for MES transition (6+ months)

**Theme Strength**: 🔴 CRITICAL - Inadequate support guarantees adoption failure

---

### THEME 17: Manufacturing Floor Experience Gap in IT

**Definition**: Most IT and support staff come from traditional IT backgrounds without manufacturing experience, creating a gap in understanding floor workflows and pressures.

**Mentioned by (3)**:
1. Tom Bradley (Interview 9) - "Only 1 of 10 support people has manufacturing background (Steve)"
2. Tom Bradley (Interview 9) - Floor workers call support "people who don't understand manufacturing"
3. Maria Santos (Interview 8) - "IT doesn't understand what we deal with on the floor"
4. Robert Garcia (Interview 4) - "Tech people don't understand floor reality"

**Experience Gap Evidence**:
- Support team: 9 of 10 from traditional IT, only Steve from manufacturing
- IT team: Primarily traditional enterprise IT backgrounds
- New leadership: Michael and David from tech industry (not manufacturing)
- Result: Solutions designed without understanding floor context

**Why This Matters**:
- Manufacturing workflows different from office IT
- Floor pressures not understood (production can't wait)
- 2 AM problems different from office-hour problems
- Equipment interdependencies not obvious to traditional IT
- Operator language and priorities different
- Real-time nature of manufacturing vs. batch processing mindset

**Impact on Support**:
- Friction between support and operators
- Longer resolution times (don't understand context)
- Trust deficit ("they don't get what we do")
- Support seen as unhelpful or slow

**Implication**:
- Recruit support contractors with manufacturing background
- Cross-train IT staff on manufacturing operations
- Michael working floor shift (understand reality)
- Value Steve's manufacturing background (only person who has it)
- Partner with floor workers (they're the manufacturing experts)
- Design solutions WITH floor input, not in isolation

**Theme Strength**: 🟠 HIGH - Understanding gap creates friction and trust issues

---

### THEME 18: On-Call Brutality and Burnout

**Definition**: IT and support staff are subjected to brutal on-call schedules with frequent nighttime pages, causing burnout and attrition.

**Mentioned by (3)**:
1. Tom Bradley (Interview 9) - "3-4 pages per night, every night during on-call week"
2. Tom Bradley (Interview 9) - "SAP was 10-15 pages/night, one person had breakdown"
3. Tom Bradley (Interview 9) - "30% attrition in 18 months, people getting 2-3 hours sleep on-call weeks"
4. Sarah Kim (Interview 2) - "Current systems page us constantly" / "Reduced on-call burden" in success vision

**On-Call Reality**:
- **Normal on-call**: 3-4 pages per night
- **SAP on-call**: 10-15 pages per night (crisis period)
- **Rotation**: 1 week on-call every 5 weeks
- **Sleep**: 2-3 hours during on-call weeks
- **Impact**: People getting sick, burned out, quitting

**SAP Support Nightmare**:
- 200-300 tickets/day (vs. normal 80-100)
- 10-15 pages/night (vs. normal 3-4)
- One person had breakdown, called in sick for week
- Team traumatized by experience

**Burnout Consequences**:
- 30% attrition in 18 months (3 people left)
- Morale low across support team
- "Running on fumes" (Tom's words)
- Work-life balance destroyed
- Career sustainability questioned

**Migration Will Make Worse**:
- Ticket volume doubles during migration (150-200/day)
- Supporting both old and new systems
- On-call burden will increase
- Already burned-out team facing more pressure

**Implication**:
- Address burnout BEFORE migration starts
- Support contractors to reduce on-call burden
- Improve system reliability (reduce pages)
- Sustainable on-call rotation
- Mental health support
- Retention at risk if not addressed
- Success vision includes "reduced on-call burden"

**Theme Strength**: 🔴 CRITICAL - Burnout causing attrition, will worsen during migration

---

## Theme Category Analysis

### Trust and Relationship Themes (4)
- THEME 2: Trust Deficit Between IT and Floor
- THEME 7: "Tech People Don't Understand Manufacturing"
- THEME 17: Manufacturing Floor Experience Gap in IT
- THEME 18: On-Call Brutality and Burnout (contributes to trust deficit)

**Pattern**: Fundamental relationship problems between IT and floor operations

### Resource Reality Themes (5)
- THEME 5: Skills Gap (Zero Cloud Experience)
- THEME 8: Budget Reality Check (Massive Underestimation)
- THEME 12: Contractor Dependency
- THEME 13: Retention Risk
- THEME 16: Support as Critical Success Factor

**Pattern**: Significant gap between assumed resources and actual needs

### Timeline and Constraints Themes (3)
- THEME 3: Timeline Reality vs. Leadership Goals
- THEME 9: 24/7 Manufacturing Reality
- THEME 10: Maintenance Window Constraints

**Pattern**: Physical and operational constraints that cannot be negotiated away

### Quality and Preparation Themes (3)
- THEME 6: Training Inadequacy Pattern
- THEME 11: Parallel Running Necessity
- THEME 14: Change Management as Discipline

**Pattern**: Proper preparation requires time and resources

### Risk and Failure Themes (3)
- THEME 1: SAP Trauma and "Never Again"
- THEME 4: MES as Mission-Critical System
- THEME 15: Union Implications

**Pattern**: High stakes and low tolerance for failure

---

## Cross-Cutting Analysis

### Themes Mentioned by 5+ Stakeholders (Strongest)
1. SAP Trauma (8 mentions) - Universal reference point
2. Trust Deficit (7 mentions) - Pervasive relationship problem
3. Timeline Reality (7 mentions) - Universal concern
4. MES Critical (7 mentions) - Highest risk system
5. Training Inadequacy (6 mentions) - Historical pattern
6. Support Adequacy (6 mentions) - Critical success factor

### Themes Mentioned by 3-4 Stakeholders
1. Tech People Don't Understand Manufacturing (5 mentions)
2. Budget Reality Check (4 mentions)
3. Skills Gap (5 mentions)
4. 24/7 Manufacturing Reality (5 mentions)
5. Contractor Dependency (5 mentions)
6. Parallel Running (4 mentions)
7. Support as Critical Success Factor (3 mentions)
8. Manufacturing Floor Experience Gap (3 mentions)
9. On-Call Brutality and Burnout (3 mentions)

### Emerging Themes (1-2 mentions)
1. Retention Risk (3 mentions)
2. Change Management (2 mentions)
3. Union Implications (2 mentions)
4. Maintenance Windows (2 mentions)

---

## Key Insights

### 1. SAP Dominates Everything
Every stakeholder measures this initiative against SAP failure. It's the lens through which all decisions are evaluated. Must acknowledge and address explicitly.

### 2. Trust Is Fundamental
Cannot succeed without rebuilding trust between IT and floor. Partnership approach required. Michael working floor shift recommended by 3 stakeholders.

### 3. Resource Gap Is Massive
Skills, budget, contractors, support staff - every resource dimension is significantly underestimated. $3M → $18.5-26.5M, 18 months → 36-60 months.

### 4. Support Cannot Be Afterthought
Support team already burned out. Migration will double ticket volume. Floor-level support model needed. $2-3M contractors not budgeted. Must address support as critical success factor from day one.

### 5. Manufacturing Floor Experience Matters
Only 1 of 10 support staff has manufacturing background. IT doesn't understand floor reality. Gap creates friction and trust deficit. Need manufacturing-experienced contractors and IT cross-training.

### 6. On-Call Burden Causing Attrition
3-4 pages every night, 30% attrition in 18 months, people burned out. Migration will make worse. Must address burnout BEFORE migration starts.

### 7. MES Is Different
Every stakeholder identifies MES as highest risk. Should be separate sub-project with extensive validation. Floor-level support essential.

### 8. Timeline Is Constrained
Not aspirational - physically constrained by maintenance windows, skills development time, training delivery. Mathematical proof shows 36-60 months minimum.

---

## Recommendations

### Immediate Actions
1. **Acknowledge SAP explicitly** - Don't minimize past trauma
2. **Trust rebuilding initiative** - Partnership approach, floor involvement
3. **Support adequacy planning** - Engage Tom immediately, design floor-level model
4. **Budget reality session** - Present $18.5-26.5M realistic estimate
5. **Timeline reality session** - Present mathematical proof of 36-60 months
6. **Address support burnout** - Cannot start migration with burned-out team

### Strategic Approaches
1. **Floor workers as experts** - Partner WITH them, not impose ON them
2. **MES as sub-project** - Separate strategy for highest-risk system
3. **Skills development first** - 8-12 months before migration execution
4. **Support model design** - Floor-level, all shifts, adequate contractors
5. **Michael floor experience** - 2nd shift week to understand reality
6. **Manufacturing-experienced contractors** - Support and training roles

---

**Document Status**: Artifact updated through Interview 9 (Tom Bradley)  
**Next Update**: After Interviews 10-11 complete