# Open Questions - Azure Cloud Modernization Project

**Project**: Precision Manufacturing Inc. - Azure Cloud Migration  
**Document Version**: 1.9  
**Last Updated**: 2025-11-05  
**Interview Progress**: 9 of 11 complete (82%)

---

## Executive Summary

**Total Questions**: 48  
**Answered**: 31 (65%)  
**Remaining**: 17 (35%)

**Questions by Priority**:
- 🔴 CRITICAL: 8 remaining
- 🟠 HIGH: 6 remaining
- 🟡 MODERATE: 3 remaining

**Questions by Stakeholder**:
- For Michael: 3
- For IT Manager (Interview 10): 5
- For HR Director (Interview 11): 6
- For Investigation: 3

---

## Questions Answered by Interview 9 (Tom Bradley)

### ✅ ANSWERED: Support Team Capacity and Readiness

**Q1**: What is the support team's capacity and burnout level?  
**Answer**: Support team already at breaking point:
- 10 people (6 Level 1, 3 Level 2, 1 lead)
- 3-4 pages per night, every night
- 30% attrition in 18 months (3 people left)
- 80-100 tickets/day currently, will be 150-200 during migration
- Morale low, team "running on fumes"

**Q2**: What support model is needed during migration?  
**Answer**: Help desk model breaks down during major changes:
- Need floor-level support (ON THE FLOOR, not remote)
- All shifts coverage (especially 2nd/3rd)
- 6+ months duration during MES transition
- Manufacturing background needed (most support staff are traditional IT)
- $2-3M for support contractors ($300-450K backfill + $1.2-1.8M floor support)

**Q3**: What are support team's cloud/Azure skills?  
**Answer**: Zero Azure/cloud skills, need 3-6 months training before migration starts

**Q4**: What is MES support complexity?  
**Answer**: MES is most problematic system to support:
- 30-35% of current tickets are MES-related
- Resolution times: 15 minutes to 6 hours
- System freezes, slow performance, login issues, scanner failures
- Floor operators cannot work when MES has issues

**Q5**: How does support team feel about migration?  
**Answer**: Concerned but willing if done properly:
- Not consulted yet (heard "third-hand")
- Fears "SAP 2.0" (200-300 tickets/day, 10-15 pages/night during SAP)
- One person had breakdown during SAP support chaos
- Will support if: adequate resources, realistic timeline, proper training, burnout addressed

**Q6**: What was SAP support experience?  
**Answer**: Traumatic:
- 200-300 tickets/day (vs. normal 80-100)
- 10-15 pages/night (vs. normal 3-4)
- One person had breakdown, called in sick for week
- Team still references SAP as nightmare

**Q7**: What is support contractor budget need?  
**Answer**: $2-3M total:
- Backfill contractors: 2-3 people @ $150-225K/year = $300-450K
- Migration floor support: 4-6 people @ $200-300K for 18 months = $1.2-1.8M

**Q8**: Does support team have manufacturing background?  
**Answer**: Only 1 of 10 (Steve, Level 2 tech):
- Rest from traditional IT backgrounds
- Don't understand floor workflows
- Creates friction with operators
- Need contractors with manufacturing background

---

## Critical Questions Remaining (8)

### 🔴 FOR MICHAEL (Post-Interviews)

**Q9**: Will you commit to realistic timeline (36-60 months) based on mathematical proof?  
**Why Critical**: Current 18-month goal is mathematically impossible  
**Impact**: Timeline drives all other planning  
**Source**: Contradicts maintenance window constraints, skills development time, training delivery time

**Q10**: Will you commit to realistic budget ($18.5-26.5M) vs. initial $3M estimate?  
**Why Critical**: Cannot plan without budget reality  
**Impact**: Financial feasibility depends on realistic budget  
**Source**: Linda's training costs ($12-15M), Tom's support costs ($2-3M), David's architecture costs

**Q11**: Will you work 2nd shift for a week to understand floor reality?  
**Why Critical**: Suggested by 3 different stakeholders (Robert, Maria, Tom)  
**Impact**: Demonstrates commitment to understanding floor perspective  
**Source**: Consistent theme across interviews 4, 8, 9

