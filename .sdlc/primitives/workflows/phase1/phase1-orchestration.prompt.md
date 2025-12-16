# Phase 1 Orchestration Workflow

**Purpose**: This workflow orchestrates the complete Phase 1 specification and design process, coordinating all Phase 1 agents to produce validated artifacts ready for Phase 2.

**Version**: 1.0  
**Last Updated**: 2025-12-15  
**Location**: `.sdlc/primitives/workflows/phase1/phase1-orchestration.prompt.md`

---

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│              Phase 1: Specification & Design                     │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  0. Phase 1 Kickoff      │
                 │  - Load Phase 0 outputs  │
                 │  - Set up workspace      │
                 │  - Confirm scope         │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Constitution         │
                 │  (Constitution Agent)    │
                 │  - Project principles    │
                 │  - Quality standards     │
                 │  - Constraints           │
                 └──────────────────────────┘
                                │
                ┌───────────────┴───────────────┐
                ▼                               ▼
     ┌──────────────────┐           ┌──────────────────┐
     │  2a. Specification│          │  2b. PRD         │
     │  (Analyst Agent) │           │  (PM Agent)      │
     │  - Requirements  │           │  - Vision        │
     │  - User stories  │           │  - Priorities    │
     │  - Business rules│           │  - MVP scope     │
     └──────────────────┘           └──────────────────┘
                │                               │
                └───────────────┬───────────────┘
                                ▼
                 ┌──────────────────────────┐
                 │  3. Architecture         │
                 │  (Architect Agent)       │
                 │  - System design         │
                 │  - Data model            │
                 │  - API specification     │
                 │  - ADRs                  │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Validation           │
                 │  (Validator Agent)       │
                 │  - Completeness          │
                 │  - Consistency           │
                 │  - Traceability          │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. Stakeholder Review   │
                 │  - Review artifacts      │
                 │  - Address feedback      │
                 │  - Obtain approval       │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  Ready for Phase 2       │
                 │  (Planning & Setup)      │
                 └──────────────────────────┘
```

---

## Phase 1 Agents & Workflows

| Step | Agent | Chatmode | Estimated Time | Output Artifacts |
|------|-------|----------|----------------|------------------|
| 1 | Constitution Agent | - | 2-4 hours | `constitution.md` |
| 2a | Analyst Agent | `analyst.chatmode.md` | 1-2 days | `spec.md` |
| 2b | PM Agent | `pm.chatmode.md` | 1-2 days | `prd.md` |
| 3 | Architect Agent | `architect.chatmode.md` | 2-3 days | `architecture.md`, `data-model.md`, `api-spec.json`, ADRs |
| 4 | Validator Agent | `validator.chatmode.md` | 4-6 hours | `validation-report.md` |
| 5 | Human | - | 1-2 days | Stakeholder approvals |

**Total Phase 1 Duration**: 6-10 days (varies by project complexity)

---

## Session Strategy

Phase 1 should use **focused sessions** to prevent context collapse:

1. **Foundation Session** (Constitution creation)
2. **Requirements Sessions** (Specification development - may be multiple)
3. **Product Sessions** (PRD development - may be multiple)
4. **Architecture Sessions** (Architecture, data model, API - likely multiple)
5. **Validation Session** (Comprehensive validation)
6. **Review Sessions** (Stakeholder feedback incorporation)

**Session Splitting Guidelines**:
- Maximum 3-4 hours per session
- One primary focus per session
- Save and reload context between sessions
- Use `phase1-context.md` to track state

---

## Step 0: Phase 1 Kickoff

### Objective
Set up Phase 1 workspace and confirm readiness to proceed.

### Prerequisites
- Phase 0 complete (if used) OR project scope defined
- Problem statement available
- Stakeholders identified
- Timeline agreed

### Actions

#### 0.1 Create Phase 1 Workspace

```bash
# Create Phase 1 directory structure
mkdir -p projects/[project-name]/phase1/{working,artifacts,adrs,validation}

