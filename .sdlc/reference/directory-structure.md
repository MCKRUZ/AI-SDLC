# Agentic SDLC - Complete Directory Structure

**Version**: 3.0  
**Last Updated**: 2025-12-13  
**Scope**: Full SDLC (Phase 0, 1, 2, 3) + Track System (Quick, Standard, Enterprise)

---

## Overview

This directory structure supports a complete agentic SDLC from discovery through deployment. The structure is tool-agnostic, working conversationally first with optional programmatic enhancements. It separates reusable primitives, organizational memory, and per-project work.

### Key Concepts

**Phases**: The SDLC is divided into four sequential phases:
- **Phase 0**: Discovery & Ideation - Validate the problem
- **Phase 1**: Specification & Design - Define the solution
- **Phase 2**: Planning & Setup - Plan the work and prepare infrastructure
- **Phase 3**: Implementation - Execute sprints and deliver software

**Tracks**: Three methodology tracks provide right-sized planning depth:
- **Quick Track**: 1-4 hours planning for <2 week projects
- **Standard Track**: 2-5 days planning for 2-12 week projects
- **Enterprise Track**: 1-3 weeks planning for 12+ week projects

---

## Complete Directory Tree

```
project-root/
├── .sdlc/                              # Hidden root for SDLC system
│   ├── primitives/                     # Reusable building blocks
│   │   ├── agents/                     # Agent instruction files
│   │   │   ├── phase0/                 # Phase 0: Discovery & Ideation
│   │   │   │   ├── discovery-facilitator.instructions.md
│   │   │   │   ├── feasibility-analyzer.instructions.md
│   │   │   │   └── synthesis-agent.instructions.md
│   │   │   ├── phase1/                 # Phase 1: Specification & Design
│   │   │   │   ├── analyst-agent.instructions.md
│   │   │   │   ├── pm-agent.instructions.md
│   │   │   │   ├── architect-agent.instructions.md
│   │   │   │   ├── constitution-agent.instructions.md
│   │   │   │   └── validator-agent.instructions.md
│   │   │   ├── phase2/                 # Phase 2: Planning & Setup
│   │   │   │   ├── planning-agent.instructions.md
│   │   │   │   ├── devops-scaffolder.instructions.md
│   │   │   │   └── quality-architect.instructions.md
│   │   │   └── phase3/                 # Phase 3: Implementation
│   │   │       ├── scrum-master.instructions.md
│   │   │       ├── developer.instructions.md
│   │   │       └── qa-engineer.instructions.md
│   │   ├── templates/                  # Artifact templates
│   │   │   ├── phase0/
│   │   │   │   ├── problem-statement.template.md
│   │   │   │   ├── interview-transcript.template.md
│   │   │   │   ├── feasibility-report.template.md
│   │   │   │   ├── feasibility-quick.template.md    # Standard Track
│   │   │   │   └── risk-register.template.md
│   │   │   ├── phase1/
│   │   │   │   ├── spec.template.md
│   │   │   │   ├── prd.template.md
│   │   │   │   ├── constitution.template.md
│   │   │   │   ├── architecture.template.md
│   │   │   │   ├── data-model.template.md
│   │   │   │   └── api-spec.template.json
│   │   │   ├── phase2/
│   │   │   │   ├── task-breakdown.template.md
│   │   │   │   ├── sprint-plan.template.md
│   │   │   │   ├── dependency-map.template.md
│   │   │   │   ├── test-plan.template.md
│   │   │   │   ├── repository-structure.template.md
│   │   │   │   └── environment-config.template.md
│   │   │   ├── phase3/
│   │   │   │   ├── story-file.template.md          # Self-contained story context
│   │   │   │   ├── sprint-summary.template.md
│   │   │   │   └── release-notes.template.md
│   │   │   └── quick-track/                        # Quick Track templates
│   │   │       ├── tech-spec-lite.template.md
│   │   │       └── rollback-plan.template.md
│   │   ├── workflows/                  # Multi-step process prompts
│   │   │   ├── scale-selection.workflow.prompt.md  # Track selection (cross-phase)
│   │   │   ├── phase0/
│   │   │   │   ├── discovery-workflow.prompt.md
│   │   │   │   ├── interview-workflow.prompt.md
│   │   │   │   └── synthesis-workflow.prompt.md
│   │   │   ├── phase1/
│   │   │   │   ├── specification-workflow.prompt.md
│   │   │   │   ├── architecture-design.prompt.md
│   │   │   │   └── validation-workflow.prompt.md
│   │   │   ├── phase2/
│   │   │   │   ├── phase2-orchestration.prompt.md
│   │   │   │   ├── task-decomposition.prompt.md
│   │   │   │   ├── sprint-planning.prompt.md
│   │   │   │   ├── repository-setup.prompt.md
│   │   │   │   └── quality-planning.prompt.md
│   │   │   └── phase3/
│   │   │       ├── story-lifecycle.workflow.prompt.md
│   │   │       ├── sprint-execution.workflow.prompt.md
│   │   │       └── release-workflow.prompt.md
│   │   ├── chatmodes/                  # Focused interaction patterns
│   │   │   ├── analyst.chatmode.md
│   │   │   ├── architect.chatmode.md
│   │   │   ├── pm.chatmode.md
│   │   │   └── scrum-master.chatmode.md
│   │   └── checklists/                 # Quality gates
│   │       ├── phase-0-completion.checklist.md
│   │       ├── phase-1-completion.checklist.md
│   │       ├── phase-2-completion.checklist.md
│   │       └── phase-3-sprint.checklist.md
│   ├── memory/                         # Organizational knowledge
│   │   ├── organization.context.md
│   │   ├── technical-stack.context.md
│   │   ├── prior-projects.memory.md
│   │   ├── lessons-learned.memory.md
│   │   └── decisions.memory.md
│   ├── config/                         # Phase and track configurations
│   │   ├── phase0.config.md
│   │   ├── phase1.config.md
│   │   ├── phase2.config.md
│   │   ├── phase3.config.md
│   │   ├── quick-track.config.md       # Track configurations
│   │   ├── standard-track.config.md
│   │   └── enterprise-track.config.md
│   └── reference/                      # Documentation
│       ├── README.md
│       ├── directory-structure.md      # This file
│       ├── document-sharding-strategy.md
│       └── sdlc-workflow.html
│
├── phases/                             # Phase definitions for orchestrator
│   ├── phase0.json
│   ├── phase1.json
│   ├── phase2.json                     # Planning & Setup
│   └── phase3.json                     # Implementation
│
└── projects/                           # All project work
    └── [project-name]/                 # Individual project
        ├── phase0/                     # Discovery artifacts
        │   ├── phase0-context.md       # Current state tracker
        │   ├── interviews/
        │   │   ├── 001-ceo-interview.md
        │   │   ├── 002-cto-interview.md
        │   │   └── ...
        │   ├── working/
        │   │   ├── problem-statement-v1.md
        │   │   ├── problem-statement-v2.md
        │   │   └── notes.md
        │   ├── artifacts/
        │   │   ├── problem-statement.final.md
        │   │   ├── feasibility-report.md
        │   │   ├── risk-register.md
        │   │   ├── success-criteria.md
        │   │   └── constraints.md
        │   └── validation/
        │       ├── phase0-completion-checklist.md
        │       └── phase0-approval.md
        │
        ├── phase1/                     # Specification artifacts
        │   ├── phase1-context.md
        │   ├── working/
        │   │   ├── spec-v1.md
        │   │   ├── architecture-v1.md
        │   │   └── notes.md
        │   ├── artifacts/
        │   │   ├── spec.md
        │   │   ├── prd.md
        │   │   ├── architecture.md
        │   │   ├── data-model.md
        │   │   ├── api-spec.json
        │   │   └── constitution.md
        │   ├── shards/                 # Document shards (Enterprise Track)
        │   │   ├── architecture/
        │   │   │   ├── _index.md
        │   │   │   ├── system-overview.shard.md
        │   │   │   └── component-[name].shard.md
        │   │   ├── prd/
        │   │   │   ├── _index.md
        │   │   │   └── epic-[name].shard.md
        │   │   └── spec/
        │   │       ├── _index.md
        │   │       └── story-[id].shard.md
        │   ├── adrs/
        │   │   ├── 001-technology-selection.md
        │   │   ├── 002-architecture-pattern.md
        │   │   └── 003-deployment-strategy.md
        │   └── validation/
        │       ├── phase1-completion-checklist.md
        │       ├── traceability-matrix.md
        │       └── phase1-approval.md
        │
        ├── phase2/                     # Planning artifacts
        │   ├── phase2-context.md
        │   ├── working/
        │   │   ├── task-breakdown-v1.md
        │   │   ├── sprint-plan-v1.md
        │   │   └── notes.md
        │   ├── artifacts/
        │   │   ├── task-breakdown.md
        │   │   ├── dependency-map.md
        │   │   ├── sprint-plan.md
        │   │   ├── repository-structure.md
        │   │   ├── environment-config.md
        │   │   ├── test-plan.md
        │   │   ├── quality-gates.md
        │   │   └── sprints/
        │   │       ├── sprint-0-plan.md
        │   │       ├── sprint-1-plan.md
        │   │       └── sprint-N-plan.md
        │   └── validation/
        │       ├── phase2-completion-checklist.md
        │       └── phase2-approval.md
        │
        └── phase3/                     # Implementation artifacts
            ├── phase3-context.md
            ├── stories/                # Story files (self-contained)
            │   ├── backlog/            # Ready stories not in sprint
            │   │   ├── PROJ-EPIC-001.story.md
            │   │   └── PROJ-EPIC-002.story.md
            │   ├── sprint-1/           # Current sprint stories
            │   │   ├── PROJ-EPIC-003.story.md
            │   │   └── PROJ-EPIC-004.story.md
            │   ├── sprint-2/
            │   └── completed/          # Done stories (archive)
            │       ├── sprint-0/
            │       └── sprint-1/
            ├── sprints/                # Sprint execution tracking
            │   ├── sprint-0-summary.md
            │   ├── sprint-1-summary.md
            │   └── velocity-report.md
            ├── releases/               # Release artifacts
            │   ├── v1.0.0/
            │   │   ├── release-notes.md
            │   │   └── changelog.md
            │   └── v1.1.0/
            └── validation/
                └── sprint-completion-checklists/
```

