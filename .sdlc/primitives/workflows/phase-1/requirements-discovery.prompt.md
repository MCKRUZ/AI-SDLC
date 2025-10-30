# Requirements Discovery Workflow - Phase 1

**Purpose**: This workflow orchestrates the requirements discovery process in Phase 1, coordinating the Analyst Agent and PM Agent to transform Phase 0 outputs into detailed, validated requirements and product specifications.

---

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│         Phase 1: Requirements Discovery & Product Definition     │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Initiate Phase 1     │
                 │  - Load Phase 0 artifacts│
                 │  - Create session        │
                 │  - Set up structure      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  2. Requirements Analysis│
                 │  (Analyst Agent)         │
                 │  - Decompose problem     │
                 │  - Identify requirements │
                 │  - Define acceptance     │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  3. Requirements Refine  │
                 │  (Analyst Agent)         │
                 │  - Write user stories    │
                 │  - Document business rules│
                 │  - Create spec.md        │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Stakeholder Review   │
                 │  - Present requirements  │
                 │  - Gather feedback       │
                 │  - Resolve ambiguities   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. Product Strategy     │
                 │  (PM Agent)              │
                 │  - Define vision         │
                 │  - Create personas       │
                 │  - Map user journeys     │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  6. Feature Definition   │
                 │  (PM Agent)              │
                 │  - Prioritize features   │
                 │  - Define MVP scope      │
                 │  - Create roadmap        │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  7. PRD Creation         │
                 │  (PM Agent)              │
                 │  - Document PRD          │
                 │  - Define metrics        │
                 │  - Create go-to-market   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  8. Requirements Valid.  │
                 │  - Trace to Phase 0      │
                 │  - Check completeness    │
                 │  - Stakeholder approval  │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  Ready for Architecture  │
                 │  Design Workflow         │
                 └──────────────────────────┘
```

---

## Step 1: Initiate Phase 1

### Objective
Set up Phase 1 session with all Phase 0 artifacts and create proper structure for requirements work.

### Time Required
30-60 minutes

### Actions

#### 1.1 Create Phase 1 Session Directory

```bash
# Create Phase 1 session folder
mkdir -p phase-1-sessions/[NNN-project-name]/{requirements,product,architecture,validation,artifacts}

# Create working subdirectories
mkdir -p phase-1-sessions/[NNN-project-name]/requirements/{drafts,reviews,clarifications}
mkdir -p phase-1-sessions/[NNN-project-name]/product/{personas,journeys,features}
```

#### 1.2 Load Phase 0 Artifacts

**Required Phase 0 Inputs**:
```markdown
## Phase 0 Artifacts to Load

**MUST HAVE**:
- [ ] `problem-statement.final.md` - The validated problem definition
- [ ] Interview transcripts (all) - Raw stakeholder insights
- [ ] `feasibility-report.md` - Technical viability assessment
- [ ] `constraints.md` - All constraints identified
- [ ] `success-criteria.md` - Measurable success definition

**SHOULD HAVE**:
- [ ] Risk register - Known risks
- [ ] Prior attempts documentation - What didn't work
- [ ] Competitive analysis - What others have done

**Copy to Phase 1 session**:
```bash
cp discovery-sessions/[project]/artifacts/* phase-1-sessions/[project]/requirements/phase-0-inputs/
```

#### 1.3 Create Session Metadata

```markdown
# Phase 1 Session Metadata

**Project Name**: [Name from Phase 0]
**Session ID**: [NNN-project-name]
**Phase 0 Session**: [Link to Phase 0 session]
**Start Date**: [YYYY-MM-DD]
**Status**: [Active]

**Team**:
- Requirements Analyst: [Name/Agent]
- Product Manager: [Name/Agent]
- Solutions Architect: [Name/Agent - for later]
- Validator: [Name/Agent - for later]

**Phase 0 Summary**:
- Problem: [One sentence from Phase 0]
- Root Cause: [Primary root cause]
- Business Impact: [Key quantified impact]
- Feasibility: [GO/CONDITIONAL/POC/NO-GO]
- Key Constraints: [Top 3 constraints]

**Phase 1 Goals**:
1. Transform problem into detailed functional requirements
2. Create product vision and MVP scope
3. Validate requirements with stakeholders
4. Prepare for architecture design

**Timeline**: [Estimated weeks]
```

**Save as**: `phase-1-sessions/[NNN-project-name]/session.meta.md`

#### 1.4 Load Organizational Context

**Context to Load**:
```markdown
## Context Files for Phase 1

**From Memory**:
- `.discovery/memory/organization.context.md`
- `.discovery/memory/technical-stack.context.md`
- `.discovery/memory/prior-projects.memory.md`

**From Phase 0**:
- Problem statement (validated)
- Stakeholder interviews (for traceability)
- Constraints (must respect)
- Success criteria (requirements must support)

**Templates to Load**:
- `spec.template.md` (for requirements specification)
- `prd.template.md` (for product requirements)
- `constitution.template.md` (for later)
```

---

## Step 2: Requirements Analysis (Analyst Agent)

### Objective
Decompose the Phase 0 problem statement into specific, testable functional requirements.

### Agent: Analyst Agent
Load: `.primitives/agents/analyst-agent.instructions.md`

### Time Required
2-4 hours (first pass)

### Context to Provide Agent

