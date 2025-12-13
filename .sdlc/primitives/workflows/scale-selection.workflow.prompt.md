# Scale-Adaptive Track Selection Workflow

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Analyze project characteristics and recommend appropriate methodology track  
**Location**: `.sdlc/primitives/workflows/scale-selection.workflow.prompt.md`

---

## Overview

Not every project needs full discovery. This workflow analyzes project characteristics and recommends one of three methodology tracks, each with appropriate depth of planning, artifacts, and time investment.

### The Three Tracks

| Track | Effort Range | Planning Time | Key Artifacts | When to Use |
|-------|--------------|---------------|---------------|-------------|
| **Quick** | < 2 weeks | 1-4 hours | Tech spec only | Bug fixes, small features, well-understood changes |
| **Standard** | 2-12 weeks | 2-5 days | Problem statement, PRD, Architecture | Features, small projects, moderate complexity |
| **Enterprise** | 12+ weeks | 1-3 weeks | Full Phase 0/1/2 artifacts, cost estimates, pod design | Major initiatives, high stakes, complex stakeholder landscape |

---

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                    SCALE SELECTION WORKFLOW                      │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Gather Project Info  │
                 │  - Effort estimate       │
                 │  - Stakeholder count     │
                 │  - Technical complexity  │
                 │  - Risk/compliance needs │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  2. Calculate Complexity │
                 │     Score (0-100)        │
                 │  - Weighted factors      │
                 │  - Override conditions   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  3. Determine Track      │
                 │  - Quick (0-25)          │
                 │  - Standard (26-60)      │
                 │  - Enterprise (61-100)   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Present              │
                 │     Recommendation       │
                 │  - Track + rationale     │
                 │  - Override option       │
                 │  - Artifact checklist    │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. Load Track-Specific  │
                 │     Resources            │
                 │  - Agents                │
                 │  - Templates             │
                 │  - Workflows             │
                 └──────────────────────────┘
```

---

## Step 1: Gather Project Information

### Agent: Any (This is a meta-workflow)

### 1.1 Initial Assessment Questions

Ask the following questions to understand project scope:

```markdown
## Project Scale Assessment

I'll help you determine the right level of planning for your project. 
Please answer these questions:

### Effort & Duration

1. **Estimated effort**: How much development time do you expect?
   - [ ] Less than 1 week
   - [ ] 1-2 weeks
   - [ ] 2-4 weeks
   - [ ] 1-3 months
   - [ ] 3-6 months
   - [ ] 6+ months
   - [ ] Unknown/Uncertain

2. **Timeline pressure**: What's the deadline situation?
   - [ ] Urgent (ASAP, within days)
   - [ ] Near-term (within 2-4 weeks)
   - [ ] Planned (1-3 months out)
   - [ ] Strategic (3+ months, flexible)

### Stakeholder Complexity

3. **Decision makers**: How many people need to approve this work?
   - [ ] 1 (just me or my direct manager)
   - [ ] 2-3 people
   - [ ] 4-6 people
   - [ ] 7+ people or multiple committees

4. **Stakeholder alignment**: How aligned are stakeholders on what's needed?
   - [ ] Fully aligned - everyone agrees
   - [ ] Mostly aligned - minor differences
   - [ ] Partially aligned - some disagreement
   - [ ] Not aligned - significant conflicts
   - [ ] Unknown - haven't discussed yet

5. **User groups affected**: How many distinct user groups will this impact?
   - [ ] 1 group
   - [ ] 2-3 groups
   - [ ] 4-5 groups
   - [ ] 6+ groups

### Technical Complexity

6. **System familiarity**: How well do you understand the systems involved?
   - [ ] Expert - I built/maintain these systems
   - [ ] Familiar - I've worked with them before
   - [ ] Some knowledge - I know the basics
   - [ ] Limited - I'll need to learn
   - [ ] Unknown - new territory

7. **Integration points**: How many external systems does this touch?
   - [ ] 0 - Self-contained
   - [ ] 1-2 systems
   - [ ] 3-5 systems
   - [ ] 6+ systems

