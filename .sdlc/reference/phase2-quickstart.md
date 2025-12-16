# Phase 2: Planning & Setup - Quick Start Guide

**Purpose**: Use Phase 2 to plan HOW to build by decomposing requirements into tasks, planning sprints, and setting up infrastructure.

**When to Use Phase 2**:
- After Phase 1 specification is complete
- Starting implementation of a specified project
- Setting up a new development environment
- Planning sprints for a defined scope

**When to Skip Phase 2**:
- Very small projects (< 1 week)
- Solo work with no infrastructure needs
- Continuation of existing project with established process

---

## What You'll Produce

| Artifact | Purpose |
|----------|---------|
| **Task Breakdown** | All requirements decomposed into implementable tasks |
| **Dependency Map** | Technical dependencies between tasks |
| **Sprint Plan** | Tasks allocated to sprints |
| **Repository Structure** | Code organization and setup |
| **CI/CD Pipeline** | Automated build, test, deploy |
| **Test Plan** | Testing strategy and approach |
| **Quality Gates** | Automated quality checkpoints |
| **Developer Onboarding** | How to get started |

---

## Quick Start (30 minutes to first session)

### Step 1: Create Workspace

```bash
# Create project structure
mkdir -p projects/[project-name]/phase2/{working,artifacts,validation}

# Initialize context file
touch projects/[project-name]/phase2/phase2-context.md
```

### Step 2: Gather Inputs

**If coming from Phase 1**, load:
- `phase1/artifacts/constitution.md`
- `phase1/artifacts/spec.md`
- `phase1/artifacts/prd.md`
- `phase1/artifacts/architecture.md`
- `phase1/artifacts/data-model.md`
- `phase1/artifacts/api-spec.json`

**If starting fresh** (scope already defined elsewhere), prepare:
- Requirements list with acceptance criteria
- Architecture/design decisions
- Technology stack
- Team composition

### Step 3: Load Required Files

Load these into your AI context:

**Agent Instructions** (load as needed):
```
.sdlc/primitives/agents/phase2/planning-agent_instructions.md
.sdlc/primitives/agents/phase2/devops-scaffolder_instructions.md
.sdlc/primitives/agents/phase2/quality-architect_instructions.md
```

**Configuration**:
```
.sdlc/config/phase2_config.md
```

**Organizational Context**:
```
.sdlc/memory/organization_context.md
.sdlc/memory/technical-stack_context.md
.sdlc/memory/lessons-learned_memory.md  # For velocity data
```

### Step 4: Start with Task Decomposition

Use this prompt to begin:

```
I'm starting Phase 2 planning for [project name].

Here's the context:
- Specification: [Paste spec.md summary or load file]
- Architecture: [Paste architecture summary or load file]
- Team size: [N] developers
- Sprint length: [N] weeks
- Target delivery: [Date or "flexible"]

Let's start by decomposing requirements into implementable tasks.
Please use the Planning Agent instructions.

Constraints:
- Maximum task size: 5 days
- Each task must be independently testable
- Must respect the architecture component boundaries
```

---

## Phase 2 Flow

```
┌─────────────────────────────────────────────────────────────┐
│                         PHASE 2                              │
└─────────────────────────────────────────────────────────────┘
                              │
              ┌───────────────┴───────────────┐
              ▼                               ▼
   ┌────────────────────┐        ┌────────────────────┐
   │  1. TASK BREAKDOWN │        │  2. DEPENDENCY MAP │
   │    (2-3 days)      │        │  (included in #1)  │
   │  Decompose reqs    │        │  Identify order    │
   └─────────┬──────────┘        └─────────┬──────────┘
             │                              │
             └───────────────┬──────────────┘
                             ▼
               ┌──────────────────────────┐
               │    3. SPRINT PLANNING    │
               │      (2-3 days)          │
               │  Allocate to sprints     │
               └──────────────┬───────────┘
                              │
              ┌───────────────┴───────────────┐
              ▼                               ▼
   ┌────────────────────┐        ┌────────────────────┐
   │  4. REPO SETUP     │        │ 5. QUALITY PLANNING│
   │  (DevOps)          │        │ (Quality Architect)│
   │  (2-3 days)        │        │ (1-2 days)         │
   └─────────┬──────────┘        └─────────┬──────────┘
             │                              │
             └───────────────┬──────────────┘
                             ▼
               ┌──────────────────────────┐
               │    6. VALIDATION         │
               │      (1 day)             │
               │  Ready for development   │
               └──────────────────────────┘
```

---

## Key Activities

### Task Decomposition (Planning Agent)

Break every requirement into tasks:
- **Size**: 2-5 days maximum
- **Clarity**: Clear acceptance criteria
- **Independence**: Can be tested in isolation
- **Estimates**: Story points AND time

