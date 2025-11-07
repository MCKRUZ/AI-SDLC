# Completion Criteria Enhancement Guide

**Purpose**: Provide explicit completion criteria to add to discovery-workflow.prompt.md to prevent premature step transitions.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/workflows/phase0/completion-criteria-enhancements.md`

---

## Why Explicit Completion Criteria?

**Problem this solves**:
- Teams move to next step prematurely ("We've done enough interviews")
- Quality gates are subjective or implicit
- No clear definition of "done" for each step
- Inconsistent execution across projects

**Benefit of explicit criteria**:
- Clear checkpoints before proceeding
- Objective assessment of completeness
- Reduced rework from incomplete discovery
- Consistent quality across facilitators

---

## How to Use This Guide

This document provides completion criteria blocks to insert into your existing `discovery-workflow.prompt.md` file.

**Integration Instructions**:
1. Open your `discovery-workflow.prompt.md`
2. At the END of each step description, insert the corresponding completion criteria block
3. Before proceeding to the next step, verify ALL criteria are met
4. Document any criteria that cannot be met and the justification

---

## Step 1: Initiate Discovery - Completion Criteria

**Insert this block at the end of Step 1 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 1 Completion Criteria

Before proceeding to Step 2, verify the following:

#### Required Documentation
- [ ] Initial problem statement documented (can be high-level/draft)
- [ ] Project background and context captured
- [ ] Executive sponsor identified and confirmed
- [ ] Project constraints documented (budget, timeline, scope boundaries)
- [ ] Success definition drafted (can be refined later)

#### Stakeholder Identification
- [ ] Minimum stakeholder categories identified:
  - [ ] Executive/leadership perspective (1+ person)
  - [ ] Technical leadership (1+ person)
  - [ ] Operations/business owners (1+ person)
  - [ ] End users/practitioners (2+ people)
  - [ ] Support/maintenance personnel (1+ person)
- [ ] Stakeholder contact information obtained
- [ ] Interview priorities assigned (who to talk to first/last)

#### Methodology Setup
- [ ] Discovery Facilitator instructions loaded
- [ ] Interview workflow protocol loaded
- [ ] Templates accessed and ready (interview, feasibility, risk, problem statement)
- [ ] Session directory structure created
- [ ] Phase 0 context tracker initialized

#### Logistics
- [ ] Interview schedule drafted (who, when, how long)
- [ ] Interview approach confirmed (1:1, group, async, etc.)
- [ ] Recording/note-taking approach established
- [ ] Stakeholder communications sent (calendar invites, prep materials)

#### Validation Gate
**STOP if any critical items are missing:**
- ❌ No executive sponsor identified → Cannot proceed without sponsorship
- ❌ Cannot identify end users to interview → Cannot validate problem
- ❌ No access to methodology templates → Quality will suffer

**Decision Point**: 
✅ All critical items complete → Proceed to Step 2  
⚠️ Minor items incomplete → Document as known gaps, proceed with caution  
❌ Critical items incomplete → Address before proceeding

**Step 1 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Status: [Complete / Complete with gaps / Blocked]
- Notes: [Any important context]
```

---

## Step 2: Problem Exploration - Completion Criteria

**Insert this block at the end of Step 2 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 2 Completion Criteria

Before proceeding to Step 3, verify the following:

#### Interview Coverage
- [ ] **Minimum interview count met**: 
  - At least 1 executive/leadership
  - At least 1 technical leader
  - At least 2 operations/business stakeholders
  - At least 2 end users/practitioners
  - At least 1 support/maintenance person
  - **Total**: Minimum 7 interviews (recommended: 8-12)

- [ ] **Perspective diversity achieved**:
  - [ ] Optimistic perspective captured (usually leadership)
  - [ ] Realistic/pragmatic perspective captured (usually ops/technical)
  - [ ] Skeptical/cautious perspective captured (someone with concerns)
  - [ ] Floor-level truth captured (practitioners who live in the system)

- [ ] **Organizational depth achieved**:
  - [ ] C-suite or equivalent
  - [ ] Director level
  - [ ] Manager level
  - [ ] Individual contributor level

#### Theme Saturation
- [ ] **Major themes identified** (typically 5-8 themes):
  - Theme 1: [Name] - Appeared in interviews [X, Y, Z]
  - Theme 2: [Name] - Appeared in interviews [X, Y, Z]
  - [etc.]

