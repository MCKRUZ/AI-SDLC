# Artifact Delta Update Template

**Purpose**: Standardized format for documenting incremental changes to Phase 0 artifacts.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/templates/phase0/artifact-delta_template.md`

---

## When to Use This Template

Use this template to document changes when:
- Updating an artifact based on new interview insights
- Incorporating stakeholder feedback
- Refining based on additional analysis
- Resolving contradictions
- Addressing validation gaps

**DO NOT use for**:
- Initial artifact creation (use the main artifact templates)
- Complete rewrites (create new version instead)

---

## Delta Update Document Structure

```markdown
# Artifact Delta Update - [Artifact Name]

**Artifact**: [e.g., Problem Statement / Feasibility Report / Risk Register / Success Criteria]  
**Update Date**: [YYYY-MM-DD]  
**Previous Version**: [e.g., v1 / v2]  
**New Version**: [e.g., v2 / v3]  
**Updated By**: [Name/Role]  
**Session**: [Session number if applicable]

---

## Update Trigger

**What prompted this update?**

[Check all that apply]
- [ ] New interview(s) completed: Interview #[N] with [Role]
- [ ] Stakeholder feedback received from: [Name/Role]
- [ ] Contradiction identified that needed resolution
- [ ] Five Whys analysis revealed deeper root cause
- [ ] Quantitative data obtained that wasn't available before
- [ ] Validation gap identified in review
- [ ] Other: [Describe]

**Specific Trigger Description**:
[1-2 sentences explaining exactly what prompted this update]

---

## Summary of Changes

**High-Level Summary**:
[2-3 sentences describing what changed and why]

**Change Magnitude**: [Minor / Moderate / Significant]
- Minor: Clarifications, typo fixes, minor additions (<10% of content)
- Moderate: New sections, substantial additions (10-30% of content)
- Significant: Major restructuring, new insights (>30% of content)

**Change Type**: [Additive / Corrective / Refinement / Restructure]

---

## Detailed Changes

### 1. Additions

**New content added to the artifact:**

