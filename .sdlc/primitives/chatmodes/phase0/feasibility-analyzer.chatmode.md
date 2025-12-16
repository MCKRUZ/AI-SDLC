# Feasibility Analyzer Chatmode

## Purpose
Focused feasibility assessment sessions using the Feasibility Analyzer Agent to evaluate whether a project should proceed.

## When to Use This Mode
- Assessing technical feasibility of proposed solutions
- Evaluating business viability and ROI potential
- Analyzing resource requirements and availability
- Validating timeline constraints
- Researching precedents and similar implementations
- Making GO/NO-GO/CONDITIONAL/POC recommendations

## Session Setup

### Before Starting
Load these artifacts into context:
1. Feasibility Analyzer instructions (`feasibility-analyzer_instructions.md`)
2. Problem statement from discovery (`phase0/artifacts/problem-statement.md`)
3. Interview synthesis or key findings
4. Organization context (`../../memory/organization_context.md`)
5. Technical stack context (`../../memory/technical-stack_context.md`)
6. Feasibility report template (`../templates/phase0/feasibility-report_template.md`)
7. Risk register template (`../templates/phase0/risk-register_template.md`)
8. Phase 0 config (`../../config/phase0_config.md`)

### Agent Instructions
Load: `feasibility-analyzer_instructions.md`

### Session Goal
Define a clear goal for the session:
- "Assess technical feasibility for [solution approach]"
- "Evaluate business case and ROI"
- "Analyze resource requirements"
- "Research precedents for [technology/approach]"
- "Create comprehensive feasibility recommendation"

---

## Interaction Patterns

### Pattern 1: Technical Feasibility Assessment

**When to Use**: Evaluating whether the proposed solution can be built

**Opening Prompt**:
```
I need to assess the technical feasibility of [proposed solution/approach].

Problem Statement Summary:
[Paste problem statement or key points]

Proposed Solution Direction:
[Describe the general approach being considered]

Technical Context:
- Current tech stack: [List]
- Team expertise: [List key skills]
- Known constraints: [List]

Please assess technical feasibility across these dimensions:
1. Technology maturity (proven vs. emerging vs. experimental)
2. Team capability (skills match, learning curve)
3. Integration complexity (with existing systems)
4. Technical risks (what could go wrong)
5. Unknowns that need research or POC
```

**Follow-up Prompts**:
```
For technical risk #[N]: [Risk description]
Please provide:
1. Probability assessment (High/Medium/Low)
2. Impact if it occurs
3. Mitigation strategies
4. Early warning indicators
5. Contingency plan
```

**Closing Prompt**:
```
Please summarize the technical feasibility assessment:
1. Overall technical feasibility score (1-10)
2. Confidence level in this score (High/Medium/Low)
3. Top 3 technical risks
4. Key assumptions that must hold true
5. Recommended technical spikes or POCs
6. Technical verdict: Feasible / Feasible with Caveats / Not Feasible
```

---

### Pattern 2: Business Feasibility Assessment

**When to Use**: Evaluating business case, ROI, and strategic alignment

**Opening Prompt**:
```
I need to assess the business feasibility of [project/initiative].

Problem Statement:
[Paste or summarize]

Business Context:
- Strategic priorities: [List]
- Budget constraints: [If known]
- Expected benefits: [From discovery]
- Stakeholder expectations: [Key points]

Please assess business feasibility across:
1. Strategic alignment (does this support company goals?)
2. Value proposition (is the benefit clear and compelling?)
3. ROI potential (rough order of magnitude)
4. Opportunity cost (what else could we do with these resources?)
5. Market/competitive factors (timing, competition)
6. Organizational readiness (change management)
```

**ROI Deep Dive Prompt**:
```
Let's explore the ROI in more detail.

Potential Benefits:
[List benefits identified in discovery]

Please help me:
1. Categorize benefits (cost savings, revenue increase, risk reduction, efficiency)
2. Estimate magnitude where possible (order of magnitude is fine)
3. Identify how we would measure each benefit
4. Estimate time to realize benefits
5. Identify assumptions behind benefit estimates
```

**Closing Prompt**:
```
Please summarize the business feasibility assessment:
1. Overall business feasibility score (1-10)
2. Confidence level (High/Medium/Low)
3. Strongest business case arguments
4. Weakest points / concerns
5. Key assumptions that must hold
6. Business verdict: Feasible / Feasible with Caveats / Not Feasible
```

