# INVEST Scoring Reference

## Overview

INVEST is an acronym for evaluating user story quality. Each letter represents
a characteristic that good user stories should have.

---

## The INVEST Criteria

### I - Independent (0-2 points)

Stories should be self-contained with no inherent dependency on other stories.

| Score | Criteria |
|-------|----------|
| 2 | Completely independent; can be developed in any order |
| 1 | Minor dependencies exist but can be stubbed/mocked |
| 0 | Tightly coupled; cannot be completed without other stories |

**Questions to Ask:**
- Can this story be developed without waiting for another story?
- Can we reorder this in the backlog without breaking anything?
- Are dependencies technical or just logical sequencing?

---

### N - Negotiable (0-2 points)

Stories are not contracts; details can be negotiated during implementation.

| Score | Criteria |
|-------|----------|
| 2 | Captures intent, leaves room for creative solutions |
| 1 | Some flexibility but key implementation details specified |
| 0 | Prescriptive; specifies exact implementation |

**Questions to Ask:**
- Does this describe WHAT not HOW?
- Can the team propose alternative approaches?
- Is there room for conversation with the product owner?

---

### V - Valuable (0-2 points)

Stories must deliver value to users or stakeholders.

| Score | Criteria |
|-------|----------|
| 2 | Clear, direct user/business value articulated |
| 1 | Value exists but is indirect or technical |
| 0 | No clear value; purely technical task |

**Questions to Ask:**
- Would a user or stakeholder care about this?
- Can we articulate the "so that" benefit clearly?
- Does completing this move us toward a goal?

---

### E - Estimable (0-2 points)

Stories must be understood well enough to estimate effort.

| Score | Criteria |
|-------|----------|
| 2 | Team confidently estimates; well understood |
| 1 | Rough estimate possible; some unknowns |
| 0 | Cannot estimate; too vague or unknown |

**Questions to Ask:**
- Can the team give a point estimate?
- Are the acceptance criteria clear enough to estimate?
- Do we understand the technical approach?

---

### S - Small (0-2 points)

Stories should be completable within a single sprint.

| Score | Criteria |
|-------|----------|
| 2 | Fits easily in sprint with room to spare (1-5 points) |
| 1 | Fills significant sprint capacity (6-8 points) |
| 0 | Too large for single sprint; needs splitting |

**Questions to Ask:**
- Can this be completed in 1-3 days?
- Does this need to be split into smaller stories?
- Are we trying to do too much in one story?

---

### T - Testable (0-2 points)

Stories must have clear criteria for determining completion.

| Score | Criteria |
|-------|----------|
| 2 | Acceptance criteria are specific and verifiable |
| 1 | Some criteria testable; others subjective |
| 0 | No clear way to verify completion |

**Questions to Ask:**
- Can we write test cases from the acceptance criteria?
- Will we know when this is "done"?
- Are success criteria objective or subjective?

---

## Scoring Summary

| Total Score | Quality Level | Action |
|-------------|---------------|--------|
| 11-12 | Excellent | Ready for sprint |
| 9-10 | Good | Minor refinement needed |
| 7-8 | Acceptable | Refine before sprint |
| 5-6 | Poor | Significant rework needed |
| 0-4 | Unacceptable | Rewrite completely |

---

## Common INVEST Failures

### Independence Failures
- "After the user logs in..." (depends on login story)
- Technical dependencies not identified
- **Fix**: Use stubs, mocks, or feature flags

### Negotiable Failures
- "Use React with Redux and styled-components..."
- Specifying database schema in story
- **Fix**: Focus on user outcome, not implementation

### Valuable Failures
- "Refactor the authentication module"
- "Set up CI/CD pipeline"
- **Fix**: Reframe as user benefit or create as technical task

### Estimable Failures
- "Integrate with third-party API" (which one? what features?)
- Vague acceptance criteria
- **Fix**: Spike first, then write story

### Small Failures
- Epic-sized stories in backlog
- "As a user, I can manage my account"
- **Fix**: Split by user action, data type, or scenario

### Testable Failures
- "System should be fast"
- "User should have a good experience"
- **Fix**: Add specific, measurable criteria

---

## INVEST Scoring Worksheet

```markdown
## Story: [Story Title]

### Scoring

| Criterion | Score (0-2) | Notes |
|-----------|-------------|-------|
| Independent | | |
| Negotiable | | |
| Valuable | | |
| Estimable | | |
| Small | | |
| Testable | | |
| **TOTAL** | **/12** | |

### Quality Assessment
- [ ] Score ≥ 9: Ready for sprint
- [ ] Score 7-8: Needs refinement
- [ ] Score < 7: Requires rework

### Improvement Actions
1. [Action to improve lowest-scoring criterion]
2. [Action to improve second-lowest]
```

---

## Quick Reference Card

**Good Story Example:**
```
As a customer
I want to filter products by price range
So that I can find items within my budget

Acceptance Criteria:
- Given I am on the product listing page
- When I set min price to $10 and max price to $50
- Then only products priced between $10-$50 are displayed
- And the count updates to show filtered results
```

**INVEST Score: 12/12**
- Independent: Yes (no dependencies)
- Negotiable: Yes (doesn't specify UI)
- Valuable: Yes (clear user benefit)
- Estimable: Yes (well-defined scope)
- Small: Yes (single feature)
- Testable: Yes (specific criteria)
