# Contradiction Analysis Reference

## Overview

Contradictions occur when stakeholders provide conflicting information.
They're not problems to hide—they're valuable signals that reveal
complexity, politics, or gaps in understanding.

---

## Types of Contradictions

### Type 1: Factual Contradictions

**Definition**: Different stakeholders state different facts

**Example**:
- CEO: "We process 10,000 orders per day"
- Operations: "Average is 3,000 orders per day"

**Resolution**: Verify with data. One is wrong.

**Action**: Find source of truth (reports, logs, metrics)

---

### Type 2: Perspective Contradictions

**Definition**: Same situation, different interpretations

**Example**:
- Sales: "The system is too slow for customers"
- IT: "System performance is within SLA"

**Resolution**: Both may be "right" from their perspective

**Action**: Understand the different contexts and needs

---

### Type 3: Priority Contradictions

**Definition**: Stakeholders disagree on importance

**Example**:
- Marketing: "Mobile app is the top priority"
- Finance: "Cost reduction is the top priority"

**Resolution**: This is a business decision, not a discovery finding

**Action**: Escalate for leadership alignment

---

### Type 4: Solution Contradictions

**Definition**: Different stakeholders want different solutions

**Example**:
- Users: "We need more features"
- Support: "We need fewer, simpler features"

**Resolution**: Focus on underlying need, not proposed solution

**Action**: Apply Five Whys to find common root need

---

### Type 5: Timeline Contradictions

**Definition**: Different understanding of urgency

**Example**:
- Sponsor: "This needs to launch by Q2"
- Team: "Q4 is the earliest realistic date"

**Resolution**: Gap between desire and reality

**Action**: Surface the gap, discuss trade-offs

---

## Contradiction Detection

### During Interviews

Listen for:
- Statements that conflict with prior interviews
- Hesitation or qualification ("well, sort of...")
- Different numbers for the same metric
- Different descriptions of the same process
- Blame or defensiveness about other stakeholders

### During Synthesis

Compare across interviews:
- Same topic, different facts
- Same metric, different values
- Same process, different descriptions
- Same priority, different rankings
- Same timeline, different expectations

---

## Contradiction Documentation

### Contradiction Log Template

```markdown
## Contradiction: [Brief Title]

### Type
[Factual | Perspective | Priority | Solution | Timeline]

### Stakeholder Positions

**Stakeholder A** ([Role]):
> "[Direct quote or paraphrase]"
- Context: [When/why they said this]
- Evidence: [What supports their view]

**Stakeholder B** ([Role]):
> "[Direct quote or paraphrase]"
- Context: [When/why they said this]
- Evidence: [What supports their view]

### Analysis

**Why might this contradiction exist?**
- [Possible reason 1]
- [Possible reason 2]

**Who is likely correct?**
[Assessment based on evidence]

**Does it matter?**
[Impact if unresolved]

### Resolution Approach

- [ ] Verify with data
- [ ] Probe in follow-up interviews
- [ ] Escalate for alignment
- [ ] Document as risk/assumption
- [ ] Accept both as valid perspectives

### Status
[Unresolved | Investigating | Resolved | Accepted as Risk]

### Resolution (if resolved)
[How it was resolved and what the answer is]
```

---

## Resolution Strategies

### Strategy 1: Verify with Data

For factual contradictions:

1. Identify the source of truth (database, reports, logs)
2. Pull the actual data
3. Share findings with both stakeholders
4. Document the verified fact

**Example**:
> Contradiction: Order volume disagreement
> Resolution: Pulled from order database - 4,200 average daily orders
> CEO was citing peak days, Operations citing average

---

### Strategy 2: Probe Deeper

For perspective contradictions:

1. Ask each stakeholder to explain their perspective
2. Identify the context that shapes their view
3. Find the underlying truth that explains both views
4. Document both perspectives and the synthesis

**Example**:
> Contradiction: System speed disagreement
> Resolution: SLA measures server response (200ms). Sales experiences 
> include network + rendering (3 seconds). Both are "true."

---

### Strategy 3: Escalate for Alignment

For priority contradictions:

