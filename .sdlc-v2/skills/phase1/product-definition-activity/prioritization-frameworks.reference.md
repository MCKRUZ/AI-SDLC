# Prioritization Frameworks Reference

## Overview

Prioritization frameworks help make objective decisions about what to
build first. Choose a framework based on your context and stick with it
for consistency.

---

## RICE Framework

### Components

| Factor | Description | Scale |
|--------|-------------|-------|
| **R**each | How many users affected per quarter | Actual number |
| **I**mpact | How much will it move the metric | 0.25, 0.5, 1, 2, 3 |
| **C**onfidence | How sure are we about estimates | 0-100% |
| **E**ffort | Person-months to complete | Actual estimate |

### Formula

```
RICE Score = (Reach × Impact × Confidence) / Effort
```

### Impact Scale

| Score | Meaning | Description |
|-------|---------|-------------|
| 3 | Massive | Game-changer, 2x+ improvement |
| 2 | High | Significant improvement |
| 1 | Medium | Noticeable improvement |
| 0.5 | Low | Minor improvement |
| 0.25 | Minimal | Barely noticeable |

### Confidence Scale

| Score | Meaning | Evidence |
|-------|---------|----------|
| 100% | High | Data-backed, validated |
| 80% | Medium | Some data, good intuition |
| 50% | Low | Educated guess |
| 20% | Moonshot | Pure speculation |

### Example

| Feature | Reach | Impact | Confidence | Effort | Score |
|---------|-------|--------|------------|--------|-------|
| Quick checkout | 10,000 | 2 | 80% | 2 | 8,000 |
| Wishlist | 5,000 | 1 | 80% | 1 | 4,000 |
| Dark mode | 2,000 | 0.5 | 100% | 0.5 | 2,000 |

**Priority**: Quick checkout > Wishlist > Dark mode

### When to Use RICE

- Product teams with user metrics
- Features affecting different user segments
- When effort varies significantly
- Data-driven organizations

---

## MoSCoW Framework

### Categories

| Category | Meaning | Guideline |
|----------|---------|-----------|
| **M**ust Have | Critical for release | ~60% of effort |
| **S**hould Have | Important but not critical | ~20% of effort |
| **C**ould Have | Nice to have if time permits | ~20% of effort |
| **W**on't Have | Not this release | Explicitly excluded |

### Decision Criteria

**Must Have (Mo)**
- System won't work without it
- Legally required
- Core value proposition
- No workaround possible

**Should Have (S)**
- Important but not critical
- Workaround exists (painful)
- High business value
- Expected by most users

**Could Have (C)**
- Nice to have
- Easy workaround exists
- Enhancement to core feature
- Delighters

**Won't Have (W)**
- Out of scope for this release
- Future consideration
- Too expensive for value
- Not aligned with vision

### Example

| Feature | Category | Rationale |
|---------|----------|-----------|
| User login | Must | Can't use system without it |
| Password reset | Must | Support burden without it |
| Two-factor auth | Should | Important for security |
| Social login | Could | Convenience feature |
| Biometric auth | Won't | Future mobile consideration |

### When to Use MoSCoW

- Fixed timelines
- Stakeholder alignment sessions
- MVP definition
- Contract negotiations

---

## Value vs Effort Matrix

### Quadrants

```
                 High Value
                     │
        ┌────────────┼────────────┐
        │            │            │
        │   Quick    │   Major    │
        │   Wins     │  Projects  │
 Low ───┼────────────┼────────────┼─── High
 Effort │            │            │   Effort
        │   Fill-    │   Time     │
        │   Ins      │   Sinks    │
        │            │            │
        └────────────┼────────────┘
                     │
                 Low Value
```

### Quadrant Actions

| Quadrant | Value | Effort | Action |
|----------|-------|--------|--------|
| Quick Wins | High | Low | Do first |
| Major Projects | High | High | Plan carefully |
| Fill-Ins | Low | Low | Do when convenient |
| Time Sinks | Low | High | Avoid or defer |

### When to Use

- Initial backlog triage
- Sprint planning
- Quick prioritization discussions
- When detailed scoring isn't needed

---

## Kano Model

### Categories

| Category | Description | Impact on Satisfaction |
|----------|-------------|----------------------|
| **Basic** | Expected, assumed | Dissatisfied if missing |
| **Performance** | More is better | Linear satisfaction |
| **Delighters** | Unexpected, wow factor | High satisfaction boost |
| **Indifferent** | Doesn't affect either way | No impact |
| **Reverse** | Some users don't want it | Can reduce satisfaction |