- [ ] **Saturation achieved**: New interviews are reinforcing existing themes, not revealing fundamentally new information
  - Test: Last 3 interviews revealed [0-1 new major themes]
  - If revealing 2+ new themes → Need more interviews

#### Methodology Adherence
- [ ] **Five Whys applied consistently**:
  - Root causes identified, not just symptoms
  - Example documented in at least 3 interviews
  
- [ ] **Jobs-to-be-Done explored**:
  - Understood why stakeholders want this project
  - Understood what "jobs" they're trying to accomplish
  - Identified underlying motivations beyond stated reasons

- [ ] **Contradictions captured**:
  - Documented all contradictions between stakeholders
  - Each contradiction has clear attribution (Person A says X, Person B says Y)
  - Contradictions prioritized by impact

#### Business Impact Quantified
- [ ] **Financial impact estimated**:
  - Current cost of problem: $[amount] per [timeframe]
  - Expected benefit: $[amount] per [timeframe]
  - Confidence level: [High/Medium/Low]
  - Source: [Which stakeholders provided this]

- [ ] **Operational impact quantified**:
  - Time savings: [X hours/days per timeframe]
  - Quality improvements: [X% reduction in defects/errors]
  - Customer impact: [X customers affected]
  - Source: [Stakeholder attribution]

- [ ] **Strategic impact defined**:
  - How does this enable strategic goals?
  - What happens if we don't do this?
  - Source: [Leadership interviews]

#### Artifact Quality
- [ ] **Interview transcripts complete**:
  - All interviews have documented transcripts
  - Key quotes captured with attribution
  - Each transcript includes: context, key findings, contradictions, follow-ups

- [ ] **Working artifacts updated**:
  - Problem statement (v[N]) reflects all interviews
  - Feasibility assessment (v[N]) updated continuously
  - Risk register (v[N]) includes risks from all interviews
  - Contradiction log maintained
  - Stakeholder map current

- [ ] **Traceability maintained**:
  - Can trace each major finding back to source interview
  - Can trace each risk back to who raised it
  - Can trace each contradiction back to stakeholders involved

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ Interviewed <5 people → Insufficient perspective diversity
- ❌ Only interviewed leadership → Missing operational reality
- ❌ New themes still emerging rapidly → Haven't reached saturation
- ❌ Cannot quantify business impact → Validation will be difficult
- ❌ Contradictions not documented → Will surface during implementation

**Progressive Revelation Check**:
- Does each interview build on previous ones?
- Did we sequence from assumptions to reality?
- Can we show how understanding deepened over time?
- Have we tested leadership assumptions against operational reality?

**Red Flags** that suggest more interviews needed:
- 🚩 Major stakeholder group not represented
- 🚩 Significant disagreement on basic facts
- 🚩 Feasibility score wildly fluctuating (not converging)
- 🚩 Open questions that only specific people can answer
- 🚩 "Surprises" in last 2 interviews (should be confirmation, not revelation)

**Decision Point**: 
✅ All critical criteria met → Proceed to Step 3 (Synthesis)  
⚠️ Minor gaps → Document and proceed with awareness  
❌ Critical gaps → Continue interviewing or address gaps  
⏸️ Enough for now → Can proceed but flag areas needing validation later

