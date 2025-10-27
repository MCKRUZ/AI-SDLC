# Phase 0: Discovery & Ideation - Directory Structure

## Overview
This directory structure supports tool-agnostic discovery workflows with optional programmatic enhancements. The structure separates templates, active work, completed artifacts, and reusable primitives.

```
project-root/
├── .discovery/
│   ├── primitives/
│   │   ├── agents/
│   │   │   ├── discovery-facilitator.instructions.md
│   │   │   ├── feasibility-analyzer.instructions.md
│   │   │   └── synthesis-agent.instructions.md
│   │   ├── templates/
│   │   │   ├── problem-statement.template.md
│   │   │   ├── interview-transcript.template.md
│   │   │   ├── feasibility-report.template.md
│   │   │   ├── risk-register.template.md
│   │   │   └── success-criteria.template.md
│   │   ├── workflows/
│   │   │   ├── discovery-workflow.prompt.md
│   │   │   ├── interview-workflow.prompt.md
│   │   │   └── synthesis-workflow.prompt.md
│   │   └── checklists/
│   │       ├── phase-0-completion.checklist.md
│   │       ├── problem-validation.checklist.md
│   │       └── feasibility-validation.checklist.md
│   ├── memory/
│   │   ├── organization.context.md
│   │   ├── technical-stack.context.md
│   │   ├── prior-projects.memory.md
│   │   └── lessons-learned.memory.md
│   ├── sessions/
│   │   ├── README.md
│   │   └── [active session folders created dynamically]
│   └── config/
│       ├── discovery.config.md
│       └── agent-settings.md
├── discovery-sessions/
│   ├── [session-001-project-name]/
│   │   ├── interviews/
│   │   │   ├── 001-ceo-interview.md
│   │   │   ├── 002-cto-interview.md
│   │   │   ├── 003-support-lead-interview.md
│   │   │   └── 004-customer-interviews.md
│   │   ├── working/
│   │   │   ├── problem-statement-v1.md
│   │   │   ├── problem-statement-v2.md
│   │   │   ├── problem-statement-v3.md
│   │   │   └── notes.md
│   │   ├── artifacts/
│   │   │   ├── problem-statement.final.md
│   │   │   ├── feasibility-report.md
│   │   │   ├── risk-register.md
│   │   │   ├── success-criteria.md
│   │   │   ├── constraints.md
│   │   │   └── stakeholder-alignment.md
│   │   ├── validation/
│   │   │   ├── completion-checklist.md
│   │   │   ├── stakeholder-approvals.md
│   │   │   └── traceability-matrix.md
│   │   └── session.meta.md
│   └── [session-002-another-project]/
└── specs/
    └── [handed off from Phase 0 to Phase 1]
```

## Directory Explanations

### `.discovery/` (Hidden Root)
Contains all reusable discovery assets, templates, and organizational knowledge.

#### `primitives/`
Reusable building blocks for discovery workflows.