---

## Directory Deep Dive

### `.sdlc/` (Hidden Root)

The system root containing all reusable assets, templates, and organizational knowledge. This directory is shared across all projects and rarely changes.

---

### `.sdlc/primitives/`

Reusable building blocks based on GitHub's agentic primitives framework.

#### `agents/`

Agent instruction files defining specialized AI personas with clear responsibilities, decision-making logic, and workflows. Organized by phase.

**Phase 0 Agents** (Discovery & Ideation):
- `discovery-facilitator.instructions.md` - Conducts stakeholder interviews, synthesizes insights
- `feasibility-analyzer.instructions.md` - Assesses technical/business/resource/timeline feasibility
- `synthesis-agent.instructions.md` - Consolidates discovery findings into artifacts

**Phase 1 Agents** (Specification & Design):
- `analyst-agent.instructions.md` - Creates technical specifications and user stories
- `pm-agent.instructions.md` - Creates product requirements documents and prioritizes features
- `architect-agent.instructions.md` - Designs system architecture and makes technology decisions
- `constitution-agent.instructions.md` - Creates project constitution with values and constraints
- `validator-agent.instructions.md` - Validates artifacts against quality standards

**Phase 2 Agents** (Planning & Setup):
- `planning-agent.instructions.md` - Decomposes tasks, plans sprints, manages dependencies
- `devops-scaffolder.instructions.md` - Sets up repository, infrastructure, CI/CD pipelines
- `quality-architect.instructions.md` - Designs testing strategy and quality frameworks