8. **Data complexity**: What's the data situation?
   - [ ] Simple - CRUD operations on existing models
   - [ ] Moderate - New models or moderate transformations
   - [ ] Complex - Migrations, multiple data sources, complex transformations
   - [ ] Very complex - Data warehouse, ML pipelines, regulatory data

### Risk & Compliance

9. **Business criticality**: What happens if this fails?
   - [ ] Minor inconvenience
   - [ ] Noticeable impact, workarounds exist
   - [ ] Significant business impact
   - [ ] Critical - major revenue/reputation risk

10. **Regulatory/Compliance**: Are there compliance requirements?
    - [ ] None
    - [ ] Standard (SOC2, basic security)
    - [ ] Significant (HIPAA, PCI, GDPR)
    - [ ] Heavy (FedRAMP, financial regulations, healthcare)

11. **Security sensitivity**: How sensitive is the data/functionality?
    - [ ] Public/Non-sensitive
    - [ ] Internal/Confidential
    - [ ] Highly sensitive (PII, financial, health)
    - [ ] Critical (secrets, authentication, payment)

### Problem Clarity

12. **Problem definition**: How well-defined is the problem?
    - [ ] Crystal clear - we know exactly what to build
    - [ ] Mostly clear - some details to work out
    - [ ] Partially clear - we know the goal but not the path
    - [ ] Unclear - we know something's wrong but not what
    - [ ] Exploratory - we're investigating possibilities

13. **Solution approach**: Do you know how to solve this?
    - [ ] Yes - clear technical approach
    - [ ] Mostly - need to validate a few things
    - [ ] Partially - several options to evaluate
    - [ ] No - need significant research/discovery
```

---

## Step 2: Calculate Complexity Score

### 2.1 Scoring Matrix

Each answer maps to a score. Sum all scores to get complexity rating.

```markdown
## Scoring Guide

### Effort & Duration (Max 25 points)

| Answer | Points |
|--------|--------|
| Less than 1 week | 0 |
| 1-2 weeks | 5 |
| 2-4 weeks | 10 |
| 1-3 months | 15 |
| 3-6 months | 20 |
| 6+ months | 25 |
| Unknown/Uncertain | 15 (assume medium-high) |

### Timeline Pressure (Max 5 points)

| Answer | Points |
|--------|--------|
| Urgent | 0 (forces Quick track) |
| Near-term | 2 |
| Planned | 4 |
| Strategic | 5 |

### Decision Makers (Max 10 points)

| Answer | Points |
|--------|--------|
| 1 person | 0 |
| 2-3 people | 3 |
| 4-6 people | 7 |
| 7+ people | 10 |

### Stakeholder Alignment (Max 10 points)

| Answer | Points |
|--------|--------|
| Fully aligned | 0 |
| Mostly aligned | 2 |
| Partially aligned | 5 |
| Not aligned | 8 |
| Unknown | 10 |

### User Groups (Max 5 points)

| Answer | Points |
|--------|--------|
| 1 group | 0 |
| 2-3 groups | 2 |
| 4-5 groups | 4 |
| 6+ groups | 5 |

### System Familiarity (Max 5 points)

| Answer | Points |
|--------|--------|
| Expert | 0 |
| Familiar | 1 |
| Some knowledge | 3 |
| Limited | 4 |
| Unknown | 5 |

### Integration Points (Max 10 points)

| Answer | Points |
|--------|--------|
| 0 - Self-contained | 0 |
| 1-2 systems | 3 |
| 3-5 systems | 7 |
| 6+ systems | 10 |

### Data Complexity (Max 5 points)

| Answer | Points |
|--------|--------|
| Simple | 0 |
| Moderate | 2 |
| Complex | 4 |
| Very complex | 5 |

### Business Criticality (Max 10 points)

| Answer | Points |
|--------|--------|
| Minor inconvenience | 0 |
| Noticeable impact | 3 |
| Significant impact | 7 |
| Critical | 10 |

### Regulatory/Compliance (Max 10 points)