```markdown
## Context for Analyst Agent

You are beginning requirements analysis for [Project Name].

**Your Mission**: Transform the Phase 0 problem statement into detailed, 
testable functional requirements that will guide implementation.

**Inputs Provided**:
- Phase 0 problem statement (validated by all stakeholders)
- Phase 0 interview transcripts (for additional context)
- Constraints document (hard and soft constraints)
- Success criteria (measurable outcomes)

**Your Output**: 
- Functional requirements (spec.md)
- Business rules (within spec.md)
- Clarifications needed (clarifications.md)

**Frameworks to Apply**:
- Five Whys (understand causation)
- Jobs-to-be-Done (understand user intent)
- User Story Mapping (organize by workflow)
- INVEST principles (evaluate quality)

**Quality Standards**:
- Each requirement must be testable
- Each requirement must trace to Phase 0
- Use "shall/must" for mandatory, "should" for recommended
- Avoid implementation details (describe WHAT, not HOW)

Begin with requirements decomposition.
```

### Actions

#### 2.1 Problem Decomposition

**Decompose Problem into Functional Areas**:

```markdown
## Requirements Decomposition - [Project Name]

### From Phase 0 Problem Statement
**The Problem**: [Restate from Phase 0]

### Functional Areas Identified

**Area 1: [Functional Area Name]**
- **Purpose**: [What this area addresses]
- **From Phase 0**: [Which part of problem statement]
- **User/Actor**: [Who interacts with this]
- **Initial Requirements Identified**: [Count]

**Area 2: [Functional Area Name]**
[Same structure]

**Area 3: [Functional Area Name]**
[Same structure]

### Cross-Cutting Concerns
- **Security**: [Authentication, authorization, data protection needs]
- **Integration**: [External systems to connect with]
- **Reporting**: [What needs to be tracked/reported]
- **Administration**: [Management and configuration needs]

### Requirements Organization Strategy
[How will requirements be structured in spec.md?]
- [ ] By functional area (recommended)
- [ ] By user role
- [ ] By user journey
- [ ] By priority
- [ ] Other: [Specify]
```

**Save as**: `requirements/drafts/decomposition-v1.md`

#### 2.2 Extract Requirements from Phase 0

**Mine Phase 0 for Requirements**:

```markdown
## Requirements Extraction from Phase 0

### From Problem Statement

**Problem Element**: [Section from Phase 0]
↓
**Requirement**: [Extracted functional requirement]
- **Rationale**: [Why this requirement exists]
- **Source**: Problem statement, section [X]
- **Priority**: [Must-have/Should-have/Could-have]

**Problem Element**: [Another section]
↓
**Requirement**: [Extracted requirement]
[Same structure]

### From Interview Transcripts

**Stakeholder Quote**: "[Verbatim quote from interview]"
-- [Stakeholder Name, Role]
↓
**Requirement**: [Functional requirement derived from quote]
- **Source**: Interview with [Stakeholder], line [X]
- **Interpretation**: [How we're interpreting this]

### From Success Criteria

**Success Metric**: [Metric from Phase 0]
↓
**Supporting Requirements**:
- REQ-XXX: [Requirement needed to achieve this metric]
- REQ-YYY: [Another supporting requirement]

### From Constraints

**Constraint**: [Constraint from Phase 0]
↓
**Implications for Requirements**:
- Must: [What we must do]
- Must not: [What we can't do]
- Derived requirements: [Requirements that stem from constraint]
```

#### 2.3 Generate Initial Requirements List

**First Draft of Requirements**:

```markdown
## Requirements List - Draft v1

### Functional Area: [Area Name]

**REQ-[AREA]-001**: The system shall [specific action]
- **Actor**: [Who performs this]
- **Preconditions**: [What must be true before]
- **Postconditions**: [What is true after]
- **Success Criteria**: [How we know it works]
- **Source**: [Phase 0 reference]
- **Priority**: [Must/Should/Could/Won't]
- **Complexity**: [Low/Medium/High - initial estimate]

**REQ-[AREA]-002**: The system shall [specific action]
[Same structure]

### Functional Area: [Another Area]

**REQ-[AREA2]-001**: [Requirement]
[Same structure]

### Initial Statistics
- Total requirements identified: [N]
- Must-have: [N]
- Should-have: [N]
- Could-have: [N]
- High complexity: [N]
- Medium complexity: [N]
- Low complexity: [N]
```

**Save as**: `requirements/drafts/requirements-list-v1.md`

#### 2.4 Identify Gaps and Questions

**Track What's Unclear**:

```markdown
## Requirements Clarifications Needed

### Ambiguities in Phase 0
1. **Ambiguity**: [What's unclear from Phase 0]
   - **Impact**: [Which requirements are affected]
   - **Questions for Stakeholders**: [Specific questions]
   - **Assumed for Now**: [Temporary assumption]
   - **Priority**: [High/Medium/Low]

### Missing Information
1. **Gap**: [Information we don't have]
   - **Needed For**: [Which requirements need this]
   - **Source to Consult**: [Who/what can provide this]
   - **Impact of Not Having**: [What happens if we guess wrong]

### Contradictions Found
1. **Contradiction**: [What conflicts]
   - **Source A**: [One source says X]
   - **Source B**: [Another says Y]
   - **Needs Resolution**: [Yes/No]
   - **Resolution Strategy**: [How to resolve]

### Assumptions Made
1. **Assumption**: [What we're assuming]
   - **Rationale**: [Why we're making this assumption]
   - **Risk**: [What if we're wrong]
   - **Validation Plan**: [How to confirm]
```

**Save as**: `requirements/clarifications/clarifications-v1.md`

---

## Step 3: Requirements Refinement (Analyst Agent)

### Objective
Refine requirements into user stories, document business rules, and create the formal specification.

### Agent: Analyst Agent (refinement mode)

### Time Required
3-5 hours

### Actions

#### 3.1 Write User Stories

**Convert Requirements to User Stories** (for user-facing features):

