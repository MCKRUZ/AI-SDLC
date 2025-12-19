---
name: sprint-planning-activity
description: >
  Plan sprints by allocating tasks to team capacity, respecting dependencies.
  Creates sprint plans with goals and commitments. Use when planning sprints
  or balancing workload.
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
