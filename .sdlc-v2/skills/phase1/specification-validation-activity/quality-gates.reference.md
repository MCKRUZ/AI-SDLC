# Quality Gates Reference

## Overview

Quality gates are checkpoints that artifacts must pass before proceeding
to the next phase. They ensure quality is built in, not inspected later.

---

## Phase 1 Exit Gate

### Gate Criteria

| Category | Criterion | Required | Weight |
|----------|-----------|----------|--------|
| **Completeness** | All artifacts present | Yes | 20% |
| **Specification** | INVEST score ≥ 9 (all stories) | Yes | 15% |
| **Architecture** | ADRs for major decisions | Yes | 15% |
| **PRD** | MVP clearly defined | Yes | 10% |
| **Constitution** | Values & constraints documented | Yes | 10% |
| **Consistency** | No contradictions | Yes | 15% |
| **Traceability** | Phase 0 → Phase 1 complete | Yes | 10% |
| **Approval** | Stakeholder sign-off | Yes | 5% |

### Pass Thresholds

| Level | Score | Outcome |
|-------|-------|---------|
| Pass | 100% | Proceed to Phase 2 |
| Conditional | 80-99% | Proceed with documented exceptions |
| Fail | < 80% | Rework required |

---

## Artifact-Specific Gates

### Specification Quality Gate

| Check | Pass Criteria | Blocker? |
|-------|---------------|----------|
| All stories have AC | 100% coverage | Yes |
| INVEST scores | All ≥ 9 | Yes |
| Testable criteria | All AC testable | Yes |
| Priority assigned | All stories prioritized | No |
| Estimates present | All stories estimated | No |
| Dependencies mapped | Critical path known | No |
| Data requirements | All entities defined | Yes |
| Integration specs | All integrations documented | Yes |

**Blocker**: Must pass to proceed
**Non-blocker**: Should pass, exceptions allowed

### Architecture Quality Gate

| Check | Pass Criteria | Blocker? |
|-------|---------------|----------|
| C4 diagrams | Level 1 & 2 complete | Yes |
| Technology decisions | All documented in ADRs | Yes |
| NFR targets | All measurable | Yes |
| Security design | AuthN/AuthZ addressed | Yes |
| Scalability plan | Documented | No |
| Data model | Supports all stories | Yes |
| API spec | OpenAPI/Swagger complete | Yes |
| Deployment plan | Environments defined | No |

### PRD Quality Gate

| Check | Pass Criteria | Blocker? |
|-------|---------------|----------|
| Vision statement | Clear and inspiring | Yes |
| MVP scope | Explicitly defined | Yes |
| Features prioritized | Using consistent framework | Yes |
| Success metrics | SMART metrics defined | Yes |
| User personas | At least 2 detailed | No |
| Roadmap | Post-MVP phases outlined | No |
| Risks documented | Product risks identified | No |

### Constitution Quality Gate

| Check | Pass Criteria | Blocker? |
|-------|---------------|----------|
| Values defined | Stack ranked list | Yes |
| Non-negotiables | At least 3 listed | Yes |
| Constraints documented | Tech, resource, org | Yes |
| Decision frameworks | At least 3 frameworks | No |
| Governance | Decision rights clear | No |
| Definition of Done | Quality criteria listed | Yes |
| Team agreement | All team signed | Yes |

---

## Gate Review Process

### Pre-Review Checklist

Before requesting gate review:

- [ ] All artifacts in final state (not draft)
- [ ] Self-validation completed
- [ ] Known issues documented
- [ ] Stakeholders informed

### Review Meeting Agenda

```markdown
## Gate Review Meeting

**Duration**: 1-2 hours
**Attendees**: Product Owner, Tech Lead, Architect, QA Lead

### Agenda

1. **Overview** (10 min)
   - Recap of Phase 1 scope
   - Summary of artifacts produced

2. **Artifact Walkthrough** (30 min)
   - Specification highlights
   - Architecture overview
   - PRD/MVP summary
   - Constitution key points

3. **Quality Checks** (30 min)
   - Completeness verification
   - Consistency review
   - Traceability validation
   - Open issues discussion

4. **Gate Decision** (20 min)
   - Score calculation
   - Pass/Conditional/Fail determination
   - Action items if conditional
   - Sign-off if passing

5. **Next Steps** (10 min)
   - Phase 2 kickoff planning
   - Resource confirmation
   - Timeline review
```

