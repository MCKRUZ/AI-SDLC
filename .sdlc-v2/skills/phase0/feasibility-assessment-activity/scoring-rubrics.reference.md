# Scoring Rubrics Reference

## Overview

Consistent scoring requires clear rubrics. Use these rubrics to score
each feasibility dimension objectively.

---

## Scoring Scale

| Score | Label | Meaning |
|-------|-------|---------|
| 5 | Excellent | Highly favorable, minimal risk |
| 4 | Good | Favorable, manageable risk |
| 3 | Acceptable | Neutral, moderate risk |
| 2 | Concerning | Unfavorable, significant risk |
| 1 | Critical | Highly unfavorable, major risk |

---

## Technical Feasibility Rubric

### Score: 5 (Excellent)

- Technology is mature and battle-tested at scale
- Team has extensive experience (3+ similar projects)
- Integration patterns are well-documented and proven
- No significant technical unknowns
- Multiple successful precedents exist

**Example**: Building a CRUD web app with React/Node.js for a team that has built 5 similar apps.

### Score: 4 (Good)

- Technology is mature with good ecosystem
- Team has some experience (1-2 similar projects)
- Integration is understood with minor unknowns
- Technical risks are identified and manageable
- Precedents exist, though may differ somewhat

**Example**: Adding a new microservice using team's standard stack, with one new integration to a known API.

### Score: 3 (Acceptable)

- Technology is established but team is learning
- Team has related but not direct experience
- Integration has some unknowns requiring spikes
- Technical risks exist but have mitigation paths
- Some precedent exists but not identical

**Example**: First Kubernetes deployment for a team experienced with Docker, with standard cloud services.

### Score: 2 (Concerning)

- Technology is emerging or team lacks experience
- Significant skill gaps requiring training/hiring
- Integration complexity is high with many unknowns
- Technical risks are significant, mitigations unclear
- Limited precedent, mostly theoretical

**Example**: Implementing ML pipeline with team new to ML, integrating with legacy systems with poor documentation.

### Score: 1 (Critical)

- Technology is experimental or unproven
- Team has no relevant experience
- Integration appears extremely complex
- Technical unknowns could be project-ending
- No precedent exists; truly novel

**Example**: Building on a new protocol with no production implementations, requiring custom tooling.

---

## Business Feasibility Rubric

### Score: 5 (Excellent)

- Clear, quantified ROI > 3x investment
- Directly enables top strategic priority
- Strong executive sponsorship (C-level)
- Broad stakeholder enthusiasm
- Competitive necessity or regulatory mandate

**Example**: Compliance project required by new regulation, with CEO sponsorship and clear cost of non-compliance.

### Score: 4 (Good)

- Solid business case with ROI > 1.5x
- Aligns with strategic priorities
- Has executive sponsor (VP level)
- Most stakeholders supportive
- Clear competitive or efficiency benefits

**Example**: Platform modernization that will reduce operational costs 40% with VP Engineering sponsoring.

### Score: 3 (Acceptable)

- Business case exists but ROI less certain
- Generally aligns with strategy
- Has sponsor but not senior executive
- Mixed stakeholder support
- Benefits are real but not urgent

**Example**: Internal tool improvement that will help productivity, sponsored by Director, some teams skeptical.

### Score: 2 (Concerning)

- Business case is weak or speculative
- Tangential to strategic priorities
- Sponsor is unclear or low-level
- Stakeholder resistance exists
- "Nice to have" not "need to have"

**Example**: Innovation project without clear business problem, championed by individual contributor.

### Score: 1 (Critical)

- No clear business case
- Conflicts with strategic direction
- No sponsor identified
- Active stakeholder opposition
- Solution looking for a problem

**Example**: Pet project that leadership doesn't know about, solves problem no one has articulated.

---

## Resource Feasibility Rubric

### Score: 5 (Excellent)

- Budget fully approved and allocated
- Team identified, available, and committed
- All required skills present on team
- No significant competing priorities
- Infrastructure ready

**Example**: Funded project with dedicated team already assembled, using existing infrastructure.

### Score: 4 (Good)

- Budget approved, minor uncertainty
- Team mostly identified, minor gaps
- Most skills present, small gaps fillable
- Some competing priorities, manageable
- Infrastructure available or easily provisioned

**Example**: Approved project with team 80% allocated, one role to hire, standard cloud resources needed.

### Score: 3 (Acceptable)

