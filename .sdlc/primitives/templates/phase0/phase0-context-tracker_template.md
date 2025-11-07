# Phase 0 Context Tracker Template

**Purpose**: Maintain current state of Phase 0 discovery session for continuity and context restoration.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/templates/phase0/phase0-context-tracker_template.md`

---

## When to Use This Template

Use this tracker:
- **At session start**: Create initial context file
- **After each interview**: Update progress, findings, artifacts
- **Before session breaks**: Ensure current state is captured
- **For session handoffs**: Transfer context to another facilitator

**Update Frequency**: After every significant activity (interview, synthesis, validation).

---

## Phase 0 Context Tracker

```markdown
# Phase 0 Discovery Context - [Project Name]

**Last Updated**: YYYY-MM-DD HH:MM  
**Updated By**: [Facilitator Name]  
**Session ID**: [session-XXX-project-name]  
**Project**: [Full Project Name]

---

## Quick Status Dashboard

| Metric | Status |
|--------|--------|
| **Phase** | Phase 0: Discovery |
| **Current Step** | Step [N]: [Step Name] |
| **Progress** | [N]% complete |
| **Interviews** | [Completed] / [Planned] |
| **Feasibility Score** | [X]/100 ([Improving/Declining/Stable]) |
| **Risk Count** | [N] risks ([High/Medium/Low breakdown]) |
| **Decision Status** | [GO/NO-GO/NEEDS-MORE-DISCOVERY] |
| **Days in Phase** | [N] days |
| **Next Milestone** | [Description] |

---

## Phase 0 Workflow Progress

Track progress through the 7-step discovery workflow:

### ✅ Step 1: Initiate Discovery (COMPLETE)
- **Completed**: YYYY-MM-DD
- **Key Outputs**: 
  - Initial problem statement (v1)
  - Stakeholder identification
  - Interview plan
- **Duration**: [N] days
- **Notes**: [Any notable observations]

### 🔄 Step 2: Problem Exploration (IN PROGRESS)
- **Started**: YYYY-MM-DD
- **Current Activity**: Interview [N] of [Total]
- **Progress**: [N]% complete
- **Key Outputs So Far**:
  - [Artifact name] - v[N]
  - [Artifact name] - v[N]
- **Active Issues**:
  - [Issue 1]
  - [Issue 2]
- **Notes**: [Current observations]

### ⏳ Step 3: Problem Synthesis (PENDING)
- **Status**: Not started
- **Blocked By**: [What needs to complete first]
- **Expected Start**: YYYY-MM-DD
- **Estimated Duration**: [N] days

### ⏳ Step 4: Feasibility Analysis (ONGOING)
- **Status**: Continuous throughout Step 2
- **Current Assessment**: [Summary]
- **Major Concerns**: [List]
- **Notes**: [Observations]

### ⏳ Step 5: Risk Assessment (ONGOING)
- **Status**: Continuous throughout Step 2
- **Current Risk Count**: [N]
- **Critical Risks**: [List]
- **Notes**: [Observations]

### ⏳ Step 6: Validation (NOT STARTED)
- **Status**: Awaiting Step 2 completion
- **Planned Activities**: [List]

### ⏳ Step 7: Decision & Handoff (NOT STARTED)
- **Status**: Awaiting validation
- **Expected**: YYYY-MM-DD

---

## Interview Tracker

| # | Stakeholder | Role | Status | Date | Key Themes | Delta? |
|---|-------------|------|--------|------|------------|--------|
| 1 | [Name] | [Role] | ✅ Complete | YYYY-MM-DD | [Theme 1, Theme 2] | Yes - v1→v2 |
| 2 | [Name] | [Role] | ✅ Complete | YYYY-MM-DD | [Theme 1, Theme 2] | Yes - v2→v3 |
| 3 | [Name] | [Role] | ✅ Complete | YYYY-MM-DD | [Theme 1, Theme 2] | No |
| 4 | [Name] | [Role] | 🔄 In Progress | YYYY-MM-DD | [In progress] | TBD |
| 5 | [Name] | [Role] | ⏳ Scheduled | YYYY-MM-DD | Not started | - |
| 6 | [Name] | [Role] | 📋 Planned | TBD | Not started | - |

**Interview Coverage**:
- ✅ Executive perspective: [N] interviews
- ✅ Technical perspective: [N] interviews
- ✅ Operations perspective: [N] interviews
- 🔄 End-user perspective: [N] interviews (need [N] more)
- ⏳ Support perspective: [N] interviews (planned)

**Theme Saturation Status**:
- Theme 1: [Saturated/Still Emerging] - Appeared in interviews [1, 3, 5]
- Theme 2: [Saturated/Still Emerging] - Appeared in interviews [2, 4, 6]
- Theme 3: [Just Emerged] - Appeared in interview [7]

---

## Artifact Version Control

Track all working artifacts and their current versions:

