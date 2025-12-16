# Phase 1: Specification & Design - Quick Start Guide

**Purpose**: Use Phase 1 to define WHAT to build through requirements, product vision, and architecture before implementation.

**When to Use Phase 1**:
- Starting a new project that needs specification
- Designing a significant new feature
- Modernizing or replacing an existing system
- Any work requiring architectural decisions

**When to Skip Phase 1**:
- Bug fixes with clear reproduction steps
- Tiny enhancements with obvious implementation
- Work already specified elsewhere

---

## What You'll Produce

| Artifact | Purpose |
|----------|---------|
| **Constitution** | Project principles, quality standards, constraints |
| **Specification** | Detailed requirements with acceptance criteria |
| **PRD** | Product vision, priorities, MVP definition |
| **Architecture** | System design, components, technology choices |
| **Data Model** | Entity definitions and relationships |
| **API Specification** | Endpoint contracts |
| **ADRs** | Key decision documentation |

---

## Quick Start (30 minutes to first session)

### Step 1: Create Workspace

```bash
# Create project structure
mkdir -p projects/[project-name]/phase1/{working,artifacts,adrs,validation}

# Initialize context file
touch projects/[project-name]/phase1/phase1-context.md
```

### Step 2: Gather Inputs

**If coming from Phase 0**, load:
- `phase0/artifacts/problem-statement.md`
- `phase0/artifacts/feasibility-report.md`
- `phase0/artifacts/success-criteria.md`
- `phase0/artifacts/constraints.md`

**If starting fresh**, prepare:
- Problem/opportunity description (1-2 paragraphs)
- Known constraints (timeline, budget, technology)
- Key stakeholders and their priorities
- Success criteria (how will we know it worked?)

### Step 3: Load Required Files

Load these into your AI context:

**Agent Instructions** (load as needed):
```
.sdlc/primitives/agents/phase1/constitution-agent_instructions.md
.sdlc/primitives/agents/phase1/analyst-agent_instructions.md
.sdlc/primitives/agents/phase1/pm-agent_instructions.md
.sdlc/primitives/agents/phase1/architect-agent_instructions.md
.sdlc/primitives/agents/phase1/validator-agent_instructions.md
```

**Configuration**:
```
.sdlc/config/phase1_config.md
```

**Organizational Context**:
```
.sdlc/memory/organization_context.md
.sdlc/memory/technical-stack_context.md
```

### Step 4: Start with Constitution

Use this prompt to begin:

```
I'm starting Phase 1 specification for [project name].

Here's the context:
- Problem: [Brief description or paste problem statement]
- Constraints: [List known constraints]
- Success criteria: [How we'll measure success]

Let's start by creating the Project Constitution - the principles and 
standards that will guide all other work. Please use the Constitution 
Agent instructions.
```

---

## Phase 1 Flow

```
┌─────────────────────────────────────────────────────────────┐
│                         PHASE 1                              │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
               ┌──────────────────────────┐
               │     1. CONSTITUTION      │  Principles, standards
               │       (2-4 hours)        │  Quality gates
               └──────────────┬───────────┘
                              │
              ┌───────────────┴───────────────┐
              ▼                               ▼
   ┌────────────────────┐        ┌────────────────────┐
   │  2a. SPECIFICATION │        │     2b. PRD        │
   │    (1-2 days)      │        │   (1-2 days)       │
   │  Requirements      │        │  Vision, MVP       │
   │  Acceptance criteria│       │  Priorities        │
   └─────────┬──────────┘        └─────────┬──────────┘
             │                              │
             └───────────────┬──────────────┘
                             ▼
               ┌──────────────────────────┐
               │    3. ARCHITECTURE       │  System design
               │      (2-3 days)          │  Data model, API
               └──────────────┬───────────┘
                              │
                              ▼
               ┌──────────────────────────┐
               │    4. VALIDATION         │  Completeness
               │      (4-6 hours)         │  Consistency
               └──────────────┬───────────┘
                              │
                              ▼
               ┌──────────────────────────┐
               │   5. STAKEHOLDER REVIEW  │  Approval
               │      (1-2 days)          │  Sign-off
               └──────────────────────────┘
```

