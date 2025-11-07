# Methodology Adherence Scorecard

**Purpose**: Measure how well Phase 0 discovery follows the defined methodology and identify process improvements.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/templates/phase0/methodology-adherence-scorecard_template.md`

---

## Why Measure Methodology Adherence?

**Problems this scorecard solves**:
- Inconsistent execution across different facilitators
- Skipped quality gates leading to rework
- Ad-hoc processes that work once but don't scale
- Difficulty troubleshooting what went wrong
- Can't improve what you don't measure

**Benefits of tracking adherence**:
- Identify methodology gaps early
- Ensure quality gates are respected
- Enable process improvement based on data
- Support facilitator training and coaching
- Validate methodology effectiveness

---

## When to Use This Scorecard

**Timing**:
- **Mid-Phase Check**: After 50% of interviews complete
- **Phase Completion**: Before moving to validation
- **Retrospective**: After project completes
- **Audit**: When quality issues are suspected

**Who Uses**:
- Discovery facilitators (self-assessment)
- Methodology owners (quality assurance)
- Project retrospectives (lessons learned)

---

## Methodology Adherence Scorecard

```markdown
# Phase 0 Methodology Adherence - [Project Name]

**Assessment Date**: YYYY-MM-DD  
**Assessed By**: [Name, Role]  
**Session ID**: [session-XXX-project-name]  
**Phase Status**: [In Progress / Complete]  
**Assessment Type**: [Self-Assessment / QA Review / Retrospective]

---

## Overall Adherence Score

**Total Score**: [X] / 100  
**Grade**: [A: 90-100 | B: 80-89 | C: 70-79 | D: 60-69 | F: <60]  
**Assessment**: [Excellent / Good / Acceptable / Needs Improvement / Poor]

**Score Breakdown**:
- Agent Instructions: [X]/15
- Workflows: [X]/25
- Templates: [X]/20
- Validation: [X]/20
- Context Management: [X]/10
- Documentation: [X]/10

---

## Category 1: Agent Instructions (15 points)

**Purpose**: Verify that appropriate agent instructions were loaded and followed.

### 1.1 Discovery Facilitator Instructions (5 points)

**Did you load and follow the Discovery Facilitator instructions?**

- ✅ **5 points**: Instructions loaded at session start; consistently referenced throughout
- ⚠️ **3 points**: Instructions loaded but not consistently followed
- ❌ **1 point**: Instructions partially loaded or rarely referenced
- ❌ **0 points**: Instructions not loaded or used

**Score**: [X] / 5  
**Evidence**: [How did you use these instructions?]  
**Notes**: [Any deviations and why]

---

### 1.2 Feasibility Analyzer Instructions (5 points)

**Did you load and follow the Feasibility Analyzer instructions?**

- ✅ **5 points**: Instructions loaded; systematic scoring methodology applied
- ⚠️ **3 points**: Instructions loaded but scoring was ad-hoc
- ❌ **1 point**: Instructions partially loaded or inconsistently applied
- ❌ **0 points**: Instructions not loaded; feasibility assessment was subjective

**Score**: [X] / 5  
**Evidence**: [How did you assess feasibility?]  
**Notes**: [Deviations]

---

### 1.3 Synthesis Agent Instructions (5 points)

**Did you load and follow the Synthesis Agent instructions for problem synthesis?**

- ✅ **5 points**: Instructions loaded; formal synthesis step conducted
- ⚠️ **3 points**: Instructions loaded but synthesis was informal
- ❌ **1 point**: Instructions referenced but not really followed
- ❌ **0 points**: Instructions not loaded; no formal synthesis

**Score**: [X] / 5  
**Evidence**: [Did you do a formal synthesis step?]  
**Notes**: [Why skipped or modified]

---

**Category 1 Total**: [X] / 15

---

## Category 2: Workflows (25 points)

**Purpose**: Verify that defined workflows were followed step-by-step.

### 2.1 Discovery Workflow (10 points)

**Did you follow the 7-step Discovery Workflow?**

**Step-by-Step Adherence**:
- Step 1 - Initiate Discovery: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 2 - Problem Exploration: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 3 - Problem Synthesis: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 4 - Feasibility Analysis: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 5 - Risk Assessment: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 6 - Validation: [✅ Yes / ⚠️ Partial / ❌ Skipped]
- Step 7 - Decision & Handoff: [✅ Yes / ⚠️ Partial / ❌ Skipped]

**Scoring**:
- ✅ **10 points**: All 7 steps followed in order with proper gates
- ⚠️ **7 points**: All steps attempted but some gates skipped
- ⚠️ **5 points**: 5-6 steps followed; 1-2 skipped with justification
- ❌ **3 points**: 4 or fewer steps followed; workflow mostly ignored
- ❌ **0 points**: Workflow not loaded or referenced

