# Phase 0: Discovery & Ideation - Quick Start Guide

**Purpose**: Use Phase 0 to validate that a problem exists and is worth solving before investing in solution design.

**When to Use Phase 0**:
- Starting a new initiative with unclear requirements
- Exploring a business problem or opportunity
- Validating stakeholder alignment before committing resources
- When you need a GO/NO-GO decision before proceeding

**When to Skip Phase 0**:
- Requirements are already crystal clear
- Small bug fix or well-defined enhancement
- Continuation of existing project with established understanding

---

## What You'll Produce

| Artifact | Purpose |
|----------|---------|
| **Problem Statement** | Clear definition of what problem we're solving |
| **Feasibility Report** | Assessment of whether this is achievable |
| **Risk Register** | Known risks and mitigations |
| **Success Criteria** | How we'll know if we succeeded |
| **Constraints** | Boundaries we must work within |

---

## Quick Start (30 minutes to first session)

### Step 1: Create Workspace

```bash
# Create project structure
mkdir -p projects/[project-name]/phase0/{interviews,working,artifacts,validation}

# Initialize context file
touch projects/[project-name]/phase0/phase0-context.md
```

### Step 2: Load Required Files

Load these into your AI context:

**Agent Instructions** (choose based on activity):
```
.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md
.sdlc/primitives/agents/phase0/feasibility-analyzer_instructions.md
```

**Configuration**:
```
.sdlc/config/phase0_config.md
```

**Organizational Context**:
```
.sdlc/memory/organization_context.md
.sdlc/memory/technical-stack_context.md
```

**Templates** (for reference):
```
.sdlc/primitives/templates/phase0/problem-statement_template.md
.sdlc/primitives/templates/phase0/feasibility-report_template.md
```

### Step 3: Start Discovery Session

Use this prompt to begin:

```
I'm starting Phase 0 discovery for [project/initiative name].

Here's what I know so far:
- Problem/opportunity: [Brief description]
- Key stakeholders: [List roles]
- Timeline pressure: [Any deadlines?]
- Known constraints: [List any known constraints]

Please help me plan stakeholder interviews to validate this problem.
Use the Discovery Facilitator agent instructions and Five Whys / 
Jobs-to-be-Done frameworks.
```

---

## Phase 0 Flow

```
┌─────────────────┐
│ 1. EXPLORE      │  Conduct stakeholder interviews
│    (1-5 days)   │  Use Five Whys, Jobs-to-be-Done
└────────┬────────┘
         ▼
┌─────────────────┐
│ 2. SYNTHESIZE   │  Combine findings into problem statement
│    (1 day)      │  Identify patterns and contradictions
└────────┬────────┘
         ▼
┌─────────────────┐
│ 3. ASSESS       │  Technical, Business, Resource, Timeline
│    (1-2 days)   │  feasibility across four dimensions
└────────┬────────┘
         ▼
┌─────────────────┐
│ 4. RECOMMEND    │  GO / CONDITIONAL GO / POC / NO-GO
│    (1 day)      │  with confidence level
└────────┬────────┘
         ▼
┌─────────────────┐
│ 5. VALIDATE     │  Stakeholder review and approval
│    (1-2 days)   │  
└─────────────────┘
```

---

## Key Activities

### Stakeholder Interviews

**Who to interview** (minimum coverage):
- 1 Executive/Sponsor (strategic view)
- 1 Technical Lead (feasibility view)
- 2+ End Users (pain point view)
- 1 Operations/Support (impact view)

**Use these frameworks**:
- **Five Whys**: Dig into root causes
- **Jobs-to-be-Done**: Understand motivations

**Chatmode**: Use `discovery-facilitator.chatmode.md` for structured interview sessions.

### Feasibility Assessment

Assess across four dimensions:

| Dimension | Key Question |
|-----------|--------------|
| **Technical** | Can we build this? |
| **Business** | Should we build this? |
| **Resource** | Do we have capacity? |
| **Timeline** | Can we deliver in time? |

**Chatmode**: Use `feasibility-analyzer.chatmode.md` for assessment sessions.

### Recommendation

**GO**: All dimensions favorable, proceed to Phase 1

**CONDITIONAL GO**: Proceed with specific conditions that must be met

**POC**: Too many unknowns - run time-boxed proof-of-concept first

**NO-GO**: Fundamental issues prevent success

---

## Completion Checklist

Before exiting Phase 0:

- [ ] Minimum stakeholder coverage achieved
- [ ] Problem statement drafted and validated
- [ ] All four feasibility dimensions assessed
- [ ] Risks identified and documented
- [ ] Success criteria defined
- [ ] Constraints documented
- [ ] Clear recommendation made (GO/CONDITIONAL/POC/NO-GO)
- [ ] Key stakeholders reviewed and approved

Use: `.sdlc/primitives/checklists/phase-0-completion_checklist.md`

---

## Handoff to Phase 1

If GO or CONDITIONAL GO, package these for Phase 1:

1. `problem-statement.md` - Final validated version
2. `feasibility-report.md` - Summary of assessment
3. `risk-register.md` - Risks for Phase 1 to track
4. `success-criteria.md` - How we measure success
5. `constraints.md` - Boundaries Phase 1 must respect

---

## Tips for Success

✅ **Don't skip stakeholder interviews** - Even brief conversations surface critical insights

✅ **Document contradictions** - Different stakeholders will disagree; capture this explicitly

✅ **Be honest about feasibility** - A NO-GO saves more than it costs

✅ **Time-box discovery** - Set a deadline; you can always learn more later

✅ **Get explicit approval** - Don't assume silence is agreement

---

## Common Pitfalls

❌ **Jumping to solutions** - Phase 0 is about the problem, not the solution

❌ **Interview only friendly stakeholders** - Include skeptics

❌ **Ignoring red flags** - If something seems off, investigate

❌ **Over-documenting** - Focus on insights, not transcript length

❌ **Skipping feasibility** - Enthusiasm isn't a substitute for assessment

---

## Need Help?

**Full Workflow**: `.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md`

**Interview Guide**: `.sdlc/primitives/workflows/phase0/interview-workflow.prompt.md`

**Session Recovery**: `.sdlc/primitives/workflows/phase0/phase0-session-bridge-workflow.prompt.md`

---

*Phase 0 is optional but valuable. When in doubt, a few days of discovery can save weeks of building the wrong thing.*
