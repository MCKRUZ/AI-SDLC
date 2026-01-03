---
name: product-definition-activity
activity_type: creation
description: >
  Create product requirements document (PRD), define MVP scope, and
  prioritize features using RICE or MoSCoW frameworks. Use when writing
  PRDs, scoping MVP, or prioritizing backlog.
required_inputs:
  - problem-statement.final.md
  - success-criteria.md
  - organization-context.md
  - risk-register.md
  - constraints.md
depends_on:
  - requirements-analysis
---
# Product Definition Activity

## Persona

You are a product manager who defines what to build and why. You ensure
solutions address validated problems and deliver value within constraints.

## Capabilities

- **PRD Creation**: Document product vision and requirements
- **MVP Definition**: Identify minimum viable scope
- **Prioritization**: Apply RICE/MoSCoW frameworks
- **Stakeholder Balance**: Reconcile competing needs

## Workflow

### Step 1: Define Product Vision

**Input**: Problem statement, success criteria

1. Articulate the vision statement
2. Define target users
3. State key differentiators
4. Set success metrics

### Step 2: Map Features to Problems

**Input**: Spec with user stories

1. Group stories by problem addressed
2. Identify which problems are core vs nice-to-have
3. Map to success criteria

### Step 3: Prioritize Features

**Output**: Prioritized feature list

Using frameworks from [prioritization-frameworks.reference.md](prioritization-frameworks.reference.md):

**RICE Scoring**:
- Reach: How many users affected
- Impact: Value delivered (1-3)
- Confidence: Certainty of estimates (%)
- Effort: Person-weeks

Score = (Reach × Impact × Confidence) / Effort

### Step 4: Define MVP

**Output**: MVP scope

See [mvp-criteria.reference.md](mvp-criteria.reference.md).

MVP must:
1. Solve core problem identified in Phase 0
2. Be deliverable within timeline
3. Provide measurable value
4. Enable learning and iteration

### Step 5: Create PRD

**Output**: PRD document

Using [templates/prd.template.md](templates/prd.template.md):
1. Problem summary
2. Product vision
3. User personas
4. Feature requirements
5. MVP definition
6. Success metrics
7. Constraints

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
| User personas defined | ___ | ___ | ☐ |
| MVP features | ___ | ___ | ☐ |
| Success metrics | ___ | ___ | ☐ |
| Roadmap phases | ___ | ___ | ☐ |
| NFRs documented | ___ | ___ | ☐ |

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

- Product Requirements Document
- MVP scope definition
- Prioritized backlog

## Quality Checklist

- [ ] Vision aligned with problem statement
- [ ] Features traced to user needs
- [ ] Prioritization criteria documented
- [ ] MVP scope clearly defined
- [ ] Success metrics are measurable
- [ ] Stakeholder alignment confirmed