**Score**: [X] / 10  
**Evidence**: [Which steps were followed?]  
**Deviations**: [What was skipped and why?]

---

### 2.2 Interview Workflow (10 points)

**Did you follow the Interview Workflow protocol?**

**Protocol Elements**:
- Pre-interview preparation: [✅ Yes / ⚠️ Partial / ❌ No]
- Warm-up phase: [✅ Yes / ⚠️ Partial / ❌ No]
- Five Whys methodology: [✅ Consistently / ⚠️ Sometimes / ❌ Rarely]
- Jobs-to-be-Done questions: [✅ Yes / ⚠️ Partial / ❌ No]
- Follow-up probing: [✅ Deep / ⚠️ Surface / ❌ Minimal]
- Contradiction capture: [✅ Systematic / ⚠️ Ad-hoc / ❌ Missed]
- Post-interview debrief: [✅ Every time / ⚠️ Sometimes / ❌ Rarely]

**Scoring**:
- ✅ **10 points**: Protocol followed for all interviews with discipline
- ⚠️ **7 points**: Protocol mostly followed; occasional deviations
- ⚠️ **5 points**: Protocol partially followed; significant deviations
- ❌ **3 points**: Protocol rarely followed; mostly ad-hoc
- ❌ **0 points**: Protocol not used

**Score**: [X] / 10  
**Evidence**: [How consistent was interview execution?]  
**Notes**: [Common deviations]

---

### 2.3 Progressive Revelation (5 points)

**Did you structure interviews to progressively reveal deeper truth?**

- ✅ **5 points**: Deliberate sequencing (leadership → operations → floor); each interview built on previous
- ⚠️ **3 points**: Some sequencing logic but not systematic
- ❌ **1 point**: Interview order was mostly convenience-based
- ❌ **0 points**: No consideration of progressive revelation

**Score**: [X] / 5  
**Evidence**: [How did you sequence interviews?]  
**Example**: [Show how one interview informed the next]

---

**Category 2 Total**: [X] / 25

---

## Category 3: Templates (20 points)

**Purpose**: Verify that templates were used correctly for artifact creation.

### 3.1 Interview Transcript Template (5 points)

**Did you use the interview transcript template?**

- ✅ **5 points**: Template used for all interviews; consistent format
- ⚠️ **3 points**: Template used for most interviews; some ad-hoc
- ❌ **1 point**: Template used rarely; mostly free-form notes
- ❌ **0 points**: Template not used

**Score**: [X] / 5  
**Evidence**: [How many interviews used the template?]

---

### 3.2 Problem Statement Template (5 points)

**Did you use the problem statement template?**

- ✅ **5 points**: Template used; all sections completed with rigor
- ⚠️ **3 points**: Template used but sections incomplete or thin
- ❌ **1 point**: Template partially used; mostly ad-hoc document
- ❌ **0 points**: Template not used

**Score**: [X] / 5  
**Evidence**: [Link to problem statement document]

---

### 3.3 Feasibility Report Template (5 points)

**Did you use the feasibility report template?**

- ✅ **5 points**: Template used; systematic scoring with rationale
- ⚠️ **3 points**: Template used but scoring was subjective
- ❌ **1 point**: Template partially used; ad-hoc assessment
- ❌ **0 points**: Template not used

**Score**: [X] / 5  
**Evidence**: [Link to feasibility report]

---

### 3.4 Risk Register Template (5 points)

**Did you use the risk register template?**

- ✅ **5 points**: Template used; risks scored, sourced, and prioritized
- ⚠️ **3 points**: Template used but risk scoring was inconsistent
- ❌ **1 point**: Template partially used; mostly bullet list
- ❌ **0 points**: Template not used

**Score**: [X] / 5  
**Evidence**: [Link to risk register]

---

**Category 3 Total**: [X] / 20

---

## Category 4: Validation (20 points)

**Purpose**: Verify that quality gates and validation steps were executed.

### 4.1 Completion Checklist (8 points)

**Did you use the Phase 0 completion checklist before exiting Phase 0?**

- ✅ **8 points**: Checklist used; all items verified before proceeding
- ⚠️ **5 points**: Checklist used but some items skipped/assumed
- ❌ **2 points**: Checklist referenced but not systematically checked
- ❌ **0 points**: Checklist not used

**Score**: [X] / 8  
**Evidence**: [Link to completed checklist]  
**Items Skipped**: [Which items were not validated?]

---

### 4.2 Traceability (6 points)

**Did you maintain traceability from findings to sources?**

**Traceability Quality**:
- All risks traced to source interview: [✅ Yes / ⚠️ Partial / ❌ No]
- All contradictions have stakeholder attribution: [✅ Yes / ⚠️ Partial / ❌ No]
- All feasibility factors sourced: [✅ Yes / ⚠️ Partial / ❌ No]