```markdown
## User Stories - [Project Name]

### Functional Area: [Area Name]

**US-001**: As a [user role], I want [capability], so that [benefit]

**Acceptance Criteria**:
- [ ] Given [context], when [action], then [expected result]
- [ ] Given [context], when [action], then [expected result]
- [ ] Given [context], when [action], then [expected result]

**Business Rules**:
- [Rule that governs this story]
- [Another rule]

**Supporting Requirements**: REQ-[AREA]-001, REQ-[AREA]-003

**Story Points**: [Fibonacci: 1,2,3,5,8,13,21]

**Priority**: [Must/Should/Could]

**Notes**:
- [Implementation notes]
- [Design considerations]
- [Dependencies]

---

**US-002**: As a [user role], I want [capability], so that [benefit]
[Same structure]
```

**Save as**: `requirements/drafts/user-stories-v1.md`

#### 3.2 Document Business Rules

**Extract and Formalize Business Rules**:

```markdown
## Business Rules - [Project Name]

### Rule Category: [Category Name]

**BR-001**: [Rule Name]

**Statement**: [Clear statement of the rule]

**Rationale**: [Why this rule exists]

**Conditions**:
```
IF [condition 1]
  AND [condition 2]
  OR [condition 3]
THEN [action or outcome]
ELSE IF [condition 4]
THEN [alternative action]
ELSE [default action]
```

**Examples**:
- Scenario 1: [Description] → Result: [What happens]
- Scenario 2: [Description] → Result: [What happens]

**Exceptions**:
- [Exception condition]: [What happens instead]

**Source**: [Phase 0 reference or stakeholder]

**Affected Requirements**: REQ-XXX, REQ-YYY

**Complexity**: [Simple/Moderate/Complex]

---

**BR-002**: [Rule Name]
[Same structure]

### Rule Dependencies

```
BR-001 depends on BR-005
BR-002 conflicts with BR-007 (needs resolution)
BR-003 must execute before BR-004
```
```

**Save as**: `requirements/drafts/business-rules-v1.md`

#### 3.3 Create Formal Specification (spec.md)

**Use Template**: `spec.template.md`

**Structure of spec.md**:

```markdown
# Requirements Specification - [Project Name]

**Version**: 1.0
**Status**: Draft for Review
**Date**: [YYYY-MM-DD]
**Authors**: [Names]

---

## Document Control

**Version History**:
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | [Date] | [Name] | Initial draft |
| 1.0 | [Date] | [Name] | First complete version |

**Approvals Required**:
- [ ] Product Owner: [Name]
- [ ] Technical Lead: [Name]
- [ ] Key Stakeholders: [Names]

---

## Executive Summary

[2-3 paragraphs summarizing:
- What this specification covers
- Key functional areas
- Total number of requirements
- Critical requirements
- Next steps after approval]

---

## 1. Introduction

### 1.1 Purpose
[What this document is for, who should read it]

### 1.2 Scope
**In Scope**:
- [Functional area 1]
- [Functional area 2]
- [Functional area 3]

**Out of Scope** (for this phase):
- [What's explicitly not included]
- [Future phases or features]

### 1.3 Intended Audience
- Product Managers
- Developers
- QA/Testers
- Solutions Architects
- Stakeholders

### 1.4 References
- Phase 0 Problem Statement: [Link]
- Phase 0 Feasibility Report: [Link]
- Related Documents: [Links]

---

## 2. Traceability to Phase 0

### 2.1 Problem Statement Mapping

**Phase 0 Problem**: [Restate validated problem]

**How These Requirements Address It**:
- [Problem element] → Requirements: REQ-001, REQ-005, REQ-012
- [Problem element] → Requirements: REQ-007, REQ-009
- [Problem element] → Requirements: REQ-003, REQ-014, REQ-020

### 2.2 Success Criteria Mapping

| Phase 0 Success Criterion | Supporting Requirements |
|---------------------------|-------------------------|
| [Criterion 1] | REQ-XXX, REQ-YYY, REQ-ZZZ |
| [Criterion 2] | REQ-AAA, REQ-BBB |

### 2.3 Constraints Compliance

| Phase 0 Constraint | How Requirements Respect It |
|--------------------|----------------------------|
| [Constraint 1] | [Explanation] |
| [Constraint 2] | [Explanation] |

---

## 3. Functional Requirements

### 3.1 Functional Area: [Area Name]

**Overview**: [What this area covers]

**Actors**:
- [Actor 1]: [Description and role]
- [Actor 2]: [Description and role]

#### 3.1.1 [Sub-area or Use Case]

**REQ-[AREA]-001**: The system shall [specific, testable requirement]

**Priority**: [Must/Should/Could]

**Rationale**: [Why this requirement exists]

**Acceptance Criteria**:
- [ ] Given [context], when [action], then [result]
- [ ] [Additional acceptance criterion]
- [ ] [Additional acceptance criterion]

**Source**: [Phase 0 reference]

**Business Rules**: BR-001, BR-003

**Complexity**: [Low/Medium/High]

**Dependencies**: None / REQ-XXX must be implemented first

---

**REQ-[AREA]-002**: [Next requirement]
[Same structure]

### 3.2 Functional Area: [Another Area]
[Same structure]

---

## 4. User Stories

### 4.1 By User Role

#### 4.1.1 [User Role Name]

**US-001**: As a [role], I want [capability], so that [benefit]

**Acceptance Criteria**:
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

**Story Points**: [Estimate]

**Supporting Requirements**: REQ-XXX, REQ-YYY

---

## 5. Business Rules

[Include all documented business rules organized by category]

[Use structure from Step 3.2]

---

## 6. Data Requirements

### 6.1 Data Entities
[High-level entities - detailed data model in data-model.md]

### 6.2 Data Quality Requirements
- Accuracy: [Requirements]
- Completeness: [Requirements]
- Consistency: [Requirements]
- Timeliness: [Requirements]

### 6.3 Data Retention
[Retention policies]

---

## 7. External Interface Requirements

### 7.1 User Interfaces
[High-level UI requirements - not detailed designs]

### 7.2 System Interfaces
[Systems to integrate with, from Phase 0 constraints]

### 7.3 API Requirements
[High-level API needs - detailed spec in api-spec.json later]

---

## 8. Non-Functional Requirements (Summary)

[Brief summary - detailed NFRs are in constitution.md]

- Performance: [Key performance requirements]
- Security: [Key security requirements]
- Reliability: [Key reliability requirements]
- Scalability: [Key scalability requirements]
- Usability: [Key usability requirements]

---

## 9. Requirements Traceability Matrix

| Requirement ID | Phase 0 Source | User Story | Business Rule | Priority | Complexity |
|----------------|----------------|------------|---------------|----------|-----------|
| REQ-CORE-001 | Problem Stmt §2 | US-001 | BR-003 | Must | High |
| REQ-CORE-002 | Interview #2 | US-002 | BR-001 | Must | Medium |
| [All requirements listed] | | | | | |

---

## 10. Requirements Summary

### 10.1 Statistics
- Total Functional Requirements: [N]
- Must-Have Requirements: [N]
- Should-Have Requirements: [N]
- Could-Have Requirements: [N]
- Total User Stories: [N]
- Total Business Rules: [N]

### 10.2 Complexity Distribution
- High Complexity: [N requirements]
- Medium Complexity: [N requirements]
- Low Complexity: [N requirements]

### 10.3 Coverage Analysis
- Phase 0 Problems Addressed: [N/N = 100%]
- Success Criteria Supported: [N/N = 100%]
- Constraints Respected: [N/N = 100%]

---

## Appendix A: Glossary

[Define all domain-specific terms]

## Appendix B: Assumptions

[List all assumptions made during requirements analysis]

## Appendix C: Open Questions

[Questions that need resolution before finalization]
```