### Gate Decision Matrix

| Scenario | Decision | Action |
|----------|----------|--------|
| All blockers pass, score ≥ 100% | **PASS** | Proceed to Phase 2 |
| All blockers pass, score 80-99% | **CONDITIONAL PASS** | Document exceptions, proceed |
| Any blocker fails | **FAIL** | Fix blocker, re-review |
| Score < 80% | **FAIL** | Significant rework needed |

---

## Conditional Pass Management

### Documenting Exceptions

```markdown
## Gate Exception Record

**Gate**: Phase 1 Exit
**Date**: YYYY-MM-DD
**Decision**: Conditional Pass

### Exceptions Granted

| Item | Reason | Owner | Resolution Date |
|------|--------|-------|-----------------|
| Missing API spec for integration X | Third-party not ready | [Name] | Sprint 1 |
| 2 stories below INVEST threshold | Refine in Sprint 0 | [Name] | Sprint 0 |

### Conditions for Proceeding

1. API spec must be complete before Sprint 1 planning
2. Low-INVEST stories cannot be in Sprint 1
3. Weekly status on exception resolution

### Risk Acceptance

By signing below, stakeholders accept the risk of proceeding with exceptions:

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Product Owner | | | |
| Tech Lead | | | |
| Project Sponsor | | | |
```

### Exception Tracking

Track exceptions through Phase 2:

| Exception | Status | Update |
|-----------|--------|--------|
| API spec incomplete | 🟡 In Progress | Third-party meeting scheduled |
| Low INVEST stories | 🟢 Resolved | Refined in Sprint 0 |

---

## Automated Gate Checks

### Scriptable Checks

```markdown
## Automated Validation Script

### Completeness Checks
- [ ] spec.md exists and not empty
- [ ] architecture.md exists and not empty
- [ ] prd.md exists and not empty
- [ ] constitution.md exists and not empty
- [ ] All ADRs referenced exist

### Format Checks
- [ ] All stories follow template format
- [ ] All acceptance criteria use Given-When-Then
- [ ] API spec validates against OpenAPI schema
- [ ] Data model has valid entity definitions

### Metric Checks
- [ ] All INVEST scores ≥ 9
- [ ] All NFRs have numeric targets
- [ ] All stories have priority assigned
- [ ] All stories have estimate assigned
```

### CI/CD Integration

```yaml
# .github/workflows/phase1-gate.yml
name: Phase 1 Quality Gate

on:
  pull_request:
    paths:
      - 'docs/spec.md'
      - 'docs/architecture.md'
      - 'docs/prd.md'

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - name: Check artifact completeness
        run: ./scripts/check-artifacts.sh
      
      - name: Validate story format
        run: ./scripts/validate-stories.sh
      
      - name: Check INVEST scores
        run: ./scripts/check-invest.sh
      
      - name: Generate gate report
        run: ./scripts/generate-gate-report.sh
```

---

## Gate Metrics Dashboard

### Key Metrics to Track

| Metric | Target | Actual |
|--------|--------|--------|
| Gate pass rate | > 80% | |
| Average gate attempts | < 1.5 | |
| Exception rate | < 10% | |
| Time in gate review | < 2 hours | |
| Rework time after failure | < 2 days | |

### Trend Analysis

Track over time:
- First-time pass rate
- Common failure reasons
- Time to resolve failures
- Exception resolution rate

---

## Quick Reference

### Phase 1 Gate Essentials

**Must Have** (Blockers):
- [ ] All artifacts complete
- [ ] INVEST ≥ 9 for all stories
- [ ] ADRs for major decisions
- [ ] MVP defined
- [ ] No contradictions
- [ ] Stakeholder sign-off

**Should Have** (Non-blockers):
- [ ] All estimates present
- [ ] Roadmap beyond MVP
- [ ] Risk register complete
- [ ] Full traceability

### Gate Review Checklist

- [ ] Pre-review checklist complete
- [ ] All reviewers present
- [ ] Artifacts accessible to all
- [ ] Decision documented
- [ ] Action items assigned
- [ ] Next phase planned
