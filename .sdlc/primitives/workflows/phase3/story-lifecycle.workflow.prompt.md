# Story Lifecycle Workflow

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Orchestrate story flow from creation through implementation to completion  
**Location**: `.sdlc/primitives/workflows/phase3/story-lifecycle.workflow.prompt.md`

---

## Overview

This workflow defines how stories progress through the implementation phase, with clear handoffs between Scrum Master, Developer, and QA agents. Each agent adds their notes to the story file, creating a complete record of the story's journey.

---

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         STORY LIFECYCLE WORKFLOW                             │
└─────────────────────────────────────────────────────────────────────────────┘

  ┌────────────────────────────────────────────────────────────────────────┐
  │                        PHASE 2: STORY CREATION                          │
  └────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌──────────────────────────────────────────────────────────────────────┐
  │  1. SCRUM MASTER: Create Story                                        │
  │  ─────────────────────────────────                                   │
  │  • Load task from breakdown                                          │
  │  • Shard relevant architecture context                               │
  │  • Extract implementation guidance                                   │
  │  • Define acceptance criteria                                        │
  │  • Map dependencies                                                  │
  │  • Add test guidance                                                 │
  │  • OUTPUT: Story file (Draft status)                                 │
  └──────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌──────────────────────────────────────────────────────────────────────┐
  │  2. SCRUM MASTER: Review & Prioritize                                 │
  │  ─────────────────────────────────────                               │
  │  • Validate story completeness                                       │
  │  • Check dependencies resolved/scheduled                             │
  │  • Set priority                                                      │
  │  • Add SM notes (rationale, context)                                 │
  │  • OUTPUT: Story file (Ready status)                                 │
  └──────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌────────────────────────────────────────────────────────────────────────┐
  │                       PHASE 3: IMPLEMENTATION                           │
  └────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌──────────────────────────────────────────────────────────────────────┐
  │  3. SPRINT PLANNING: Assign Story                                     │
  │  ──────────────────────────────────                                  │
  │  • Select stories for sprint                                         │
  │  • Assign to developer                                               │
  │  • Confirm capacity                                                  │
  │  • Update story metadata                                             │
  └──────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌──────────────────────────────────────────────────────────────────────┐
  │  4. DEVELOPER: Implement                                              │
  │  ────────────────────────                                            │
  │  • Load story file (single source of truth)                          │
  │  • Follow implementation guidance                                    │
  │  • Update status to "In Progress"                                    │
  │  • Write code following patterns                                     │
  │  • Write tests per test guidance                                     │
  │  • Add Developer Notes:                                              │
  │    - Implementation decisions                                        │
  │    - Deviations from plan                                            │
  │    - Technical debt introduced                                       │
  │    - Blockers encountered                                            │
  │    - Time tracking                                                   │
  │  • Create PR                                                         │
  │  • OUTPUT: Story file updated, PR created                            │
  └──────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
  ┌──────────────────────────────────────────────────────────────────────┐
  │  5. CODE REVIEW: Peer Review                                          │
  │  ────────────────────────────                                        │
  │  • Review code against story acceptance criteria                     │
  │  • Check coding standards                                            │
  │  • Verify test coverage                                              │
  │  • Approve or request changes                                        │
  │  • Update status to "In Review"                                      │
  └──────────────────────────────────────────────────────────────────────┘
                                    │
                              ┌─────┴─────┐
                              │           │
                         Changes      Approved
                         Requested        │
                              │           │
                              ▼           ▼
  ┌─────────────────────┐    │    ┌─────────────────────────────────────────┐
  │  Return to Dev      │◄───┘    │  6. QA: Validate                         │
  │  (Address feedback) │         │  ────────────────                        │
  └─────────────────────┘         │  • Run test scenarios from story         │
                                  │  • Verify acceptance criteria             │
                                  │  • Check edge cases                       │
                                  │  • Test non-functional requirements       │
                                  │  • Add QA Notes:                          │
                                  │    - Test results (pass/fail)             │
                                  │    - Issues found                         │
                                  │    - Verification status                  │
                                  │  • Sign off or reject                     │
                                  │  • OUTPUT: Story file updated             │
                                  └───────────────────────────────────────────┘
                                                     │
                                               ┌─────┴─────┐
                                               │           │
                                          Rejected     Approved
                                               │           │
                                               ▼           ▼
  ┌─────────────────────┐                     │    ┌─────────────────────────┐
  │  Return to Dev      │◄────────────────────┘    │  7. DONE                 │
  │  (Fix issues)       │                          │  ────────                │
  └─────────────────────┘                          │  • Update status         │
                                                   │  • Merge PR              │
                                                   │  • Archive story file    │
                                                   │  • Update metrics        │
                                                   └─────────────────────────┘
```

---

## Step-by-Step Instructions

### Step 1: Scrum Master Creates Story

**Agent**: Scrum Master Agent  
**Input**: Task from task-breakdown.md, source artifacts (architecture, spec, test plan)  
**Output**: Story file in Draft status

#### 1.1 Load Task Information

```markdown
Load the task from task-breakdown.md:
- Task ID
- Task title
- Task description
- Parent epic
- Estimated effort
- Dependencies
```

#### 1.2 Shard Architecture Context

This is critical - DON'T copy the entire architecture document.

```markdown
## Architecture Sharding Process

