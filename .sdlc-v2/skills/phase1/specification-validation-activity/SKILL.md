---
name: specification-validation-activity
description: >
  Validate all Phase 1 artifacts for completeness, consistency, and quality.
  Ensures specs, architecture, PRD, and constitution meet quality gates
  before Phase 2. Use when completing Phase 1 or reviewing specifications.
required_inputs:
  - phase1-handoff-package.md
depends_on:
  - requirements-analysis
  - architecture-design
  - product-definition
  - constitution-definition
---
# Specification Validation Activity

## Persona

You are a quality gatekeeper who ensures Phase 1 artifacts meet standards
before planning begins. You verify completeness, consistency, and alignment.

## Capabilities

- **Completeness Checking**: All required sections present
- **Consistency Validation**: Artifacts align with each other
- **Quality Scoring**: INVEST and other quality metrics
- **Gap Identification**: Missing requirements or decisions

## Workflow

### Pre-Validation Completeness Check

**CRITICAL**: Execute these checks BEFORE proceeding to quality scoring. If any check fails, STOP validation and return the artifact to its owning activity for completion.

#### Placeholder Text Scan

Search each artifact for the following patterns. Finding ANY of these is a validation blocker:

| Pattern | Artifact | Found? | Action if Found |
|---------|----------|--------|-----------------|
| `[Continue...` | All | [ ] | Return to owning activity |
| `[Follow same format...]` | All | [ ] | Return to owning activity |
| `[TBD]` or `TBD` | All | [ ] | Flag for explicit resolution |
| `[Name]` or `[Date]` placeholders | All | [ ] | Must be filled or explicitly marked N/A |
| `_[` (italicized placeholder) | All | [ ] | Return to owning activity |
| `XXX` as placeholder | All | [ ] | Return to owning activity |

#### Section Completeness Scan

For each major section in each artifact, verify:
- [ ] Section has actual content (not just headers)
- [ ] Section content is substantive (>3 sentences for prose sections)
- [ ] Tables have data rows (not just headers)
- [ ] Lists have items (not empty)

#### Completeness Gate Decision

| Result | Action |
|--------|--------|
| All checks pass | Proceed to quality scoring |
| 1-2 minor issues (TBD in non-critical fields) | Flag issues, proceed with reduced score ceiling |
| Any placeholder patterns found | **STOP** - Return to owning activity |
| Any empty sections | **STOP** - Return to owning activity |

**Do NOT proceed to quality scoring if completeness gate fails.**

### Step 1: Validate Specification

**Input**: spec.md

Using rules from [validation-rules.reference.md](validation-rules.reference.md):

1. All user types have personas
2. All pain points have stories
3. Stories pass INVEST (≥12)
4. Acceptance criteria are testable
5. Traceability complete

### Step 2: Validate Architecture

**Input**: architecture.md, ADRs

1. C4 diagrams present and complete
2. Major decisions have ADRs
3. NFRs have measurable targets
4. Security addressed
5. Aligns with spec requirements

### Step 3: Validate PRD

**Input**: prd.md

1. Vision aligns with problem statement
2. Features trace to requirements
3. MVP clearly scoped
4. Success metrics defined
5. Priorities documented

### Step 4: Validate Constitution

**Input**: constitution.md

1. Values articulated
2. Constraints documented
3. Decision frameworks present
4. Governance defined

### Step 5: Cross-Artifact Consistency

**Input**: All artifacts

1. Terminology consistent
2. Scope aligned across docs
3. No contradictions
4. Traceability to Phase 0

### Step 6: Quality Gate Review

**Input**: All validations

Using [quality-gates.reference.md](quality-gates.reference.md):

1. All mandatory checks pass
2. Quality scores meet thresholds
3. Stakeholder approvals obtained

### Step 7: Document Results

**Output**: Validation report

Using [templates/validation-report.template.md](templates/validation-report.template.md).

## Scoring Calibration Guide

Use these guidelines to ensure consistent, accurate scoring across validations.

### Completeness Score Deductions

| Issue Found | Deduction | Notes |
|-------------|-----------|-------|
| Placeholder section (entire section missing content) | -15 points | Per section |
| Placeholder text within section | -10 points | Per occurrence |
| Claimed item not documented | -5 points | Per item |
| Section <50% complete | -10 points | Per section |
| Missing required section entirely | -20 points | Per section |

### Quality Score Deductions

| Issue Found | Deduction | Notes |
|-------------|-----------|-------|
| Ambiguous requirement (vague terms) | -2 points | Per requirement |
| Requirement missing acceptance criteria | -3 points | Per requirement |
| User story failing INVEST | -2 points | Per story |
| ADR missing for major decision | -5 points | Per decision |
| NFR without measurable target | -3 points | Per NFR |
| Business rule with unclear logic | -2 points | Per rule |

### Consistency Score Deductions

| Issue Found | Deduction | Notes |
|-------------|-----------|-------|
| Terminology mismatch across artifacts | -5 points | Per term |
| NFR without architecture support | -10 points | Per NFR |
| Requirement without PRD traceability | -3 points | Per requirement |
| Phase 0 item not traced | -5 points | Per item |
| Conflicting statements across artifacts | -10 points | Per conflict |

### Traceability Score Deductions

| Issue Found | Deduction | Notes |
|-------------|-----------|-------|
| Phase 0 constraint not addressed | -10 points | Per constraint |
| Phase 0 risk without mitigation | -5 points | Per risk |
| Requirement without Phase 0 source | -3 points | Per requirement |
| Feature without requirement backing | -5 points | Per feature |

### Score Interpretation Guide

| Score Range | Interpretation | Action |
|-------------|---------------|--------|
| 90-100 | Excellent - Ready for Phase 2 | Approve |
| 80-89 | Good - Minor fixes needed | Conditional approve with fix list |
| 70-79 | Acceptable - Significant gaps exist | Conditional approve with remediation plan |
| 60-69 | Below Standard - Major rework required | Return to Phase 1 activities |
| <60 | Unacceptable - Fundamental issues | Restart Phase 1 with guidance |

### Calibration Examples

**Example 1: Requirements Spec**
- Claims 25 requirements, only 10 documented = -75 points (15 × -5)
- 3 placeholder sections = -30 points (3 × -10)
- Starting score 100, deductions 105 = Score: 0 (floor)
- **Action**: Return immediately, do not score other categories

**Example 2: Architecture**
- 1 ADR documented, 5 major decisions = -20 points (4 × -5)
- Scalability section generic (no numbers) = -15 points
- Starting score 100, deductions 35 = Score: 65
- **Action**: Conditional pass, require ADRs and scalability details

**Be rigorous. Generous scoring lets problems reach Phase 2 where they're expensive to fix.**

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
| Artifacts validated | 4 | ___ | ☐ |
| Issues identified | ___ | ___ | ☐ |
| Phase 0 items traced | ___ | ___ | ☐ |
| Requirements validated | ___ | ___ | ☐ |

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

- Validation report with pass/fail status
- Issues list with severity
- Recommended remediations
- Sign-off documentation

## Quality Checklist

- [ ] All artifacts validated
- [ ] Cross-artifact consistency verified
- [ ] Quality scores calculated
- [ ] Issues documented with severity
- [ ] Remediations identified
- [ ] Stakeholder approval obtained