**Step 2 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Total Interviews: [N]
- Themes Identified: [N]
- Saturation Achieved: [Yes/No/Partial]
- Status: [Complete / Complete with gaps / Need more interviews]
- Notes: [Any important context or known gaps]
```

---

## Step 3: Problem Synthesis - Completion Criteria

**Insert this block at the end of Step 3 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 3 Completion Criteria

Before proceeding to Step 4, verify the following:

#### Synthesis Artifacts Created
- [ ] **Problem Statement (FINAL)**:
  - All interviews synthesized into coherent narrative
  - Both leadership view AND operational reality captured
  - Contradictions acknowledged and explained
  - Problem scope clearly bounded
  - Success criteria measurable and specific
  - Version marked as "final" (not working draft)

- [ ] **Stakeholder Map (COMPLETE)**:
  - All interviewed stakeholders mapped
  - Power dynamics documented (who has veto power?)
  - Trust hierarchies identified (who trusts whom?)
  - Influence patterns clear (who influences decisions?)
  - Coalition opportunities identified
  - Resistance points mapped

- [ ] **Contradiction Analysis (COMPLETE)**:
  - All contradictions documented with sources
  - Each contradiction analyzed for root cause
  - Impact of each contradiction assessed
  - Resolution approach defined for critical contradictions
  - Unresolvable contradictions flagged as constraints

#### Pattern Analysis
- [ ] **Cross-cutting themes synthesized**:
  - Major themes ranked by frequency and impact
  - Patterns across stakeholder groups identified
  - Outlier perspectives noted and explained
  - Convergent views vs. divergent views clear

- [ ] **Root causes identified**:
  - Surface symptoms distinguished from root causes
  - "Five Whys" synthesis shows causation chains
  - Systemic issues vs. point problems separated
  - Interconnections between problems mapped

- [ ] **Hidden constraints surfaced**:
  - Organizational constraints (culture, politics, capacity)
  - Technical constraints (legacy systems, integrations)
  - Financial constraints (budget, ROI expectations)
  - Timeline constraints (regulatory, market, strategic deadlines)
  - People constraints (skills, training, resistance)

#### Insight Quality
- [ ] **Non-obvious insights documented**:
  - What did we learn that wasn't in initial assumptions?
  - What surprised us?
  - What contradicts conventional wisdom?
  - What would we have missed without deep discovery?

- [ ] **Organizational dynamics understood**:
  - Power structure clear (who really decides?)
  - Trust levels assessed (who works well together?)
  - Past project history understood (what shaped current attitudes?)
  - Change readiness evaluated (how receptive is organization?)

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ Problem statement still contains contradictions → Need resolution
- ❌ Cannot identify veto powers → Political risk too high
- ❌ Root causes still unclear → Treating symptoms, not causes
- ❌ Major patterns unexplained → Insufficient synthesis depth

**Synthesis Quality Check**:
- Would a new person reading the problem statement understand the full complexity?
- Have we captured BOTH "what leadership wants" AND "what's actually needed"?
- Can we explain every major finding with evidence from interviews?
- Do stakeholder quotes support our conclusions?

**Decision Point**: 
✅ Comprehensive synthesis complete → Proceed to Step 4  
⚠️ Synthesis adequate but gaps exist → Document gaps, proceed carefully  
❌ Synthesis incomplete or weak → Revisit interviews or deepen analysis

**Step 3 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Key Insights: [List 3-5 most important]
- Critical Contradictions: [Count unresolved]
- Confidence Level: [High/Medium/Low]
- Status: [Complete / Complete with gaps]
- Notes: [Important context]
```

---

## Step 4: Feasibility Analysis - Completion Criteria

**Insert this block at the end of Step 4 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 4 Completion Criteria

Before proceeding to Step 5, verify the following:

#### Feasibility Dimensions Assessed
- [ ] **Technical Feasibility** (scored):
  - Can this be built with available technology?
  - Do we have the technical skills?
  - Are integrations feasible?
  - Score: [X]/20 with rationale

- [ ] **Operational Feasibility** (scored):
  - Can operations adopt this change?
  - Are processes compatible?
  - Is organizational capacity sufficient?
  - Score: [X]/20 with rationale

- [ ] **Financial Feasibility** (scored):
  - Is budget realistic for scope?
  - Is ROI acceptable?
  - Are ongoing costs sustainable?
  - Score: [X]/20 with rationale

- [ ] **Timeline Feasibility** (scored):
  - Are timelines realistic given constraints?
  - Are dependencies manageable?
  - Is sequence achievable?
  - Score: [X]/20 with rationale

- [ ] **Organizational Feasibility** (scored):
  - Is change capacity available?
  - Is political support sufficient?
  - Is culture compatible?
  - Score: [X]/20 with rationale

#### Scoring Quality
- [ ] **Overall feasibility score calculated**: [X]/100
- [ ] **Score trend documented**: 
  - Initial score: [X]
  - Current score: [Y]
  - Trend: [Improving/Declining/Stable]
  
- [ ] **Each score has evidence**:
  - Every dimension links to specific interview findings
  - Scoring rationale is explicit, not subjective
  - Can defend every score with stakeholder quotes