**Save as**: `requirements/spec.md` (version 1.0)

---

## Step 4: Stakeholder Review

### Objective
Present requirements to stakeholders for feedback and validation.

### Time Required
1-2 weeks (including review time)

### Actions

#### 4.1 Prepare Review Package

**Create Review Document**:

```markdown
# Requirements Review Package - [Project Name]

**Date**: [YYYY-MM-DD]
**Reviewers**: [List of stakeholders]
**Review Period**: [Start date] to [End date]
**Review Meeting**: [Date and time]

---

## What We're Asking You to Review

We've transformed the Phase 0 problem statement into detailed functional 
requirements. We need you to review and confirm:

1. ✅ **Completeness**: Do these requirements fully address the problem?
2. ✅ **Accuracy**: Do we have the details right?
3. ✅ **Priority**: Have we prioritized correctly?
4. ✅ **Feasibility**: Are these requirements realistic?
5. ✅ **Clarity**: Is anything ambiguous or unclear?

---

## Documents to Review

**Primary Document**:
- `spec.md` - Complete requirements specification

**Supporting Documents**:
- `user-stories.md` - User-centric view of requirements
- `business-rules.md` - Detailed business logic
- `clarifications.md` - Known questions and assumptions

---

## How to Provide Feedback

### Option 1: Inline Comments
Add comments directly in the spec.md document using this format:
```
[REVIEWER NAME - DATE]: Comment here
```

### Option 2: Structured Feedback Form
Use the feedback template provided

### Option 3: Review Meeting
Attend the review meeting on [date]

---

## Feedback Template

**Reviewer**: [Your name]
**Role**: [Your role]
**Date**: [YYYY-MM-DD]

### Overall Assessment
- [ ] Approve as-is
- [ ] Approve with minor comments
- [ ] Needs revision (major issues)

### Completeness
Missing requirements:
1. [What's missing]
2. [What's missing]

### Accuracy Issues
1. REQ-XXX: [What's wrong]
2. REQ-YYY: [What's wrong]

### Priority Concerns
1. [Requirement ID]: Should be [higher/lower] priority because [reason]

### Clarity Issues
1. [Requirement ID]: This is ambiguous because [reason]
2. [Requirement ID]: This is unclear

### Other Comments
[Additional feedback]
```

**Send to**: All Phase 0 stakeholders + new stakeholders identified

#### 4.2 Track Review Status

```markdown
## Requirements Review Tracking

| Reviewer | Role | Review Due | Status | Comments Submitted |
|----------|------|------------|--------|-------------------|
| [Name] | [Role] | [Date] | [Not Started/In Progress/Complete] | [Yes/No] |
| [Name] | [Role] | [Date] | [Status] | [Yes/No] |
```

#### 4.3 Consolidate Feedback

**After review period**:

```markdown
## Requirements Review - Consolidated Feedback

### Feedback by Category

**Completeness (Missing Requirements)**:
1. [Missing item] - Mentioned by: [Reviewer A, Reviewer C]
   - **Action**: Add REQ-NEW-001
   - **Owner**: [Name]
   - **Status**: [Added/In Progress/Won't Fix]

**Accuracy (Incorrect Requirements)**:
1. REQ-XXX incorrect - Mentioned by: [Reviewer B]
   - **Issue**: [Description]
   - **Action**: Correct wording
   - **Status**: [Fixed/In Progress]

**Priority Changes**:
1. REQ-YYY priority change - Requested by: [Reviewer A]
   - **Current**: Should-have
   - **Requested**: Must-have
   - **Rationale**: [Reason]
   - **Decision**: [Accepted/Rejected/Deferred]

**Clarity Issues**:
1. REQ-ZZZ ambiguous - Mentioned by: [Reviewer C]
   - **Ambiguity**: [What's unclear]
   - **Resolution**: [How we clarified]
   - **Status**: [Resolved]

### Feedback Statistics
- Total feedback items: [N]
- Accepted: [N]
- Rejected: [N]
- Deferred: [N]
```

