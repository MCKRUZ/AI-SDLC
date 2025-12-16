# Planning Agent Chatmode

## Purpose
Focused task decomposition, estimation, and sprint planning sessions using the Planning Agent.

## When to Use This Mode
- Decomposing requirements into implementable tasks
- Estimating effort using story points and time
- Mapping dependencies between tasks
- Creating sprint plans
- Balancing workload across team members
- Identifying and managing planning risks

## Session Setup

### Before Starting
Load these artifacts into context:
1. Planning Agent instructions (`planning-agent_instructions.md`)
2. Phase 2 config (`../../config/phase2_config.md`)
3. From Phase 1:
   - Specification (`phase1/artifacts/spec.md`)
   - Architecture (`phase1/artifacts/architecture.md`)
   - PRD (`phase1/artifacts/prd.md`)
   - Constitution (`phase1/artifacts/constitution.md`)
4. Organization context (`../../memory/organization_context.md`)
5. Lessons learned (`../../memory/lessons-learned_memory.md`) - for velocity data
6. Task breakdown template (`../templates/phase2/task-breakdown_template.md`)
7. Sprint plan template (`../templates/phase2/sprint-plan_template.md`)

### Agent Instructions
Load: `planning-agent_instructions.md`

### Session Goal
Define a clear goal for the session:
- "Decompose [feature/epic] into tasks"
- "Estimate tasks for [component]"
- "Map dependencies for [feature set]"
- "Create sprint plan for sprints 1-3"
- "Balance workload across team"

---

## Interaction Patterns

### Pattern 1: Feature Decomposition Session

**When to Use**: Breaking down a feature or epic into implementable tasks

**Opening Prompt**:
```
I need to decompose [feature/epic name] into implementable tasks.

Feature Description:
[Paste from spec.md or PRD]

Architecture Context:
[Paste relevant architecture sections]

Constraints:
- Max task size: 5 days
- Tasks must be independently testable
- Must follow Definition of Done from constitution

Please help me:
1. Identify all work items needed to complete this feature
2. Break into tasks of 2-5 days each
3. Write clear acceptance criteria for each task
4. Identify technical dependencies between tasks
5. Flag any tasks that need clarification
```

**Deep Dive Prompt**:
```
Task [N]: [Task name] seems complex. Let's break it down further.

Current description:
[Paste task]

Please:
1. Identify sub-tasks within this task
2. Check if any sub-task should be its own task
3. Clarify acceptance criteria
4. Identify what makes this task "done"
```

**Closing Prompt**:
```
Please summarize the decomposition for [feature]:
1. Total number of tasks created
2. Estimated total effort (story points and days)
3. Critical path through tasks
4. Tasks flagged as high risk or uncertain
5. Dependencies requiring coordination
6. Format all tasks using the template
```

---

### Pattern 2: Task Estimation Session

**When to Use**: Estimating effort for a set of tasks

**Opening Prompt**:
```
I need to estimate these tasks:

[List tasks with descriptions]

Team Context:
- Team size: [N] developers
- Skill levels: [Senior/Mid/Junior mix]
- Historical velocity: [X] points per sprint (if known)
- Sprint length: [N] weeks

Please help me estimate each task:
1. Story points (Fibonacci: 1, 2, 3, 5, 8, 13)
2. Time estimate (in days, assuming senior developer)
3. Complexity factors (what makes it harder/easier)
4. Risk factors (what could blow up the estimate)
5. Confidence level (High/Medium/Low)
```

**Estimation Calibration Prompt**:
```
Let's calibrate our estimates. 

Here's a reference task we've done before:
- Task: [Description]
- Actual effort: [X] days
- Story points: [Y]

Using this as baseline, please re-evaluate these tasks:
[List tasks]

Are any estimates too optimistic or pessimistic?
```

**Closing Prompt**:
```
Please summarize the estimation session:
1. Total story points for all tasks
2. Total estimated days
3. High-risk estimates (low confidence)
4. Tasks that need more information before finalizing estimate
5. Recommendations for padding/contingency
```

---

### Pattern 3: Dependency Mapping Session

**When to Use**: Identifying and documenting task dependencies

**Opening Prompt**:
```
I need to map dependencies between these tasks:

[List all tasks]

Types of dependencies to identify:
1. Technical (Task A's output is Task B's input)
2. Resource (Same person needed for both)
3. External (Waiting on third party)
4. Architectural (Must follow design sequence)

Please create a dependency map showing:
1. Which tasks can start immediately (no dependencies)
2. Which tasks are blocked and by what
3. Critical path (longest chain of dependencies)
4. Parallel work opportunities
5. Potential bottlenecks
```

**Critical Path Analysis Prompt**:
```
Let's analyze the critical path.

Critical path tasks:
[List from dependency map]

Please help me:
1. Calculate total critical path duration
2. Identify which tasks are on critical path vs. have float
3. Find opportunities to shorten critical path
4. Identify risks that could extend critical path
5. Recommend mitigation strategies
```

**Closing Prompt**:
```
Please create the final dependency map including:
1. Visual representation (Mermaid diagram if possible)
2. Critical path highlighted
3. Tasks grouped by parallel execution opportunity
4. Dependencies documented in task breakdown
5. Risk assessment for dependency chains
```

---

### Pattern 4: Sprint Planning Session

**When to Use**: Creating sprint-by-sprint delivery plan

**Opening Prompt**:
```
I need to create a sprint plan for [project].

Inputs:
- Task breakdown: [Reference or paste summary]
- Dependency map: [Reference or paste summary]
- Team capacity: [X] points per sprint
- Sprint length: [N] weeks
- Number of sprints to plan: [N]
- MVP scope: [What must be in MVP]

Sprint 0 (setup) scope:
- Infrastructure setup
- CI/CD pipeline
- Development environment
- Initial scaffolding

Please create a sprint plan that:
1. Respects dependencies
2. Stays within capacity (70-80% to allow for unknowns)
3. Delivers MVP by target sprint
4. Balances risk (don't front-load all hard stuff)
5. Accounts for Sprint 0 setup
```

