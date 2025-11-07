# Phase 0 Session Tracker Template

**Purpose**: Track current state of Phase 0 discovery session for continuity and context restoration.

**Version**: 2.0 (Streamlined)  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/templates/phase0/phase0-session-tracker_template.md`

---

## When to Use This Template

Use this tracker:
- **At session start**: Create initial tracker file
- **After each interview**: Update progress, findings, artifacts
- **Before session breaks**: Ensure current state is captured
- **For session handoffs**: Transfer context to another facilitator

**Update Frequency**: After every significant activity (interview, synthesis, validation).

**Note**: This tracker focuses on SESSION STATE only. Organizational context (company info, tech stack, culture) is maintained separately in `.sdlc/memory/context.template.md`.

---

## Phase 0 Session Tracker

```markdown
# Phase 0 Session Tracker - [Project Name]

**Last Updated**: YYYY-MM-DD HH:MM  
**Updated By**: [Facilitator Name]  
**Session ID**: [session-XXX-project-name]  
**Session Directory**: `discovery-sessions/session-XXX-project-name/`

**Organizational Context**: See `.sdlc/memory/context.template.md` for company background, tech stack, and culture.

---

## Quick Status

| Metric | Current Value |
|--------|---------------|
| **Phase** | Phase 0: Discovery |
| **Current Step** | Step [N]: [Step Name] |
| **Overall Progress** | [N]% complete |
| **Interviews** | [Completed] / [Planned] |
| **Feasibility Score** | [X]/100 ([Trend: ↑↓→]) |
| **Risk Count** | [N] total ([Critical/High/Med/Low]) |
| **Decision Readiness** | [GO/NO-GO/NEEDS-MORE-DISCOVERY] |
| **Days in Discovery** | [N] days |
| **Next Milestone** | [Description] |

---

## Workflow Progress

Current position in the 7-step discovery workflow:

- [ ] **Step 1**: Initiate Discovery
- [ ] **Step 2**: Problem Exploration  
- [ ] **Step 3**: Problem Synthesis
- [ ] **Step 4**: Feasibility Analysis
- [ ] **Step 5**: Risk Assessment
- [ ] **Step 6**: Validation
- [ ] **Step 7**: Decision & Handoff

**Current Step Details**:
- **Step**: [N] - [Name]
- **Status**: [Not Started / In Progress / Complete]
- **Started**: YYYY-MM-DD
- **Expected Completion**: YYYY-MM-DD
- **Key Activities Remaining**: [List 2-3]

---

## Interview Tracker

| # | Stakeholder | Role | Status | Date | Key Themes | Delta Created? |
|---|-------------|------|--------|------|------------|----------------|
| 1 | [Name] | [Role] | ✅ | YYYY-MM-DD | [Theme1, Theme2] | Yes/No |
| 2 | [Name] | [Role] | ✅ | YYYY-MM-DD | [Theme1, Theme2] | Yes/No |
| 3 | [Name] | [Role] | 🔄 | YYYY-MM-DD | [In progress] | TBD |
| 4 | [Name] | [Role] | ⏳ | YYYY-MM-DD | [Scheduled] | - |

**Coverage Status**:
- Executive: [N] completed / [N] planned
- Technical: [N] completed / [N] planned  
- Operations: [N] completed / [N] planned
- End Users: [N] completed / [N] planned
- Support: [N] completed / [N] planned

**Theme Saturation**: [Achieved / Still Emerging]

---

## Artifact Status

Track current version and state of all working artifacts:

| Artifact | Version | Last Updated | Status | Confidence |
|----------|---------|--------------|--------|------------|
| Problem Statement | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |
| Feasibility Assessment | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |
| Risk Register | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |
| Success Criteria | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |
| Stakeholder Map | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |
| Contradiction Log | v[N] | YYYY-MM-DD | Draft/Review/Final | High/Med/Low |

**Artifact Locations**:
- Working versions: `working/`
- Delta updates: `working/deltas/`
- Final versions: `artifacts/`

---

## Key Metrics

### Feasibility Score Trend

| Date | Score | Change | Trigger |
|------|-------|--------|---------|
| YYYY-MM-DD | [X]/100 | Initial | Session start |
| YYYY-MM-DD | [Y]/100 | [±Z] | Interview [N] |
| YYYY-MM-DD | [Y]/100 | [±Z] | Interview [N] |

**Current Assessment**: [Description of what score means]

### Risk Register Summary

| Severity | Count | Key Risks |
|----------|-------|-----------|
| Critical (20-25) | [N] | [Risk 1, Risk 2] |
| High (12-19) | [N] | [Risk 1, Risk 2] |
| Medium (6-11) | [N] | [Count only] |
| Low (1-5) | [N] | [Count only] |

**Top 3 Risks**:
1. [Risk name] - Score [X] - [Brief description]
2. [Risk name] - Score [X] - [Brief description]
3. [Risk name] - Score [X] - [Brief description]

