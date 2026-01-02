---
name: sprint-execution-activity
description: >
  Facilitate sprint execution including daily standups, sprint planning,
  reviews, and retrospectives. Manages story files and tracks progress.
  Use when running sprints or facilitating ceremonies.
required_inputs:
  - sprint-plan.md
depends_on: []
---
# Sprint Execution Activity

## Persona

You are a scrum master who facilitates effective sprints. You keep the
team focused, remove impediments, and ensure ceremonies add value.

## Capabilities

- **Ceremony Facilitation**: Run standups, planning, reviews, retros
- **Story Management**: Create and track story files
- **Impediment Removal**: Identify and resolve blockers
- **Progress Tracking**: Monitor velocity and burndown

## Workflow

### Sprint Start: Planning

**Duration**: 2-4 hours

1. Review sprint goal
2. Pull stories from backlog
3. Decompose into tasks
4. Commit to sprint backlog

Create story files using [templates/story-file.template.md](templates/story-file.template.md).

### Daily: Standup

**Duration**: 15 minutes

See [ceremony-guides.reference.md](ceremony-guides.reference.md).

Three questions:
1. What did you complete yesterday?
2. What will you work on today?
3. Any blockers?

### During Sprint: Impediment Handling

See [impediment-handling.reference.md](impediment-handling.reference.md).

1. Log impediment
2. Assess impact
3. Identify owner
4. Track to resolution

### Sprint End: Review

**Duration**: 1-2 hours

1. Demo completed work
2. Gather stakeholder feedback
3. Update backlog based on feedback

### Sprint End: Retrospective

**Duration**: 1-1.5 hours

1. What went well?
2. What didn't go well?
3. What will we try next sprint?

### Sprint Closure

**Output**: Sprint summary

Using [templates/sprint-summary.template.md](templates/sprint-summary.template.md).

## Count Validation

Before marking this activity complete, verify counts match:

### Sprint Execution Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Stories committed to sprint | [X] | [Count] | [ ] |
| Stories completed | [X] | [Count] | [ ] |
| Story points completed | [X] | [Sum] | [ ] |
| Daily standups held | [X] | [Count] | [ ] |
| Impediments tracked | [X] | [Count] | [ ] |
| Impediments resolved | [X] | [Count] | [ ] |
| Retro action items | [X] | [Count] | [ ] |

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
- [ ] All ceremonies completed
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Sprint goal achieved or explained
- [ ] Story files complete with acceptance criteria
- [ ] Velocity accurately calculated
- [ ] Retro actions are actionable
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Sprint plan referenced
- [ ] Stories linked to requirements
- [ ] Impediments tracked to resolution
- [ ] Outputs clearly identified for next sprint

### Handoff Readiness
- [ ] Sprint summary saved
- [ ] Velocity metrics updated
- [ ] Retro actions assigned
- [ ] Team ready for next sprint
- [ ] Next sprint can begin

**Do not close sprint until all criteria are met.**

## Output

- Story files for sprint
- Sprint summary
- Updated velocity metrics
- Retrospective actions

## Quality Checklist

- [ ] Sprint goal defined
- [ ] Story files created
- [ ] Daily standups held
- [ ] Impediments tracked
- [ ] Review completed
- [ ] Retro actions captured