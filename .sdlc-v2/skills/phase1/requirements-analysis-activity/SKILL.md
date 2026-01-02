---
name: requirements-analysis-activity
description: >
  Transform problem statements into technical specifications with user
  stories and acceptance criteria. Uses INVEST principles for story
  quality. Use when writing specs, creating user stories, or defining
  acceptance criteria.
required_inputs:
  - problem-statement.final.md
  - success-criteria.md
  - organization-context.md
  - feasibility-report.md
depends_on: []
---

# Requirements Analysis Activity

## Persona

You are a technical analyst who bridges business needs and technical
implementation. You create clear, testable requirements that developers
can implement confidently.

## Capabilities

- **Story Writing**: User stories following INVEST principles
- **Acceptance Criteria**: Given-When-Then scenarios
- **Decomposition**: Break epics into implementable stories
- **Traceability**: Link requirements to problem statement

## Workflow

### Step 1: Review Problem Statement

**Input**: Phase 0 problem statement, success criteria

1. Identify all user types mentioned
2. List pain points to address
3. Note constraints and assumptions
4. Map success criteria to potential features

### Step 2: Define User Personas

**Output**: Persona definitions

1. Create persona for each user type
2. Document goals and frustrations
3. Identify primary vs secondary users

### Step 3: Create Epics

**Output**: Epic list with priorities

1. Group related functionality into epics
2. Name epics by user goal achieved
3. T-shirt size epics (S/M/L/XL)
4. Prioritize by value and risk

### Step 4: Write User Stories

**Output**: Stories for each epic

For each epic:

1. Decompose into implementable stories
2. Write in format: "As a [user], I want [action], so that [benefit]"
3. Validate against INVEST criteria - see [invest-criteria.reference.md](invest-criteria.reference.md)
4. Estimate story points

### Step 5: Define Acceptance Criteria

**Output**: Stories with criteria

For each story:

1. Write Given-When-Then scenarios
2. Cover happy path and edge cases
3. Include validation rules
4. Make criteria testable

See [story-patterns.reference.md](story-patterns.reference.md) for examples.

### Step 6: Assemble Specification

**Output**: Complete spec document

Using [templates/spec.template.md](templates/spec.template.md):

1. Organize stories by epic
2. Add traceability to problem statement
3. Include glossary
4. Document assumptions

## Completion Verification

Before marking this activity complete, execute these verification checks:

### Requirement Count Validation

| Metric | Value |
|--------|-------|
| Stated Total Requirements | [Enter number from Executive Summary] |
| Actually Documented Requirements | [Count all REQ-XXX entries] |
| **Match** | YES / NO |

**If counts don't match**: Either document missing requirements OR correct the stated count in Executive Summary. Do not proceed with mismatched counts.

### Domain Coverage Check

| Domain | Expected Reqs | Documented Reqs | Complete? |
|--------|---------------|-----------------|-----------|
| [Domain 1] | [X] | [Y] | [ ] |
| [Domain 2] | [X] | [Y] | [ ] |
| [Domain 3] | [X] | [Y] | [ ] |

**All domains listed in the spec must have actual documented requirements, not placeholders.**

### User Story Verification

| Metric | Count |
|--------|-------|
| Total User Stories Claimed | [X] |
| Stories with Full Acceptance Criteria | [Y] |
| Stories with INVEST Scores | [Z] |

**All three counts must match.**

### Completeness Criteria Checklist

The requirements specification is NOT complete until ALL of the following are true:

- [ ] All requirements documented with full detail (no placeholders)
- [ ] All user stories have testable acceptance criteria
- [ ] All business rules documented with clear IF-THEN logic
- [ ] All data entities defined with complete attributes
- [ ] All integrations documented with error handling
- [ ] Stated counts match actual documented counts
- [ ] No placeholder text exists anywhere in document

**Quality Gate**: Run this checklist before requesting validation. If any item unchecked, continue work on this activity.

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
| Total functional requirements (per STATED_REQUIREMENT_COUNT) | ___ | ___ | ☐ |
| User stories (per STATED_USER_STORY_COUNT) | ___ | ___ | ☐ |
| Business rules (per STATED_BUSINESS_RULE_COUNT) | ___ | ___ | ☐ |
| Data entities defined | ___ | ___ | ☐ |
| Integration points documented | ___ | ___ | ☐ |

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

- Technical specification document
- User stories with acceptance criteria
- Traceability matrix

## Quality Checklist

- [ ] All pain points addressed by stories
- [ ] Every story passes INVEST (score ≥12)
- [ ] Each story has ≥3 acceptance criteria
- [ ] Traceability to problem statement complete
- [ ] No implementation details in stories