| Answer | Points |
|--------|--------|
| None | 0 |
| Standard | 3 |
| Significant | 7 |
| Heavy | 10 |

### Security Sensitivity (Max 5 points)

| Answer | Points |
|--------|--------|
| Public/Non-sensitive | 0 |
| Internal/Confidential | 2 |
| Highly sensitive | 4 |
| Critical | 5 |

### Problem Definition (Max 10 points)

| Answer | Points |
|--------|--------|
| Crystal clear | 0 |
| Mostly clear | 2 |
| Partially clear | 5 |
| Unclear | 8 |
| Exploratory | 10 |

### Solution Approach (Max 5 points)

| Answer | Points |
|--------|--------|
| Yes - clear | 0 |
| Mostly | 1 |
| Partially | 3 |
| No | 5 |
```

### 2.2 Override Conditions

Certain conditions automatically escalate or de-escalate the track:

```markdown
## Automatic Track Overrides

### Force Enterprise Track (regardless of score)
- [ ] Regulatory compliance is "Heavy" (FedRAMP, financial, healthcare)
- [ ] 7+ decision makers involved
- [ ] Effort is 6+ months
- [ ] Problem definition is "Unclear" or "Exploratory" AND Business criticality is "Significant" or "Critical"
- [ ] Cost estimate required by stakeholders
- [ ] External client/customer facing

### Force Quick Track (regardless of score)
- [ ] Timeline is "Urgent" AND effort is < 2 weeks
- [ ] Problem is "Crystal clear" AND solution is "Yes - clear" AND effort < 1 week

### Prevent Quick Track (minimum Standard)
- [ ] Stakeholder alignment is "Not aligned" or "Unknown"
- [ ] 4+ decision makers
- [ ] Security sensitivity is "Critical"
- [ ] Any regulatory compliance beyond "None"
```

---

## Step 3: Determine Track

### 3.1 Score Thresholds

```markdown
## Track Selection

| Score Range | Track | Description |
|-------------|-------|-------------|
| 0-25 | **Quick** | Fast-track for well-understood, low-risk changes |
| 26-60 | **Standard** | Balanced approach for typical projects |
| 61-100 | **Enterprise** | Full methodology for complex, high-stakes initiatives |

**After Override Application:**
- Check override conditions
- Apply any forced escalations/de-escalations
- Present final recommendation with rationale
```

### 3.2 Track Definitions

#### Quick Track

```markdown
## Quick Track

**Best For**: Bug fixes, small features, well-understood changes, < 2 weeks effort

**Time Investment**: 1-4 hours planning

### Phases Used
- Phase 0: **SKIP** (no formal discovery)
- Phase 1: **MINIMAL** (tech spec only)
- Phase 2: **SKIP** (straight to implementation)

### Required Artifacts
1. `tech-spec-lite.md` - Lightweight technical specification
   - Problem summary (2-3 sentences)
   - Proposed solution (bullet points)
   - Implementation approach
   - Testing approach
   - Risks/concerns

### Optional Artifacts
- Architecture impact assessment (if touching shared components)
- Rollback plan (if production change)

### Agents to Load
- Analyst Agent (lite mode) - for tech spec creation
- Developer Agent - for implementation

### Skip These
- Discovery Facilitator
- Feasibility Analyzer
- Cost Estimator
- Resource Planner
- PM Agent (full PRD not needed)
- Constitution Agent

### Quality Gates
- [ ] Tech spec reviewed by technical lead
- [ ] Implementation approach validated
- [ ] Tests identified
```

#### Standard Track

```markdown
## Standard Track

**Best For**: Features, small-to-medium projects, 2-12 weeks effort

**Time Investment**: 2-5 days planning

### Phases Used
- Phase 0: **ABBREVIATED** (2-3 stakeholder conversations, no formal interviews)
- Phase 1: **FULL** (PRD, Architecture, Constitution)
- Phase 2: **STANDARD** (task breakdown, sprint planning)

### Required Artifacts