#### 4.4 Update Requirements

**Create revised spec**:
```bash
cp requirements/spec.md requirements/spec-v1.0.md  # Archive
# Make updates to spec.md
# Update version to 1.1
# Document changes in version history
```

---

## Step 5: Product Strategy (PM Agent)

### Objective
Define product vision, personas, and user journeys that bring requirements to life.

### Agent: PM Agent
Load: `.primitives/agents/pm-agent.instructions.md`

### Time Required
2-3 hours

### Context to Provide Agent

```markdown
## Context for PM Agent

You are defining product strategy for [Project Name].

**Your Mission**: Transform technical requirements into a compelling product 
vision with clear user personas and journeys.

**Inputs Provided**:
- Phase 0 problem statement (the WHY)
- Requirements specification (the WHAT)
- Phase 0 interview transcripts (user insights)
- Success criteria (measurable outcomes)

**Your Output**:
- Product vision statement
- User personas (primary and secondary)
- User journey maps (key workflows)
- Initial feature list

**Frameworks to Apply**:
- Persona development (demographics, goals, behaviors)
- User Journey Mapping (stages, touchpoints, emotions)
- Value Proposition Canvas
- Jobs-to-be-Done

Begin with product vision.
```

### Actions

#### 5.1 Define Product Vision

**Create Vision Statement**:

```markdown
## Product Vision - [Project Name]

### Vision Statement
[1-2 compelling paragraphs that answer:
- Who is this for?
- What problem does it solve?
- What makes it different/better?
- What's the ultimate outcome?]

**Example**:
"For [target users] who [statement of need], [Product Name] is a [product category] 
that [key benefit]. Unlike [alternatives], our product [key differentiator]."

### Product Positioning

**Target Market**: [Who we're selling to]

**Value Proposition**: [Core value we deliver]

**Competitive Differentiation**:
- vs. [Competitor A]: [How we're different/better]
- vs. [Competitor B]: [How we're different/better]
- vs. Status Quo: [Why change is worth it]

### Product Principles
[3-5 principles that guide product decisions]

1. **[Principle Name]**: [Description]
2. **[Principle Name]**: [Description]
3. **[Principle Name]**: [Description]

### Success Vision
In [6/12/24] months, we will have:
- [Measurable outcome 1]
- [Measurable outcome 2]
- [Measurable outcome 3]
```

**Save as**: `product/product-vision.md`

#### 5.2 Create User Personas

**Develop Detailed Personas**:

```markdown
## User Personas - [Project Name]

### Primary Persona: [Name]

**Photo/Avatar**: [If available]

**Quote**: "[A quote that captures their perspective]"

**Demographics**:
- **Age**: [Range]
- **Role**: [Job title]
- **Experience Level**: [Junior/Mid/Senior]
- **Technical Proficiency**: [Low/Medium/High]
- **Location**: [Where they work]

**Background**:
[Narrative about who they are, their role, their typical day]

**Goals & Motivations**:
- 🎯 Primary Goal: [What they're trying to achieve]
- 🎯 Secondary Goals: [Other objectives]
- 💪 Motivations: [What drives them]

**Pain Points** (from Phase 0):
- 😞 [Pain point 1] - Source: [Interview reference]
- 😞 [Pain point 2] - Source: [Interview reference]
- 😞 [Pain point 3] - Source: [Interview reference]

**Current Behavior** (workarounds):
- [What they do now]
- [Workarounds they've developed]
- [Tools they currently use]

**Frustrations**:
- [Frustration 1]
- [Frustration 2]

**Needs** (derived from requirements):
- ✅ [Need 1] - Addressed by: REQ-XXX
- ✅ [Need 2] - Addressed by: REQ-YYY
- ✅ [Need 3] - Addressed by: REQ-ZZZ

**Success Criteria for This Persona**:
- [What success means for them specifically]

**Preferences**:
- [How they like to work]
- [Communication preferences]
- [Learning style]

**Influence**:
- **Decision Making Power**: [High/Medium/Low]
- **Influence on Others**: [High/Medium/Low]

---

### Secondary Persona: [Name]
[Same structure]

### Other Personas
[List additional personas - less detailed]
```

**Save as**: `product/personas/personas.md`

#### 5.3 Map User Journeys

**Create Journey Maps for Key Workflows**:

```markdown
## User Journey Maps - [Project Name]

### Journey 1: [Journey Name]

**Persona**: [Primary Persona Name]

**Goal**: [What user is trying to accomplish]

**Scenario**: [Specific context for this journey]

**Journey Stages**:

#### Stage 1: [Stage Name]
**User Actions**:
- [Action user takes]
- [Next action]

**Touchpoints**:
- [System interaction point]
- [Another touchpoint]

**User Thoughts**:
💭 "[What user is thinking]"

**User Emotions**:
- Beginning: 😐 [Neutral/Hopeful/Anxious]
- During: 😞 [Frustrated/Confused]
- End: 😊 [Satisfied/Relieved]

**Pain Points**:
- ⚠️ [Pain point experienced in this stage]
- ⚠️ [Another pain point]

**Opportunities**:
- 💡 [How we can improve this stage]
- 💡 [Another opportunity]

**Supporting Requirements**:
- REQ-XXX: [How this requirement supports this stage]
- REQ-YYY: [How this requirement helps]

---

#### Stage 2: [Stage Name]
[Same structure]

---

### Journey Success Metrics
- Time to Complete: Current [X] → Target [Y]
- Success Rate: Current [X%] → Target [Y%]
- Satisfaction: Current [NPS X] → Target [NPS Y]

---

### Journey 2: [Another Key Journey]
[Same structure]

### Journey 3: [Another Key Journey]
[Same structure]
```

