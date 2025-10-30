# Risk Register

**Project Name**: [Project name from constitution]  
**Date Created**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Version**: [v1.0, v2.0, etc.]  
**Owner**: [Project Manager name]  
**Status**: [Active | Monitoring | Closed]

---

## Purpose of This Document

This Risk Register is the **central repository for all project risks**, their assessments, mitigation strategies, and ongoing status tracking. It is a living document that must be updated continuously throughout the project lifecycle.

**What This Document Contains**:
- Complete inventory of all identified project risks
- Risk assessment scores (probability, impact, severity)
- Detailed mitigation and contingency plans
- Risk ownership and accountability
- Monitoring and escalation procedures
- Risk budget and schedule impact tracking

**What This Document Does NOT Contain**:
- Project plan details (see sprint-plan.md)
- Technical architecture (see architecture.md)
- Detailed task breakdown (see task-breakdown.md)

**Who Uses This Document**:
- Project Manager: Overall risk management
- Technical Leads: Technical risk ownership
- Development Team: Awareness and mitigation execution
- Stakeholders: Risk transparency and decision-making
- Executive Sponsor: Strategic risk oversight

**Update Frequency**:
- Daily: During Sprint 0 and high-risk periods
- Weekly: During normal development (weekly risk review)
- Sprint Retrospectives: Comprehensive review and lessons learned
- Monthly: Strategic risk review with stakeholders

---

## Executive Summary

**Overall Project Risk Level**: [CRITICAL | HIGH | MEDIUM | LOW]

**Total Risks Identified**: [Number]
- 🔴 Critical (20-25): [Count] - IMMEDIATE ACTION REQUIRED
- 🟠 High (12-19): [Count] - Action required this sprint
- 🟡 Medium (6-11): [Count] - Monitor and plan mitigation
- 🟢 Low (3-5): [Count] - Accept or monitor
- ⚪ Very Low (1-2): [Count] - Accept

**Risk Trend**: [Increasing | Stable | Decreasing]

**Top 3 Risks**:
1. [RISK-XXX]: [Risk title] - Score [X] - Status: [Status]
2. [RISK-XXX]: [Risk title] - Score [X] - Status: [Status]
3. [RISK-XXX]: [Risk title] - Score [X] - Status: [Status]

**Risk Mitigation Status**:
- Mitigation plans in place: [X] of [Y] high risks
- Mitigation tasks completed: [X] of [Y] tasks
- Contingency budget allocated: $[Amount]
- Schedule buffer allocated: [X]% / [X] days

**Key Concerns**:
[1-2 sentence summary of biggest concerns right now]

**Last Review Date**: [YYYY-MM-DD]  
**Next Review Date**: [YYYY-MM-DD]

---

## Risk Assessment Scale

### Probability Scale

| Score | Level | Description | Criteria |
|-------|-------|-------------|----------|
| 5 | Very High | >75% probability | Almost certain; multiple indicators; occurred on similar projects |
| 4 | High | 50-75% probability | Likely; several indicators; occurred on some similar projects |
| 3 | Medium | 25-50% probability | May or may not occur; some indicators present |
| 2 | Low | 10-25% probability | Unlikely but possible; few indicators present |
| 1 | Very Low | <10% probability | Very unlikely; no clear indicators |

### Impact Scale

| Score | Level | Description | Schedule Impact | Budget Impact | Other Impact |
|-------|-------|-------------|-----------------|---------------|--------------|
| 5 | Critical | Catastrophic | >4 weeks delay | >50% overrun | Project failure, data loss, security breach |
| 4 | High | Severe | 2-4 weeks delay | 25-50% overrun | Major features cut, significant rework |
| 3 | Medium | Moderate | 1-2 weeks delay | 10-25% overrun | Minor features cut, some rework |
| 2 | Low | Minor | <1 week delay | <10% overrun | Minimal rework, minor inconvenience |
| 1 | Very Low | Negligible | No delay | No impact | Easily worked around |

