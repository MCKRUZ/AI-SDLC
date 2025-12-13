# Story File Template

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Self-contained context carrier for implementation  
**Location**: `.sdlc/primitives/templates/phase3/story-file_template.md`

---

## Overview

A **Story File** is a self-contained document that carries all context needed for implementation. Unlike traditional user stories that reference external documents, story files embed relevant context directly, eliminating context loss between sessions and handoffs.

### Key Principles

1. **Self-Contained**: Developer can implement without loading other documents
2. **Context-Rich**: Includes architectural context, not just requirements
3. **Living Document**: Accumulates notes from SM → Dev → QA through lifecycle
4. **Sharded**: Only includes relevant portions of larger documents
5. **Traceable**: Links back to source artifacts for reference

---

## Template

```markdown
# Story: [STORY-ID] - [Title]

## Metadata
| Field | Value |
|-------|-------|
| **Story ID** | [PROJECT]-[EPIC]-[NUMBER] (e.g., PORTAL-AUTH-003) |
| **Title** | [Concise story title] |
| **Epic** | [Parent epic name] |
| **Created** | [Date] |
| **Status** | [Draft │ Ready │ In Progress │ In Review │ Done] |
| **Priority** | [P0-Critical │ P1-High │ P2-Medium │ P3-Low] |
| **Estimated Effort** | [X hours/days] |
| **Assigned To** | [Developer name/agent] |
| **Sprint** | [Sprint number] |

---

## User Story

**As a** [user type/persona],  
**I want** [goal/desire],  
**So that** [benefit/value].

### Additional Context
[Any clarifying information about the user need - 2-3 sentences max]

---

## Acceptance Criteria

### Functional Criteria

```gherkin
Scenario: [Scenario name]
  Given [precondition]
  When [action]
  Then [expected result]
  And [additional expectation]

Scenario: [Another scenario]
  Given [precondition]
  When [action]
  Then [expected result]
```

### Non-Functional Criteria
- [ ] **Performance**: [Specific requirement, e.g., "Response time < 200ms"]
- [ ] **Security**: [Specific requirement, e.g., "Input must be sanitized"]
- [ ] **Accessibility**: [Specific requirement, e.g., "WCAG 2.1 AA compliant"]
- [ ] **Other**: [Any other NFRs]

---

## Architecture Context (Sharded)

> This section contains ONLY the architectural elements relevant to THIS story.
> Source: `phase1/artifacts/architecture.md` (Sections: [list sections])

### Component(s) Affected

```
[Component name]
├── Purpose: [What this component does]
├── Location: [File path or module]
├── Responsibilities relevant to this story:
│   ├── [Responsibility 1]
│   └── [Responsibility 2]
└── Dependencies:
    ├── [Dependency 1] - [Why needed]
    └── [Dependency 2] - [Why needed]
```

### Integration Points

| System/Service | Integration Type | Relevant To This Story |
|----------------|------------------|------------------------|
| [System A] | [REST API / Event / DB] | [How this story interacts] |
| [System B] | [REST API / Event / DB] | [How this story interacts] |

### Data Model (Excerpt)

```
[Entity relevant to this story]
├── field1: type - [purpose]
├── field2: type - [purpose]
└── relationship: [related entity] - [cardinality]
```

### API Contract (If Applicable)

```yaml
# Only the endpoint(s) relevant to this story
endpoint: [METHOD] [/path]
request:
  headers:
    - [header]: [description]
  body:
    field1: type  # [description]
response:
  200:
    field1: type  # [description]
  400:
    error: string  # [when this occurs]
