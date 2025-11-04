# Agentic SDLC - Complete Directory Structure

**Version**: 2.0  
**Last Updated**: 2025-10-31  
**Scope**: Full SDLC (Phase 0, 1, 2)

---

## Overview

This directory structure supports a complete agentic SDLC from discovery through deployment. The structure is tool-agnostic, working conversationally first with optional programmatic enhancements. It separates reusable primitives, organizational memory, and per-project work.

---

## Complete Directory Tree

```
project-root/
├── .sdlc/                              # Hidden root for SDLC system
│   ├── primitives/                     # Reusable building blocks
│   │   ├── agents/                     # Agent instruction files
│   │   │   ├── phase0/                 # Phase 0: Discovery & Ideation
│   │   │   │   ├── discovery-facilitator_instructions.md
│   │   │   │   ├── feasibility-analyzer_instructions.md
│   │   │   │   └── synthesis-agent_instructions.md
│   │   │   ├── phase1/                 # Phase 1: Specification & Design
│   │   │   │   ├── analyst-agent_instructions.md
│   │   │   │   ├── pm-agent_instructions.md
│   │   │   │   ├── architect-agent_instructions.md
│   │   │   │   ├── constitution-agent_instructions.md
│   │   │   │   └── validator-agent_instructions.md
│   │   │   └── phase2/                 # Phase 2: Planning & Setup
│   │   │       ├── planning-agent_instructions.md
│   │   │       ├── devops-scaffolder_instructions.md
│   │   │       └── quality-architect_instructions.md
│   │   ├── templates/                  # Artifact templates
│   │   │   ├── phase0/
│   │   │   │   ├── problem-statement_template.md
│   │   │   │   ├── interview-transcript_template.md
│   │   │   │   ├── feasibility-report_template.md
│   │   │   │   └── risk-register_template.md
│   │   │   ├── phase1/
│   │   │   │   ├── spec_template.md
│   │   │   │   ├── prd_template.md
│   │   │   │   ├── constitution_template.md
│   │   │   │   ├── architecture_template.md
│   │   │   │   ├── data-model_template.md
│   │   │   │   └── api-spec_template.json
│   │   │   └── phase2/
│   │   │       ├── task-breakdown_template.md
│   │   │       ├── sprint-plan_template.md
│   │   │       ├── dependency-map_template.md
│   │   │       ├── test-plan_template.md
│   │   │       ├── repository-structure_template.md
│   │   │       └── environment-config_template.md
│   │   ├── workflows/                  # Multi-step process prompts
│   │   │   ├── phase0/
│   │   │   │   ├── discovery-workflow_prompt.md
│   │   │   │   ├── interview-workflow_prompt.md
│   │   │   │   └── requirements-discovery_prompt.md
│   │   │   ├── phase1/
│   │   │   │   ├── requirements-discovery_prompt.md
│   │   │   │   ├── architecture-design_prompt.md
│   │   │   │   └── risk-assessment_prompt.md
│   │   │   └── phase2/
│   │   │       ├── phase2-orchestration_prompt.md
│   │   │       ├── task-decomposition_prompt.md
│   │   │       ├── sprint-planning_prompt.md
│   │   │       ├── repository-setup_prompt.md
│   │   │       └── quality-planning_prompt.md
│   │   ├── chatmodes/                  # Focused interaction patterns
│   │   │   ├── analyst_chatmode.md
│   │   │   ├── architect_chatmode.md
│   │   │   ├── pm_chatmode.md
│   │   │   └── validator_chatmode.md
│   │   └── checklists/                 # Quality gates and validation
│   │       ├── phase-0-completion_checklist.md
│   │       ├── phase-1-completion_checklist.md
│   │       └── phase-2-completion_checklist.md
│   ├── memory/                         # Persistent organizational knowledge
│   │   ├── organization_context.md     # Company info, industry, culture
│   │   ├── technical-stack_context.md  # Current tech stack, standards
│   │   ├── prior-projects_memory.md    # Past project outcomes
│   │   ├── lessons-learned_memory.md   # Accumulated wisdom
│   │   └── decisions_memory.md         # Key decisions made
│   ├── config/                         # Phase configuration files
│   │   ├── phase0_config.md            # Discovery & Ideation config
│   │   ├── phase1_config.md            # Specification & Design config
│   │   └── phase2_config.md            # Planning & Setup config
│   └── reference/                      # Reference documentation
│       ├── sdlc-workflow.html          # Visual workflow diagram
│       ├── directory-structure.md      # This file
│       └── getting-started.md          # Quick start guide
│
├── projects/                           # All project work
│   └── [project-name]/                 # Individual project folder
│       ├── phase0/                     # Phase 0: Discovery & Ideation
│       │   ├── phase0-context.md       # Current state tracker (per project)
│       │   ├── interviews/             # Stakeholder interviews
│       │   │   ├── 001-ceo-interview.md
│       │   │   ├── 002-cto-interview.md
│       │   │   └── 003-user-interviews.md
│       │   ├── working/                # Iterative drafts
│       │   │   ├── problem-statement-v1.md
│       │   │   ├── problem-statement-v2.md
│       │   │   ├── problem-statement-v3.md
│       │   │   └── notes.md
│       │   ├── artifacts/              # Final, validated deliverables
│       │   │   ├── problem-statement.final.md
│       │   │   ├── feasibility-report.md
│       │   │   ├── risk-register.md
│       │   │   ├── success-criteria.md
│       │   │   ├── constraints.md
│       │   │   └── stakeholder-alignment.md
│       │   └── validation/             # Quality checks and approvals
│       │       ├── phase0-completion-checklist.md
│       │       ├── phase0-validation-report.md
│       │       ├── phase0-approval.md
│       │       └── stakeholder-approvals.md
│       │
│       ├── phase1/                     # Phase 1: Specification & Design
│       │   ├── phase1-context.md       # Current state tracker (per project)
│       │   ├── working/                # Iterative drafts
│       │   │   ├── spec-v1.md
│       │   │   ├── spec-v2.md
│       │   │   ├── architecture-v1.md
│       │   │   ├── architecture-v2.md
│       │   │   ├── constitution-v1.md
│       │   │   ├── prd-v1.md
│       │   │   └── notes.md
│       │   ├── artifacts/              # Final, validated deliverables
│       │   │   ├── spec.md
│       │   │   ├── architecture.md
│       │   │   ├── data-model.md
│       │   │   ├── api-spec.json
│       │   │   ├── constitution.md
│       │   │   └── prd.md
│       │   ├── adrs/                   # Architecture Decision Records
│       │   │   ├── 001-frontend-framework.md
│       │   │   ├── 002-database-choice.md
│       │   │   └── 003-deployment-strategy.md
│       │   └── validation/             # Quality checks and approvals
│       │       ├── phase1-completion-checklist.md
│       │       ├── phase1-validation-report.md
│       │       ├── phase1-approval.md
│       │       ├── traceability-matrix.md
│       │       ├── spec-approval.md
│       │       ├── architecture-approval.md
│       │       ├── constitution-approval.md
│       │       └── prd-approval.md
│       │
│       └── phase2/                     # Phase 2: Planning & Setup
│           ├── phase2-context.md       # Current state tracker (per project)
│           ├── working/                # Iterative drafts
│           │   ├── task-breakdown-v1.md
│           │   ├── task-breakdown-v2.md
│           │   ├── sprint-plan-v1.md
│           │   ├── sprint-plan-v2.md
│           │   ├── test-plan-v1.md
│           │   └── notes.md
│           ├── artifacts/              # Final, validated deliverables
│           │   ├── task-breakdown.md
│           │   ├── dependency-map.md
│           │   ├── sprint-plan.md
│           │   ├── repository-structure.md
│           │   ├── environment-config.md
│           │   ├── test-plan.md
│           │   ├── quality-gates.md
│           │   └── sprints/            # Individual sprint plans
│           │       ├── sprint-0-plan.md
│           │       ├── sprint-1-plan.md
│           │       ├── sprint-2-plan.md
│           │       └── sprint-N-plan.md
│           └── validation/             # Quality checks and approvals
│               ├── phase2-completion-checklist.md
│               ├── phase2-validation-report.md
│               ├── phase2-approval.md
│               ├── task-breakdown-approval.md
│               └── sprint-plan-approval.md
│
└── [actual-code-repository]/          # Created in Phase 2, used in Phase 3+
    ├── src/
    ├── tests/
    ├── docs/
    └── .github/
```