**Save as**: `product/journeys/user-journeys.md`

---

## Step 6: Feature Definition (PM Agent)

### Objective
Identify features, prioritize them, and define MVP scope.

### Agent: PM Agent (feature planning mode)

### Time Required
2-3 hours

### Actions

#### 6.1 Extract Features from Requirements

**Map Requirements to Features**:

```markdown
## Feature Extraction - [Project Name]

### Feature Mapping

**Feature 1: [Feature Name]**
**Description**: [What this feature does in user-friendly terms]

**Supporting Requirements**:
- REQ-XXX: [Requirement description]
- REQ-YYY: [Requirement description]
- REQ-ZZZ: [Requirement description]

**User Value**: [Why users care about this feature]

**User Stories**: US-001, US-005, US-012

**Dependencies**: [Other features this depends on]

---

**Feature 2: [Feature Name]**
[Same structure]

### Features List
1. [Feature 1 name]
2. [Feature 2 name]
3. [Feature 3 name]
[Continue for all features]

Total Features: [N]
```

#### 6.2 Prioritize Features

**Apply RICE Framework** (or MoSCoW, Kano, etc.):

```markdown
## Feature Prioritization - [Project Name]

**Framework Used**: RICE (Reach × Impact × Confidence / Effort)

### RICE Scoring

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---------|-------|--------|-----------|--------|------------|----------|
| [Feature 1] | 1000 | 3 | 80% | 5 | 480 | 1 |
| [Feature 2] | 500 | 2 | 90% | 2 | 450 | 2 |
| [Feature 3] | 800 | 1 | 70% | 3 | 187 | 3 |
| [All features scored] | | | | | | |

**Scoring Definitions**:
- **Reach**: Number of users affected per quarter
- **Impact**: 3=Massive, 2=High, 1=Medium, 0.5=Low, 0.25=Minimal
- **Confidence**: 100%=High, 80%=Medium, 50%=Low
- **Effort**: Person-months to implement

---

**Alternative: MoSCoW Prioritization**

**Must Have** (Critical for MVP):
- [Feature 1]: [Rationale]
- [Feature 2]: [Rationale]

**Should Have** (Important but not critical):
- [Feature 3]: [Rationale]
- [Feature 4]: [Rationale]

**Could Have** (Nice to have):
- [Feature 5]: [Rationale]

**Won't Have** (Not in this phase):
- [Feature 6]: [Rationale why deferred]
```

**Save as**: `product/features/prioritization.md`

#### 6.3 Define MVP Scope

**MVP Definition**:

```markdown
## MVP Scope - [Project Name]

### MVP Definition

**What is "Minimal"?**
[What's the minimum set of features that solves the core problem?]

**What is "Viable"?**
[What's the minimum quality level that users will accept and use?]

**What is a "Product"?**
[What makes this a complete experience vs. a prototype?]

### MVP Success Criteria
From Phase 0, these are the metrics that define MVP success:
- [Metric 1]: Baseline [X] → Target [Y]
- [Metric 2]: Baseline [X] → Target [Y]
- [Metric 3]: Baseline [X] → Target [Y]

### MVP Features (In Scope)

**Core Features** (Must Have):
1. **[Feature Name]**
   - Why in MVP: [Rationale]
   - Supporting Requirements: [List]
   - Estimated Effort: [Person-weeks]
   
2. **[Feature Name]**
   [Same structure]

**Total MVP Features**: [N]
**Total MVP Requirements**: [N]
**Estimated MVP Effort**: [Person-months]

### Post-MVP Features (Out of Scope for Now)

**Phase 2 Features**:
- [Feature]: [Why deferred]
- [Feature]: [Why deferred]

**Future Considerations**:
- [Feature]: [Why much later]

### MVP Boundaries

**What Users CAN Do**:
- [Capability 1]
- [Capability 2]
- [Capability 3]

**What Users CANNOT Do** (explicitly out of scope):
- [Capability] - Coming in Phase 2
- [Capability] - Coming in Phase 3
- [Capability] - Not planned

### MVP Constraints
- **Timeline**: [X weeks/months]
- **Team Size**: [N developers]
- **Budget**: [If applicable]
- **Technical**: [Key technical constraints from Phase 0]

### MVP Risks
1. **Risk**: [Description]
   - Mitigation: [Strategy]
2. **Risk**: [Description]
   - Mitigation: [Strategy]
```

**Save as**: `product/mvp-scope.md`

---

## Step 7: PRD Creation (PM Agent)

### Objective
Create comprehensive Product Requirements Document combining vision, personas, features, and metrics.

### Agent: PM Agent (documentation mode)

### Time Required
2-3 hours

### Actions

#### 7.1 Create PRD Document

**Use Template**: `prd.template.md`

**PRD Structure** (excerpt - full template is comprehensive):