---

### 🔴 FOR IT MANAGER (Interview 10)

**Q12**: What is overall IT team morale and retention risk?  
**Why Critical**: Tom revealed 30% support attrition; need to understand if this is broader pattern  
**Impact**: Retention risk could derail project  
**Follow-up from**: Tom's interview revealed support team crisis

**Q13**: How many IT staff are at flight risk if migration proceeds with current plan?  
**Why Critical**: Losing key people = project failure  
**Impact**: Need retention strategy  
**Follow-up from**: Linda's retention concern, Tom's attrition data

**Q14**: What is infrastructure team's view of timeline?  
**Why Critical**: Need to validate David's assessment  
**Impact**: Timeline feasibility  
**Follow-up from**: David's 24-36 month minimum, maintenance windows

**Q15**: What are maintenance window realities (frequency, duration, constraints)?  
**Why Critical**: Mathematical proof of timeline depends on accurate window data  
**Impact**: Physical constraint on timeline  
**Follow-up from**: David's weekend-only constraint

**Q16**: How does IT team capacity/workload compare to support team?  
**Why Critical**: Support team burned out; is IT team also at breaking point?  
**Impact**: Team capacity assessment  
**Follow-up from**: Tom revealed support team crisis

---

### 🔴 FOR HR DIRECTOR (Interview 11)

**Q17**: What is realistic cost and timeline to hire 4-6 new support staff?  
**Why Critical**: Support team inadequate for migration  
**Impact**: Support adequacy timeline  
**Follow-up from**: Tom identified need for 4-6 more support staff

**Q18**: How long to recruit support people with manufacturing background?  
**Why Critical**: Only 1 of 10 support staff has manufacturing background  
**Impact**: Support quality and floor trust  
**Follow-up from**: Tom revealed manufacturing experience gap

---

### 🔴 FOR INVESTIGATION

**Q19**: What is support contractor sourcing strategy for manufacturing-experienced people?  
**Why Critical**: Need $2-3M in contractors with manufacturing background  
**Impact**: Support model success  
**Follow-up from**: Tom's contractor needs and manufacturing background requirement

**Q20**: What is detailed support model design for floor-level presence?  
**Why Critical**: Help desk model inadequate; need floor-level support designed  
**Impact**: Adoption success depends on adequate support  
**Follow-up from**: Tom's feedback that help desk breaks down during major changes

---

## High Priority Questions Remaining (6)

### 🟠 FOR IT MANAGER (Interview 10)

**Q21**: What lessons from SAP should inform this project?  
**Why High**: SAP trauma shapes all stakeholder responses  
**Impact**: Avoid repeating mistakes  
**Source**: Every stakeholder references SAP

**Q22**: What is realistic infrastructure readiness timeline?  
**Why High**: David identified network upgrades needed  
**Impact**: Prerequisites for migration  
**Source**: David's $500K-1M network upgrade estimate

---

### 🟠 FOR HR DIRECTOR (Interview 11)

**Q23**: What is retention strategy to prevent support team attrition?  
**Why High**: 30% attrition in 18 months indicates crisis  
**Impact**: Support team stability during migration  
**Follow-up from**: Tom revealed support team burnout and attrition

**Q24**: How to address support team burnout before migration starts?  
**Why High**: Cannot start migration with burned-out team  
**Impact**: Project timing and team health  
**Follow-up from**: Tom's "running on fumes" assessment

**Q25**: What is manufacturing-experienced trainer sourcing strategy?  
**Why High**: Linda estimated 80-100 hours per operator training  
**Impact**: Training quality and credibility  
**Source**: Linda's training cost breakdown, Tom's manufacturing background importance

**Q26**: What is change management team composition and budget?  
**Why High**: Linda said she cannot do this alone  
**Impact**: Change management adequacy  
**Source**: Linda's requirement for proper change management resources

---

## Moderate Priority Questions Remaining (3)

### 🟡 FOR HR DIRECTOR (Interview 11)