# Copy templates
cp .sdlc/primitives/templates/phase1/*.md projects/[project-name]/phase1/working/

# Create phase context file
touch projects/[project-name]/phase1/phase1-context.md
```

#### 0.2 Load Inputs

**If coming from Phase 0**, load:
- `phase0/artifacts/problem-statement.md`
- `phase0/artifacts/feasibility-report.md`
- `phase0/artifacts/success-criteria.md`
- `phase0/artifacts/constraints.md`
- `phase0/artifacts/risk-register.md`

**If starting fresh** (Phase 1 standalone), gather:
- Problem/opportunity description
- Scope boundaries
- Known constraints
- Key stakeholders
- Timeline expectations

#### 0.3 Load Organizational Context

Load memory files:
- `.sdlc/memory/organization_context.md`
- `.sdlc/memory/technical-stack_context.md`
- `.sdlc/memory/prior-projects_memory.md`
- `.sdlc/memory/lessons-learned_memory.md`

#### 0.4 Initialize Phase 1 Context

Create `phase1-context.md`:

```markdown
# Phase 1 Context - [Project Name]

## Current State

**Phase Status**: Step 0 - Kickoff
**Last Updated**: [Date]
**Current Session**: [N]

## Inputs Loaded

**From Phase 0** (or equivalent):
- [ ] Problem statement
- [ ] Feasibility assessment
- [ ] Success criteria
- [ ] Constraints
- [ ] Risk register

**Organizational Context**:
- [ ] Organization context
- [ ] Technical stack
- [ ] Prior projects (relevant)
- [ ] Lessons learned (relevant)

## Artifacts Status

| Artifact | Status | Version | Last Updated | Owner |
|----------|--------|---------|--------------|-------|
| Constitution | Not Started | - | - | Constitution Agent |
| Specification | Not Started | - | - | Analyst Agent |
| PRD | Not Started | - | - | PM Agent |
| Architecture | Not Started | - | - | Architect Agent |
| Data Model | Not Started | - | - | Architect Agent |
| API Spec | Not Started | - | - | Architect Agent |
| Validation Report | Not Started | - | - | Validator Agent |

## Key Decisions

[Track key decisions as they're made]

## Open Questions

[Track questions needing resolution]

## Next Steps

1. Begin Step 1: Constitution creation
```

#### 0.5 Confirm Scope

Before proceeding, verify:
- [ ] Problem/opportunity clearly understood
- [ ] Success criteria defined
- [ ] Constraints identified
- [ ] Key stakeholders listed
- [ ] Timeline agreed
- [ ] Team ready to proceed

**Decision Point**: Ready for Step 1?
- ✅ Yes → Proceed to Constitution
- ❌ No → Resolve blockers first

---

## Step 1: Constitution Creation (Constitution Agent)

### Objective
Establish project principles, quality standards, and constraints that guide all other work.

### Agent: Constitution Agent
Load: `.sdlc/primitives/agents/phase1/constitution-agent_instructions.md`

### Time Required
2-4 hours

### Context to Provide

```markdown
## Context for Constitution Agent

You are creating the Project Constitution for [Project Name].

**Inputs**:
- Problem Statement: [Summary or paste]
- Constraints: [From Phase 0 or kickoff]
- Success Criteria: [From Phase 0 or kickoff]
- Organizational Standards: [From memory files]

**Your Mission**: Create a constitution that serves as the project's 
"north star" - guiding all technical and product decisions.

**Sections to Create**:
1. Project Vision & Objectives
2. Core Principles (non-negotiable values)
3. Quality Standards
4. Technical Constraints
5. Process Standards
6. Definition of Done
7. Anti-patterns to Avoid
8. Decision-Making Framework
9. Success Metrics
10. Glossary

**Quality Standards**: Align with organizational standards while 
addressing project-specific needs.
```

### Deliverable
- `artifacts/constitution.md` - Comprehensive project constitution

### Validation
- [ ] Vision is clear and inspiring
- [ ] Principles are actionable, not vague
- [ ] Quality standards are measurable
- [ ] Constraints are realistic
- [ ] Success metrics are testable
- [ ] Stakeholders can use this for decision-making

**Update Phase 1 Context**: Mark constitution as complete, note version.

---

## Step 2a: Requirements Specification (Analyst Agent)

### Objective
Transform problem statement into detailed requirements with acceptance criteria.

### Agent: Analyst Agent
Load: `.sdlc/primitives/agents/phase1/analyst-agent_instructions.md`

### Chatmode
Use: `analyst.chatmode.md` for interactive sessions

### Time Required
1-2 days (multiple sessions)

### Context to Provide

```markdown
## Context for Analyst Agent

You are creating the Requirements Specification for [Project Name].

**Inputs**:
- Constitution: [Load constitution.md]
- Problem Statement: [From Phase 0 or kickoff]
- Success Criteria: [From Phase 0 or kickoff]
- Constraints: [From Phase 0 or constitution]

**Your Mission**: Create comprehensive requirements that fully 
address the problem statement while respecting the constitution.

**Sections to Create**:
1. Executive Summary
2. Scope (In/Out)
3. Glossary
4. User Roles & Permissions
5. Functional Requirements (FR-XXX format)
6. Non-Functional Requirements (NFR-XXX format)
7. Business Rules
8. Integration Requirements
9. Data Requirements
10. Assumptions & Constraints
11. Success Metrics

**Quality Standards**:
- Every requirement must be testable
- Use INVEST principles for user stories
- Include acceptance criteria for all FRs
- NFRs must be measurable
- Trace all requirements to problem statement
```

### Deliverable
- `artifacts/spec.md` - Complete requirements specification

### Validation
- [ ] All functional requirements have acceptance criteria
- [ ] Non-functional requirements are measurable
- [ ] Business rules are clear
- [ ] Requirements trace to problem statement
- [ ] No ambiguous language
- [ ] INVEST principles applied to stories
- [ ] Integration points identified

**Update Phase 1 Context**: Mark specification as complete, note version.

---

## Step 2b: Product Requirements Document (PM Agent)

### Objective
Create product vision, prioritize features, and define MVP scope.

### Agent: PM Agent
Load: `.sdlc/primitives/agents/phase1/pm-agent_instructions.md`

### Chatmode
Use: `pm.chatmode.md` for interactive sessions

### Time Required
1-2 days (can run parallel with Step 2a)

### Context to Provide

```markdown
## Context for PM Agent

You are creating the Product Requirements Document for [Project Name].

**Inputs**:
- Constitution: [Load constitution.md]
- Specification: [Load spec.md - partial is OK]
- Problem Statement: [From Phase 0 or kickoff]
- Success Criteria: [From Phase 0 or kickoff]

**Your Mission**: Create a product strategy that prioritizes 
features, defines MVP, and provides a roadmap.

**Sections to Create**:
1. Product Vision
2. User Personas
3. User Journey Maps
4. Feature List with Priorities
5. MVP Definition
6. Feature Prioritization (RICE or MoSCoW)
7. Product Roadmap
8. Success Metrics
9. Competitive Context (if relevant)
10. Go-to-Market Considerations (if relevant)

**Prioritization Framework**: Use [RICE / MoSCoW - per constitution]
```

### Deliverable
- `artifacts/prd.md` - Complete product requirements document

### Validation
- [ ] Vision is compelling
- [ ] Personas are realistic
- [ ] Priorities are justified
- [ ] MVP is clearly defined
- [ ] Roadmap is realistic
- [ ] Success metrics align with constitution

**Update Phase 1 Context**: Mark PRD as complete, note version.

---

## Step 3: Architecture Design (Architect Agent)

### Objective
Design system architecture, data model, and API contracts.

### Agent: Architect Agent
Load: `.sdlc/primitives/agents/phase1/architect-agent_instructions.md`

### Chatmode
Use: `architect.chatmode.md` for interactive sessions

### Time Required
2-3 days (multiple sessions)

### Context to Provide

```markdown
## Context for Architect Agent

You are designing the system architecture for [Project Name].

**Inputs**:
- Constitution: [Load constitution.md]
- Specification: [Load spec.md]
- PRD: [Load prd.md]
- Technical Stack: [From memory files]
- Organizational Standards: [From memory files]

**Your Mission**: Design a system architecture that satisfies all 
requirements while respecting constraints and quality standards.

**Deliverables**:
1. Architecture Document (architecture.md)
   - System overview and context
   - Component architecture
   - Communication patterns
   - Technology stack decisions
   - Security architecture
   - Scalability strategy
   - Deployment architecture

2. Data Model (data-model.md)
   - Entity definitions
   - Relationships
   - Indexes
   - Data retention

3. API Specification (api-spec.json)
   - Endpoints
   - Request/response formats
   - Authentication
   - Versioning

4. Architecture Decision Records (ADRs)
   - Key decisions with rationale

**Quality Standards**:
- Meet all NFRs from specification
- Align with constitution principles
- Follow organizational standards
```

### Sessions

Break architecture work into focused sessions:

**Session 3.1**: High-level architecture
- System context diagram
- Component identification
- Technology selection

**Session 3.2**: Data architecture
- Entity relationship design
- Database selection
- Data flow

**Session 3.3**: API design
- Endpoint definition
- Request/response design
- Authentication approach

**Session 3.4**: Infrastructure and deployment
- Deployment architecture
- Scalability approach
- Security measures

### Deliverables
- `artifacts/architecture.md` - System architecture document
- `artifacts/data-model.md` - Data model and schema
- `artifacts/api-spec.json` - OpenAPI specification
- `adrs/001-[decision].md`, `adrs/002-[decision].md`, etc.

### Validation
- [ ] All NFRs addressed in architecture
- [ ] Data model supports all data requirements
- [ ] API covers all functional requirements
- [ ] Technology choices justified (ADRs)
- [ ] Scalability approach defined
- [ ] Security approach defined
- [ ] Constitution standards met

**Update Phase 1 Context**: Mark architecture artifacts as complete.

---

## Step 4: Comprehensive Validation (Validator Agent)

### Objective
Validate all Phase 1 artifacts for completeness, consistency, and traceability.

### Agent: Validator Agent
Load: `.sdlc/primitives/agents/phase1/validator-agent_instructions.md`

### Chatmode
Use: `validator.chatmode.md` for validation session

### Time Required
4-6 hours

### Context to Provide

```markdown
## Context for Validator Agent

You are performing comprehensive validation of Phase 1 artifacts.

**All Artifacts to Load**:
- constitution.md
- spec.md
- prd.md
- architecture.md
- data-model.md
- api-spec.json
- All ADRs

**Also Load**:
- Phase 0 outputs (problem statement, success criteria, constraints)
- Phase 1 completion checklist

**Validation Dimensions**:
1. Completeness - All required sections present
2. Consistency - No contradictions within or between artifacts
3. Traceability - Everything traces to Phase 0/problem statement
4. Quality - Meets constitution standards
5. Feasibility - Architecture is implementable
6. Phase 2 Readiness - Enough detail for planning

**Your Output**: Comprehensive validation report
```

### Validation Process

1. **Individual Artifact Review**
   - Check each artifact against its template
   - Verify all sections complete
   - Check quality standards met

2. **Cross-Artifact Consistency**
   - Requirements in spec → Features in PRD
   - Requirements in spec → Components in architecture
   - Data requirements → Data model
   - API requirements → API spec

3. **Traceability Check**
   - Problem statement → Requirements
   - Requirements → Architecture
   - Success criteria → Measurable outcomes

4. **Phase 2 Readiness Assessment**
   - Enough detail to decompose into tasks?
   - Unknowns identified?
   - Risks documented?

### Deliverable
- `validation/phase1-validation-report.md`

### Validation Report Structure

```markdown
# Phase 1 Validation Report

## Executive Summary
- Overall Status: [PASS / CONDITIONAL PASS / FAIL]
- Phase 2 Readiness: [Ready / Conditionally Ready / Not Ready]
- Critical Issues: [Count]
- Major Issues: [Count]
- Minor Issues: [Count]

## Artifact-by-Artifact Assessment

### Constitution
- Completeness: [Score/10]
- Issues: [List]

### Specification
- Completeness: [Score/10]
- Issues: [List]

[Continue for each artifact]

## Cross-Artifact Consistency

[Findings]

## Traceability Matrix

[Matrix showing requirement → artifact coverage]

## Issues Summary

### Critical (Must fix before Phase 2)
1. [Issue]
2. [Issue]

### Major (Should fix)
1. [Issue]

### Minor (Nice to fix)
1. [Issue]

## Recommendations

[Specific recommendations for addressing issues]

## Phase 2 Readiness Checklist

- [ ] All requirements decomposable into tasks
- [ ] Architecture provides clear implementation guidance
- [ ] No blocking unknowns
- [ ] Risks identified and documented
- [ ] Stakeholder alignment confirmed
```

### Decision Point

Based on validation:
- **PASS** → Proceed to Step 5 (Stakeholder Review)
- **CONDITIONAL PASS** → Fix critical issues, then proceed
- **FAIL** → Return to relevant step to address issues

---

## Step 5: Stakeholder Review & Approval

### Objective
Get stakeholder buy-in on Phase 1 artifacts before Phase 2.

### Participants
- Technical Lead / Architect
- Product Owner
- Development Team Lead
- Key Stakeholders from Phase 0

### Time Required
1-2 days (including feedback incorporation)

### Process

#### 5.1 Prepare Review Package

Create review package containing:
- Executive summary (1 page)
- Constitution highlights
- PRD summary (vision, MVP, roadmap)
- Architecture overview (diagrams)
- Key decisions (ADR summaries)
- Validation summary
- Questions for stakeholders

#### 5.2 Conduct Reviews

**Technical Review** (Architecture focus):
- Architecture patterns
- Technology choices
- Scalability approach
- Security approach
- Technical risks

**Product Review** (PRD focus):
- Vision alignment
- MVP scope
- Priority order
- Success metrics
- Competitive positioning

**Business Review** (Constitution/Success Criteria):
- Business alignment
- Success criteria
- Constraints
- Timeline implications

#### 5.3 Incorporate Feedback

For each piece of feedback:
1. Document the feedback
2. Determine action (accept, modify, reject)
3. Update relevant artifact(s)
4. Re-validate if significant changes

Track in `validation/stakeholder-feedback.md`:

```markdown
# Stakeholder Feedback Log

## Review Date: [Date]

### Technical Review

| Feedback | From | Action | Status |
|----------|------|--------|--------|
| [Feedback] | [Name] | [Accept/Modify/Reject - Reason] | [Done/Pending] |

### Product Review

[Same format]

### Business Review

[Same format]

## Changes Made

1. [Change to artifact X]
2. [Change to artifact Y]

## Rejected Feedback (with rationale)

1. [Feedback] - Rejected because [reason]
```

#### 5.4 Obtain Approvals

Collect explicit approval:

```markdown
# Phase 1 Sign-off

## Project: [Name]
## Date: [Date]

### Approval Status

| Artifact | Approver | Date | Status |
|----------|----------|------|--------|
| Constitution | [Name] | [Date] | ✅ Approved |
| Specification | [Name] | [Date] | ✅ Approved |
| PRD | [Name] | [Date] | ✅ Approved |
| Architecture | [Name] | [Date] | ✅ Approved |
| Data Model | [Name] | [Date] | ✅ Approved |
| API Spec | [Name] | [Date] | ✅ Approved |

### Conditional Approvals

[Any conditions attached to approvals]

### Outstanding Items

[Anything that must be addressed in Phase 2]

### Sign-off

By signing below, stakeholders confirm:
- Artifacts are complete and accurate
- Architecture is appropriate
- MVP scope is agreed
- Phase 2 can proceed

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Product Owner | | | |
| Technical Lead | | | |
| Project Sponsor | | | |
```

---

## Phase 1 Completion

### Completion Checklist

Run: `.sdlc/primitives/checklists/phase-1-completion_checklist.md`

### Phase 1 Outputs

**Artifacts Produced**:
- `constitution.md` - Project principles and standards
- `spec.md` - Requirements specification
- `prd.md` - Product requirements document
- `architecture.md` - System architecture
- `data-model.md` - Data model
- `api-spec.json` - API specification
- `adrs/` - Architecture decision records
- `validation/phase1-validation-report.md`
- `validation/stakeholder-feedback.md`

### Handoff to Phase 2

Create `phase1-handoff.md`:

```markdown
# Phase 1 → Phase 2 Handoff

## Project: [Name]
## Handoff Date: [Date]

## Executive Summary

[One paragraph summary of what Phase 1 produced]

## Artifacts for Phase 2

| Artifact | Location | Version | Key Points |
|----------|----------|---------|------------|
| Constitution | artifacts/constitution.md | 1.0 | Quality standards, Definition of Done |
| Specification | artifacts/spec.md | 1.0 | [N] FRs, [M] NFRs |
| PRD | artifacts/prd.md | 1.0 | MVP includes [features] |
| Architecture | artifacts/architecture.md | 1.0 | [Pattern], [Tech stack] |
| Data Model | artifacts/data-model.md | 1.0 | [N] entities |
| API Spec | artifacts/api-spec.json | 1.0 | [N] endpoints |

## Key Decisions (ADRs)

1. [ADR-001]: [Decision summary]
2. [ADR-002]: [Decision summary]
3. [ADR-003]: [Decision summary]

## Constraints for Phase 2

[List constraints that Phase 2 must work within]

## Known Risks

[List risks for Phase 2 to track]

## Open Questions

[Any questions that Phase 2 needs to resolve]

## Recommended Phase 2 Focus

1. [Priority area 1]
2. [Priority area 2]
3. [Priority area 3]

## Success Criteria Reminder

[From constitution - what defines success]
```

---

## Quick Reference

### Phase 1 Steps Summary

| Step | What | Who | Duration | Output |
|------|------|-----|----------|--------|
| 0 | Kickoff | Human + AI | 2-4 hours | Workspace, context |
| 1 | Constitution | Constitution Agent | 2-4 hours | constitution.md |
| 2a | Specification | Analyst Agent | 1-2 days | spec.md |
| 2b | PRD | PM Agent | 1-2 days | prd.md |
| 3 | Architecture | Architect Agent | 2-3 days | architecture.md, data-model.md, api-spec.json, ADRs |
| 4 | Validation | Validator Agent | 4-6 hours | validation-report.md |
| 5 | Review | Humans | 1-2 days | Approvals |

**Total**: 6-10 days

### Key Decision Points

1. After Step 0: Ready to start Phase 1?
2. After Step 1: Constitution approved?
3. After Step 2: Requirements complete?
4. After Step 3: Architecture viable?
5. After Step 4: Validation passed?
6. After Step 5: Stakeholders approved?

### Critical Success Factors

1. ✅ Start with solid inputs (Phase 0 or equivalent)
2. ✅ Constitution first (guides everything else)
3. ✅ Iterate on requirements (don't try to get it perfect first pass)
4. ✅ Architecture respects constraints
5. ✅ Validate before review (don't waste stakeholder time on incomplete work)
6. ✅ Get explicit sign-off (avoid scope creep later)

---

*This workflow orchestrates all Phase 1 activities. Follow it step-by-step to ensure complete and high-quality specification before Phase 2 planning begins.*