**Phase 0 (Abbreviated)**:
1. `problem-statement.md` - Problem definition with basic root cause
2. `stakeholder-input.md` - Summary of stakeholder conversations (not full transcripts)
3. `feasibility-quick.md` - Quick feasibility check (1 page)

**Phase 1 (Full)**:
1. `prd.md` - Product Requirements Document
2. `architecture.md` - System architecture
3. `constitution.md` - Project constitution and constraints
4. `spec.md` - Technical specification with user stories

**Phase 2 (Standard)**:
1. `task-breakdown.md` - Task decomposition
2. `sprint-plan.md` - Sprint planning

### Optional Artifacts
- Cost estimate (if budget is a concern)
- Risk register (if elevated risk)
- Data model (if significant data changes)

### Agents to Load
- Discovery Facilitator (conversation mode, not interview mode)
- Feasibility Analyzer (quick assessment mode)
- Analyst Agent
- PM Agent
- Architect Agent
- Constitution Agent
- Validator Agent
- Planning Agent

### Quality Gates
- [ ] Problem statement validated with key stakeholders
- [ ] Feasibility confirmed (GO or CONDITIONAL GO)
- [ ] PRD approved by product owner
- [ ] Architecture reviewed by technical lead
- [ ] Sprint plan accepted by team
```

#### Enterprise Track

```markdown
## Enterprise Track

**Best For**: Major initiatives, complex stakeholder landscape, 12+ weeks effort, high stakes

**Time Investment**: 1-3 weeks planning

### Phases Used
- Phase 0: **FULL** (complete discovery with structured interviews)
- Phase 1: **FULL** (all artifacts with detailed validation)
- Phase 2: **FULL** (comprehensive planning with cost/resource estimation)

### Required Artifacts

**Phase 0 (Full Discovery)**:
1. `problem-statement.md` - Comprehensive problem definition with Five Whys
2. `interviews/*.md` - Full interview transcripts (5-11+ stakeholders)
3. `feasibility-report.md` - Four-dimension feasibility assessment
4. `risk-register.md` - Identified risks with mitigations
5. `success-criteria.md` - Measurable success criteria
6. `constraints.md` - Technical, business, regulatory constraints
7. `stakeholder-alignment.md` - Stakeholder analysis and alignment status

**Phase 1 (Full Specification)**:
1. `prd.md` - Comprehensive PRD
2. `architecture.md` - Detailed architecture with C4 diagrams
3. `constitution.md` - Project constitution
4. `spec.md` - Technical specification
5. `data-model.md` - Data architecture
6. `api-spec.json` - API specifications (if applicable)
7. `adrs/*.md` - Architecture Decision Records

**Phase 2 (Full Planning)**:
1. `cost-estimate.md` - ROM and detailed cost estimates
2. `resource-plan.md` - Pod structure and staffing plan
3. `task-breakdown.md` - Comprehensive task decomposition
4. `sprint-plan.md` - Multi-sprint planning
5. `dependency-map.md` - Task dependencies
6. `test-plan.md` - Testing strategy
7. `repository-structure.md` - Code organization
8. `environment-config.md` - Infrastructure setup

### Agents to Load (All)
- Discovery Facilitator
- Feasibility Analyzer
- Synthesis Agent
- Analyst Agent
- PM Agent
- Architect Agent
- Constitution Agent
- Validator Agent
- Cost Estimator
- Resource Planner
- Planning Agent
- DevOps Scaffolder
- Quality Architect

### Quality Gates
- [ ] Discovery completion checklist passed
- [ ] Feasibility GO or CONDITIONAL GO (with mitigations)
- [ ] All Phase 0 artifacts approved by stakeholders
- [ ] Phase 1 validation complete
- [ ] Cost estimate within acceptable range
- [ ] Resource plan validated
- [ ] All Phase 2 artifacts approved
- [ ] Steering committee sign-off (if applicable)
```

---

## Step 4: Present Recommendation

### 4.1 Recommendation Template

```markdown
## Scale Selection Recommendation

**Project**: [Project Name]
**Date**: [Date]
**Assessed By**: [Name/Agent]

