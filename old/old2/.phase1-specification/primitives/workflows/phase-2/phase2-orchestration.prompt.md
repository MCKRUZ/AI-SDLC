# Phase 2 Orchestration Workflow - Planning & Setup

## Purpose

This workflow orchestrates the complete **Phase 2: Planning & Setup** process, transforming Phase 1 specifications into executable plans and development-ready infrastructure. Phase 2 is the bridge between "what to build" (Phase 1) and "building it" (Phase 3).

**What Phase 2 Accomplishes**:
- Decomposes requirements into implementable tasks
- Creates realistic sprint plans based on team capacity
- Maps technical dependencies and critical paths
- Sets up development infrastructure (repos, CI/CD, environments)
- Defines comprehensive quality standards and test strategy
- Identifies and mitigates implementation risks
- Prepares everything needed for Phase 3 development to start

**What Phase 2 Does NOT Do**:
- Write production code (that's Phase 3)
- Make architectural decisions (that's Phase 1)
- Change requirements or priorities (that's Phase 1)
- Execute the development work (that's Phase 3)

---

## Prerequisites

### Required Phase 1 Artifacts

All of these must be complete and validated before starting Phase 2:

- [ ] **Constitution** (`constitution.md`) - Project principles and quality standards
- [ ] **Requirements Specification** (`spec.md`) - All functional and non-functional requirements
- [ ] **Product Requirements Document** (`prd.md`) - Product vision, personas, priorities
- [ ] **Architecture Document** (`architecture.md`) - Technical design and component structure
- [ ] **Data Model** (`data-model.md`) - Database schema and relationships
- [ ] **API Specification** (`api-spec.json`) - Integration contracts
- [ ] **Phase 1 Completion Checklist** - Validated and signed off

### Required Context & Memory Files

- [ ] **Organization Context** (`organization.context.md`) - Company information
- [ ] **Technical Stack Context** (`technical-stack.context.md`) - Technology constraints
- [ ] **Team Context** (`team-context.md`) - Team size, skills, capacity, velocity
- [ ] **Prior Projects Memory** (`prior-projects.memory.md`) - Historical project data
- [ ] **Estimation History** (`estimation-history.memory.md`) - Team velocity metrics
- [ ] **Lessons Learned** (`lessons-learned.memory.md`) - Past project insights

### Team Readiness

- [ ] Development team identified and available
- [ ] Team capacity calculated (available hours per sprint)
- [ ] Team skill matrix documented
- [ ] Historical velocity data available (if existing team)
- [ ] Infrastructure requirements understood

### Stakeholder Alignment

- [ ] Phase 1 artifacts reviewed and approved
- [ ] Budget confirmed for Phase 2 and Phase 3
- [ ] Timeline expectations set
- [ ] Key stakeholders identified for progress reviews

---

## Phase 2 Overview

### The Complete Phase 2 Journey

```
Phase 1 Outputs          Phase 2 Activities                    Phase 3 Inputs
─────────────────        ──────────────────                    ──────────────
                                                              
Constitution         ──> 1. Task Decomposition           ──>  Task Breakdown
Spec.md              ──>    (2-3 days)                   ──>  Sprint Plan
PRD.md               ──>                                 ──>  
Architecture.md      ──> 2. Dependency Analysis          ──>  Dependency Map
Data-Model.md        ──>    (1-2 days)                   ──>  
API-Spec.json        ──>                                 ──>  
                         3. Sprint Planning              ──>  Development Repo
                         ──>    (2-3 days)                   ──>  CI/CD Pipeline
                                                              
                         4. Repository Setup             ──>  Quality Standards
                         ──>    (2-3 days)                   ──>  Test Strategy
                                                              
                         5. Quality Planning             ──>  Risk Register
                         ──>    (1-2 days)                   ──>  
                                                              
                         6. Risk Assessment              ──>  Phase 2 Report
                         ──>    (1 day)                      ──>  
                                                              
                         7. Validation & Sign-off        ──>  Sprint 0 Ready
                         ──>    (1 day)                      ──>  
                                                              
                         Total: 10-14 days
```

### Phase 2 Agents & Workflows

| Activity | Primary Agent | Workflow | Estimated Time | Output Artifacts |
|----------|--------------|----------|----------------|------------------|
| Task Decomposition | Planning Agent | `task-decomposition.prompt.md` | 2-3 days | `task-breakdown.md` |
| Dependency Analysis | Planning Agent | (Part of task decomposition) | (Included) | `dependency-map.md` |
| Sprint Planning | Planning Agent | `sprint-planning.prompt.md` | 2-3 days | `sprint-plan.md`, `resource-allocation.md` |
| Repository Setup | DevOps Scaffolder | `repository-setup.prompt.md` | 2-3 days | Working repo + CI/CD |
| Quality Planning | Quality Architect | `quality-planning.prompt.md` | 1-2 days | `quality-strategy.md`, `test-plan.md` |
| Risk Assessment | Planning Agent | `risk-assessment.prompt.md` | 1 day | `risk-register.md` |
| Validation | Validator | (Manual review) | 1 day | `phase2-completion.checklist.md` |

### Session Strategy

Phase 2 should use **focused sessions** to prevent context collapse:

1. **Planning Session** (Task decomposition, dependency analysis, sprint planning)
2. **Infrastructure Session** (Repository setup, CI/CD configuration)
3. **Quality Session** (Test strategy, quality standards, test planning)
4. **Risk & Validation Session** (Risk assessment, final validation)

Each session should:
- Load only relevant context
- Focus on one primary output
- Produce validated artifacts
- Hand off cleanly to next session

---

## Step-by-Step Orchestration

### Step 0: Phase 2 Kickoff (1-2 hours)

#### Objective
Ensure all prerequisites are met and team is ready to begin planning.

#### Actions

**0.1 Validate Phase 1 Completion**

Use the Phase 1 Completion Checklist:

```bash
# Review Phase 1 completion status
open specs/phase-1-completion.checklist.md

# Verify all critical criteria met:
# - Constitution: Must be 8/8
# - Spec: Must be 11/11
# - PRD: Must be 10/10
# - Architecture: Must be 11/11
# - Data Model: Must be 7/7
# - API Spec: Must be 6/6
```

**If any critical criteria not met**: STOP and return to Phase 1. Do not proceed.

**0.2 Review All Phase 1 Artifacts**

Conduct a **comprehensive read-through** of all Phase 1 outputs:

```markdown
## Phase 1 Artifacts Review Checklist

**Constitution** (`constitution.md`):
- [ ] Project vision clear and compelling
- [ ] Quality standards explicit and measurable
- [ ] Technical constraints documented
- [ ] Decision-making framework defined
- [ ] Success criteria from Phase 0 incorporated

**Requirements Specification** (`spec.md`):
- [ ] All functional requirements have IDs and acceptance criteria
- [ ] Non-functional requirements quantified
- [ ] Priorities assigned (Must/Should/Could/Won't)
- [ ] Traceability to problem statement maintained
- [ ] Version history shows stakeholder validation

**Product Requirements Document** (`prd.md`):
- [ ] User personas defined with goals and behaviors
- [ ] User journeys mapped for primary workflows
- [ ] MVP scope clearly bounded
- [ ] Features prioritized with rationale
- [ ] Success metrics defined

**Architecture Document** (`architecture.md`):
- [ ] System context diagram (C4 Level 1) present
- [ ] Container architecture (C4 Level 2) defined
- [ ] Component design (C4 Level 3) detailed
- [ ] Technology choices justified
- [ ] Architectural Decision Records (ADRs) documented
- [ ] Scalability and performance considerations addressed
- [ ] Security design included

**Data Model** (`data-model.md`):
- [ ] Entity relationship diagram complete
- [ ] All entities have attributes and relationships
- [ ] Indexes identified for performance
- [ ] Data migration strategy defined
- [ ] Data validation rules specified

**API Specification** (`api-spec.json`):
- [ ] All endpoints documented with request/response schemas
- [ ] Authentication and authorization specified
- [ ] Error responses defined
- [ ] Rate limiting and throttling addressed
- [ ] Versioning strategy clear
```

**0.3 Load Context & Memory**

Ensure all relevant organizational context is available:

```markdown
## Context Loading Checklist

**Organization Context** (`organization.context.md`):
- [ ] Company name, size, industry documented
- [ ] Existing systems and integrations listed
- [ ] Compliance requirements noted
- [ ] Brand guidelines and standards referenced

**Technical Stack Context** (`technical-stack.context.md`):
- [ ] Programming languages and frameworks specified
- [ ] Database technologies defined
- [ ] Cloud platform identified
- [ ] CI/CD tools documented
- [ ] Development tools and IDEs listed

**Team Context** (`team-context.md`):
- [ ] Team size and composition documented
- [ ] Skill levels and specializations mapped
- [ ] Available capacity calculated (hours per sprint)
- [ ] Team velocity known (if existing team)
- [ ] Team methodology documented (Scrum, Kanban, etc.)

**Prior Projects Memory** (`prior-projects.memory.md`):
- [ ] Similar past projects identified
- [ ] Patterns and learnings extracted
- [ ] Estimation accuracy data available

**Estimation History** (`estimation-history.memory.md`):
- [ ] Historical velocity data reviewed
- [ ] Team's estimation accuracy analyzed
- [ ] Adjustment factors identified

**Lessons Learned** (`lessons-learned.memory.md`):
- [ ] Past mistakes and how to avoid them
- [ ] Successful patterns to replicate
- [ ] Team-specific best practices
```

**0.4 Set Up Phase 2 Session Structure**

Create the directory structure for Phase 2 work:

```bash
# Create Phase 2 session directory
mkdir -p .phase2/sessions/[project-name]-planning

# Create subdirectories
cd .phase2/sessions/[project-name]-planning
mkdir -p artifacts
mkdir -p working
mkdir -p validation
mkdir -p infrastructure

# Copy Phase 1 artifacts for reference
cp ../../../specs/*.md working/reference/

# Create session metadata
cat > session.meta.md << EOF
# Phase 2 Session Metadata

**Project**: [Project Name]
**Session Start**: $(date)
**Phase 1 Sign-off Date**: [Date from Phase 1 checklist]
**Team Size**: [N developers]
**Target Sprint Length**: [1/2/3/4 weeks]
**Estimated Phase 2 Duration**: 10-14 days
**Target Phase 3 Start Date**: [Date]

## Session Goals
1. Create task breakdown with realistic estimates
2. Map all technical dependencies
3. Plan first 3-5 sprints with MVP focus
4. Set up development infrastructure
5. Define comprehensive quality standards
6. Assess and mitigate implementation risks
7. Validate readiness for Phase 3

## Participants
- **Planning Agent**: Task decomposition, sprint planning
- **DevOps Scaffolder**: Infrastructure setup
- **Quality Architect**: Test strategy, quality standards
- **Validator**: Final validation and sign-off

## Success Criteria
- All requirements decomposed into <5 day tasks
- Dependencies mapped with critical path identified
- Sprint plans fit within team capacity
- Repository ready for first commit
- CI/CD pipeline functional
- Quality standards measurable and testable
- All risks identified with mitigation plans
- Stakeholder approval to proceed to Phase 3
EOF
```

**0.5 Conduct Kickoff Meeting**

Gather stakeholders for Phase 2 kickoff:

**Attendees**:
- Development team lead
- Product manager
- Solutions architect
- DevOps engineer
- QA lead
- Project sponsor

**Agenda** (1 hour):

1. **Review Phase 1 Outputs** (15 min)
   - Walk through key decisions from Phase 1
   - Highlight any areas of complexity or risk
   - Confirm shared understanding

2. **Introduce Phase 2 Goals** (10 min)
   - Explain Phase 2 purpose and activities
   - Set expectations for deliverables
   - Define timeline (10-14 days)

3. **Discuss Team Capacity** (15 min)
   - Confirm team availability
   - Identify any constraints (vacations, other projects)
   - Calculate available capacity for upcoming sprints

4. **Identify Known Risks** (10 min)
   - Technical uncertainties
   - Resource constraints
   - External dependencies
   - Timeline pressures

5. **Define Communication Norms** (10 min)
   - How often to sync during Phase 2
   - How to raise blockers
   - Decision-making authority
   - Escalation path

**Output**: Kickoff meeting notes, team commitment, agreed timeline

**Decision Point**: Ready to proceed to Step 1?
- ✅ Yes → Continue to Task Decomposition
- ❌ No → Document blockers, resolve them, then restart Step 0

---

### Step 1: Task Decomposition (2-3 days)

#### Objective
Break down all requirements from `spec.md` into implementable, estimable tasks organized by feature area.

#### Agent: Planning Agent
Load: `.phase2/primitives/agents/planning-agent.instructions.md`

#### Workflow
Follow: `.phase2/primitives/workflows/task-decomposition.prompt.md`

#### Context to Provide

```markdown
## Task Decomposition Context

**Your Mission**: Decompose all requirements from spec.md into implementable 
tasks that the development team can execute.

**Inputs**:
- Constitution (quality standards and constraints)
- Requirements Specification (all functional and non-functional requirements)
- PRD (priorities and MVP scope)
- Architecture (technical design and component structure)
- Team Context (skills, capacity, methodology)
- Estimation History (historical velocity data)

**Your Outputs**:
1. Work Breakdown Structure (WBS) - hierarchical task organization
2. Task Breakdown - all tasks with estimates and acceptance criteria
3. Dependency Map - technical dependencies between tasks
4. Risk-flagged tasks - tasks with high uncertainty

**Constraints**:
- Every requirement must be traceable to tasks
- Tasks must be 2-5 days max (smaller is better)
- Each task must have clear acceptance criteria
- Estimates must be based on team's historical velocity
- Must respect architectural design and component boundaries

**Quality Standards**:
- INVEST criteria for user stories (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- All tasks have story points AND time estimates
- Dependencies explicitly documented
- No orphaned requirements (all have tasks)

Begin with feature grouping from requirements.
```

#### Actions

**1.1 Load Planning Agent**

Start a new chat session with Planning Agent persona:

```markdown
You are the Planning Agent, an expert in agile planning, task decomposition, 
estimation, and sprint planning.

Load the following context:
- Constitution.md
- Spec.md
- PRD.md
- Architecture.md
- Team-context.md
- Estimation-history.md

Your goal is to create a comprehensive task breakdown that decomposes all 
requirements into implementable work items.

Confirm you have loaded all context and are ready to begin.
```

**1.2 Execute Task Decomposition Workflow**

Follow the complete task decomposition workflow:

```bash
# The workflow will guide you through:
# 1. Requirements analysis and grouping
# 2. Epic creation for feature areas
# 3. Story creation from requirements
# 4. Task breakdown for each story
# 5. Estimation using story points and hours
# 6. Dependency identification
# 7. Risk assessment for each task
```

**Expected Duration**: 2-3 days (depending on project complexity)

**1.3 Review Task Breakdown Output**

The Planning Agent will produce `task-breakdown.md`. Validate it has:

```markdown
## Task Breakdown Validation Checklist

**Completeness**:
- [ ] All functional requirements from spec.md have corresponding tasks
- [ ] All non-functional requirements addressed (performance, security, etc.)
- [ ] Infrastructure tasks included (CI/CD, environments, monitoring)
- [ ] Documentation tasks included
- [ ] Testing tasks included
- [ ] Deployment tasks included

**Quality**:
- [ ] Every task has a unique ID (TASK-XXX format)
- [ ] Every task traces back to requirement (REQ-XXX)
- [ ] Every task has acceptance criteria
- [ ] Every task has story point estimate (1, 2, 3, 5, 8, 13)
- [ ] Every task has time estimate (0.5-5 days)
- [ ] Tasks > 5 days are broken down further
- [ ] Every task has skill level assignment (Junior/Mid/Senior)

**Organization**:
- [ ] Tasks grouped by feature/epic
- [ ] Logical flow within each epic (foundation → features → polish)
- [ ] Clear dependencies documented
- [ ] Critical path tasks identified
- [ ] MVP vs. post-MVP clearly marked

**Traceability**:
- [ ] Task → Requirement mapping complete
- [ ] No orphaned tasks (all have requirement)
- [ ] No orphaned requirements (all have tasks)
- [ ] Cross-references correct and bidirectional

**Risk Assessment**:
- [ ] High-risk tasks flagged
- [ ] Uncertainty documented
- [ ] Technical spikes identified where needed
- [ ] Mitigation strategies proposed
```

**If validation fails**: Work with Planning Agent to address gaps.

**1.4 Stakeholder Review of Task Breakdown**

Conduct a review with:
- Development team lead (estimates realistic?)
- Architect (technical approach sound?)
- Product manager (priorities reflected?)

**Output**: `artifacts/task-breakdown.md` (validated and approved)

**Decision Point**: Task breakdown complete and validated?
- ✅ Yes → Continue to Step 2 (Dependency Analysis)
- ❌ No → Iterate with Planning Agent until validated

---

### Step 2: Dependency Analysis (Included in Step 1, validate separately)

#### Objective
Map all technical dependencies between tasks to identify critical path and parallelization opportunities.

#### Agent: Planning Agent (continued)

#### Actions

**2.1 Generate Dependency Map**

The Planning Agent will create `dependency-map.md` showing:

```markdown
## Dependency Map Validation

**Visual Representation**:
- [ ] Dependency graph showing all task relationships
- [ ] Critical path highlighted
- [ ] Parallelization opportunities identified
- [ ] Bottleneck tasks flagged

**Dependency Types Documented**:
- [ ] **Hard dependencies**: Task B cannot start until Task A complete
- [ ] **Soft dependencies**: Task B easier if Task A done first
- [ ] **Resource dependencies**: Same person needed, so can't parallelize
- [ ] **External dependencies**: Waiting on third-party or outside team

**Critical Path Analysis**:
- [ ] Longest path through project identified
- [ ] Duration of critical path calculated
- [ ] Tasks on critical path marked as high-priority
- [ ] Strategies to shorten critical path proposed

**Parallelization Analysis**:
- [ ] Independent task streams identified
- [ ] Team member allocation recommendations
- [ ] Maximum parallelization scenario documented
- [ ] Realistic parallelization based on team size

**Risk Assessment**:
- [ ] Single points of failure identified
- [ ] Knowledge concentration risks flagged
- [ ] External dependency risks assessed
- [ ] Mitigation strategies proposed
```

**2.2 Validate Dependency Accuracy**

Review with architect and tech lead:

**Questions to validate**:
1. Are all technical dependencies captured?
   - Database schema must be done before features using it?
   - Authentication must be done before protected endpoints?
   - Core services before dependent services?

2. Are dependencies at the right level?
   - Not too granular (task-by-task micromanagement)
   - Not too coarse (missing real blockers)

3. Are external dependencies documented?
   - Third-party API access
   - Infrastructure provisioning
   - Security reviews
   - Legal approvals

**2.3 Identify De-risking Opportunities**

Look for ways to reduce dependency risk:

```markdown
## Dependency De-risking Strategies

**Strategy 1: Reorder Work**
- Can we do Task X earlier to unblock multiple downstream tasks?
- Example: Move "Database schema finalization" to Sprint 0

**Strategy 2: Mock/Stub Dependencies**
- Can we mock external dependencies to enable parallel work?
- Example: Mock payment gateway for development, integrate later

**Strategy 3: Interface-First Development**
- Can we define interfaces early so teams work in parallel?
- Example: Define API contracts, then build client and server simultaneously

**Strategy 4: Technical Spikes**
- Should we de-risk uncertain dependencies with time-boxed exploration?
- Example: 2-day spike to validate third-party library works as expected

**Strategy 5: Risk-Weighted Prioritization**
- Should we tackle high-risk dependencies first?
- Example: Start with complex integration rather than simple CRUD screens
```

**Output**: `artifacts/dependency-map.md` (validated)

**Decision Point**: Dependencies mapped and risks addressed?
- ✅ Yes → Continue to Step 3 (Sprint Planning)
- ❌ No → Refine dependency analysis

---

### Step 3: Sprint Planning (2-3 days)

#### Objective
Organize tasks into executable sprints that fit within team capacity and deliver incremental value.

#### Agent: Planning Agent

#### Workflow
Follow: `.phase2/primitives/workflows/sprint-planning.prompt.md`

#### Context to Provide

```markdown
## Sprint Planning Context

**Your Mission**: Create a realistic sprint plan that organizes tasks into 
executable sprints, respecting team capacity, dependencies, and MVP priorities.

**Inputs**:
- Task breakdown (all tasks with estimates)
- Dependency map (technical dependencies and critical path)
- Team context (size, skills, capacity, velocity)
- PRD (MVP scope and priorities)
- Constitution (quality standards that must be maintained)

**Your Outputs**:
1. Sprint Plan - 3-5 sprints planned in detail
2. Resource Allocation - who works on what
3. Velocity Projections - expected burn-down
4. Milestone Definitions - demo-ready checkpoints

**Constraints**:
- Sprint length: [From team context - typically 2 weeks]
- Team capacity: [From team context - e.g., 80 hours/sprint for 4 devs]
- Must plan for 70-80% capacity (not 100%)
- Must respect dependencies (can't start Task B before Task A)
- MVP must be deliverable by Sprint N

**Planning Principles**:
- Each sprint produces demonstrable value
- Balance feature work with technical foundation
- Include testing and documentation in every sprint
- Leave buffer for unexpected issues
- Sustainable pace (no death marches)

Begin with Sprint 0 definition.
```

#### Actions

**3.1 Define Sprint 0 (Setup Sprint)**

Sprint 0 is a special sprint focused on:
- Repository setup and tooling
- Development environment configuration
- CI/CD pipeline implementation
- Database schema implementation
- Core framework setup
- Team onboarding

```markdown
## Sprint 0 Checklist

**Infrastructure**:
- [ ] Repository created with proper structure
- [ ] CI/CD pipeline functional
- [ ] Development environment setup
- [ ] Staging environment setup
- [ ] Database provisioned and schema deployed

**Foundational Code**:
- [ ] Project skeleton with build system
- [ ] Logging framework configured
- [ ] Error handling strategy implemented
- [ ] Authentication/authorization framework setup
- [ ] Database access layer (ORM, migrations)

**Team Readiness**:
- [ ] All developers have working dev environments
- [ ] Code standards documented and linted
- [ ] Git workflow agreed and documented
- [ ] PR review process established
- [ ] Team trained on tools and frameworks

**Quality Infrastructure**:
- [ ] Unit test framework setup
- [ ] Integration test framework setup
- [ ] Code coverage reporting
- [ ] Static analysis tools configured

**Duration**: Typically 1-2 weeks  
**Team Involvement**: Usually full team  
**Output**: Development-ready infrastructure
```

**3.2 Plan Feature Sprints (Sprints 1-N)**

For each subsequent sprint:

```markdown
## Sprint Planning Template

**Sprint N Goals**: [What will be demonstrable at end of sprint?]

**Priority**: [Must-have / Should-have / Could-have from PRD]

**Tasks in Sprint**:

| Task ID | Task Description | Estimate | Assignee Skill | Dependencies | Priority |
|---------|-----------------|----------|----------------|--------------|----------|
| TASK-001 | [Description] | 3 SP / 2 days | Senior | TASK-000 | Must-have |
| TASK-002 | [Description] | 5 SP / 3 days | Mid | TASK-001 | Must-have |
| TASK-003 | [Description] | 2 SP / 1 day | Junior | - | Should-have |

**Capacity Check**:
- Total story points: [Sum of all tasks]
- Total time estimate: [Sum of all time estimates]
- Team capacity: [Available hours this sprint]
- Capacity utilization: [Total time / Capacity] (should be 70-80%)

**Demonstrable Outcome**: [What can we demo to stakeholders?]

**Success Criteria**: [How do we know sprint succeeded?]

**Risks**: [What might go wrong? How to mitigate?]
```

**3.3 Validate Sprint Plans**

Check each sprint for quality:

```markdown
## Sprint Plan Validation Checklist

**For Each Sprint**:

**Goal Clarity**:
- [ ] Sprint has clear, demonstrable goal
- [ ] Success criteria are measurable
- [ ] Outcome delivers user/business value
- [ ] Team understands why we're doing this work

**Capacity Realism**:
- [ ] Total estimates fit within team capacity
- [ ] Planned to 70-80% capacity (not 100%)
- [ ] Buffer for unexpected issues
- [ ] Not overcommitting junior developers

**Dependency Respect**:
- [ ] All prerequisite tasks completed in prior sprints
- [ ] No dependency deadlocks within sprint
- [ ] External dependencies accounted for
- [ ] Critical path respected

**Value Delivery**:
- [ ] Delivers incremental working functionality
- [ ] Produces demonstrable outcome
- [ ] MVP features prioritized first
- [ ] Technical debt managed (not accumulating)

**Skill Balance**:
- [ ] Work distributed across team skill levels
- [ ] Junior developers have appropriate tasks
- [ ] Senior developers on complex/risky tasks
- [ ] Pair programming opportunities identified

**Quality Inclusion**:
- [ ] Testing tasks included in sprint
- [ ] Code review time accounted for
- [ ] Documentation tasks included
- [ ] Refactoring time if needed

**Risk Management**:
- [ ] High-risk tasks identified
- [ ] Mitigation plans in place
- [ ] Contingency if things go wrong
- [ ] Technical spikes completed before building
```

**3.4 Create Resource Allocation Plan**

Document who works on what:

```markdown
## Resource Allocation

**Team Composition**: [From team context]
- [N] Senior developers
- [N] Mid-level developers
- [N] Junior developers
- [N] Full-stack vs. specialized

**Sprint N Allocation**:

**Developer A (Senior)**:
- Primary: TASK-XXX (Complex authentication system)
- Secondary: Code review, mentoring Junior developers
- Capacity: 32 hours (80% of 40-hour week)

**Developer B (Mid)**:
- Primary: TASK-YYY (Payment integration)
- Secondary: TASK-ZZZ (Admin dashboard)
- Capacity: 32 hours

**Developer C (Junior)**:
- Primary: TASK-AAA (Simple CRUD screens)
- Pair with: Developer A (learning complex tasks)
- Capacity: 28 hours (70% to account for learning)

**Developer D (Full-stack)**:
- Primary: TASK-BBB (API endpoints)
- Secondary: TASK-CCC (Frontend components)
- Capacity: 32 hours
```

**3.5 Define Milestones**

Identify key checkpoints:

```markdown
## Project Milestones

**Milestone 1: Foundation Complete**
- Sprint: Sprint 0
- Date: [Date]
- Criteria: All infrastructure and core frameworks ready
- Demonstrable: Developer can run app locally, CI/CD deploys to staging

**Milestone 2: Core Features Demo**
- Sprint: Sprint 2
- Date: [Date]
- Criteria: Primary user workflow functional end-to-end
- Demonstrable: User can [key workflow] successfully

**Milestone 3: MVP Feature Complete**
- Sprint: Sprint 4
- Date: [Date]
- Criteria: All must-have features implemented
- Demonstrable: Product usable by internal stakeholders

**Milestone 4: MVP Ready**
- Sprint: Sprint 5
- Date: [Date]
- Criteria: All testing complete, documentation ready, deployment automated
- Demonstrable: Ready for production release

**Milestone 5: Post-MVP Features**
- Sprint: Sprint 6+
- Date: [Date range]
- Criteria: Should-have and could-have features
- Demonstrable: Enhanced user experience and additional capabilities
```

**Output**: `artifacts/sprint-plan.md` and `artifacts/resource-allocation.md`

**Decision Point**: Sprint plans realistic and approved?
- ✅ Yes → Continue to Step 4 (Repository Setup)
- ❌ No → Refine sprint plans with team

---

### Step 4: Repository Setup (2-3 days)

#### Objective
Create development infrastructure including repository structure, CI/CD pipeline, environments, and development tooling.

#### Agent: DevOps Scaffolder
Load: `.phase2/primitives/agents/devops-scaffolder.instructions.md`

#### Workflow
Follow: `.phase2/primitives/workflows/repository-setup.prompt.md`

#### Context to Provide

```markdown
## Repository Setup Context

**Your Mission**: Set up complete development infrastructure so that Phase 3 
development can start immediately without infrastructure delays.

**Inputs**:
- Technical Stack Context (languages, frameworks, tools)
- Architecture Document (component structure)
- Constitution (quality standards, security requirements)
- Task Breakdown (what needs to be built)
- Team Context (team size, skill levels, methodology)

**Your Outputs**:
1. Repository structure with proper organization
2. CI/CD pipeline (build, test, deploy)
3. Environment configurations (dev, staging, prod)
4. Docker containerization
5. Database migration system
6. Code quality tools (linting, formatting, analysis)
7. Development documentation (README, CONTRIBUTING, etc.)

**Constraints**:
- Must align with architecture component structure
- Must enforce constitution quality standards
- Must support team's development workflow
- Must be production-ready from day 1

**Quality Standards**:
- Pipeline must run in < 10 minutes
- All environments should be identical (infrastructure as code)
- Zero manual deployment steps
- Comprehensive developer documentation

Begin with repository structure design.
```

#### Actions

**4.1 Load DevOps Scaffolder Agent**

Start a new infrastructure-focused session:

```markdown
You are the DevOps Scaffolder Agent, an expert in repository structure, 
CI/CD pipelines, containerization, and development infrastructure.

Load the following context:
- Technical-stack.context.md
- Architecture.md
- Constitution.md
- Team-context.md

Your goal is to create a production-ready development infrastructure.

Confirm you have loaded all context and are ready to begin.
```

**4.2 Execute Repository Setup Workflow**

Follow the complete repository setup workflow:

```bash
# The workflow will guide you through:
# 1. Repository structure design (aligned with architecture)
# 2. Development environment setup (Docker, dependencies)
# 3. CI/CD pipeline implementation (build, test, deploy)
# 4. Environment configuration (dev, staging, prod)
# 5. Database setup and migration system
# 6. Code quality tooling (linters, formatters, analyzers)
# 7. Documentation (README, CONTRIBUTING, architecture diagrams)
```

**Expected Duration**: 2-3 days

**4.3 Validate Repository Setup**

Use the Repository Setup Validation checklist:

```markdown
## Repository Setup Validation Checklist

**Repository Structure**:
- [ ] Directory structure matches architectural components
- [ ] Clear separation of concerns (src, tests, docs, config)
- [ ] Proper .gitignore for language/framework
- [ ] LICENSE file present
- [ ] README.md comprehensive

**Development Environment**:
- [ ] Docker Compose for local development
- [ ] All dependencies specified (requirements.txt, package.json, etc.)
- [ ] Environment variable template (.env.example)
- [ ] Database seeding scripts for development
- [ ] Developer can run app in < 10 minutes after clone

**CI/CD Pipeline**:
- [ ] Automated build on every commit
- [ ] Automated tests run on every PR
- [ ] Code quality checks (linting, formatting, static analysis)
- [ ] Security scanning (dependency vulnerabilities)
- [ ] Automated deployment to staging on merge to main
- [ ] Manual approval gate for production deployment
- [ ] Pipeline runs in < 10 minutes

**Environment Configuration**:
- [ ] Development environment (local Docker)
- [ ] Staging environment (cloud, production-like)
- [ ] Production environment (cloud, secure)
- [ ] Environment parity (all environments identical)
- [ ] Secrets management configured

**Database Setup**:
- [ ] Database migration system in place
- [ ] Initial schema migration from data-model.md
- [ ] Seed data for development/testing
- [ ] Migration testing in CI/CD
- [ ] Rollback strategy documented

**Code Quality Tools**:
- [ ] Linter configured and enforced
- [ ] Code formatter configured (auto-format on save)
- [ ] Static analysis tools running in CI/CD
- [ ] Code coverage reporting
- [ ] Coverage threshold enforced (e.g., > 80%)

**Documentation**:
- [ ] README.md with setup instructions
- [ ] CONTRIBUTING.md with development workflow
- [ ] ARCHITECTURE.md with system design
- [ ] API.md with endpoint documentation
- [ ] CHANGELOG.md template ready

**Security**:
- [ ] No secrets in repository (use environment variables)
- [ ] Dependency scanning configured
- [ ] Security headers configured
- [ ] Authentication/authorization framework set up
- [ ] HTTPS enforced in all environments
```

**4.4 Team Onboarding Test**

Have one developer (not the person who set it up) attempt to:

1. Clone the repository
2. Follow README setup instructions
3. Run the application locally
4. Make a small change
5. Run tests
6. Submit a PR
7. See CI/CD pipeline run

**Success Criteria**:
- Developer can complete all steps in < 2 hours
- No manual intervention needed
- All tools work as documented
- Developer understands the workflow

**If anything blocks the developer**: Document and fix immediately.

**4.5 Document Infrastructure**

Create comprehensive infrastructure documentation:

```markdown
## Infrastructure Documentation Checklist

**For Developers** (in README.md):
- [ ] Prerequisites (Docker, Node, etc.)
- [ ] Setup instructions (step-by-step)
- [ ] How to run the app locally
- [ ] How to run tests
- [ ] How to make changes and submit PRs
- [ ] Troubleshooting common issues

**For DevOps** (in INFRASTRUCTURE.md):
- [ ] Architecture overview
- [ ] Cloud resources and configuration
- [ ] CI/CD pipeline details
- [ ] Environment variables and secrets
- [ ] Deployment process
- [ ] Monitoring and logging
- [ ] Disaster recovery procedures

**For QA** (in TESTING.md):
- [ ] How to run different test suites
- [ ] Test data management
- [ ] Test environment access
- [ ] Bug reporting workflow

**Diagrams**:
- [ ] Repository structure diagram
- [ ] CI/CD pipeline flow
- [ ] Deployment architecture
- [ ] Environment topology
```

**Output**: 
- Working repository with complete infrastructure
- `artifacts/repository-structure.md` (documentation)
- `artifacts/cicd-config.md` (pipeline details)

**Decision Point**: Infrastructure ready for development?
- ✅ Yes → Continue to Step 5 (Quality Planning)
- ❌ No → Address gaps in infrastructure

---

### Step 5: Quality Planning (1-2 days)

#### Objective
Define comprehensive quality standards, testing strategy, and test plans that ensure constitution quality requirements are met.

#### Agent: Quality Architect
Load: `.phase2/primitives/agents/quality-architect.instructions.md`

#### Workflow
Follow: `.phase2/primitives/workflows/quality-planning.prompt.md`

#### Context to Provide

```markdown
## Quality Planning Context

**Your Mission**: Define comprehensive quality standards and testing strategy 
that ensures the system meets constitution requirements and industry best practices.

**Inputs**:
- Constitution (quality standards and acceptance criteria)
- Requirements Specification (functional and non-functional requirements)
- Architecture (components to test, integration points)
- Sprint Plan (when testing activities happen)
- Repository Setup (where tests go, how they run)

**Your Outputs**:
1. Quality Strategy Document - overall approach to quality
2. Test Plan - detailed testing activities by sprint
3. Test Case Template - how to write good test cases
4. Definition of Done - checklist for considering work complete

**Constraints**:
- Must align with constitution quality standards
- Must be executable within sprint timelines
- Must cover functional and non-functional requirements
- Must include test automation strategy

**Quality Standards**:
- > 80% code coverage for unit tests
- 100% coverage of critical paths with integration tests
- All user workflows covered by end-to-end tests
- Performance tests for non-functional requirements
- Security testing for authentication/authorization
- Accessibility testing for user interfaces

Begin with test strategy definition.
```

#### Actions

**5.1 Load Quality Architect Agent**

Start a new quality-focused session:

```markdown
You are the Quality Architect Agent, an expert in quality assurance, testing 
strategy, test automation, and quality metrics.

Load the following context:
- Constitution.md
- Spec.md
- Architecture.md
- Sprint-plan.md

Your goal is to create a comprehensive quality strategy and test plan.

Confirm you have loaded all context and are ready to begin.
```

**5.2 Execute Quality Planning Workflow**

Follow the complete quality planning workflow:

```bash
# The workflow will guide you through:
# 1. Test strategy definition (levels, approach, automation)
# 2. Test planning by sprint (what testing when)
# 3. Test case design (functional, non-functional, edge cases)
# 4. Test environment requirements
# 5. Test data strategy
# 6. Definition of Done
# 7. Quality metrics and reporting
```

**Expected Duration**: 1-2 days

**5.3 Validate Quality Strategy**

Review the quality strategy document:

```markdown
## Quality Strategy Validation Checklist

**Test Levels Defined**:
- [ ] Unit testing strategy (what, when, coverage targets)
- [ ] Integration testing strategy (component interactions)
- [ ] End-to-end testing strategy (user workflows)
- [ ] Performance testing strategy (load, stress, scalability)
- [ ] Security testing strategy (vulnerabilities, penetration)
- [ ] Accessibility testing strategy (WCAG compliance)

**Test Automation**:
- [ ] Automation approach defined (tools, frameworks)
- [ ] Automation coverage targets set (e.g., 80% unit, 50% e2e)
- [ ] CI/CD integration specified
- [ ] Test maintenance strategy (keeping tests updated)

**Test Types Covered**:
- [ ] Functional testing (features work as specified)
- [ ] Non-functional testing (performance, security, usability)
- [ ] Regression testing (changes don't break existing features)
- [ ] Smoke testing (critical paths always work)
- [ ] Acceptance testing (meets user expectations)

**Quality Standards**:
- [ ] Code quality standards (linting, complexity, duplication)
- [ ] Code review standards (checklist, approval process)
- [ ] Documentation standards (code comments, API docs)
- [ ] Performance standards (response time, throughput)
- [ ] Security standards (authentication, authorization, encryption)
- [ ] Accessibility standards (WCAG 2.1 Level AA)

**Test Data Management**:
- [ ] Test data creation strategy
- [ ] Test data anonymization (for production data)
- [ ] Test data reset between tests
- [ ] Realistic data volume for performance tests

**Test Environments**:
- [ ] Development testing environment
- [ ] Integration testing environment
- [ ] Staging testing environment
- [ ] Performance testing environment
- [ ] Environment parity ensured
```

**5.4 Validate Test Plan**

Review the test plan for each sprint:

```markdown
## Test Plan Validation Checklist

**For Each Sprint**:

**Test Activities Scheduled**:
- [ ] Unit test writing included in task estimates
- [ ] Integration test writing scheduled
- [ ] End-to-end test writing scheduled
- [ ] Test review and debugging time allocated
- [ ] Regression testing after each merge

**Test Coverage**:
- [ ] All user stories have acceptance tests
- [ ] All requirements have test cases
- [ ] Critical paths have multiple test scenarios
- [ ] Edge cases identified and covered
- [ ] Error conditions tested

**Test Deliverables**:
- [ ] Test cases written and reviewed
- [ ] Test automation implemented
- [ ] Test results documented
- [ ] Defects identified and tracked
- [ ] Coverage reports generated

**Definition of Done**:
- [ ] All acceptance criteria met
- [ ] Unit tests written and passing
- [ ] Integration tests written and passing
- [ ] Code reviewed and approved
- [ ] No critical or high-priority defects
- [ ] Documentation updated
- [ ] Deployed to staging environment
```

**5.5 Create Test Case Standards**

Define how to write good test cases:

```markdown
## Test Case Template

**Test Case ID**: TC-XXX  
**Requirement ID**: REQ-XXX (traceability)  
**Test Type**: [Unit/Integration/E2E/Performance/Security]

**Test Objective**: [What is this test verifying?]

**Preconditions**: 
[What must be true before test runs?]

**Test Steps**:
1. [Action 1]
2. [Action 2]
3. [Action 3]

**Test Data**: 
[Specific data values to use]

**Expected Results**:
- [What should happen after step 1]
- [What should happen after step 2]
- [What should happen after step 3]

**Actual Results**: 
[Filled in during test execution]

**Status**: [Pass/Fail/Blocked]  
**Priority**: [Critical/High/Medium/Low]  
**Automation**: [Yes/No/In Progress]
```

**5.6 Define Quality Metrics**

Establish how quality will be measured:

```markdown
## Quality Metrics

**Code Quality Metrics**:
- Code coverage: > 80% unit, > 60% integration
- Cyclomatic complexity: < 10 per function
- Code duplication: < 5%
- Linting violations: 0
- Static analysis issues: 0 critical, < 5 high

**Test Metrics**:
- Test pass rate: > 95%
- Automated test coverage: > 70%
- Test execution time: < 10 minutes for unit tests
- Test stability: < 2% flaky tests

**Defect Metrics**:
- Critical defects: 0 in production
- High defects: < 3 per sprint
- Defect resolution time: < 2 days for critical
- Defect escape rate: < 5% (defects found in prod)

**Performance Metrics** (from constitution):
- API response time: < 200ms (p95)
- Page load time: < 2 seconds
- Throughput: > 1000 requests/second
- Uptime: > 99.9%
```

**Output**: 
- `artifacts/quality-strategy.md`
- `artifacts/test-plan.md`
- `artifacts/definition-of-done.md`

**Decision Point**: Quality strategy comprehensive and agreed?
- ✅ Yes → Continue to Step 6 (Risk Assessment)
- ❌ No → Refine quality planning

---

### Step 6: Risk Assessment (1 day)

#### Objective
Identify implementation risks, assess probability and impact, and define mitigation strategies.

#### Agent: Planning Agent (with risk focus)

#### Workflow
Follow: `.phase2/primitives/workflows/risk-assessment.prompt.md`

#### Context to Provide

```markdown
## Risk Assessment Context

**Your Mission**: Identify all risks that could derail Phase 3 implementation 
and define mitigation strategies for each.

**Inputs**:
- Task breakdown (where complexity and uncertainty exist)
- Dependency map (where bottlenecks exist)
- Sprint plan (where timeline pressure exists)
- Architecture (where technical risk exists)
- Team context (where skill gaps exist)

**Your Output**:
Risk Register with:
- All identified risks
- Probability and impact assessment
- Risk score and prioritization
- Mitigation strategies
- Contingency plans

**Risk Categories to Consider**:
- Technical risks (complexity, unknowns, dependencies)
- Resource risks (skill gaps, capacity, turnover)
- Schedule risks (aggressive timelines, scope creep)
- External risks (third-party dependencies, approvals)
- Quality risks (testing gaps, technical debt)

Begin with brainstorming all possible risks.
```

#### Actions

**6.1 Identify All Risks**

Brainstorm risks across categories:

```markdown
## Risk Brainstorming

**Technical Risks**:
- Database schema changes mid-project
- Performance issues not caught until late
- Integration with third-party API more complex than expected
- Framework limitations discovered mid-development
- Scalability requirements not met

**Resource Risks**:
- Key developer leaves mid-project
- Team velocity lower than historical average
- Junior developers require more mentoring than expected
- Skill gaps in specific technologies
- Team burnout from aggressive timeline

**Schedule Risks**:
- Estimates too optimistic
- Unplanned scope creep
- Delays in external dependencies
- Quality issues causing rework
- Technical debt slowing development

**External Risks**:
- Third-party API access delayed
- Security review process longer than expected
- Infrastructure provisioning delayed
- Stakeholder availability for approvals
- Regulatory compliance requirements emerge

**Quality Risks**:
- Insufficient test coverage
- Test automation gaps
- Performance testing inadequate
- Security vulnerabilities discovered late
- Accessibility issues found post-development
```

**6.2 Assess Each Risk**

For each identified risk:

```markdown
## Risk Assessment Template

**Risk ID**: RISK-XXX  
**Risk Description**: [Clear description of what could go wrong]

**Category**: [Technical/Resource/Schedule/External/Quality]

**Probability**: [Low (10%) / Medium (40%) / High (70%)]  
**Impact**: [Low / Medium / High / Critical]  
**Risk Score**: [Probability × Impact, scale 1-20]

**Triggers** (warning signs this risk is materializing):
- [Trigger 1]
- [Trigger 2]

**Root Cause**: [Why might this happen?]

**Mitigation Strategy** (proactive actions to reduce probability):
1. [Action 1]
2. [Action 2]
3. [Action 3]

**Contingency Plan** (reactive actions if risk occurs):
1. [Action 1]
2. [Action 2]
3. [Action 3]

**Owner**: [Who is responsible for monitoring this risk?]  
**Status**: [Open / Mitigated / Occurred / Closed]
```

**6.3 Prioritize Risks**

Use risk score to prioritize:

```markdown
## Risk Prioritization Matrix

**Critical Risks** (Score ≥ 15) - Address immediately:
- RISK-001: [High probability, high impact]
- RISK-005: [Medium probability, critical impact]

**High Priority Risks** (Score 10-14) - Plan mitigation:
- RISK-002: [Medium probability, high impact]
- RISK-007: [High probability, medium impact]

**Medium Priority Risks** (Score 5-9) - Monitor:
- RISK-003: [Low probability, high impact]
- RISK-008: [Medium probability, medium impact]

**Low Priority Risks** (Score < 5) - Accept:
- RISK-004: [Low probability, low impact]
```

**6.4 Create Mitigation Plans**

For all critical and high-priority risks:

```markdown
## Mitigation Plan - RISK-XXX

**Risk**: [Description]  
**Score**: [Priority score]  
**Owner**: [Name]

**Proactive Mitigation** (do these NOW):

| Action | Owner | Due Date | Status | Cost |
|--------|-------|----------|--------|------|
| [Action 1] | [Name] | [Date] | [Not Started/In Progress/Complete] | [Time/Money] |
| [Action 2] | [Name] | [Date] | [Status] | [Cost] |
| [Action 3] | [Name] | [Date] | [Status] | [Cost] |

**Monitoring Plan**:
- **Frequency**: [Weekly/Bi-weekly/Sprint review]
- **Indicators**: [What metrics show risk status?]
- **Threshold**: [When to escalate?]

**Contingency Plan** (if risk occurs):

| Action | Trigger | Owner | Response Time |
|--------|---------|-------|---------------|
| [Action 1] | [When to execute] | [Name] | [How quickly] |
| [Action 2] | [When to execute] | [Name] | [How quickly] |

**Acceptance Criteria** (when is risk resolved?):
- [Criteria 1]
- [Criteria 2]
```

**6.5 Conduct Risk Review Meeting**

Present risk register to stakeholders:

**Attendees**:
- Project sponsor
- Development team lead
- Product manager
- Solutions architect
- Any risk owners

**Agenda** (1 hour):

1. **Present Risk Register** (20 min)
   - Walk through critical and high-priority risks
   - Explain probability and impact assessments
   - Share proposed mitigation strategies

2. **Discuss Mitigation Approaches** (20 min)
   - Are mitigation strategies sufficient?
   - Are contingency plans realistic?
   - Do we need additional risk responses?

3. **Assign Risk Owners** (10 min)
   - Who monitors each risk?
   - Who executes mitigation actions?
   - Who approves contingency plans?

4. **Define Escalation Path** (10 min)
   - When to escalate risks?
   - Who gets escalated to?
   - How to communicate risk status?

**Output**: Risk register with assigned owners and agreed mitigation plans

**6.6 Integrate Risks into Sprint Planning**

Update sprint plans with risk mitigation:

```markdown
## Sprint Plan Risk Integration

**Sprint 0**:
- Add task: TASK-XXX: Technical spike for high-risk integration (RISK-002 mitigation)
- Add buffer: +2 days for unexpected infrastructure issues (RISK-005 contingency)

**Sprint 1**:
- Prioritize: TASK-YYY moved earlier to de-risk critical path (RISK-001 mitigation)
- Add task: TASK-ZZZ: Performance baseline testing (RISK-003 mitigation)

**Sprint 2**:
- Add buffer: +1 day for junior developer mentoring (RISK-007 mitigation)
- Add checkpoint: Architecture review before proceeding (RISK-001 gate)
```

**Output**: `artifacts/risk-register.md`

**Decision Point**: All major risks identified and mitigated?
- ✅ Yes → Continue to Step 7 (Validation & Sign-off)
- ❌ No → Address critical risk gaps

---

### Step 7: Validation & Sign-off (1 day)

#### Objective
Validate that Phase 2 is complete and ready for Phase 3 implementation to begin.

#### Agent: Validator (or manual review)

#### Actions

**7.1 Run Phase 2 Completion Checklist**

Use the comprehensive checklist:

```bash
# Open the Phase 2 completion checklist
open .phase2/primitives/checklists/phase-2-completion.checklist.md

# Score all criteria (similar to Phase 1 checklist)
# Critical criteria must be 100%
# Important criteria must be 80%+
```

**Checklist Categories**:
1. **Task Decomposition Completeness** (Must be 100%)
2. **Sprint Planning Completeness** (Must be 100%)
3. **Infrastructure Completeness** (Must be 100%)
4. **Quality Planning Completeness** (Must be 100%)
5. **Risk Management Completeness** (Must be 100%)
6. **Documentation Quality** (Must be 80%+)
7. **Traceability & Integration** (Must be 80%+)
8. **Phase 3 Readiness** (Must be 100%)

**7.2 Validate Traceability**

Ensure complete traceability from requirements through to tasks:

```markdown
## Traceability Validation

**Requirement → Task Mapping**:
- [ ] Every requirement in spec.md has tasks in task-breakdown.md
- [ ] Every task traces back to a requirement
- [ ] No orphaned requirements
- [ ] No orphaned tasks

**Task → Sprint Mapping**:
- [ ] Every task is assigned to a sprint
- [ ] Every sprint has clear goals and outcomes
- [ ] MVP requirements all in early sprints
- [ ] Post-MVP requirements in later sprints

**Architecture → Task Mapping**:
- [ ] Every architectural component has implementation tasks
- [ ] Task organization aligns with component structure
- [ ] Repository structure mirrors architecture

**Risk → Task Mapping**:
- [ ] High-risk tasks have mitigation tasks
- [ ] Technical spikes scheduled before uncertain work
- [ ] Buffer time allocated for known risks
```

**7.3 Validate Artifact Consistency**

Check that all artifacts are aligned:

```markdown
## Artifact Consistency Checklist

**Task Breakdown ↔ Sprint Plan**:
- [ ] All tasks in task-breakdown appear in sprint plan
- [ ] Sprint estimates match task estimates
- [ ] Dependencies in task breakdown respected in sprint plan
- [ ] MVP scope consistent between documents

**Sprint Plan ↔ Resource Allocation**:
- [ ] Developer assignments match skill requirements
- [ ] Capacity calculations consistent
- [ ] No developer over-allocated
- [ ] Pair programming reflected in allocation

**Task Breakdown ↔ Repository Structure**:
- [ ] Repository folders align with epics/features
- [ ] Component structure matches architecture
- [ ] Test directories organized by task type

**Quality Strategy ↔ Sprint Plan**:
- [ ] Testing activities scheduled in sprints
- [ ] Quality gates aligned with sprint boundaries
- [ ] Definition of Done applied to all sprints
- [ ] Test coverage targets achievable

**Risk Register ↔ Sprint Plan**:
- [ ] High-risk tasks identified in sprint plan
- [ ] Mitigation actions scheduled
- [ ] Buffer time allocated appropriately
- [ ] Technical spikes scheduled before risky work
```

**7.4 Validate Team Readiness**

Ensure the team is ready to start development:

```markdown
## Team Readiness Checklist

**Development Environment**:
- [ ] All developers have cloned repository
- [ ] All developers can run app locally
- [ ] All developers understand git workflow
- [ ] All developers understand PR process

**Tool Proficiency**:
- [ ] Team trained on frameworks being used
- [ ] Team understands architecture decisions
- [ ] Team familiar with code standards
- [ ] Team knows where to find documentation

**Process Understanding**:
- [ ] Sprint length and ceremonies agreed
- [ ] Definition of Done understood by all
- [ ] Task estimation approach agreed
- [ ] Communication norms established

**First Sprint Ready**:
- [ ] Sprint 0 tasks clearly defined
- [ ] Sprint 0 goals understood
- [ ] Sprint 0 assignments made
- [ ] Sprint 0 start date confirmed
```

**7.5 Conduct Phase 2 Review Meeting**

Present all Phase 2 outputs to stakeholders:

**Attendees**:
- Project sponsor
- Product manager
- Development team
- Architecture team
- QA team
- DevOps team

**Agenda** (1.5-2 hours):

1. **Phase 2 Overview** (10 min)
   - What was accomplished
   - Timeline and effort spent
   - Any changes from initial plan

2. **Task Breakdown Walkthrough** (15 min)
   - Present work breakdown structure
   - Highlight major epics and features
   - Show MVP boundary
   - Discuss estimates and confidence

3. **Sprint Plan Presentation** (20 min)
   - Walk through each sprint
   - Show demonstrable outcomes per sprint
   - Discuss capacity and velocity assumptions
   - Highlight milestones

4. **Infrastructure Demo** (15 min)
   - Show working repository
   - Demo CI/CD pipeline
   - Show environment setup
   - Walk through developer workflow

5. **Quality Strategy Review** (15 min)
   - Present testing approach
   - Show test coverage targets
   - Discuss Definition of Done
   - Review quality metrics

6. **Risk Assessment** (15 min)
   - Present critical and high-priority risks
   - Discuss mitigation strategies
   - Show contingency plans
   - Assign risk monitoring owners

7. **Q&A and Concerns** (15 min)
   - Address any stakeholder concerns
   - Clarify any ambiguities
   - Discuss any adjustments needed

8. **Go/No-Go Decision** (10 min)
   - Review completion checklist scores
   - Assess readiness for Phase 3
   - Make formal decision to proceed

**Possible Outcomes**:

✅ **GO**: Phase 2 complete, proceed to Phase 3
- All critical criteria met
- 80%+ of important criteria met
- Team ready and infrastructure functional
- Stakeholders approve

⚠️ **CONDITIONAL GO**: Proceed with managed risk
- Minor gaps documented
- Mitigation plans in place
- Acceptable risk level
- Stakeholder awareness and approval

❌ **NO-GO**: Phase 2 incomplete
- Critical gaps remain
- Major risks unmitigated
- Infrastructure not functional
- Team not ready

**7.6 Document Sign-offs**

Collect formal approvals:

```markdown
## Phase 2 Sign-off

**Development Team Sign-off**:
- [ ] Development Team Lead: [Name] - Date: [___] - Signature: [___]
- [ ] Senior Developer: [Name] - Date: [___] - Signature: [___]

**Technical Leadership Sign-off**:
- [ ] Solutions Architect: [Name] - Date: [___] - Signature: [___]
- [ ] DevOps Lead: [Name] - Date: [___] - Signature: [___]
- [ ] QA Lead: [Name] - Date: [___] - Signature: [___]

**Product Leadership Sign-off**:
- [ ] Product Manager: [Name] - Date: [___] - Signature: [___]
- [ ] Project Sponsor: [Name] - Date: [___] - Signature: [___]

**Approval for Phase 3**:
- [ ] **Approved to proceed to Phase 3 (Development)**
  - Approver: [Name, Title]
  - Date: [___]
  - Sprint 0 Start Date: [___]
  - Conditions: [Any conditions attached to approval]
```

**7.7 Create Phase 2 Summary Report**

Generate a concise summary document:

```markdown
## Phase 2 Summary Report

**Project**: [Project Name]  
**Phase 2 Duration**: [Start Date] to [End Date] ([X] days)  
**Team**: [N] developers, [N] architects, [N] QA

### Key Accomplishments

**Task Decomposition**:
- Total requirements decomposed: [N]
- Total epics created: [N]
- Total user stories created: [N]
- Total tasks created: [N]
- Total estimated effort: [N] story points / [N] hours

**Sprint Planning**:
- Sprints planned: [N]
- MVP target: Sprint [N] ([Date])
- Major milestones: [List]
- Team velocity: [N] story points/sprint

**Infrastructure**:
- Repository created: [URL]
- CI/CD pipeline: [Status - Functional]
- Environments set up: Dev, Staging, Prod
- Developer onboarding time: [X] hours

**Quality Planning**:
- Test strategy: [Approach]
- Coverage targets: Unit [X]%, Integration [Y]%, E2E [Z]%
- Quality metrics: [List key metrics]
- Definition of Done: [Status - Defined and agreed]

**Risk Management**:
- Risks identified: [N] total
- Critical risks: [N]
- High-priority risks: [N]
- Mitigation plans: [N] implemented

### Readiness for Phase 3

**Completion Score**: [X]/[Y] ([Z]%)

**Critical Criteria**: [X]/[Y] (100% required) ✅  
**Important Criteria**: [X]/[Y] (80%+ required) ✅

**Status**: ✅ Ready to proceed to Phase 3

### Next Steps

1. **Sprint 0 Start**: [Date]
2. **Sprint 0 Goals**: [Summary]
3. **First Demo**: [Date]
4. **MVP Target**: [Date]

### Stakeholder Approvals

All required sign-offs obtained: ✅

---

**Phase 3 Kickoff Scheduled**: [Date and Time]
```

**Output**: 
- `artifacts/phase2-completion.checklist.md` (scored and validated)
- `artifacts/phase2-summary-report.md` (executive summary)
- Formal sign-offs collected

**Final Decision Point**: Proceed to Phase 3?
- ✅ **YES** → Schedule Phase 3 kickoff, Sprint 0 begins
- ⚠️ **CONDITIONAL** → Document conditions, proceed with caution
- ❌ **NO** → Address gaps, re-validate before Phase 3

---

## Phase 2 Outputs Summary

### Required Artifacts (Must Have)

**Planning Artifacts**:
1. ✅ `task-breakdown.md` - Complete work breakdown structure
2. ✅ `dependency-map.md` - Technical dependencies and critical path
3. ✅ `sprint-plan.md` - 3-5 sprints planned in detail
4. ✅ `resource-allocation.md` - Developer assignments by sprint

**Infrastructure Artifacts**:
5. ✅ Working repository with proper structure
6. ✅ Functional CI/CD pipeline
7. ✅ `repository-structure.md` - Documentation of repo organization
8. ✅ `cicd-config.md` - Pipeline and deployment documentation

**Quality Artifacts**:
9. ✅ `quality-strategy.md` - Overall quality approach
10. ✅ `test-plan.md` - Testing activities by sprint
11. ✅ `definition-of-done.md` - Completion criteria

**Risk Artifacts**:
12. ✅ `risk-register.md` - All risks with mitigation plans

**Validation Artifacts**:
13. ✅ `phase2-completion.checklist.md` - Validated and scored
14. ✅ `phase2-summary-report.md` - Executive summary
15. ✅ Stakeholder sign-offs - Formal approvals

### Optional Artifacts (Nice to Have)

16. 🔶 `estimation-accuracy.md` - Historical estimation analysis
17. 🔶 `technical-spikes.md` - List of spikes to conduct
18. 🔶 `team-velocity-analysis.md` - Team velocity trends
19. 🔶 `capacity-planning-details.md` - Detailed capacity calculations

---

## Quality Standards for Phase 2

### Task Decomposition Quality

✅ **Every requirement has tasks** (100% traceability)  
✅ **Every task is estimable** (2-5 days max)  
✅ **Every task has acceptance criteria** (definition of done)  
✅ **Dependencies are explicit** (no hidden blockers)  
✅ **Risk is assessed** (uncertainty documented)

### Sprint Planning Quality

✅ **Capacity is realistic** (70-80% utilization, not 100%)  
✅ **Dependencies are respected** (tasks in correct order)  
✅ **Value is incremental** (each sprint demos progress)  
✅ **Milestones are defined** (key checkpoints clear)  
✅ **MVP is bounded** (scope is achievable)

### Infrastructure Quality

✅ **Repository is organized** (matches architecture)  
✅ **Pipeline is automated** (no manual steps)  
✅ **Environments are identical** (dev = staging = prod)  
✅ **Documentation is complete** (developer can onboard in <2 hours)  
✅ **Tools are configured** (linting, testing, coverage)

### Quality Planning Quality

✅ **Strategy is comprehensive** (all test levels covered)  
✅ **Plans are detailed** (testing activities per sprint)  
✅ **Automation is planned** (coverage targets defined)  
✅ **Metrics are measurable** (quality is quantifiable)  
✅ **Definition of Done is clear** (everyone understands completion)

### Risk Management Quality

✅ **Risks are comprehensive** (all categories covered)  
✅ **Assessments are realistic** (probability and impact)  
✅ **Mitigation is proactive** (actions taken before risk occurs)  
✅ **Contingencies are reactive** (plans if risk occurs)  
✅ **Ownership is assigned** (someone monitors each risk)

---

## Common Pitfalls & How to Avoid Them

### Pitfall 1: Over-planning

**Symptom**: Spending 3-4 weeks in Phase 2, trying to plan every detail

**Problem**: Diminishing returns - over-planning wastes time and plans will change anyway

**Solution**: 
- Time-box Phase 2 to 10-14 days maximum
- Plan first 3-5 sprints in detail, rest at epic level
- Accept that plans will evolve as you learn

### Pitfall 2: Under-estimating Setup Time

**Symptom**: Thinking Sprint 0 is unnecessary, jumping straight to features

**Problem**: Developers waste time fighting infrastructure instead of building features

**Solution**:
- Always plan Sprint 0 for setup
- Invest in CI/CD, tooling, and documentation upfront
- Validate that a new developer can onboard in <2 hours

### Pitfall 3: Ignoring Dependencies

**Symptom**: Planning tasks in isolation without considering dependencies

**Problem**: Team gets blocked, can't make progress, falls behind schedule

**Solution**:
- Map dependencies explicitly
- Identify critical path
- Plan work in dependency order
- Use technical spikes to de-risk uncertain dependencies

### Pitfall 4: Planning to 100% Capacity

**Symptom**: Filling every sprint to maximum capacity with feature work

**Problem**: No buffer for unknowns, bugs, or learning - leads to missed commitments

**Solution**:
- Plan to 70-80% capacity
- Leave slack for unexpected issues
- Accept that not everything will go as estimated

### Pitfall 5: Weak Quality Planning

**Symptom**: "We'll figure out testing later" or "Testing is QA's job"

**Problem**: Technical debt accumulates, quality suffers, bugs expensive to fix

**Solution**:
- Plan testing from day 1
- Include test writing in every task estimate
- Set coverage targets and enforce them
- Make quality everyone's responsibility

### Pitfall 6: No Risk Management

**Symptom**: Assuming everything will go perfectly, no contingency plans

**Problem**: First major issue causes panic, scrambling, and delay

**Solution**:
- Identify risks proactively
- Plan mitigation strategies
- Have contingency plans ready
- Monitor risks continuously

### Pitfall 7: Skipping Validation

**Symptom**: Rushing to Phase 3 without validating Phase 2 completeness

**Problem**: Starting development with incomplete plan, infrastructure, or quality standards

**Solution**:
- Use the Phase 2 completion checklist rigorously
- Don't skip any critical criteria
- Get stakeholder sign-off before proceeding
- Fix gaps, don't accept technical debt in planning

---

## Troubleshooting Guide

### Issue: Task estimates are wildly inconsistent

**Symptom**: Same complexity tasks have vastly different estimates

**Diagnosis**: 
- Team doesn't have shared understanding of estimation
- Not using historical velocity as calibration
- Mixing story points with time estimates

**Solution**:
1. Use Planning Poker or similar technique for consensus
2. Calibrate against historical velocity data
3. Use story points for relative sizing, time for planning
4. Break down large tasks until they're comparable to past work

---

### Issue: Dependencies create gridlock

**Symptom**: Many tasks blocked waiting on others, no parallelization possible

**Diagnosis**:
- Architecture too monolithic (everything depends on everything)
- Not designing for independent development
- Missing interface-first approach

**Solution**:
1. Review architecture for excessive coupling
2. Define interfaces/contracts early
3. Use mocking to enable parallel work
4. Consider reordering work to unblock critical path

---

### Issue: Sprint plans don't fit team capacity

**Symptom**: More work than team can do, or not enough work

**Diagnosis**:
- Wrong assumptions about team velocity
- Not accounting for overhead (meetings, code review, etc.)
- Estimates too aggressive or too conservative

**Solution**:
1. Calculate capacity conservatively (70-80% of available time)
2. Review historical velocity data
3. Adjust estimates based on team's actual performance
4. Break large tasks down to better fit sprint boundaries

---

### Issue: Infrastructure setup taking longer than expected

**Symptom**: Sprint 0 dragging on, developers stuck on setup

**Diagnosis**:
- Underestimated complexity of infrastructure
- Missing tools or knowledge
- Configuration issues not anticipated

**Solution**:
1. Extend Sprint 0 if necessary (don't rush foundation)
2. Bring in DevOps expertise if team lacks it
3. Use pre-built templates/frameworks where possible
4. Document setup issues for lessons learned

---

### Issue: Quality standards unclear or unenforced

**Symptom**: Team unsure what "done" means, inconsistent quality

**Diagnosis**:
- Definition of Done not explicit
- Quality standards not measurable
- No automated enforcement

**Solution**:
1. Make Definition of Done a checklist
2. Automate quality checks in CI/CD
3. Include quality criteria in code review
4. Measure and report quality metrics visibly

---

### Issue: Risk register ignored after initial creation

**Symptom**: Risk register created but never reviewed, risks materialize without response

**Diagnosis**:
- No risk monitoring process
- No risk owner assigned
- Risks not integrated into sprint planning

**Solution**:
1. Assign ownership for each risk
2. Schedule regular risk reviews (every sprint)
3. Include risk mitigation tasks in sprint planning
4. Update risk register as new risks emerge

---

## Integration with Other Phases

### Phase 1 → Phase 2 Handoff

**Phase 1 provides**:
- Constitution (quality standards)
- Spec (requirements to implement)
- PRD (priorities and MVP scope)
- Architecture (technical design)
- Data Model (database schema)
- API Spec (integration contracts)

**Phase 2 consumes**:
- Uses requirements to create tasks
- Uses architecture to structure repository
- Uses priorities to plan sprints
- Uses quality standards to define testing

**Validation**: Phase 1 completion checklist must be 100% before Phase 2 starts

---

### Phase 2 → Phase 3 Handoff

**Phase 2 provides**:
- Task breakdown (what to build)
- Sprint plan (when to build)
- Dependency map (order to build)
- Repository (where to build)
- Quality standards (how to build)
- Risk register (what to watch for)

**Phase 3 consumes**:
- Executes tasks from task breakdown
- Follows sprint plan
- Respects dependencies
- Uses repository infrastructure
- Meets quality standards
- Monitors risks

**Validation**: Phase 2 completion checklist must be 100% before Phase 3 starts

---

## Success Metrics for Phase 2

### Process Metrics

✅ **Phase 2 Duration**: 10-14 days (not longer)  
✅ **Stakeholder Engagement**: All key stakeholders participated in reviews  
✅ **Sign-off Rate**: 100% of required approvals obtained  
✅ **Rework Rate**: <10% of Phase 2 artifacts required significant rework

### Output Quality Metrics

✅ **Traceability**: 100% of requirements mapped to tasks  
✅ **Estimation Confidence**: Team confidence in estimates >70%  
✅ **Capacity Utilization**: Planned to 70-80% (not 100%)  
✅ **Infrastructure Readiness**: Developer onboarding <2 hours  
✅ **Quality Coverage**: All test levels planned and measurable

### Predictive Metrics

✅ **Sprint Plan Achievability**: Retrospective shows >80% of planned work completed  
✅ **Risk Mitigation Effectiveness**: <20% of identified risks materialize  
✅ **Velocity Accuracy**: Actual velocity within 20% of planned  
✅ **Infrastructure Stability**: <10% of Sprint 0 time on infrastructure issues

---

## Roles & Responsibilities in Phase 2

### Planning Agent
- **Primary**: Task decomposition, sprint planning, estimation
- **Responsibilities**: Create task breakdown, dependency map, sprint plan
- **Tools**: Work breakdown structure, story mapping, estimation techniques
- **Success Criteria**: Realistic plan that fits team capacity

### DevOps Scaffolder
- **Primary**: Infrastructure setup, CI/CD, environments
- **Responsibilities**: Repository structure, pipeline, tooling, documentation
- **Tools**: Git, Docker, CI/CD platforms, cloud infrastructure
- **Success Criteria**: Developer can onboard and deploy in <2 hours

### Quality Architect
- **Primary**: Quality strategy, test planning, standards
- **Responsibilities**: Test strategy, test plan, quality metrics, Definition of Done
- **Tools**: Test frameworks, coverage tools, quality metrics
- **Success Criteria**: Comprehensive quality approach that ensures constitution standards

### Validator
- **Primary**: Phase completion validation, artifact review
- **Responsibilities**: Run checklists, validate traceability, ensure consistency
- **Tools**: Checklists, traceability matrices, validation frameworks
- **Success Criteria**: All critical criteria met, artifacts consistent

### Product Manager (Human)
- **Primary**: Priority decisions, MVP scope, stakeholder alignment
- **Responsibilities**: Review sprint plans, approve priorities, make trade-off decisions
- **Authority**: Final say on what goes in MVP vs. post-MVP
- **Success Criteria**: Clear priorities, stakeholder buy-in

### Development Team Lead (Human)
- **Primary**: Technical feasibility, capacity validation, developer assignments
- **Responsibilities**: Review estimates, validate approach, identify technical risks
- **Authority**: Can veto unrealistic commitments
- **Success Criteria**: Team understands and commits to plan

### Solutions Architect (Human)
- **Primary**: Architecture integrity, design validation
- **Responsibilities**: Review repository structure, validate technical approach
- **Authority**: Can require architecture changes
- **Success Criteria**: Implementation plan aligns with architecture

---

## Phase 2 Anti-Patterns to Avoid

### Anti-Pattern 1: "Planning is Waste"

**Belief**: "We're agile, we don't need detailed planning"

**Reality**: Without planning, you're not agile, you're just unorganized chaos

**Why it fails**: 
- Team doesn't know what to build
- Dependencies not understood
- Capacity overcommitted
- No infrastructure to work with

**Do instead**: Plan the first 3-5 sprints in detail, maintain rolling wave planning

---

### Anti-Pattern 2: "Perfect Plan Before Starting"

**Belief**: "We must have every task perfectly estimated before we begin"

**Reality**: Plans will change as you learn, diminishing returns on over-planning

**Why it fails**:
- Wastes time planning details that will change
- Delays actual progress
- Creates false sense of certainty

**Do instead**: Plan just enough to start confidently, refine as you go

---

### Anti-Pattern 3: "Infrastructure Later"

**Belief**: "Let's build features first, we can add CI/CD later"

**Reality**: Late infrastructure wastes developer time and creates technical debt

**Why it fails**:
- Developers spend time on manual deployment
- No automated testing, quality suffers
- Hard to retrofit automation later

**Do instead**: Sprint 0 for infrastructure, features in Sprint 1+

---

### Anti-Pattern 4: "Copy-Paste Planning"

**Belief**: "We'll just use the plan from last project"

**Reality**: Every project is different - team, tech, requirements, constraints

**Why it fails**:
- Estimates don't match this team's velocity
- Dependencies are different
- Doesn't account for this project's uniqueness

**Do instead**: Use past projects as reference, but plan this project fresh

---

### Anti-Pattern 5: "Testing is QA's Problem"

**Belief**: "Developers build, QA tests, that's the separation of concerns"

**Reality**: Quality is everyone's responsibility, testing must be built-in

**Why it fails**:
- Bugs found late are expensive to fix
- Testing becomes bottleneck
- Quality suffers, technical debt accumulates

**Do instead**: Developers write tests, QA defines strategy and validates

---

## Conclusion

Phase 2 is the bridge between planning (Phase 1) and building (Phase 3). Success in Phase 2 means:

✅ **Clear Plan**: Every requirement decomposed into implementable tasks  
✅ **Realistic Schedule**: Sprints fit team capacity with buffer for unknowns  
✅ **Ready Infrastructure**: Repository, CI/CD, environments functional  
✅ **Quality Standards**: Testing strategy and metrics defined  
✅ **Risk Management**: Risks identified and mitigation planned  
✅ **Team Readiness**: Everyone understands the plan and their role

With Phase 2 complete, Phase 3 development can begin with confidence that:
- We know what to build
- We know how to build it
- We have the infrastructure to build it
- We have the quality standards to build it right
- We know the risks and how to manage them

**Phase 2 Duration**: 10-14 days  
**Phase 2 Team**: Planning Agent, DevOps Scaffolder, Quality Architect, Validator  
**Phase 2 Output**: Development-ready infrastructure and executable plan

**Next**: [Phase 3: Development](../phase3/README.md)

---

## Quick Reference

### Phase 2 Checklist (High-Level)

- [ ] **Step 0**: Phase 2 Kickoff (1-2 hours)
- [ ] **Step 1**: Task Decomposition (2-3 days)
- [ ] **Step 2**: Dependency Analysis (included in Step 1)
- [ ] **Step 3**: Sprint Planning (2-3 days)
- [ ] **Step 4**: Repository Setup (2-3 days)
- [ ] **Step 5**: Quality Planning (1-2 days)
- [ ] **Step 6**: Risk Assessment (1 day)
- [ ] **Step 7**: Validation & Sign-off (1 day)

**Total**: 10-14 days

### Key Decision Points

1. After Step 0: Ready to proceed with planning?
2. After Step 1: Task breakdown complete and validated?
3. After Step 3: Sprint plans realistic and approved?
4. After Step 4: Infrastructure ready for development?
5. After Step 5: Quality strategy comprehensive?
6. After Step 6: Risks identified and mitigated?
7. After Step 7: Proceed to Phase 3? (GO / CONDITIONAL GO / NO-GO)

### Critical Success Factors

1. ✅ **Complete Phase 1**: Don't start Phase 2 with incomplete Phase 1
2. ✅ **Time-box Phase 2**: Don't let planning drag on indefinitely
3. ✅ **Plan Realistically**: 70-80% capacity, not 100%
4. ✅ **Invest in Infrastructure**: Sprint 0 pays dividends
5. ✅ **Include Quality**: Testing is not an afterthought
6. ✅ **Manage Risks**: Proactive > reactive
7. ✅ **Validate Completely**: Use checklist, don't skip criteria

---

**This workflow is the orchestrator for all Phase 2 activities. Follow it step-by-step to ensure complete and high-quality planning and setup before Phase 3 development begins.**
