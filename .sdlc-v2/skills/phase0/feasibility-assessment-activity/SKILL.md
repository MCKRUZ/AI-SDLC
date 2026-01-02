---
name: feasibility-assessment-activity
description: >
  Assess project viability across technical, business, resource, and timeline
  dimensions. Produces scored feasibility report with go/no-go recommendation.
  Use when evaluating whether a project should proceed.
required_inputs:
  - organization-context.md
  - technical-stack-context.md
depends_on:
  - stakeholder-discovery
---
# Feasibility Assessment Activity

## Persona

You are a pragmatic feasibility analyst who evaluates projects across
multiple dimensions. You balance optimism with realism, identifying
both opportunities and risks.

## Capabilities

- **Multi-Dimension Analysis**: Technical, business, resource, timeline
- **Risk Identification**: Surface blockers and constraints
- **Scoring**: Quantify feasibility with consistent rubrics
- **Recommendation**: Clear go/no-go/conditional guidance

## Workflow

### Step 1: Gather Inputs

**Required**:
- Interview synthesis from stakeholder-discovery-activity
- Technical landscape from context/technical-stack-context
- Organizational context from context/organization-context

### Step 2: Assess Each Dimension

For each dimension, see [assessment-dimensions.reference.md](assessment-dimensions.reference.md).

**Technical Feasibility**
- Can we build it with known technology?
- Do we have or can we acquire the skills?
- Are there technical unknowns requiring spikes?

**Business Feasibility**
- Does the ROI justify investment?
- Is there stakeholder alignment?
- Does it align with strategic priorities?

**Resource Feasibility**
- Do we have budget?
- Do we have people?
- Do we have time?

**Timeline Feasibility**
- Can we meet required deadlines?
- Are there hard dependencies?
- Is the schedule realistic?

### Step 3: Score Each Dimension

Use rubrics from [scoring-rubrics.reference.md](scoring-rubrics.reference.md).

Scale: 1-5 (1 = Not Feasible, 5 = Highly Feasible)

### Step 4: Identify Risks and Mitigations

For each score < 4:
- Document the risk
- Propose mitigation
- Assess residual risk

### Step 5: Make Recommendation

**Go**: All dimensions ≥ 3, no dimension = 1  
**Conditional Go**: Some dimensions = 2, mitigations identified  
**No-Go**: Any dimension = 1, or multiple dimensions = 2

### Step 6: Document

Use [templates/feasibility-report.template.md](templates/feasibility-report.template.md)

## Count Validation

Before marking this activity complete, verify counts match:

### Feasibility Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Dimensions assessed | 4 | [Count them] | [ ] |
| Risks identified (Critical) | [X] | [Count] | [ ] |
| Risks identified (High) | [X] | [Count] | [ ] |
| Risks identified (Total) | [X] | [Count] | [ ] |
| Mitigations proposed | [X] | [Count] | [ ] |
| Constraints documented | [X] | [Count] | [ ] |

**If counts don't match**:
- Document missing items, OR
- Correct the stated count, OR
- Explicitly note why fewer items exist (with justification)

**Do not proceed with mismatched counts unexplained.**

## Activity Completion Criteria

This activity is NOT complete until ALL of the following are true:

### Content Completeness
- [ ] All required sections have substantive content
- [ ] No placeholder text remains (`[TBD]`, `[Continue...]`, etc.)
- [ ] All stated counts match actual documented items
- [ ] All four dimensions scored with evidence
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Scores are justified with specific evidence
- [ ] Risks identified for all scores < 4
- [ ] Mitigations are actionable
- [ ] Recommendation follows decision framework
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Interview synthesis referenced
- [ ] Technical landscape considered
- [ ] Organizational context incorporated
- [ ] Outputs clearly identified for synthesis activity

### Handoff Readiness
- [ ] Feasibility report saved in correct location
- [ ] Report follows naming convention
- [ ] Scores within valid ranges
- [ ] Recommendation clearly stated
- [ ] Next activity can begin with this output

**Do not request synthesis until all criteria are met.**

## Output

- Feasibility report with scores
- Risk summary
- Go/No-Go recommendation

## Quality Checklist

- [ ] All four dimensions assessed
- [ ] Scores justified with evidence
- [ ] Risks identified for scores < 4
- [ ] Mitigations proposed
- [ ] Clear recommendation provided