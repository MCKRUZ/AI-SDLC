# Estimation Techniques Reference

## Overview

Estimation is the process of predicting the effort, time, and resources
required to complete work. Good estimates enable realistic planning.

---

## Estimation Approaches

### 1. Story Points (Relative Sizing)

**What**: Measure complexity relative to other stories, not absolute time.

**Scale**: Modified Fibonacci (1, 2, 3, 5, 8, 13, 20)

| Points | Meaning | Example |
|--------|---------|---------|
| 1 | Trivial | Copy change, config update |
| 2 | Small | Simple bug fix, minor UI change |
| 3 | Medium | Standard feature, single component |
| 5 | Large | Multi-component feature |
| 8 | Very Large | Complex feature, multiple integrations |
| 13 | Epic-sized | Should be broken down |
| 20+ | Too big | Must be decomposed |

**Best For**: Sprint planning, velocity tracking

### 2. T-Shirt Sizing

**What**: Quick, rough sizing for high-level planning.

| Size | Effort | Story Points Equivalent |
|------|--------|------------------------|
| XS | < 2 hours | 1 |
| S | 2-4 hours | 2 |
| M | 1-2 days | 3-5 |
| L | 3-5 days | 8 |
| XL | 1-2 weeks | 13+ |

**Best For**: Roadmap planning, early estimates

### 3. Time-Based (Hours/Days)

**What**: Direct estimate of time required.

**Guidelines**:
- Tasks should be 1-8 hours
- Anything > 8 hours should be broken down
- Include buffer for unknowns (20-50%)

**Best For**: Sprint task planning, detailed schedules

---

## Estimation Techniques

### Planning Poker

**Process**:
1. Product Owner presents story
2. Team discusses requirements
3. Each member selects a card privately
4. All reveal simultaneously
5. Discuss outliers
6. Re-vote until consensus

**Tips**:
- Highest and lowest explain their reasoning
- Focus on relative complexity, not hours
- Use reference stories for calibration

### Three-Point Estimation

**Formula**: `E = (O + 4M + P) / 6`

| Variable | Meaning |
|----------|---------|
| O | Optimistic (best case) |
| M | Most Likely (typical case) |
| P | Pessimistic (worst case) |

**Example**:
- Optimistic: 2 days
- Most Likely: 4 days
- Pessimistic: 10 days
- **Estimate**: (2 + 16 + 10) / 6 = **4.7 days**

### Reference Story Comparison

**Process**:
1. Identify well-understood completed stories
2. Use as calibration points
3. Compare new stories to references

**Example Reference Stories**:
- "Login page" = 3 points
- "User CRUD" = 5 points
- "Payment integration" = 13 points

---

## Task Decomposition

### Breaking Down Stories

A story should be decomposed into tasks when:
- Estimate > 8 hours
- Multiple skills required
- Multiple components involved
- Dependencies exist within the story

### Task Types

| Type | Example | Typical Size |
|------|---------|--------------|
| Implementation | "Create UserService" | 2-8 hours |
| Testing | "Write unit tests for UserService" | 1-4 hours |
| Integration | "Connect to payment API" | 2-4 hours |
| Documentation | "Update API docs" | 1-2 hours |
| Review | "Code review" | 0.5-2 hours |

---

## Estimation Pitfalls

### Common Mistakes

| Mistake | Impact | Solution |
|---------|--------|----------|
| Optimism bias | Underestimate | Use historical data |
| Forgetting testing | 30-50% underestimate | Always include test time |
| Ignoring integration | Surprises late | Estimate integration separately |
| Not accounting for meetings | Lost capacity | Use focus factor (0.6-0.8) |
| Anchoring | Groupthink | Use Planning Poker |

### Cone of Uncertainty

Estimate accuracy improves as you learn more:

| Phase | Accuracy Range |
|-------|----------------|
| Initial concept | 4x - 0.25x |
| After requirements | 2x - 0.5x |
| After design | 1.5x - 0.67x |
| After detailed planning | 1.25x - 0.8x |

---

## Improving Estimates

### Track Actuals

| Story | Estimated | Actual | Variance |
|-------|-----------|--------|----------|
| US-001 | 5 SP | 5 SP | 0% |
| US-002 | 3 SP | 5 SP | +67% |
| US-003 | 8 SP | 6 SP | -25% |

### Calculate Velocity

```
Velocity = Story Points Completed / Sprint

Rolling Average = (Sprint N + N-1 + N-2) / 3
```

### Adjust for Team Composition

| Factor | Adjustment |
|--------|------------|
| New team member | +20-30% |
| New technology | +30-50% |
| Legacy code | +20-40% |
| High uncertainty | +50%+ |

---

## Quick Reference

**For a new story**:
1. Understand acceptance criteria
2. Identify components involved
3. Compare to reference stories
4. Account for testing, integration, unknowns
5. Use Planning Poker for team estimate

**For task breakdown**:
1. List all work types (code, test, docs)
2. Estimate each in hours
3. Verify tasks are 1-8 hours each
4. Sum for total, add 20% buffer