```markdown
# Product Requirements Document - [Project Name]

**Version**: 1.0
**Status**: Draft for Review
**Date**: [YYYY-MM-DD]
**Author**: [PM Name/Agent]

---

## 1. Executive Summary

[1-2 page summary covering:
- Product vision
- Target users
- Key features
- MVP scope
- Success metrics
- Timeline and resources]

---

## 2. Product Vision

[From Step 5.1 - product-vision.md]

---

## 3. Market & Users

### 3.1 Target Market
[Who we're selling to, market size, opportunity]

### 3.2 User Personas
[From Step 5.2 - personas.md]

### 3.3 User Needs
[Mapped from personas and Phase 0]

---

## 4. Product Features

### 4.1 Feature Overview
[List of all features with descriptions]

### 4.2 MVP Features
[From Step 6.3 - mvp-scope.md]

### 4.3 Post-MVP Roadmap
[Features planned for later phases]

---

## 5. User Experience

### 5.1 User Journeys
[From Step 5.3 - user-journeys.md]

### 5.2 Key Workflows
[High-level workflow descriptions]

---

## 6. Success Metrics

### 6.1 MVP Success Criteria
[From Phase 0, refined]

### 6.2 Leading Indicators
[Metrics to track during development]

### 6.3 Lagging Indicators
[Metrics to measure after launch]

---

## 7. Go-to-Market Strategy

### 7.1 Launch Plan
[If applicable]

### 7.2 Marketing Approach
[If applicable]

### 7.3 Sales/Distribution
[If applicable]

---

## 8. Requirements Traceability

[Link to spec.md - formal requirements documentation]

---

## 9. Timeline & Resources

### 9.1 MVP Timeline
[High-level milestones]

### 9.2 Resource Requirements
[Team, budget, tools]

---

## 10. Risks & Mitigation

[From Phase 0 + new risks identified in Phase 1]

---

## Appendices
- Appendix A: Competitive Analysis
- Appendix B: User Research
- Appendix C: Technical Considerations
```

**Save as**: `product/prd.md`

---

## Step 8: Requirements Validation

### Objective
Ensure requirements are complete, consistent, traceable, and ready for architecture design.

### Time Required
2-4 hours

### Actions

#### 8.1 Traceability Check

**Verify Complete Traceability**:

```markdown
## Requirements Traceability Validation

### Phase 0 → Spec Traceability

**Every Phase 0 Problem Element Addressed?**
- [ ] Problem element 1 → REQ-XXX, REQ-YYY [✓]
- [ ] Problem element 2 → REQ-ZZZ [✓]
- [ ] Problem element 3 → No requirements [✗] **GAP!**

**Every Phase 0 Success Criterion Supported?**
- [ ] Criterion 1 → REQ-AAA, REQ-BBB [✓]
- [ ] Criterion 2 → REQ-CCC [✓]

**Every Phase 0 Constraint Respected?**
- [ ] Constraint 1 → Respected in REQ-XXX [✓]
- [ ] Constraint 2 → Respected in design approach [✓]

### Spec → PRD Traceability

**Every Requirement Appears in PRD?**
- [ ] All requirements mapped to features [✓]
- [ ] All requirements prioritized [✓]
- [ ] MVP requirements in MVP scope [✓]

### Completeness

**Coverage**:
- Phase 0 coverage: [X/Y = Z%] - Must be 100%
- Success criteria coverage: [X/Y = Z%] - Must be 100%
- Constraint compliance: [X/Y = Z%] - Must be 100%

**Gaps Identified**:
1. [Gap description] - **Action**: [How to address]
```

#### 8.2 Consistency Check

```markdown
## Requirements Consistency Validation

### Internal Consistency (within spec.md)

**Contradictions**:
- [ ] No requirements contradict each other [✓/✗]
- [ ] Business rules are consistent [✓/✗]
- [ ] Priorities are logical [✓/✗]

**Issues Found**:
1. REQ-XXX vs REQ-YYY: [Description of conflict]
   - Resolution: [How to fix]

### Cross-Document Consistency

**Spec vs. PRD**:
- [ ] Feature names match [✓/✗]
- [ ] MVP scope aligns [✓/✗]
- [ ] Priorities consistent [✓/✗]

**Spec vs. Phase 0**:
- [ ] Terminology consistent [✓/✗]
- [ ] No contradictions with Phase 0 findings [✓/✗]

**Issues Found**:
[List any consistency issues]
```

#### 8.3 Quality Check

```markdown
## Requirements Quality Validation

### INVEST Principles Check

For each user story:
- [ ] **Independent**: Can be developed independently
- [ ] **Negotiable**: Room for discussion on implementation
- [ ] **Valuable**: Delivers clear user value
- [ ] **Estimable**: Team can estimate effort
- [ ] **Small**: Appropriately sized (not too big)
- [ ] **Testable**: Can verify implementation

**Stories Failing INVEST**: [List with issues]

### Requirement Writing Quality

Sample check (repeat for all requirements):
- [ ] REQ-XXX: Clear, unambiguous language [✓/✗]
- [ ] REQ-XXX: Testable acceptance criteria [✓/✗]
- [ ] REQ-XXX: No implementation details [✓/✗]
- [ ] REQ-XXX: Proper "shall/should/may" usage [✓/✗]

**Quality Issues**: [List requirements needing improvement]
```

#### 8.4 Stakeholder Final Approval

**Obtain Sign-offs**:

```markdown
## Requirements & PRD Approval

### Sign-off Required From

**Product Owner**:
- [ ] PRD approved
- [ ] MVP scope approved
- [ ] Success metrics approved
- Signature: [__________] Date: [__________]

**Technical Lead**:
- [ ] Requirements are technically feasible
- [ ] Complexity estimates reasonable
- [ ] Constraints understood
- Signature: [__________] Date: [__________]

**Key Stakeholders**:
- [ ] [Stakeholder 1]: Requirements address their needs
  - Signature: [__________] Date: [__________]
- [ ] [Stakeholder 2]: Requirements address their needs
  - Signature: [__________] Date: [__________]

### Final Checklist

- [ ] All Phase 0 problems addressed
- [ ] All stakeholders reviewed and approved
- [ ] All feedback incorporated or explicitly deferred
- [ ] Traceability complete
- [ ] Quality standards met
- [ ] Documents professionally formatted
- [ ] No critical open questions
- [ ] Ready for architecture design phase
```

#### 8.5 Package for Architecture Phase

**Prepare Handoff**:

