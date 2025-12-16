# Agentic SDLC Framework

**A Tool-Agnostic, AI-Powered Software Development Lifecycle System**

Version 3.0 | Last Updated: 2025-12-13

---

## Table of Contents

1. [What Is This?](#what-is-this)
2. [Key Features](#key-features)
3. [The Four Phases](#the-four-phases)
4. [The Three Tracks](#the-three-tracks)
5. [Quick Start](#quick-start)
6. [Directory Structure](#directory-structure)
7. [Core Concepts](#core-concepts)
8. [Phase-by-Phase Guide](#phase-by-phase-guide)
9. [Track Selection Guide](#track-selection-guide)
10. [Story Files & Document Sharding](#story-files--document-sharding)
11. [Automation with SDLCOrchestrator](#automation-with-sdlcorchestrator)
12. [FAQ](#faq)
13. [Contributing](#contributing)

---

## What Is This?

The **Agentic SDLC Framework** is a comprehensive, structured approach to software development that leverages AI agents to amplify human decision-making throughout the entire software development lifecycle.

### What Makes It "Agentic"?

This framework uses **agentic AI** - specialized AI personas with:

- **Clear roles and responsibilities** (Discovery Facilitator, Technical Architect, Scrum Master, etc.)
- **Decision-making frameworks** (when to escalate, what quality standards to meet)
- **Contextual awareness** (what information to load for each activity)
- **Collaborative workflows** (how agents work together and hand off to each other)

The AI agents **generate and propose**, while humans **validate and decide**. This keeps domain experts in control while dramatically accelerating the SDLC.

---

## Key Features

### 🎯 Right-Sized Planning with Three Tracks

Not every project needs full discovery. Choose the methodology depth that fits:

| Track | Planning Time | Effort Range | Best For |
|-------|---------------|--------------|----------|
| **Quick** | 1-4 hours | < 2 weeks | Bug fixes, small features |
| **Standard** | 2-5 days | 2-12 weeks | Features, small projects |
| **Enterprise** | 1-3 weeks | 12+ weeks | Major initiatives, high stakes |

### 📦 Self-Contained Story Files

Story files carry all context needed for implementation:
- Developers load ONE file, not multiple documents
- Architecture excerpts are sharded (not copied wholesale)
- Notes accumulate as story progresses (SM → Dev → QA)

### 🔗 Document Sharding (Enterprise Track)

Large documents are sharded by consumer need:
- 90%+ token savings vs loading full documents
- Each story only loads relevant architecture sections
- Shards include source metadata for traceability

### 🏗️ Four Clear Phases

1. **Discovery** - Validate the problem exists
2. **Specification** - Define what to build
3. **Planning** - Plan how to build it
4. **Implementation** - Build it

### 💰 Built-in Cost & Resource Planning

- Cost estimation at multiple fidelity levels
- Resource planning with pod design
- Validation loops between cost and capacity

---

## The Four Phases

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           AGENTIC SDLC PHASES                               │
└─────────────────────────────────────────────────────────────────────────────┘

  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
  │   PHASE 0    │    │   PHASE 1    │    │   PHASE 2    │    │   PHASE 3    │
  │  Discovery   │───▶│Specification │───▶│   Planning   │───▶│Implementation│
  │              │    │   & Design   │    │   & Setup    │    │              │
  └──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
        │                   │                   │                   │
        ▼                   ▼                   ▼                   ▼
  • Stakeholder      • PRD              • Task breakdown    • Sprint execution
    interviews       • Architecture     • Sprint planning   • Story files
  • Problem          • Specification    • Repo setup        • Code & tests
    validation       • Constitution     • CI/CD pipeline    • QA validation
  • Feasibility      • Data model       • Test plan         • Releases
    assessment       • API spec         • Quality gates     • Documentation
```

### Phase 0: Discovery & Ideation

**Purpose**: Validate the problem before designing solutions

**Key Activities**:
- Stakeholder interviews (using Five Whys, Jobs-to-be-Done)
- Problem statement creation
- Feasibility assessment (Technical, Business, Resource, Timeline)
- Risk identification

**Key Agents**: Discovery Facilitator, Feasibility Analyzer, Synthesis Agent

**Output**: Validated problem statement, feasibility report, risk register

**Gate**: GO / CONDITIONAL GO / POC / NO-GO decision

---

### Phase 1: Specification & Design

**Purpose**: Define what to build and how

**Key Activities**:
- Product requirements documentation
- System architecture design
- Technical specification with user stories
- Data model and API contract design
- Project constitution (values, constraints, decisions)

**Key Agents**: PM Agent, Architect Agent, Analyst Agent, Constitution Agent

**Output**: PRD, Architecture, Spec, Data Model, API Spec, Constitution, ADRs

**Gate**: All artifacts approved by stakeholders

---

### Phase 2: Planning & Setup

**Purpose**: Plan the work and prepare infrastructure

**Key Activities**:
- Task decomposition and estimation
- Dependency mapping
- Sprint planning
- Repository and CI/CD setup
- Test strategy and quality gates
- Team capacity planning

**Key Agents**: Planning Agent, DevOps Scaffolder, Quality Architect

**Output**: Task breakdown, sprint plan, working repository, test plan

**Gate**: Infrastructure functional, team ready, plan approved

---

### Phase 3: Implementation

**Purpose**: Execute sprints and deliver working software

**Key Activities**:
- Story file creation (self-contained context)
- Sprint execution
- Code development and testing
- QA validation
- Release management

**Key Agents**: Scrum Master, Developer, QA Engineer

**Output**: Working software, documentation, releases

**Gate**: Per-sprint DoD, release criteria

---

## The Three Tracks

### Track Selection Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         SCALE SELECTION WORKFLOW                             │
└─────────────────────────────────────────────────────────────────────────────┘
                                │
                    ┌───────────┴───────────┐
                    │  Analyze Project:     │
                    │  • Effort estimate    │
                    │  • Stakeholder count  │
                    │  • Complexity         │
                    │  • Risk/compliance    │
                    └───────────┬───────────┘
                                │
            ┌───────────────────┼───────────────────┐
            ▼                   ▼                   ▼
     ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
     │ QUICK TRACK │     │  STANDARD   │     │ ENTERPRISE  │
     │  (0-25 pts) │     │   TRACK     │     │   TRACK     │
     │             │     │ (26-60 pts) │     │ (61-100 pts)│
     └─────────────┘     └─────────────┘     └─────────────┘
           │                   │                   │
           ▼                   ▼                   ▼
     1-4 hours            2-5 days            1-3 weeks
     planning             planning            planning
```

### Quick Track

**Best For**: Bug fixes, small features, well-understood changes

**Time Budget**: 1-4 hours total planning

**Phases Used**:
- Phase 0: **SKIP**
- Phase 1: **MINIMAL** (tech-spec-lite only)
- Phase 2: **SKIP**
- Phase 3: Direct implementation

**Required Artifacts**: Tech Spec Lite only

**When to Use**:
- Effort < 2 weeks
- Requirements crystal clear
- No stakeholder alignment needed
- Low technical risk

---

### Standard Track

**Best For**: Features, small projects, moderate complexity

**Time Budget**: 2-5 days planning

**Phases Used**:
- Phase 0: **ABBREVIATED** (conversations, not formal interviews)
- Phase 1: **FULL**
- Phase 2: **STANDARD**
- Phase 3: **FULL**

**Required Artifacts**: Problem statement, PRD, Architecture, Spec, Task breakdown, Sprint plan

**When to Use**:
- Effort 2-12 weeks
- Moderate complexity
- Some stakeholder coordination needed
- Standard risk profile

---

### Enterprise Track

**Best For**: Major initiatives, complex stakeholder landscape, high stakes

**Time Budget**: 1-3 weeks planning

**Phases Used**:
- Phase 0: **FULL** (formal interviews, comprehensive discovery)
- Phase 1: **FULL** with document sharding
- Phase 2: **FULL** with cost estimation and resource planning
- Phase 3: **FULL** with comprehensive story management

**Required Artifacts**: Everything, including cost estimates, resource plans, sharded documents

**When to Use**:
- Effort 12+ weeks
- High complexity or uncertainty
- Multiple stakeholders with competing priorities
- Regulatory/compliance requirements
- Budget approval needed

---

## Quick Start

### 1. Select Your Track

```bash
# Start any new project with scale selection
"I want to start a new project. Help me determine the right track."
```

The AI will ask questions about effort, stakeholders, complexity, and risk to recommend Quick, Standard, or Enterprise track.

### 2. Follow Track-Specific Workflow

**Quick Track**:
```bash
# Load minimal resources, create tech spec
"Load Analyst Agent in lite mode. Let's create a tech spec for [description]."
```

**Standard Track**:
```bash
# Start with abbreviated discovery
"Load Discovery Facilitator in conversation mode. Let's explore the problem for [description]."
```

**Enterprise Track**:
```bash
# Start with full discovery
"Load Discovery Facilitator. Let's plan stakeholder interviews for [description]."
```

### 3. Progress Through Phases

Each phase has clear entry criteria, activities, and exit gates. The AI agents guide you through, creating artifacts and validating quality.

---

## Directory Structure

```
project-root/
├── .sdlc/                          # System primitives (shared)
│   ├── primitives/
│   │   ├── agents/phase[0-3]/      # Agent instructions by phase
│   │   ├── templates/phase[0-3]/   # Artifact templates
│   │   ├── workflows/phase[0-3]/   # Process workflows
│   │   └── checklists/             # Quality gate checklists
│   ├── config/                     # Phase and track configs
│   ├── memory/                     # Organizational knowledge
│   └── reference/                  # Documentation
│
├── phases/                         # Orchestrator phase definitions
│   ├── phase0.json                 # Discovery
│   ├── phase1.json                 # Specification
│   ├── phase2.json                 # Planning (not implementation!)
│   └── phase3.json                 # Implementation
│
└── projects/[project-name]/        # Per-project work
    ├── phase0/                     # Discovery artifacts
    ├── phase1/                     # Specification artifacts
    │   └── shards/                 # Document shards (Enterprise)
    ├── phase2/                     # Planning artifacts
    └── phase3/                     # Implementation artifacts
        └── stories/                # Story files by status
            ├── backlog/
            ├── sprint-N/
            └── completed/
```

See `reference/directory-structure.md` for complete details.

---

## Core Concepts

### Story Files

Story files are **self-contained context carriers** for implementation. Instead of developers loading multiple documents, the Scrum Master creates a story file that includes:

- User story with acceptance criteria
- **Sharded** architecture context (only relevant sections)
- Implementation guidance
- Test guidance
- Dependencies
- Lifecycle notes (SM → Dev → QA)

**Benefits**:
- Developer loads ONE file
- No context collapse across sessions
- Complete history preserved
- 90%+ token savings

### Document Sharding

For Enterprise Track, large documents are sharded by consumer need:

```
Full architecture.md (2000+ lines)
        │
        ▼
Sharded into:
├── system-overview.shard.md (always load)
├── auth-service.shard.md (load for auth stories)
├── payment-service.shard.md (load for payment stories)
└── data-model.shard.md (load for data stories)
```

Each shard is self-contained with source metadata for traceability.

### Feasibility Framework

Phase 0 produces a feasibility assessment across four dimensions:

| Dimension | Question |
|-----------|----------|
| **Technical** | Can we build this? |
| **Business** | Should we build this? |
| **Resource** | Do we have capacity? |
| **Timeline** | Can we deliver in time? |

**Outcomes**: GO, CONDITIONAL GO, POC (Proof of Concept needed), NO-GO

---

## FAQ

### Q: Do I have to use all four phases?

No! The track system lets you right-size:
- **Quick Track**: Skip Phase 0 and 2
- **Standard Track**: Abbreviated Phase 0
- **Enterprise Track**: Full methodology

### Q: What if my project changes scope mid-stream?

The track system includes escalation triggers. If complexity increases significantly, you can escalate from Quick → Standard or Standard → Enterprise.

### Q: Can I use this without the SDLCOrchestrator?

Absolutely. The framework is designed to work conversationally first. Load agent instructions, use workflows as prompts, fill in templates manually. Automation is an enhancement, not a requirement.

### Q: How do story files differ from user stories?

Traditional user stories reference external documents ("see architecture section 3.2"). Story files **embed** the relevant context, making them self-contained. Developers load one file, not five.

### Q: When should I shard documents?

Document sharding is primarily for Enterprise Track with large artifacts. If your architecture doc is under 500 lines, sharding may not be necessary.

---

## What's Your Differentiator?

Compared to other AI-SDLC approaches:

✅ **Discovery Methodology** - Comprehensive Phase 0 with structured interviews  
✅ **Cost Estimation** - Built-in cost modeling at multiple fidelity levels  
✅ **Resource Planning** - Pod design and capacity planning  
✅ **Feasibility Framework** - GO/CONDITIONAL/POC/NO GO decisions  
✅ **Organizational Memory** - Lessons learned accumulate across projects  
✅ **Enterprise/Consulting Focus** - Designed for complex stakeholder environments  

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-10-31 | Initial release (Phase 0, 1, 2) |
| 2.0 | 2025-11-15 | Added cost estimation, resource planning |
| 3.0 | 2025-12-13 | Added Phase 3 (Implementation), Three-track system, Story files, Document sharding |

---

## License

[Your license here]
