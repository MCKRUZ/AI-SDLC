# Risk Register

**Project Name**: [Project name from constitution]  
**Date Created**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Version**: [v1.0, v2.0, etc.]  
**Risk Manager**: [Planning Agent / PM name]  
**Status**: [Active | Under Review | Archived]

---

## Purpose of This Document

This Risk Register is the **central repository for all identified project risks**, their assessments, mitigation strategies, and monitoring status. It serves as a living document that guides proactive risk management throughout the project lifecycle.

**What This Document Contains**:
- All identified risks with unique IDs
- Risk probability and impact assessments
- Risk severity ratings and prioritization
- Mitigation and contingency strategies
- Risk ownership and accountability
- Risk status tracking and updates
- Risk trigger conditions and indicators
- Historical risk resolution outcomes

**What This Document Does NOT Contain**:
- Detailed task execution plans (see sprint-plan.md)
- Technical design decisions (see architecture.md)
- Quality standards (see quality-strategy.md)
- Day-to-day issue tracking (use issue tracker)

**Who Uses This Document**:
- Project Manager: Overall risk oversight and escalation
- Planning Agent: Risk-aware sprint planning
- Development Team: Understanding and mitigating technical risks
- Product Owner: Business risk awareness and prioritization
- Stakeholders: Risk transparency and informed decision-making
- Leadership: Strategic risk visibility for resource allocation

**Traceability**:
- **From**: All project artifacts (constitution, spec, architecture, task breakdown, sprint plan)
- **To**: Risk mitigation tasks in sprint plan, contingency plans in project plan
- **Related**: lessons-learned.memory.md, prior-projects.memory.md

---

## Executive Summary

**Overall Risk Profile**: [Low / Medium / High / Critical]  
**Last Assessment Date**: [YYYY-MM-DD]  
**Next Review Date**: [YYYY-MM-DD]

**Risk Statistics**:
- **Total Risks**: [X] active risks
- **Critical Risks**: [X] (Probability × Impact ≥ 12)
- **High Risks**: [X] (Probability × Impact 8-11)
- **Medium Risks**: [X] (Probability × Impact 4-7)
- **Low Risks**: [X] (Probability × Impact 1-3)
- **Closed Risks**: [X] (mitigated or occurred)

