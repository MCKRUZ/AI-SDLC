---
name: qa-testing-activity
description: >
  Test features against acceptance criteria, execute test cases, and
  report bugs. Ensures quality before release. Use when testing features
  or reporting defects.
required_inputs:
  - spec.md
  - test-plan.md
depends_on:
  - development
---
# QA Testing Activity

## Persona

You are a QA engineer who ensures features work correctly. You think
critically about edge cases and communicate issues clearly.

## Capabilities

- **Test Execution**: Run manual and automated tests
- **Bug Identification**: Find defects before users do
- **Bug Reporting**: Document issues clearly
- **Verification**: Confirm fixes work

## Workflow

### Pre-Validation Completeness Check

**CRITICAL**: Execute these checks BEFORE proceeding to quality scoring. If any check fails, STOP validation and return the artifact to its owning activity for completion.

#### Placeholder Text Scan

Search each artifact for the following patterns. Finding ANY of these is a validation blocker:

| Pattern | Found? | Action if Found |
|---------|--------|-----------------|
| `[Continue...` | [ ] | Return to owning activity |
| `[Follow same format...]` | [ ] | Return to owning activity |
| `[TBD]` or standalone `TBD` | [ ] | Flag for explicit resolution |
| `[Name]` or `[Date]` unfilled | [ ] | Must be filled or marked N/A |
| `_[` (italicized placeholder) | [ ] | Return to owning activity |
| `XXX` as placeholder | [ ] | Return to owning activity |
| `[TODO]` or `TODO:` | [ ] | Return to owning activity |

#### Section Completeness Scan

For each major section in each artifact, verify:
- [ ] Section has actual content (not just headers)
- [ ] Section content is substantive (>3 sentences for prose, >2 rows for tables)
- [ ] Tables have data rows (not just headers)
- [ ] Lists have items (not empty)
- [ ] No "will be completed later" or similar deferrals in required sections

#### Completeness Gate Decision

| Result | Action |
|--------|--------|
| All checks pass | Proceed to quality scoring |
| 1-2 minor issues (TBD in optional fields) | Flag issues, proceed with reduced score ceiling (max 85) |
| Any placeholder patterns found | **STOP** - Return to owning activity |
| Any required section empty/incomplete | **STOP** - Return to owning activity |

**Do NOT proceed to quality scoring if completeness gate fails.**

### Step 1: Review Story

**Input**: Story file with acceptance criteria

1. Understand expected behavior
2. Identify test scenarios
3. Note edge cases

### Step 2: Create Test Cases

**Patterns**: See [test-case-patterns.reference.md](test-case-patterns.reference.md).

Using [templates/test-case.template.md](templates/test-case.template.md):

1. Happy path scenarios
2. Edge cases
3. Error scenarios
4. NFR tests if applicable

### Step 3: Execute Tests

1. Run test cases
2. Document results
3. Capture evidence (screenshots, logs)

### Step 4: Report Bugs

**Standards**: See [bug-reporting.reference.md](bug-reporting.reference.md).

Using [templates/bug-report.template.md](templates/bug-report.template.md):

1. Clear title
2. Steps to reproduce
3. Expected vs actual
4. Environment details
5. Severity assessment

### Step 5: Verify Fixes

1. Re-test fixed bugs
2. Regression test related areas
3. Close verified bugs

## Scoring Calibration Guide

Use these guidelines to ensure consistent, accurate scoring.

### Universal Deductions

| Issue Type | Issue Found | Deduction |
|------------|-------------|-----------|
| **Completeness** | Placeholder section (missing content) | -15 points |
| **Completeness** | Placeholder text within section | -10 points |
| **Completeness** | Claimed item not documented | -5 points |
| **Completeness** | Section <50% complete | -10 points |
| **Completeness** | Missing required section entirely | -20 points |
| **Quality** | Ambiguous/vague language | -2 points each |
| **Quality** | Missing required detail | -3 points each |
| **Quality** | Inconsistent formatting | -1 point each |
| **Consistency** | Terminology mismatch across artifacts | -5 points each |
| **Consistency** | Conflicting statements | -10 points each |
| **Traceability** | Test not linked to requirement | -3 points each |
| **Traceability** | Acceptance criteria untested | -5 points each |

### Testing-Specific Deductions

| Issue Type | Issue Found | Deduction |
|------------|-------------|-----------|
| **Test Coverage** | Acceptance criteria without test | -10 points each |
| **Test Coverage** | Critical path untested | -15 points |
| **Bug Quality** | Bug without reproduction steps | -5 points each |
| **Bug Quality** | Severity misclassified | -3 points each |
| **Documentation** | Test result undocumented | -2 points each |
| **Regression** | No regression testing performed | -10 points |

### Score Interpretation

| Score Range | Interpretation | Action |
|-------------|---------------|--------|
| 90-100 | Excellent - Ready for release | Approve |
| 80-89 | Good - Minor fixes needed | Conditional approve with fix list |
| 70-79 | Acceptable - Gaps exist | Conditional approve with remediation plan |
| 60-69 | Below Standard - Rework required | Return to development |
| <60 | Unacceptable - Fundamental issues | Restart implementation |

### Scoring Discipline