- **agents/**: Agent instruction files defining roles, capabilities, and protocols
- **templates/**: Markdown templates for all discovery artifacts
- **workflows/**: Multi-step process definitions combining multiple agents
- **checklists/**: Quality gates and validation criteria

#### `memory/`
Persistent organizational context loaded across sessions.

- **organization.context.md**: Company info, industry, size, culture
- **technical-stack.context.md**: Current technologies, platforms, constraints
- **prior-projects.memory.md**: Past project outcomes, lessons learned
- **lessons-learned.memory.md**: Accumulated wisdom from previous discoveries

#### `sessions/`
Temporary workspace for active discovery conversations (AI agent working directory).

#### `config/`
Configuration files for discovery process customization.

### `discovery-sessions/`
Active and completed discovery sessions. Each project gets its own folder.

#### `[session-XXX-project-name]/`
Individual discovery session container.

- **interviews/**: Raw interview transcripts organized by stakeholder
- **working/**: Iterative drafts showing evolution (delta tracking)
- **artifacts/**: Final, validated deliverables
- **validation/**: Quality checks, approvals, traceability
- **session.meta.md**: Session metadata, timestamps, participants

### `specs/`
Output directory where Phase 0 artifacts are packaged for Phase 1 handoff.

## Usage Patterns

### Pattern 1: Conversational (Manual)
```
1. Human creates new session folder: discovery-sessions/001-customer-portal/
2. Human loads: .discovery/primitives/agents/discovery-facilitator.instructions.md
3. Agent conducts interview following instructions
4. Human saves transcript to: interviews/001-ceo-interview.md
5. Repeat for all stakeholders
6. Human loads: .discovery/primitives/workflows/synthesis-workflow.prompt.md
7. Agent synthesizes problem statement
8. Human saves iterations to: working/problem-statement-v1.md, v2.md, etc.
9. Human validates using: .discovery/primitives/checklists/phase-0-completion.checklist.md
10. Human copies finals to: artifacts/
```

### Pattern 2: Template-Based (Semi-Automated)
```bash
# Initialize new discovery session
/discovery.init "Customer Portal Redesign"
# Creates: discovery-sessions/001-customer-portal/ with templates

# Conduct structured interview
/discovery.interview role="CEO" framework="five-whys"
# Saves to: interviews/001-ceo-interview.md

# Synthesize problem statement
/discovery.synthesize
# Creates: working/problem-statement-v1.md

# Validate completeness
/discovery.validate
# Checks against: .discovery/primitives/checklists/phase-0-completion.checklist.md
```

### Pattern 3: Programmatic (Advanced)
C# application reads from `.discovery/primitives/` and orchestrates automated workflows.

## File Naming Conventions

### Interview Files
Format: `NNN-role-interview.md`
- `001-ceo-interview.md`
- `002-cto-interview.md`
- `003-support-lead-interview.md`

### Working Files (Versioned)
Format: `artifact-name-vN.md`
- `problem-statement-v1.md`
- `problem-statement-v2.md`
- `problem-statement-v3.md`

### Final Artifacts (No Version)
Format: `artifact-name.final.md` or just `artifact-name.md`
- `problem-statement.final.md`
- `feasibility-report.md`
- `risk-register.md`

### Agent Primitives
Format: `agent-name.instructions.md`
- `discovery-facilitator.instructions.md`
- `feasibility-analyzer.instructions.md`

### Templates
Format: `artifact-name.template.md`
- `problem-statement.template.md`
- `interview-transcript.template.md`

### Workflows
Format: `workflow-name.prompt.md`
- `discovery-workflow.prompt.md`
- `interview-workflow.prompt.md`

### Checklists
Format: `checklist-name.checklist.md`
- `phase-0-completion.checklist.md`
- `problem-validation.checklist.md`

## Benefits of This Structure

1. **Separation of Concerns**: Templates separate from active work separate from completed artifacts
2. **Reusability**: Agent primitives used across all sessions
3. **Traceability**: Clear version history in working/ directory
4. **Scalability**: Multiple concurrent discovery sessions supported
5. **Tool Agnostic**: Works with or without automation
6. **Progressive Enhancement**: Start conversational, add automation later
7. **Knowledge Accumulation**: Memory files capture organizational learning

## Migration Path

**Start Simple:**
```
project-root/
├── .discovery/primitives/agents/discovery-facilitator.instructions.md
└── discovery-sessions/001-my-project/
    ├── interviews/001-stakeholder.md
    └── artifacts/problem-statement.md
```

**Grow as Needed:**
Add templates, workflows, checklists, memory files, and programmatic automation incrementally.

## Integration with Phase 1

When Phase 0 completes:
```bash
# Copy artifacts to specs directory for Phase 1
cp discovery-sessions/001-customer-portal/artifacts/* specs/001-customer-portal/phase-0/
```

Phase 1 reads from `specs/001-customer-portal/phase-0/` to begin specification work.