### Risk Severity Calculation

**Risk Score = Probability × Impact**

| Score Range | Severity Level | Color | Response Required |
|-------------|----------------|-------|-------------------|
| 20-25 | Critical | 🔴 Red | Immediate executive attention and action |
| 12-19 | High | 🟠 Orange | Immediate action required this sprint |
| 6-11 | Medium | 🟡 Yellow | Monitor closely and plan mitigation |
| 3-5 | Low | 🟢 Green | Accept or monitor |
| 1-2 | Very Low | ⚪ White | Accept |

---

## Critical Risks (Score 20-25)

> 🔴 **CRITICAL PRIORITY**: These risks require immediate executive attention and action

### RISK-C001: [Risk Title]

**Status**: [🔴 Active | 🟡 Monitoring | 🟢 Mitigated | ⚫ Closed]  
**Current Score**: [Probability × Impact = Score]  
**Target Score**: [After mitigation]  
**Date Identified**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Owner**: [Name/Role]  
**Review Frequency**: [Daily | Weekly]

#### Risk Details

**Description**:  
[Clear, detailed description of the risk in 2-3 sentences. What could go wrong?]

**Category**: [Technical | Schedule | Resource | Business | Quality]

**Trigger Conditions**:  
[What events or situations would cause this risk to materialize?]
- Trigger 1: [Specific event or condition]
- Trigger 2: [Specific event or condition]
- Trigger 3: [Specific event or condition]

**Impact if Occurs**:  
[Detailed description of consequences if this risk materializes]
- **Schedule Impact**: [Specific delay estimate]
- **Budget Impact**: [Specific cost estimate]
- **Quality Impact**: [How quality would be affected]
- **Business Impact**: [Customer/business consequences]
- **Team Impact**: [Effect on team morale/capacity]

#### Risk Assessment

**Probability Assessment**: [1-5] - [Very Low | Low | Medium | High | Very High]

**Probability Rationale**:  
[Why did you assign this probability score? What evidence or indicators?]

**Impact Assessment**: [1-5] - [Very Low | Low | Medium | High | Critical]

**Impact Rationale**:  
[Why did you assign this impact score? What would be affected?]

**Risk Score**: [Probability] × [Impact] = **[Total Score]** (🔴 Critical)

#### Mitigation Strategy

**Strategy Type**: [Avoid | Mitigate | Transfer | Accept]

**Primary Mitigation Actions**:

**Action 1**: [Specific mitigation action]
- **Owner**: [Name]
- **Timeline**: [Start date - End date]
- **Cost**: [Time/money required]
- **Status**: [Not Started | In Progress | Complete]
- **Expected Impact**: [How much this reduces probability or impact]

**Action 2**: [Specific mitigation action]
- **Owner**: [Name]
- **Timeline**: [Start date - End date]
- **Cost**: [Time/money required]
- **Status**: [Not Started | In Progress | Complete]
- **Expected Impact**: [How much this reduces probability or impact]

**Action 3**: [Specific mitigation action]
- **Owner**: [Name]
- **Timeline**: [Start date - End date]
- **Cost**: [Time/money required]
- **Status**: [Not Started | In Progress | Complete]
- **Expected Impact**: [How much this reduces probability or impact]

**Total Mitigation Cost**: [Time and money across all actions]

#### Contingency Plan

**If Risk Occurs, We Will**:
1. [Immediate response action 1]
2. [Immediate response action 2]
3. [Immediate response action 3]

**Contingency Resources**:
- **Budget**: $[Amount reserved for this contingency]
- **Time**: [Days/weeks in schedule buffer]
- **People**: [Who would be pulled in to help]

**Escalation Path**:
- **Level 1**: [Team handles] - Try contingency actions 1-3
- **Level 2**: [PM escalates to] [Role] - If actions 1-3 don't work
- **Level 3**: [Executive escalation to] [Role] - If major project impact