### Complexity Score: [X]/100

**Score Breakdown**:
| Factor | Score | Max |
|--------|-------|-----|
| Effort & Duration | [X] | 25 |
| Timeline Pressure | [X] | 5 |
| Decision Makers | [X] | 10 |
| Stakeholder Alignment | [X] | 10 |
| User Groups | [X] | 5 |
| System Familiarity | [X] | 5 |
| Integration Points | [X] | 10 |
| Data Complexity | [X] | 5 |
| Business Criticality | [X] | 10 |
| Regulatory/Compliance | [X] | 10 |
| Security Sensitivity | [X] | 5 |
| Problem Definition | [X] | 10 |
| Solution Approach | [X] | 5 |
| **Total** | **[X]** | **100** |

### Override Conditions
- [List any override conditions that applied]
- [Or "None" if no overrides]

### Recommended Track: [QUICK / STANDARD / ENTERPRISE]

**Rationale**:
[2-3 sentences explaining why this track is appropriate]

### Key Factors Driving This Recommendation
1. [Factor 1]
2. [Factor 2]
3. [Factor 3]

### Alternative Consideration
[If score is near a boundary, mention the adjacent track and when to consider it]

---

## Override Option

You may choose a different track if you believe the assessment doesn't capture 
important factors. Common reasons to override:

**Escalate to higher track**:
- Political sensitivity not captured in questions
- Previous project failures in this area
- New team with no organizational knowledge
- External client expectations

**De-escalate to lower track**:
- Similar project completed recently (can reuse artifacts)
- Proof-of-concept, not production
- Throwaway/experimental work

**Your choice**: [ ] Accept recommendation  [ ] Override to: ____________

---

## Next Steps

Based on [TRACK] track, here's what to do next:

[Track-specific next steps - see Step 5]
```

---

## Step 5: Load Track-Specific Resources

### 5.1 Resource Loading Guide

```markdown
## Resource Loading by Track

### Quick Track Resources

**Load These Files**:
```
.sdlc/primitives/agents/phase1/analyst-agent_instructions.md (lite sections only)
.sdlc/primitives/templates/phase1/tech-spec-lite_template.md
.sdlc/config/quick-track_config.md
```

**Create Project Structure**:
```bash
mkdir -p projects/[project-name]/{working,artifacts}
# No phase subdirectories needed
```

**Start Command**:
"Load the Analyst Agent in lite mode. We're using Quick Track for a 
[brief description]. Let's create a tech spec."

---

### Standard Track Resources

**Load These Files**:
```
# Phase 0 (Abbreviated)
.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md
.sdlc/primitives/templates/phase0/problem-statement_template.md
.sdlc/primitives/templates/phase0/feasibility-quick_template.md

# Phase 1 (Full)
.sdlc/primitives/agents/phase1/analyst-agent_instructions.md
.sdlc/primitives/agents/phase1/pm-agent_instructions.md
.sdlc/primitives/agents/phase1/architect-agent_instructions.md
.sdlc/primitives/agents/phase1/constitution-agent_instructions.md
.sdlc/primitives/agents/phase1/validator-agent_instructions.md
.sdlc/primitives/templates/phase1/*.md

# Phase 2 (Standard)
.sdlc/primitives/agents/phase2/planning-agent_instructions.md
.sdlc/primitives/templates/phase2/task-breakdown_template.md
.sdlc/primitives/templates/phase2/sprint-plan_template.md

# Config
.sdlc/config/standard-track_config.md
```

**Create Project Structure**:
```bash
mkdir -p projects/[project-name]/phase0/{working,artifacts}
mkdir -p projects/[project-name]/phase1/{working,artifacts,adrs}
mkdir -p projects/[project-name]/phase2/{working,artifacts}
```

**Start Command**:
"Load the Discovery Facilitator in conversation mode. We're using Standard 
Track for [brief description]. Let's start with problem exploration - I'll 
share what I know from stakeholder conversations."

---

### Enterprise Track Resources