---

## Directory Deep Dive

### `.sdlc/` (Hidden Root)

The system root containing all reusable assets, templates, and organizational knowledge. This directory is shared across all projects and rarely changes.

---

#### `.sdlc/primitives/`

Reusable building blocks based on GitHub's agentic primitives framework.

##### `agents/`

Agent instruction files defining specialized AI personas with clear responsibilities, decision-making logic, and workflows. Organized by phase.

**Phase 0 Agents** (Discovery & Ideation):
- `discovery-facilitator_instructions.md` - Conducts stakeholder interviews, synthesizes insights
- `feasibility-analyzer_instructions.md` - Assesses technical/business/resource/timeline feasibility
- `synthesis-agent_instructions.md` - Consolidates discovery findings into artifacts

**Phase 1 Agents** (Specification & Design):
- `analyst-agent_instructions.md` - Creates technical specifications and user stories
- `pm-agent_instructions.md` - Creates product requirements documents and prioritizes features
- `architect-agent_instructions.md` - Designs system architecture and makes technology decisions
- `constitution-agent_instructions.md` - Creates project constitution with values and constraints
- `validator-agent_instructions.md` - Validates artifacts against quality standards

**Phase 2 Agents** (Planning & Setup):
- `planning-agent_instructions.md` - Decomposes tasks, plans sprints, manages dependencies
- `devops-scaffolder_instructions.md` - Sets up repository, infrastructure, CI/CD pipelines
- `quality-architect_instructions.md` - Designs testing strategy and quality frameworks