---

### Pattern 3: Resource Feasibility Assessment

**When to Use**: Evaluating whether you have the people, budget, and capacity

**Opening Prompt**:
```
I need to assess resource feasibility for [project].

Estimated Scope:
[High-level scope from discovery]

Available Resources:
- Team size: [N] developers
- Budget: [If known, or "TBD"]
- Timeline pressure: [Hard deadline? Flexible?]
- Competing priorities: [Other projects/work]

Skills Needed (estimated):
[List key skills from technical assessment]

Please assess resource feasibility:
1. Team capacity (can we staff this?)
2. Skills coverage (do we have the expertise?)
3. Budget adequacy (rough estimate vs. available)
4. Timeline realism (can we deliver in time?)
5. External dependencies (vendors, partners, approvals)
```

**Capacity Analysis Prompt**:
```
Let's do a rough capacity analysis.

Team composition:
[List team members and their current allocation]

Estimated effort:
[Rough estimate from discovery - even if uncertain]

Please help me:
1. Calculate available capacity (accounting for other work)
2. Identify skill gaps that require hiring/training/contractors
3. Estimate timeline based on realistic capacity
4. Identify capacity risks (key person dependencies, etc.)
5. Suggest team composition if we could staff ideally
```

**Closing Prompt**:
```
Please summarize the resource feasibility assessment:
1. Overall resource feasibility score (1-10)
2. Confidence level (High/Medium/Low)
3. Critical resource constraints
4. Skills gaps requiring action
5. Resource verdict: Feasible / Feasible with Caveats / Not Feasible
```

---

### Pattern 4: Timeline Feasibility Assessment

**When to Use**: Evaluating whether delivery timeline is realistic

**Opening Prompt**:
```
I need to assess timeline feasibility for [project].

Timeline Constraints:
- Hard deadline: [Yes/No - if yes, what?]
- Business driver: [Why this timeline?]
- Flexibility: [Any room to negotiate?]

Scope Summary:
[High-level scope]

Resource Context:
[Team size, availability]

Please assess timeline feasibility:
1. Scope vs. timeline match (is it achievable?)
2. Critical path items (what determines the timeline?)
3. Dependencies (external factors that could delay)
4. Buffer/contingency (is there room for problems?)
5. Phasing options (could we deliver incrementally?)
```

**Phasing Analysis Prompt**:
```
The timeline seems tight. Let's explore phasing options.

Current scope:
[List major features/capabilities]

Please help me:
1. Identify what could be MVP (must have for initial value)
2. Identify what could be Phase 2 (important but can wait)
3. Identify what could be cut (nice to have)
4. Estimate timeline for MVP only
5. Assess risk of scope creep if we start with MVP
```

**Closing Prompt**:
```
Please summarize the timeline feasibility assessment:
1. Overall timeline feasibility score (1-10)
2. Confidence level (High/Medium/Low)
3. Recommended timeline (if different from constraint)
4. Key schedule risks
5. Phasing recommendation
6. Timeline verdict: Feasible / Feasible with Caveats / Not Feasible
```

---

### Pattern 5: Precedent Research

**When to Use**: Researching similar implementations for lessons learned

**Opening Prompt**:
```
I need to research precedents for [approach/technology/solution type].

What we're considering:
[Describe the approach]

What I want to learn:
1. Has this been done before? At what scale?
2. What were the success factors?
3. What were common failure modes?
4. What lessons can we apply?
5. Who could we talk to for insights?

Please help me structure this research:
- Internal precedents (within our organization)
- Industry precedents (similar companies)
- Technology precedents (similar technical approaches)
```

**Internal Research Prompt**:
```
Let's check for internal precedents.

Organization context:
[Relevant details about your company]

Previous projects that might be relevant:
[List any known similar projects]

Please help me:
1. Identify what made these projects succeed/fail
2. Extract lessons applicable to our project
3. Identify people we should talk to
4. Find reusable assets (code, designs, documentation)
```

**Closing Prompt**:
```
Please summarize the precedent research:
1. Most relevant precedents found
2. Key success factors from precedents
3. Warning signs / failure patterns to avoid
4. Confidence boost or concern from research
5. Recommendations for our approach
```

---

### Pattern 6: Comprehensive Feasibility Recommendation

**When to Use**: Creating the final GO/NO-GO/CONDITIONAL/POC recommendation