**Chatmode**: Use `planning-agent.chatmode.md`

**Key outputs**:
- `task-breakdown.md` - All tasks with estimates
- `dependency-map.md` - Task ordering

### Sprint Planning (Planning Agent)

Allocate tasks to sprints:
- **Capacity**: Plan to 70-80%, not 100%
- **Dependencies**: Respect task ordering
- **MVP**: Ensure MVP features are prioritized
- **Sprint 0**: Include setup/infrastructure time

**Key outputs**:
- `sprint-plan.md` - Sprint-by-sprint allocation

### Repository & Infrastructure Setup (DevOps Scaffolder)

Set up development environment:
- Repository structure
- CI/CD pipelines
- Docker configuration
- Development environment
- Onboarding documentation

**Chatmode**: Use `devops-scaffolder.chatmode.md`

**Key outputs**:
- Working repository
- Functional CI/CD
- Developer onboarding guide

### Quality Planning (Quality Architect)

Define quality approach:
- Test strategy (unit, integration, E2E)
- Quality metrics and thresholds
- Quality gates for CI/CD
- Definition of Done

**Chatmode**: Use `quality-architect.chatmode.md`

**Key outputs**:
- `test-plan.md`
- Quality gate configurations
- Definition of Done

---

## Completion Checklist

Before exiting Phase 2:

- [ ] All requirements decomposed into tasks
- [ ] All tasks < 5 days
- [ ] All tasks have acceptance criteria
- [ ] Dependencies mapped
- [ ] Critical path identified
- [ ] Sprints planned within capacity (70-80%)
- [ ] MVP fits within target timeline
- [ ] Repository created and accessible
- [ ] CI/CD pipeline functional
- [ ] Development environment works
- [ ] Test strategy defined
- [ ] Quality gates configured
- [ ] Definition of Done agreed
- [ ] Team can start Sprint 0

Use: `.sdlc/primitives/checklists/phase-2-completion_checklist.md`

---

## Handoff to Development (Phase 3)

Development team receives:

1. `task-breakdown.md` - What to build
2. `sprint-plan.md` - When to build it
3. `dependency-map.md` - Order constraints
4. Repository URL - Where to build it
5. CI/CD status - How to deploy
6. `test-plan.md` - How to test
7. Definition of Done - When it's done

---

## Tips for Success

✅ **Decompose thoroughly** - Smaller tasks are easier to estimate and track

✅ **Don't over-plan** - Plan 3-5 sprints ahead, not the entire project

✅ **Plan to 70-80% capacity** - Leave room for unknowns and interruptions

✅ **Sprint 0 matters** - Invest in infrastructure; it pays dividends

✅ **Quality gates in CI** - Enforce standards automatically

✅ **Test your setup** - New developer should onboard in < 2 hours

---

## Common Pitfalls

❌ **Tasks too big** - "Build authentication" is not a task; break it down

❌ **100% capacity planning** - Guarantees slipping

❌ **Ignoring dependencies** - Causes blocked developers

❌ **Skipping Sprint 0** - Leads to infrastructure firefighting

❌ **Manual quality checks** - Automate in CI/CD

❌ **No onboarding docs** - Wastes time for every new person

---

## Parallel Workstreams

Phase 2 can run some activities in parallel:

```
Week 1:
├── Task Decomposition (Planning Agent)
└── Repository Setup starts (DevOps Scaffolder)

Week 2:
├── Sprint Planning (Planning Agent)
├── Repository Setup continues
└── Quality Planning starts (Quality Architect)

Week 3:
├── Validation
├── Quality Planning completes
└── Team onboarding
```

---

## Session Strategies

| Session | Focus | Duration | Agent |
|---------|-------|----------|-------|
| 1-2 | Task Decomposition | 3-4 hours each | Planning |
| 3 | Dependency Mapping | 2-3 hours | Planning |
| 4 | Sprint Planning | 3-4 hours | Planning |
| 5-6 | Repository Setup | 2-3 hours each | DevOps |
| 7 | Quality Planning | 3-4 hours | Quality |
| 8 | Validation | 2-3 hours | All |

**Between sessions**: Save context to `phase2-context.md`

---

## Need Help?

**Full Workflow**: `.sdlc/primitives/workflows/phase2/phase2-orchestration.prompt.md`

**Task Decomposition**: `.sdlc/primitives/workflows/phase2/task-decomposition.prompt.md`

**Sprint Planning**: `.sdlc/primitives/workflows/phase2/sprint-planning.prompt.md`

**Chatmodes**:
- `planning-agent.chatmode.md`
- `devops-scaffolder.chatmode.md`
- `quality-architect.chatmode.md`

---

*Phase 2 is where intention becomes plan. Good planning prevents the chaos of unstructured development.*