---

##### `templates/`

Markdown/JSON templates for all artifacts. Organized by phase. These provide structure and guidance for creating consistent, high-quality deliverables.

**Phase 0 Templates**:
- `problem-statement_template.md` - Structured problem definition with Five Whys
- `interview-transcript_template.md` - Consistent interview documentation format
- `feasibility-report_template.md` - Four-dimension feasibility assessment
- `risk-register_template.md` - Risk identification and mitigation tracking

**Phase 1 Templates**:
- `spec_template.md` - Technical specification with user stories and acceptance criteria
- `prd_template.md` - Product requirements document with MVP definition
- `constitution_template.md` - Project values, constraints, and decision framework
- `architecture_template.md` - C4 model architecture documentation
- `data-model_template.md` - Entity-relationship and data architecture
- `api-spec_template.json` - OpenAPI 3.0 specification

**Phase 2 Templates**:
- `task-breakdown_template.md` - Detailed task decomposition with estimates
- `sprint-plan_template.md` - Sprint planning with goals and capacity
- `dependency-map_template.md` - Task dependency visualization
- `test-plan_template.md` - Comprehensive testing strategy
- `repository-structure_template.md` - Code repository organization
- `environment-config_template.md` - Infrastructure and environment setup

---

##### `workflows/`

Multi-step process prompts that orchestrate complex activities. These combine multiple agents and define the sequence of steps for major workflows.

**Phase 0 Workflows**:
- `discovery-workflow_prompt.md` - End-to-end discovery process
- `interview-workflow_prompt.md` - Structured stakeholder interview process
- `requirements-discovery_prompt.md` - Requirements elicitation and validation

**Phase 1 Workflows**:
- `requirements-discovery_prompt.md` - Creating detailed technical specifications
- `architecture-design_prompt.md` - System architecture design process
- `risk-assessment_prompt.md` - Risk identification and mitigation planning

**Phase 2 Workflows**:
- `phase2-orchestration_prompt.md` - Overall Phase 2 coordination (parallel workstreams)
- `task-decomposition_prompt.md` - Breaking requirements into implementable tasks
- `sprint-planning_prompt.md` - Sprint planning and capacity management
- `repository-setup_prompt.md` - Code repository initialization and configuration
- `quality-planning_prompt.md` - Test strategy and quality framework setup

---

##### `chatmodes/`

Focused interaction patterns that define how to engage with specific agent personas in context-specific situations. These enable efficient, targeted conversations.

- `analyst_chatmode.md` - Requirements elicitation and specification mode
- `architect_chatmode.md` - Architecture design and review mode
- `pm_chatmode.md` - Product planning and prioritization mode
- `validator_chatmode.md` - Artifact validation and quality assurance mode

---

##### `checklists/`

Quality gates and completion criteria for each phase. Used during validation to ensure nothing is missed.

- `phase-0-completion_checklist.md` - Discovery completion criteria
- `phase-1-completion_checklist.md` - Specification & design completion criteria
- `phase-2-completion_checklist.md` - Planning & setup completion criteria

---

#### `.sdlc/memory/`

Persistent organizational knowledge loaded across sessions. These files capture context that applies to all projects and accumulates over time.

- `organization_context.md` - Company information, industry, size, culture, structure
- `technical-stack_context.md` - Current technology stack, standards, preferences, constraints
- `prior-projects_memory.md` - Historical project data, outcomes, lessons, patterns
- `lessons-learned_memory.md` - Accumulated wisdom from retrospectives and post-mortems
- `decisions_memory.md` - Key organizational and technical decisions made over time

**Context Loading Strategy**: 
- Load `organization_context.md` and `technical-stack_context.md` for ALL activities
- Load `prior-projects_memory.md` when similar projects exist
- Load `lessons-learned_memory.md` when relevant lessons apply
- Load `decisions_memory.md` when making decisions

---

#### `.sdlc/config/`

Phase configuration files that define HOW each phase operates. These are organization-wide settings that can be customized per company/team.

- `phase0_config.md` - Discovery & ideation configuration (interview methods, feasibility frameworks, quality standards)
- `phase1_config.md` - Specification & design configuration (requirements methodologies, architecture approaches, quality thresholds)
- `phase2_config.md` - Planning & setup configuration (task sizing, sprint planning, infrastructure standards, quality frameworks)