#### Residual Risk

**Residual Probability**: [1-5] - [After mitigation is complete]  
**Residual Impact**: [1-5] - [After mitigation is complete]  
**Residual Risk Score**: [Probability] × [Impact] = **[Score]**

**Is Residual Risk Acceptable?**: [YES | NO]  
**Acceptance Rationale**: [Why this residual risk level is acceptable, or what else we'll do]

#### Status History

| Date | Event | New Score | Notes |
|------|-------|-----------|-------|
| [YYYY-MM-DD] | Risk identified | [Score] | [Context of identification] |
| [YYYY-MM-DD] | Mitigation plan approved | [Score] | [Decisions made] |
| [YYYY-MM-DD] | Mitigation action 1 completed | [Score] | [Results/learnings] |
| [YYYY-MM-DD] | Risk re-assessed | [New score] | [Why score changed] |

---

## High Risks (Score 12-19)

> 🟠 **HIGH PRIORITY**: These risks require immediate action this sprint

### RISK-H001: [Risk Title]

**Status**: [🔴 Active | 🟡 Monitoring | 🟢 Mitigated | ⚫ Closed]  
**Current Score**: [Probability × Impact = Score]  
**Target Score**: [After mitigation]  
**Date Identified**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Owner**: [Name/Role]  
**Review Frequency**: [Weekly]

#### Risk Details

**Description**:  
[Clear description of the risk]

**Category**: [Technical | Schedule | Resource | Business | Quality]

**Trigger Conditions**:  
- [Trigger 1]
- [Trigger 2]

**Impact if Occurs**:  
- **Schedule**: [Impact]
- **Budget**: [Impact]
- **Quality**: [Impact]
- **Business**: [Impact]

#### Risk Assessment

**Probability**: [1-5] - [Level]  
**Rationale**: [Why]

**Impact**: [1-5] - [Level]  
**Rationale**: [Why]

**Risk Score**: [P] × [I] = **[Score]** (🟠 High)

#### Mitigation Strategy

**Action 1**: [Mitigation action]
- Owner: [Name]
- Timeline: [Dates]
- Cost: [Estimate]
- Status: [Status]
- Expected Impact: [Effect]

**Action 2**: [Mitigation action]
- Owner: [Name]
- Timeline: [Dates]
- Cost: [Estimate]
- Status: [Status]
- Expected Impact: [Effect]

[Add more actions as needed]

#### Contingency Plan

**If Risk Occurs**:
1. [Response 1]
2. [Response 2]
3. [Response 3]

**Contingency Resources**: [Budget/time reserved]

#### Residual Risk

**After Mitigation**: [Probability] × [Impact] = **[Score]**  
**Acceptable?**: [YES | NO]

#### Status History

| Date | Event | Score | Notes |
|------|-------|-------|-------|
| [Date] | [Event] | [Score] | [Notes] |

---

[Continue for all High Risks using same format...]

---

## Medium Risks (Score 6-11)

> 🟡 **MONITOR**: These risks should be monitored and may need mitigation planning

### RISK-M001: [Risk Title]

**Status**: [Status]  
**Score**: [P × I = Score]  
**Owner**: [Name]  
**Date Identified**: [Date]

**Description**: [Brief description]

**Probability**: [Score] | **Impact**: [Score] | **Total**: [Score] (🟡 Medium)

**Response Strategy**: [Monitor | Plan Mitigation | Accept with monitoring]

**Monitoring Plan**:
- **What to watch**: [Indicators that risk is escalating]
- **Review frequency**: [Weekly/Monthly]
- **Escalation trigger**: [When to elevate to High priority]

**Prepared Response** (if needed):
1. [Quick response action 1]
2. [Quick response action 2]

**Status**: [Latest update on this risk]

---

[Continue for all Medium Risks using same format...]

---

## Low Risks (Score 3-5)

> 🟢 **ACCEPT**: These risks are accepted or monitored lightly

### Low Risk Summary

| Risk ID | Title | P | I | Score | Owner | Status |
|---------|-------|---|---|-------|-------|--------|
| RISK-L001 | [Title] | [P] | [I] | [Score] | [Owner] | [Status] |
| RISK-L002 | [Title] | [P] | [I] | [Score] | [Owner] | [Status] |
| RISK-L003 | [Title] | [P] | [I] | [Score] | [Owner] | [Status] |

**Response**: These risks are accepted with minimal monitoring. If conditions change and risk escalates, will be moved to Medium or High category.

---

## Very Low Risks (Score 1-2)

> ⚪ **ACCEPTED**: These risks are fully accepted

### Very Low Risk Summary

| Risk ID | Title | Score | Status |
|---------|-------|-------|--------|
| RISK-VL001 | [Title] | [Score] | Accepted |
| RISK-VL002 | [Title] | [Score] | Accepted |

---

## Closed Risks

### Risks Successfully Mitigated or No Longer Relevant

| Risk ID | Title | Original Score | Date Closed | Closure Reason |
|---------|-------|----------------|-------------|----------------|
| RISK-XXX | [Title] | [Score] | [Date] | [Mitigation successful / No longer relevant / Risk occurred and handled] |

---

## Risk Categories Analysis

### Technical Risks

**Total**: [Count]  
**Average Score**: [Score]  
**Highest Risk**: [RISK-ID] - [Title] (Score [X])

**Key Concerns**:
- [Concern 1]
- [Concern 2]

### Schedule Risks

**Total**: [Count]  
**Average Score**: [Score]  
**Highest Risk**: [RISK-ID] - [Title] (Score [X])

**Key Concerns**:
- [Concern 1]
- [Concern 2]

### Resource Risks

**Total**: [Count]  
**Average Score**: [Score]  
**Highest Risk**: [RISK-ID] - [Title] (Score [X])

**Key Concerns**:
- [Concern 1]
- [Concern 2]

### Business Risks

**Total**: [Count]  
**Average Score**: [Score]  
**Highest Risk**: [RISK-ID] - [Title] (Score [X])

**Key Concerns**:
- [Concern 1]
- [Concern 2]

### Quality Risks

**Total**: [Count]  
**Average Score**: [Score]  
**Highest Risk**: [RISK-ID] - [Title] (Score [X])

**Key Concerns**:
- [Concern 1]
- [Concern 2]

---

## Risk Concentration Analysis

### High-Risk Sprint Phases

**Sprint 0: Infrastructure Setup**
- Risk Count: [Number]
- Combined Risk Score: [Sum of all risks]
- Key Risks: [List top 3 risks in this phase]
- Mitigation Focus: [What we're doing about it]

**Sprint 1-2: Core Architecture Implementation**
- Risk Count: [Number]
- Combined Risk Score: [Sum]
- Key Risks: [List top 3]
- Mitigation Focus: [Actions]

**Sprint 3-4: External Integrations**
- Risk Count: [Number]
- Combined Risk Score: [Sum]
- Key Risks: [List top 3]
- Mitigation Focus: [Actions]

[Continue for other high-risk phases...]

---

## Risk Budget and Resources

### Mitigation Budget

| Category | Allocated | Spent | Remaining | Notes |
|----------|-----------|-------|-----------|-------|
| Technical mitigation | $[Amount] | $[Spent] | $[Remaining] | [Notes] |
| Training & education | $[Amount] | $[Spent] | $[Remaining] | [Notes] |
| External expertise | $[Amount] | $[Spent] | $[Remaining] | [Notes] |
| Tools & infrastructure | $[Amount] | $[Spent] | $[Remaining] | [Notes] |
| **Contingency buffer** | $[Amount] | $[Spent] | $[Remaining] | [Emergency use] |
| **TOTAL** | $[Total] | $[Spent] | $[Remaining] | |

**Budget Status**: [ON TRACK | AT RISK | OVER BUDGET]

### Schedule Buffer

| Phase | Planned Duration | Buffer Allocated | Buffer Used | Remaining |
|-------|------------------|------------------|-------------|-----------|
| Sprint 0 | [Days] | [Days] ([%]) | [Days] | [Days] |
| Sprint 1-2 | [Days] | [Days] ([%]) | [Days] | [Days] |
| Sprint 3-5 | [Days] | [Days] ([%]) | [Days] | [Days] |
| **TOTAL** | [Days] | [Days] ([%]) | [Days] | [Days] |

**Schedule Status**: [ON TRACK | AT RISK | DELAYED]

### Resource Allocation

**Dedicated Risk Mitigation Time**:
- Sprint 0: [X]% of team capacity
- Sprint 1-2: [X]% of team capacity
- Sprint 3+: [X]% of team capacity

**Risk Owners**:
- Technical risks: [Name/Role]
- Schedule risks: [Name/Role]
- Resource risks: [Name/Role]
- Business risks: [Name/Role]
- Quality risks: [Name/Role]

---

## Risk Monitoring Plan

### Daily Monitoring (During Standups)

**Focus Areas**:
- Sprint 0: Database and infrastructure setup progress
- Sprint 1-2: Architecture implementation challenges
- Any new risks emerging
- Status of in-progress mitigation tasks

**Questions to Ask**:
- Any blockers related to known risks?
- Any new concerns or risks identified?
- Mitigation tasks on track?

### Weekly Risk Review (15-30 minutes)

**Agenda**:
1. Review all HIGH risks (score 12+)
2. Check if any MEDIUM risks escalating
3. Update risk scores if conditions changed
4. Review mitigation task progress
5. Identify any new risks
6. Update risk register

**Participants**:
- Project Manager (facilitates)
- Technical Lead
- Key risk owners as needed

### Sprint Planning Risk Activities

**Integration Points**:
- Review risks when estimating tasks
- Allocate capacity for risk mitigation tasks
- Prioritize risk mitigation appropriately
- Build buffers into sprint plan
- Assign mitigation task owners

### Sprint Retrospective Risk Review

**Discussion Topics**:
- Which risks materialized? How did we handle them?
- Were mitigation strategies effective?
- Any new risks discovered during sprint?
- What worked well in risk management?
- What should we improve?
- Update lessons learned

### Monthly Strategic Risk Review

**Participants**:
- Project Manager
- Executive Sponsor
- Key Stakeholders
- Technical Leadership

**Agenda**:
1. Overall project risk level trend
2. Cumulative impact on budget and schedule
3. Major risk mitigation successes/failures
4. Need for course correction or escalation
5. Update risk response strategies
6. Executive decisions required

**Output**: Updated risk strategy and executive decisions

---

## Risk Escalation Process

### Level 1: Team Level (Risks Score 6-11)

**Who Handles**: Development team with PM oversight

**Process**:
1. Team identifies and discusses in standup
2. PM documents in risk register
3. Team plans mitigation in sprint planning
4. PM monitors progress

**Escalate to Level 2 if**:
- Risk score increases to 12+
- Mitigation not effective
- Resources needed beyond team

### Level 2: Project Manager Level (Risks Score 12-15)

**Who Handles**: Project Manager with technical leads

**Process**:
1. PM convenes risk response meeting
2. Detailed mitigation plan created
3. Resources allocated (budget/people)
4. May adjust schedule or scope
5. Regular (weekly) monitoring
6. Report to stakeholders

**Escalate to Level 3 if**:
- Risk score increases to 16+
- Mitigation requires significant budget/schedule changes
- Strategic decisions needed
- Multiple high risks converging

### Level 3: Executive Level (Risks Score 16+)

**Who Handles**: Executive sponsor with PM and leadership

**Process**:
1. PM prepares executive briefing
2. Emergency meeting with exec sponsor
3. Strategic decisions made:
   - Significant budget increase
   - Major schedule change
   - Scope reduction
   - Project pivot or cancellation
4. Communication plan to broader org
5. Daily monitoring until resolved

---

## Lessons Learned

### Risks That Materialized

| Risk ID | Title | Original Score | What Happened | How We Handled It | Lessons Learned |
|---------|-------|----------------|---------------|-------------------|-----------------|
| [ID] | [Title] | [Score] | [Description] | [Response] | [Learning] |

### Mitigation Successes

| Risk ID | Title | Mitigation Strategy | Why It Worked | Lessons for Future |
|---------|-------|---------------------|---------------|-------------------|
| [ID] | [Title] | [Strategy] | [Success factors] | [Learning] |

### Mitigation Failures

| Risk ID | Title | Attempted Mitigation | Why It Failed | What We Learned |
|---------|-------|---------------------|---------------|-----------------|
| [ID] | [Title] | [Strategy] | [Failure reasons] | [Learning] |

### Unexpected Risks

| Risk ID | Title | When Discovered | Why We Missed It | Prevention Strategy |
|---------|-------|-----------------|------------------|-------------------|
| [ID] | [Title] | [Sprint/Date] | [Root cause] | [How to catch earlier] |

### Risk Management Process Improvements

**What Worked Well**:
- [Success 1]
- [Success 2]
- [Success 3]

**What Needs Improvement**:
- [Issue 1] → [Planned improvement]
- [Issue 2] → [Planned improvement]
- [Issue 3] → [Planned improvement]

**Actions for Next Project**:
1. [Action 1]
2. [Action 2]
3. [Action 3]

---

## Change Log

| Version | Date | Changed By | Changes Made | Reason |
|---------|------|------------|--------------|--------|
| v1.0 | [Date] | [Name] | Initial risk assessment | Phase 2 kickoff |
| v1.1 | [Date] | [Name] | Added RISK-H003, updated RISK-T001 score | Sprint 1 learning |
| v2.0 | [Date] | [Name] | Closed 3 risks, added 2 new risks | Sprint 2 retrospective |

---

## Notes and Guidance

### Using This Risk Register

**DO**:
- Update the register weekly (minimum)
- Document all significant risks (score 6+)
- Be honest about probability and impact
- Create concrete mitigation plans
- Track mitigation task progress
- Close risks when truly resolved
- Learn from risks that materialize

**DON'T**:
- Let the register get stale (it's a living document)
- Ignore risks hoping they'll go away
- Be overly optimistic in risk scoring
- Create vague mitigation plans like "be careful"
- Skip risk reviews because "everything is fine"
- Track every tiny possible issue (focus on significant risks)
- Blame people when risks occur (focus on learning)

### Risk Management Best Practices

1. **Identify Early and Often**: The best time to find a risk is before it becomes a problem
2. **Be Realistic**: Don't downplay risks to look good - face reality
3. **Act Proactively**: Address high risks immediately, don't wait
4. **Communicate Transparently**: Stakeholders need to know about significant risks
5. **Monitor Continuously**: Risk conditions change - stay vigilant
6. **Learn and Adapt**: Each risk is a learning opportunity
7. **Balance Rigor with Pragmatism**: Don't make risk management overhead, make it valuable

### Common Pitfalls

- **Ignoring the register**: Creating it once then never updating it
- **Too many risks**: Tracking 100+ risks is unmanageable - focus on significant ones
- **Vague descriptions**: "Something might go wrong" isn't actionable
- **No ownership**: Risks need clear owners who will drive mitigation
- **No follow-through**: Creating mitigation plans but not executing them
- **Risk aversion paralysis**: Some risk is inevitable - balance mitigation with progress

---

**Remember: Risk management is about being prepared, not being perfect. The goal is to know what could go wrong, have plans ready, and adapt as conditions change. This register is your tool for making informed decisions and protecting project success.**
