# Artifact Delta Update Template

**Purpose**: Track incremental changes to Phase 0 artifacts throughout the discovery process.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/templates/phase0/artifact-delta-update_template.md`

---

## When to Use This Template

Use delta updates when:
- An interview reveals new information requiring artifact updates
- Contradictions are discovered requiring reconciliation
- Risk scores or feasibility assessments change
- Stakeholder alignment shifts

**DO NOT use for**: Initial artifact creation (use the base templates) or final versions (use artifact-name.final.md).

---

## Delta Update Document

```markdown
# Delta Update: [Artifact Name] - v[N] to v[N+1]

**Update Date**: YYYY-MM-DD  
**Session**: [Session ID - e.g., session-001-contoso-azure]  
**Updated By**: [Facilitator name]  
**Trigger**: [What caused this update]

---

## Update Trigger Context

**Source**: Interview [N] with [Stakeholder Name + Role]  
**Key Findings**: 
- [Finding 1]
- [Finding 2]
- [Finding 3]

**Why Update Required**: [1-2 sentence explanation of why this necessitates artifact changes]

---

## Changes Made

### Additions

**New Sections Added**:
- **[Section Name]**: [Why added]
  - Source: [Interview N with Person]
  - Content summary: [Brief description]
  - Confidence: [High/Medium/Low]

**New Items in Existing Sections**:
- **[Section] → [Item Added]**: [Description]
  - Source: [Interview N]
  - Rationale: [Why this matters]
  - Dependencies: [What depends on this]

---

### Modifications

**Changed Assessments**:
- **[Assessment Changed]**: 
  - **Previous**: [Old value/description]
  - **New**: [New value/description]
  - **Change Magnitude**: [+/- amount or significant/moderate/minor]
  - **Reason**: [Why changed - cite source]
  - **Validated By**: [Stakeholder who confirmed or contradicted]

**Updated Estimates**:
- **[Estimate Type]**: 
  - **Was**: [Original estimate]
  - **Now**: [Updated estimate]
  - **Variance**: [Percentage or absolute difference]
  - **Impact**: [What this affects]

**Refined Descriptions**:
- **[Section/Item]**: 
  - **Enhancement**: [What was clarified/refined]
  - **Source**: [Where better info came from]

---

### Removals

**Deprecated Sections**:
- **[Section Removed]**: [Why removed]
  - Reason for deprecation: [Invalidated by what]
  - Moved to: [If relocated to another artifact]

**Deleted Items**:
- **[Item Removed]**: [Why removed]
  - Superseded by: [What replaced it, if applicable]

---

## Impact Analysis

### Quantitative Changes

**Feasibility Score**:
- Previous: [X]/100
- Current: [Y]/100
- Delta: [+/- Z] points
- Trend: [Improving/Declining/Stable]
- Interpretation: [What this means]

**Risk Register**:
- Previous Risk Count: [X]
- Current Risk Count: [Y]
- Net Change: [+/- Z] risks
- Breakdown:
  - New Risks: [Count] - [Brief list]
  - Escalated Risks: [Count] - [Which ones]
  - Mitigated Risks: [Count] - [Which ones]

**Timeline Estimates**:
- Previous Range: [Min-Max months]
- Current Range: [Min-Max months]
- Shift: [+/- months]
- Confidence: [Higher/Lower/Same]

**Budget Estimates**:
- Previous Range: $[Min]-$[Max]
- Current Range: $[Min]-$[Max]
- Variance: [+/- $amount or %]
- Confidence: [Higher/Lower/Same]

---

### Qualitative Changes

**Stakeholder Alignment**:
- Previous State: [Description]
- Current State: [Description]
- Change: [Improved/Worsened/Unchanged]
- Key Shifts: [What changed in stakeholder positions]

**Contradictions**:
- Previous: [X] unresolved contradictions
- Current: [Y] unresolved contradictions
- Resolved: [List which contradictions were resolved]
- New: [List new contradictions discovered]

**Confidence Level**:
- Previous: [High/Medium/Low] confidence in [aspect]
- Current: [High/Medium/Low] confidence
- Reason: [Why confidence changed]

---

## Cascading Updates Required

**Other Artifacts Affected**:
- **[Artifact Name]**: [What needs to update in that artifact]
  - Section: [Specific section]
  - Type: [Add/Modify/Remove]
  - Priority: [Urgent/Normal/Low]