### Problem Statement
- **Location**: `working/problem-statement.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Status**: [Draft/Under Review/Validated]
- **Confidence**: [High/Medium/Low]
- **Changes in Last Update**: [Summary]
- **Outstanding Issues**: [List]

### Feasibility Assessment
- **Location**: `working/feasibility-assessment.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Current Score**: [X]/100
- **Score Trend**: [Graph or arrow indicating trend]
- **Major Concerns**: [List]
- **Outstanding Items**: [List]

### Risk Register
- **Location**: `working/risk-register.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Total Risks**: [N]
- **Breakdown**:
  - Critical: [N]
  - High: [N]
  - Medium: [N]
  - Low: [N]
- **New Since Last Update**: [List]
- **Escalations**: [List]

### Contradiction Log
- **Location**: `working/contradiction-log.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Active Contradictions**: [N]
- **Resolved**: [N]
- **Critical Unresolved**: [List]

### Stakeholder Map
- **Location**: `working/stakeholder-map.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Total Stakeholders**: [N]
- **Veto Powers Identified**: [N]
- **Trust Hierarchy Mapped**: [Yes/Partial/No]

### Success Criteria
- **Location**: `working/success-criteria.md`
- **Current Version**: v[N]
- **Last Updated**: YYYY-MM-DD
- **Criteria Defined**: [N]
- **Validated By**: [Stakeholder list]
- **Measurability**: [All Measurable/Some Vague/Needs Work]

---

## Delta Updates Applied

Track all significant updates to artifacts:

| Date | Artifact | Version Change | Trigger | Impact Score | Notes |
|------|----------|----------------|---------|--------------|-------|
| YYYY-MM-DD | Feasibility | v1 → v2 | Interview 2 | -15 points | Timeline concerns raised |
| YYYY-MM-DD | Risk Register | v2 → v3 | Interview 3 | +3 risks | Compliance issues identified |
| YYYY-MM-DD | Problem Statement | v1 → v2 | Interview 4 | Scope expanded | User needs broader than assumed |

---

## Key Findings & Insights

### Major Discoveries
1. **[Finding 1]**
   - Source: Interview [N] with [Person]
   - Impact: [Description]
   - Status: [Validated/Needs Confirmation]

2. **[Finding 2]**
   - Source: Interview [N] with [Person]
   - Impact: [Description]
   - Status: [Validated/Needs Confirmation]

### Patterns Emerging
- **Pattern 1**: [Description] - Observed in interviews [N, N, N]
- **Pattern 2**: [Description] - Observed in interviews [N, N, N]

### Contradictions
- **Contradiction 1**: [Person A says X, Person B says Y]
  - Status: [Unresolved/Investigating/Resolved]
  - Impact: [Description]
  - Resolution Approach: [Plan]

### Red Flags
- 🚩 **[Red Flag 1]**: [Description]
  - Severity: [Critical/High/Medium]
  - Source: [Where identified]
  - Action: [What we're doing about it]

---

## Decision Factors Tracking

Track factors influencing GO/NO-GO decision:

### Positive Factors (GO signals)
- ✅ [Factor 1]
- ✅ [Factor 2]
- ✅ [Factor 3]

### Concerns (Proceed with Caution signals)
- ⚠️ [Concern 1]
- ⚠️ [Concern 2]

### Blockers (NO-GO signals)
- 🛑 [Blocker 1]
- 🛑 [Blocker 2]

### Current Recommendation
**Status**: [GO / CONDITIONAL GO / NO-GO / NEED MORE DISCOVERY]

**Rationale**: [1-2 sentence explanation of current assessment]

**Confidence**: [High/Medium/Low] - [Why]

---

## Open Questions

Questions that need answering before decision:

| # | Question | Why Critical | Who Can Answer | Status | Target Date |
|---|----------|--------------|----------------|--------|-------------|
| 1 | [Question] | [Impact if unanswered] | [Stakeholder] | Open | YYYY-MM-DD |
| 2 | [Question] | [Impact if unanswered] | [Stakeholder] | In Progress | YYYY-MM-DD |
| 3 | [Question] | [Impact if unanswered] | [Stakeholder] | Answered | YYYY-MM-DD |

---

## Next Actions

### Immediate (Today/Tomorrow)
- [ ] [Action 1]
- [ ] [Action 2]
- [ ] [Action 3]

### Short-term (This Week)
- [ ] [Action 1]
- [ ] [Action 2]

### Medium-term (Next 2 Weeks)
- [ ] [Action 1]
- [ ] [Action 2]

---

## Session Context

### Methodology Components Loaded
- ✅ Discovery Facilitator Instructions
- ✅ Phase 0 Configuration
- ✅ Discovery Workflow
- ✅ Interview Workflow
- ✅ Templates (Interview, Feasibility, Risk, Problem Statement)
- ⚠️ Synthesis Agent Instructions (not yet needed)
- ⏳ Validation Checklist (not yet needed)

### Organizational Context
- **Industry**: [Industry]
- **Company Size**: [Size]
- **Key Constraints**: [List]
- **Cultural Factors**: [List]
- **Prior Failed Projects**: [Any relevant history]

### Project Background
- **Strategic Driver**: [Why now?]
- **Executive Sponsor**: [Name, Role]
- **Budget Range**: $[Min] - $[Max]
- **Timeline Expectation**: [Range]
- **Success Metric**: [Primary measure]

---

## Lessons Learned (This Session)

Document learnings as you go:

**What's Working Well**:
- [Observation 1]
- [Observation 2]

**What Could Be Better**:
- [Observation 1]
- [Observation 2]

**Process Improvements to Consider**:
- [Idea 1]
- [Idea 2]

**Methodology Refinements Needed**:
- [Template update needed]
- [Workflow clarification needed]

---

## Session Metadata

**Created**: YYYY-MM-DD  
**Session Directory**: `discovery-sessions/session-XXX-project-name/`  
**GitHub Repo**: [If applicable]  
**Documentation Location**: [Where artifacts live]  
**Backup Status**: [Last backed up]  
**Collaboration**: [Who else is involved]

---

## Notes & Observations

Free-form notes for context that doesn't fit elsewhere:

[Your notes here]
```