---

## Key Activities

### Constitution (Start Here!)

The constitution establishes:
- Project vision and objectives
- Non-negotiable principles
- Quality standards (coverage targets, performance requirements)
- Definition of Done
- Decision-making framework

**Why first?** Everything else references constitution standards.

### Requirements Specification

Using the Analyst Agent, create:
- Functional requirements (FR-XXX format)
- Non-functional requirements (NFR-XXX format)
- User stories with acceptance criteria
- Business rules
- Integration requirements

**Chatmode**: Use `analyst.chatmode.md` for requirement sessions.

**Quality Check**: Every requirement must be testable.

### Product Requirements Document

Using the PM Agent, create:
- Product vision statement
- User personas
- Feature prioritization (RICE or MoSCoW)
- MVP definition
- Product roadmap
- Success metrics

**Chatmode**: Use `pm.chatmode.md` for product sessions.

### Architecture

Using the Architect Agent, create:
- System context and components
- Technology stack decisions
- Data model (entities, relationships)
- API specification
- Security architecture
- Scalability approach
- Architecture Decision Records (ADRs)

**Chatmode**: Use `architect.chatmode.md` for design sessions.

### Validation

Using the Validator Agent, verify:
- All artifacts complete
- No contradictions between artifacts
- Requirements trace to problem statement
- Architecture satisfies requirements
- Ready for Phase 2

**Chatmode**: Use `validator.chatmode.md` for validation.

---

## Completion Checklist

Before exiting Phase 1:

- [ ] Constitution complete and approved
- [ ] All functional requirements have acceptance criteria
- [ ] All NFRs are measurable
- [ ] PRD includes clear MVP definition
- [ ] Architecture addresses all NFRs
- [ ] Data model supports data requirements
- [ ] API specification covers all integrations
- [ ] Key decisions documented in ADRs
- [ ] Validation report shows no critical issues
- [ ] Stakeholders have signed off

Use: `.sdlc/primitives/checklists/phase-1-completion_checklist.md`

---

## Handoff to Phase 2

Package these for Phase 2 (Planning & Setup):

1. `constitution.md` - Quality standards and Definition of Done
2. `spec.md` - Requirements to decompose into tasks
3. `prd.md` - MVP scope and priorities
4. `architecture.md` - Implementation guidance
5. `data-model.md` - Database schema
6. `api-spec.json` - API contracts
7. `adrs/` - Decision context

---

## Tips for Success

✅ **Constitution first** - Don't skip it; it guides everything else

✅ **Iterate on requirements** - First draft won't be perfect; refine

✅ **Validate continuously** - Don't wait until the end to check consistency

✅ **Get stakeholder input early** - Don't surprise them at review

✅ **Document decisions** - ADRs prevent re-litigating later

✅ **Use chatmodes** - They provide structure for common sessions

---

## Common Pitfalls

❌ **Vague requirements** - "System should be fast" is not testable

❌ **Architecture before requirements** - Solution before understanding problem

❌ **Gold-plating** - Over-engineering for day 1

❌ **Skipping validation** - Hoping inconsistencies won't matter

❌ **No stakeholder sign-off** - Leading to scope creep later

---

## Session Strategies

Phase 1 is too big for one session. Break it up:

| Session | Focus | Duration |
|---------|-------|----------|
| 1 | Constitution | 2-4 hours |
| 2-3 | Requirements (Analyst) | 2-4 hours each |
| 4-5 | PRD (PM) | 2-4 hours each |
| 6-8 | Architecture | 2-4 hours each |
| 9 | Validation | 4-6 hours |

**Between sessions**: Save context to `phase1-context.md`

---

## Need Help?

**Full Workflow**: `.sdlc/primitives/workflows/phase1/phase1-orchestration.prompt.md`

**Architecture Guide**: `.sdlc/primitives/workflows/phase1/architecture-design.prompt.md`

**Chatmodes**:
- `analyst.chatmode.md`
- `pm.chatmode.md`  
- `architect.chatmode.md`
- `validator.chatmode.md`

---

*Phase 1 is where clarity is created. Time invested here prevents expensive changes later.*