**Q27**: What are union partnership strategies for technology change?  
**Why Moderate**: Operators are unionized, need partnership approach  
**Impact**: Floor worker cooperation  
**Source**: Linda mentioned union implications

**Q28**: What is detailed breakdown of $12-15M training costs?  
**Why Moderate**: Need to validate Linda's estimate with detailed plan  
**Impact**: Budget accuracy  
**Source**: Linda's $12-15M training estimate

**Q29**: What are career development opportunities to support retention?  
**Why Moderate**: Part of retention strategy  
**Impact**: Long-term retention  
**Source**: Linda's retention recommendations

---

## Questions Fully Answered (31)

### Timeline and Planning (Answered)

✅ **Q**: Is 18-month timeline realistic?  
**A**: No. 24-36 months minimum (Sarah, David), 36-60 months with all constraints (mathematical proof)

✅ **Q**: How long for skills development?  
**A**: 8-12 months for IT team (Sarah), 3-6 months for support team (Tom)

✅ **Q**: Is there time for architecture/POC phase?  
**A**: Need 3-6 months before migration (David)

✅ **Q**: What are maintenance window constraints?  
**A**: Weekend-only, mathematical constraint proves 36-60 months minimum (David)

✅ **Q**: How long for training delivery?  
**A**: 6-12 months minimum, cannot be concurrent with migration (Linda)

✅ **Q**: How long does support team need to prepare?  
**A**: 12-18 months minimum (Tom)

### Budget and Costs (Answered)

✅ **Q**: Is $3M budget realistic?  
**A**: No. $18.5-26.5M realistic (evolution from $3M → $16.5-23.5M → $18.5-26.5M)