**Validation Needed**:
- [ ] Cross-check with [Related Artifact]
- [ ] Validate with [Stakeholder]
- [ ] Update traceability matrix
- [ ] Recalculate [Dependent calculation]

---

## Next Actions

**Immediate** (Do before next interview):
- [ ] [Action 1]
- [ ] [Action 2]

**Short-term** (Within current step):
- [ ] [Action 1]
- [ ] [Action 2]

**Before Phase Completion**:
- [ ] [Action 1]
- [ ] [Action 2]

---

## Update Log

| Version | Date | Trigger | Change Summary | Confidence |
|---------|------|---------|----------------|------------|
| v1 | YYYY-MM-DD | Initial creation | Created base artifact | Medium |
| v2 | YYYY-MM-DD | Interview 3 | Added risk X, updated timeline | Medium |
| v3 | YYYY-MM-DD | Interview 5 | Contradiction resolved, feasibility dropped | High |
| v[N+1] | YYYY-MM-DD | [This update] | [Summary of this delta] | [Level] |

---

## Notes

**Open Questions**:
- [Question that needs answering]
- [Assumption that needs validating]

**Parking Lot** (Items noted but not yet actioned):
- [Item 1]
- [Item 2]

**Lessons Learned**:
- [What did we learn from this update process?]
```

---

## Usage Instructions

### How to Create a Delta Update

**Step 1: Copy Template**
- Create new file: `working/[artifact-name]-delta-v[N]-to-v[N+1].md`
- Copy this template

**Step 2: Fill Header**
- Date, trigger, facilitator name
- Brief context of what prompted the update

**Step 3: Document Changes**
- Be specific: What changed, why, and based on what source
- Always cite the interview/source that drove the change
- Quantify changes where possible

**Step 4: Analyze Impact**
- Update scores, counts, estimates
- Identify cascading effects on other artifacts
- Note validation needs

**Step 5: Plan Next Steps**
- What needs to happen now
- What can wait
- What needs stakeholder confirmation

**Step 6: Update Artifact**
- Apply changes to the working artifact file
- Increment version number
- Archive the delta document for traceability

---

## Example Excerpt

```markdown
# Delta Update: Feasibility Assessment - v2 to v3

**Update Date**: 2024-10-15  
**Session**: session-001-contoso-azure  
**Updated By**: Discovery Team  
**Trigger**: Interview 5 revealed maintenance window constraints

---

## Update Trigger Context

**Source**: Interview 5 with Sarah Kim (IT Director)  
**Key Findings**: 
- Only 4 Sunday maintenance windows per year (48 hours total)
- Each system requires minimum 8 hours downtime for major changes
- No flexibility to extend windows due to 24/7 operations

**Why Update Required**: The maintenance window constraints mathematically invalidate the 18-month timeline assumption.

---

## Changes Made

### Modifications

**Changed Assessments**:
- **Timeline Feasibility**: 
  - **Previous**: 18 months (optimistic but possible)
  - **New**: 36-48 months (realistic given constraints)
  - **Change Magnitude**: 2-3x longer
  - **Reason**: 48 hours/year ÷ 8 hours/migration = 6 systems/year. With 8 systems = 1.3 years minimum. Add testing, rollback capacity, contingency = 36-48 months.
  - **Validated By**: Sarah Kim confirmed calculation, Robert Chen (Operations) confirmed no window flexibility

---

## Impact Analysis

### Quantitative Changes

**Feasibility Score**:
- Previous: 68/100
- Current: 45/100
- Delta: -23 points
- Trend: Declining sharply
- Interpretation: Timeline constraint creates major feasibility concern. Project is no longer "challenging but achievable" - now "requires significant scope or timeline changes."

**Timeline Estimates**:
- Previous Range: 18-24 months
- Current Range: 36-48 months
- Shift: +18-24 months
- Confidence: High (mathematically proven constraint)
```

---

## File Metadata

**Template Version**: 1.0  
**Intended For**: Phase 0 discovery working artifacts  
**Maintenance**: Update this template if delta tracking patterns emerge  
**Related**: 
- `problem-statement_template.md` (what gets updated)
- `feasibility-report_template.md` (what gets updated)
- `risk-register_template.md` (what gets updated)
- `phase0-context-tracker_template.md` (tracks these deltas)