**Sprint Balancing Prompt**:
```
Sprint [N] looks overloaded. Let's rebalance.

Current Sprint [N]:
[List tasks and points]

Capacity: [X] points
Current load: [Y] points

Please:
1. Identify which tasks can move to Sprint [N+1]
2. Check if any dependencies prevent moving tasks
3. Ensure MVP features stay on track
4. Rebalance both sprints
```

**Closing Prompt**:
```
Please finalize the sprint plan:
1. Sprint-by-sprint task allocation
2. Story points per sprint vs. capacity
3. MVP delivery date
4. Full scope delivery date
5. Key milestones per sprint
6. Risks to the plan
7. Format using sprint plan template
```

---

### Pattern 5: Resource Allocation Session

**When to Use**: Assigning tasks to team members based on skills

**Opening Prompt**:
```
I need to allocate tasks to team members.

Team:
- [Name]: [Role], [Skills], [Availability %]
- [Name]: [Role], [Skills], [Availability %]
- [Name]: [Role], [Skills], [Availability %]

Tasks to assign (Sprint [N]):
[List tasks with skill requirements]

Please help me:
1. Match tasks to team members by skill
2. Balance workload across team
3. Identify skill gaps (tasks no one can do well)
4. Consider learning opportunities
5. Avoid single points of failure
```

**Workload Balancing Prompt**:
```
[Team member] seems overloaded. Let's rebalance.

Current allocation:
- [Name 1]: [X] points, [List tasks]
- [Name 2]: [Y] points, [List tasks]
- [Name 3]: [Z] points, [List tasks]

Please:
1. Identify tasks that can be reassigned
2. Consider skill requirements for reassignment
3. Create balanced allocation
4. Note any trade-offs (e.g., learning curve)
```

---

### Pattern 6: Risk Assessment Session

**When to Use**: Identifying and planning for execution risks

**Opening Prompt**:
```
I need to assess execution risks for this plan.

Sprint Plan Summary:
[Key points from plan]

Dependency Map:
[Key dependencies]

Please identify risks across these categories:
1. Estimation risks (what if tasks take longer?)
2. Dependency risks (what if something is delayed?)
3. Resource risks (what if someone is unavailable?)
4. Technical risks (what if something doesn't work?)
5. External risks (vendors, approvals, etc.)
6. Scope risks (what if requirements change?)

For each risk, provide:
- Probability (High/Medium/Low)
- Impact (High/Medium/Low)
- Mitigation strategy
- Trigger (how will we know it's happening?)
```

**Mitigation Planning Prompt**:
```
For risk: [Risk description]

Please develop a detailed mitigation plan:
1. Preventive actions (reduce probability)
2. Contingency plan (if it happens)
3. Early warning indicators
4. Owner responsible for monitoring
5. Resources needed for mitigation
```

---

## Best Practices for This Mode

### Do's
- ✅ Decompose to small tasks (2-5 days max)
- ✅ Every task has clear acceptance criteria
- ✅ Plan to 70-80% capacity, not 100%
- ✅ Identify dependencies early
- ✅ Use historical velocity if available
- ✅ Include contingency for unknowns
- ✅ Balance workload across team
- ✅ Track risks proactively

### Don'ts
- ❌ Don't create tasks > 5 days
- ❌ Don't plan to 100% capacity
- ❌ Don't ignore dependencies
- ❌ Don't estimate without considering who does the work
- ❌ Don't forget Sprint 0 setup time
- ❌ Don't skip risk assessment
- ❌ Don't assume estimates are accurate (they're not)

---

## Session Outputs

### Primary Artifacts
- **Task Breakdown** (`task-breakdown.md`):
  - All tasks with descriptions
  - Acceptance criteria
  - Estimates (points and days)
  - Skill requirements
  - Dependencies noted

- **Sprint Plan** (`sprint-plan.md`):
  - Sprint-by-sprint allocation
  - Capacity vs. planned load
  - Milestones
  - MVP delivery target

- **Dependency Map** (`dependency-map.md`):
  - Task dependencies visualized
  - Critical path identified
  - Parallel work opportunities

### Work-in-Progress Outputs
- Estimation worksheets
- Resource allocation drafts
- Risk registers
- What-if scenarios

---

## Quality Checks Before Ending Session

- [ ] All requirements decomposed into tasks
- [ ] All tasks < 5 days
- [ ] All tasks have acceptance criteria
- [ ] All tasks estimated (points and days)
- [ ] Dependencies mapped
- [ ] Critical path identified
- [ ] Sprint plan created
- [ ] Capacity not exceeded (70-80% target)
- [ ] MVP fits within target timeline
- [ ] Risks identified and documented
- [ ] Artifacts follow templates

---

## Transitioning Out of This Mode

**When Planning is Complete**:
- Task breakdown approved
- Sprint plan approved
- Dependencies understood
- Risks acknowledged

**Next Steps**:
- `devops-scaffolder.chatmode.md` - Set up infrastructure
- `quality-architect.chatmode.md` - Plan quality approach

**Handoff Prompt**:
```
Planning is complete. Please create a handoff summary including:
1. Total scope (tasks, points, estimated duration)
2. Sprint plan overview
3. Critical path and risks
4. Sprint 0 infrastructure requirements
5. Team assignments (if applicable)
6. Key decisions made during planning
```

---

*Created for: Phase 2 - Planning & Setup*
*Works with: Planning Agent*
*Last Updated: 2025-12-15*