✅ **Q**: What is realistic training cost?  
**A**: $12-15M (vs. Michael's $50K estimate) - Linda

✅ **Q**: What is validation environment cost?  
**A**: $1.5-2.5M (David)

✅ **Q**: What is network infrastructure cost?  
**A**: $500K-1M (David)

✅ **Q**: What is IT contractor cost?  
**A**: $4-6M (Linda, David, Sarah)

✅ **Q**: What is support contractor cost?  
**A**: $2-3M (Tom) - $300-450K backfill + $1.2-1.8M floor support

✅ **Q**: What is parallel running cost?  
**A**: $1-2M/year for 6-12 months (James, David)

✅ **Q**: What is retention bonus budget?  
**A**: $500K recommended (Linda)

### Team and Skills (Answered)

✅ **Q**: Does IT team have cloud skills?  
**A**: Zero cloud experience (Sarah)

✅ **Q**: Does support team have cloud skills?  
**A**: Zero Azure/cloud experience (Tom)

✅ **Q**: Is team capacity adequate?  
**A**: No. Team already stretched thin (Sarah), support team burned out (Tom)

✅ **Q**: Is external expertise needed?  
**A**: Yes. Architecture, migration specialists, support contractors (Sarah, David, Tom)

✅ **Q**: How many support staff with manufacturing background?  
**A**: Only 1 of 10 (Steve) - Tom

### Trust and SAP (Answered)

✅ **Q**: What is trust state between IT and floor?  
**A**: Trust is broken, must be rebuilt (Robert, Jennifer, Maria, Tom)

✅ **Q**: What are SAP lessons learned?  
**A**: Multiple failures documented - training inadequate, support overwhelmed, trust destroyed, trauma persists

✅ **Q**: What was SAP support experience?  
**A**: 200-300 tickets/day, 10-15 pages/night, one person had breakdown (Tom)

✅ **Q**: How does SAP still affect operations?  
**A**: Workarounds, slower processes, ongoing pain (Jennifer, Robert)

### MES and Critical Systems (Answered)

✅ **Q**: Why is MES so critical?  
**A**: Touches all production, zero tolerance for failure, operators cannot work if down (Robert, Jennifer, Maria, Tom)

✅ **Q**: What is MES complexity?  
**A**: Most complex integration, needs custom rearchitecture, most problematic to support (David, Tom)

✅ **Q**: What is MES support burden?  
**A**: 30-35% of current tickets, resolution 15 min to 6 hours (Tom)

### Support and Operations (Answered)

✅ **Q**: What is support team capacity?  
**A**: 10 people, already burned out, 30% attrition (Tom)

✅ **Q**: What is ticket volume during migration?  
**A**: Will double from 80-100/day to 150-200/day (Tom)

✅ **Q**: What support model is needed?  
**A**: Floor-level support (not help desk), all shifts, 6+ months (Tom)

✅ **Q**: What is on-call burden?  
**A**: 3-4 pages/night normally, 10-15 during SAP, 1 week per 5 weeks rotation (Tom)

✅ **Q**: What is floor support adequacy?  
**A**: 2nd/3rd shift underserved, issues wait until morning (Robert, Maria, Tom)

---

## Question Status by Stakeholder

### Michael Chen (CEO) - 3 critical questions remaining
- Timeline commitment to 36-60 months?
- Budget commitment to $18.5-26.5M?
- Will work floor shift?

### Sarah Kim (IT Director) - All questions answered ✅
- Team capacity, skills, timeline, contractor needs all addressed

### James Wilson (CFO) - All questions answered ✅
- Cost concerns, ROI, cash flow all addressed

### Robert Garcia (Floor Supervisor) - All questions answered ✅
- Trust, MES concerns, training needs, floor reality all addressed

### Jennifer Martinez (VP Operations) - All questions answered ✅
- Floor involvement, MES criticality, support needs all addressed

### Linda Park (HR Director) - All questions answered ✅
- Training costs, retention, change management all addressed

### David Foster (CTO) - All questions answered ✅
- Architecture, complexity, validation, timeline all addressed

### Maria Santos (Floor Operator) - All questions answered ✅
- Operator perspective, training, support, trust all addressed

### Tom Bradley (Support Lead) - All questions answered ✅
- Support capacity, burnout, costs, model, skills all addressed

### IT Manager (Interview 10) - 5 questions pending
- Team morale and retention risk
- Flight risk assessment
- Infrastructure timeline view
- Maintenance window details
- Team capacity vs. support team

### HR Director (Interview 11) - 6 questions pending
- Support staff hiring (cost, timeline, manufacturing background)
- Support team burnout and retention strategy
- Manufacturing trainer sourcing
- Change management team composition
- Union partnership strategies
- Training cost breakdown validation
- Career development opportunities

---

## Question Resolution Priority

### Before Proceeding with Project (CRITICAL - 8 questions)
1. Michael timeline commitment (36-60 months)
2. Michael budget commitment ($18.5-26.5M)
3. Michael floor shift commitment
4. IT team morale and retention (Interview 10)
5. IT staff flight risk assessment (Interview 10)
6. Support staff hiring plan (Interview 11)
7. Manufacturing background recruitment (Interview 11)
8. Support contractor sourcing strategy

### During Phase 1 Planning (HIGH - 6 questions)
1. Infrastructure timeline (Interview 10)
2. Maintenance window validation (Interview 10)
3. IT team capacity assessment (Interview 10)
4. Support burnout mitigation (Interview 11)
5. Manufacturing trainer sourcing (Interview 11)
6. Change management team (Interview 11)

### During Detailed Planning (MODERATE - 3 questions)
1. Union partnership strategy (Interview 11)
2. Training cost validation (Interview 11)
3. Career development plan (Interview 11)

---

## Emerging Questions from Patterns

### From Support Team Crisis (Tom - Interview 9)

**NEW Q30**: What is succession plan if Steve (only manufacturing-experienced support person) leaves?  
**Why Important**: Critical knowledge walking out door  
**Impact**: Support capability for manufacturing systems  
**Priority**: 🟠 HIGH

**NEW Q31**: What is mental health support for support team?  
**Why Important**: 30% attrition, burnout, one person had breakdown during SAP  
**Impact**: Team health and retention  
**Priority**: 🟡 MODERATE

**NEW Q32**: What is realistic support team size for supporting migration + operations?  
**Why Important**: 10 people inadequate, need 4-6 more per Tom  
**Impact**: Support adequacy  
**Priority**: 🔴 CRITICAL - for Interview 11

### From Manufacturing Background Gap (Tom - Interview 9)

**NEW Q33**: What is cross-training plan for IT staff on manufacturing operations?  
**Why Important**: Only 1 of 10 support staff understand manufacturing  
**Impact**: IT-floor relationship and support quality  
**Priority**: 🟠 HIGH

**NEW Q34**: What is manufacturing background requirement for contractor roles?  
**Why Important**: Need to specify in contractor sourcing  
**Impact**: Contractor effectiveness  
**Priority**: 🟠 HIGH

---

## Questions by Interview Source

### Interview 10 (IT Manager) - Target Questions
1. 🔴 Overall IT team morale and retention risk
2. 🔴 How many staff at flight risk
3. 🔴 Infrastructure timeline view
4. 🔴 Maintenance window validation
5. 🔴 IT team capacity vs. support team
6. 🟠 SAP lessons learned details
7. 🟠 Infrastructure readiness timeline
8. 🟠 Cross-training plan for manufacturing operations

### Interview 11 (HR Director) - Target Questions
1. 🔴 Support staff hiring (cost, timeline)
2. 🔴 Manufacturing background recruitment strategy
3. 🔴 Realistic support team size
4. 🟠 Support burnout mitigation
5. 🟠 Support retention strategy
6. 🟠 Manufacturing trainer sourcing
7. 🟠 Change management team composition
8. 🟡 Union partnership strategies
9. 🟡 Training cost validation
10. 🟡 Career development opportunities
11. 🟡 Mental health support for teams

### For Michael (Post-Interviews)
1. 🔴 Timeline commitment (36-60 months)
2. 🔴 Budget commitment ($18.5-26.5M)
3. 🔴 Floor shift commitment

### For Investigation Team
1. 🔴 Support contractor sourcing (manufacturing background)
2. 🔴 Floor-level support model design
3. 🟠 Manufacturing background requirements for contractors
4. 🟠 Succession planning (Steve and other key people)

---

## Key Insights from Question Evolution

### Pattern 1: Questions Get More Specific
- Started: "Is timeline realistic?"
- Now: "Will you commit to 36-60 months based on mathematical proof?"

### Pattern 2: Hidden Costs Keep Emerging
- $3M → $16.5-23.5M → $18.5-26.5M
- Each interview reveals new cost categories
- Support contractors ($2-3M) latest discovery

### Pattern 3: People Issues Dominate
- Technical questions answerable
- People, trust, capacity questions most critical
- Support team crisis major revelation in Interview 9

### Pattern 4: Support Emerged as Critical Theme
- Wasn't primary concern in early interviews
- Tom's interview revealed support as existential risk
- Help desk model assumption fundamentally wrong

### Pattern 5: Manufacturing Background Gap
- Only emerged in Interview 9 (Tom)
- Only 1 of 10 support staff from manufacturing
- Creates friction, trust issues, support quality problems

---

## Recommendations

### Before Interview 10
1. Review maintenance window constraints with Alex (IT Manager)
2. Validate David's technical assessments
3. Assess broader IT team morale beyond support

### Before Interview 11
1. Prepare detailed questions on support hiring and retention
2. Explore manufacturing background recruitment strategies
3. Validate Linda's $12-15M training estimate with detailed breakdown

### After All Interviews
1. Synthesize all answers into comprehensive findings
2. Present reality check to Michael (timeline, budget, conditions)
3. Develop detailed planning approach based on answers
4. Create stakeholder engagement strategy

---

## Success Criteria

**Question Resolution Target**: 
- All critical questions answered before project decision
- All high questions answered during Phase 1 planning
- All moderate questions answered during detailed planning

**Current Status**: 31 of 48 answered (65%), 17 remaining (35%)

**After Interviews 10-11**: Expect 90-95% answered, ready for Phase 0 synthesis

---

**Document Status**: Artifact updated through Interview 9 (Tom Bradley)  
**Next Update**: After Interviews 10-11 complete