#### Addition 1: [Section Name or Topic]
- **Location**: [Section/subsection where added]
- **Content Added**: [Brief description of what was added]
- **Rationale**: [Why this was added]
- **Source**: [Interview #N with Role, or other source]
- **Impact**: [How this changes understanding]

**Example**:
```
Addition 1: Technical Constraint - Legacy System Dependencies

Location: Section 4 - Constraints
Content Added: Added constraint about 15-year-old ERP system that can't be decommissioned until Q4 2026 due to audit requirements
Rationale: Interview #5 with CTO revealed this critical timeline dependency that affects migration sequencing
Source: Interview #005-cto-interview.md, page 3
Impact: Extends minimum timeline from 12 months to 18 months
```

#### Addition 2: [Section Name or Topic]
[Repeat structure]

[Continue for all additions]

---

### 2. Modifications

**Existing content that was changed:**

#### Modification 1: [Section Name or Topic]
- **Location**: [Section/subsection that was modified]
- **Original Content**: [What it said before]
- **Updated Content**: [What it says now]
- **Rationale**: [Why this was changed]
- **Source**: [What informed this change]
- **Impact**: [How this affects understanding]

**Example**:
```
Modification 1: Business Impact Quantification

Location: Section 2 - Business Impact
Original Content: "Customer complaints have increased significantly"
Updated Content: "Customer complaints increased 340% YoY (from 12/month to 53/month), resulting in estimated $180K in churn"
Rationale: Interview #3 with Support Lead provided specific metrics
Source: Interview #003-support-lead-interview.md, Support ticket data referenced
Impact: Strengthens business case with quantified impact
```

#### Modification 2: [Section Name or Topic]
[Repeat structure]

[Continue for all modifications]

---

### 3. Removals

**Content that was removed or replaced:**

#### Removal 1: [Section Name or Topic]
- **Location**: [Section/subsection where removed]
- **Content Removed**: [Brief description of what was removed]
- **Rationale**: [Why this was removed]
- **Replaced With**: [What replaced it, or "Nothing - content was incorrect"]
- **Impact**: [How this changes understanding]

**Example**:
```
Removal 1: Incorrect Timeline Assumption

Location: Section 7 - Success Criteria, Timeline metric
Content Removed: "Project can be completed in 6 months"
Rationale: Interview #4 with Dev Lead revealed 6-month timeline is impossible due to testing requirements
Replaced With: "Project requires minimum 12 months (6 months development + 6 months testing/validation)"
Impact: Timeline expectations now realistic based on operational constraints
```

#### Removal 2: [Section Name or Topic]
[Repeat structure]

[Continue for all removals]

---

### 4. Contradiction Resolutions

**Contradictions addressed in this update:**

#### Contradiction 1: [Topic]
- **Stakeholders Involved**: [Role A] vs [Role B]
- **Contradiction**: [Describe the conflicting information]
- **Resolution Approach**: [How we resolved it]
- **Outcome**: [What we determined to be accurate]
- **Artifact Impact**: [How artifact was updated]

**Example**:
```
Contradiction 1: Project Budget

Stakeholders Involved: CEO vs CFO
Contradiction: CEO stated budget is $500K; CFO stated maximum available is $300K with additional $200K requiring board approval
Resolution Approach: Scheduled alignment meeting with both; reviewed actual budget allocation documents
Outcome: Current approved budget is $300K; $200K additional is contingent on Phase 0 feasibility results
Artifact Impact: Updated budget constraint section to reflect $300K firm, $500K conditional
```

#### Contradiction 2: [Topic]
[Repeat structure]

[Continue for all contradictions addressed]

---

### 5. Root Cause Deepening

**Five Whys analysis that was extended:**

#### Root Cause Update 1: [Topic]
- **Original Root Cause** (from previous version): [What we thought]
- **Deepened Analysis**: [Additional Why questions asked]
- **New/Refined Root Cause**: [What we now understand]
- **Source**: [Interview that revealed deeper layer]
- **Artifact Impact**: [How problem statement or analysis updated]

**Example**:
```
Root Cause Update 1: Why customers aren't using mobile app

Original Root Cause (v1): "App is slow"
Deepened Analysis (v2): 
- Why is app slow? → Large image files
- Why large image files? → No compression
- Why no compression? → Dev team didn't know how
- Why didn't they know? → No training budget
- Why no training budget? → Company prioritizes shipping features over quality

New/Refined Root Cause: Company culture prioritizes speed over quality, leading to technical debt accumulation and lack of engineering best practices
Source: Interview #006-dev-lead-interview.md
Artifact Impact: Problem statement now addresses organizational/cultural dimension, not just technical
```

[Continue for all root cause deepening]

---

## Impact Analysis

### Artifact Quality Impact

**Before This Update**:
- Quality Score: [X]/10
- Completeness: [X]%
- Evidence Support: [Strong / Moderate / Weak]
- Clarity: [High / Medium / Low]

**After This Update**:
- Quality Score: [Y]/10 (△ [+/-Z])
- Completeness: [Y]% (△ [+/-Z]%)
- Evidence Support: [Strong / Moderate / Weak]
- Clarity: [High / Medium / Low]

**Key Quality Improvements**:
- [Improvement 1]
- [Improvement 2]
- [Improvement 3]

### Downstream Impact

**How this update affects other artifacts:**

| Affected Artifact | Impact | Action Required |
|-------------------|--------|-----------------|
| [e.g., Feasibility Report] | [Description of impact] | [✅ Updated / ⏳ Needs Update / ➖ No action needed] |
| [e.g., Risk Register] | [Description of impact] | [✅ Updated / ⏳ Needs Update / ➖ No action needed] |
| [e.g., Success Criteria] | [Description of impact] | [✅ Updated / ⏳ Needs Update / ➖ No action needed] |

### Phase 0 Metrics Impact

**Feasibility Score**: [Previous: X/100] → [Current: Y/100] (△ [+/-Z])
- Technical: [X→Y]
- Business: [X→Y]
- Resource: [X→Y]
- Timeline: [X→Y]

**Risk Count**: [Previous: X] → [Current: Y] (△ [+/-Z])
- Critical (≥20): [X→Y]
- High (15-19): [X→Y]
- Medium (10-14): [X→Y]
- Low (<10): [X→Y]

**Timeline Estimate**: [Previous: X months] → [Current: Y months] (△ [+/-Z])

**Budget Estimate**: [Previous: $X] → [Current: $Y] (△ [+/-$Z])

**Recommendation**: [Previous: GO/CONDITIONAL/NO-GO] → [Current: GO/CONDITIONAL/NO-GO]

---

## Validation

### Change Validation Checklist

Verify this update maintains artifact quality:

- [ ] All new claims are supported by interview evidence or analysis
- [ ] Sources are cited (interview #, document, data source)
- [ ] Contradictions are resolved or explicitly noted as unresolved
- [ ] Root causes are traced (Five Whys applied)
- [ ] Quantitative data is included where possible
- [ ] Technical accuracy verified (if applicable)
- [ ] Logical consistency maintained across artifact
- [ ] New content uses appropriate template sections
- [ ] Cross-references to other artifacts updated

### Stakeholder Review

**Reviewed By**: [Name/Role] on [YYYY-MM-DD]  
**Review Outcome**: [✅ Approved / 🔄 Revisions Requested / ❌ Rejected]  
**Feedback**: [Summary of reviewer feedback]  
**Actions Taken**: [How feedback was addressed]

---

## Next Steps

### Immediate Actions

1. **[Action]**
   - Owner: [Name/Role]
   - Due: [Date]
   - Status: [Not Started / In Progress / Complete]

2. **[Action]**
   - Owner: [Name/Role]
   - Due: [Date]
   - Status: [Not Started / In Progress / Complete]

### Future Updates Planned

**Known Gaps Remaining** (to be addressed in future versions):
- [Gap 1 - requires Interview #X to complete]
- [Gap 2 - waiting for [data/info/clarification]]
- [Gap 3 - depends on [other artifact/decision]]

**Next Version Trigger**:
[What will cause the next update - e.g., "After Interview #7 with Operations Manager" or "After stakeholder feedback session"]

---

## Document Metadata

**Previous Version**: v[N] ([YYYY-MM-DD])  
**Current Version**: v[N+1] ([YYYY-MM-DD])  
**Days Between Versions**: [N] days  
**Update Session**: Session [N]  
**Time to Update**: [X] hours  
**Words Added/Modified**: [X] words  

**Version History Context**:
- v1: [Date] - Initial creation
- v2: [Date] - [Brief description of v2 changes]
- v3: [Date] - [Brief description of v3 changes - THIS VERSION]

---

## Appendix: Full Change Diff

**If helpful, include a side-by-side comparison**:

```
BEFORE (v[N]):
[Relevant excerpt showing before state]

AFTER (v[N+1]):
[Same section showing after state]
```

---

**END OF DELTA UPDATE DOCUMENT**

This delta update template ensures:
- All changes are documented with rationale
- Sources are cited
- Impact is analyzed
- Quality is validated
- Downstream effects are tracked
- Traceability is maintained

Use this template every time you update a major Phase 0 artifact (problem statement, feasibility report, risk register, success criteria).
```

---

## Usage Examples

### Example 1: Problem Statement Update After Interview

```markdown
# Artifact Delta Update - Problem Statement

**Artifact**: Problem Statement  
**Update Date**: 2025-10-30  
**Previous Version**: v1  
**New Version**: v2  
**Updated By**: Discovery Facilitator  
**Session**: Session 2

---

## Update Trigger

**What prompted this update?**
- [x] New interview(s) completed: Interview #4 with VP Operations
- [x] Contradiction identified that needed resolution
- [ ] Stakeholder feedback received from: [Name/Role]

**Specific Trigger Description**:
Interview #4 with VP Operations revealed that the "slow system" complaint from executives is actually about batch processing that blocks morning access, not general system performance. This contradicts Interview #1 CEO's statement about "system being slow all day."

---

## Summary of Changes

**High-Level Summary**:
Updated problem definition to focus on batch processing window blocking first-shift access rather than general performance. Added quantified impact ($50K/month in first-shift delays). Resolved contradiction between CEO and VP Operations perspectives.

**Change Magnitude**: Moderate  
**Change Type**: Corrective

---

## Detailed Changes

### 1. Additions

#### Addition 1: Quantified Business Impact
- **Location**: Section 2.2 - Financial Impact
- **Content Added**: "Batch processing failures occur 2x/month, causing average 3-hour first-shift delays. At $180/hour labor cost × 60 first-shift workers × 3 hours × 2 occurrences = $64,800/month in idle labor costs."
- **Rationale**: VP Operations provided specific metrics
- **Source**: Interview #004-vp-operations-interview.md, page 2
- **Impact**: Strengthens business case with quantified monthly impact

### 2. Modifications

#### Modification 1: Problem Definition - Root Cause
- **Location**: Section 1.1 - Core Problem
- **Original Content**: "The system is slow, causing productivity issues."
- **Updated Content**: "Batch processing window (12 AM - 6 AM) frequently extends past 6 AM due to increasing data volumes, blocking first-shift access and causing $65K/month in idle labor."
- **Rationale**: Five Whys analysis with VP Operations revealed specific bottleneck
- **Source**: Interview #004, Five Whys session
- **Impact**: Problem now addresses specific technical constraint vs. vague "slow system"

### 3. Contradiction Resolutions

#### Contradiction 1: "System Slowness"
- **Stakeholders Involved**: CEO vs VP Operations
- **Contradiction**: CEO said "system is slow all day"; VP Operations said "system performs fine except first 2 hours of first shift"
- **Resolution Approach**: Asked VP Operations about CEO's complaint; learned CEO visits plant at 7 AM (during problem window)
- **Outcome**: Problem is limited to morning batch processing window, not general performance
- **Artifact Impact**: Updated problem scope from "general slowness" to "batch processing blocking morning access"

---

## Impact Analysis

### Artifact Quality Impact
**Before This Update**:
- Quality Score: 6/10
- Completeness: 70%
- Evidence Support: Moderate
- Clarity: Medium

**After This Update**:
- Quality Score: 8/10 (△ +2)
- Completeness: 85% (△ +15%)
- Evidence Support: Strong
- Clarity: High

**Key Quality Improvements**:
- Problem now specific and measurable
- Root cause identified through Five Whys
- Business impact quantified

### Phase 0 Metrics Impact
**Feasibility Score**: 65/100 → 70/100 (△ +5)
- Timeline: 60→65 (narrower scope = faster)
- Business: 70→75 (stronger business case with quantified impact)

**Timeline Estimate**: 12 months → 8-10 months (△ -2 to -4 months)
```

---

## Tips for Effective Delta Updates

1. **Be Specific**: Don't say "updated based on feedback" - say exactly what changed and why
2. **Cite Sources**: Every claim should reference an interview, data source, or analysis
3. **Show Impact**: Don't just document changes - explain how they affect feasibility, timeline, budget
4. **Resolve Contradictions**: Use delta updates as opportunity to explicitly address conflicting information
5. **Maintain Traceability**: Future readers should understand the evolution of thinking
6. **Version Consistently**: v1 → v2 → v3, not v1 → v2a → v2-final
7. **Update Downstream**: If problem statement changes, flag that feasibility and risks may need updates

---

**END OF ARTIFACT DELTA UPDATE TEMPLATE**