**Scoring**:
- ✅ **6 points**: Complete traceability throughout
- ⚠️ **4 points**: Most items traced; some gaps
- ❌ **2 points**: Minimal traceability; hard to verify sources
- ❌ **0 points**: No traceability maintained

**Score**: [X] / 6  
**Evidence**: [How did you maintain traceability?]

---

### 4.3 Stakeholder Validation (6 points)

**Did you validate findings with stakeholders before finalizing?**

- ✅ **6 points**: Key findings validated with relevant stakeholders
- ⚠️ **4 points**: Some validation; mostly with leadership
- ❌ **2 points**: Minimal validation; mostly internal team review
- ❌ **0 points**: No stakeholder validation

**Score**: [X] / 6  
**Evidence**: [Who validated what?]

---

**Category 4 Total**: [X] / 20

---

## Category 5: Context Management (10 points)

**Purpose**: Verify effective context engineering practices.

### 5.1 Context Tracker Maintenance (5 points)

**Did you maintain a phase0-context.md file?**

- ✅ **5 points**: Context tracker maintained and updated after every interview
- ⚠️ **3 points**: Context tracker created but not consistently updated
- ❌ **1 point**: Minimal context tracking; mostly ad-hoc
- ❌ **0 points**: No context tracker used

**Score**: [X] / 5  
**Evidence**: [Link to context tracker]

---

### 5.2 Delta Tracking (5 points)

**Did you track artifact changes with delta updates?**

- ✅ **5 points**: Delta updates created for all significant artifact changes
- ⚠️ **3 points**: Some delta tracking; not systematic
- ❌ **1 point**: Minimal delta tracking; mostly in-place edits
- ❌ **0 points**: No delta tracking

**Score**: [X] / 5  
**Evidence**: [How many delta updates were created?]

---

**Category 5 Total**: [X] / 10

---

## Category 6: Documentation (10 points)

**Purpose**: Verify documentation quality and completeness.

### 6.1 Interview Transcripts (4 points)

**Are interview transcripts complete and high-quality?**

- ✅ **4 points**: All interviews have detailed transcripts with quotes
- ⚠️ **3 points**: Most interviews documented; some gaps
- ❌ **1 point**: Minimal documentation; bullet points only
- ❌ **0 points**: No interview documentation

**Score**: [X] / 4  
**Evidence**: [Average transcript quality?]

---

### 6.2 Artifact Completeness (3 points)

**Are all required artifacts present?**

**Required Artifacts**:
- Problem Statement: [✅ Yes / ❌ No]
- Feasibility Report: [✅ Yes / ❌ No]
- Risk Register: [✅ Yes / ❌ No]
- Success Criteria: [✅ Yes / ❌ No]
- Stakeholder Map: [✅ Yes / ❌ No]
- Contradiction Log: [✅ Yes / ❌ No]

**Scoring**:
- ✅ **3 points**: All 6 artifacts present
- ⚠️ **2 points**: 4-5 artifacts present
- ❌ **1 point**: 2-3 artifacts present
- ❌ **0 points**: 0-1 artifacts present

**Score**: [X] / 3

---

### 6.3 Professional Quality (3 points)

**Is documentation professional and presentation-ready?**

- ✅ **3 points**: All artifacts polished, formatted, ready for stakeholder review
- ⚠️ **2 points**: Most artifacts polished; some working-draft quality
- ❌ **1 point**: Minimal polish; clearly working documents
- ❌ **0 points**: Poor quality; not presentable

**Score**: [X] / 3  
**Evidence**: [Overall documentation quality]

---

**Category 6 Total**: [X] / 10

---

## Scoring Summary

| Category | Score | Max | % |
|----------|-------|-----|---|
| Agent Instructions | [X] | 15 | [X]% |
| Workflows | [X] | 25 | [X]% |
| Templates | [X] | 20 | [X]% |
| Validation | [X] | 20 | [X]% |
| Context Management | [X] | 10 | [X]% |
| Documentation | [X] | 10 | [X]% |
| **TOTAL** | **[X]** | **100** | **[X]%** |

---

## Grade Interpretation

**A (90-100): Excellent Methodology Adherence**
- All processes followed rigorously
- Quality gates respected
- Documentation complete and professional
- Process is repeatable and scalable
- Minimal risk of rework

**B (80-89): Good Methodology Adherence**
- Most processes followed
- Some quality gates skipped but with awareness
- Documentation mostly complete
- Process mostly repeatable
- Low risk of rework

**C (70-79): Acceptable Methodology Adherence**
- Core processes followed
- Several quality gates skipped
- Documentation has gaps
- Process partially repeatable
- Moderate risk of rework