### Identification Questions

Ask users:
1. "How would you feel if this feature existed?"
2. "How would you feel if this feature didn't exist?"

| Functional (+) | Dysfunctional (-) | Category |
|----------------|-------------------|----------|
| Like | Dislike | Performance |
| Like | Neutral | Delighter |
| Neutral | Dislike | Basic |
| Neutral | Neutral | Indifferent |
| Dislike | Like | Reverse |

### Example

| Feature | Category | Priority Implication |
|---------|----------|---------------------|
| System doesn't crash | Basic | Must have |
| Fast page loads | Performance | Invest proportionally |
| AI recommendations | Delighter | Differentiate |
| Animations | Indifferent | Low priority |

### When to Use

- User experience focus
- Competitive differentiation
- Customer research
- Product positioning

---

## Weighted Scoring

### Define Criteria

| Criterion | Weight | Description |
|-----------|--------|-------------|
| Revenue potential | 30% | Direct or indirect revenue |
| Strategic alignment | 25% | Fits company direction |
| Customer demand | 20% | User requests/feedback |
| Competitive need | 15% | Market pressure |
| Technical feasibility | 10% | Ease of implementation |

### Score Each Feature

Scale: 1-5 for each criterion

| Feature | Revenue (30%) | Strategy (25%) | Demand (20%) | Compete (15%) | Tech (10%) | Total |
|---------|---------------|----------------|--------------|---------------|------------|-------|
| Feature A | 4 (1.2) | 5 (1.25) | 3 (0.6) | 4 (0.6) | 3 (0.3) | 3.95 |
| Feature B | 3 (0.9) | 4 (1.0) | 5 (1.0) | 3 (0.45) | 4 (0.4) | 3.75 |
| Feature C | 5 (1.5) | 3 (0.75) | 2 (0.4) | 2 (0.3) | 2 (0.2) | 3.15 |

### When to Use

- Multiple stakeholders with different priorities
- Need transparent, defensible decisions
- Formal product governance
- Portfolio prioritization

---

## ICE Framework

### Components

| Factor | Description | Scale |
|--------|-------------|-------|
| **I**mpact | Effect on key metric | 1-10 |
| **C**onfidence | Certainty of success | 1-10 |
| **E**ase | Ease of implementation | 1-10 |

### Formula

```
ICE Score = (Impact + Confidence + Ease) / 3
```

### Example

| Feature | Impact | Confidence | Ease | Score |
|---------|--------|------------|------|-------|
| A/B test checkout | 8 | 7 | 9 | 8.0 |
| Redesign homepage | 6 | 5 | 3 | 4.7 |
| Add reviews | 7 | 6 | 6 | 6.3 |

### When to Use

- Growth experiments
- Quick scoring needed
- Small teams
- Iterative testing

---

## Framework Selection Guide

| Situation | Recommended Framework |
|-----------|----------------------|
| Data-driven product team | RICE |
| Fixed deadline project | MoSCoW |
| Quick triage needed | Value vs Effort |
| User experience focus | Kano |
| Multiple stakeholders | Weighted Scoring |
| Growth experiments | ICE |
| MVP definition | MoSCoW + Value/Effort |

---

## Prioritization Session Template

```markdown
## Prioritization Session

**Date**: [YYYY-MM-DD]
**Participants**: [Names]
**Framework Used**: [Framework name]

### Features Evaluated

| # | Feature | [Scores] | Final Priority |
|---|---------|----------|----------------|
| 1 | | | |
| 2 | | | |

### Decisions Made

1. [Priority decision and rationale]
2. [Priority decision and rationale]

### Items Deferred

| Feature | Reason | Revisit When |
|---------|--------|--------------|
| | | |

### Action Items

- [ ] Update backlog with priorities
- [ ] Communicate decisions to stakeholders
- [ ] Schedule next prioritization review
```

---

## Quick Reference

### RICE Quick Calc

```
Score = (Users × Impact × Confidence%) / Weeks
```

### MoSCoW Quick Split

```
Must: 60% | Should: 20% | Could: 20% | Won't: Explicit
```

### Value/Effort Quick Sort

```
1. Quick Wins → 2. Major Projects → 3. Fill-ins → 4. Avoid Time Sinks
```