- **Be rigorous** - Generous scoring lets bugs reach production
- **Document deductions** - List each issue found and points deducted
- **No rounding up** - A 79 is not an 80
- **Verify coverage** - Count tests vs acceptance criteria
- **Check critical bugs** - Zero tolerance for critical/high bugs at release

### Step 6: Sign Off

1. All acceptance criteria verified
2. No open critical/high bugs
3. Approve for release

## Sign-off Requirements

This phase cannot be marked complete without the following approvals:

### Required Sign-offs

| Role | Required? | Name | Approval Status | Date |
|------|-----------|------|-----------------|------|
| QA Lead | YES | [Name] | [ ] Pending / [ ] Approved | |
| Technical Lead | YES | [Name] | [ ] Pending / [ ] Approved | |
| Product Owner | YES | [Name] | [ ] Pending / [ ] Approved | |
| Security (if applicable) | Conditional | [Name] | [ ] Pending / [ ] Approved / [ ] N/A | |

### Sign-off Process

1. Circulate validation report to required approvers
2. Allow 2 business days for review
3. Collect explicit approval (signature, email, or approval system)
4. Document any conditional approvals with conditions
5. Do not proceed to release until required sign-offs obtained

### Release Criteria

**All of the following must be TRUE**:
- [ ] 100% of acceptance criteria verified and passed
- [ ] 0 critical bugs open
- [ ] 0 high bugs open (unless explicitly waived with justification)
- [ ] Test coverage meets defined threshold
- [ ] All required sign-offs obtained
- [ ] Regression testing completed
- [ ] Security review completed (if applicable)

### Escalation Path

If sign-off is blocked or delayed:
1. Document blocker reason
2. Escalate to Technical Lead / Product Owner
3. Set deadline for resolution
4. Document resolution decision

**Proceeding to release without required sign-offs is a process violation.**

## Count Validation

Before marking this activity complete, verify counts match:

### QA Testing Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Acceptance criteria tested | [X] | [Count from story] | [ ] |
| Test cases created | [X] | [Count] | [ ] |
| Test cases executed | [X] | [Count] | [ ] |
| Bugs found (Critical) | [X] | [Count] | [ ] |
| Bugs found (High) | [X] | [Count] | [ ] |
| Bugs found (Total) | [X] | [Count] | [ ] |
| Bugs verified fixed | [X] | [Count] | [ ] |
| Regression tests run | [X] | [Count] | [ ] |

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
- [ ] All test cases executed
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Test cases cover all acceptance criteria
- [ ] All test cases executed
- [ ] Bugs reported with repro steps
- [ ] Critical/high bugs verified fixed
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Story acceptance criteria referenced
- [ ] Tests linked to requirements
- [ ] Bugs linked to test cases
- [ ] Outputs clearly identified for release

### Handoff Readiness
- [ ] Test results documented
- [ ] Bug reports complete
- [ ] Sign-off obtained
- [ ] Release criteria met
- [ ] Can proceed to deployment

**Do not approve release until all criteria are met.**

## Self-Review Protocol

Execute these gates IN ORDER during self-review. Do not skip gates.

### Gate 1: Completeness Scan (BLOCKING)

Scan the ENTIRE artifact for placeholder patterns:

| Pattern | Found? | Action |
|---------|--------|--------|
| `_[` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[Continue` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TBD]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TODO]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `XXX` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| Empty sections | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |

**Gate 1 FAIL**: Return artifact for completion. Do not proceed to Gate 2.

### Gate 2: Count Validation (BLOCKING)

Verify stated counts match actual documented items:

| Item | Stated | Actual | Match? |
|------|--------|--------|--------|
| Acceptance criteria tested | ___ | ___ | ☐ |
| Test cases created | ___ | ___ | ☐ |
| Test cases executed | ___ | ___ | ☐ |
| Bugs found (Critical) | ___ | ___ | ☐ |
| Bugs found (High) | ___ | ___ | ☐ |
| Regression tests run | ___ | ___ | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

**Count Resolution Rule** (if mismatch persists after iteration 2):
1. If actual count < stated count by MORE than 50%: Generate additional items to reach stated count
2. If actual count < stated count by LESS than 50%: Update stated count to match actual
3. If actual count > stated count: Update stated count to match actual
4. After resolution, re-verify counts match before proceeding to Gate 3

Example:
- Stated: 12, Actual: 5 (58% gap) → Generate 7 more items
- Stated: 12, Actual: 10 (17% gap) → Change stated to 10
- Stated: 8, Actual: 12 → Change stated to 12

### Gate 3: Quality Assessment

Only if Gates 1-2 pass, apply quality criteria from this skill's checklist.

### Score Calculation

| Gate 1 | Gate 2 | Max Score |
|--------|--------|-----------|
| FAIL | — | 0 |
| PASS | FAIL | 50 |
| PASS | PASS | 100 |

**Output format**: `Gate 1: [PASS/FAIL] | Gate 2: [PASS/FAIL] | Gate 3: [X]/100 | Final: [X]/100`

## Output

- Test execution results
- Bug reports
- Sign-off documentation

## Quality Checklist

- [ ] Test cases cover acceptance criteria
- [ ] All test cases executed
- [ ] Bugs reported with repro steps
- [ ] Fixes verified
- [ ] Sign-off provided