---

## Usage Instructions

### Initial Setup (Session Start)

1. **Create Context File**
   - Copy this template
   - Save as: `discovery-sessions/session-XXX-project/phase0-context.md`
   - Fill in header and Quick Status Dashboard

2. **Initialize Trackers**
   - List all planned interviews
   - List all artifacts being tracked
   - Set initial scores/metrics

3. **Load Methodology**
   - Check off which components are loaded
   - Ensure all facilitators have access

### Ongoing Maintenance

**After Each Interview**:
- Update interview tracker
- Note key themes discovered
- Flag if delta update required
- Update Quick Status Dashboard

**After Artifact Updates**:
- Update artifact version control section
- Record delta in delta updates table
- Update any affected scores/metrics

**Daily/Weekly**:
- Review and update next actions
- Check open questions status
- Update decision factors
- Add lessons learned

### Session Handoff

**When handing off to another facilitator**:
1. Ensure context tracker is current
2. Review "Next Actions" section together
3. Highlight any critical open questions
4. Transfer any tribal knowledge to "Notes" section

### Context Restoration

**When resuming after break**:
1. Read Quick Status Dashboard
2. Review last 3 delta updates
3. Check open questions
4. Review next actions
5. Scan lessons learned

---

## Example Excerpt

```markdown
# Phase 0 Discovery Context - Contoso Azure Modernization

**Last Updated**: 2024-10-15 14:30  
**Updated By**: Discovery Team  
**Session ID**: session-001-contoso-azure  
**Project**: Azure Cloud Modernization for Manufacturing Operations

---

## Quick Status Dashboard

| Metric | Status |
|--------|--------|
| **Phase** | Phase 0: Discovery |
| **Current Step** | Step 2: Problem Exploration |
| **Progress** | 55% complete |
| **Interviews** | 6 / 11 |
| **Feasibility Score** | 45/100 (Declining) |
| **Risk Count** | 23 risks (7 Critical, 9 High, 5 Medium, 2 Low) |
| **Decision Status** | NEEDS-MORE-DISCOVERY |
| **Days in Phase** | 8 days |
| **Next Milestone** | Complete floor supervisor interviews |

---

## Interview Tracker

| # | Stakeholder | Role | Status | Date | Key Themes | Delta? |
|---|-------------|------|--------|------|------------|--------|
| 1 | Michael Chen | CTO | ✅ Complete | 2024-10-08 | Digital transformation, timeline pressure | Yes - v1→v2 |
| 2 | Sarah Kim | IT Director | ✅ Complete | 2024-10-09 | Technical debt, maintenance windows | Yes - v2→v3 |
| 3 | Jennifer Martinez | CFO | ✅ Complete | 2024-10-10 | Budget constraints, PE expectations | Yes - v3→v4 |
| 4 | Robert Chen | Operations Director | ✅ Complete | 2024-10-11 | 24/7 ops, change aversion | Yes - v4→v5 |
| 5 | David Park | QA Manager | ✅ Complete | 2024-10-14 | Regulatory compliance, validation | Yes - v5→v6 |
| 6 | Maria Rodriguez | Floor Supervisor | ✅ Complete | 2024-10-15 | Training needs, shift dynamics | Yes - v6→v7 |
| 7 | Tom Brennan | Support Lead | 🔄 In Progress | 2024-10-15 | [In progress] | TBD |

**Theme Saturation Status**:
- Maintenance window constraints: Saturated - Appeared in interviews 2, 4, 6
- Training inadequacy: Just Emerged - Appeared in interview 6
- Budget mismatch: Saturated - Appeared in interviews 1, 3, 4
```

---

## File Metadata

**Template Version**: 1.0  
**Intended For**: Active Phase 0 discovery sessions  
**Update Frequency**: After each interview or significant event  
**Maintenance**: Keep current throughout Phase 0  
**Related**: 
- `session-bridge.prompt.md` (uses this file for context restoration)
- `artifact-delta-update_template.md` (records tracked here)
- `phase0_config.md` (configuration this tracker follows)
