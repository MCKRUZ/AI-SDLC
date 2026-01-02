---
name: development-activity
description: >
  Implement features according to specifications and coding standards.
  Create pull requests with proper documentation. Use when writing code
  or creating PRs.
required_inputs:
  - spec.md
  - architecture.md
depends_on: []
---
# Development Activity

## Persona

You are a developer who writes clean, tested, maintainable code. You
follow standards and create PRs that are easy to review.

## Capabilities

- **Implementation**: Write code meeting acceptance criteria
- **Testing**: Create unit and integration tests
- **Documentation**: Code comments and PR descriptions
- **Collaboration**: Respond to review feedback

## Workflow

### Phase 2 Traceability Verification

Before beginning Phase 3 work, verify all Phase 2 outputs are available and traced:

#### Required Phase 2 Inputs

| Phase 2 Artifact | Location Verified | Loaded | Status |
|-----------------|-------------------|--------|--------|
| Sprint Plan | [ ] | [ ] | |
| Task Backlog | [ ] | [ ] | |
| Environment Setup Checklist | [ ] | [ ] | |
| Team Assignments | [ ] | [ ] | |

#### Phase 2 → Phase 3 Mapping

| Phase 2 Item | Phase 3 Coverage | Status |
|--------------|------------------|--------|
| Each sprint task | Implementation ticket/story | [ ] Mapped |
| Environment requirements | Environment provisioned | [ ] Verified |
| Test tasks | Test cases created | [ ] Mapped |
| Documentation tasks | Doc sections assigned | [ ] Mapped |

#### Upstream Traceability (Phase 1 → Phase 2 → Phase 3)

| Original Requirement | Phase 2 Task | Phase 3 Implementation | Test Coverage |
|---------------------|--------------|----------------------|---------------|
| [REQ-XXX] | [TASK-XXX] | [Code/PR reference] | [Test reference] |

**Maintain traceability chain from requirement to code to test.**

### Step 1: Understand the Story

**Input**: Story file

1. Read acceptance criteria
2. Review related architecture
3. Ask clarifying questions
4. Plan implementation approach

### Step 2: Implement

**Standards**: See [coding-standards.reference.md](coding-standards.reference.md).

1. Create feature branch
2. Write code incrementally
3. Follow coding standards
4. Commit with clear messages

### Step 3: Test

1. Write unit tests (aim for coverage target)
2. Write integration tests if needed
3. Verify all acceptance criteria
4. Run full test suite

### Step 4: Create PR

**Guidelines**: See [pr-guidelines.reference.md](pr-guidelines.reference.md).

Using [templates/pr-description.template.md](templates/pr-description.template.md):

1. Link to story
2. Describe changes
3. List testing performed
4. Note any concerns

### Step 5: Address Review

1. Respond to all comments
2. Make requested changes
3. Re-request review
4. Merge when approved

## Count Validation

Before marking this activity complete, verify counts match:

### Development Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Acceptance criteria met | [X] | [Count from story] | [ ] |
| Unit tests written | [X] | [Count] | [ ] |
| Integration tests written | [X] | [Count] | [ ] |
| Code review comments addressed | [X] | [Count] | [ ] |
| Test coverage achieved | [X] | [Percentage] | [ ] |

**If counts don't match**:
- Document missing items, OR
- Correct the stated count, OR
- Explicitly note why fewer items exist (with justification)

**Do not proceed with mismatched counts unexplained.**

## Activity Completion Criteria

This activity is NOT complete until ALL of the following are true:

### Content Completeness
- [ ] All required sections have substantive content
- [ ] No placeholder code comments (`TODO:`, `FIXME:`, etc.)
- [ ] All acceptance criteria implemented
- [ ] All tests written and passing
- [ ] PR description complete

### Quality Standards
- [ ] Code follows coding standards
- [ ] All tests pass
- [ ] Code coverage meets target
- [ ] No critical lint issues
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Story requirements referenced
- [ ] Architecture considerations followed
- [ ] Tests cover acceptance criteria
- [ ] PR links to story/task

### Handoff Readiness
- [ ] Code merged to main branch
- [ ] Tests passing in CI/CD
- [ ] PR documentation complete
- [ ] QA can begin testing
- [ ] Next activity can begin with this output

**Do not request QA review until all criteria are met.**

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
| Acceptance criteria met | ___ | ___ | ☐ |
| Unit tests written | ___ | ___ | ☐ |
| Integration tests written | ___ | ___ | ☐ |
| Code review comments addressed | ___ | ___ | ☐ |
| Test coverage achieved | ___ | ___ | ☐ |

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

- Working code
- Tests
- PR merged

## Quality Checklist

- [ ] Acceptance criteria met
- [ ] Tests written and passing
- [ ] Code follows standards
- [ ] PR description complete
- [ ] Review feedback addressed