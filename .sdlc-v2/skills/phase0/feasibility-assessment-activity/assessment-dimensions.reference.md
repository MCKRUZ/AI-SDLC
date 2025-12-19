# Assessment Dimensions Reference

## Overview

Feasibility assessment evaluates projects across four key dimensions.
Each dimension considers different factors and stakeholders.

---

## Dimension 1: Technical Feasibility

### What It Answers

Can we build this with available technology and skills?

### Assessment Factors

| Factor | Questions | Evidence Sources |
|--------|-----------|------------------|
| **Technology Maturity** | Is the technology proven? Emerging? Experimental? | Industry reports, case studies |
| **Technical Complexity** | How complex is the solution? | Architecture analysis |
| **Skills Availability** | Do we have the skills? Can we acquire them? | Team assessment, hiring market |
| **Integration Complexity** | How hard to integrate with existing systems? | Technical discovery |
| **Technical Unknowns** | What don't we know? How risky? | Spike candidates |
| **Precedent** | Has this been done before? | Research, case studies |

### Key Questions

1. Has this technology been used successfully at similar scale?
2. Does our team have experience with the core technologies?
3. What's the learning curve for new technologies?
4. Are there proven integration patterns for our systems?
5. What technical spikes are needed before committing?
6. What are the technical risks and mitigations?

### Red Flags

- No precedent for this approach at scale
- Core technology is experimental/beta
- Team has zero experience with key tech
- Multiple unproven integrations required
- No clear path to resolve technical unknowns

### Green Flags

- Multiple successful implementations exist
- Team has built similar systems before
- Technology is mature with good ecosystem
- Integration patterns are well-documented
- Unknowns can be resolved with time-boxed spikes

---

## Dimension 2: Business Feasibility

### What It Answers

Does this make business sense? Will it deliver value?

### Assessment Factors

| Factor | Questions | Evidence Sources |
|--------|-----------|------------------|
| **ROI Potential** | What's the expected return? | Business case, projections |
| **Strategic Alignment** | Does it fit company strategy? | Strategy docs, exec interviews |
| **Stakeholder Support** | Who's championing this? Who's against? | Stakeholder interviews |
| **Market Timing** | Is now the right time? | Market analysis |
| **Competitive Need** | Do we need this to compete? | Competitive analysis |
| **Regulatory Impact** | Any compliance implications? | Legal/compliance review |

### Key Questions

1. What's the quantified business value (revenue, cost savings, risk reduction)?
2. How does this align with strategic priorities?
3. Who are the executive sponsors? How committed are they?
4. What happens if we don't do this?
5. Are there regulatory or compliance requirements driving this?
6. What's the competitive landscape?

### Red Flags

- No clear business case or ROI
- Misaligned with stated company strategy
- No executive sponsor
- Stakeholders actively opposed
- "Solution looking for a problem"

### Green Flags

- Clear, quantified business value
- Direct alignment with strategic priorities
- Strong executive sponsorship
- Broad stakeholder support
- Market/competitive pressure to act

---

## Dimension 3: Resource Feasibility

### What It Answers

Do we have the people, money, and capacity to do this?

### Assessment Factors

| Factor | Questions | Evidence Sources |
|--------|-----------|------------------|
| **Budget** | Is funding available? Sufficient? | Finance, budget owners |
| **People** | Do we have the team? Can we get them? | Resource planning, HR |
| **Skills** | Do we have the right skills? | Skills assessment |
| **Capacity** | Is the team available? Other commitments? | Resource calendars |
| **External Resources** | Need vendors? Consultants? | Procurement, vendors |
| **Infrastructure** | Do we have the infrastructure? | IT, operations |

### Key Questions

1. What's the estimated budget? Is it approved?
2. How many people do we need? What skills?
3. Are those people available? When?
4. What's competing for the same resources?
5. Do we need external help? Is it budgeted?
6. What infrastructure investments are needed?

### Red Flags

- No budget allocated or approved
- Key skills not available internally or externally
- Team fully committed to other priorities
- Resource conflicts with higher-priority projects
- Critical infrastructure not in place

### Green Flags

- Budget approved and allocated
- Team identified and available
- Skills match requirements
- No major resource conflicts
- Infrastructure ready or easily provisioned

---

## Dimension 4: Timeline Feasibility

### What It Answers

Can we deliver in the required timeframe?

### Assessment Factors

| Factor | Questions | Evidence Sources |
|--------|-----------|------------------|
| **Deadline Type** | Hard deadline? Soft? Arbitrary? | Stakeholder interviews |
| **Scope vs Time** | Is scope achievable in time? | Estimation, planning |
| **Dependencies** | External dependencies? Blockers? | Dependency analysis |
| **Complexity** | Is timeline realistic for complexity? | Technical assessment |
| **Team Ramp-up** | Time needed to get team productive? | Resource planning |
| **Risk Buffer** | Is there buffer for unknowns? | Risk assessment |

### Key Questions

1. Is there a hard deadline? What happens if we miss it?
2. What's driving the timeline? Can it be negotiated?
3. What external dependencies exist?
4. Is the timeline realistic given the scope?
5. How long to ramp up the team?
6. What's our contingency buffer?

### Red Flags

- Hard deadline with no flexibility
- Timeline set without estimation input
- Multiple external dependencies
- No buffer for unknowns
- Timeline assumes everything goes perfectly

### Green Flags

- Flexible or soft deadline
- Timeline based on realistic estimates
- Dependencies are understood and managed
- Adequate buffer built in
- Scope can be adjusted to fit timeline

---

## Cross-Dimension Analysis

### Dimension Interactions

| If This Is Weak | Consider Impact On |
|-----------------|-------------------|
| Technical | Timeline (learning), Resources (skills) |
| Business | Resources (budget approval) |
| Resources | Timeline (capacity), Technical (skills) |
| Timeline | All others (pressure creates risk) |

### Overall Assessment

```
Overall Feasibility = Min(Technical, Business, Resource, Timeline)
```

A project is only as feasible as its weakest dimension.

### Decision Framework

| Scenario | Recommendation |
|----------|----------------|
| All dimensions ≥ 4 | GO - Proceed with confidence |
| All dimensions ≥ 3, none = 1 | GO - Proceed with monitoring |
| Any dimension = 2 | CONDITIONAL - Mitigate before proceeding |
| Any dimension = 1 | NO-GO or POC required |
| Multiple dimensions ≤ 2 | NO-GO - Too many risks |

---

## Quick Reference

### Assessment Checklist

**Technical**
- [ ] Technology maturity evaluated
- [ ] Team skills assessed
- [ ] Integration complexity understood
- [ ] Unknowns identified
- [ ] Precedent researched

**Business**
- [ ] Business case quantified
- [ ] Strategic alignment confirmed
- [ ] Executive sponsor identified
- [ ] Stakeholder positions mapped

**Resource**
- [ ] Budget confirmed
- [ ] Team identified
- [ ] Capacity verified
- [ ] External needs assessed

**Timeline**
- [ ] Deadline type understood
- [ ] Dependencies mapped
- [ ] Realistic estimate done
- [ ] Buffer included
