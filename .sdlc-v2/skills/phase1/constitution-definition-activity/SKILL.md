---
name: constitution-definition-activity
description: >
  Establish project values, constraints, and decision-making frameworks
  that guide the team throughout implementation. Use when defining project
  principles or creating decision frameworks.
required_inputs:
  - constraints.md
  - organization-context.md
  - risk-register.md
  - feasibility-report.md
  - phase1-handoff-package.md
depends_on:
  - architecture-design
  - product-definition
---
# Constitution Definition Activity

## Persona

You are a governance specialist who establishes clear principles and
decision frameworks. You create guardrails that empower teams while
maintaining alignment.

## Capabilities

- **Values Definition**: Articulate guiding principles
- **Constraint Documentation**: Capture non-negotiables
- **Decision Frameworks**: Create guidance for common choices
- **Trade-off Documentation**: Make priorities explicit

## Workflow

### Step 1: Gather Constraints

**Input**: All Phase 0 and Phase 1 artifacts

1. Technical constraints from architecture
2. Business constraints from PRD
3. Resource constraints from feasibility
4. Timeline constraints

### Step 2: Define Core Values

**Output**: Value statements

1. What principles guide technical decisions?
2. What do we optimize for? (speed vs quality vs cost)
3. What trade-offs are acceptable?
4. What is never acceptable?

See [values-framework.reference.md](values-framework.reference.md).

### Step 3: Create Decision Frameworks

**Output**: Decision guides

For common decision types:
1. When to build vs buy vs integrate
2. When to optimize vs ship
3. When to escalate vs decide locally
4. Technology selection criteria

### Step 4: Document Trade-off Priorities

**Output**: Priority stack rank

Example:
1. Security (never compromise)
2. Data integrity
3. User experience
4. Performance
5. Development speed

### Step 5: Define Governance

**Output**: Governance structure

1. Who makes what decisions?
2. What requires approval?
3. How are disputes resolved?
4. How does constitution evolve?

### Step 6: Create Constitution

**Output**: Constitution document

Using [templates/constitution.template.md](templates/constitution.template.md).

## Phase 0 Coverage Verification

Before completing the constitution, verify EVERY Phase 0 item is explicitly addressed:

### Hard Constraints Coverage (100% Required)

| Phase 0 ID | Constraint Description | Constitution Section | How Addressed | ✓ |
|------------|----------------------|---------------------|---------------|---|
| TC-001 | [From Phase 0] | [Section reference] | [Explanation] | [ ] |
| TC-002 | [From Phase 0] | [Section reference] | [Explanation] | [ ] |
| TC-003 | [From Phase 0] | [Section reference] | [Explanation] | [ ] |
| ... | ... | ... | ... | ... |

**Coverage Requirement**: 100% of hard constraints must have explicit constitution sections.

### Soft Constraints Coverage (90% Required)

| Phase 0 ID | Constraint Description | Constitution Section | How Addressed | ✓ |
|------------|----------------------|---------------------|---------------|---|
| SC-001 | [From Phase 0] | [Section reference] | [Explanation] | [ ] |
| ... | ... | ... | ... | ... |

### Risk Mitigation Mapping

| Phase 0 Risk ID | Risk Description | Constitution/Architecture Mitigation | ADR? | ✓ |
|-----------------|------------------|-------------------------------------|------|---|
| RISK-001 | [From Phase 0 risk register] | [Mitigation approach] | [Y/N] | [ ] |
| RISK-002 | [From Phase 0 risk register] | [Mitigation approach] | [Y/N] | [ ] |
| ... | ... | ... | ... | ... |

**Coverage Requirement**:
- All Critical (P0) risks: 100% must have documented mitigation
- All High (P1) risks: 100% must have documented mitigation
- Medium (P2) risks: 80% should have documented mitigation

### Success Criteria Traceability

| Phase 0 Success Criterion | Phase 1 Artifact | How Measured | ✓ |
|--------------------------|------------------|--------------|---|
| [Criterion 1] | [spec/architecture/prd] | [Measurement approach] | [ ] |
| [Criterion 2] | [spec/architecture/prd] | [Measurement approach] | [ ] |
| ... | ... | ... | ... |

### Sign-off Requirements

The constitution REQUIRES the following approvals before Phase 1 completion:

| Role | Required? | Name | Status |
|------|-----------|------|--------|
| Technical Lead | **YES** | [Name] | [ ] Approved |
| Security Lead | **YES** | [Name] | [ ] Approved |
| Product Owner | **YES** | [Name] | [ ] Approved |
| Compliance Officer | If regulated | [Name] | [ ] Approved / N/A |

**Do not mark constitution complete without required sign-offs.**

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
| Core values defined | ___ | ___ | ☐ |
| Hard constraints from Phase 0 (100% required) | ___ | ___ | ☐ |
| Soft constraints from Phase 0 (90% required) | ___ | ___ | ☐ |
| Decision frameworks | ___ | ___ | ☐ |
| Required sign-offs obtained | 4 | ___ | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

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

- Project constitution document
- Decision frameworks
- Governance structure

## Quality Checklist

- [ ] Core values articulated
- [ ] Constraints documented
- [ ] Trade-off priorities explicit
- [ ] Decision frameworks for common scenarios
- [ ] Governance structure defined
- [ ] Stakeholder buy-in obtained