**Key Settings**:
- Agent behavior preferences
- Methodology selections (Agile, waterfall, hybrid)
- Quality standards and thresholds
- Session management rules
- Validation criteria
- Handoff requirements

---

#### `.sdlc/reference/`

Reference documentation and guides.

- `sdlc-workflow.html` - Interactive visual workflow diagram
- `directory-structure.md` - This file
- `getting-started.md` - Quick start guide for new users

---

### `projects/[project-name]/`

Each project gets its own folder containing all work across all phases. This structure keeps project artifacts organized and traceable.

---

#### `phase0/` (Discovery & Ideation)

Discovery phase artifacts focused on validating the problem before investing in solutions.

##### `phase0-context.md`

**Critical per-project file** that tracks the current state of Phase 0:
- Discovery progress (interviews completed, insights gathered)
- Artifact status (problem statement version, feasibility score)
- Stakeholder alignment
- Issues and blockers
- Key decisions made
- What context agents should load

**Update frequency**: After each interview, after each artifact iteration, when blockers arise

##### `interviews/`

Raw stakeholder interview transcripts. Each interview gets its own file with consistent naming.

**Naming**: `NNN-[stakeholder-role]-interview.md`
- `001-ceo-interview.md`
- `002-cto-interview.md`
- `003-support-lead-interview.md`

**Content**: Uses template format with structured sections (background, jobs-to-be-done, pain points, Five Whys, etc.)

##### `working/`

Iterative drafts showing the evolution of understanding. Demonstrates delta tracking and refinement process.

**Versioned files**: `artifact-name-vN.md`
- `problem-statement-v1.md` (after initial interviews)
- `problem-statement-v2.md` (refined after more interviews)
- `problem-statement-v3.md` (refined after stakeholder feedback)

**Retention**: Keep all versions to trace problem understanding evolution

##### `artifacts/`

Final, validated deliverables that pass quality gates and receive stakeholder approval.

**Required artifacts**:
- `problem-statement.final.md` - Validated problem definition with root cause analysis
- `feasibility-report.md` - Four-dimension feasibility assessment
- `risk-register.md` - Identified risks with mitigation strategies
- `success-criteria.md` - SMART metrics for project success
- `constraints.md` - Technical, business, resource, timeline constraints
- `stakeholder-alignment.md` - Stakeholder positions and consensus

##### `validation/`

Quality checks, approvals, and traceability documents.

- `phase0-completion-checklist.md` - Completed checklist from template
- `phase0-validation-report.md` - Overall validation results
- `phase0-approval.md` - Final sign-off to proceed to Phase 1
- `stakeholder-approvals.md` - Individual stakeholder approvals

---

#### `phase1/` (Specification & Design)

Specification and design phase artifacts that define WHAT to build and HOW it will be architected.

##### `phase1-context.md`

**Critical per-project file** that tracks the current state of Phase 1:
- Artifact status (spec version, architecture completion, quality scores)
- Validation results (INVEST scores, traceability coverage)
- Review and approval status
- Issues and blockers
- Key decisions made
- ADRs created
- What context agents should load

**Update frequency**: After each major artifact iteration, after reviews, when decisions made

##### `working/`

Iterative drafts of specifications and architecture documents.

**Versioned files**:
- `spec-v1.md`, `spec-v2.md`, `spec-vN.md`
- `architecture-v1.md`, `architecture-v2.md`, `architecture-vN.md`
- `constitution-v1.md`, `constitution-v2.md`, `constitution-vN.md`
- `prd-v1.md`, `prd-v2.md`, `prd-vN.md`

**Notes**: Use `notes.md` for working thoughts and decisions

##### `artifacts/`

Final, validated deliverables ready for implementation.

**Required artifacts**:
- `spec.md` - Complete technical specification with user stories, acceptance criteria, NFRs
- `architecture.md` - System architecture with C4 diagrams, technology decisions
- `data-model.md` - Entity-relationship diagrams and data architecture
- `api-spec.json` - OpenAPI 3.0 specification for all APIs
- `constitution.md` - Project values, constraints, anti-patterns, decision framework
- `prd.md` - Product requirements document with MVP definition and success metrics

##### `adrs/` (Architecture Decision Records)

Documented architecture decisions with context, rationale, alternatives, and consequences.

**Naming**: `NNN-[decision-title].md`
- `001-frontend-framework.md` (React vs Angular vs Vue)
- `002-database-choice.md` (PostgreSQL vs MongoDB)
- `003-deployment-strategy.md` (Kubernetes vs serverless)

**Format**: Standard ADR template (Context, Decision, Consequences, Alternatives)

##### `validation/`

Quality checks, approvals, and traceability documents.