**D (60-69): Needs Improvement**
- Significant process deviations
- Many quality gates skipped
- Documentation incomplete
- Process not reliably repeatable
- High risk of rework

**F (<60): Poor Methodology Adherence**
- Methodology largely ignored
- Ad-hoc execution
- Documentation inadequate
- Process not repeatable
- Very high risk of rework

---

## Improvement Actions

Based on your score, identify specific improvements:

### Critical Improvements (Must address)
- [Action 1]
- [Action 2]

### Important Improvements (Should address)
- [Action 1]
- [Action 2]

### Nice-to-Have Improvements (Consider for future)
- [Action 1]
- [Action 2]

---

## Root Cause Analysis

**Why were methodology elements skipped or poorly executed?**

### Time Pressure
- [ ] Not enough time allocated to Phase 0
- [ ] Stakeholder availability constraints
- [ ] Pressure to move fast

### Knowledge Gaps
- [ ] Facilitator unfamiliar with methodology
- [ ] Templates not clear enough
- [ ] Workflow instructions ambiguous

### Tool/Resource Issues
- [ ] Templates not easily accessible
- [ ] Context management was cumbersome
- [ ] Validation checklists not available

### Process Issues
- [ ] Methodology too rigid for this context
- [ ] Steps didn't make sense for this project type
- [ ] Quality gates felt like bureaucracy

### Other
- [Description]

---

## Lessons Learned

**What worked well?**
- [Lesson 1]
- [Lesson 2]

**What didn't work?**
- [Lesson 1]
- [Lesson 2]

**What would you do differently next time?**
- [Change 1]
- [Change 2]

**Methodology improvements needed:**
- [Update needed to template X]
- [Clarification needed in workflow Y]
- [New tool needed for Z]

---

## Sign-off

**Completed By**: [Name]  
**Date**: YYYY-MM-DD  
**Reviewed By**: [Methodology owner, if applicable]  
**Actions Assigned**: [Who will address improvement actions?]
```

---

## Usage Instructions

### When to Complete

**Mid-Phase (Recommended)**:
- After 50% of interviews complete
- Catch methodology deviations early
- Course-correct before too late

**Phase Completion**:
- Before exiting Phase 0
- Validate quality before handoff
- Identify improvements for next project

**Retrospective**:
- After project fully completes
- Comprehensive lessons learned
- Inform methodology evolution

### How to Score

**Be Honest**:
- Don't inflate scores
- The goal is improvement, not judgment
- Document actual execution, not intentions

**Provide Evidence**:
- Link to specific artifacts
- Cite examples
- Quantify where possible

**Explain Deviations**:
- Why was something skipped?
- Was the deviation justified?
- What was the impact?

**Identify Root Causes**:
- Don't just note what was skipped
- Understand why
- This informs methodology improvements

---

## Example Excerpt

```markdown
### 2.1 Discovery Workflow (10 points)

**Did you follow the 7-step Discovery Workflow?**

**Step-by-Step Adherence**:
- Step 1 - Initiate Discovery: ✅ Yes
- Step 2 - Problem Exploration: ✅ Yes
- Step 3 - Problem Synthesis: ❌ Skipped
- Step 4 - Feasibility Analysis: ⚠️ Partial
- Step 5 - Risk Assessment: ✅ Yes
- Step 6 - Validation: ❌ Skipped
- Step 7 - Decision & Handoff: ⚠️ Partial

**Score**: 5 / 10

**Evidence**: 
- Steps 1, 2, 5 followed rigorously with documentation
- Step 3 skipped entirely - went straight from interviews to decision
- Step 4 done continuously but no formal feasibility report
- Step 6 skipped - no completion checklist run
- Step 7 partial - decision made but no formal handoff package

**Deviations**: 
Skipped formal synthesis step because team felt findings were obvious after interviews. In retrospect, this led to missing several contradictions that weren't apparent until later. Validation step skipped due to time pressure - leadership wanted decision quickly.

**Impact of Deviations**:
- Missing synthesis meant contradictions surfaced during implementation
- No validation checklist meant we missed checking regulatory requirements
- Informal handoff to Phase 1 meant some context was lost

**Root Cause**: Time pressure from executive sponsor combined with facilitator's belief that "we already know the answer."

**Lessons Learned**: Even when findings seem obvious, formal synthesis surfaces non-obvious patterns. Skipping validation to save time just pushes problems downstream where they're more expensive to fix.
```

---

## File Metadata

**Template Version**: 1.0  
**Intended For**: Phase 0 completion assessment and continuous improvement  
**Update Frequency**: Per project or during mid-phase check  
**Maintenance**: Evolve based on methodology changes  
**Related**: 
- All Phase 0 workflows and templates (what this scorecard measures)
- `phase0-context-tracker_template.md` (tracks execution)
- `session-bridge.prompt.md` (uses adherence to guide resumption)