1. Document the conflicting priorities
2. Present to decision-maker (sponsor, steering committee)
3. Get explicit prioritization decision
4. Communicate decision to all stakeholders

**Example**:
> Contradiction: Mobile vs Cost priority
> Resolution: Escalated to CEO. Decision: Cost reduction first, 
> mobile in Phase 2. Documented in project charter.

---

### Strategy 4: Find Common Ground

For solution contradictions:

1. Apply Five Whys to each proposed solution
2. Find the underlying need each addresses
3. Reframe around the common need
4. Let the need drive solution discovery

**Example**:
> Contradiction: More features vs simpler features
> Analysis: Users want to accomplish tasks. Support wants fewer errors.
> Common need: Task completion with fewer errors
> Resolution: Better UX for existing features (not more, not fewer)

---

### Strategy 5: Document as Risk

When contradictions can't be resolved:

1. Document the contradiction clearly
2. Assess impact if it remains unresolved
3. Add to risk register
4. Assign owner to monitor/resolve
5. Proceed with explicit assumption

**Example**:
> Contradiction: Timeline expectations
> Impact: If Q2 is real deadline, scope must be cut significantly
> Risk: "Timeline expectation mismatch may cause scope conflict"
> Assumption: Proceeding with Q4 plan, escalate if Q2 confirmed

---

## Contradiction Severity Assessment

| Severity | Impact | Action |
|----------|--------|--------|
| **Critical** | Blocks project if unresolved | Must resolve before proceeding |
| **High** | Significant risk if unresolved | Resolve during discovery |
| **Medium** | Causes confusion or rework | Resolve before Phase 1 |
| **Low** | Minor impact | Document, resolve later |

### Severity Indicators

**Critical**:
- Core problem definition is unclear
- Sponsor disagrees with project direction
- Timeline is impossible if one view is correct

**High**:
- Key success criteria are contradicted
- Major stakeholder groups have opposing views
- Resource assumptions differ significantly

**Medium**:
- Feature priorities differ
- Process understanding differs
- Secondary stakeholders disagree

**Low**:
- Minor factual discrepancies
- Edge case handling differs
- Nice-to-have priorities differ

---

## Handling Political Contradictions

Some contradictions are political, not factual:

### Signs of Political Contradictions

- Stakeholders won't explain their position
- Positions align with organizational territories
- History of conflict between stakeholders
- Statements change when others are present

### Approach

1. **Don't take sides** - You're facilitating, not judging
2. **Focus on facts** - Ask for data, not opinions
3. **Surface privately** - Discuss sensitive topics 1:1
4. **Escalate carefully** - Let sponsor handle politics
5. **Document neutrally** - State positions without judgment

---

## Contradiction Summary Template

For Phase 0 deliverables:

```markdown
## Contradictions Summary

### Critical Contradictions (Must Resolve)

| Contradiction | Stakeholders | Status | Resolution |
|---------------|--------------|--------|------------|
| [Description] | A vs B | [Status] | [Approach] |

### High Contradictions (Should Resolve)

| Contradiction | Stakeholders | Status | Resolution |
|---------------|--------------|--------|------------|
| [Description] | A vs B | [Status] | [Approach] |

### Accepted Contradictions (Proceeding with Risk)

| Contradiction | Assumption Made | Risk Level |
|---------------|-----------------|------------|
| [Description] | [What we're assuming] | [H/M/L] |

### Resolved Contradictions

| Contradiction | Resolution | Date |
|---------------|------------|------|
| [Description] | [How resolved] | [Date] |
```

---

## Quick Reference

### Contradiction Type Decision Tree

```
Is it about facts (numbers, dates, process)?
├── Yes → Verify with data
└── No
    Is it about importance/priority?
    ├── Yes → Escalate for alignment
    └── No
        Is it about different solutions?
        ├── Yes → Find common underlying need
        └── No → Document as perspective difference
```

### Contradiction Handling Checklist

- [ ] Contradiction identified and documented
- [ ] Type classified
- [ ] Severity assessed
- [ ] Stakeholder positions captured with quotes
- [ ] Resolution approach selected
- [ ] Resolution attempted or risk accepted
- [ ] Outcome documented