- `phase1-completion-checklist.md` - Completed checklist
- `phase1-validation-report.md` - Overall validation with quality scores
- `phase1-approval.md` - Final sign-off to proceed to Phase 2
- `traceability-matrix.md` - Phase 0 → Phase 1 traceability
- `spec-approval.md` - Specification approval
- `architecture-approval.md` - Architecture approval
- `constitution-approval.md` - Constitution approval
- `prd-approval.md` - PRD approval

---

#### `phase2/` (Planning & Setup)

Planning and infrastructure setup phase that prepares for implementation.

##### `phase2-context.md`

**Critical per-project file** that tracks the current state of Phase 2:
- Workstream status (Planning, Infrastructure, Quality)
- Artifact status (task breakdown, sprint plan, infrastructure readiness)
- Sprint plan summary (total sprints, velocity, capacity)
- Infrastructure status (environments provisioned, CI/CD setup)
- Issues and blockers
- Team capacity and assignments
- What context agents should load

**Update frequency**: After each workstream milestone, weekly progress updates, when infrastructure changes

##### `working/`

Iterative drafts of plans and configurations.

**Versioned files**:
- `task-breakdown-v1.md`, `task-breakdown-v2.md`, `task-breakdown-vN.md`
- `sprint-plan-v1.md`, `sprint-plan-v2.md`, `sprint-plan-vN.md`
- `test-plan-v1.md`, `test-plan-v2.md`, `test-plan-vN.md`

##### `artifacts/`

Final, validated deliverables ready for implementation phase.

**Required artifacts**:
- `task-breakdown.md` - All requirements decomposed to implementable tasks with estimates
- `dependency-map.md` - Task dependencies visualized (critical path identified)
- `sprint-plan.md` - Overall sprint plan with goals and capacity allocation
- `repository-structure.md` - Code repository organization and conventions
- `environment-config.md` - Infrastructure setup (dev, staging, prod)
- `test-plan.md` - Comprehensive testing strategy (unit, integration, E2E)
- `quality-gates.md` - Quality gate definitions and automation

##### `artifacts/sprints/`

Individual sprint plans with detailed task assignments.

- `sprint-0-plan.md` - Infrastructure and scaffolding sprint
- `sprint-1-plan.md` - First implementation sprint
- `sprint-2-plan.md` - Second implementation sprint
- `sprint-N-plan.md` - Subsequent sprints

**Content**: Sprint goal, assigned tasks, team capacity, acceptance criteria

##### `validation/`

Quality checks, approvals, and traceability documents.

- `phase2-completion-checklist.md` - Completed checklist
- `phase2-validation-report.md` - Overall validation with traceability metrics
- `phase2-approval.md` - Final sign-off to proceed to Phase 3
- `task-breakdown-approval.md` - Task decomposition approval
- `sprint-plan-approval.md` - Sprint plan approval

---

### `[actual-code-repository]/`

The actual code repository created during Phase 2 and used in Phase 3+ (implementation). This is typically a separate Git repository.

**Created during**: Phase 2 (repository setup)
**Used during**: Phase 3, 4, 5 (implementation, testing, deployment)

**Structure** (example):
```
project-repository/
├── src/                    # Source code
├── tests/                  # Test files
├── docs/                   # Code documentation
├── .github/                # CI/CD workflows
├── infrastructure/         # IaC files (Terraform, etc.)
└── README.md              # Setup instructions
```

---

## File Naming Conventions

### Context Files (Per Project)

**Format**: `phase[N]-context.md`

**Location**: Root of each phase directory

**Purpose**: Track current state of specific project phase

**Examples**:
- `phase0-context.md`
- `phase1-context.md`
- `phase2-context.md`

---

### Config Files (Organization-Wide)

**Format**: `phase[N]_config.md`

**Location**: `.sdlc/config/`

**Purpose**: Define how phase operates (methodology, standards, thresholds)

**Examples**:
- `phase0_config.md`
- `phase1_config.md`
- `phase2_config.md`

---

### Agent Instructions

**Format**: `[agent-name]-agent_instructions.md` or `[agent-name]_instructions.md`

**Location**: `.sdlc/primitives/agents/phase[N]/`

**Examples**:
- `discovery-facilitator_instructions.md`
- `analyst-agent_instructions.md`
- `planning-agent_instructions.md`

---

### Templates

**Format**: `[artifact-name]_template.md` or `[artifact-name]_template.json`

**Location**: `.sdlc/primitives/templates/phase[N]/`

**Examples**:
- `problem-statement_template.md`
- `spec_template.md`
- `api-spec_template.json`

---

### Workflows

**Format**: `[workflow-name]_prompt.md`

**Location**: `.sdlc/primitives/workflows/phase[N]/`

**Examples**:
- `discovery-workflow_prompt.md`
- `architecture-design_prompt.md`
- `sprint-planning_prompt.md`

---

### Chatmodes

**Format**: `[agent-name]_chatmode.md`