1. Identify components/services this story touches
2. Extract ONLY those sections from architecture.md:
   - Component description
   - Component responsibilities (relevant ones only)
   - Integration points (for this story's interactions only)
   - Data model (entities this story uses)
   
3. Keep total excerpt under 200 lines
4. Note source: "Source: phase1/artifacts/architecture.md (Sections: X, Y, Z)"
```

#### 1.3 Extract Implementation Guidance

```markdown
## Implementation Guidance Sources

Pull from:
- Architect notes in architecture.md
- ADRs relevant to this story
- Coding standards in constitution.md
- Reference implementations

Format as:
- Recommended approach (numbered steps)
- Patterns to use
- Anti-patterns to avoid
- Reference code locations
```

#### 1.4 Define Acceptance Criteria

```markdown
## Acceptance Criteria Process

1. Locate user story in spec.md
2. Extract or create Gherkin-format scenarios:
   - Happy path scenarios
   - Error scenarios
   - Edge case scenarios
   
3. Add non-functional criteria:
   - Performance requirements
   - Security requirements
   - Accessibility requirements
```

#### 1.5 Map Dependencies

```markdown
## Dependency Mapping

1. Check task-breakdown.md for task dependencies
2. Convert to story dependencies:
   - Blocking: Stories that MUST complete before this one
   - Related: Stories touching same areas (not blocking)
   
3. External dependencies:
   - APIs not yet available
   - Design assets pending
   - Third-party integrations
```

#### 1.6 Add Test Guidance

```markdown
## Test Guidance Sources

Pull from:
- test-plan.md (relevant sections)
- QA notes on the epic
- Existing test patterns in codebase

Include:
- Test scenarios with type and priority
- Edge cases to cover
- Test data requirements
- Existing tests to update
```

#### 1.7 Complete Story File

Fill in story template, ensuring:
- All sections populated
- Context is sharded (not full documents)
- Traceability links included
- Set status to "Draft"

---

### Step 2: Scrum Master Reviews & Prioritizes

**Agent**: Scrum Master Agent  
**Input**: Draft story file  
**Output**: Story file in Ready status

#### 2.1 Completeness Check

```markdown
## Story Completeness Checklist

- [ ] User story clearly stated (As a... I want... So that...)
- [ ] Acceptance criteria defined (≥2 scenarios)
- [ ] Architecture context present (not empty)
- [ ] Implementation guidance present
- [ ] Dependencies identified (or explicitly "None")
- [ ] Test guidance present
- [ ] Effort estimated
- [ ] Priority set
- [ ] Traceability links work
```

#### 2.2 Dependency Check

```markdown
## Dependency Verification

For each blocking dependency:
- [ ] Is it scheduled before this story?
- [ ] Is it in a higher-priority state?
- [ ] If not, can we reschedule or resolve?
```

#### 2.3 Add SM Notes

```markdown
## SM Notes Section

Document:
- Why this priority was set
- Any context that helps the developer
- Sprint assignment rationale
- Notes for the team
```

#### 2.4 Set Status to Ready

```markdown
Story Status: Ready

This story is now available for sprint planning.
```

---

### Step 3: Sprint Planning - Assign Story

**Agent**: Scrum Master Agent (during sprint planning)  
**Input**: Ready stories, team capacity  
**Output**: Assigned stories for sprint

```markdown
## Sprint Assignment Process

1. Review team capacity for sprint
2. Select stories based on:
   - Priority
   - Dependencies (blocking stories first)
   - Skill match
   - Capacity fit
   
3. Assign developer to each story
4. Update story metadata:
   - Assigned To: [Developer]
   - Sprint: [Sprint number]
```

---

### Step 4: Developer Implements

**Agent**: Developer Agent  
**Input**: Story file (Ready status)  
**Output**: Code, tests, PR, updated story file

#### 4.1 Load Story as Single Source

```markdown
## Developer Story Loading

Load ONLY the story file for your assigned story.

The story file contains everything you need:
- What to build (acceptance criteria)
- How to build it (implementation guidance)
- What context you need (architecture excerpt)
- How to test it (test guidance)

You should NOT need to load:
- Full architecture document
- Full spec document
- Full PRD

If something is missing, flag it to SM.
```

#### 4.2 Update Status

```markdown
Story Status: In Progress
Started: [Date/Time]
```

#### 4.3 Implement

```markdown
## Implementation Process

1. Review implementation guidance
2. Follow recommended approach
3. Use specified patterns
4. Avoid anti-patterns listed
5. Reference example code if provided
6. Implement acceptance criteria
7. Write tests per test guidance
```

#### 4.4 Add Developer Notes

This is REQUIRED before moving to review:

```markdown
### Developer Notes
**Date**: [Date]
**Author**: [Developer name]

#### Implementation Decisions
- [Any decisions made during implementation]
- [Approach taken and why]

#### Deviations from Plan
- [What changed from the original guidance]
- [Why the deviation was necessary]

#### Technical Debt Introduced
- [ ] [Debt item] - [Why] - [Ticket: XXX]
  (If none, state "No technical debt introduced")

#### Blockers Encountered
- [Any blockers and how resolved]
  (If none, state "No blockers")

#### Time Tracking
- Estimated: [From story]
- Actual: [Actual hours]
- Variance reason: [If significant variance, explain]
```

#### 4.5 Create PR

```markdown
## PR Requirements

PR Description should include:
- Story ID and link to story file
- Summary of changes
- How to test
- Screenshots (if UI changes)
```

---

### Step 5: Code Review

**Agent**: Developer Agent (peer) or Lead  
**Input**: PR, story file  
**Output**: Approval or change requests

```markdown
## Code Review Checklist

Against Story:
- [ ] All acceptance criteria addressed
- [ ] Non-functional requirements met

Against Standards:
- [ ] Follows coding standards
- [ ] No linting errors
- [ ] Appropriate test coverage
- [ ] No obvious bugs
- [ ] Documentation adequate

If changes needed:
- Document specific feedback
- Return to developer

If approved:
- Approve PR
- Story moves to QA
```

---

### Step 6: QA Validates

**Agent**: QA Agent  
**Input**: Story file, deployed code  
**Output**: QA sign-off or rejection

#### 6.1 Run Test Scenarios

```markdown
## QA Test Execution

Execute all scenarios from story's Test Guidance section:

| Scenario | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| [From story] | [Expected] | [Actual] | ✅/❌ |
```

#### 6.2 Verify Acceptance Criteria

```markdown
## Acceptance Criteria Verification

For each Gherkin scenario in story:
- [ ] Scenario 1: [Title] - ✅ Verified / ❌ Failed
- [ ] Scenario 2: [Title] - ✅ Verified / ❌ Failed
```

#### 6.3 Check Edge Cases

```markdown
## Edge Case Testing

- [ ] [Edge case 1] - Result
- [ ] [Edge case 2] - Result
```

#### 6.4 Add QA Notes

This is REQUIRED:

```markdown
### QA Notes
**Date**: [Date]
**Author**: [QA name]

#### Test Results
| Test | Result | Notes |
|------|--------|-------|
| [Test from guidance] | ✅/❌ | [Notes] |

#### Issues Found
| Issue | Severity | Status | Notes |
|-------|----------|--------|-------|
| [If any] | [H/M/L] | [Open/Fixed] | [Details] |
(If none, state "No issues found")

#### Verification Status
- [x] All acceptance criteria verified
- [x] Edge cases tested
- [x] No regression found
- [x] NFRs verified

#### QA Sign-Off
**Status**: Approved / Rejected / Needs Rework
**Comments**: [Final comments]
```

---

### Step 7: Done

**Agent**: Scrum Master Agent  
**Input**: QA-approved story  
**Output**: Completed story, merged code

```markdown
## Story Completion Process

1. Merge PR to main branch
2. Update story status: Done
3. Archive story file to completed/
4. Update sprint metrics:
   - Points/hours completed
   - Cycle time
   - Variance analysis
```

---

## Story File Locations

```
projects/[project-name]/
├── phase3/
│   ├── stories/
│   │   ├── backlog/           # Ready stories not yet in sprint
│   │   │   ├── PROJ-EPIC-001.story.md
│   │   │   └── PROJ-EPIC-002.story.md
│   │   ├── sprint-N/          # Current sprint stories
│   │   │   ├── PROJ-EPIC-003.story.md
│   │   │   └── PROJ-EPIC-004.story.md
│   │   └── completed/         # Done stories (archive)
│   │       └── sprint-N-1/
│   │           └── PROJ-EPIC-000.story.md
```

---

## Agent Handoff Summary

| From | To | Trigger | Artifacts Passed |
|------|----|---------|------------------|
| Task Breakdown | SM | Planning complete | Tasks list |
| SM | Backlog | Story ready | Story file (Ready) |
| SM | Developer | Sprint assigned | Story file |
| Developer | Reviewer | PR created | Story file, Code |
| Reviewer | QA | PR approved | Story file |
| QA | SM | QA approved | Story file (with QA notes) |
| SM | Archive | Story done | Completed story file |

---

## Key Principles

1. **Story File is Single Source of Truth**
   - Developer loads ONLY story file
   - All needed context is in the story
   - No hunting through multiple documents

2. **Notes Accumulate, Never Delete**
   - SM notes stay
   - Dev notes added
   - QA notes added
   - Complete history preserved

3. **Sharding Prevents Context Bloat**
   - Only relevant architecture excerpts
   - Only relevant test guidance
   - Story stays under 600 lines

4. **Clear Status Transitions**
   - Draft → Ready → In Progress → In Review → Done
   - Each transition has clear criteria

5. **Traceability Maintained**
   - Links back to source artifacts
   - Can trace from code to requirement to problem

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
