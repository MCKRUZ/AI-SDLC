# Discovery Workflow - Complete Process

**Purpose**: This workflow orchestrates the complete Phase 0 discovery process, coordinating the Discovery Facilitator and Feasibility Analyzer agents to produce validated artifacts ready for Phase 1.

---

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                     Phase 0: Discovery & Ideation                │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Initiate Discovery   │
                 │  - Create session        │
                 │  - Load context          │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  2. Problem Exploration  │
                 │  (Discovery Facilitator) │
                 │  - Stakeholder interviews│
                 │  - Five Whys analysis    │
                 │  - JTBD framework        │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  3. Problem Synthesis    │
                 │  (Discovery Facilitator) │
                 │  - Combine findings      │
                 │  - Identify patterns     │
                 │  - Draft problem stmt    │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Stakeholder Validation│
                 │  - Review problem stmt   │
                 │  - Resolve contradictions│
                 │  - Obtain alignment      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. Feasibility Analysis │
                 │  (Feasibility Analyzer)  │
                 │  - Research precedents   │
                 │  - Assess risks          │
                 │  - Validate constraints  │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  6. Recommendation       │
                 │  (Feasibility Analyzer)  │
                 │  - GO/CONDITIONAL/POC/NO │
                 │  - Confidence level      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  7. Completion Validation│
                 │  - Checklist review      │
                 │  - Stakeholder approval  │
                 │  - Package artifacts     │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │   Ready for Phase 1      │
                 │   (Specification)        │
                 └──────────────────────────┘
```

---

## Step 1: Initiate Discovery

### Objective
Set up the discovery session with proper context and structure.

### Actions

#### 1.1 Create Session Directory
```bash
# Create new session folder
mkdir -p discovery-sessions/[NNN-project-name]/{interviews,working,artifacts,validation}