**Location**: `.sdlc/primitives/chatmodes/`

**Examples**:
- `analyst_chatmode.md`
- `architect_chatmode.md`
- `pm_chatmode.md`

---

### Checklists

**Format**: `phase-[N]-completion_checklist.md`

**Location**: `.sdlc/primitives/checklists/`

**Examples**:
- `phase-0-completion_checklist.md`
- `phase-1-completion_checklist.md`
- `phase-2-completion_checklist.md`

---

### Working Files (Versioned)

**Format**: `[artifact-name]-v[N].md`

**Location**: `projects/[project-name]/phase[N]/working/`

**Purpose**: Track evolution and delta changes

**Examples**:
- `problem-statement-v1.md`
- `problem-statement-v2.md`
- `spec-v1.md`
- `architecture-v2.md`

---

### Final Artifacts

**Format**: `[artifact-name].md` or `[artifact-name].final.md`

**Location**: `projects/[project-name]/phase[N]/artifacts/`

**Purpose**: Validated, approved deliverables

**Examples**:
- `problem-statement.final.md`
- `spec.md`
- `architecture.md`
- `task-breakdown.md`

---

### Interview Transcripts

**Format**: `NNN-[stakeholder-role]-interview.md`

**Location**: `projects/[project-name]/phase0/interviews/`

**Examples**:
- `001-ceo-interview.md`
- `002-cto-interview.md`
- `003-support-lead-interview.md`

---

### Architecture Decision Records (ADRs)

**Format**: `NNN-[decision-title].md`

**Location**: `projects/[project-name]/phase1/adrs/`

**Examples**:
- `001-frontend-framework.md`
- `002-database-choice.md`
- `003-deployment-strategy.md`

---

### Sprint Plans

**Format**: `sprint-[N]-plan.md`

**Location**: `projects/[project-name]/phase2/artifacts/sprints/`

**Examples**:
- `sprint-0-plan.md` (infrastructure setup)
- `sprint-1-plan.md`
- `sprint-2-plan.md`

---

## Usage Patterns

### Pattern 1: Conversational (Manual)

**Best for**: Learning the system, simple projects, manual control

**Process**:
1. Create project folder: `projects/my-project/phase0/`
2. Copy `phase0-context.md` template and fill in project details
3. Load agent instructions: `.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md`
4. Load config: `.sdlc/config/phase0_config.md`
5. Load organizational context: `.sdlc/memory/organization_context.md` and `.sdlc/memory/technical-stack_context.md`
6. Conduct interview following workflow: `.sdlc/primitives/workflows/phase0/interview-workflow_prompt.md`
7. Save transcript to: `projects/my-project/phase0/interviews/001-ceo-interview.md`
8. Repeat for all stakeholders
9. Load synthesis workflow: `.sdlc/primitives/workflows/phase0/synthesis-workflow_prompt.md`
10. Create problem statement iterations in `working/`
11. Validate using: `.sdlc/primitives/checklists/phase-0-completion_checklist.md`
12. Move final artifacts to `artifacts/`
13. Update `phase0-context.md` with completion status
14. Proceed to Phase 1

**Advantages**: 
- Full control and transparency
- Learn the methodology deeply
- No tooling required

**Disadvantages**:
- Manual file management
- Repetitive context loading
- Prone to human error

---

### Pattern 2: Semi-Automated (CLI Tools)

**Best for**: Regular use, medium-sized projects, team collaboration

**Process**:

```bash
# Initialize new project
sdlc init "Customer Portal Redesign"
# Creates: projects/customer-portal-redesign/phase0/ with templates

# Start Phase 0
sdlc phase0 start
# Loads: phase0_config.md, organizational context, agent instructions

# Conduct interview
sdlc interview --role="CEO" --framework="five-whys"
# Saves to: interviews/001-ceo-interview.md

# Synthesize problem statement
sdlc synthesize --artifact="problem-statement"
# Creates: working/problem-statement-v1.md

# Iterate problem statement
sdlc refine --artifact="problem-statement" --feedback="stakeholder feedback"
# Creates: working/problem-statement-v2.md

# Validate Phase 0
sdlc validate --phase=0
# Runs: phase-0-completion_checklist.md checks

# Complete Phase 0
sdlc phase0 complete
# Moves artifacts to artifacts/, updates phase0-context.md

# Start Phase 1
sdlc phase1 start
# Loads: phase1_config.md, Phase 0 artifacts, organizational context
```

**Advantages**:
- Faster workflow
- Consistent context loading
- Automated validation
- Less manual file management

**Disadvantages**:
- Requires CLI tool installation
- Less visibility into process
- Learning curve for commands

---

### Pattern 3: Fully Automated (API/SDK)

**Best for**: Large organizations, enterprise-scale, integration with existing tools