---

## Critical Findings

### Major Discoveries

1. **[Finding 1]**
   - Source: Interview [N] with [Person]
   - Impact: [Description]
   - Status: [Validated/Needs Confirmation]

2. **[Finding 2]**
   - Source: Interview [N] with [Person]
   - Impact: [Description]
   - Status: [Validated/Needs Confirmation]

### Unresolved Contradictions

- **[Person A] vs [Person B]**: [Description]
  - Impact: [High/Med/Low]
  - Resolution Approach: [Plan]

### Red Flags

- 🚩 **[Red Flag 1]**: [Description] - [Severity]
- 🚩 **[Red Flag 2]**: [Description] - [Severity]

---

## Decision Factors

### GO Signals ✅
- [Factor 1]
- [Factor 2]

### Concerns ⚠️
- [Concern 1]
- [Concern 2]

### Blockers 🛑
- [Blocker 1] (if any)

**Current Recommendation**: [GO / CONDITIONAL GO / NO-GO / NEED MORE DISCOVERY]

**Confidence Level**: [High/Medium/Low]

**Rationale**: [1-2 sentences]

---

## Open Questions

| Priority | Question | Why Critical | Who Can Answer | Target Date |
|----------|----------|--------------|----------------|-------------|
| P0 | [Question] | [Impact] | [Stakeholder] | YYYY-MM-DD |
| P1 | [Question] | [Impact] | [Stakeholder] | YYYY-MM-DD |

---

## Next Actions

### Immediate (Today/Tomorrow)
- [ ] [Action 1]
- [ ] [Action 2]

### This Week
- [ ] [Action 1]
- [ ] [Action 2]

### Next 2 Weeks
- [ ] [Action 1]
- [ ] [Action 2]

---

## Session Notes

**What's Working Well**:
- [Observation 1]
- [Observation 2]

**Challenges**:
- [Challenge 1]
- [Challenge 2]

**Process Improvements Needed**:
- [Idea 1]
- [Idea 2]

---

## Files & References

**Session Directory**: `discovery-sessions/session-XXX-project-name/`

**Key Files**:
- Interviews: `interviews/*.md`
- Working artifacts: `working/*.md`
- Delta updates: `working/deltas/*.md`
- This tracker: `phase0-session-tracker.md`

**Organizational Context** (load for full context):
- Company background: `.sdlc/memory/context.template.md`
- Lessons learned: `.sdlc/memory/lessons-learned.memory.md`
- Prior projects: `.sdlc/memory/prior-projects.memory.md`

**Methodology Resources**:
- Agent instructions: `.sdlc/primitives/agents/phase0/*.md`
- Workflows: `.sdlc/primitives/workflows/phase0/*.md`
- Templates: `.sdlc/primitives/templates/phase0/*.md`

---

## Session Metadata

**Created**: YYYY-MM-DD  
**Project Type**: [e.g., Cloud Migration, System Modernization]  
**Strategic Driver**: [Why now?]  
**Executive Sponsor**: [Name, Role]  
**Budget Range**: $[Min] - $[Max]  
**Timeline Expectation**: [Min] - [Max] months  

---

_Last updated by [Name] on YYYY-MM-DD at HH:MM_
```

---

## Usage Instructions

### Initial Setup

1. **Copy this template** to your session directory:
   ```
   cp phase0-session-tracker_template.md \
      discovery-sessions/session-XXX-project-name/phase0-session-tracker.md
   ```

2. **Fill in header** (session ID, project name, dates)

3. **Set initial status** (all steps unchecked, 0 interviews, initial scores)

4. **Reference organizational context** - Don't duplicate it here; just reference `.sdlc/memory/context.template.md`

### Ongoing Updates

**After Each Interview**:
- Update interview tracker (mark complete, add themes)
- Note if delta update was created
- Update metrics if changed (feasibility score, risk count)
- Add to "Critical Findings" if major discovery
- Update "Next Actions"

**Daily/Weekly**:
- Review and update next actions
- Check open questions status
- Update decision factors
- Add session notes

**Before Session Break**:
- Ensure all sections are current
- Update "Last updated" timestamp
- Review "Next Actions" so you remember when you return

### For Context Restoration

When resuming work (new conversation), load:
1. This session tracker (current state)
2. `.sdlc/memory/context.template.md` (organizational context)
3. Current working artifacts (latest versions)
4. Recent interview transcripts (last 2-3)

---

## File Metadata

**Template Version**: 2.0 (Streamlined)  
**Changes from v1.0**: Removed organizational context sections (now in `.sdlc/memory/context.template.md`)  
**Intended For**: Active Phase 0 discovery sessions  
**Update Frequency**: After each interview or significant event  
**Related**: 
- `.sdlc/memory/context.template.md` (organizational context - load this too)
- `session-bridge.prompt.md` (uses this file for context restoration)
- `artifact-delta-update_template.md` (deltas tracked here)