**Top 3 Risks** (requiring immediate attention):
1. **[RISK-ID]**: [Risk name] - [Why it's critical]
2. **[RISK-ID]**: [Risk name] - [Why it's critical]
3. **[RISK-ID]**: [Risk name] - [Why it's critical]

**Risk Trend**: [Improving ↓ / Stable → / Worsening ↑]
- Risks closed since last review: [X]
- New risks identified: [X]
- Risks escalated in severity: [X]
- Risks de-escalated: [X]

**Budget Impact**:
- **Risk Reserve Allocated**: $[X] or [Y] person-days
- **Risk Reserve Used**: $[X] or [Y] person-days ([Z]%)
- **Risk Reserve Remaining**: $[X] or [Y] person-days ([Z]%)

**Schedule Impact**:
- **Schedule Buffer Allocated**: [X] days/weeks ([Y]% of timeline)
- **Schedule Buffer Consumed**: [X] days/weeks ([Y]%)
- **Current Project Delay Risk**: [Low / Medium / High]

---

## Risk Assessment Framework

### Probability Scale (1-4)

| Level | Probability | Description | Percentage |
|-------|-------------|-------------|------------|
| **1** | Very Low | Highly unlikely to occur | < 10% |
| **2** | Low | Unlikely but possible | 10-40% |
| **3** | Medium | Reasonably likely | 40-70% |
| **4** | High | Very likely or almost certain | > 70% |

### Impact Scale (1-4)

| Level | Impact | Schedule | Budget | Quality | Scope |
|-------|--------|----------|--------|---------|-------|
| **1** | Minimal | < 1 week delay | < 5% over | Minor quality degradation | Trivial scope change |
| **2** | Low | 1-2 weeks delay | 5-10% over | Noticeable quality impact | Small feature dropped |
| **3** | Medium | 2-4 weeks delay | 10-20% over | Significant quality compromise | Major feature at risk |
| **4** | High | > 4 weeks delay | > 20% over | Critical quality failure | MVP scope threatened |

### Severity Rating (Probability × Impact)

| Severity | Score Range | Priority | Action Required |
|----------|-------------|----------|-----------------|
| **Critical** | 12-16 | P0 | Immediate action, daily monitoring, executive escalation |
| **High** | 8-11 | P1 | Proactive mitigation, weekly monitoring, PM escalation |
| **Medium** | 4-7 | P2 | Mitigation planned, bi-weekly monitoring |
| **Low** | 1-3 | P3 | Accept or monitor, monthly review |

---

## Risk Categories

Risks are classified into these categories for systematic identification:

### Technical Risks (TECH)
- Technology uncertainty or immaturity
- Integration complexity
- Performance or scalability concerns
- Technical debt accumulation
- Architecture decisions

### Schedule Risks (SCHED)
- Timeline constraints
- Resource availability
- Dependency delays
- Estimation accuracy
- Scope creep

### Resource Risks (RES)
- Team size or skill gaps
- Key person dependencies
- Budget constraints
- Infrastructure limitations
- Tooling inadequacy

### External Risks (EXT)
- Third-party dependencies
- Vendor reliability
- Regulatory changes
- Market conditions
- Stakeholder availability

### Quality Risks (QUAL)
- Testing coverage gaps
- Security vulnerabilities
- Performance issues
- Usability problems
- Technical debt

### Business Risks (BIZ)
- Market fit uncertainty
- User adoption
- ROI concerns
- Competitive threats
- Strategic alignment

---

## Risk Register

### Critical Risks (P0 - Immediate Action Required)

| ID | Risk Description | Category | Probability | Impact | Severity | Owner | Status | Last Updated |
|----|------------------|----------|-------------|--------|----------|-------|--------|--------------|
| RISK-001 | [Description of critical risk] | [Category] | 4 | 4 | 16 | [Name] | [Open/Mitigating/Closed] | [Date] |
| RISK-002 | [Description of critical risk] | [Category] | 3 | 4 | 12 | [Name] | [Open/Mitigating/Closed] | [Date] |

---

#### RISK-001: [Risk Name]

**Category**: [TECH/SCHED/RES/EXT/QUAL/BIZ]  
**Date Identified**: [YYYY-MM-DD]  
**Identified By**: [Name/Role]  
**Owner**: [Name] (responsible for monitoring and mitigation)  
**Status**: [Open | Mitigating | Monitoring | Closed | Occurred]

**Description**:
[Detailed description of the risk - what could go wrong and why it matters]

**Probability Assessment**: 4 (High - >70% chance)  
**Rationale**: [Why this probability rating - what factors increase likelihood]

**Impact Assessment**: 4 (High - >4 weeks delay or >20% budget or MVP threatened)  
**Impact Areas**:
- **Schedule**: [Specific impact on timeline]
- **Budget**: [Specific impact on cost]
- **Quality**: [Specific impact on quality]
- **Scope**: [Specific impact on features/requirements]

**Severity**: 16 (Critical)  
**Priority**: P0

**Trigger Conditions** (early warning signs):
1. [Observable indicator that risk is materializing]
2. [Observable indicator that risk is materializing]
3. [Observable indicator that risk is materializing]

**Root Causes**:
- [Underlying cause 1]
- [Underlying cause 2]
- [Underlying cause 3]

**Related Risks**: [RISK-XXX, RISK-YYY] (dependencies or similar risks)

**Mitigation Strategy** (reduce probability or impact BEFORE risk occurs):
1. **Action**: [Specific mitigation action]
   - **Responsibility**: [Who will do it]
   - **Timeline**: [When it will be done]
   - **Success Criteria**: [How we'll know it worked]
   - **Cost**: [Effort/budget required]

2. **Action**: [Specific mitigation action]
   - **Responsibility**: [Who will do it]
   - **Timeline**: [When it will be done]
   - **Success Criteria**: [How we'll know it worked]
   - **Cost**: [Effort/budget required]

**Contingency Plan** (response IF risk occurs):
1. [Immediate action to take]
2. [Escalation path]
3. [Recovery steps]
4. [Fallback options]

**Monitoring Plan**:
- **Frequency**: [Daily/Weekly/Bi-weekly]
- **KPIs**: [Specific metrics to track]
- **Review Forum**: [Where risk is discussed - standup/sprint review/steering committee]
- **Escalation Threshold**: [When to escalate to next level]

**Updates**:
- **[YYYY-MM-DD]**: [Status update - what changed, current state, next actions]
- **[YYYY-MM-DD]**: [Status update - what changed, current state, next actions]

**Closure Criteria**:
- [ ] Mitigation actions completed successfully
- [ ] Risk no longer applicable (conditions changed)
- [ ] Risk occurred and was resolved
- [ ] Risk accepted as residual risk

**Lessons Learned** (if closed):
[What we learned from this risk - capture for future projects]

---

### High Risks (P1 - Proactive Mitigation Required)

| ID | Risk Description | Category | Probability | Impact | Severity | Owner | Status | Last Updated |
|----|------------------|----------|-------------|--------|----------|-------|--------|--------------|
| RISK-003 | [Description of high risk] | [Category] | 4 | 3 | 12 | [Name] | [Status] | [Date] |
| RISK-004 | [Description of high risk] | [Category] | 3 | 3 | 9 | [Name] | [Status] | [Date] |

[Use same detailed format as RISK-001 above for each high risk]

---

### Medium Risks (P2 - Monitor and Plan)

| ID | Risk Description | Category | Probability | Impact | Severity | Owner | Status | Last Updated |
|----|------------------|----------|-------------|--------|----------|-------|--------|--------------|
| RISK-010 | [Description] | [Category] | 3 | 2 | 6 | [Name] | [Status] | [Date] |
| RISK-011 | [Description] | [Category] | 2 | 3 | 6 | [Name] | [Status] | [Date] |

[Can use abbreviated format for medium risks unless they escalate]

---

### Low Risks (P3 - Accept or Monitor)

| ID | Risk Description | Category | Probability | Impact | Severity | Owner | Status | Last Updated |
|----|------------------|----------|-------------|--------|----------|-------|--------|--------------|
| RISK-020 | [Description] | [Category] | 2 | 2 | 4 | [Name] | [Status] | [Date] |
| RISK-021 | [Description] | [Category] | 1 | 3 | 3 | [Name] | [Status] | [Date] |

---

## Risk Response Strategies

### Mitigation (Reduce Probability or Impact)
**When to Use**: High-priority risks that can be prevented or reduced  
**Examples**:
- Technical spike to reduce uncertainty
- Add experienced developer to reduce skill gap risk
- Implement automated testing to reduce quality risk
- Early prototype to validate approach

### Avoidance (Eliminate the Risk)
**When to Use**: Critical risks that can be avoided by changing approach  
**Examples**:
- Choose proven technology instead of cutting-edge
- Reduce scope to eliminate risky features
- Use vendor solution instead of building custom
- Change architecture to avoid integration complexity

### Transfer (Share or Shift the Risk)
**When to Use**: Risks that others are better equipped to handle  
**Examples**:
- Use SaaS instead of hosting (transfer infrastructure risk)
- Outsource specialized work (transfer skill gap risk)
- Purchase insurance (transfer financial risk)
- Partner with vendor (transfer technology risk)

### Acceptance (Acknowledge and Plan for It)
**When to Use**: Low-priority risks or risks where mitigation cost > impact  
**Examples**:
- Accept minor UI inconsistencies in MVP
- Accept moderate technical debt for speed
- Accept limited browser support initially
- Set aside contingency budget/time

---

## Risk Ownership & Accountability

### Risk Owner Responsibilities

Each risk must have a designated owner who is:
- **Accountable** for monitoring the risk
- **Responsible** for executing mitigation actions
- **Informed** about any changes to risk status
- **Empowered** to escalate when needed

**Risk Owner Duties**:
1. Monitor trigger conditions and early warnings
2. Execute mitigation actions per plan
3. Update risk register with status changes
4. Escalate when severity increases or mitigation fails
5. Communicate with stakeholders about risk status
6. Participate in risk reviews
7. Document lessons learned when risk closes

### Escalation Path

**Level 1 - Team Level** (Low/Medium Risks):
- Owner: Development team member or tech lead
- Forum: Daily standup, sprint planning
- Response Time: Within sprint
- Authority: Adjust task priorities, request help

**Level 2 - Project Level** (High Risks):
- Owner: Project Manager or Product Owner
- Forum: Sprint review, weekly status meeting
- Response Time: Within 2-3 days
- Authority: Adjust sprint scope, reallocate resources, engage external help

**Level 3 - Executive Level** (Critical Risks):
- Owner: Executive Sponsor or Department Head
- Forum: Steering committee, executive briefing
- Response Time: Within 24 hours
- Authority: Change project timeline, increase budget, pivot strategy, stop project

---

## Risk Monitoring & Review Cadence

### Daily Monitoring (Critical Risks Only)
- **Who**: Risk owner and project manager
- **What**: Check trigger conditions, review mitigation progress
- **Duration**: 5-10 minutes
- **Output**: Update risk status if changed, escalate if needed

### Weekly Risk Review (All Active Risks)
- **Who**: Project manager, tech lead, risk owners
- **What**: Review all high and medium risks, trends, new risks
- **Duration**: 30-45 minutes
- **Output**: Updated risk register, new mitigation actions, escalations

### Sprint Risk Review (Sprint Planning Input)
- **Who**: Full team, product owner, stakeholders
- **What**: Risk-informed sprint planning, capacity adjustments
- **Duration**: 15-20 minutes within sprint planning
- **Output**: Risk-aware sprint commitments, buffer allocation

### Monthly Strategic Risk Review
- **Who**: Project manager, executive sponsor, key stakeholders
- **What**: Overall risk profile, trend analysis, risk reserve status
- **Duration**: 60 minutes
- **Output**: Strategic adjustments, budget/timeline revisions if needed

### Risk Closure Review (Ad Hoc)
- **Who**: Risk owner, project manager, affected team members
- **What**: Document lessons learned, update risk patterns
- **Duration**: 15-30 minutes
- **Output**: Lessons learned captured, risk closed in register

---

## Risk Metrics & KPIs

### Leading Indicators (Predictive)
- **Risk Identification Rate**: New risks found per sprint (target: declining trend)
- **Risk Closure Rate**: Risks mitigated per sprint (target: > identification rate)
- **Mitigation Action Completion**: % of mitigation actions completed on time (target: >80%)
- **Trigger Condition Monitoring**: % of risks with defined triggers (target: 100% for P0/P1)

### Lagging Indicators (Historical)
- **Risk Materialization Rate**: % of risks that actually occurred (target: <20%)
- **Impact Accuracy**: Actual vs. estimated impact when risks occur (target: within 25%)
- **Mitigation Effectiveness**: % reduction in severity after mitigation (target: >50%)
- **Risk Reserve Burn Rate**: % of reserve used vs. timeline elapsed (target: linear or better)

### Risk Profile Trends
- **Severity Distribution**: Trend in critical/high/medium/low risk counts
- **Risk Age**: Average time risks stay open (target: declining)
- **Risk Category Concentration**: Which categories have most risks
- **Escalation Frequency**: Number of risks escalated (target: low and declining)

---

## Risk Register Maintenance

### Adding New Risks

**Process**:
1. Any team member can identify a risk
2. Capture basic information (description, category, potential impact)
3. Planning Agent or PM assigns risk ID
4. Risk owner assesses probability and impact
5. Mitigation strategy developed within 2 days for high+ severity
6. Risk added to register and next review agenda

**Information Required**:
- Clear description of what could go wrong
- Category and root causes
- Estimated probability and impact
- Suggested owner (subject matter expert)

### Updating Existing Risks

**When to Update**:
- Status changes (open → mitigating → closed)
- Probability or impact changes (reassessment)
- Mitigation actions completed or added
- Trigger conditions observed
- New information affects the risk
- At least bi-weekly for medium+ risks

**Update Process**:
1. Risk owner adds dated entry to Updates section
2. Updates relevant fields (status, severity, etc.)
3. Notifies project manager if severity changes
4. Escalates if needed per escalation path

### Closing Risks

**Closure Reasons**:
- **Mitigated**: Risk no longer possible due to mitigation
- **Occurred**: Risk happened and was resolved
- **Obsolete**: Conditions changed, risk no longer relevant
- **Accepted**: Formally accepted as residual risk

**Closure Process**:
1. Verify closure criteria met
2. Document final outcome and lessons learned
3. Update risk status to "Closed"
4. Move to "Closed Risks" section
5. Extract lessons for lessons-learned.memory.md

---

## Integration with Other Artifacts

### Task Breakdown & Sprint Plan
- **Mitigation Tasks**: Specific tasks created in task-breakdown.md for risk mitigation
- **Buffer Allocation**: Sprint capacity reduced to account for risk reserve
- **Priority Adjustments**: High-risk features prioritized for early validation
- **Technical Spikes**: Spikes scheduled for high-uncertainty risks

### Quality Strategy
- **Quality Risks**: Quality-related risks inform test strategy and coverage
- **Quality Gates**: Risks inform which quality gates are critical
- **Definition of Done**: Risk mitigation may be part of DoD

### Architecture
- **Technical Risks**: Architecture decisions informed by technical risk assessment
- **Architecture Patterns**: Risk mitigation may drive pattern choices
- **Technology Choices**: High-risk technologies may be avoided or de-risked

### Constitution
- **Non-Functional Requirements**: Risks to NFR achievement tracked
- **Constraints**: Constraint violations identified as risks
- **Quality Standards**: Risks to meeting standards tracked

---

## Closed Risks Archive

### Successfully Mitigated Risks

| ID | Risk Description | Original Severity | Mitigation Applied | Outcome | Lessons Learned | Closed Date |
|----|------------------|-------------------|--------------------|---------|--------------------|-------------|
| RISK-xxx | [Description] | [Score] | [What we did] | [Result] | [What we learned] | [Date] |

### Risks That Materialized

| ID | Risk Description | Original Severity | Actual Impact | Response Actions | Outcome | Lessons Learned | Closed Date |
|----|------------------|-------------------|---------------|------------------|---------|-----------------|-------------|
| RISK-xxx | [Description] | [Score] | [What happened] | [How we responded] | [Result] | [What we learned] | [Date] |

### Obsolete Risks

| ID | Risk Description | Reason Obsolete | Closed Date |
|----|------------------|-----------------|-------------|
| RISK-xxx | [Description] | [Why no longer relevant] | [Date] |

---

## Appendices

### Appendix A: Risk Identification Checklist

Use this checklist during risk identification sessions:

**Technical Risks**:
- [ ] New or unproven technology?
- [ ] Complex integrations?
- [ ] Performance/scalability concerns?
- [ ] Security vulnerabilities?
- [ ] Technical debt accumulation?

**Schedule Risks**:
- [ ] Aggressive timeline?
- [ ] Resource availability issues?
- [ ] Dependencies on external parties?
- [ ] Estimation uncertainty?
- [ ] Scope likely to grow?

**Resource Risks**:
- [ ] Skill gaps in team?
- [ ] Key person dependencies?
- [ ] Budget constraints?
- [ ] Infrastructure limitations?
- [ ] Inadequate tooling?

**External Risks**:
- [ ] Third-party dependencies?
- [ ] Vendor reliability concerns?
- [ ] Regulatory/compliance changes?
- [ ] Market volatility?
- [ ] Stakeholder availability?

**Quality Risks**:
- [ ] Testing coverage gaps?
- [ ] Security testing insufficient?
- [ ] Performance testing needed?
- [ ] Usability concerns?
- [ ] Accessibility requirements?

**Business Risks**:
- [ ] Market fit uncertainty?
- [ ] User adoption concerns?
- [ ] ROI questionable?
- [ ] Competitive threats?
- [ ] Strategic misalignment?

### Appendix B: Risk Assessment Examples

[Include 2-3 well-documented example risks with complete assessments]

### Appendix C: Mitigation Strategy Patterns

[Document common mitigation patterns that work for similar risk types]

### Appendix D: Risk Review Meeting Template

**Agenda**:
1. Review critical and high risks (10 min)
2. Review medium risks (5 min)
3. Identify new risks (10 min)
4. Update risk register (5 min)
5. Escalation needs (5 min)

### Appendix E: Risk Reporting Template

**Weekly Risk Summary Email**:
```
Subject: [Project] Risk Status - Week of [Date]

Critical Risks (P0): [X] - [Trend ↑/→/↓]
- [RISK-ID]: [Status summary]

High Risks (P1): [X] - [Trend ↑/→/↓]
- [RISK-ID]: [Status summary]

New Risks This Week: [X]
Closed Risks This Week: [X]
Escalations Required: [Yes/No]

Risk Reserve: [X]% used, [Y]% remaining

Next Risk Review: [Date/Time]
```

---

## Approval & Sign-Off

**Risk Register Approved By**:

- **Project Manager**: [Name] - [Date]  
  *Confirms risk identification complete and mitigation plans adequate*

- **Technical Lead**: [Name] - [Date]  
  *Confirms technical risk assessments accurate*

- **Product Owner**: [Name] - [Date]  
  *Acknowledges business and schedule risks*

- **Executive Sponsor**: [Name] - [Date]  
  *Accepts overall risk profile and authorizes risk reserve*

**Risk Management Approach Approved**: ✅ Yes / ❌ No  
**Risk Reserve Authorized**: $[X] or [Y] person-days  
**Schedule Buffer Approved**: [X] days/weeks ([Y]% of timeline)

**Next Full Risk Assessment**: [YYYY-MM-DD]

---

*Last Updated: [Date]*  
*Version: [Version number]*  
*Document Owner: [Planning Agent / PM name]*