```

---

## Implementation Guidance

> Notes from Architect/Tech Lead on HOW to implement this story.

### Recommended Approach

1. [Step 1 - What to do first]
2. [Step 2 - What to do next]
3. [Step 3 - Continue pattern]

### Patterns to Use
- **Pattern Name**: [Brief description of when/how to apply]
- **Pattern Name**: [Brief description of when/how to apply]

### Anti-Patterns to Avoid
- ❌ **Don't**: [What not to do]
- ❌ **Don't**: [What not to do]

### Reference Implementations
- `[file path]` - [What it demonstrates]
- `[file path]` - [What it demonstrates]

### Technical Decisions Made
> ADR references or inline decisions
- **Decision**: [What was decided]
  - **Context**: [Why this decision was needed]
  - **Rationale**: [Why this option was chosen]

---

## Dependencies

### Blocking Dependencies (Must Complete First)
| Story ID | Title | Status | Blocker Reason |
|----------|-------|--------|----------------|
| [ID] | [Title] | [Status] | [Why this blocks] |

### Related Stories (Touch Same Areas)
| Story ID | Title | Relationship |
|----------|-------|--------------|
| [ID] | [Title] | [How related - shared component, same feature, etc.] |

### External Dependencies
- [ ] [External dependency] - [Status/Notes]

---

## Test Guidance

> From QA/Test Architect - what testing this story needs.

### Test Scenarios

| Scenario | Type | Priority | Notes |
|----------|------|----------|-------|
| [Happy path] | Unit/Integration/E2E | High | [Notes] |
| [Edge case 1] | Unit/Integration | Medium | [Notes] |
| [Error case 1] | Unit | Medium | [Notes] |

### Edge Cases to Cover
- [ ] [Edge case description]
- [ ] [Edge case description]

### Test Data Requirements
- [Data requirement 1]
- [Data requirement 2]

### Existing Tests to Update
- `[test file path]` - [What needs updating]

---

## Definition of Done

### Code Complete
- [ ] All acceptance criteria implemented
- [ ] Code follows project coding standards
- [ ] No linting errors or warnings
- [ ] Self-review completed

### Testing Complete
- [ ] Unit tests written and passing
- [ ] Integration tests written and passing (if applicable)
- [ ] Edge cases covered
- [ ] Test coverage meets threshold ([X]%)

### Documentation Complete
- [ ] Code comments for complex logic
- [ ] README updated (if applicable)
- [ ] API documentation updated (if applicable)

### Review Complete
- [ ] PR created with description
- [ ] Code review approved
- [ ] QA review passed

---

## Lifecycle Notes

> This section is updated as the story progresses through its lifecycle.
> Each role appends their notes - DO NOT DELETE previous notes.

### Scrum Master Notes
**Date**: [Date]  
**Author**: [SM name/agent]

[Notes about story creation, prioritization decisions, sprint assignment rationale]

---

### Developer Notes
**Date**: [Date]  
**Author**: [Developer name/agent]

#### Implementation Decisions
- [Decision made during implementation]
- [Another decision]

#### Deviations from Plan
- [What changed and why]

#### Technical Debt Introduced
- [ ] [Debt item] - [Reason/Justification] - [Ticket to address]

#### Blockers Encountered
- [Blocker] - [Resolution]

#### Time Tracking
- Estimated: [X hours]
- Actual: [Y hours]
- Variance reason: [Why different]

---

### QA Notes
**Date**: [Date]  
**Author**: [QA name/agent]

#### Test Results
| Test | Result | Notes |
|------|--------|-------|
| [Test 1] | ✅ Pass / ❌ Fail | [Notes] |
| [Test 2] | ✅ Pass / ❌ Fail | [Notes] |

#### Issues Found
| Issue | Severity | Status | Notes |
|-------|----------|--------|-------|
| [Issue 1] | [High/Med/Low] | [Open/Fixed] | [Details] |

#### Verification Status
- [ ] All acceptance criteria verified
- [ ] No regression in related functionality
- [ ] Performance acceptable
- [ ] Security review passed (if applicable)

#### QA Sign-Off
**Status**: [Approved / Rejected / Needs Rework]  
**Comments**: [Final comments]

---

## Traceability

| Artifact | Reference | Relevant Section |
|----------|-----------|------------------|
| PRD | `phase1/artifacts/prd.md` | [Section] |
| Architecture | `phase1/artifacts/architecture.md` | [Section] |
| Spec | `phase1/artifacts/spec.md` | [User Story ID] |
| Task Breakdown | `phase2/artifacts/task-breakdown.md` | [Task ID] |
| Epic | `phase2/artifacts/epics/[epic-name].md` | N/A |

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | [Date] | [SM] | Initial story creation |
| 1.1 | [Date] | [Dev] | Added dev notes |
| 1.2 | [Date] | [QA] | Added QA results |
```

---

## Usage Guide

### When to Create Story Files

Story files are created during Phase 2 (Planning) or Phase 3 (Implementation):

1. **Task Breakdown** → Identifies stories
2. **Scrum Master** → Creates story files from tasks + sharded context
3. **Developer** → Implements using story file as sole reference
4. **QA** → Validates against acceptance criteria in story file

### How to Create a Story File

```markdown
## Story File Creation Process (Scrum Master)

1. **Identify the story** from task breakdown or epic
2. **Load relevant architecture sections** (shard - don't copy everything)
3. **Extract implementation guidance** from architect notes
4. **Define acceptance criteria** from requirements
5. **Add test guidance** from test plan
6. **Map dependencies** to other stories
7. **Create traceability links** to source artifacts
```

### Sharding Guidelines

When copying context into story files:

✅ **DO**:
- Include ONLY sections relevant to this specific story
- Keep excerpts concise (< 200 lines per section)
- Note the source file and section for reference
- Update if source changes significantly

❌ **DON'T**:
- Copy entire architecture document
- Include irrelevant components or systems
- Duplicate information already in other story files
- Forget to note the source

### Context Size Targets

| Section | Target Size | Maximum |
|---------|-------------|---------|
| Architecture Context | 50-100 lines | 200 lines |
| Implementation Guidance | 20-50 lines | 100 lines |
| Test Guidance | 10-30 lines | 50 lines |
| **Total Story File** | 200-400 lines | 600 lines |

---

## Story Lifecycle

```
┌─────────────────┐
│     DRAFT       │ ← SM creates initial story
└────────┬────────┘
         │ SM completes, adds to backlog
         ▼
┌─────────────────┐
│     READY       │ ← Ready for sprint planning
└────────┬────────┘
         │ Assigned to developer, sprint started
         ▼
┌─────────────────┐
│  IN PROGRESS    │ ← Developer implementing
│                 │   Developer adds notes
└────────┬────────┘
         │ Development complete, PR created
         ▼
┌─────────────────┐
│   IN REVIEW     │ ← Code review + QA
│                 │   QA adds test results
└────────┬────────┘
         │ Reviews passed
         ▼
┌─────────────────┐
│      DONE       │ ← Story complete
└─────────────────┘
```

---

## Integration with Orchestrator

If using SDLCOrchestrator, story files can be:

```json
{
  "storyManagement": {
    "enabled": true,
    "templatePath": ".sdlc/primitives/templates/phase3/story-file_template.md",
    "outputPath": "projects/{project}/phase3/stories/",
    "namingPattern": "{storyId}-{slug}.story.md",
    "autoShard": {
      "enabled": true,
      "maxContextLines": 200,
      "sources": ["architecture", "spec", "testPlan"]
    },
    "lifecycleTracking": {
      "enabled": true,
      "statuses": ["Draft", "Ready", "InProgress", "InReview", "Done"],
      "requireNotes": {
        "InProgress": ["Developer"],
        "Done": ["Developer", "QA"]
      }
    }
  }
}
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
