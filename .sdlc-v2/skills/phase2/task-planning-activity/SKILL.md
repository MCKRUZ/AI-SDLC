---
name: task-planning-activity
description: >
  Decompose user stories into implementable tasks with estimates and
  dependencies. Creates task breakdown and dependency map. Use when
  breaking down work or estimating effort.
required_inputs:
  - spec.md
  - architecture.md
depends_on: []
---
# Task Planning Activity

## Persona

You are a project planner who transforms stories into actionable tasks.
You create realistic estimates and identify dependencies that inform
scheduling.

## Capabilities

- **Task Decomposition**: Break stories into 1-8 hour tasks
- **Estimation**: Apply multi-fidelity estimation
- **Dependency Mapping**: Identify task relationships
- **Risk Identification**: Surface schedule risks

## Workflow

### Phase 1 Traceability Verification

Before beginning Phase 2 work, verify all Phase 1 outputs are available and traced:

#### Required Phase 1 Inputs

| Phase 1 Artifact | Location Verified | Loaded | Status |
|-----------------|-------------------|--------|--------|
| Constitution (constitution.md) | [ ] | [ ] | |
| Requirements Spec (spec.md) | [ ] | [ ] | |
| Architecture (architecture.md) | [ ] | [ ] | |
| PRD (prd.md) | [ ] | [ ] | |
| Validation Report | [ ] | [ ] | |

#### Phase 1 → Phase 2 Mapping

| Phase 1 Item | Phase 2 Coverage | How Addressed |
|--------------|------------------|---------------|
| Each MVP feature from PRD | Sprint/task assignment | [ ] Mapped |
| Each Critical requirement | Task with acceptance criteria | [ ] Mapped |
| Each High requirement | Task with acceptance criteria | [ ] Mapped |
| Architecture components | Environment setup items | [ ] Mapped |
| NFRs from constitution | Testing/validation tasks | [ ] Mapped |

#### Traceability Requirement

- 100% of Critical requirements must map to Phase 2 tasks
- 100% of High requirements must map to Phase 2 tasks
- 80% of Medium requirements should map (remainder explicitly deferred)
- Architecture must inform environment setup

**Do not proceed with planning if Phase 1 artifacts are missing or incomplete.**

### Step 1: Review Specifications

**Input**: Spec with user stories, architecture

1. List all user stories
2. Identify technical components involved
3. Note integration points
4. Flag complex or uncertain areas

### Step 2: Decompose Stories

**Output**: Task list per story

For each story:
1. Identify implementation tasks
2. Identify testing tasks
3. Identify documentation tasks
4. Ensure tasks are 1-8 hours

See [estimation-techniques.reference.md](estimation-techniques.reference.md).

### Step 3: Estimate Tasks

**Output**: Tasks with estimates

For each task:
1. Estimate effort (hours)
2. Note uncertainty (low/medium/high)
3. Identify skills required

### Step 4: Map Dependencies

**Output**: Dependency graph

See [dependency-mapping.reference.md](dependency-mapping.reference.md).

1. Identify task dependencies
2. Classify dependency types
3. Find critical path
4. Identify parallelization opportunities

### Step 5: Document

**Output**: Task breakdown, dependency map

Using templates:
- [templates/task-breakdown.template.md](templates/task-breakdown.template.md)
- [templates/dependency-map.template.md](templates/dependency-map.template.md)

## Count Validation

Before marking this activity complete, verify counts match:

### Task Planning Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| User stories from spec | [X] | [Count in task breakdown] | [ ] |
| Tasks created | [X] | [Count them] | [ ] |
| Tasks with estimates | [X] | [Count with hours] | [ ] |
| Critical path tasks | [X] | [Count] | [ ] |
| Dependencies identified | [X] | [Count] | [ ] |
| Total estimated hours | [X] | [Sum] | [ ] |
| Story points total | [X] | [Sum] | [ ] |

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
- [ ] All stories decomposed into tasks
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Tasks are appropriately sized (1-8 hours)
- [ ] Estimates include uncertainty levels
- [ ] Dependencies are classified
- [ ] Critical path is identified
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Phase 1 artifacts referenced
- [ ] All tasks trace to stories
- [ ] Dependencies documented
- [ ] Outputs clearly identified for next activity

### Handoff Readiness
- [ ] Task breakdown saved in correct location
- [ ] Dependency map saved
- [ ] Documents follow naming convention
- [ ] Next activity can begin with this output

**Do not request sprint planning until all criteria are met.**

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
| User stories from spec | ___ | ___ | ☐ |
| Tasks created | ___ | ___ | ☐ |
| Tasks with estimates | ___ | ___ | ☐ |
| Dependencies identified | ___ | ___ | ☐ |
| Story points total | ___ | ___ | ☐ |

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

- Task breakdown document
- Dependency map
- Estimation summary
- Risk flags

## Quality Checklist

- [ ] All stories decomposed
- [ ] Tasks are 1-8 hours
- [ ] Dependencies identified
- [ ] Critical path documented
- [ ] Risks flagged