- [ ] **Confidence levels assigned**:
  - High confidence: Backed by data and validation
  - Medium confidence: Reasonable estimates but assumptions present
  - Low confidence: Significant unknowns remain

#### Reality-Check Validation
- [ ] **Mathematical validation** (where applicable):
  - Maintenance windows calculated (hours available per year)
  - Training time calculated (people × hours × coverage)
  - Migration time calculated (systems × hours × constraints)
  - Example: "48 hours/year ÷ 8 hours/migration = 6 systems/year max"

- [ ] **Comparative validation**:
  - Compared to similar projects (what did they actually take?)
  - Industry benchmarks referenced (what do others report?)
  - Historical performance considered (what has this org achieved before?)

- [ ] **Constraint analysis**:
  - Every hard constraint documented (regulatory, legal, contractual)
  - Every soft constraint documented (cultural, political, resource)
  - Constraint impact quantified (how much do these limit feasibility?)

#### Feasibility Report Quality
- [ ] **Report structure complete**:
  - Executive summary (1-page, decision-focused)
  - Detailed scoring by dimension
  - Supporting evidence and sources
  - Assumptions and caveats
  - Recommendation (GO/CONDITIONAL GO/NO-GO/DEFER)

- [ ] **Report is decision-ready**:
  - Leadership can make GO/NO-GO decision from this report
  - Rationale is clear and evidence-based
  - Trade-offs are explicit
  - Risks are transparent

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ Feasibility score not evidence-based → Subjective assessment won't hold up
- ❌ Major dimensions not assessed → Incomplete analysis
- ❌ Timeline not mathematically validated → Unrealistic expectations will cause failure
- ❌ Cannot identify which constraints are binding → Can't plan around them

**Feasibility Red Flags**:
- 🚩 Feasibility score <50/100 → Serious concerns, likely NO-GO
- 🚩 Score declining over discovery → Reality worse than assumptions
- 🚩 Technical feasible but organizational infeasible → People problem, not tech problem
- 🚩 Large gap between stakeholder estimates → Fundamental disagreement on reality

**Decision Point**: 
✅ Rigorous feasibility analysis complete → Proceed to Step 5  
⚠️ Feasibility assessment adequate → Proceed but flag gaps for validation  
❌ Feasibility unclear or poorly supported → Deepen analysis before risk assessment