**Opening Prompt**:
```
I'm ready to create the comprehensive feasibility recommendation.

Assessment summaries:
- Technical feasibility: [Score, verdict]
- Business feasibility: [Score, verdict]  
- Resource feasibility: [Score, verdict]
- Timeline feasibility: [Score, verdict]

Key risks identified:
[List top risks]

Key assumptions:
[List critical assumptions]

Please create a comprehensive feasibility recommendation following the template:
1. Executive Summary (one paragraph)
2. Recommendation (GO / CONDITIONAL GO / POC / NO-GO)
3. Confidence Level
4. Summary by dimension (Technical, Business, Resource, Timeline)
5. Critical success factors
6. Key risks and mitigations
7. Conditions (if CONDITIONAL GO)
8. POC scope (if POC recommended)
9. Next steps
```

**Recommendation Criteria**:
```
Help me calibrate the recommendation:

**GO** if:
- All dimensions score 7+ AND
- No unmitigated critical risks AND
- Key assumptions are validated or low-risk

**CONDITIONAL GO** if:
- Most dimensions score 6+ AND
- Critical risks have mitigation plans AND
- Conditions for success are achievable

**POC** if:
- Technical feasibility is uncertain (< 6) OR
- Key assumptions are unvalidated AND
- A time-boxed POC could resolve uncertainty

**NO-GO** if:
- Any dimension scores < 4 with no path to improve OR
- Critical risks have no viable mitigation OR
- Business case is fundamentally flawed

Based on our assessments, which recommendation fits?
```

---

## Best Practices for This Mode

### Do's
- ✅ Be evidence-based - cite discovery findings
- ✅ Quantify where possible, even rough estimates
- ✅ Acknowledge uncertainty explicitly
- ✅ Consider multiple scenarios (optimistic, realistic, pessimistic)
- ✅ Identify assumptions and their risk if wrong
- ✅ Provide actionable recommendations
- ✅ Make the recommendation clear and defensible

### Don'ts
- ❌ Don't overstate confidence
- ❌ Don't ignore inconvenient evidence
- ❌ Don't assume constraints can be negotiated away
- ❌ Don't skip dimensions because they're "obviously fine"
- ❌ Don't make GO recommendation to please stakeholders
- ❌ Don't forget to document assumptions

---

## Session Outputs

### Primary Artifacts
- **Feasibility Report**:
  - Four-dimension assessment (Technical, Business, Resource, Timeline)
  - Overall recommendation
  - Confidence level
  - Supporting evidence
  
- **Risk Register**:
  - Risks identified during assessment
  - Probability and impact ratings
  - Mitigation strategies
  - Owners and timelines

### Work-in-Progress Outputs
- Dimension-specific assessments
- Precedent research notes
- Assumption logs
- Scenario analyses

---

## Quality Checks Before Ending Session

- [ ] All four dimensions assessed
- [ ] Each dimension has a score and verdict
- [ ] Key risks documented with mitigations
- [ ] Assumptions explicitly stated
- [ ] Recommendation is clear (GO/CONDITIONAL/POC/NO-GO)
- [ ] Confidence level stated
- [ ] Conditions listed (if CONDITIONAL)
- [ ] POC scope defined (if POC)
- [ ] Report follows template format
- [ ] Evidence from discovery is cited

---

## Transitioning Out of This Mode

**When Feasibility is Complete**:
- All dimensions assessed
- Recommendation documented
- Stakeholders briefed
- Decision made (proceed or not)

**If GO or CONDITIONAL GO → Phase 1**:
```
Feasibility assessment complete with [GO/CONDITIONAL GO] recommendation.

Please create a Phase 1 handoff package including:
1. Problem statement (final)
2. Feasibility summary (key points for Phase 1 to know)
3. Constraints to carry forward
4. Risks to track
5. Success criteria
6. Recommended scope boundaries
7. Any conditions that must be addressed in Phase 1
```

**If POC → Define POC Scope**:
```
Feasibility assessment recommends POC before proceeding.

Please define the POC:
1. Key question(s) the POC must answer
2. Success criteria for POC
3. POC scope (what to build)
4. POC timeline (time-boxed)
5. POC resources needed
6. Decision criteria (when do we GO vs NO-GO after POC)
```

---

*Created for: Phase 0 - Discovery & Ideation*
*Works with: Feasibility Analyzer Agent*
*Last Updated: 2025-12-15*
