# Sprint Planning Workflow

## Purpose

This workflow guides you through the systematic process of organizing tasks from `task-breakdown.md` into executable, demo-driven sprints. The output is a comprehensive sprint plan that the development team can immediately execute.

**What This Workflow Accomplishes**:
- Organizes tasks into time-boxed sprints (typically 2 weeks)
- Assigns tasks to team members based on skills and capacity
- Creates meaningful sprint goals focused on demonstrable value
- Validates sprint feasibility with the team
- Establishes sprint ceremonies and cadence
- Creates burndown expectations and velocity targets
- Ensures MVP scope is prioritized appropriately

**What This Workflow Does NOT Do**:
- Change task estimates (those are from task decomposition)
- Alter priorities (those come from PRD)
- Make architecture decisions (that's Phase 1)
- Assign specific work hours by day (that's daily standup territory)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Task Breakdown** (`task-breakdown.md`) - Complete task list with estimates from previous workflow
- [ ] **Dependency Map** (`dependency-map.md`) - Technical dependencies and critical path
- [ ] **PRD** (`prd.md`) - Priorities and MVP scope definition
- [ ] **Team Context** (`team-context.md`) - Team size, skills, roles, capacity
- [ ] **Estimation History** (`estimation-history.memory.md`) - Historical velocity data
- [ ] **Risk Register** (if available) - Known risks that might affect sprint planning
- [ ] **Calendar/Availability** - Team member vacations, holidays, other commitments

### Agent Setup

You should be in **Planning Agent** mode with all context loaded:

```markdown
You are the Planning Agent, an expert in agile sprint planning, capacity 
planning, and iterative delivery.

Context loaded:
- Task-breakdown.md (all tasks with estimates and dependencies)
- Dependency-map.md (technical dependencies and critical path)
- PRD.md (priorities and MVP definition)
- Team-context.md (team composition, skills, velocity)
- Estimation-history.md (historical velocity data)

Your mission: Organize tasks into executable sprints that maximize value 
delivery while respecting team capacity and technical dependencies.

Ready to begin sprint planning.
```

---

## Workflow Steps

### Step 1: Establish Sprint Parameters (30 minutes)

#### Objective
Define the fundamental parameters that will govern sprint planning.

#### Actions

**1.1 Confirm Sprint Length**

Work with the team to determine sprint duration:

```markdown
## Sprint Length Decision

**Standard Options**:
- 1 week sprints (fast feedback, high overhead)
- 2 week sprints (most common, balanced)
- 3 week sprints (lower overhead, slower feedback)
- 4 week sprints (rarely recommended)

**Factors to Consider**:
- Team experience with agile (newer teams → shorter sprints for faster learning)
- Project timeline (tighter deadline → shorter sprints for visibility)
- Deployment complexity (complex deployments → longer sprints)
- Stakeholder availability (limited availability → longer sprints)

**Recommendation**: 2 week sprints for most projects

**Decision**: [Sprint length chosen]
**Rationale**: [Why this length makes sense for this project]
```

**1.2 Calculate Team Capacity**

Determine how much work the team can realistically accomplish per sprint:

```markdown
## Team Capacity Calculation

### Team Composition
From `team-context.md`:

| Role | Name | Level | Availability | Story Points/Sprint |
|------|------|-------|--------------|---------------------|
| [Role] | [Name] | [Junior/Mid/Senior] | [%] | [SP estimate] |
| ... | ... | ... | ... | ... |

**Total Team Capacity**: [Sum of story points/sprint]

### Capacity Adjustments

**Planned Time Off**:
- [Person]: [Dates] → -[X] story points
- [Person]: [Dates] → -[Y] story points

**Other Commitments**:
- Production support: -[X]% capacity → -[Y] story points/sprint
- Meetings/ceremonies: -[Z] story points/sprint
- Onboarding new team member: -[A] story points for first 2 sprints

**Adjusted Capacity**:
- Sprint 1: [Total SP available]
- Sprint 2: [Total SP available]
- Sprint 3: [Total SP available]
- ...

**Velocity Buffer**:
Apply 80% planning rule (only plan to 80% of capacity to account for unknowns):
- Sprint 1: [80% of capacity] SP should be planned
- Sprint 2: [80% of capacity] SP should be planned
- ...
```

**1.3 Define Sprint Cadence**

Establish when sprints start/end and ceremony schedule:

```markdown
## Sprint Cadence

**Sprint Start Day**: [Day of week, typically Monday]
**Sprint End Day**: [Day of week, typically Friday]

**Sprint 0** (Setup/Preparation):
- Start: [Date]
- End: [Date]
- Goal: Infrastructure setup, repo configuration, tooling

**Sprint 1** (First feature sprint):
- Start: [Date]
- End: [Date]
- Goal: [To be determined in Step 4]

**Sprint 2**:
- Start: [Date]
- End: [Date]
- Goal: [To be determined in Step 4]

[Continue for all planned sprints]

### Ceremony Schedule

**Daily Standup**: [Time], [Duration: 15 min], [Location]
- What did I do yesterday?
- What will I do today?
- Any blockers?

**Sprint Planning**: [Day], [Time], [Duration: 2-4 hours for 2-week sprint]
- Review sprint goal
- Commit to sprint backlog
- Break down tasks if needed

**Sprint Review/Demo**: [Day], [Time], [Duration: 1-2 hours]
- Demonstrate completed work
- Get stakeholder feedback
- Update product backlog based on learnings

**Sprint Retrospective**: [Day], [Time], [Duration: 1-1.5 hours]
- What went well?
- What could be improved?
- Action items for next sprint

**Backlog Refinement** (mid-sprint): [Day], [Time], [Duration: 1 hour]
- Review upcoming stories
- Clarify requirements
- Prepare for next sprint planning
```

**Output**: Sprint parameters document with length, capacity, and cadence defined

---

### Step 2: Analyze Task Priorities and Dependencies (1-2 hours)

#### Objective
Understand the optimal sequencing of work based on business value and technical dependencies.

#### Actions

**2.1 Review Business Priorities**

Load the PRD priorities and map to tasks:

```markdown
## Business Priority Mapping

From PRD, our priorities are:

### P0 - Must Have for MVP
[List of P0 features from PRD]

**Tasks for P0 Features**:
- [TASK-001]: [Description] - [SP]
- [TASK-002]: [Description] - [SP]
- ...

**Total P0 Effort**: [Sum of SP]
**Sprints Required**: [Calculate: Total P0 SP / Team capacity per sprint]

### P1 - Should Have for MVP
[List of P1 features]

**Tasks for P1 Features**:
- [TASK-XXX]: [Description] - [SP]
- ...

**Total P1 Effort**: [Sum of SP]

### P2 - Nice to Have
[List of P2 features]

**Tasks for P2 Features**: [List tasks]
**Total P2 Effort**: [Sum of SP]

### P3 - Future Enhancements
[List of P3 features]
```

**2.2 Analyze Technical Dependencies**

Review the dependency map from task decomposition:

```markdown
## Critical Path Analysis

From `dependency-map.md`:

**Foundation Tasks** (must be completed first):
- [TASK-XXX]: [Description] → Blocks [N] other tasks
- [TASK-YYY]: [Description] → Blocks [M] other tasks

**Critical Path Tasks** (longest sequence of dependent tasks):
1. [TASK-AAA] (Sprint 0) → 
2. [TASK-BBB] (Sprint 1) → 
3. [TASK-CCC] (Sprint 2) → 
4. ...

**Duration of Critical Path**: [X] sprints minimum

**Parallelization Opportunities**:
- After [TASK-XXX] completes, [N] tasks can be done in parallel:
  - Track 1: [TASK-AAA, TASK-BBB, ...]
  - Track 2: [TASK-CCC, TASK-DDD, ...]
  - Track 3: [TASK-EEE, TASK-FFF, ...]
```

**2.3 Identify Sprint 0 Tasks**

Determine infrastructure and setup tasks that must happen before feature development:

```markdown
## Sprint 0: Infrastructure Setup

**Purpose**: Establish development infrastructure and tooling before feature work begins

**Tasks**:
- [TASK-XXX]: Repository setup and structure
- [TASK-YYY]: CI/CD pipeline configuration
- [TASK-ZZZ]: Development environment setup
- [TASK-AAA]: Database provisioning and schema
- [TASK-BBB]: Authentication/authorization framework
- [TASK-CCC]: Logging and monitoring setup
- [TASK-DDD]: Code standards and linting configuration
- [TASK-EEE]: Test framework setup

**Total Sprint 0 Effort**: [Sum of SP]

**Sprint 0 Capacity Check**:
- Capacity available: [Team capacity for Sprint 0]
- Work to be done: [Total Sprint 0 effort]
- Feasibility: [✅ Fits / ⚠️ Tight / ❌ Overloaded]

**If overloaded**: 
- Option A: Extend Sprint 0 to two sprints
- Option B: Reduce scope (what can be deferred?)
- Option C: Bring in additional help for setup
```

**Output**: Prioritized task list with dependencies clearly understood

---

### Step 3: Create Sprint Assignments (2-3 hours)

#### Objective
Assign tasks to specific sprints based on priority, dependencies, capacity, and skills.

#### Actions

**3.1 Assign Sprint 0 Tasks**

```markdown
## Sprint 0 Plan

**Sprint Goal**: "Establish complete development infrastructure and tooling"

**Tasks Assigned**:

| Task ID | Description | SP | Assigned To | Dependencies | Notes |
|---------|-------------|-------|-------------|--------------|-------|
| TASK-001 | Repository setup | 3 | [DevOps] | None | First task |
| TASK-002 | CI/CD pipeline | 5 | [DevOps] | TASK-001 | Must complete by day 3 |
| TASK-003 | Dev environment | 3 | [Senior Dev] | TASK-001 | Docker setup |
| TASK-004 | Database setup | 5 | [Backend Lead] | TASK-001 | Includes migrations |
| TASK-005 | Auth framework | 8 | [Senior Dev] | TASK-004 | Critical path |
| ... | ... | ... | ... | ... | ... |

**Total Planned**: [Sum SP] / [Available capacity] SP

**Success Criteria**:
- [ ] All developers can clone and run the application locally
- [ ] CI/CD pipeline successfully builds and tests on every commit
- [ ] Database is provisioned and migration system works
- [ ] Basic auth framework in place (even if just JWT setup)
- [ ] Code standards enforced by linting
- [ ] Tests can be run locally and in CI

**Demo**: 
- Show working local development environment
- Show successful CI/CD build
- Show basic auth flow (login endpoint returns token)
```

**3.2 Assign Feature Sprints (Sprint 1+)**

For each subsequent sprint:

```markdown
## Sprint [N] Plan

**Sprint Goal**: "[One-sentence goal focused on user value or technical capability]"

**Theme**: [What is this sprint primarily focused on?]
- Example: "User Management Core"
- Example: "Search and Discovery"
- Example: "Reporting and Analytics Foundation"

**Tasks Assigned**:

| Task ID | Description | SP | Assigned To | Dependencies | Priority | Risk |
|---------|-------------|-------|-------------|--------------|----------|------|
| TASK-XXX | [Description] | [SP] | [Person] | [Tasks] | P0 | Low |
| TASK-YYY | [Description] | [SP] | [Person] | [Tasks] | P0 | Medium |
| ... | ... | ... | ... | ... | ... | ... |

**Capacity Check**:
- Available capacity: [Team SP for this sprint]
- Planned work: [Sum of task SP]
- Buffer remaining: [Available - Planned] SP
- Status: [✅ Good / ⚠️ Tight / ❌ Overcommitted]

**Dependencies from Previous Sprints**:
- [TASK-AAA] from Sprint [N-1] must be complete
- [TASK-BBB] from Sprint [N-1] should be complete (but could slip)

**Success Criteria** (specific to this sprint):
- [ ] [Specific functional outcome 1]
- [ ] [Specific functional outcome 2]
- [ ] [Specific quality outcome]
- [ ] [Specific technical outcome]

**Demo Script** (what we'll show stakeholders):
1. [Demo step 1 - show specific user value]
2. [Demo step 2 - show specific feature working]
3. [Demo step 3 - show quality/performance aspect]

**Known Risks**:
- [Risk 1]: Mitigation: [Strategy]
- [Risk 2]: Mitigation: [Strategy]
```

Repeat this template for each sprint.

**3.3 Validate Skill Assignments**

Ensure tasks are assigned to people with appropriate skills:

```markdown
## Skill Assignment Validation

### Frontend Tasks
**Sprint [N] Frontend Load**:
- [Frontend Dev 1]: [X] SP across [N] tasks
- [Frontend Dev 2]: [Y] SP across [M] tasks
- Status: [Balanced / Overloaded / Underutilized]

### Backend Tasks
**Sprint [N] Backend Load**:
- [Backend Dev 1]: [X] SP across [N] tasks
- [Backend Dev 2]: [Y] SP across [M] tasks
- Status: [Balanced / Overloaded / Underutilized]

### Full-Stack Tasks
...

### DevOps Tasks
...

**Skill Bottlenecks Identified**:
- [Skill area]: Only [Person] can do these tasks
  - Risk: Single point of failure
  - Mitigation: Pair programming with [Other person] to cross-train

**Junior Developer Assignments**:
- Ensure junior developers have:
  - ✅ Tasks appropriate to their level
  - ✅ Senior developer assigned for pairing/mentoring
  - ✅ Mix of stretch tasks and comfortable tasks
```

**Output**: Complete sprint assignments with capacity validated

---

### Step 4: Define Sprint Goals and Demo Scenarios (1 hour)

#### Objective
Create compelling sprint goals that focus the team and provide clear demo targets.

#### Actions

**4.1 Write Sprint Goals**

Each sprint goal should:
- Be one sentence
- Focus on user value or business outcome
- Be demonstrable
- Be achievable within the sprint

```markdown
## Sprint Goals

**Sprint 0**: "Establish complete development infrastructure so all developers can contribute on Day 1 of Sprint 1"

**Sprint 1**: "Enable users to register, log in, and manage their basic profile information"
- Why: This is foundation for all user-centric features
- Demo: Show complete registration and login flow

**Sprint 2**: "Allow users to create, read, update, and delete [core entity] with basic validation"
- Why: This is the core domain object; validates our data model works
- Demo: Show full CRUD operations from UI

**Sprint 3**: "Enable users to search and filter [core entity] with real-time results"
- Why: Usability is critical; users need to find things quickly
- Demo: Show search working with 1000+ entities, <500ms response time

**Sprint 4**: "[Next most valuable feature]"
...

### MVP Completion Target
**Sprints 0-[N]** complete the MVP scope.

**Estimated MVP Completion Date**: [Calculate based on sprint count]
**Confidence Level**: [High/Medium/Low - based on risk assessment]
```

**4.2 Create Demo Scenarios**

For each sprint, write a specific demo script:

```markdown
## Sprint [N] Demo Scenario

**Duration**: 10-15 minutes
**Audience**: Product owner, stakeholders, users (if available)

**Demo Flow**:

**1. Introduction** (1 min)
   - Sprint goal recap
   - Reminder of what we're building and why

**2. Demo Core Feature** (5-7 min)
   - [Step-by-step walkthrough of the main feature]
   - [Show both happy path and error handling]
   - [Highlight any performance/quality aspects]

**3. Show Technical Achievement** (2-3 min)
   - [Show something technical that demonstrates quality]
   - Examples: Test coverage dashboard, CI/CD pipeline, monitoring

**4. Review Sprint Metrics** (2 min)
   - Velocity: [Planned SP vs. Completed SP]
   - Quality: [Bugs found, test coverage %]
   - Blockers resolved: [List any major blockers overcome]

**5. Preview Next Sprint** (1 min)
   - What we're tackling next
   - Any risks or help needed

**6. Q&A** (3-5 min)
   - Open floor for questions and feedback

**Preparation Checklist**:
- [ ] Demo environment is stable and prepped with data
- [ ] Demo script has been rehearsed
- [ ] All features work end-to-end
- [ ] Backup plan if demo environment has issues
- [ ] Screenshots/recordings prepared as backup
```

**Output**: Sprint goals and demo scenarios that focus the team

---

### Step 5: Validate Sprint Plan with Team (2-4 hours)

#### Objective
Review the sprint plan with the development team and get their commitment.

#### Actions

**5.1 Conduct Sprint Planning Session**

Hold a meeting with the entire development team:

**Agenda** (2-4 hours):

1. **Review Project Context** (15 min)
   - Constitution: Quality standards and constraints
   - Architecture: Key technical decisions
   - PRD: Business priorities and user needs

2. **Review Sprint Parameters** (10 min)
   - Sprint length, capacity, ceremony schedule
   - Confirm everyone's availability

3. **Walk Through Sprint 0** (20 min)
   - Review all tasks and assignments
   - Discuss technical approach
   - Identify any missing tasks
   - Get commitment from team

4. **Walk Through Sprint 1-[N]** (60-90 min)
   - Review each sprint's goal and tasks
   - Discuss dependencies and risks
   - Validate estimates (developers can challenge and refine)
   - Confirm skill assignments work
   - Adjust based on team feedback

5. **Review Demo Scenarios** (20 min)
   - Ensure demo targets make sense
   - Confirm they're achievable
   - Identify demo risks

6. **Address Questions and Concerns** (20 min)
   - Open floor for team questions
   - Document any concerns or reservations
   - Identify action items to address concerns

7. **Get Team Commitment** (10 min)
   - Fist-of-five vote on confidence level:
     - 5 fingers: Very confident we can do this
     - 4 fingers: Confident with minor concerns
     - 3 fingers: Concerned but willing to try
     - 2 fingers: Significant concerns, need to address
     - 1 finger: Cannot commit, too many problems
   - If average < 3, must address concerns before proceeding

**5.2 Refine Based on Team Feedback**

Common adjustments:

```markdown
## Sprint Plan Refinements

**Estimates Adjusted**:
- TASK-XXX: 5 SP → 8 SP (more complex than initially thought)
- TASK-YYY: 8 SP → 5 SP (simpler approach identified)

**Tasks Added** (discovered during planning):
- TASK-NEW-1: [Description] - [SP] (was missing from original breakdown)

**Tasks Moved Between Sprints**:
- TASK-ZZZ: Sprint 2 → Sprint 3 (dependency wasn't clear)
- TASK-AAA: Sprint 3 → Sprint 2 (can be parallelized after all)

**Sprint Goals Refined**:
- Sprint 2 goal changed to better reflect user value

**Capacity Adjustments**:
- Sprint 1: Reduced planned work by 3 SP (team velocity unknown)
- Sprint 2: Added 2 SP buffer for onboarding time

**Risks Identified**:
- [New risk found during planning]
- Mitigation: [Strategy agreed by team]
```

**5.3 Document Team Commitments**

```markdown
## Team Commitment Record

**Date**: [Date of planning session]
**Participants**: [List all attendees]

**Commitment Level**: [Average fist-of-five score]

**Team Commitments**:
- We commit to achieving the sprint goals as defined
- We commit to the sprint capacity and task assignments
- We commit to the ceremony schedule
- We commit to raising blockers immediately

**Concerns Raised**:
- [Concern 1]: [Resolution or mitigation strategy]
- [Concern 2]: [Resolution or mitigation strategy]

**Action Items Before Sprint 0**:
- [ ] [Action item 1] - Owner: [Person] - Due: [Date]
- [ ] [Action item 2] - Owner: [Person] - Due: [Date]

**Signatures/Approval**:
- Team Lead: [Name] - [Date]
- Product Owner: [Name] - [Date]
- Tech Lead: [Name] - [Date]
```

**Output**: Validated sprint plan with team commitment

---

### Step 6: Create Supporting Artifacts (1-2 hours)

#### Objective
Generate all necessary artifacts to execute and track the sprint plan.

#### Actions

**6.1 Create Sprint Backlog**

For each sprint, create a detailed backlog:

```markdown
## Sprint [N] Backlog

**Sprint Goal**: [Goal from Step 4]

**Backlog Items**:

### User Stories (if using story-based approach)
1. **US-XXX**: As a [user type], I want [goal] so that [benefit]
   - **Tasks**:
     - TASK-001: [Technical task]
     - TASK-002: [Technical task]
   - **Acceptance Criteria**:
     - [ ] [Criterion 1]
     - [ ] [Criterion 2]
   - **Story Points**: [SP]
   - **Assigned To**: [Person(s)]

2. **US-YYY**: [Next user story]
   ...

### Technical Tasks (tasks not tied to user stories)
- **TASK-XXX**: [Infrastructure task]
  - **Acceptance Criteria**: [...]
  - **Story Points**: [SP]
  - **Assigned To**: [Person]

**Backlog Status**:
- Total Items: [Count]
- Total Story Points: [Sum]
- Capacity: [Available capacity]
- Buffer: [Capacity - Planned]
```

**6.2 Create Resource Allocation Chart**

```markdown
## Resource Allocation - Sprint [N]

| Developer | Role | Capacity (SP) | Assigned (SP) | Utilization | Tasks |
|-----------|------|---------------|---------------|-------------|-------|
| [Name] | Senior FE | 13 | 11 | 85% | TASK-001, TASK-005, TASK-012 |
| [Name] | Mid BE | 8 | 8 | 100% | TASK-003, TASK-007 |
| [Name] | Junior FS | 5 | 4 | 80% | TASK-009 |
| ... | ... | ... | ... | ... | ... |

**Team Utilization**: [Average utilization %]
**Target**: 80% (leave buffer for unknowns)
**Status**: [✅ Good / ⚠️ High / ❌ Overallocated]

**Skills Distribution**:
- Frontend: [X] SP across [N] tasks
- Backend: [Y] SP across [M] tasks
- DevOps: [Z] SP across [P] tasks
- Full-stack: [A] SP across [Q] tasks
```

**6.3 Create Burn-Down Expectations**

```markdown
## Sprint [N] Burn-Down Projection

**Total Story Points**: [Total SP planned]
**Sprint Duration**: [N] working days

**Ideal Burn-Down** (assuming even velocity):
- Day 0: [Total SP] SP remaining
- Day 1: [Total - (Total/Days)] SP remaining
- Day 2: [Calculate] SP remaining
- ...
- Day [N]: 0 SP remaining

**Historical Velocity Pattern** (from past projects):
- First 20% of sprint: Slower (ramp-up, planning overhead)
- Middle 60% of sprint: Steady (normal velocity)
- Last 20% of sprint: Faster (push to finish, testing overlap)

**Expected Burn-Down** (adjusted for pattern):
- Day 0: [Total SP]
- Day 1: [Slightly less than ideal]
- Day 2-3: [Slower than ideal - ramp-up period]
- Day 4-7: [Steady burn]
- Day 8-10: [Accelerated burn - finishing and testing]

**Warning Thresholds**:
- ⚠️ Yellow: >20% behind ideal by mid-sprint
- 🚨 Red: >30% behind ideal by mid-sprint or >10% behind with 2 days left

**Action Plan if Behind**:
1. Daily standup focuses on blockers
2. Identify tasks that can be deprioritized
3. Consider moving tasks to next sprint
4. Escalate if needed
```

**6.4 Create Sprint Success Metrics**

```markdown
## Sprint [N] Success Metrics

**Velocity Metrics**:
- **Planned Velocity**: [Planned SP]
- **Target Completion**: ≥90% of planned SP completed
- **Target Predictability**: Actual velocity within ±20% of planned

**Quality Metrics**:
- **Test Coverage**: ≥80% line coverage for new code
- **Code Review**: 100% of code reviewed before merge
- **CI/CD Success Rate**: ≥95% of builds pass
- **Bugs Found**: Track all bugs, target <5 P0/P1 bugs

**Demo Metrics**:
- **Demo Prep**: Demo rehearsed 1 day before sprint review
- **Demo Success**: All planned features work in demo
- **Stakeholder Satisfaction**: ≥4/5 average rating

**Process Metrics**:
- **Daily Standup Attendance**: ≥90%
- **Blocker Resolution Time**: <24 hours average
- **Sprint Goal Achievement**: ✅ Goal met in full

**Retrospective Actions**:
- Track action items from previous retrospective
- Target: ≥80% of action items completed
```

**Output**: Complete set of sprint execution artifacts

---

### Step 7: Finalize and Document (1 hour)

#### Objective
Create the final sprint plan document and prepare for handoff to Phase 3 (Execution).

#### Actions

**7.1 Compile Final Sprint Plan Document**

Create `sprint-plan.md`:

```markdown
# Sprint Plan - [Project Name]

**Project**: [Project Name]
**Created**: [Date]
**Created By**: Planning Agent + Development Team
**Status**: Approved and Ready for Execution

---

## Executive Summary

**Total Duration**: [X] sprints over [Y] weeks
**MVP Completion Target**: Sprint [N] - [Date]
**Team Size**: [N] developers
**Estimated Velocity**: [X] story points per sprint

**High-Level Timeline**:
- Sprint 0 (Infrastructure): [Dates]
- Sprints 1-[N] (MVP Features): [Dates]
- Sprints [N+1]-[M] (Post-MVP): [Dates]

**Key Milestones**:
- [Milestone 1]: End of Sprint [N] - [Date]
- [Milestone 2]: End of Sprint [M] - [Date]

---

## Sprint Parameters

[Include from Step 1]
- Sprint length
- Team capacity
- Sprint cadence
- Ceremony schedule

---

## Sprint Details

[For each sprint, include:]
- Sprint goal
- Task assignments
- Resource allocation
- Dependencies
- Success criteria
- Demo scenario
- Risk mitigation

[Use output from Steps 3-4]

---

## Resource Allocation

[Include from Step 6.2]
- Resource allocation chart
- Skills distribution
- Utilization targets

---

## Burn-Down Projections

[Include from Step 6.3]
- Expected burn-down patterns
- Warning thresholds
- Action plans

---

## Success Metrics

[Include from Step 6.4]
- Velocity metrics
- Quality metrics
- Demo metrics
- Process metrics

---

## Risk Management

[Include risks identified during planning]

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| RISK-001 | [Description] | High | High | [Strategy] | [Person] |
| ... | ... | ... | ... | ... | ... |

---

## Dependencies

**External Dependencies** (outside the team):
- [Dependency 1]: [What we need] from [Who] by [When]
- [Dependency 2]: [What we need] from [Who] by [When]

**Internal Dependencies** (within sprints):
[Reference dependency map from task decomposition]

---

## Assumptions

Key assumptions made during sprint planning:

1. [Assumption 1 about team capacity/availability]
2. [Assumption 2 about technical complexity]
3. [Assumption 3 about stakeholder availability]
4. [Assumption 4 about infrastructure/environment]

**Validation Plan**:
- [How/when we'll validate assumption 1]
- [How/when we'll validate assumption 2]
- ...

---

## Appendices

### Appendix A: Team Commitment Record
[From Step 5.3]

### Appendix B: Sprint Backlogs
[Detailed backlogs for all sprints from Step 6.1]

### Appendix C: Historical Velocity Data
[From estimation-history.memory.md]

### Appendix D: Adjustments from Initial Decomposition
[Document any changes made from task-breakdown.md during planning]

---

## Approval

This sprint plan has been reviewed and approved by:

- **Team Lead**: [Name] - [Date]
- **Product Owner**: [Name] - [Date]
- **Tech Lead**: [Name] - [Date]
- **Architect**: [Name] - [Date]

**Team Confidence Level**: [X]/5 (from fist-of-five vote)

**Ready to Proceed**: ✅ Yes
**Next Step**: Phase 3 - Implementation (Sprint 0 begins [Date])
```

**7.2 Create Resource Allocation Document**

Create `resource-allocation.md`:

```markdown
# Resource Allocation Plan - [Project Name]

## Overview

This document details how development resources are allocated across sprints
to ensure balanced workload, skill utilization, and goal achievement.

---

## Team Composition

| Developer | Role | Level | Primary Skills | Capacity (SP/sprint) |
|-----------|------|-------|----------------|----------------------|
| [Name] | Frontend | Senior | React, TypeScript, CSS | 13 |
| [Name] | Backend | Mid | C#, .NET, SQL | 8 |
| [Name] | Full-Stack | Junior | React, C#, Learning | 5 |
| ... | ... | ... | ... | ... |

**Total Team Capacity**: [Sum] SP per sprint

---

## Sprint-by-Sprint Allocation

[For each sprint, include allocation chart from Step 6.2]

### Sprint 0 Allocation
[Chart]

### Sprint 1 Allocation
[Chart]

### Sprint 2 Allocation
[Chart]

...

---

## Skills Balance Analysis

### Frontend Workload Across Sprints
| Sprint | Frontend SP | Frontend Developers | Avg Load per Dev |
|--------|-------------|---------------------|------------------|
| Sprint 1 | [X] | [N] | [X/N] |
| Sprint 2 | [Y] | [N] | [Y/N] |
| ... | ... | ... | ... |

**Status**: [✅ Balanced / ⚠️ Unbalanced / 🚨 Overloaded]

### Backend Workload Across Sprints
[Similar table]

### DevOps Workload Across Sprints
[Similar table]

---

## Skill Bottlenecks and Mitigation

**Identified Bottlenecks**:

1. **[Skill Area] - Only [Person] has this skill**
   - **Risk**: Single point of failure
   - **Mitigation**: 
     - Pair [Person] with [Other Person] in Sprint [N]
     - [Other Person] shadows [Person] on TASK-XXX
     - Knowledge transfer session scheduled for [Date]

2. **[Another bottleneck]**
   - **Risk**: [Risk description]
   - **Mitigation**: [Strategy]

---

## Junior Developer Onboarding Plan

**[Junior Dev Name]**:
- **Sprint 0**: Onboarding, environment setup, pair with [Senior Dev]
- **Sprint 1**: Simple tasks with mentorship (TASK-XXX, TASK-YYY)
- **Sprint 2**: More complex tasks, reduced pairing time
- **Sprint 3**: Regular workload with occasional check-ins

**Target**: By Sprint 3, [Junior Dev] should be at full productivity (5 SP/sprint)

---

## Cross-Training Plan

To reduce bottlenecks and improve team resilience:

| Knowledge Area | Current Experts | Trainees | Training Sprints | Method |
|----------------|----------------|----------|------------------|---------|
| [Area 1] | [Person A] | [Person B] | Sprint 1-2 | Pairing |
| [Area 2] | [Person C] | [Person D] | Sprint 3-4 | Code reviews + pairing |
| ... | ... | ... | ... | ... |

---

## Availability Calendar

**Known Absences**:
- [Person]: [Dates] - [Reason]
- [Person]: [Dates] - [Reason]

**Impact on Sprints**:
- Sprint [N]: Reduced capacity by [X] SP
- Sprint [M]: Reduced capacity by [Y] SP

**Mitigation**: Tasks redistributed, sprint goals adjusted

---

## Utilization Targets

**Target Utilization**: 80% of capacity
- Leaves 20% buffer for unexpected work, bugs, meetings, learning

**Warning Thresholds**:
- ⚠️ Yellow: Developer at >90% utilization
- 🚨 Red: Developer at >100% utilization or <60% utilization

**Action Plan if Threshold Breached**:
- Rebalance workload immediately
- Identify tasks that can be deprioritized or moved
- Escalate to team lead
```

**Output**: Final sprint plan and resource allocation documents ready for execution

---

## Success Criteria

This sprint planning workflow is complete when:

✅ **Sprint parameters defined**: Length, capacity, cadence all established  
✅ **All tasks assigned to sprints**: Every task from task-breakdown.md is scheduled  
✅ **Resource allocation validated**: No overallocation, balanced workload  
✅ **Sprint goals defined**: Each sprint has clear, demonstrable goal  
✅ **Demo scenarios created**: Each sprint has specific demo script  
✅ **Team commitment secured**: Team voted ≥3/5 confidence level  
✅ **Dependencies managed**: Critical path understood, parallelization maximized  
✅ **Artifacts complete**: Sprint plan, resource allocation, and backlogs finalized  
✅ **Risks identified and mitigated**: Risk register updated with sprint-level risks  
✅ **Ready for execution**: Phase 3 (Implementation) can begin immediately

---

## Handoff to Phase 3 (Implementation)

With sprint planning complete, you're ready for execution:

**What Phase 3 Needs**:
1. ✅ Sprint plan with all tasks assigned
2. ✅ Resource allocation showing who does what
3. ✅ Sprint goals and demo scenarios
4. ✅ Burn-down expectations and success metrics
5. ✅ Team commitment and confidence level

**Next Workflow**: `sprint-execution.prompt.md` (Phase 3)

**Inputs to Sprint Execution**:
- `sprint-plan.md` (from this workflow)
- `resource-allocation.md` (from this workflow)
- `task-breakdown.md` (all task details)
- `architecture.md` (technical reference)
- `spec.md` (requirements reference)

Sprint execution will:
- Execute Sprint 0 (infrastructure setup)
- Execute feature sprints according to plan
- Run daily standups and track progress
- Hold sprint reviews and retrospectives
- Adjust plans based on actual velocity

---

## Troubleshooting

### Issue: Team doesn't commit (low confidence vote)

**Symptom**: Fist-of-five vote averages <3

**Root Causes**:
- Estimates seem unrealistic
- Sprint goals are unclear
- Technical approach is uncertain
- Resource allocation doesn't match skills
- Too many unknowns or risks

**Solution**:
1. Identify specific concerns through discussion
2. Address each concern systematically:
   - Unclear estimates → Add technical spike or buffer
   - Unclear goals → Refine sprint goals
   - Technical uncertainty → Schedule architecture discussion
   - Skill mismatch → Reassign tasks or add pairing
3. Revote after addressing concerns
4. If still <3, consider extending planning time or reducing scope

---

### Issue: Sprints are unbalanced

**Symptom**: Some sprints are overloaded, others underloaded

**Root Causes**:
- Dependencies force sequential work
- Skills bottlenecks (only one person can do certain tasks)
- Priorities force all P0 work into early sprints

**Solution**:
- Reexamine dependencies to find parallelization opportunities
- Cross-train team members to reduce skill bottlenecks
- Consider breaking large tasks into smaller pieces
- Spread out high-priority work if possible
- Accept some imbalance if unavoidable, but communicate clearly

---

### Issue: Can't fit MVP into available sprints

**Symptom**: MVP requires more sprints than timeline allows

**Root Causes**:
- Scope is too large for MVP
- Team velocity is lower than expected
- Too many infrastructure/setup tasks
- Estimates were too optimistic

**Solution**:
1. **Descope MVP**: Work with PM to reduce P0 features
2. **Increase team size**: Add developers (but beware onboarding cost)
3. **Extend timeline**: Negotiate deadline extension if possible
4. **Reduce quality**: NOT recommended, creates technical debt
5. **Hybrid approach**: Descope AND slightly extend timeline

**Recommendation**: Descoping is almost always the right answer for MVP

---

### Issue: Dependencies create sequential sprints (can't parallelize)

**Symptom**: Sprint N can't start until Sprint N-1 is 100% complete

**Root Causes**:
- Architecture is too coupled
- Interfaces not defined early enough
- Database schema not finalized
- Shared components have dependencies

**Solution**:
- Define interfaces early (even if implementation is stubbed)
- Use mocking to enable parallel work
- Complete foundational work in Sprint 0
- Break tight coupling in architecture if possible
- Schedule dependent work strategically

---

### Issue: Estimates keep changing during planning

**Symptom**: Task estimates grow significantly as team discusses them

**Root Causes**:
- Initial decomposition was too shallow
- Technical complexity wasn't fully understood
- Requirements are ambiguous
- Team is risk-averse and inflating estimates

**Solution**:
1. Accept that refinement is normal
2. Update task-breakdown.md with new estimates
3. Adjust sprint plans to account for new estimates
4. If estimates keep growing, consider:
   - Technical spike to reduce uncertainty
   - Breaking tasks down further
   - Getting expert input
   - Adding buffer to estimates

**Remember**: Better to discover complexity now than during execution

---

**This workflow provides a systematic approach to sprint planning that translates task breakdowns into executable, team-committed sprint plans. Follow it step-by-step to create a sprint plan that sets your team up for successful delivery.**