**Step 4 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Feasibility Score: [X]/100 ([Interpretation])
- Confidence: [High/Medium/Low]
- Recommendation: [GO/CONDITIONAL/NO-GO/DEFER]
- Status: [Complete / Needs validation]
- Notes: [Key concerns or caveats]
```

---

## Step 5: Risk Assessment - Completion Criteria

**Insert this block at the end of Step 5 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 5 Completion Criteria

Before proceeding to Step 6, verify the following:

#### Risk Identification
- [ ] **Risk categories covered**:
  - [ ] Technical risks (tech stack, integration, complexity)
  - [ ] Organizational risks (capacity, capability, culture)
  - [ ] Operational risks (business continuity, downtime, rollback)
  - [ ] Financial risks (budget overrun, ROI shortfall)
  - [ ] Timeline risks (delays, dependencies, schedule pressure)
  - [ ] People risks (turnover, training, resistance)
  - [ ] Regulatory/Compliance risks
  - [ ] External risks (vendor, market, competition)

- [ ] **Minimum risk count**: At least 15 risks identified
  - If <10 risks → Discovery was too shallow
  - If 10-15 risks → Acceptable for simple projects
  - If 15-30 risks → Expected for complex projects
  - If >30 risks → Consider whether project is too complex

#### Risk Scoring
- [ ] **All risks scored consistently**:
  - Probability: [1-5 scale, explicitly defined]
  - Impact: [1-5 scale, explicitly defined]
  - Risk Score: Probability × Impact
  - Scored by: [Who assessed - facilitator + stakeholders]

- [ ] **Risk severity distribution** documented:
  - Critical (score 20-25): [N] risks
  - High (score 12-19): [N] risks
  - Medium (score 6-11): [N] risks
  - Low (score 1-5): [N] risks

- [ ] **Each risk has**:
  - Clear description
  - Source (which interview/stakeholder raised it)
  - Probability and impact justification
  - Potential mitigation strategies
  - Owner (who would manage this risk if project proceeds)

#### Risk Analysis
- [ ] **Risk interdependencies mapped**:
  - Which risks amplify each other?
  - Which risks cascade (if X happens, then Y becomes more likely)?
  - Which risks are independent?

- [ ] **Risk timing analyzed**:
  - When would each risk materialize (discovery/planning/build/deploy/operate)?
  - Early risks vs. late risks identified
  - Risks that could derail project early flagged

- [ ] **Unmitigable risks identified**:
  - Which risks have no good mitigation?
  - Which risks are constraints we must accept?
  - Are any unmitigable risks showstoppers?

#### Risk Register Quality
- [ ] **Register is comprehensive**:
  - All major risks from all interviews captured
  - Cross-referenced to feasibility assessment
  - Each risk traceable to source
  - Register includes mitigations and owners

- [ ] **Register is actionable**:
  - Leadership can make risk acceptance decisions
  - Project team could create risk management plan from this
  - Priorities are clear (what to address first)

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ <10 risks identified → Discovery was insufficient
- ❌ No critical/high risks identified → Unrealistic assessment
- ❌ Risks not traceable to sources → Can't validate
- ❌ No mitigation strategies → Can't develop risk management plan

**Risk Red Flags**:
- 🚩 Multiple unmitigable critical risks → Potential NO-GO
- 🚩 Cascading risk chains identified → Higher project risk
- 🚩 Risks contradict feasibility assessment → Reconcile discrepancy
- 🚩 Organizational risks dominate → This is a people project, not a tech project

**Decision Point**: 
✅ Comprehensive risk assessment complete → Proceed to Step 6  
⚠️ Risk assessment adequate but gaps exist → Flag for deeper analysis  
❌ Risk assessment incomplete or unrealistic → Deepen before validation

**Step 5 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Total Risks: [N]
- Critical Risks: [N]
- Risk Assessment: [Manageable / Significant / Severe]
- Showstoppers: [Any? List if so]
- Status: [Complete / Needs deeper analysis]
- Notes: [Key risk themes]
```

---

## Step 6: Validation - Completion Criteria

**Insert this block at the end of Step 6 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 6 Completion Criteria

Before proceeding to Step 7, verify the following:

#### Artifact Validation
- [ ] **Problem Statement validated**:
  - Reviewed with executive sponsor
  - Validated with key stakeholders
  - Contradictions acknowledged and signed off
  - Success criteria confirmed as measurable
  - Sign-off: [Name, Date]

- [ ] **Feasibility Assessment validated**:
  - Technical feasibility confirmed by technical leadership
  - Operational feasibility confirmed by operations
  - Financial feasibility confirmed by finance/CFO
  - Timeline feasibility confirmed by all parties
  - Sign-off: [Names, Dates]

- [ ] **Risk Register validated**:
  - All critical/high risks reviewed with stakeholders
  - Risk scores validated (not just facilitator opinion)
  - Mitigation strategies assessed for viability
  - Risk owners identified and agreed
  - Sign-off: [Names, Dates]

#### Cross-Validation
- [ ] **Consistency check completed**:
  - Feasibility assessment aligns with risk register
  - Problem statement aligns with success criteria
  - Stakeholder map aligns with interview findings
  - No contradictions between artifacts (or contradictions are explained)

- [ ] **Traceability validated**:
  - Can trace every major conclusion to source interviews
  - Can trace every risk to stakeholder who raised it
  - Can trace every constraint to its source
  - Traceability matrix created (optional but recommended)

#### Completion Checklist
- [ ] **Phase 0 completion checklist run**:
  - Loaded from: `test/.sdlc/primitives/checklists/phase0-completion.checklist.md`
  - All items checked and validated
  - Any items skipped are justified in writing
  - Completion checklist signed off

#### Stakeholder Alignment
- [ ] **Key stakeholder sign-offs obtained**:
  - Executive sponsor: [Name] - [Date]
  - Technical leadership: [Name] - [Date]
  - Operations leadership: [Name] - [Date]
  - Finance (if applicable): [Name] - [Date]

- [ ] **Alignment on decision criteria**:
  - Stakeholders understand the GO/NO-GO criteria
  - Stakeholders agree on what "success" means
  - Stakeholders accept the risks identified
  - Stakeholders acknowledge constraints documented