**Process** (C# Example):

```csharp
using AgenticSDLC;

// Initialize project
var project = await Project.InitializeAsync(
    name: "Customer Portal Redesign",
    sponsor: "Jane Doe",
    budget: 500000m
);

// Start Phase 0
var phase0 = await project.StartPhase0Async();

// Configure discovery
phase0.Configure(options => {
    options.InterviewMethodology = InterviewMethodology.JobsToBeDonePlusFiveWhys;
    options.FeasibilityFramework = FeasibilityFramework.FourDimension;
    options.MinimumStakeholderInterviews = 5;
});

// Conduct interviews
var interviews = new[] {
    await phase0.ConductInterviewAsync(role: "CEO", duration: 60),
    await phase0.ConductInterviewAsync(role: "CTO", duration: 60),
    await phase0.ConductInterviewAsync(role: "Support Lead", duration: 45)
};

// Synthesize problem statement
var problemStatement = await phase0.SynthesizeProblemStatementAsync(interviews);

// Iterative refinement
while (!await problemStatement.IsValidatedAsync()) {
    var feedback = await problemStatement.GetStakeholderFeedbackAsync();
    problemStatement = await problemStatement.RefineAsync(feedback);
}

// Assess feasibility
var feasibilityReport = await phase0.AssessFeasibilityAsync(problemStatement);

// Validate Phase 0
var validation = await phase0.ValidateAsync();

if (validation.IsComplete && validation.GoDecision == GoDecision.Go) {
    await phase0.CompleteAsync();
    
    // Start Phase 1
    var phase1 = await project.StartPhase1Async();
    // ... continue
}
```

**Advantages**:
- Highly automated
- Integrates with existing tools (Jira, Azure DevOps, etc.)
- Scalable to many projects
- Consistent quality
- Analytics and reporting

**Disadvantages**:
- Requires significant upfront investment
- Complex to build and maintain
- Less flexible
- Requires technical expertise

---

## Integration Between Phases

### Phase 0 → Phase 1 Handoff

**Trigger**: Phase 0 validation complete, all approvals obtained

**Handoff Artifacts** (copied from Phase 0 artifacts/ to Phase 1 context):
- `problem-statement.final.md`
- `feasibility-report.md`
- `success-criteria.md`
- `constraints.md`
- `stakeholder-alignment.md`
- `risk-register.md`

**Phase 1 Entry Actions**:
1. Create `projects/[project-name]/phase1/` directory
2. Copy `phase1-context.md` template
3. Load Phase 0 artifacts
4. Load `phase1_config.md`
5. Load organizational memory
6. Brief Phase 1 team
7. Kickoff Phase 1

---

### Phase 1 → Phase 2 Handoff

**Trigger**: Phase 1 validation complete, all approvals obtained

**Handoff Artifacts** (copied from Phase 1 artifacts/ to Phase 2 context):
- `spec.md`
- `architecture.md`
- `data-model.md`
- `api-spec.json`
- `constitution.md`
- `prd.md`
- All ADRs

**Phase 2 Entry Actions**:
1. Create `projects/[project-name]/phase2/` directory
2. Copy `phase2-context.md` template
3. Load Phase 0 and Phase 1 artifacts
4. Load `phase2_config.md`
5. Load organizational memory
6. Brief Phase 2 team (planning, DevOps, QA)
7. Kickoff Phase 2 workstreams in parallel

---

### Phase 2 → Phase 3 Handoff

**Trigger**: Phase 2 validation complete, infrastructure ready, Sprint 0 planned

**Handoff Artifacts**:
- `task-breakdown.md`
- `sprint-plan.md` + all individual sprint plans
- `test-plan.md`
- `quality-gates.md`
- Repository URL with base structure
- Environment access credentials
- Development setup guide

**Phase 3 Entry Actions**:
1. Development team onboarded
2. All developers can run project locally
3. Sprint 0 kickoff (infrastructure and scaffolding)
4. Daily standups begin
5. Implementation starts

---

## Benefits of This Structure

### 1. Separation of Concerns
- **Primitives** separate from **active work** separate from **completed artifacts**
- **Config** (how to run) separate from **context** (current state)
- **Organization-wide** separate from **project-specific**

### 2. Reusability
- Agent instructions used across all projects
- Templates standardize artifact creation
- Workflows ensure consistent processes
- Memory files accumulate organizational learning

### 3. Traceability
- Version history in `working/` shows evolution
- Context files track current state
- Validation documents prove quality gates met
- Handoff criteria ensure nothing lost between phases

### 4. Scalability
- Multiple concurrent projects supported
- Parallel workstreams within phases
- Team members can work independently
- Clear handoff protocols

### 5. Tool Agnostic
- Works conversationally (human + AI)
- Can add CLI tools incrementally
- Can build full automation progressively
- No vendor lock-in

### 6. Progressive Enhancement
- Start simple (conversational)
- Add templates when helpful
- Add workflows when mature
- Add automation when ROI positive

### 7. Knowledge Accumulation
- Memory files capture lessons learned
- Prior projects inform future estimates
- Decisions documented for reference
- Organizational wisdom grows over time

### 8. Quality Built In
- Templates enforce standards
- Checklists prevent mistakes
- Config files define thresholds
- Validation gates ensure quality

---

## Migration Path

### Phase 1: Start Minimal

```
project-root/
├── .sdlc/
│   ├── primitives/agents/phase0/
│   │   └── discovery-facilitator_instructions.md
│   ├── config/
│   │   └── phase0_config.md
│   └── memory/
│       └── organization_context.md
└── projects/my-project/
    └── phase0/
        ├── phase0-context.md
        ├── interviews/001-ceo-interview.md
        └── artifacts/problem-statement.final.md
```

**Start with**:
- One agent (Discovery Facilitator)
- One config file (Phase 0)
- One memory file (organization context)
- One project

---

### Phase 2: Add Structure

Add templates, workflows, more agents as you learn the system.

```
.sdlc/
├── primitives/
│   ├── agents/phase0/ (all Phase 0 agents)
│   ├── templates/phase0/ (all templates)
│   └── workflows/phase0/ (all workflows)
└── ...
```

---

### Phase 3: Expand to Multiple Phases

Add Phase 1 and Phase 2 as you mature.

```
.sdlc/
├── primitives/
│   ├── agents/
│   │   ├── phase0/
│   │   ├── phase1/
│   │   └── phase2/
│   └── ...
└── projects/my-project/
    ├── phase0/
    ├── phase1/
    └── phase2/
```

---

### Phase 4: Add Automation

Build CLI tools or API/SDK when ROI is clear.

```bash
sdlc init "Project Name"
sdlc phase0 start
sdlc interview --role="CEO"
sdlc validate --phase=0
```

---

## Quick Reference

### Starting a New Project

1. Create project directory: `projects/[project-name]/`
2. Start with Phase 0: `projects/[project-name]/phase0/`
3. Copy context template: `phase0-context.md`
4. Load config: `.sdlc/config/phase0_config.md`
5. Load organizational context: `.sdlc/memory/organization_context.md`
6. Follow discovery workflow: `.sdlc/primitives/workflows/phase0/discovery-workflow_prompt.md`

### Conducting an Interview

1. Load agent: `.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md`
2. Load workflow: `.sdlc/primitives/workflows/phase0/interview-workflow_prompt.md`
3. Use template: `.sdlc/primitives/templates/phase0/interview-transcript_template.md`
4. Save to: `projects/[project-name]/phase0/interviews/NNN-role-interview.md`

### Completing a Phase

1. Move all working files to `artifacts/`
2. Complete validation checklist: `.sdlc/primitives/checklists/phase-[N]-completion_checklist.md`
3. Generate validation report: `validation/phase[N]-validation-report.md`
4. Obtain all required approvals: `validation/phase[N]-approval.md`
5. Update context file: `phase[N]-context.md` (mark as complete)
6. Brief next phase team
7. Begin next phase

### Finding What You Need

**"How do I run Phase [N]?"**
→ `.sdlc/config/phase[N]_config.md`

**"Where is my project now?"**
→ `projects/[project-name]/phase[N]/phase[N]-context.md`

**"How do I do [activity]?"**
→ `.sdlc/primitives/workflows/phase[N]/[activity]-workflow_prompt.md`

**"What should [artifact] look like?"**
→ `.sdlc/primitives/templates/phase[N]/[artifact]_template.md`

**"How do I use [agent]?"**
→ `.sdlc/primitives/agents/phase[N]/[agent]_instructions.md`

---

## Next Steps

### For New Users

1. Read: `.sdlc/reference/getting-started.md`
2. Review: `.sdlc/reference/sdlc-workflow.html`
3. Start simple: Use conversational pattern (Pattern 1)
4. Follow along: Work through one complete Phase 0

### For Teams

1. Customize configs: Update `.sdlc/config/` files for your organization
2. Populate memory: Fill in `.sdlc/memory/` files with your context
3. Train team: Ensure everyone understands primitives
4. Start project: Follow Phase 0 → Phase 1 → Phase 2 progression

### For Organizations

1. Standardize: Create organization-wide config files
2. Build tooling: Implement CLI or API (Pattern 2 or 3)
3. Integrate: Connect with existing tools (Jira, Azure DevOps, etc.)
4. Measure: Track metrics and continuously improve
5. Scale: Roll out across multiple teams and projects

---

*This directory structure provides a comprehensive, scalable foundation for agentic SDLC from discovery through deployment. Start simple and enhance progressively as your needs grow.*
