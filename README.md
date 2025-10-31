# Agentic SDLC Framework

**A Tool-Agnostic, AI-Powered Software Development Lifecycle System**

Version 2.0 | Last Updated: 2025-10-31

---

## Table of Contents

1. [What Is This?](#what-is-this)
2. [Why Use This Framework?](#why-use-this-framework)
3. [Core Philosophy](#core-philosophy)
4. [System Architecture](#system-architecture)
5. [Key Concepts](#key-concepts)
6. [Directory Structure](#directory-structure)
7. [Essential Files Explained](#essential-files-explained)
8. [Usage Patterns](#usage-patterns)
9. [Getting Started](#getting-started)
10. [Phase-by-Phase Guide](#phase-by-phase-guide)
11. [Real-World Example](#real-world-example)
12. [Benefits](#benefits)
13. [FAQ](#faq)
14. [Contributing](#contributing)
15. [License](#license)

---

## What Is This?

The **Agentic SDLC Framework** is a comprehensive, structured approach to software development that leverages AI agents to amplify human decision-making throughout the entire software development lifecycle. It provides:

- **Structured processes** for discovery, specification, architecture, planning, and implementation
- **AI agent personas** specialized for different SDLC activities (discovery, analysis, architecture, planning)
- **Reusable templates** for all major deliverables (specs, architectures, plans)
- **Quality gates** and validation checklists at each phase
- **Organizational memory** that accumulates wisdom across projects
- **Flexible automation** - works conversationally, with CLI tools, or fully automated

### What Makes It "Agentic"?

This framework uses **agentic AI** - specialized AI personas with:
- **Clear roles and responsibilities** (Discovery Facilitator, Technical Architect, Planning Agent, etc.)
- **Decision-making frameworks** (when to escalate, what quality standards to meet)
- **Contextual awareness** (what information to load for each activity)
- **Collaborative workflows** (how agents work together and hand off to each other)

The AI agents **generate and propose**, while humans **validate and decide**. This keeps domain experts in control while dramatically accelerating the SDLC.

---

## Why Use This Framework?

### Problems This Solves

❌ **Traditional SDLC Issues**:
- Requirements are vague and incomplete
- Architecture decisions are poorly documented
- Planning estimates are wildly inaccurate
- Context is lost between phases
- Knowledge doesn't accumulate across projects
- Teams reinvent processes each time

✅ **What This Framework Provides**:
- **Structured discovery** ensures problems are validated before solutions
- **Quality gates** prevent bad requirements from becoming bad code
- **Traceability** maintains coherence from problem → requirement → task → code
- **Organizational memory** captures lessons learned and improves estimates
- **Consistent quality** through templates and validation checklists
- **Progressive enhancement** - start simple, add automation as needed

### Who Is This For?

- **Solo Developers**: Structure your projects and avoid common pitfalls
- **Small Teams**: Coordinate work and maintain quality without heavy process
- **Growing Startups**: Scale development practices as team grows
- **Enterprises**: Standardize SDLC across multiple teams and projects
- **Consultants**: Deliver consistent, high-quality projects for clients

---

## Core Philosophy

### 1. Tool-Agnostic Foundation

The framework works **conversationally first**:
- Core workflows use human-AI dialogue
- Templates are markdown-based
- Validation can be human-driven
- No vendor lock-in

Code and automation are **optional enhancements**, not requirements.

### 2. Specification Before Implementation

Every phase produces **validated artifacts** before moving forward:
- Phase 0: Validate the **problem** before designing solutions
- Phase 1: Validate the **design** before planning implementation
- Phase 2: Validate the **plan** before writing code

**Quality gates** between phases prevent compounding mistakes.

### 3. Human Amplification, Not Replacement

AI agents **generate**, humans **decide**:
- Agents propose requirements → Humans approve
- Agents design architecture → Humans review
- Agents create plans → Humans validate

Domain experts remain in control. AI accelerates, humans ensure correctness.

### 4. Context Engineering

Prevent **context collapse** through intentional design:
- **Session splitting**: One focus per conversation
- **Explicit context loading**: Load only what's needed when needed
- **Delta updates**: Incremental refinement, not full rewrites
- **Traceability links**: Maintain coherence across sessions

### 5. Knowledge Accumulation

The framework gets **smarter over time**:
- **Memory files** capture organizational context
- **Lessons learned** inform future estimates
- **Prior projects** provide reference patterns
- **Decisions** are documented for future reference

Each project makes the next one better.

---

## System Architecture

### High-Level Structure

```
┌─────────────────────────────────────────────────────────────┐
│                      .sdlc/ (System Root)                   │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Primitives  │  │    Memory    │  │    Config    │     │
│  │ (Reusable)   │  │ (Persistent) │  │  (Settings)  │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
                           ↓ Used by ↓
┌─────────────────────────────────────────────────────────────┐
│                  projects/ (Active Work)                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   Phase 0    │→ │   Phase 1    │→ │   Phase 2    │→    │
│  │  Discovery   │  │   Spec &     │  │  Planning &  │     │
│  │              │  │   Design     │  │    Setup     │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
```

### The Three Pillars

#### 1. Primitives (`.sdlc/primitives/`)
**Reusable building blocks** used across all projects:
- **Agents**: Specialized AI personas (Discovery Facilitator, Architect, etc.)
- **Templates**: Artifact structures (problem statements, specs, plans)
- **Workflows**: Multi-step processes (discovery, architecture design)
- **Chatmodes**: Focused interaction patterns
- **Checklists**: Quality gates and completion criteria

#### 2. Memory (`.sdlc/memory/`)
**Organizational knowledge** that persists across projects:
- **Organization Context**: Company info, culture, structure
- **Technical Stack**: Current technologies, standards, constraints
- **Prior Projects**: Historical data, outcomes, patterns
- **Lessons Learned**: Accumulated wisdom from retrospectives
- **Decisions**: Key organizational and technical decisions

#### 3. Config (`.sdlc/config/`)
**Phase configurations** defining HOW each phase operates:
- **phase0_config.md**: Discovery methodologies, interview frameworks
- **phase1_config.md**: Requirements approaches, architecture standards
- **phase2_config.md**: Task sizing, sprint planning, infrastructure

### The SDLC Phases

#### Phase 0: Discovery & Ideation
**Validate the problem before designing solutions**

**Key Activities**:
- Stakeholder interviews
- Problem statement definition
- Feasibility assessment
- Risk identification
- Success criteria definition

**Deliverables**:
- Problem statement (validated)
- Feasibility report
- Risk register
- Success criteria
- Stakeholder alignment

---

#### Phase 1: Specification & Design
**Define WHAT to build and HOW it will be architected**

**Key Activities**:
- Requirements elicitation
- Technical specification
- System architecture design
- Technology selection
- Project constitution creation

**Deliverables**:
- Technical specification
- System architecture (C4 model)
- Data model
- API specification
- Constitution
- Product Requirements Document (PRD)

---

#### Phase 2: Planning & Setup
**Prepare infrastructure and create implementation plan**

**Key Activities**:
- Task decomposition
- Sprint planning
- Repository setup
- Infrastructure provisioning
- Quality framework establishment

**Deliverables**:
- Task breakdown
- Sprint plan
- Repository structure
- Environment configuration
- Test plan
- Quality gates

---

## Key Concepts

### Config Files vs Context Files

These two file types work together but serve different purposes:

#### Config Files (`.sdlc/config/`)

**Purpose**: Define **HOW** phases operate

**Characteristics**:
- Organization-wide settings
- Long-lived (months to years)
- Infrequent updates (when methodology changes)
- Shared across all projects

**Files**:
- `phase0_config.md` - Discovery methodologies, quality standards
- `phase1_config.md` - Requirements approaches, architecture frameworks
- `phase2_config.md` - Task sizing, sprint planning, infrastructure standards

**Example Content**:
```markdown
## Interview Methodology
Current Mode: jobs-to-be-done + five-whys

## Feasibility Scoring
Minimum Threshold: 3.0/5.0 average across dimensions

## Quality Standards
Problem Statement Score: 80/100 minimum
```

---

#### Context Files (per project)

**Purpose**: Track **WHERE** the project currently is

**Characteristics**:
- Project-specific
- Short-lived (duration of project)
- Frequent updates (after each milestone)
- Unique per project

**Files**:
- `phase0-context.md` - Current discovery progress
- `phase1-context.md` - Current specification status
- `phase2-context.md` - Current planning status

**Example Content**:
```markdown
## Current Status
Phase 0 Stage: Problem Statement Refinement
Interviews Complete: 5/7
Problem Statement Version: v3
Feasibility Score: 3.8/5.0

## Next Steps
- Complete remaining 2 interviews
- Finalize problem statement v4
- Run validation checklist
```

**Think of it this way**:
- **Config** = The rules of the game (chess rules)
- **Context** = The current board state (your current game position)

---

### Agentic Primitives

Based on GitHub's agentic primitives framework:

#### 1. Instructions Files
Define specialized AI agent personas:
- **Role and responsibilities**: What this agent does
- **Decision-making logic**: When to act autonomously vs escalate
- **Quality standards**: What "good" looks like
- **Workflows**: Step-by-step processes
- **Examples**: Reference patterns

**Example**: `discovery-facilitator_instructions.md`

---

#### 2. Chat Modes
Focused interaction patterns for specific contexts:
- **Purpose**: When to use this mode
- **Prerequisites**: What context to load
- **Interaction patterns**: How to engage effectively
- **Quality checks**: What to verify before ending
- **Expected outputs**: What you should have at the end

**Example**: `analyst_chatmode.md`

---

#### 3. Workflows
Multi-step orchestration prompts:
- **Entry criteria**: What's needed to start
- **Process steps**: Detailed step-by-step instructions
- **Decision points**: Where human input is required
- **Validation gates**: Quality checks along the way
- **Exit criteria**: When the workflow is complete

**Example**: `architecture-design_prompt.md`

---

#### 4. Memory Files
Persistent context loaded across sessions:
- **Organization context**: Company info, culture
- **Technical stack**: Current technologies
- **Prior projects**: Historical outcomes
- **Lessons learned**: Accumulated wisdom
- **Decisions**: Key choices made

**Example**: `lessons-learned_memory.md`

---

#### 5. Templates
Reusable artifact structures:
- **Required sections**: What must be included
- **Guidance text**: How to fill each section
- **Examples**: Reference content
- **Validation criteria**: How to check quality

**Example**: `spec_template.md`

---

### Session Management

Projects are broken into **focused sessions** to prevent context collapse:

#### Session Splitting Strategies

**When to Split**:
- Switching between major artifacts (spec → architecture)
- Moving from creation to validation mode
- Phase transitions (Phase 0 → Phase 1)
- Context window exceeds 75% usage

**How to Split**:
1. Complete current activity
2. Save all artifacts
3. Update context file with current state
4. Start new session
5. Load only relevant context for next activity

**Example**: 
- Session 1: Conduct 3 stakeholder interviews
- Session 2: Synthesize problem statement from interviews
- Session 3: Conduct 3 more interviews
- Session 4: Refine problem statement with new insights

---

### Quality Gates

Each phase has **validation checkpoints** before proceeding:

#### Phase 0 Quality Gate
- ✅ All key stakeholders interviewed
- ✅ Problem statement score ≥80/100
- ✅ Feasibility score ≥3.0/5.0
- ✅ All critical risks have mitigation plans
- ✅ Success criteria are SMART
- ✅ Stakeholder alignment achieved

#### Phase 1 Quality Gate
- ✅ All artifacts score ≥80/100
- ✅ INVEST score ≥12/18 for all user stories
- ✅ Traceability ≥90% (Phase 0 → Phase 1)
- ✅ All NFRs addressed in architecture
- ✅ Zero critical issues
- ✅ All approvals obtained

#### Phase 2 Quality Gate
- ✅ All requirements mapped to tasks (100%)
- ✅ All tasks assigned to sprints
- ✅ Dependencies resolved
- ✅ Infrastructure provisioned and validated
- ✅ Quality gates defined
- ✅ Sprint 0 fully planned

---

## Directory Structure

### Complete Tree Overview

```
project-root/
├── .sdlc/                              # System root (shared across projects)
│   ├── primitives/                     # Reusable building blocks
│   │   ├── agents/                     # Agent instruction files
│   │   │   ├── phase0/                 # Discovery agents
│   │   │   ├── phase1/                 # Specification agents
│   │   │   └── phase2/                 # Planning agents
│   │   ├── templates/                  # Artifact templates
│   │   │   ├── phase0/
│   │   │   ├── phase1/
│   │   │   └── phase2/
│   │   ├── workflows/                  # Multi-step process prompts
│   │   │   ├── phase0/
│   │   │   ├── phase1/
│   │   │   └── phase2/
│   │   ├── chatmodes/                  # Focused interaction patterns
│   │   └── checklists/                 # Quality gates
│   ├── memory/                         # Organizational knowledge
│   │   ├── organization_context.md
│   │   ├── technical-stack_context.md
│   │   ├── prior-projects_memory.md
│   │   ├── lessons-learned_memory.md
│   │   └── decisions_memory.md
│   ├── config/                         # Phase configurations
│   │   ├── phase0_config.md
│   │   ├── phase1_config.md
│   │   └── phase2_config.md
│   └── reference/                      # Documentation
│       ├── README.md                   # This file
│       ├── directory-structure.md      # Detailed structure docs
│       └── sdlc-workflow.html          # Visual workflow
│
└── projects/                           # All project work
    └── [project-name]/                 # Individual project
        ├── phase0/                     # Discovery artifacts
        │   ├── phase0-context.md       # Current state tracker
        │   ├── interviews/
        │   ├── working/
        │   ├── artifacts/
        │   └── validation/
        ├── phase1/                     # Specification artifacts
        │   ├── phase1-context.md
        │   ├── working/
        │   ├── artifacts/
        │   ├── adrs/
        │   └── validation/
        └── phase2/                     # Planning artifacts
            ├── phase2-context.md
            ├── working/
            ├── artifacts/
            └── validation/
```

### Key Directories Explained

#### `.sdlc/primitives/agents/`
Contains all agent instruction files organized by phase. Each agent has a specialized role with clear responsibilities, decision-making logic, and step-by-step workflows.

#### `.sdlc/primitives/templates/`
Provides structure for all deliverables. Templates include guidance text, examples, and validation criteria to ensure consistent, high-quality artifacts.

#### `.sdlc/memory/`
Persistent organizational knowledge that gets smarter over time. Memory files are loaded across all projects to provide relevant context and lessons learned.

#### `projects/[project-name]/phase[N]/`
Per-project work organized by phase. Each phase has:
- **Context file**: Tracks current state
- **Interviews/**: Raw inputs (Phase 0 only)
- **Working/**: Iterative drafts with version history
- **Artifacts/**: Final, validated deliverables
- **Validation/**: Quality checks and approvals

---

## Essential Files Explained

### Agent Instructions

**Location**: `.sdlc/primitives/agents/phase[N]/[agent-name]_instructions.md`

**Purpose**: Define specialized AI personas with clear roles, responsibilities, and workflows.

**Key Agents**:

| Phase | Agent | Role |
|-------|-------|------|
| 0 | Discovery Facilitator | Conducts interviews, synthesizes insights |
| 0 | Feasibility Analyzer | Assesses technical/business/resource feasibility |
| 1 | Analyst Agent | Creates specifications and user stories |
| 1 | Architect Agent | Designs system architecture |
| 1 | PM Agent | Creates product requirements and prioritizes |
| 1 | Constitution Agent | Defines project values and constraints |
| 1 | Validator Agent | Validates artifacts against quality standards |
| 2 | Planning Agent | Decomposes tasks and plans sprints |
| 2 | DevOps Scaffolder | Sets up repository and infrastructure |
| 2 | Quality Architect | Designs testing strategy |

**Structure**:
```markdown
# Agent Name

## Role and Responsibilities
[What this agent does]

## Scope and Boundaries
[What's in scope, what's out of scope]

## Decision-Making Logic
[When to act autonomously vs escalate]

## Workflows
[Step-by-step processes]

## Quality Standards
[What "good" looks like]

## Context Loading
[What information to load]

## Examples
[Reference patterns]
```

---

### Config Files

**Location**: `.sdlc/config/phase[N]_config.md`

**Purpose**: Define how each phase operates - methodologies, standards, thresholds.

**Key Sections**:
- **Phase Mode**: Approach to use (discovery-driven, parallel-tracks, etc.)
- **Agent Settings**: Preferences for each agent (methodologies, frameworks)
- **Workflow Orchestration**: How activities sequence and coordinate
- **Quality Standards**: Scoring systems and minimum thresholds
- **Handoff Criteria**: Requirements to proceed to next phase

**When to Modify**:
- Team expertise changes
- Project complexity varies
- Organizational standards evolve
- Historical data suggests improvements

---

### Context Files

**Location**: `projects/[project-name]/phase[N]/phase[N]-context.md`

**Purpose**: Track the current state of a specific project phase.

**Key Sections**:
- **Current Status**: What stage we're in, what's being worked on
- **Artifact Status**: Completion %, quality scores, versions
- **Progress Tracking**: Milestones, completion estimates
- **Decisions Made**: Key choices and rationale
- **Issues and Blockers**: What's preventing progress
- **Context Loading Guide**: What agents should load for activities

**Update Frequency**:
- After each major milestone
- After each artifact iteration
- When blockers arise or resolve
- When decisions are made
- Before phase transitions

---

### Templates

**Location**: `.sdlc/primitives/templates/phase[N]/[artifact]_template.md`

**Purpose**: Provide consistent structure for all deliverables.

**Key Templates by Phase**:

**Phase 0**:
- `problem-statement_template.md`
- `interview-transcript_template.md`
- `feasibility-report_template.md`
- `risk-register_template.md`

**Phase 1**:
- `spec_template.md`
- `architecture_template.md`
- `prd_template.md`
- `constitution_template.md`

**Phase 2**:
- `task-breakdown_template.md`
- `sprint-plan_template.md`
- `test-plan_template.md`

**Structure**:
- Required sections with guidance text
- Optional sections marked clearly
- Examples where helpful
- Validation criteria at end

---

### Workflows

**Location**: `.sdlc/primitives/workflows/phase[N]/[workflow-name]_prompt.md`

**Purpose**: Multi-step orchestration prompts for complex activities.

**Key Workflows**:
- `discovery-workflow_prompt.md` - End-to-end Phase 0 process
- `requirements-discovery_prompt.md` - Creating specifications
- `architecture-design_prompt.md` - System architecture design
- `task-decomposition_prompt.md` - Breaking requirements into tasks
- `sprint-planning_prompt.md` - Sprint planning and capacity management

**Structure**:
- Entry criteria (what's needed to start)
- Process steps (detailed instructions)
- Decision points (where human input required)
- Validation gates (quality checks)
- Exit criteria (when complete)

---

### Checklists

**Location**: `.sdlc/primitives/checklists/phase-[N]-completion_checklist.md`

**Purpose**: Ensure nothing is missed before proceeding to next phase.

**Coverage**:
- Artifact completeness
- Quality scoring results
- Traceability validation
- Stakeholder approvals
- Technical readiness
- Team readiness

---

## Usage Patterns

The framework supports three usage patterns, from fully manual to fully automated. Choose based on your team size, technical capability, and automation needs.

---

## Pattern 1: Conversational (Fully Manual)

**Best For**: 
- Learning the system
- Solo developers or very small teams
- Simple projects
- Maximum control and transparency

**Requirements**:
- Access to AI assistant (Claude, ChatGPT, etc.)
- Ability to manage files manually
- Text editor for markdown files

**Advantages**:
- ✅ No tooling required
- ✅ Full visibility into every step
- ✅ Learn methodology deeply
- ✅ Easy to customize on the fly
- ✅ No code to maintain

**Disadvantages**:
- ❌ Manual file management
- ❌ Repetitive context loading
- ❌ Prone to human error
- ❌ Time-consuming at scale

---

### How to Use Pattern 1

#### Step-by-Step Example: Phase 0 Discovery

**1. Set Up Project Structure**

```bash
# Create project directory
mkdir -p projects/customer-portal-redesign/phase0/{interviews,working,artifacts,validation}

# Copy context template
cp .sdlc/primitives/templates/phase0-context_template.md \
   projects/customer-portal-redesign/phase0/phase0-context.md
```

**2. Start AI Conversation**

Open your AI assistant and load relevant files:

```
Hi! I'm starting Phase 0 discovery for a new project.
Please read the following files to understand your role and context:

1. Agent Instructions:
[paste .sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md]

2. Configuration:
[paste .sdlc/config/phase0_config.md]

3. Organization Context:
[paste .sdlc/memory/organization_context.md]

4. Technical Stack:
[paste .sdlc/memory/technical-stack_context.md]

5. Discovery Workflow:
[paste .sdlc/primitives/workflows/phase0/discovery-workflow_prompt.md]

We're ready to begin. Let's start with planning our stakeholder interviews.
```

**3. Conduct Interview**

```
I'm about to interview our CEO about this project. 
Please guide me through the interview using the Jobs-to-be-Done 
and Five Whys methodology.

[AI guides interview with structured questions]

[You conduct the interview and take notes]
```

**4. Document Interview**

```
Here are my notes from the CEO interview:
[paste your notes]

Please help me structure these into a formal interview transcript
using the interview template.

[AI generates structured transcript]

[You save to: projects/customer-portal-redesign/phase0/interviews/001-ceo-interview.md]
```

**5. Synthesize Problem Statement**

After 3-5 interviews:

```
I've completed interviews with CEO, CTO, and 3 end users. 
Here are all the transcripts:
[paste interview transcripts]

Please synthesize these insights into a problem statement draft
using the Five Whys to identify the root cause.

[AI generates problem-statement-v1.md]

[You save to: projects/customer-portal-redesign/phase0/working/problem-statement-v1.md]
```

**6. Iterate Problem Statement**

```
I received feedback from stakeholders on v1:
[paste feedback]

Please refine the problem statement to address this feedback.

[AI generates problem-statement-v2.md]

[You save to: projects/customer-portal-redesign/phase0/working/problem-statement-v2.md]
```

**7. Assess Feasibility**

```
Please assess the feasibility of solving this problem using the 
four-dimension framework (technical, business, resource, timeline).

Problem Statement: [paste final problem statement]

[AI generates feasibility-report.md]

[You save to: projects/customer-portal-redesign/phase0/artifacts/feasibility-report.md]
```

**8. Validate Phase 0**

```
Please validate Phase 0 completion using the checklist:
[paste .sdlc/primitives/checklists/phase-0-completion_checklist.md]

Here are all our artifacts:
- Problem Statement: [paste]
- Feasibility Report: [paste]
- Risk Register: [paste]
- Success Criteria: [paste]

[AI validates and generates report]

[You save validation report and get stakeholder approvals]
```

**9. Update Context File**

```bash
# Update phase0-context.md with:
# - All interviews completed
# - Final problem statement version
# - Feasibility score
# - Validation results
# - Status: Complete
```

**10. Proceed to Phase 1**

---

### Pattern 1 Best Practices

**Context Management**:
- Start new conversation when switching major activities
- Keep conversation focused on single artifact
- Save all work incrementally to files
- Update context file regularly

**File Organization**:
- Use consistent naming conventions
- Keep version history in working/ directory
- Move only validated artifacts to artifacts/
- Document decisions as you go

**Quality Assurance**:
- Use checklists religiously
- Get peer reviews on major artifacts
- Validate traceability manually
- Don't skip quality gates

---

## Pattern 2: Semi-Automated (CLI Tools)

**Best For**:
- Small to medium teams
- Regular project cadence
- Teams with some technical capability
- Balance of control and efficiency

**Requirements**:
- Command-line interface (CLI) tool
- Basic terminal/command prompt skills
- Git for version control

**Advantages**:
- ✅ Faster than manual
- ✅ Consistent context loading
- ✅ Automated validation
- ✅ Built-in best practices
- ✅ Less human error

**Disadvantages**:
- ❌ Requires CLI tool installation and setup
- ❌ Less visibility into process
- ❌ Learning curve for commands
- ❌ Some code to maintain

---

### How to Use Pattern 2

#### CLI Tool Concept

A command-line tool wraps the conversational pattern with automation:

```bash
# Install CLI tool
npm install -g @agentic-sdlc/cli
# or
dotnet tool install -g AgenticSDLC.CLI

# Initialize configuration
sdlc setup
```

#### Step-by-Step Example: Phase 0 Discovery

**1. Initialize New Project**

```bash
sdlc init "Customer Portal Redesign" \
  --sponsor="Jane Doe" \
  --budget=500000

# Creates:
# - projects/customer-portal-redesign/
# - phase0-context.md from template
# - Loads default config
```

**2. Start Phase 0**

```bash
sdlc phase0 start

# Automatically:
# - Loads phase0_config.md
# - Loads organization_context.md
# - Loads technical-stack_context.md
# - Loads discovery-facilitator_instructions.md
# - Creates AI session with proper context
```

**3. Conduct Interview**

```bash
sdlc interview \
  --role="CEO" \
  --duration=60 \
  --framework="five-whys"

# Interactive session:
# - AI guides you through structured interview
# - You answer questions
# - Transcript automatically saved to interviews/001-ceo-interview.md
# - phase0-context.md updated with interview count
```

**4. Synthesize Problem Statement**

```bash
sdlc synthesize \
  --artifact="problem-statement" \
  --version=1

# Automatically:
# - Loads all interview transcripts
# - Applies Five Whys analysis
# - Generates problem-statement-v1.md in working/
# - Updates phase0-context.md
```

**5. Iterate Problem Statement**

```bash
sdlc refine \
  --artifact="problem-statement" \
  --feedback="stakeholder-feedback.txt"

# Automatically:
# - Loads problem-statement-v1.md
# - Incorporates feedback
# - Generates problem-statement-v2.md
# - Updates context
```

**6. Assess Feasibility**

```bash
sdlc assess-feasibility

# Automatically:
# - Loads final problem statement
# - Applies four-dimension framework
# - Generates feasibility-report.md
# - Generates risk-register.md
# - Calculates overall score
```

**7. Create Success Criteria**

```bash
sdlc create \
  --artifact="success-criteria"

# Interactive:
# - AI proposes metrics
# - You validate/adjust
# - Saves to artifacts/success-criteria.md
```

**8. Validate Phase 0**

```bash
sdlc validate --phase=0

# Automatically:
# - Runs phase-0-completion_checklist.md
# - Validates all artifacts
# - Calculates quality scores
# - Checks traceability
# - Generates validation report
# - Lists any blockers
```

**9. Get Approvals**

```bash
sdlc approvals \
  --phase=0 \
  --stakeholders="ceo,cto,product-owner"

# Interactive:
# - Generates approval forms
# - Tracks approval status
# - Updates validation/phase0-approval.md
```

**10. Complete Phase 0**

```bash
sdlc phase0 complete

# Automatically:
# - Moves all final artifacts to artifacts/
# - Generates phase0-validation-report.md
# - Updates phase0-context.md status to "Complete"
# - Creates Phase 1 directory structure
# - Generates transition brief
```

**11. Start Phase 1**

```bash
sdlc phase1 start

# Automatically:
# - Loads all Phase 0 artifacts
# - Loads phase1_config.md
# - Loads phase1-context.md template
# - Briefs Phase 1 team
# - Creates AI session for requirements
```

---

### Pattern 2 CLI Reference

#### Project Management

```bash
# Initialize new project
sdlc init <project-name> [options]

# List all projects
sdlc list

# Show project status
sdlc status [project-name]

# Archive completed project
sdlc archive <project-name>
```

#### Phase Operations

```bash
# Start phase
sdlc phase<N> start

# Complete phase
sdlc phase<N> complete

# Validate phase
sdlc validate --phase=<N>

# Show phase status
sdlc phase<N> status
```

#### Artifact Creation

```bash
# Create artifact from template
sdlc create --artifact=<name> [--version=N]

# Refine existing artifact
sdlc refine --artifact=<name> [--feedback=<file>]

# Validate artifact
sdlc validate --artifact=<name>

# View artifact
sdlc view --artifact=<name> [--version=N]
```

#### Discovery Operations (Phase 0)

```bash
# Conduct stakeholder interview
sdlc interview --role=<role> [options]

# Synthesize insights
sdlc synthesize --artifact=<name>

# Assess feasibility
sdlc assess-feasibility

# Identify risks
sdlc identify-risks
```

#### Specification Operations (Phase 1)

```bash
# Create specification
sdlc spec create

# Add user story
sdlc story add [options]

# Design architecture
sdlc arch design

# Create ADR
sdlc adr create --title=<title>

# Create constitution
sdlc constitution create
```

#### Planning Operations (Phase 2)

```bash
# Decompose tasks
sdlc tasks decompose

# Plan sprints
sdlc sprints plan [--duration=<weeks>] [--team-size=<N>]

# Set up repository
sdlc repo setup

# Provision infrastructure
sdlc infra provision [--env=<dev|staging|prod>]

# Create test plan
sdlc test plan
```

#### Configuration

```bash
# View current config
sdlc config show [--phase=<N>]

# Edit config
sdlc config edit [--phase=<N>]

# Reset to defaults
sdlc config reset [--phase=<N>]
```

---

### Pattern 2 Best Practices

**Configuration**:
- Customize configs before first project
- Review configs after each project (lessons learned)
- Keep configs under version control
- Document any deviations from defaults

**Team Collaboration**:
- Use shared git repository for projects
- Commit after each major milestone
- Use feature branches for parallel work
- Tag releases at phase completions

**Automation**:
- Add custom commands for common tasks
- Create project templates for similar work
- Integrate with existing tools (Jira, Slack)
- Build reporting dashboards

---

## Pattern 3: Fully Automated (API/SDK)

**Best For**:
- Large teams and enterprises
- High project volume
- Organizations with technical capability
- Integration with existing tools

**Requirements**:
- Custom application using API/SDK
- Development resources
- Infrastructure for hosting
- Integration architecture

**Advantages**:
- ✅ Highly automated workflow
- ✅ Integrates with existing tools
- ✅ Scalable to many projects
- ✅ Consistent quality
- ✅ Analytics and reporting
- ✅ Custom business logic

**Disadvantages**:
- ❌ Significant upfront investment
- ❌ Complex to build and maintain
- ❌ Less flexible
- ❌ Requires dedicated team

---

### How to Use Pattern 3

#### SDK Architecture (C# Example)

```csharp
using AgenticSDLC;
using AgenticSDLC.Phase0;
using AgenticSDLC.Phase1;
using AgenticSDLC.Phase2;

// Initialize SDK
var sdlc = new AgenticSDLCClient(config: new SDLCConfig
{
    OrganizationId = "acme-corp",
    ConfigPath = ".sdlc/config",
    MemoryPath = ".sdlc/memory",
    ProjectsPath = "projects"
});
```

#### Complete Example: Automated Project Flow

```csharp
public class Program
{
    public static async Task Main(string[] args)
    {
        // 1. Initialize Project
        var project = await InitializeProjectAsync();
        
        // 2. Run Phase 0 (Discovery)
        var phase0Result = await RunPhase0Async(project);
        
        if (phase0Result.GoDecision == GoDecision.Go)
        {
            // 3. Run Phase 1 (Specification)
            var phase1Result = await RunPhase1Async(project, phase0Result);
            
            if (phase1Result.ValidationStatus == ValidationStatus.Passed)
            {
                // 4. Run Phase 2 (Planning)
                var phase2Result = await RunPhase2Async(project, phase1Result);
                
                if (phase2Result.ReadyForPhase3)
                {
                    // 5. Kickoff Phase 3 (Implementation)
                    await KickoffPhase3Async(project, phase2Result);
                }
            }
        }
    }
}
```

#### Phase 0 Implementation

```csharp
public static async Task<Phase0Result> RunPhase0Async(Project project)
{
    // Initialize Phase 0
    var phase0 = await project.StartPhase0Async(options =>
    {
        options.InterviewMethodology = InterviewMethodology.JobsToBeDonePlusFiveWhys;
        options.FeasibilityFramework = FeasibilityFramework.FourDimension;
        options.MinimumStakeholderInterviews = 5;
        options.AutoSynthesis = true;
    });
    
    // Load organizational context
    await phase0.LoadContextAsync(new[] {
        "organization_context.md",
        "technical-stack_context.md",
        "prior-projects_memory.md",
        "lessons-learned_memory.md"
    });
    
    // Define stakeholders
    var stakeholders = new[] {
        new Stakeholder { Role = "CEO", Name = "Jane Doe", Priority = Priority.Critical },
        new Stakeholder { Role = "CTO", Name = "John Smith", Priority = Priority.Critical },
        new Stakeholder { Role = "Product Owner", Name = "Sarah Johnson", Priority = Priority.High },
        new Stakeholder { Role = "Lead Developer", Name = "Mike Chen", Priority = Priority.Medium },
        new Stakeholder { Role = "Support Lead", Name = "Emily Brown", Priority = Priority.Medium }
    };
    
    // Schedule and conduct interviews
    var interviews = new List<Interview>();
    foreach (var stakeholder in stakeholders)
    {
        // Schedule interview
        var appointment = await phase0.ScheduleInterviewAsync(stakeholder, duration: 60);
        
        // Send calendar invite with interview guide
        await SendInterviewInviteAsync(stakeholder, appointment);
        
        // Conduct interview (interactive or recorded)
        var interview = await phase0.ConductInterviewAsync(
            stakeholder: stakeholder,
            framework: InterviewFramework.JobsToBeDonePlusFiveWhys,
            duration: 60
        );
        
        interviews.Add(interview);
        
        // Auto-save transcript
        await interview.SaveTranscriptAsync($"interviews/{interviews.Count:000}-{stakeholder.Role.ToLower()}-interview.md");
        
        // Update context
        await phase0.UpdateContextAsync(context =>
        {
            context.InterviewsCompleted++;
            context.LastUpdate = DateTime.Now;
        });
    }
    
    // Synthesize problem statement
    var problemStatement = await phase0.SynthesizeProblemStatementAsync(
        interviews: interviews,
        applyFiveWhys: true
    );
    
    // Save version 1
    await problemStatement.SaveAsync("working/problem-statement-v1.md");
    
    // Iterative refinement loop
    int version = 1;
    while (!await problemStatement.IsValidatedAsync())
    {
        // Get stakeholder feedback
        var feedback = await GetStakeholderFeedbackAsync(problemStatement, stakeholders);
        
        // Refine problem statement
        problemStatement = await problemStatement.RefineAsync(feedback);
        
        version++;
        await problemStatement.SaveAsync($"working/problem-statement-v{version}.md");
        
        // Prevent infinite loops
        if (version >= 5) break;
    }
    
    // Finalize problem statement
    var finalProblemStatement = await problemStatement.FinalizeAsync();
    await finalProblemStatement.SaveAsync("artifacts/problem-statement.final.md");
    
    // Assess feasibility
    var feasibilityReport = await phase0.AssessFeasibilityAsync(
        problemStatement: finalProblemStatement,
        framework: FeasibilityFramework.FourDimension
    );
    
    await feasibilityReport.SaveAsync("artifacts/feasibility-report.md");
    
    // Identify and assess risks
    var riskRegister = await phase0.IdentifyRisksAsync(
        problemStatement: finalProblemStatement,
        feasibilityReport: feasibilityReport
    );
    
    await riskRegister.SaveAsync("artifacts/risk-register.md");
    
    // Define success criteria
    var successCriteria = await phase0.DefineSuccessCriteriaAsync(
        problemStatement: finalProblemStatement,
        stakeholders: stakeholders,
        ensureSMART: true
    );
    
    await successCriteria.SaveAsync("artifacts/success-criteria.md");
    
    // Create stakeholder alignment document
    var alignment = await phase0.AssessStakeholderAlignmentAsync(
        problemStatement: finalProblemStatement,
        stakeholders: stakeholders,
        interviews: interviews
    );
    
    await alignment.SaveAsync("artifacts/stakeholder-alignment.md");
    
    // Validate Phase 0
    var validation = await phase0.ValidateAsync(new ValidationOptions
    {
        UseChecklist = true,
        CheckTraceability = true,
        CalculateQualityScores = true,
        GenerateReport = true
    });
    
    await validation.SaveReportAsync("validation/phase0-validation-report.md");
    
    // Get approvals
    var approvals = await GetApprovalsAsync(
        phase: phase0,
        stakeholders: stakeholders.Where(s => s.Priority >= Priority.High),
        artifacts: new[] {
            finalProblemStatement,
            feasibilityReport,
            successCriteria
        }
    );
    
    await approvals.SaveAsync("validation/phase0-approval.md");
    
    // Complete Phase 0
    await phase0.CompleteAsync();
    
    return new Phase0Result
    {
        ProblemStatement = finalProblemStatement,
        FeasibilityReport = feasibilityReport,
        RiskRegister = riskRegister,
        SuccessCriteria = successCriteria,
        ValidationReport = validation,
        GoDecision = validation.RecommendedGoDecision,
        Approvals = approvals
    };
}
```

#### Phase 1 Implementation

```csharp
public static async Task<Phase1Result> RunPhase1Async(
    Project project, 
    Phase0Result phase0Result)
{
    // Initialize Phase 1
    var phase1 = await project.StartPhase1Async(options =>
    {
        options.RequirementsMethodology = RequirementsMethodology.JobsToBeDonePlusUserStories;
        options.ArchitectureFramework = ArchitectureFramework.C4Model;
        options.PrioritizationFramework = PrioritizationFramework.RICE;
    });
    
    // Load Phase 0 artifacts
    await phase1.LoadPhase0ArtifactsAsync(phase0Result);
    
    // === Parallel Track 1: Requirements Specification ===
    var specTask = Task.Run(async () =>
    {
        // Create specification using Analyst Agent
        var analyst = await phase1.GetAgentAsync<AnalystAgent>();
        
        var spec = await analyst.CreateSpecificationAsync(
            problemStatement: phase0Result.ProblemStatement,
            successCriteria: phase0Result.SuccessCriteria
        );
        
        // Validate INVEST compliance
        await spec.ValidateInvestComplianceAsync(minimumScore: 12);
        
        // Save final spec
        await spec.SaveAsync("artifacts/spec.md");
        
        return spec;
    });
    
    // === Parallel Track 2: Architecture Design ===
    var architectureTask = Task.Run(async () =>
    {
        // Create architecture using Architect Agent
        var architect = await phase1.GetAgentAsync<ArchitectAgent>();
        
        var architecture = await architect.DesignArchitectureAsync(
            problemStatement: phase0Result.ProblemStatement,
            constraints: phase0Result.Constraints,
            framework: ArchitectureFramework.C4Model
        );
        
        // Create ADRs for key decisions
        var adrs = await architect.DocumentDecisionsAsync(architecture);
        
        foreach (var adr in adrs)
        {
            await adr.SaveAsync($"adrs/{adr.Number:000}-{adr.Slug}.md");
        }
        
        // Save architecture
        await architecture.SaveAsync("artifacts/architecture.md");
        
        return architecture;
    });
    
    // Wait for both tracks
    await Task.WhenAll(specTask, architectureTask);
    
    var spec = await specTask;
    var architecture = await architectureTask;
    
    // === Create Constitution ===
    var constitutionAgent = await phase1.GetAgentAsync<ConstitutionAgent>();
    
    var constitution = await constitutionAgent.CreateConstitutionAsync(
        phase0Artifacts: phase0Result,
        spec: spec,
        architecture: architecture
    );
    
    await constitution.SaveAsync("artifacts/constitution.md");
    
    // === Create PRD ===
    var pmAgent = await phase1.GetAgentAsync<PMAgent>();
    
    var prd = await pmAgent.CreatePRDAsync(
        spec: spec,
        architecture: architecture,
        constitution: constitution,
        prioritizationFramework: PrioritizationFramework.RICE
    );
    
    await prd.SaveAsync("artifacts/prd.md");
    
    // === Create Data Model ===
    var dataModel = await architecture.ExtractDataModelAsync();
    await dataModel.SaveAsync("artifacts/data-model.md");
    
    // === Create API Specification ===
    var apiSpec = await architecture.GenerateAPISpecificationAsync(
        format: APISpecFormat.OpenAPI30
    );
    await apiSpec.SaveAsync("artifacts/api-spec.json");
    
    // === Validate Phase 1 ===
    var validator = await phase1.GetAgentAsync<ValidatorAgent>();
    
    var validation = await validator.ValidateAsync(new ValidationOptions
    {
        ValidateCompleteness = true,
        ValidateConsistency = true,
        ValidateTraceability = true,
        ValidateQuality = true,
        MinimumQualityScore = 80
    });
    
    await validation.SaveReportAsync("validation/phase1-validation-report.md");
    
    // === Complete Phase 1 ===
    await phase1.CompleteAsync();
    
    return new Phase1Result
    {
        Spec = spec,
        Architecture = architecture,
        DataModel = dataModel,
        APISpec = apiSpec,
        Constitution = constitution,
        PRD = prd,
        ADRs = await phase1.GetADRsAsync(),
        ValidationReport = validation,
        ValidationStatus = validation.Status
    };
}
```

#### Phase 2 Implementation

```csharp
public static async Task<Phase2Result> RunPhase2Async(
    Project project,
    Phase1Result phase1Result)
{
    // Initialize Phase 2
    var phase2 = await project.StartPhase2Async(options =>
    {
        options.TaskSizingApproach = TaskSizingApproach.StoryPointsFibonacci;
        options.SprintDuration = TimeSpan.FromDays(14);
        options.TeamSize = 5;
        options.VelocityEstimation = VelocityEstimation.Conservative;
    });
    
    // Load Phase 1 artifacts
    await phase2.LoadPhase1ArtifactsAsync(phase1Result);
    
    // === Parallel Workstream 1: Planning ===
    var planningTask = Task.Run(async () =>
    {
        var planningAgent = await phase2.GetAgentAsync<PlanningAgent>();
        
        // Decompose requirements into tasks
        var taskBreakdown = await planningAgent.DecomposeTasksAsync(
            spec: phase1Result.Spec,
            architecture: phase1Result.Architecture
        );
        
        await taskBreakdown.SaveAsync("artifacts/task-breakdown.md");
        
        // Map dependencies
        var dependencyMap = await planningAgent.MapDependenciesAsync(taskBreakdown);
        await dependencyMap.SaveAsync("artifacts/dependency-map.md");
        
        // Plan sprints
        var sprintPlan = await planningAgent.PlanSprintsAsync(
            taskBreakdown: taskBreakdown,
            dependencies: dependencyMap,
            teamCapacity: options.TeamSize * 8 // 8 points per dev per sprint
        );
        
        await sprintPlan.SaveAsync("artifacts/sprint-plan.md");
        
        // Generate individual sprint plans
        foreach (var sprint in sprintPlan.Sprints)
        {
            await sprint.SaveAsync($"artifacts/sprints/sprint-{sprint.Number}-plan.md");
        }
        
        return new PlanningArtifacts
        {
            TaskBreakdown = taskBreakdown,
            DependencyMap = dependencyMap,
            SprintPlan = sprintPlan
        };
    });
    
    // === Parallel Workstream 2: Infrastructure ===
    var infraTask = Task.Run(async () =>
    {
        var devOpsAgent = await phase2.GetAgentAsync<DevOpsScaffolderAgent>();
        
        // Set up repository
        var repoStructure = await devOpsAgent.SetupRepositoryAsync(
            architecture: phase1Result.Architecture,
            branchingStrategy: BranchingStrategy.GitHubFlow
        );
        
        await repoStructure.SaveAsync("artifacts/repository-structure.md");
        
        // Provision infrastructure
        var environmentConfig = await devOpsAgent.ProvisionInfrastructureAsync(
            architecture: phase1Result.Architecture,
            environments: new[] { "dev", "staging", "prod" },
            asCode: true
        );
        
        await environmentConfig.SaveAsync("artifacts/environment-config.md");
        
        // Set up CI/CD
        var cicdConfig = await devOpsAgent.SetupCICDAsync(
            repository: repoStructure,
            environments: environmentConfig
        );
        
        return new InfrastructureArtifacts
        {
            RepositoryStructure = repoStructure,
            EnvironmentConfig = environmentConfig,
            CICDConfig = cicdConfig
        };
    });
    
    // === Parallel Workstream 3: Quality ===
    var qualityTask = Task.Run(async () =>
    {
        var qualityAgent = await phase2.GetAgentAsync<QualityArchitectAgent>();
        
        // Create test plan
        var testPlan = await qualityAgent.CreateTestPlanAsync(
            spec: phase1Result.Spec,
            architecture: phase1Result.Architecture,
            strategy: TestStrategy.TestPyramidWithE2E
        );
        
        await testPlan.SaveAsync("artifacts/test-plan.md");
        
        // Define quality gates
        var qualityGates = await qualityAgent.DefineQualityGatesAsync(
            testPlan: testPlan,
            automationLevel: AutomationLevel.Progressive
        );
        
        await qualityGates.SaveAsync("artifacts/quality-gates.md");
        
        return new QualityArtifacts
        {
            TestPlan = testPlan,
            QualityGates = qualityGates
        };
    });
    
    // Wait for all workstreams
    await Task.WhenAll(planningTask, infraTask, qualityTask);
    
    var planningArtifacts = await planningTask;
    var infraArtifacts = await infraTask;
    var qualityArtifacts = await qualityTask;
    
    // === Validate Phase 2 ===
    var validation = await phase2.ValidateAsync(new ValidationOptions
    {
        ValidateTaskCoverage = true,
        ValidateDependencies = true,
        ValidateInfrastructure = true,
        ValidateQualityFramework = true
    });
    
    await validation.SaveReportAsync("validation/phase2-validation-report.md");
    
    // === Complete Phase 2 ===
    await phase2.CompleteAsync();
    
    return new Phase2Result
    {
        TaskBreakdown = planningArtifacts.TaskBreakdown,
        DependencyMap = planningArtifacts.DependencyMap,
        SprintPlan = planningArtifacts.SprintPlan,
        RepositoryStructure = infraArtifacts.RepositoryStructure,
        EnvironmentConfig = infraArtifacts.EnvironmentConfig,
        TestPlan = qualityArtifacts.TestPlan,
        QualityGates = qualityArtifacts.QualityGates,
        ValidationReport = validation,
        ReadyForPhase3 = validation.Status == ValidationStatus.Passed
    };
}
```

---

### Pattern 3 Integration Examples

#### Integrate with Jira

```csharp
public static async Task SyncWithJiraAsync(Phase2Result phase2Result)
{
    var jiraClient = new JiraClient(config.JiraApiKey);
    
    // Create epic for project
    var epic = await jiraClient.CreateEpicAsync(new Epic
    {
        Summary = project.Name,
        Description = phase2Result.TaskBreakdown.Summary
    });
    
    // Create stories and tasks
    foreach (var task in phase2Result.TaskBreakdown.Tasks)
    {
        var story = await jiraClient.CreateStoryAsync(new Story
        {
            Summary = task.Title,
            Description = task.Description,
            StoryPoints = task.Points,
            Epic = epic,
            AcceptanceCriteria = task.AcceptanceCriteria
        });
        
        // Link dependencies
        foreach (var dependency in task.Dependencies)
        {
            await jiraClient.CreateLinkAsync(story, dependency, LinkType.Blocks);
        }
    }
    
    // Create sprints
    foreach (var sprint in phase2Result.SprintPlan.Sprints)
    {
        var jiraSprint = await jiraClient.CreateSprintAsync(new Sprint
        {
            Name = sprint.Name,
            Goal = sprint.Goal,
            StartDate = sprint.StartDate,
            EndDate = sprint.EndDate
        });
        
        // Assign tasks to sprint
        foreach (var task in sprint.Tasks)
        {
            await jiraClient.AddToSprintAsync(task.JiraId, jiraSprint.Id);
        }
    }
}
```

#### Integrate with Azure DevOps

```csharp
public static async Task SyncWithAzureDevOpsAsync(Phase2Result phase2Result)
{
    var adoClient = new AzureDevOpsClient(config.AdoToken);
    
    // Create project
    var adoProject = await adoClient.CreateProjectAsync(project.Name);
    
    // Create repository
    var repo = await adoClient.CreateRepositoryAsync(
        project: adoProject,
        structure: phase2Result.RepositoryStructure
    );
    
    // Set up pipelines
    foreach (var pipeline in phase2Result.CICDConfig.Pipelines)
    {
        await adoClient.CreatePipelineAsync(
            repository: repo,
            definition: pipeline
        );
    }
    
    // Create work items
    var workItemClient = adoClient.GetWorkItemClient();
    
    foreach (var task in phase2Result.TaskBreakdown.Tasks)
    {
        await workItemClient.CreateWorkItemAsync(new WorkItem
        {
            Type = WorkItemType.UserStory,
            Title = task.Title,
            Description = task.Description,
            Effort = task.Points,
            AreaPath = adoProject.AreaPath,
            IterationPath = task.Sprint.IterationPath
        });
    }
}
```

---

### Pattern 3 Best Practices

**Architecture**:
- Use microservices or modular architecture
- Implement proper error handling and retries
- Log all operations for audit trail
- Design for extensibility

**Integration**:
- Use webhooks for real-time sync
- Implement idempotent operations
- Handle API rate limits gracefully
- Cache frequently accessed data

**Monitoring**:
- Track project health metrics
- Monitor agent performance
- Alert on validation failures
- Generate analytics dashboards

**Security**:
- Encrypt sensitive data
- Implement role-based access control
- Audit all operations
- Follow least privilege principle

---

## Getting Started

### Prerequisites

**For All Patterns**:
- Access to AI assistant (Claude, ChatGPT, etc.)
- Basic understanding of SDLC concepts
- Text editor (VS Code, Sublime, etc.)

**For Pattern 2 (CLI)**:
- Node.js or .NET runtime
- Command-line skills
- Git (recommended)

**For Pattern 3 (API)**:
- Development skills (C#, TypeScript, Python)
- API/SDK from framework provider
- Infrastructure for hosting

---

### Quick Start (Pattern 1)

**Step 1: Download the Framework**

```bash
git clone https://github.com/yourusername/agentic-sdlc.git
cd agentic-sdlc
```

**Step 2: Review Core Files**

Read these files to understand the system:
- `.sdlc/reference/README.md` (this file)
- `.sdlc/reference/directory-structure.md`
- `.sdlc/reference/sdlc-workflow.html`

**Step 3: Customize Config**

Update config files for your organization:
- `.sdlc/config/phase0_config.md`
- `.sdlc/config/phase1_config.md`
- `.sdlc/config/phase2_config.md`

**Step 4: Fill Memory Files**

Add organizational context:
- `.sdlc/memory/organization_context.md`
- `.sdlc/memory/technical-stack_context.md`

**Step 5: Start Your First Project**

```bash
# Create project directory
mkdir -p projects/my-first-project/phase0/{interviews,working,artifacts,validation}

# Copy context template
cp .sdlc/primitives/templates/phase0-context_template.md \
   projects/my-first-project/phase0/phase0-context.md

# Start AI conversation following Pattern 1 guide above
```

---

## Phase-by-Phase Guide

### Phase 0: Discovery & Ideation

**Goal**: Validate the problem before investing in solutions

**Duration**: 1-2 weeks

**Key Activities**:
1. **Stakeholder Interviews** (5-10 interviews)
   - Executive sponsor
   - Product owner
   - End users (2-3)
   - Technical stakeholders
   - Support/operations

2. **Problem Statement** (3-5 iterations)
   - Initial draft after 2-3 interviews
   - Refinement after feedback
   - Five Whys root cause analysis
   - Final validation

3. **Feasibility Assessment**
   - Technical feasibility (can we build it?)
   - Business feasibility (should we build it?)
   - Resource feasibility (do we have what we need?)
   - Timeline feasibility (can we deliver in time?)

4. **Risk & Success**
   - Identify major risks
   - Define mitigation strategies
   - Create SMART success metrics

5. **Stakeholder Alignment**
   - Ensure consensus on problem
   - Resolve misalignments
   - Get approval to proceed

**Deliverables**:
- ✅ Problem statement (validated)
- ✅ Feasibility report (≥3.0/5.0)
- ✅ Risk register
- ✅ Success criteria (SMART)
- ✅ Stakeholder alignment

**Exit Criteria**:
- All key stakeholders interviewed
- Problem clearly defined
- Feasibility confirmed
- Critical risks mitigated
- Executive approval obtained

---

### Phase 1: Specification & Design

**Goal**: Define WHAT to build and HOW it will be architected

**Duration**: 2-4 weeks

**Key Activities**:
1. **Requirements Specification**
   - User stories with acceptance criteria
   - Non-functional requirements
   - Edge cases and dependencies
   - INVEST validation

2. **Architecture Design**
   - C4 Context diagram (system in environment)
   - C4 Container diagram (major components)
   - Technology selection with ADRs
   - Data model and API design
   - NFR decomposition

3. **Constitution Creation**
   - Project values and principles
   - Non-negotiables (must haves)
   - Anti-patterns (must not do)
   - Decision framework
   - Quality standards

4. **Product Requirements**
   - MVP definition
   - Success metrics
   - Release strategy
   - Prioritization

5. **Validation**
   - Traceability (Phase 0 → Phase 1)
   - Quality scoring (all ≥80)
   - Consistency check
   - Stakeholder approval

**Deliverables**:
- ✅ Technical specification
- ✅ System architecture (C4 diagrams)
- ✅ Data model
- ✅ API specification (OpenAPI)
- ✅ Constitution
- ✅ Product Requirements Document
- ✅ Architecture Decision Records

**Exit Criteria**:
- All artifacts score ≥80
- Traceability ≥90%
- Zero critical issues
- All approvals obtained
- Team briefed

---

### Phase 2: Planning & Setup

**Goal**: Prepare infrastructure and create executable plan

**Duration**: 2-3 weeks

**Key Activities**:

**Workstream 1: Planning**
- Decompose requirements to tasks
- Estimate using story points
- Map dependencies
- Plan sprints with capacity
- Define Sprint 0 (infrastructure)

**Workstream 2: Infrastructure**
- Set up code repository
- Define repository structure
- Provision environments (dev, staging, prod)
- Configure CI/CD pipelines
- Set up monitoring

**Workstream 3: Quality**
- Design test strategy
- Set up test frameworks
- Define quality gates
- Plan code review process
- Configure automated checks

**Deliverables**:
- ✅ Task breakdown
- ✅ Dependency map
- ✅ Sprint plan (all sprints)
- ✅ Repository structure
- ✅ Environment configuration
- ✅ Test plan
- ✅ Quality gates

**Exit Criteria**:
- All requirements mapped to tasks
- Dependencies resolved
- Infrastructure ready
- Quality framework defined
- Team onboarded
- Sprint 0 ready

---

## Real-World Example

### Case Study: E-Commerce Checkout Redesign

**Background**: Mid-sized online retailer with 500K monthly users experiencing 35% cart abandonment rate at checkout.

---

#### Phase 0: Discovery (1.5 weeks)

**Week 1: Stakeholder Interviews**

Conducted 7 interviews:
1. CEO (30 min) - Business context and urgency
2. VP Product (60 min) - Product vision and constraints
3. CTO (60 min) - Technical feasibility and architecture
4. UX Designer (45 min) - Current pain points
5-7. Customers (30 min each) - Jobs-to-be-done analysis

**Key Insight from Interviews**:
- Users abandon because checkout requires account creation
- Mobile experience is particularly poor
- Payment options are limited
- Security concerns (no trust badges)

**Week 2: Synthesis and Validation**

**Problem Statement Evolution**:
- v1: "Checkout process is too long" (too vague)
- v2: "Users abandon because we require account creation" (getting closer)
- v3 (Final): "Users need to complete purchases quickly without creating accounts, especially on mobile, while feeling secure about payment. Root cause: We designed for company convenience (data collection) not user needs."

**Five Whys Analysis**:
- Why do users abandon? → Checkout takes too long
- Why does checkout take too long? → Must create account
- Why must they create account? → That's our policy
- Why is that our policy? → We want customer data
- Why do we want customer data? → To enable marketing
- **Root Cause**: Prioritizing data collection over conversion

**Feasibility Assessment** (4.2/5.0):
- Technical: 4/5 (guest checkout is standard)
- Business: 5/5 (higher conversion = more revenue)
- Resource: 4/5 (team available, 3 months effort)
- Timeline: 4/5 (can ship in 3 months)

**Success Metrics**:
- Reduce cart abandonment from 35% to 20% (primary)
- Increase mobile conversion by 40% (primary)
- Maintain or improve security ratings (secondary)
- Launch within 3 months (timeline)

**Outcome**: Go decision approved

---

#### Phase 1: Specification & Design (3 weeks)

**Week 1-2: Requirements and Architecture**

**Technical Specification** (spec.md):
- 12 user stories covering guest checkout flow
- 28 acceptance criteria using Given-When-Then
- INVEST scores: 14.5/18 average (excellent)

**Example User Story**:
```markdown
## US-001: Guest Checkout Option

As a customer,
I want to checkout without creating an account,
So that I can complete my purchase quickly.

**Acceptance Criteria**:
1. Given I'm on the cart page
   When I click "Checkout"
   Then I see options for "Guest Checkout" and "Sign In"

2. Given I select "Guest Checkout"
   When I proceed
   Then I only provide email, shipping, and payment info

3. Given I complete guest checkout
   When order is confirmed
   Then I receive email with option to create account later

**Story Points**: 5
**Dependencies**: None
**Priority**: Must Have
```

**System Architecture** (architecture.md):
- C4 Context: E-commerce system with payment gateway integration
- C4 Container: React SPA, Node.js API, PostgreSQL
- Technology decisions: 3 ADRs created

**ADR Example - 001: Guest Checkout Storage**:
```markdown
# ADR 001: Guest Checkout Session Storage

**Status**: Accepted
**Date**: 2025-10-15

**Context**: 
We need to store guest checkout data temporarily without
creating user accounts.

**Decision**: 
Use secure session storage (Redis) with 24-hour TTL.
After order completion, migrate to order history.

**Consequences**:
+ No database pollution with incomplete guest data
+ Fast session retrieval
+ Automatic cleanup
- Requires Redis infrastructure
- Need migration logic post-purchase

**Alternatives Considered**:
1. Store in database immediately (rejected: data pollution)
2. Use browser localStorage (rejected: security concerns)
```

**Week 3: Constitution and PRD**

**Constitution** (constitution.md):
```markdown
## Non-Negotiables
- User privacy: Never sell customer data
- Security: PCI-DSS compliance required
- Performance: Page load <2 seconds
- Accessibility: WCAG 2.1 AA compliance

## Anti-Patterns
- Do NOT require account creation for purchase
- Do NOT collect unnecessary user data
- Do NOT compromise mobile experience
- Do NOT ignore security best practices
```

**PRD - MVP Definition**:
```markdown
## Must Have (Sprint 1-2)
- Guest checkout flow
- Mobile-optimized UI
- Essential payment methods (cards, PayPal)
- Basic trust badges

## Should Have (Sprint 3-4)
- Additional payment methods (Apple Pay, Google Pay)
- Save info for later (without account)
- Enhanced trust signals
- A/B testing framework

## Could Have (Future)
- One-click checkout for returning guests
- Social login integration
- Cryptocurrency payment
```

**Validation**: 
- All artifacts scored 85+
- Traceability: 94%
- Approved by all stakeholders

---

#### Phase 2: Planning & Setup (2.5 weeks)

**Week 1-2: Task Decomposition and Sprint Planning**

**Task Breakdown**:
- 43 tasks total from 12 user stories
- Average task size: 6 story points
- Total effort: 258 story points

**Dependency Analysis**:
- Critical path: 7 sprints (14 weeks)
- Parallel tracks identified for optimization
- 0 circular dependencies

**Sprint Plan** (5 sprints, 2 weeks each):
```markdown
## Sprint 0: Infrastructure (Weeks 1-2)
**Goal**: Set up development environment and CI/CD
**Capacity**: 40 points
**Tasks**: Repository setup, staging environment, CI pipeline
**Team**: Full team

## Sprint 1: Core Guest Flow (Weeks 3-4)
**Goal**: Implement basic guest checkout
**Capacity**: 40 points
**Tasks**: 
- Guest checkout option UI
- Email capture
- Basic validation
- Session management
**Team**: 2 frontend, 2 backend, 1 QA

## Sprint 2: Payment Integration (Weeks 5-6)
**Goal**: Integrate payment processing
**Capacity**: 40 points
**Tasks**:
- Payment gateway integration
- Security implementation
- Error handling
- Receipt generation
**Team**: 2 backend, 1 frontend, 2 QA

## Sprint 3: Mobile Optimization (Weeks 7-8)
**Goal**: Optimize for mobile devices
**Capacity**: 40 points
**Tasks**:
- Responsive design
- Mobile payment methods
- Performance optimization
- Mobile-specific testing
**Team**: 3 frontend, 1 backend, 1 QA

## Sprint 4: Polish and Testing (Weeks 9-10)
**Goal**: Complete testing and prepare for launch
**Capacity**: 40 points
**Tasks**:
- E2E testing
- Security audit
- Performance testing
- Bug fixes
**Team**: Full team
```

**Week 2-3: Infrastructure and Quality**

**Repository Setup**:
- Monorepo structure with frontend and backend
- GitHub Actions CI/CD
- Branch protection rules configured

**Infrastructure Provisioned**:
- Development: AWS ECS dev cluster
- Staging: Production-like environment
- Production: Auto-scaling ECS cluster with CloudFront

**Test Strategy**:
```markdown
## Unit Tests
**Target**: 80% coverage
**Framework**: Jest (frontend), Mocha (backend)

## Integration Tests
**Target**: 60% of critical paths
**Framework**: Cypress

## E2E Tests
**Target**: 100% of checkout flow
**Framework**: Playwright

## Performance Tests
**Target**: <2s page load, <500ms API response
**Tool**: Lighthouse, k6
```

**Quality Gates**:
1. Code commit: Linting passes
2. PR: Unit tests pass, coverage ≥80%
3. Staging: Integration tests pass
4. Production: E2E tests pass, performance benchmarks met

**Validation**:
- All requirements → tasks: 100%
- Infrastructure ready: ✅
- Team onboarded: ✅
- Sprint 0 starting: ✅

---

#### Results (After Implementation)

**Metrics Achieved** (3 months post-launch):
- Cart abandonment: 35% → 18% (exceeded goal of 20%)
- Mobile conversion: +52% (exceeded goal of +40%)
- Average checkout time: 8 min → 2.5 min
- Customer satisfaction: +23%

**Business Impact**:
- Revenue increase: +18% ($2.1M annually)
- ROI: 7x within 6 months
- Customer complaints: -45%

**Lessons Learned**:
- Discovery investment (1.5 weeks) prevented 3 months of wrong solution
- Mobile-first design from Phase 1 critical for success
- Parallel workstreams in Phase 2 saved 2 weeks
- Quality gates caught 23 critical bugs before production

---

## Benefits

### For Individuals

**Clarity and Structure**:
- No more guessing what to do next
- Clear processes for each phase
- Quality gates prevent mistakes
- Templates accelerate work

**Learning and Growth**:
- Learn professional SDLC practices
- Build portfolio of well-documented projects
- Develop systematic thinking
- Improve decision-making skills

**Career Advancement**:
- Demonstrate professional rigor
- Show ability to manage complex projects
- Provide proof of systematic approach
- Stand out from unstructured developers

---

### For Teams

**Coordination**:
- Everyone follows same process
- Clear handoffs between phases
- Parallel workstreams well-defined
- Reduced miscommunication

**Quality**:
- Consistent artifact quality
- Fewer defects reach production
- Better architecture decisions
- Improved requirements clarity

**Velocity**:
- AI accelerates grunt work
- Less rework due to quality gates
- Faster onboarding of new members
- Reusable patterns and templates

**Knowledge Sharing**:
- Accumulated organizational wisdom
- Documentation as work proceeds
- Lessons learned captured
- Best practices evolve

---

### For Organizations

**Standardization**:
- Consistent SDLC across teams
- Predictable quality levels
- Comparable metrics
- Easier resource allocation

**Scalability**:
- New teams adopt quickly
- Process handles growth
- Can run multiple projects
- Distributed teams coordinate

**Risk Reduction**:
- Problems caught early
- Quality gates prevent bad code
- Traceability enables audits
- Decision documentation

**Continuous Improvement**:
- Data-driven refinements
- Lessons learned applied
- Historical data improves estimates
- Process evolves with organization

**Cost Savings**:
- Fewer failed projects (validate problems first)
- Less rework (quality gates)
- Faster development (AI assistance)
- Better resource utilization

---

## FAQ

### General Questions

**Q: Is this just waterfall in disguise?**

A: No. While we have phase gates, work within phases is highly iterative. You can also adapt to use more agile approaches. The key difference from waterfall: we validate understanding before proceeding, but we expect iteration and refinement.

**Q: How long does each phase take?**

A: Typical timelines:
- Phase 0: 1-2 weeks
- Phase 1: 2-4 weeks
- Phase 2: 2-3 weeks
- Total pre-implementation: 5-9 weeks

For smaller projects, phases can be compressed. For larger projects, they extend.

**Q: Do I have to use all three usage patterns?**

A: No. Choose one:
- **Pattern 1** (Manual): Best for learning and small projects
- **Pattern 2** (CLI): Best for regular use and medium teams
- **Pattern 3** (API): Best for large organizations and high volume

**Q: Can I use this with existing tools (Jira, Azure DevOps, etc.)?**

A: Yes! The framework is tool-agnostic. Pattern 2 and 3 include integrations with common tools. You can also build custom integrations.

**Q: What if my team doesn't want to change?**

A: Start small:
1. Use it yourself on a side project
2. Demonstrate results
3. Offer to pilot on one team project
4. Gradually expand adoption

Show, don't tell.

---

### Technical Questions

**Q: What AI models work with this?**

A: Any capable AI assistant:
- Claude (Sonnet 3.5+)
- ChatGPT (GPT-4+)
- Other LLMs with sufficient context window

The framework is model-agnostic.

**Q: How much does this cost?**

A: The framework itself is free and open source.

Costs:
- **Pattern 1**: Only AI API costs ($20-100/month for most projects)
- **Pattern 2**: AI costs + potential CLI tool license
- **Pattern 3**: AI costs + development + infrastructure

**Q: What programming languages are supported?**

A: All. The framework is language-agnostic. Architecture and code decisions are made in Phase 1-2 based on your needs.

**Q: Can this work for non-software projects?**

A: Yes! The discovery and planning processes work for any project. You'd just adapt Phase 1-2 for your domain.

---

### Process Questions

**Q: Can we skip Phase 0 if we know the problem?**

A: Not recommended. Even "known" problems benefit from validation. Phase 0 often reveals:
- Misalignments between stakeholders
- Root causes deeper than symptoms
- Constraints you didn't know about
- Better alternative solutions

Budget 1-2 weeks. It's worth it.

**Q: What if feasibility is low in Phase 0?**

A: That's a success! You learned the project isn't viable before wasting months. Options:
- No-go (save resources)
- Pivot (solve different problem)
- Conditional-go (mitigate risks first)

**Q: How do we handle changing requirements?**

A: The framework expects changes:
- **During phase**: Update working versions, maintain traceability
- **After phase**: Assess impact, potentially re-validate
- **During implementation**: Follow change control process defined in constitution

**Q: What if we don't have stakeholders to interview?**

A: You always have stakeholders:
- Internal product: Business owners, users, operations
- Side project: Yourself (as user), potential users, technical constraints
- Consulting: Client, end users, client's team

If truly solo: Interview yourself systematically, but be rigorous about root cause analysis.

---

### Customization Questions

**Q: Can we customize the templates?**

A: Absolutely! Templates are markdown - edit freely. Just maintain:
- Required sections (per your organization's standards)
- Validation criteria
- Consistent structure across projects

**Q: Can we change the phase structure?**

A: Yes, but carefully. The three phases (Discover, Specify, Plan) represent natural breakpoints:
- Validating problem before designing solution
- Validating design before implementing
- Preparing infrastructure before coding

If you modify, ensure quality gates remain.

**Q: Can we use different methodologies?**

A: Yes! Config files let you choose:
- Interview methods (Jobs-to-be-Done, Contextual Inquiry, etc.)
- Requirements approaches (User Stories, Use Cases, etc.)
- Architecture frameworks (C4, 4+1 Views, arc42, etc.)
- Planning methods (Scrum, Kanban, etc.)

The framework is methodology-agnostic - it's a structure, not a religion.

---

## Contributing

### How to Contribute

We welcome contributions!

**Ways to Contribute**:
- Report bugs or issues
- Suggest enhancements
- Submit templates for different domains
- Share lessons learned
- Create integrations with tools
- Improve documentation
- Build CLI tools or SDKs

**Contribution Process**:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

**Contribution Guidelines**:
- Follow existing file naming conventions
- Use markdown for documentation
- Include examples in templates
- Add tests for code contributions
- Update relevant documentation

---

### Areas We Need Help

**High Priority**:
- Industry-specific templates (healthcare, finance, etc.)
- Integration examples (Jira, Azure DevOps, GitHub Projects)
- CLI tool implementation (Node.js or .NET)
- Case studies and examples
- Video tutorials

**Medium Priority**:
- Additional chatmode definitions
- More workflow prompts
- Quality scoring automation
- Traceability analysis tools

**Low Priority**:
- Visual workflow diagram improvements
- Additional language translations
- Alternative template formats

---

## License

MIT License

Copyright (c) 2025 [Your Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

---

## Additional Resources

### Documentation

- **Directory Structure**: See `.sdlc/reference/directory-structure.md` for complete structure details
- **Visual Workflow**: Open `.sdlc/reference/sdlc-workflow.html` for interactive diagram
- **Config Files**: Review `.sdlc/config/phase[N]_config.md` for phase-specific settings
- **Agent Instructions**: Read `.sdlc/primitives/agents/` for agent capabilities

### Learning Resources

- **Phase 0 Deep Dive**: [Link to Phase 0 guide]
- **Phase 1 Deep Dive**: [Link to Phase 1 guide]
- **Phase 2 Deep Dive**: [Link to Phase 2 guide]
- **Video Tutorials**: [Link to YouTube playlist]
- **Case Studies**: [Link to case studies collection]

### Community

- **GitHub**: [Repository URL]
- **Discord**: [Discord server invite]
- **Forum**: [Community forum URL]
- **Blog**: [Blog URL]

### Support

- **Issues**: Report bugs on GitHub Issues
- **Questions**: Ask on Discord or forum
- **Professional Support**: [Contact information]

---

## Acknowledgments

This framework builds on ideas from:
- **BMAD Method** (Agent-based development)
- **GitHub Spec-Kit** (Specification-driven development)
- **GitHub Agentic Primitives** (Instructions, chatmodes, workflows, memory)
- **Context Engineering** (Session management, delta updates)
- **Traditional SDLC** (Phase gates, quality assurance)

Special thanks to the open-source community for inspiration and feedback.

---

## Next Steps

Ready to get started?

### For New Users
1. ⭐ Star this repository
2. 📖 Read the [Quick Start Guide](#quick-start-pattern-1)
3. 🎯 Start your first project using Pattern 1
4. 💬 Join our Discord for support

### For Teams
1. 📋 Review and customize config files
2. 🏢 Fill in memory files with your organization's context
3. 👥 Train team on the framework
4. 🚀 Pilot on one project
5. 📈 Measure results and iterate

### For Organizations
1. 🎯 Define SDLC standardization goals
2. 🛠️ Choose usage pattern (2 or 3)
3. 🔧 Build or license necessary tools
4. 📊 Establish metrics and dashboards
5. 🌐 Roll out across teams

---

**Ready to revolutionize your SDLC?** Let's get started. 🚀

---

*Last updated: 2025-10-31 | Version 2.0 | [Changelog](#)*