**Load These Files**:
```
# All Phase 0
.sdlc/primitives/agents/phase0/*.md
.sdlc/primitives/templates/phase0/*.md
.sdlc/primitives/workflows/phase0/*.md
.sdlc/primitives/checklists/phase-0-completion_checklist.md

# All Phase 1
.sdlc/primitives/agents/phase1/*.md
.sdlc/primitives/templates/phase1/*.md
.sdlc/primitives/workflows/phase1/*.md
.sdlc/primitives/checklists/phase-1-completion_checklist.md

# All Phase 2
.sdlc/primitives/agents/phase2/*.md
.sdlc/primitives/templates/phase2/*.md
.sdlc/primitives/workflows/phase2/*.md
.sdlc/primitives/checklists/phase-2-completion_checklist.md

# Memory
.sdlc/memory/*.md

# Config
.sdlc/config/enterprise-track_config.md
.sdlc/config/phase0_config.md
.sdlc/config/phase1_config.md
.sdlc/config/phase2_config.md
```

**Create Project Structure**:
```bash
mkdir -p projects/[project-name]/phase0/{interviews,working,artifacts,validation}
mkdir -p projects/[project-name]/phase1/{working,artifacts,adrs,validation}
mkdir -p projects/[project-name]/phase2/{working,artifacts,sprints,validation}
```

**Start Command**:
"Load the Discovery Facilitator. We're using Enterprise Track for [brief 
description]. Let's begin with the full discovery workflow - starting with 
stakeholder identification and interview planning."
```

---

## Quick Reference Card

```markdown
┌─────────────────────────────────────────────────────────────────────────┐
│                    SCALE SELECTION QUICK REFERENCE                       │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  QUICK TRACK (Score 0-25)                                               │
│  ─────────────────────────                                              │
│  • Effort: < 2 weeks          • Planning: 1-4 hours                     │
│  • Artifacts: Tech spec only  • Phases: Skip 0, Minimal 1, Skip 2       │
│  • Use for: Bug fixes, small features, clear requirements               │
│                                                                          │
│  STANDARD TRACK (Score 26-60)                                           │
│  ────────────────────────────                                           │
│  • Effort: 2-12 weeks         • Planning: 2-5 days                      │
│  • Artifacts: PRD + Arch      • Phases: Abbreviated 0, Full 1, Standard 2│
│  • Use for: Features, small projects, moderate complexity               │
│                                                                          │
│  ENTERPRISE TRACK (Score 61-100)                                        │
│  ───────────────────────────────                                        │
│  • Effort: 12+ weeks          • Planning: 1-3 weeks                     │
│  • Artifacts: Everything      • Phases: Full 0, Full 1, Full 2          │
│  • Use for: Major initiatives, high stakes, complex stakeholders        │
│                                                                          │
├─────────────────────────────────────────────────────────────────────────┤
│  FORCE ENTERPRISE: Compliance heavy │ 7+ approvers │ 6+ months │        │
│                     Problem unclear + Critical business impact           │
│                                                                          │
│  FORCE QUICK: Urgent + < 2 weeks │ Crystal clear + Expert + < 1 week    │
│                                                                          │
│  MINIMUM STANDARD: Stakeholders misaligned │ 4+ approvers │             │
│                    Critical security │ Any compliance                    │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## Integration Notes

### With Orchestrator

If using the SDLCOrchestrator, the scale selection can be automated:

```json
{
  "scaleSelection": {
    "enabled": true,
    "defaultTrack": "Standard",
    "allowOverride": true,
    "autoDetect": {
      "enabled": true,
      "factors": ["effort", "stakeholders", "compliance", "problemClarity"]
    }
  }
}
```

### With Manual Workflow

For conversational use, run this workflow at the start of any new project:

```
User: I want to start a new project. [Brief description]

Agent: Before we dive in, let me help you select the right planning depth.
       I'll ask you a few questions to understand the project scope...
       [Runs scale selection workflow]
       
       Based on your answers, I recommend [TRACK] track because [rationale].
       Would you like to proceed with this track or adjust?
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