```bash
# Create architecture handoff package
mkdir -p phase-1-sessions/[project]/handoff-to-architecture/

# Copy finalized documents
cp requirements/spec.md phase-1-sessions/[project]/handoff-to-architecture/
cp product/prd.md phase-1-sessions/[project]/handoff-to-architecture/
cp requirements/clarifications/clarifications-final.md phase-1-sessions/[project]/handoff-to-architecture/

# Copy Phase 0 artifacts for reference
cp phase-1-sessions/[project]/requirements/phase-0-inputs/* phase-1-sessions/[project]/handoff-to-architecture/phase-0-reference/
```

**Create Handoff Document**:

```markdown
# Architecture Design Phase Handoff

**From**: Requirements & Product Team
**To**: Architecture Team
**Date**: [YYYY-MM-DD]

## Phase 1 Outputs Ready for Architecture

**Core Documents**:
- ✅ `spec.md` - Functional Requirements Specification (APPROVED)
- ✅ `prd.md` - Product Requirements Document (APPROVED)
- ✅ `clarifications.md` - Known questions and assumptions

**Supporting Documents**:
- `user-stories.md` - User stories with acceptance criteria
- `business-rules.md` - Detailed business logic
- `personas.md` - User personas
- `user-journeys.md` - Key user workflows
- `mvp-scope.md` - MVP definition and boundaries

**Phase 0 Reference**:
- `problem-statement.final.md` - Original problem (validated)
- `feasibility-report.md` - Technical feasibility analysis
- `constraints.md` - All constraints to respect

## Key Information for Architects

**Must-Have Requirements**: [N]
**Should-Have Requirements**: [N]
**MVP Scope**: [Brief description]

**Critical NFRs** (to detail in constitution):
- Performance: [Key targets]
- Security: [Key requirements]
- Scalability: [Key requirements]

**Key Constraints**:
1. [Constraint 1]
2. [Constraint 2]
3. [Constraint 3]

**Key Integration Points**:
- [System 1]: [Integration requirement]
- [System 2]: [Integration requirement]

**Open Questions for Architecture**:
1. [Technical question that architecture should answer]
2. [Another question]

## Next Steps

1. Architecture team reviews requirements
2. Architecture team creates constitution.md
3. Architecture team designs system architecture
4. Architecture team defines data model
5. Architecture team specifies APIs
6. Validation of architecture against requirements

**Contact for Questions**: [Name, email]
```

---

## Workflow Completion Checklist

### Requirements Analysis Complete

- [ ] Phase 0 artifacts loaded and reviewed
- [ ] Problem decomposed into functional areas
- [ ] All requirements extracted from Phase 0
- [ ] Requirements organized in spec.md
- [ ] Business rules documented
- [ ] User stories written with acceptance criteria
- [ ] Stakeholders reviewed requirements
- [ ] All feedback incorporated or deferred
- [ ] Traceability verified (Phase 0 → Requirements)
- [ ] Quality standards met (INVEST principles)

### Product Definition Complete

- [ ] Product vision defined
- [ ] User personas created (primary + secondary)
- [ ] User journeys mapped (minimum 3 key journeys)
- [ ] Features extracted from requirements
- [ ] Features prioritized using framework (RICE/MoSCoW)
- [ ] MVP scope clearly defined
- [ ] Post-MVP features identified
- [ ] PRD document created
- [ ] Success metrics defined
- [ ] Go-to-market strategy outlined (if applicable)

### Validation Complete

- [ ] All Phase 0 problems addressed by requirements
- [ ] All Phase 0 success criteria supported
- [ ] All Phase 0 constraints respected
- [ ] Requirements internally consistent
- [ ] Spec and PRD aligned
- [ ] No critical open questions
- [ ] All stakeholders approved
- [ ] Documents professionally formatted
- [ ] Ready for architecture design

### Handoff Ready

- [ ] All documents in final approved state
- [ ] Handoff package prepared
- [ ] Architecture team briefed
- [ ] Contact information provided
- [ ] Next steps clear

---

## Common Pitfalls & How to Avoid

### Pitfall: Implementation Leak
❌ "The system shall use a React frontend with Redux for state management"
✅ "The system shall provide a responsive user interface that updates in real-time"

### Pitfall: Vague Requirements
❌ "The system shall be fast"
✅ "The system shall respond to user queries within 2 seconds for 95% of requests"

### Pitfall: Missing Acceptance Criteria
❌ Just the requirement statement
✅ Requirement + Given/When/Then acceptance criteria

### Pitfall: Requirements Don't Trace to Phase 0
❌ Requirements that sound good but don't address identified problems
✅ Every requirement clearly traces to Phase 0 problem, quote, or constraint

### Pitfall: MVP Too Large
❌ Trying to include every nice-to-have feature
✅ Ruthless focus on minimum set that solves core problem

### Pitfall: Missing User Perspective
❌ Just technical requirements
✅ Requirements expressed as user stories with user value

### Pitfall: No Prioritization
❌ All requirements treated equally
✅ Clear Must/Should/Could/Won't with rationale

---

## Success Criteria for Requirements Discovery Workflow

**Ready to proceed to Architecture Design when**:
✅ Every Phase 0 problem element has supporting requirements
✅ Every requirement traces to Phase 0 source
✅ All requirements have acceptance criteria
✅ MVP is clearly defined with rationale
✅ Stakeholders have reviewed and approved
✅ No critical open questions remain
✅ Product vision is compelling and clear
✅ User personas and journeys provide context
✅ Quality standards met (INVEST, clarity, testability)
✅ Architecture team has everything they need to begin design

---

**Remember**: Requirements are the contract between stakeholders and the implementation team. Invest the time to get them right. Clear requirements prevent costly rework during implementation.

**Next Workflow**: `architecture-design.prompt.md`