**Phase 3 Agents** (Implementation):
- `scrum-master.instructions.md` - Creates story files, manages sprints, facilitates handoffs
- `developer.instructions.md` - Implements features based on story files
- `qa-engineer.instructions.md` - Validates implementations, executes tests, provides signoff

---

#### `templates/`

Markdown/JSON templates for all artifacts. Organized by phase plus special folders.

**Phase 0 Templates**: Problem statements, interview transcripts, feasibility reports
**Phase 1 Templates**: Specs, PRDs, architecture docs, data models, API specs
**Phase 2 Templates**: Task breakdowns, sprint plans, test plans, environment configs
**Phase 3 Templates**: Story files, sprint summaries, release notes
**Quick Track Templates**: Lightweight tech specs, rollback plans

---

#### `workflows/`

Multi-step process prompts that orchestrate complex activities.

**Cross-Phase Workflows**:
- `scale-selection.workflow.prompt.md` - Determines Quick/Standard/Enterprise track

**Phase-Specific Workflows**: Discovery, specification, planning, and implementation workflows

---

### `.sdlc/config/`

Configuration files that define how phases and tracks operate.

**Phase Configs** (`phase0.config.md` through `phase3.config.md`):
- Agent modes and behaviors
- Required vs optional artifacts
- Quality gate thresholds
- Session management guidelines

**Track Configs** (`quick-track.config.md`, `standard-track.config.md`, `enterprise-track.config.md`):
- Which phases to use/skip
- Time budgets
- Required artifacts per track
- Escalation/de-escalation triggers