#### Quality Assessment
- [ ] **Documentation quality validated**:
  - All artifacts are professional and presentation-ready
  - Artifacts are internally consistent
  - Artifacts are complete (no TBD or placeholder sections)
  - Artifacts can be handed off to Phase 1 team

- [ ] **Methodology adherence assessed**:
  - Methodology adherence scorecard completed (optional but recommended)
  - Score: [X]/100
  - Any methodology deviations documented and justified

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ No stakeholder sign-offs → Findings not validated
- ❌ Artifacts internally inconsistent → Quality concerns
- ❌ Traceability broken → Can't verify conclusions
- ❌ Completion checklist not run → Don't know if Phase 0 is truly complete

**Validation Red Flags**:
- 🚩 Stakeholders won't sign off → Findings not credible or politically unacceptable
- 🚩 Major contradictions remain unresolved → Will cause issues in Phase 1
- 🚩 Artifacts still "working draft" quality → Not ready for handoff
- 🚩 Key stakeholders not aligned → Decision won't stick

**Decision Point**: 
✅ All artifacts validated and signed off → Proceed to Step 7  
⚠️ Most items validated, minor gaps acceptable → Document gaps, proceed  
❌ Critical validation gaps → Address before making GO/NO-GO decision

**Step 6 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Validation Status: [Fully validated / Validated with gaps / Not validated]
- Key Sign-offs Obtained: [List]
- Ready for Decision: [Yes / No / With caveats]
- Notes: [Important validation context]
```

---

## Step 7: Decision & Handoff - Completion Criteria

**Insert this block at the end of Step 7 in discovery-workflow.prompt.md:**

```markdown
### ✅ Step 7 Completion Criteria

Before closing Phase 0, verify the following:

#### Decision Documented
- [ ] **GO/NO-GO decision made**:
  - Decision: [GO / CONDITIONAL GO / NO-GO / DEFER]
  - Decided by: [Who had authority to decide]
  - Date: YYYY-MM-DD
  - Rationale documented

- [ ] **If GO or CONDITIONAL GO**:
  - Conditions clearly stated
  - Constraints acknowledged
  - Risks accepted (explicitly)
  - Budget range confirmed: $[Min] - $[Max]
  - Timeline range confirmed: [Min] - [Max] months
  - Scope boundaries confirmed

- [ ] **If NO-GO or DEFER**:
  - Reasons clearly documented
  - Learning captured (what did we learn?)
  - Alternative approaches considered
  - Future reconsideration criteria defined (if DEFER)

#### Handoff Package Prepared
- [ ] **Final artifacts in `/artifacts/`**:
  - [ ] problem-statement.final.md
  - [ ] feasibility-report.final.md
  - [ ] risk-register.final.md
  - [ ] success-criteria.final.md
  - [ ] stakeholder-map.final.md
  - [ ] contradiction-analysis.final.md (if applicable)
  - [ ] constraints.final.md (if applicable)

- [ ] **Supporting artifacts in `/interviews/`**:
  - All interview transcripts
  - Numbered and dated
  - Cross-referenced in final artifacts

- [ ] **Session metadata complete**:
  - session.meta.md includes summary of entire Phase 0
  - Key findings summarized
  - Decision rationale captured
  - Lessons learned documented

#### Knowledge Transfer
- [ ] **Handoff meeting scheduled** (if GO):
  - Meeting with Phase 1 team (Specification & Planning)
  - Artifacts shared in advance
  - Key discovery insights prepared for discussion
  - Open questions flagged

- [ ] **Context preserved**:
  - Phase 0 context tracker finalized
  - All delta updates archived
  - Methodology adherence scorecard completed
  - Lessons learned documented for methodology improvement

#### Organizational Learning
- [ ] **Lessons learned captured**:
  - What worked well in this discovery?
  - What could have been better?
  - What would we do differently next time?
  - What methodology improvements are needed?

- [ ] **Memory updated** (if applicable):
  - Organization context updated with learnings
  - Prior projects memory updated with this case
  - Lessons learned added to organizational knowledge

#### Phase 0 Close-out
- [ ] **Session closed properly**:
  - All files moved from `/working/` to `/artifacts/` (if final)
  - Session directory cleaned up and organized
  - Phase 0 officially marked complete
  - Appropriate archival/backup completed

