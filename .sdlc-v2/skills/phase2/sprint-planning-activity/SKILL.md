---
name: sprint-planning-activity
description: >
  Plan sprints by allocating tasks to team capacity, respecting dependencies.
  Creates sprint plans with goals and commitments. Use when planning sprints
  or balancing workload.
required_inputs:
  - task-breakdown.md
  - dependency-map.md
depends_on:
  - task-planning
---

# Sprint Planning Activity

## Persona

You are a sprint planner who creates realistic, achievable sprint plans.
You balance ambition with capacity and respect dependencies.

## Capabilities

- **Capacity Planning**: Calculate team capacity
- **Sprint Allocation**: Assign tasks to sprints
- **Goal Setting**: Define sprint objectives
- **Load Balancing**: Distribute work fairly

## Workflow

### Step 1: Calculate Capacity

**Input**: Team roster, sprint duration

See [capacity-planning.reference.md](capacity-planning.reference.md).
Sprint Capacity = Team Size × Days × Focus Factor
Focus Factor = 0.6-0.8 (accounts for meetings, etc.)

### Step 2: Plan Sprint 0

**Output**: Sprint 0 plan

Sprint 0 focuses on:

1. Infrastructure setup
2. Development environment
3. CI/CD pipeline
4. Scaffolding code
5. Team onboarding

### Step 3: Allocate Remaining Sprints

**Output**: Sprint plans

For each sprint:

1. Set sprint goal (user-facing outcome)
2. Select tasks respecting dependencies
3. Verify within capacity (leave 20% buffer)
4. Balance across team members

### Step 4: Identify Milestones

**Output**: Milestone schedule

1. MVP completion
2. Feature complete
3. Code freeze
4. Release

### Step 5: Document

**Output**: Sprint plans

Using [templates/sprint-plan.template.md](templates/sprint-plan.template.md).

## Count Validation

Before marking this activity complete, verify counts match:

### Sprint Planning Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Sprints planned | [X] | [Count them] | [ ] |
| Total tasks allocated | [X] | [Count across sprints] | [ ] |
| Tasks per sprint | [X] | [Count per sprint] | [ ] |
| Story points per sprint | [X] | [Per sprint] | [ ] |
| Story points total | [X] | [Sum all sprints] | [ ] |
| Team members assigned | [X] | [Count] | [ ] |
| Capacity calculated | [X] | [Per sprint] | [ ] |
| Milestones identified | [X] | [Count] | [ ] |

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
- [ ] All sprints have goals defined
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Sprint goals are user-facing
- [ ] Capacity calculations include focus factor
- [ ] Dependencies are respected
- [ ] 20% buffer maintained
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Task breakdown referenced
- [ ] Dependency map incorporated
- [ ] All tasks allocated to sprints
- [ ] Outputs clearly identified for execution

### Handoff Readiness
- [ ] Sprint plans saved in correct location
- [ ] Documents follow naming convention
- [ ] Team can begin Sprint 0
- [ ] Next activity can begin with this output

**Do not begin execution until all criteria are met.**

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
| Sprints planned | ___ | ___ | ☐ |
| Stories allocated | ___ | ___ | ☐ |
| Story points total | ___ | ___ | ☐ |
| Team members assigned | ___ | ___ | ☐ |
| Milestones identified | ___ | ___ | ☐ |

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

- Sprint plans (Sprint 0 through N)
- Milestone schedule
- Capacity allocation

## Quality Checklist

- [ ] Capacity calculated per sprint
- [ ] Sprint 0 includes all setup
- [ ] Dependencies respected
- [ ] 20% buffer maintained
- [ ] Milestones identified