---

### `phases/`

JSON phase definitions for the SDLCOrchestrator automation tool.

- `phase0.json` - Discovery agents and configuration
- `phase1.json` - Specification agents and configuration
- `phase2.json` - Planning agents (PlanningAgent, DevOpsScaffolder, QualityArchitect)
- `phase3.json` - Implementation agents (ScrumMaster, Developer, QAEngineer)

---

### `projects/[project-name]/`

Per-project work organized by phase.

#### `phase0/` - Discovery Artifacts

Contains stakeholder interviews, problem exploration, and feasibility assessment.

#### `phase1/` - Specification Artifacts

Contains requirements, architecture, and design decisions. Includes `shards/` directory for Enterprise Track document sharding.

#### `phase2/` - Planning Artifacts

Contains task breakdowns, sprint plans, and infrastructure documentation.

#### `phase3/` - Implementation Artifacts

**New in v3.0**: Contains story files organized by lifecycle status:
- `stories/backlog/` - Ready stories not yet in a sprint
- `stories/sprint-N/` - Stories in current sprint
- `stories/completed/` - Archived done stories

Also contains sprint summaries, velocity reports, and release artifacts.

---

## The Three Tracks

### Quick Track

**When to Use**: Bug fixes, small features, <2 weeks effort, clear requirements

**Phases Used**:
- Phase 0: SKIP
- Phase 1: MINIMAL (tech-spec-lite only)
- Phase 2: SKIP
- Phase 3: Direct implementation

**Directory Impact**:
```
projects/[project]/
├── artifacts/
│   └── tech-spec-lite.md
└── [implementation directly in code repo]
```

---

### Standard Track

**When to Use**: Features, small projects, 2-12 weeks effort

**Phases Used**:
- Phase 0: ABBREVIATED (conversations, not formal interviews)
- Phase 1: FULL
- Phase 2: STANDARD
- Phase 3: FULL

**Directory Impact**: Standard structure without shards

---

### Enterprise Track

**When to Use**: Major initiatives, 12+ weeks, complex stakeholders, high stakes

**Phases Used**:
- Phase 0: FULL (formal interviews, comprehensive discovery)
- Phase 1: FULL with document sharding
- Phase 2: FULL with cost estimation and resource planning
- Phase 3: FULL with comprehensive story management

**Directory Impact**: Full structure including `shards/` directories

---

## File Naming Conventions

### Agent Instructions
**Format**: `[agent-name].instructions.md`  
**Location**: `.sdlc/primitives/agents/phase[N]/`

### Templates
**Format**: `[artifact-name].template.md` or `.json`  
**Location**: `.sdlc/primitives/templates/phase[N]/` or `quick-track/`

### Workflows
**Format**: `[workflow-name].workflow.prompt.md` or `[workflow-name].prompt.md`  
**Location**: `.sdlc/primitives/workflows/phase[N]/`

### Story Files
**Format**: `[STORY-ID].story.md` (e.g., `PORTAL-AUTH-003.story.md`)  
**Location**: `projects/[project]/phase3/stories/[status]/`

### Shards
**Format**: `[type]-[name].shard.md`  
**Location**: `projects/[project]/phase1/shards/[artifact-type]/`

### Working Versions
**Format**: `[artifact-name]-v[N].md`  
**Location**: `projects/[project]/phase[N]/working/`

---

## Integration Between Phases

### Phase 0 → Phase 1 Handoff

**Trigger**: Phase 0 validation complete, GO decision obtained

**Artifacts Passed**:
- `problem-statement.final.md`
- `feasibility-report.md`
- `success-criteria.md`
- `constraints.md`
- `risk-register.md`

---

### Phase 1 → Phase 2 Handoff

**Trigger**: Phase 1 validation complete, all approvals obtained

**Artifacts Passed**:
- `spec.md`, `prd.md`, `architecture.md`
- `data-model.md`, `api-spec.json`
- `constitution.md`
- All ADRs

---

### Phase 2 → Phase 3 Handoff

**Trigger**: Phase 2 validation complete, infrastructure ready

**Artifacts Passed**:
- `task-breakdown.md`, `sprint-plan.md`
- `test-plan.md`, `quality-gates.md`
- Repository URL with working CI/CD
- Environment access

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-10-31 | Initial structure (Phase 0, 1, 2) |
| 2.0 | 2025-11-15 | Added cost estimation, resource planning |
| 3.0 | 2025-12-13 | Added Phase 3, Track system, Story files, Document sharding |