- [ ] **Next phase prepared** (if GO):
  - Phase 1 team identified
  - Handoff scheduled
  - Phase 1 session directory created
  - Phase 1 primitives staged

#### Validation Gate
**STOP if critical criteria are not met:**
- ❌ No decision made → Phase 0 incomplete
- ❌ Artifacts still in working/ directory → Not finalized
- ❌ No handoff plan (if GO) → Phase 1 will lack context
- ❌ Lessons learned not captured → Can't improve methodology

**Close-out Quality Check**:
- If someone new reads the final artifacts, can they understand:
  - What problem we're solving?
  - Why it's feasible (or not)?
  - What risks exist?
  - What constraints must be respected?
  - What decision was made and why?

**Final Decision Point**: 
✅ Phase 0 complete, ready to close → Close Phase 0, hand off if GO  
⚠️ Minor loose ends acceptable → Document, close Phase 0  
❌ Critical items incomplete → Finish before closing

**Step 7 Completion Sign-off**:
- Completed by: [Name]
- Date: YYYY-MM-DD
- Decision: [GO/CONDITIONAL GO/NO-GO/DEFER]
- Handoff Date: [If GO] YYYY-MM-DD
- Phase 0 Duration: [N days]
- Phase 0 Status: [Complete / Complete with caveats]
- Final Notes: [Any critical context for future phases]

---

## 🎉 PHASE 0: DISCOVERY - COMPLETE
```

---

## Usage Guidelines

### How to Integrate These Criteria

**Step 1: Open Your Workflow File**
- Open: `test/.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md`

**Step 2: Insert Criteria Blocks**
- For each step (1-7), insert the corresponding completion criteria block
- Place at the END of each step description
- Keep formatting consistent with your existing file

**Step 3: Train Facilitators**
- Walk through criteria with all facilitators
- Explain why each criterion matters
- Demonstrate how to validate completion

**Step 4: Use During Execution**
- Before moving to next step, explicitly check criteria
- Document which criteria are met/unmet
- Justify any skipped criteria

### Benefits of Explicit Criteria

**Prevents Premature Progression**:
- Can't move to synthesis without sufficient interviews
- Can't make decision without validation
- Forces rigorous execution

**Creates Consistency**:
- Every facilitator uses same checkpoints
- Quality doesn't depend on facilitator experience
- Organizational learning becomes systematic

**Enables Quality Assurance**:
- Can audit Phase 0 execution
- Can identify where quality broke down
- Can improve methodology based on data

**Provides Clear Expectations**:
- Teams know what "done" means
- No ambiguity about completion
- Reduces conflicts about "good enough"

---

## Example of Enhanced Step

Here's how Step 2 would look with criteria added:

```markdown
## Step 2: Problem Exploration

Conduct systematic stakeholder interviews to deeply understand the problem space.

### Activities
- Conduct interviews with identified stakeholders
- Apply Five Whys methodology to reach root causes
- Use Jobs-to-be-Done framework to understand motivations
- Document contradictions between stakeholders
- Update working artifacts continuously
- Identify patterns and themes across interviews

### Techniques
- Progressive revelation: Structure interviews from assumptions → reality
- Active listening and probing
- Quantification of impact (financial, operational, strategic)
- Contradiction capture and analysis

### Outputs
- Interview transcripts for each stakeholder
- Updated problem statement (working version)
- Updated feasibility assessment (working version)
- Updated risk register (working version)
- Contradiction log
- Phase 0 context tracker (continuously updated)

---

### ✅ Step 2 Completion Criteria

[Insert the full Step 2 completion criteria block here]

---

## Step 3: Problem Synthesis

[Continue with Step 3...]
```

---

## File Metadata

**Guide Version**: 1.0  
**Purpose**: Provide completion criteria enhancements for discovery-workflow.prompt.md  
**Integration**: Insert criteria blocks at end of each step in the workflow  
**Maintenance**: Update as methodology evolves and new patterns emerge  
**Related**: 
- `discovery-workflow.prompt.md` (file to enhance)
- `methodology-adherence-scorecard_template.md` (measures adherence to these criteria)
- `phase0-context-tracker_template.md` (tracks progress through these criteria)
- `phase0-completion.checklist.md` (comprehensive checklist that complements these criteria)