- Budget likely but not fully confirmed
- Team partially identified
- Some skill gaps requiring hiring/training
- Moderate resource contention
- Infrastructure needs some investment

**Example**: Project in annual plan but budget not released, team to be assembled, needs new environment.

### Score: 2 (Concerning)

- Budget uncertain or insufficient
- Team not identified, availability unclear
- Significant skill gaps
- Major resource conflicts with other priorities
- Infrastructure requires significant investment

**Example**: Project proposed but not budgeted, would pull from other committed work, needs new capabilities.

### Score: 1 (Critical)

- No budget allocated or approved
- No team available
- Critical skill gaps with no path to fill
- Resources fully committed elsewhere
- Infrastructure doesn't exist and can't be built in time

**Example**: Unfunded idea competing against already-committed roadmap, requiring skills we don't have.

---

## Timeline Feasibility Rubric

### Score: 5 (Excellent)

- Deadline is soft/flexible
- Timeline based on detailed estimation
- No external dependencies
- 30%+ buffer built in
- Scope can be adjusted if needed

**Example**: Internal project with "end of year" soft target, estimated bottom-up, fully within our control.

### Score: 4 (Good)

- Deadline has some flexibility
- Timeline based on reasonable estimation
- Dependencies are understood and manageable
- 20% buffer included
- Some scope flexibility exists

**Example**: Product launch with target date, estimated by team, one external dependency confirmed, some features can slip.

### Score: 3 (Acceptable)

- Deadline is firm but achievable
- Timeline is tight but realistic
- Some dependencies with risk
- 10% buffer included
- Limited scope flexibility

**Example**: Contract deadline in 6 months, estimated at 5 months work, depends on vendor API, core scope fixed.

### Score: 2 (Concerning)

- Deadline is hard with little flexibility
- Timeline is aggressive
- Multiple dependencies with uncertainty
- Minimal or no buffer
- Scope is fixed, no flexibility

**Example**: Regulatory deadline in 4 months, estimated at 4+ months, multiple integrations needed, no scope cuts possible.

### Score: 1 (Critical)

- Deadline is immovable with severe consequences
- Timeline appears impossible
- Critical dependencies outside our control
- No buffer, already behind
- Scope exceeds capacity

**Example**: Compliance deadline already past, scope keeps growing, dependent on unresponsive third party.

---

## Scoring Guidelines

### Be Honest

- Score based on evidence, not hope
- Don't inflate scores to "make it work"
- Document uncertainty in scores

### Use Evidence

For each score, document:
- What evidence supports this score?
- What assumptions are we making?
- What would change this score?

### Consider Confidence

| Confidence | Meaning |
|------------|---------|
| High | Strong evidence, direct experience |
| Medium | Some evidence, reasonable inference |
| Low | Limited evidence, significant assumptions |

### Score Documentation Template

```markdown
## [Dimension] Assessment

**Score**: [1-5]
**Confidence**: [High/Medium/Low]

### Evidence
- [Evidence point 1]
- [Evidence point 2]

### Assumptions
- [Assumption 1]
- [Assumption 2]

### What Would Improve Score
- [Factor that would raise score]

### What Would Lower Score
- [Risk that would lower score]
```

---

## Overall Feasibility Calculation

### Simple Method

```
Overall = (Technical + Business + Resource + Timeline) / 4
```

### Weighted Method

If dimensions have different importance:

```
Overall = (Tech × W1) + (Business × W2) + (Resource × W3) + (Timeline × W4)
Where W1 + W2 + W3 + W4 = 1.0
```

Default weights: 0.30, 0.25, 0.25, 0.20

### Minimum Gate

Regardless of average, if any dimension = 1, overall recommendation should be NO-GO or POC.

---

## Quick Reference Card

| Score | Technical | Business | Resource | Timeline |
|-------|-----------|----------|----------|----------|
| 5 | Proven tech, expert team | Clear ROI, C-level sponsor | Funded, team ready | Flexible, buffered |
| 4 | Mature tech, experienced team | Good case, VP sponsor | Approved, team mostly set | Achievable, some buffer |
| 3 | Learning curve, related experience | Reasonable case, Director sponsor | Likely funded, assembling team | Tight but realistic |
| 2 | Emerging tech, skill gaps | Weak case, unclear sponsor | Uncertain funding, conflicts | Aggressive, dependencies |
| 1 | Experimental, no experience | No case, no sponsor | No budget, no team | Impossible |