# Copy templates into working directory
cp .discovery/primitives/templates/*.template.md discovery-sessions/[NNN-project-name]/working/
```

#### 1.2 Load Organizational Context
Load persistent memory files:
- `.discovery/memory/organization.context.md`
- `.discovery/memory/technical-stack.context.md`
- `.discovery/memory/prior-projects.memory.md`

#### 1.3 Create Session Metadata
```markdown
# Session Metadata

**Project Name**: [Name]
**Session ID**: [NNN-project-name]
**Start Date**: [YYYY-MM-DD]
**Status**: [Active]

**Participants**:
- Discovery Facilitator: [Name/Agent]
- Feasibility Analyzer: [Name/Agent]
- Project Sponsor: [Name]

**Stakeholders to Interview**:
- [ ] [Role 1] - [Name] - Contact: [Email]
- [ ] [Role 2] - [Name] - Contact: [Email]
- [ ] [Role 3] - [Name] - Contact: [Email]

**Goals**:
1. [Primary goal]
2. [Secondary goal]

**Timeline**: [Estimated weeks]
```

Save as: `discovery-sessions/[NNN-project-name]/session.meta.md`

---

## Step 2: Problem Exploration (Discovery Facilitator)

### Objective
Conduct structured interviews with stakeholders to understand the problem space.

### Agent: Discovery Facilitator
Load: `.discovery/primitives/agents/discovery-facilitator.instructions.md`

### Context to Provide Agent
- Session metadata
- Organizational context from memory files
- Interview transcript template
- Problem statement template (for reference)

### Actions

#### 2.1 Plan Interview Strategy
Identify stakeholder groups to interview:
- **Executive/Leadership**: Strategic perspective, business impact
- **Technical/Implementation**: Current system, constraints
- **Users/Customers**: Day-to-day pain points, workarounds
- **Operations/Support**: Frequency, severity, patterns
- **Other**: [Domain-specific roles]

#### 2.2 Conduct Stakeholder Interviews
For each stakeholder:

1. **Load Interview Context**:
   ```markdown
   You are about to interview [Name], [Role] at [Organization].
   
   **Purpose of this interview**: [What we're trying to learn]
   **Prior context**: [Summary of previous interviews]
   **Framework to use**: Five Whys + Jobs-to-be-Done
   
   Follow the interview protocol in discovery-facilitator.instructions.md
   ```

2. **Conduct Interview** (30-60 minutes)
   - Apply Five Whys to reach root causes
   - Use Jobs-to-be-Done for user perspectives
   - Paraphrase and validate understanding
   - Flag ambiguities and contradictions
   - Document implicit requirements

3. **Generate Interview Transcript**
   - Use template: `interview-transcript.template.md`
   - Save to: `interviews/NNN-role-interview.md`
   - Include verbatim quotes, insights, open questions

4. **Update Working Notes**
   ```markdown
   ## After Interview [N]
   
   **New Themes Emerged**:
   - [Theme]
   
   **Reinforced Themes**:
   - [Theme] (now mentioned by X stakeholders)
   
   **Contradictions Found**:
   - [Stakeholder A] vs [Stakeholder B] on [Topic]
   
   **Questions for Next Interview**:
   - [Question]
   ```

#### 2.3 Determine Interview Completeness
After each interview, assess:
- [ ] Have we covered all affected stakeholder groups?
- [ ] Have we reached root causes (not just symptoms)?
- [ ] Have we quantified business impact?
- [ ] Have we identified constraints?
- [ ] Are there unresolved contradictions?

**Continue interviews** until all major perspectives are captured.

---

## Step 3: Problem Synthesis (Discovery Facilitator)

### Objective
Synthesize all interview findings into a coherent problem statement.

### Agent: Discovery Facilitator (synthesis mode)

### Context to Provide Agent
- All interview transcripts
- Organizational context
- Problem statement template
- Instruction: "Synthesize findings using delta update approach"

### Actions

#### 3.1 Generate Initial Problem Statement (v1)
```markdown
## Context for Agent:

Review all interview transcripts and synthesize findings into a problem statement.

**Instructions**:
1. Use the problem-statement.template.md as structure
2. Focus on WHAT the problem is, not HOW to solve it
3. Include quantified business impact from interviews
4. Document root causes from Five Whys analyses
5. List all constraints mentioned
6. Create measurable success criteria

**Synthesis Principles**:
- Use stakeholder's own words (quoted) where powerful
- Resolve contradictions or document them explicitly
- Make all assumptions explicit
- Quantify everything possible

Create: working/problem-statement-v1.md
```

#### 3.2 Iterative Refinement (v2, v3, etc.)
As new information emerges or clarity improves:

```markdown
## Delta Update to Problem Statement

**Version**: v[N]
**Changes from v[N-1]**:

**Additions** (new information):
+ [New element with source]

**Corrections** (changed understanding):
~ Was: [Previous understanding]
~ Now: [Corrected understanding]
~ Source: [Interview or validation]

**Validations** (confirmed assumptions):
✓ [Assumption] confirmed by [Stakeholder]

**Open Questions** (still need resolution):
? [Question needing answer]

Create: working/problem-statement-v[N].md
```

#### 3.3 Create Supporting Artifacts
From the problem statement, generate:

**Success Criteria Document**:
```markdown
# Success Criteria - [Project Name]

| Metric | Baseline | Target | Method | Timeline |
|--------|----------|--------|--------|----------|
| [From problem statement] | [Current] | [Goal] | [How] | [When] |
```
Save to: `working/success-criteria.md`

**Constraints Document**:
```markdown
# Constraints - [Project Name]

## [Constraint Type]
- **Constraint**: [Description]
- **Source**: [Who/why]
- **Type**: Hard/Soft
- **Impact**: [Description]
```
Save to: `working/constraints.md`

---

## Step 4: Stakeholder Validation

### Objective
Ensure all stakeholders agree on the problem definition before proceeding.

### Agent: Discovery Facilitator (validation mode)

### Actions

#### 4.1 Prepare Validation Package
Create a review document:
```markdown
# Problem Statement Review - [Project Name]

Dear [Stakeholder],

You participated in our discovery interview on [Date]. Based on your input
and conversations with [X other stakeholders], we've synthesized the 
following problem statement.

**Please review and confirm**:
1. Does this accurately represent the problem as you understand it?
2. Is the business impact correctly stated?
3. Are the success criteria appropriate?
4. Are there any contradictions or inaccuracies?

[Include problem statement here]

**Your Response**:
- [ ] Approved as-is
- [ ] Approved with minor comments (listed below)
- [ ] Needs revision (major issues listed below)

Comments:
[Space for feedback]
```

#### 4.2 Collect Stakeholder Feedback
Send to each interviewed stakeholder for review.

Track responses:
```markdown
## Validation Tracking

| Stakeholder | Role | Review Date | Status | Comments |
|-------------|------|-------------|--------|----------|
| [Name] | [Role] | [Date] | [Status] | [Summary] |
```

Save to: `validation/stakeholder-approvals.md`

#### 4.3 Address Contradictions
If stakeholders disagree:

```markdown
## Contradiction Resolution

**Issue**: [Description of disagreement]

**Stakeholder A Perspective** ([Name], [Role]):
[Their view]

**Stakeholder B Perspective** ([Name], [Role]):
[Their view]

**Resolution Strategy**:
- [ ] Reconvene stakeholders to discuss
- [ ] Escalate to decision-maker
- [ ] Document as known conflict
- [ ] Conduct additional research

**Outcome**:
[How was this resolved?]
```

#### 4.4 Finalize Problem Statement
Once all stakeholders approve:

1. Update to final version
2. Mark as `Status: Approved`
3. Copy to artifacts: `artifacts/problem-statement.final.md`
4. Update version history with approval dates

---

## Step 5: Feasibility Analysis (Feasibility Analyzer)

### Objective
Assess whether solving this problem is technically and organizationally viable.

### Agent: Feasibility Analyzer
Load: `.discovery/primitives/agents/feasibility-analyzer.instructions.md`

### Context to Provide Agent
- Final approved problem statement
- Success criteria
- Constraints document
- Organizational context
- Feasibility report template

### Actions

#### 5.1 Conduct Precedent Research
```markdown
## Instructions for Agent:

Research similar implementations of this problem domain.

**Research Questions**:
1. Has anyone solved a problem like this before?
2. At what scale?
3. What were success rates?
4. What were common failure modes?
5. What approaches succeeded?

**Sources to Search**:
- Case studies from similar organizations
- Technical blog posts and postmortems
- Academic research papers
- Industry analyst reports
- Open source project histories

**Deliverable**:
Create: working/research-notes.md with:
- At least 5 case studies
- Both successes and failures
- Patterns across implementations
- All sources cited with URLs
```

#### 5.2 Assess Capability Gaps
```markdown
## Instructions for Agent:

Compare current organizational capabilities against what's needed.

**Analysis Framework**:

**Current Capabilities**:
- Technical skills present: [from org context]
- Infrastructure: [from tech stack context]
- Process maturity: [from org context]

**Required Capabilities**:
- [Based on problem domain and precedent research]

**Gap Analysis**:
For each gap, determine:
- Size: Major/Minor
- Criticality: Must-have/Nice-to-have
- Acquisition strategy: Hire/Train/Contract
- Timeline: Weeks/Months
- Cost: Estimate

**Deliverable**:
Add section to: working/feasibility-report-draft.md
```

#### 5.3 Identify and Assess Risks
```markdown
## Instructions for Agent:

Identify risks across three categories:

**Technical Risks**:
- Integration complexity
- Scalability concerns
- Data challenges
- Security vulnerabilities

**Business Risks**:
- Timeline uncertainty
- Resource availability
- Budget constraints
- Adoption challenges

**External Risks**:
- Vendor dependencies
- Regulatory changes
- Market dynamics
- Technology evolution

For each risk:
- Likelihood: H/M/L (with evidence)
- Impact: H/M/L (with description)
- Risk Score: 1-9
- Mitigation: 2-3 strategies
- Owner: Who should manage this?

**Deliverable**:
Create: artifacts/risk-register.md
```

#### 5.4 Validate Constraints
```markdown
## Instructions for Agent:

Review each constraint from constraints.md

For each constraint:
1. **Validate**: Is this actually a constraint or an assumption?
2. **Categorize**: Hard (immutable) or Soft (negotiable)
3. **Source**: Document origin and rationale
4. **Impact**: What's the cost of honoring this?
5. **Alternatives**: What if we relaxed it?
6. **Recommendation**: Keep/Negotiate/Challenge

**Deliverable**:
Update: working/constraints-validated.md
```

---

## Step 6: Feasibility Recommendation (Feasibility Analyzer)

### Objective
Synthesize analysis into a clear, evidence-based recommendation.

### Agent: Feasibility Analyzer (recommendation mode)

### Context to Provide Agent
- All research notes
- Capability gap analysis
- Risk register
- Validated constraints
- Feasibility report template

### Actions

#### 6.1 Synthesize Findings
```markdown
## Instructions for Agent:

Based on your complete analysis, determine feasibility recommendation.

**Decision Framework**:

**GO** if:
- Multiple successful precedents exist
- Capability gaps are small/addressable
- All high risks have viable mitigations
- Constraints are manageable
- Success rate > 60% in similar contexts

**CONDITIONAL GO** if:
- Precedents exist but with caveats
- Capability gaps require specific actions first
- High risks can be mitigated IF conditions met
- Some constraints may need negotiation

**POC REQUIRED** if:
- Limited precedents (unproven territory)
- Critical unknowns that research can't answer
- Need to validate key assumptions
- Success/failure hinges on uncertain factors

**NO-GO** if:
- No successful precedents at required scale
- Fundamental capability gaps (6+ months to close)
- High risks with no viable mitigations
- Constraints make success impossible

**Required**:
- State confidence level (XX%)
- Provide rationale with evidence
- List critical success factors
- Estimate timeline/resources (if applicable)

**Deliverable**:
Complete: artifacts/feasibility-report.md
```

#### 6.2 Document Recommendation
Using feasibility-report.template.md, create comprehensive report including:
- Executive summary with recommendation
- Technical viability assessment
- Risk assessment
- Constraint validation
- Capability gap analysis
- Detailed rationale
- Next steps

Save to: `artifacts/feasibility-report.md`

---

## Step 7: Completion Validation

### Objective
Ensure Phase 0 is complete and ready for handoff to Phase 1.

### Agent: Can use either agent in review mode

### Actions

#### 7.1 Run Completion Checklist
Load: `.discovery/primitives/checklists/phase-0-completion.checklist.md`

Review each criterion:
```markdown
## Checklist Review

Go through each section of the checklist:

**Critical Criteria**: [X/8 met]
- [List any gaps]

**Important Criteria**: [X/41 met - Need 33+]
- [List any gaps]

**Documentation Quality**: [X/17 met]
- [List any gaps]

**Readiness for Phase 1**: [X/11 met]
- [List any gaps]

**Overall Status**: [COMPLETE | CONDITIONAL | NOT COMPLETE]

**Action Items** (if not complete):
| Gap | Owner | Action | Due |
|-----|-------|--------|-----|
| [Gap] | [Name] | [Action] | [Date] |
```

Save to: `validation/completion-checklist.md`

#### 7.2 Stakeholder Final Approval
Prepare approval package:
```markdown
# Phase 0 Approval Package

**Project**: [Name]
**Recommendation**: [GO/CONDITIONAL/POC/NO-GO]
**Confidence**: [XX%]

**Deliverables**:
- Problem Statement: [Link]
- Feasibility Report: [Link]
- Risk Register: [Link]
- Success Criteria: [Link]
- Interview Transcripts: [Links]

**Key Findings**:
1. [Finding]
2. [Finding]
3. [Finding]

**Requesting Approval**:
- [ ] Project Sponsor
- [ ] Technical Lead
- [ ] Business Owner

**Next Steps** (if approved):
[Actions for Phase 1 transition]
```

#### 7.3 Package Artifacts for Phase 1
If approved, prepare handoff:

```bash
# Create Phase 1 directory
mkdir -p specs/[project-name]/phase-0/

# Copy final artifacts
cp discovery-sessions/[NNN-project-name]/artifacts/* specs/[project-name]/phase-0/

# Create handoff document
# (Summary of key points for Phase 1 team)
```

Handoff document structure:
```markdown
# Phase 0 → Phase 1 Handoff

**Project**: [Name]
**Phase 0 Completion Date**: [Date]

## Quick Reference
- **Problem**: [One sentence]
- **Root Cause**: [Primary cause]
- **Business Impact**: [$X or Y% impact]
- **Success Criteria**: [Top 3]
- **Feasibility**: [GO/CONDITIONAL/POC/NO-GO]

## Critical Information for Specification
1. [Key point]
2. [Key point]
3. [Key point]

## Constraints to Honor
- [Constraint 1]
- [Constraint 2]

## Risks to Monitor
- [Risk 1]
- [Risk 2]

## Questions? Contact:
- Discovery Lead: [Name, email]
- Stakeholder contacts: [In session.meta.md]

## Full Artifacts
- Problem Statement: [path]
- Feasibility Report: [path]
- Risk Register: [path]
```

---

## Workflow Completion

### Success Criteria
Phase 0 is complete when:
- [ ] All critical checklist items passed
- [ ] 80%+ of important checklist items passed
- [ ] Stakeholders have approved
- [ ] Artifacts are packaged and ready
- [ ] Phase 1 team has what they need to begin specification

### Handoff to Phase 1
- Copy artifacts to `specs/[project-name]/phase-0/`
- Notify Phase 1 team
- Make discovery team available for questions
- Move to Phase 1 (Specification & Design)

---

## Context Engineering Notes

### Session Splitting
Use separate conversations for:
1. **Interview sessions**: One per stakeholder (prevents context mixing)
2. **Synthesis session**: Combine all interview findings
3. **Feasibility session**: Separate from discovery to maintain objectivity
4. **Review sessions**: Validation with stakeholders

### Memory Management
**Always Load**:
- Organization context
- Technical stack context
- Session metadata

**Load When Relevant**:
- Prior project memories (if similar problem)
- Specific stakeholder context (during their interview)

**Avoid Loading**:
- Other stakeholder interviews during synthesis (can bias)
- Unrelated prior discoveries

### Delta Updates
Use incremental refinement:
- Don't rewrite problem statement from scratch each time
- Add new information with `+` marker
- Update changed information with `~` marker
- Validate assumptions with `✓` marker
- Track open questions with `?` marker

This preserves the full evolution and prevents context collapse.

---

## Troubleshooting Common Issues

### "Interviews aren't revealing root causes"
- Are you applying Five Whys rigorously?
- Are you asking "why" at least 5 levels deep?
- Are you accepting surface symptoms as answers?
- **Action**: Review discovery-facilitator.instructions.md Five Whys section

### "Stakeholders disagree on problem definition"
- This is normal and valuable!
- Document the disagreement explicitly
- Reconvene stakeholders to discuss
- May need executive tie-breaker
- **Action**: See Step 4.3 Contradiction Resolution

### "Feasibility research isn't finding similar implementations"
- Broaden search terms
- Look for adjacent problem spaces
- Search for failure stories (postmortems)
- Check academic research
- **Action**: Review research protocol in feasibility-analyzer.instructions.md

### "Too much context - agent is getting confused"
- Use session splitting (separate conversations)
- Load only relevant memory files
- Focus agent on one task at a time
- **Action**: Review Context Engineering Notes above

### "Phase 0 taking too long"
- How many stakeholder groups have you covered? (Min 3)
- Are you going too deep too early?
- Can you parallelize interviews?
- **Action**: Focus on critical path - can refine later

---

**Remember**: Phase 0 success = Phase 1 proceeds without revisiting discovery. Invest the time now to save weeks later.
