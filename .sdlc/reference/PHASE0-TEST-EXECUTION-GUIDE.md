# Phase 0 Test Execution Guide

**Purpose**: Explicit, step-by-step instructions for conducting a Phase 0 discovery test that fully exercises the agentic SDLC methodology.

**Version**: 2.0  
**Last Updated**: 2025-11-07  
**Target Audience**: Framework developers testing/validating the Phase 0 methodology

---

## Overview

This guide ensures you properly load, follow, and validate the Phase 0 methodology during testing. It leaves nothing to chance - every prompt, every file, every checkpoint is explicitly defined.

### Success Criteria for Test

By the end of this test, you will have:

✅ **Loaded all methodology components** (agents, workflows, templates, config)  
✅ **Followed the 7-step discovery workflow** exactly as designed  
✅ **Created all required artifacts** using templates  
✅ **Tracked session state** in phase0-context.md  
✅ **Applied methodology quality gates** at each checkpoint  
✅ **Validated completion** using the checklist  
✅ **Achieved methodology adherence score** ≥80%  

---

## Prerequisites

### What You Need

1. **Access to Claude** (or equivalent AI assistant with long context)
2. **Test project repository** (test/ directory in your agentic-sdlc repo)
3. **Test scenario** (real or fictional project requiring discovery)
4. **Time allocation**: 6-10 hours (can be split across multiple sessions)
5. **Note-taking tool** (for tracking what you observe)

### Test Scenario Selection

**Option A: Fictional Scenario** (Recommended for first test)
- Create a detailed fictional company/problem
- Allows full control over revelations
- Can design progressive complexity
- Example: Manufacturing company cloud migration

**Option B: Real Project** (For validation after framework is mature)
- Use actual company/problem (with appropriate permissions)
- More authentic but less controlled
- Harder to design progressive revelation

---

## Phase 0 Test Execution - Step by Step

---

## SESSION 1: Setup & First Interviews (60-90 minutes)

### STEP 1.1: Create Test Project Structure (5 min)

**Action**: Create the directory structure for your test project.

```bash
# Navigate to your test directory
cd test/projects/

# Create project structure
mkdir -p 002-[your-project-name]/phase0/{interviews,working,artifacts,validation}

# Example:
mkdir -p 002-customer-portal-modernization/phase0/{interviews,working,artifacts,validation}
```

**Verification**:
```bash
# You should see:
test/projects/002-customer-portal-modernization/
└── phase0/
    ├── interviews/
    ├── working/
    ├── artifacts/
    └── validation/
```

**Checkpoint**: ✅ Directory structure created

---

### STEP 1.2: Start New AI Session (2 min)

**Action**: Open a fresh conversation with Claude (or your AI assistant).

**Why Fresh Session**: You want to test the methodology's ability to work from scratch, simulating how a real facilitator would start.

**Checkpoint**: ✅ New AI session started

---

### STEP 1.3: Load Discovery Facilitator Agent Instructions (3 min)

**Action**: Copy and paste the exact prompt below into your AI session.

**PROMPT TO USE** (copy verbatim):

```
I am conducting a Phase 0 discovery test for an agentic SDLC framework.
I need you to act as the Discovery Facilitator agent.

Please load and internalize the following agent instructions file.
After reading, confirm your understanding of your role, responsibilities,
and the frameworks you should apply (Five Whys, Jobs-to-be-Done).

[PASTE THE ENTIRE CONTENTS OF: test/.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md]

After loading, please confirm:
1. What is your primary role?
2. What frameworks will you use?
3. What are your key responsibilities?
4. What outputs will you create?
```

**What To Paste**: Open `test/.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md` and paste the ENTIRE file contents into the bracketed section above.

**Expected Response**: Claude should summarize:
- Role: Conduct stakeholder interviews, synthesize insights
- Frameworks: Five Whys, Jobs-to-be-Done
- Responsibilities: Interview planning, execution, documentation, synthesis
- Outputs: Interview transcripts, problem statements, insights

**Checkpoint**: ✅ Agent instructions loaded and confirmed

---

### STEP 1.4: Load Phase 0 Configuration (3 min)

**Action**: Load the configuration that defines HOW Phase 0 operates.

**PROMPT TO USE**:

```
Now please load the Phase 0 configuration file that defines the methodology
settings, quality standards, and operational parameters for discovery.

[PASTE THE ENTIRE CONTENTS OF: test/.sdlc/config/phase0_config.md]

After loading, please confirm:
1. What is the minimum stakeholder coverage required?
2. What is the feasibility scoring approach?
3. What are the quality thresholds for artifacts?
4. When should we stop conducting interviews (saturation criteria)?
```

**What To Paste**: The entire `test/.sdlc/config/phase0_config.md` file.

**Expected Response**: Claude should confirm:
- Minimum coverage: 1 executive, 1 technical, 2 users, 1 operations
- Feasibility: Four-dimension framework (technical, business, resource, timeline)
- Quality: INVEST principles for requirements, etc.
- Saturation: Stop after 3+ interviews with no new themes

**Checkpoint**: ✅ Configuration loaded and confirmed

---

### STEP 1.5: Load Discovery Workflow (5 min)

**Action**: Load the 7-step workflow that orchestrates the entire Phase 0 process.

**PROMPT TO USE**:

```
Now please load the Discovery Workflow that defines the complete Phase 0 process.
This is the master workflow you will follow step-by-step.

[PASTE THE ENTIRE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md]

After loading, please:
1. Summarize the 7 steps of the workflow
2. Confirm what Step 1 requires (Initiate Discovery)
3. Tell me when we should move from Step 2 to Step 3
```

**What To Paste**: The entire `discovery-workflow.prompt.md` file.

**Expected Response**: Claude should outline:
- Step 1: Initiate Discovery
- Step 2: Problem Exploration (stakeholder interviews)
- Step 3: Problem Synthesis
- Step 4: Feasibility Analysis
- Step 5: Risk Assessment
- Step 6: Success Criteria Definition
- Step 7: Validation

**Checkpoint**: ✅ Workflow loaded and confirmed

---

### STEP 1.6: Load Interview Workflow (5 min)

**Action**: Load the detailed interview protocol.

**PROMPT TO USE**:

```
Please load the Interview Workflow that provides detailed guidance for conducting
individual stakeholder interviews.

[PASTE THE ENTIRE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/interview-workflow.prompt.md]

After loading, please:
1. Summarize the interview process steps
2. Confirm how you will apply Five Whys
3. Explain how you will document interviews
```

**What To Paste**: The entire `interview-workflow.prompt.md` file.

**Expected Response**: Claude should describe:
- 7-step interview process (pre-interview → opening → exploration → Five Whys → impact → closing → documentation)
- Five Whys: Ask "why" 5 times to reach root causes
- Documentation: Create structured transcript using template

**Checkpoint**: ✅ Interview workflow loaded and confirmed

---

### STEP 1.7: Load Templates (Reference) (5 min)

**Action**: Load the templates so Claude knows what format to use for artifacts.

**PROMPT TO USE**:

```
Please load the following templates for reference. You will use these
structures when creating artifacts.

INTERVIEW TRANSCRIPT TEMPLATE:
[PASTE: test/.sdlc/primitives/templates/phase0/interview-transcript_template.md]

PROBLEM STATEMENT TEMPLATE:
[PASTE: test/.sdlc/primitives/templates/phase0/problem-statement_template.md]

FEASIBILITY REPORT TEMPLATE:
[PASTE: test/.sdlc/primitives/templates/phase0/feasibility-report_template.md]

RISK REGISTER TEMPLATE:
[PASTE: test/.sdlc/primitives/templates/phase0/risk-register_template.md]

Confirm you have loaded these templates and understand the structure
for each artifact type.
```

**What To Paste**: Each template file's complete contents in the designated sections.

**Expected Response**: Claude should confirm it understands the structure of each template.

**Checkpoint**: ✅ Templates loaded and confirmed

---

### STEP 1.8: Create Session Metadata (10 min)

**Action**: Now begin the actual test. Start with Step 1 of the workflow: Initiate Discovery.

**PROMPT TO USE**:

```
Perfect! All methodology components are loaded. We're now ready to begin
Phase 0 discovery following the workflow.

We are at STEP 1: INITIATE DISCOVERY.

According to the workflow, Step 1.3 requires creating session metadata.

Please create session.meta.md for the following test scenario:

PROJECT: [Your project name and brief description]

SCENARIO: [2-3 paragraphs describing the test scenario - company,
problem, initial goals, stakeholders]

Create the session.meta.md file following the format specified in the
discovery-workflow. Include:
- Session ID and project name
- Stakeholders to interview (at least 7-9 planned)
- Goals
- Estimated timeline
```

**What You Provide**: Your test scenario details. Be specific. Example:

```
PROJECT: Customer Portal Modernization for RetailCo

SCENARIO: RetailCo is a 500-employee retail company with 50 retail locations.
Their customer-facing web portal was built in 2010 and is showing its age.
Customers complain about slow performance, confusing navigation, and lack of
mobile support. The CEO wants to modernize to improve customer satisfaction
and enable online ordering. The CTO is concerned about cost and timeline.
Current portal serves 10,000 active customers.

Initial Goals: Modernize portal, improve UX, add mobile support, enable online ordering.
Initial Timeline Assumption: 12 months
Initial Budget Assumption: $500K
```

**Expected Output**: Claude creates a complete session.meta.md file with:
- Project name and ID
- List of 7-9 stakeholders to interview (CEO, CTO, customers, support, developers, etc.)
- Goals
- Timeline estimate

**What You Do**: Save the generated content to:  
`test/projects/002-[project-name]/phase0/session.meta.md`

**Checkpoint**: ✅ session.meta.md created

---

### STEP 1.9: Create Phase 0 Context File (10 min)

**Action**: Create the state tracking file that will be updated throughout Phase 0.

**PROMPT TO USE**:

```
Now create the phase0-context.md file that will track our progress through
Phase 0 discovery.

This file should include:
- Current status (IN PROGRESS)
- Current step (Step 1: Initiate Discovery - COMPLETE, moving to Step 2)
- Progress tracker showing all 7 steps
- Interview tracker (0 of 9 complete)
- Artifact status (none created yet)
- Open issues (none yet)
- Methodology adherence tracker (initialize at 0/12)

Use a structured format that's easy to update incrementally.
```

**Expected Output**: Claude creates a structured context tracking file.

**What You Do**: Save the generated content to:  
`test/projects/002-[project-name]/phase0/phase0-context.md`

**Checkpoint**: ✅ phase0-context.md created

---

### STEP 1.10: Plan Interview Strategy (10 min)

**Action**: Move to Step 2 of workflow: Problem Exploration. Begin with interview planning.

**PROMPT TO USE**:

```
We have completed STEP 1: INITIATE DISCOVERY.

We are now at STEP 2: PROBLEM EXPLORATION.

According to the workflow, Step 2.1 is to plan our interview strategy.

Based on our test scenario, please:
1. Identify the stakeholder groups we need to interview
2. Recommend an interview sequence (which order to conduct interviews)
3. Explain the rationale for this sequence
4. Identify what we hope to learn from each stakeholder group

For this test, we will conduct interviews in the order you recommend.
```

**Expected Output**: Claude provides:
- List of stakeholder groups (Executive, Technical, Users, Operations, etc.)
- Recommended sequence (often: Executive → Technical → Users → Operations)
- Rationale (start with strategic view, move to operational reality)
- Learning objectives for each group

**What You Do**: Review the plan. Confirm it makes sense. You can adjust if needed.

**Checkpoint**: ✅ Interview strategy planned

---

### STEP 1.11: Conduct First Interview (20 min)

**Action**: Conduct the first stakeholder interview following the interview workflow.

**PROMPT TO USE**:

```
Let's conduct our first interview following the interview workflow.

INTERVIEW #1: [Stakeholder Role - e.g., CEO]

Please guide me through this interview using:
- The interview workflow's 7-step process
- Five Whys methodology for root cause analysis
- Jobs-to-be-Done framework for understanding motivations

For this test, I will provide the stakeholder's responses. You will:
1. Ask questions following the interview protocol
2. Apply active listening techniques (paraphrasing, etc.)
3. Probe deeper when needed
4. Flag any implicit requirements or contradictions

Let's begin. Please start with the opening phase of the interview.
```

**How This Works**:
1. Claude asks a question (as interviewer)
2. You respond as the stakeholder
3. Claude asks follow-ups, probes, uses Five Whys
4. Continue for 15-20 exchanges
5. Claude closes the interview

**Example Exchange**:
```
CLAUDE: "Thank you for meeting with me. Can you tell me about your role
and how the customer portal affects your work?"

YOU (as CEO): "I'm the CEO. The portal is our digital front door. But
frankly, it's embarrassing. Customers complain constantly about it."

CLAUDE: "You mentioned customers complain constantly. Can you give me
a specific example of a recent complaint?"

YOU (as CEO): "Last week our biggest customer called me directly - bypassed
support - to say they couldn't place an order on mobile..."

[Continue...]
```

**Duration**: Aim for 15-20 substantive exchanges (roughly a 45-60 minute real interview).

**Checkpoint**: ✅ First interview conducted

---

### STEP 1.12: Document First Interview (10 min)

**Action**: Have Claude generate the interview transcript.

**PROMPT TO USE**:

```
That completes Interview #1 with [Stakeholder Role].

Please now create the interview transcript using the interview transcript
template you loaded earlier.

Include:
- Metadata (date, stakeholder, duration, session number)
- Context
- All key questions and responses (not necessarily verbatim, but capturing
  the substance of what was discussed)
- Implicit requirements identified
- Contradictions flagged (if any with prior knowledge)
- Open questions for follow-up
- Key insights and observations

Create: 001-[stakeholder-role]-interview.md
```

**Expected Output**: Claude generates a complete, well-structured interview transcript following the template format.

**What You Do**: 
1. Review the transcript for accuracy
2. Save to: `test/projects/002-[project-name]/phase0/interviews/001-ceo-interview.md` (adjust role as appropriate)

**Checkpoint**: ✅ First interview documented

---

### STEP 1.13: Update Phase 0 Context (5 min)

**Action**: Update the context file to reflect progress.

**PROMPT TO USE**:

```
Please update phase0-context.md to reflect that we have:
- Completed Interview #1 (1 of 9 complete)
- Current step is still Step 2: Problem Exploration
- Add the first interview to the completed interviews list
- Update methodology adherence (we're following the process)

Provide the updated content for phase0-context.md.
```

**Expected Output**: Claude provides updated context file content.

**What You Do**: Update the phase0-context.md file with the new content.

**Checkpoint**: ✅ Context updated

---

### STEP 1.14: Conduct Second Interview (20 min)

**Action**: Conduct the second interview following the same process.

**PROMPT TO USE**:

```
Let's conduct Interview #2.

INTERVIEW #2: [Next Stakeholder Role - e.g., CTO]

Same process as Interview #1:
- Follow interview workflow
- Apply Five Whys and Jobs-to-be-Done
- I'll provide stakeholder responses
- You guide the interview

IMPORTANT: As you conduct this interview, be alert for:
- Themes that match Interview #1 (consensus points)
- Themes that contradict Interview #1 (conflicts)
- New themes not mentioned by first stakeholder

Begin the interview now.
```

**Process**: Same as Interview #1 (15-20 exchanges).

**Checkpoint**: ✅ Second interview conducted

---

### STEP 1.15: Document Second Interview & Update Context (10 min)

**PROMPT TO USE**:

```
Interview #2 complete.

Please:
1. Create the interview transcript: 002-[stakeholder-role]-interview.md
2. Update phase0-context.md (2 of 9 interviews complete)

Additionally, please note:
- Any themes that appeared in BOTH interviews (consensus)
- Any contradictions between Interview #1 and Interview #2
- Any new themes that only appeared in Interview #2
```

**Expected Output**: 
- Interview transcript
- Updated context
- Theme analysis

**What You Do**: Save both files.

**Checkpoint**: ✅ Second interview documented and context updated

---

### SESSION 1 COMPLETE - Save State (5 min)

**Action**: You're now 2 interviews in. Time to pause Session 1.

**PROMPT TO USE**:

```
We're pausing Session 1 after completing 2 interviews.

Please create a SESSION 1 SUMMARY that includes:
1. What we accomplished (Steps 1-2 in progress, 2 interviews complete)
2. Key themes emerging (list)
3. Contradictions identified (list)
4. Next session goals (continue interviews)
5. Methodology adherence score so far (out of 12)

Save this as: working/session-1-summary.md
```

**Expected Output**: Session summary.

**What You Do**: 
1. Save the session summary
2. Review all files created:
   - session.meta.md ✅
   - phase0-context.md ✅
   - 001-[role]-interview.md ✅
   - 002-[role]-interview.md ✅
   - working/session-1-summary.md ✅

**Checkpoint**: ✅ Session 1 complete and saved

**END OF SESSION 1**

---

## SESSION 2: Continue Interviews & Start Synthesis (60-90 minutes)

### STEP 2.1: Resume Session Using Bridge Prompt (5 min)

**Action**: Start a NEW AI conversation (fresh context).

**PROMPT TO USE**:

```
I am resuming a Phase 0 discovery test that was paused after Session 1.

I need you to act as the Discovery Facilitator agent and resume where
we left off.

First, please load the following methodology components:

1. AGENT INSTRUCTIONS:
[PASTE: test/.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md]

2. PHASE 0 CONFIG:
[PASTE: test/.sdlc/config/phase0_config.md]

3. DISCOVERY WORKFLOW:
[PASTE: test/.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md]

4. INTERVIEW WORKFLOW:
[PASTE: test/.sdlc/primitives/workflows/phase0/interview-workflow.prompt.md]

After loading methodology, please review the following to understand
where we are:

5. CURRENT CONTEXT:
[PASTE: phase0-context.md file content]

6. SESSION 1 SUMMARY:
[PASTE: working/session-1-summary.md file content]

7. INTERVIEW TRANSCRIPTS (summaries):
- Interview #1 Key Points: [Paste executive summary from interview 1]
- Interview #2 Key Points: [Paste executive summary from interview 2]

After reviewing, please:
1. Confirm where we are in the workflow (Step X)
2. Summarize what we've learned so far
3. Tell me what the next action should be
4. Confirm you're ready to continue
```

**What To Paste**: All the indicated files/sections.

**Expected Response**: Claude should:
- Confirm it's acting as Discovery Facilitator
- Understand we're at Step 2 (Problem Exploration)
- Summarize: 2 of 9 interviews complete, themes emerging
- Next action: Continue conducting interviews
- Ready to proceed

**Checkpoint**: ✅ Session resumed successfully

---

### STEP 2.2: Conduct Interviews 3-5 (60 min)

**Action**: Conduct three more interviews following the same pattern.

**For Each Interview**:

1. **Conduct Interview** (20 min)
   ```
   Interview #[N]: [Stakeholder Role]
   
   Follow the interview workflow. I'll provide responses. Begin now.
   ```

2. **Document Interview** (10 min)
   ```
   Create interview transcript: 00[N]-[role]-interview.md
   Update phase0-context.md
   Note themes (consensus, contradictions, new)
   ```

3. **Save Files** (before next interview)

**Interview Roles to Cover** (aim for diversity):
- Interview #3: Technical lead (CTO, Architect, Dev Manager)
- Interview #4: End user or customer
- Interview #5: Operations or support role

**Progressive Revelation Strategy**:
- Interviews 1-2: High-level strategy and vision
- Interviews 3-4: Technical reality and constraints
- Interview 5: Operational challenges

**As Stakeholder, Deliberately Introduce**:
- Contradictions (e.g., CEO says 12 months, CTO says 24 months)
- Hidden constraints (e.g., legacy system dependencies)
- Cost surprises (e.g., licensing fees not in budget)
- Scope creep (e.g., "oh we also need to integrate with X, Y, Z")

**Checkpoint**: ✅ Interviews 3, 4, 5 complete and documented

---

### STEP 2.3: Assess Interview Saturation (10 min)

**Action**: After 5 interviews, check if we've reached saturation (Step 2.3 in workflow).

**PROMPT TO USE**:

```
We've now completed 5 interviews. According to the discovery workflow,
Step 2.3 is to determine interview completeness and check for saturation.

Please analyze our 5 interview transcripts and tell me:

1. THEME SATURATION: Have we heard the same themes repeated for the
   last 2-3 interviews? Or are we still discovering new themes?

2. STAKEHOLDER COVERAGE: According to phase0_config.md, have we met
   the minimum stakeholder coverage requirements?
   - At least 1 executive? ✅/❌
   - At least 1 technical lead? ✅/❌
   - At least 2 end users? ✅/❌
   - At least 1 operations? ✅/❌

3. ROOT CAUSE CLARITY: Have we reached root causes through Five Whys,
   or are we still at symptom level?

4. BUSINESS IMPACT QUANTIFIED: Do we have dollar amounts, time impacts,
   customer impacts documented?

5. RECOMMENDATION: Should we:
   A) Stop interviews and move to synthesis (Step 3)
   B) Conduct 2-3 more interviews to reach saturation
   C) Something else

Provide your analysis and recommendation.
```

**Expected Output**: Claude analyzes and recommends. Typically after 5 interviews you should continue to 7-9 total.

**Decision Point**: Based on Claude's analysis, decide whether to continue interviews or move to synthesis.

**Checkpoint**: ✅ Saturation assessed

---

### STEP 2.4: Conduct Final Interviews if Needed (40 min)

**If Claude recommends more interviews**, conduct 2-4 more following the same pattern.

**Key Roles to Add** (if not covered):
- Support/Help Desk (to understand pain points)
- Sales (to understand customer-facing impacts)
- Finance/Budget owner (to understand cost constraints)

**Checkpoint**: ✅ All necessary interviews complete (typically 7-9 total)

---

### SESSION 2 COMPLETE - Update State (5 min)

**PROMPT TO USE**:

```
Session 2 complete. We've now completed [N] interviews total.

Create SESSION 2 SUMMARY including:
1. Interviews conducted this session
2. Total interviews complete ([N] of 9)
3. Updated theme analysis across all interviews
4. All contradictions identified
5. Whether we've reached saturation
6. Readiness to move to Step 3: Problem Synthesis
7. Updated methodology adherence score

Save as: working/session-2-summary.md
```

**What You Do**: Save summary and update phase0-context.md.

**Checkpoint**: ✅ Session 2 complete

**END OF SESSION 2**

---

## SESSION 3: Problem Synthesis & Feasibility (60-90 minutes)

### STEP 3.1: Resume and Load Context (5 min)

**Action**: Start new AI session, use bridge prompt (same pattern as Session 2 start).

**PROMPT TO USE**:

```
Resuming Phase 0 discovery, Session 3.

[Load all methodology components - same as Step 2.1]

[Load phase0-context.md]

[Load session-2-summary.md]

[Load brief summaries of ALL interviews conducted so far]

We are ready to move from Step 2 (Problem Exploration) to
Step 3 (Problem Synthesis).

Confirm you're ready to synthesize findings into a problem statement.
```

**Checkpoint**: ✅ Session 3 resumed

---

### STEP 3.2: Synthesize Problem Statement v1 (20 min)

**Action**: This is Step 3 of the discovery workflow.

**PROMPT TO USE**:

```
We are at STEP 3: PROBLEM SYNTHESIS.

According to the workflow, Step 3.1 is to generate the initial problem
statement (v1) by synthesizing all interview findings.

Please review ALL interview transcripts (I will provide complete transcripts
or detailed summaries if context allows) and create problem-statement-v1.md
using the problem statement template.

INTERVIEW TRANSCRIPTS:
[Paste all interview transcripts or comprehensive summaries]

Requirements for problem-statement-v1.md:
1. Use the problem statement template structure
2. Apply Five Whys analysis to identify root causes (not just symptoms)
3. Quantify business impact with data from interviews
4. Document all constraints mentioned by stakeholders
5. Cite sources (e.g., "According to Interview #3 with CTO...")
6. Create measurable success criteria
7. Note all contradictions explicitly

Create: working/problem-statement-v1.md
```

**Expected Output**: Claude generates a comprehensive problem statement following the template.

**What You Do**: 
1. Review for accuracy and completeness
2. Save to: `working/problem-statement-v1.md`

**Checkpoint**: ✅ Problem statement v1 created

---

### STEP 3.3: Iterative Refinement - v2 (15 min)

**Action**: Step 3.2 of workflow - Iterative refinement.

**PROMPT TO USE**:

```
Now that we have problem-statement-v1.md, let's refine it.

Please review v1 and identify:
1. Any claims not supported by interview evidence
2. Any vague statements that need quantification
3. Any missing perspectives
4. Any contradictions not adequately addressed
5. Any root causes that need deeper Five Whys analysis

Based on your review, create problem-statement-v2.md with improvements.

For this test, simulate stakeholder feedback by identifying gaps
and addressing them in v2.
```

**Expected Output**: Claude creates refined v2 with improvements.

**What You Do**: Save to: `working/problem-statement-v2.md`

**Checkpoint**: ✅ Problem statement v2 created

---

### STEP 3.4: Finalize Problem Statement (10 min)

**Action**: Step 3.3 of workflow - Finalize.

**PROMPT TO USE**:

```
Review problem-statement-v2.md and confirm it meets quality standards:

QUALITY CHECKLIST:
✅ Clear problem definition (what, not how)
✅ Root causes identified (Five Whys applied)
✅ Business impact quantified ($, time, customers)
✅ All major constraints documented
✅ Success criteria are measurable (SMART)
✅ All claims cite interview sources
✅ Contradictions acknowledged and addressed
✅ Readable by both technical and non-technical stakeholders

If v2 meets all criteria, create the final version:
artifacts/problem-statement.final.md

If not, create v3 with remaining improvements.
```

**Expected Output**: Either final version or v3 with explanation.

**What You Do**: Save to appropriate location (artifacts/ if final, working/ if v3).

**Checkpoint**: ✅ Problem statement finalized

---

### STEP 3.5: Assess Feasibility (20 min)

**Action**: Move to Step 4 of workflow - Feasibility Analysis.

**PROMPT TO USE**:

```
We are at STEP 4: FEASIBILITY ANALYSIS.

Using the feasibility report template and the four-dimension framework
from phase0_config.md, please assess the feasibility of solving the
problem described in our final problem statement.

FOUR DIMENSIONS TO ASSESS:
1. Technical Feasibility: Can it be built?
2. Business Feasibility: Should it be built (ROI, market, strategy)?
3. Resource Feasibility: Do we have skills/people/time?
4. Timeline Feasibility: Can it be done in proposed timeframe?

For each dimension:
- Score 0-10
- Provide rationale
- Cite evidence from interviews
- Identify risks

Also:
- Calculate overall feasibility score
- Provide recommendation (GO / CONDITIONAL GO / NO-GO)
- Specify confidence level

Create: working/feasibility-report-v1.md
```

**Expected Output**: Comprehensive feasibility assessment.

**What You Do**: Save to: `working/feasibility-report-v1.md`

**Checkpoint**: ✅ Feasibility assessed

---

### STEP 3.6: Identify and Assess Risks (20 min)

**Action**: Step 5 of workflow - Risk Assessment.

**PROMPT TO USE**:

```
We are at STEP 5: RISK ASSESSMENT.

Based on our problem statement and feasibility analysis, please:

1. Identify all risks mentioned in interviews
2. Identify additional risks based on feasibility analysis
3. For each risk, assess:
   - Likelihood (High/Medium/Low)
   - Impact (High/Medium/Low)
   - Severity score (Likelihood × Impact, scale 1-25)
4. Categorize risks (Technical, Business, Operational, etc.)
5. Propose mitigation strategies
6. Identify any "showstopper" risks (severity ≥20)

Use the risk register template.

Create: working/risk-register-v1.md
```

**Expected Output**: Comprehensive risk register.

**What You Do**: Save to: `working/risk-register-v1.md`

**Checkpoint**: ✅ Risks identified and assessed

---

### SESSION 3 COMPLETE - Update State (5 min)

**PROMPT TO USE**:

```
Session 3 complete.

Create SESSION 3 SUMMARY:
1. Completed Step 3: Problem Synthesis (problem statement finalized)
2. Completed Step 4: Feasibility Analysis (score: X/100)
3. Completed Step 5: Risk Assessment (Y risks identified, Z critical)
4. Next session: Step 6 (Success Criteria) and Step 7 (Validation)
5. Updated methodology adherence score

Update phase0-context.md to reflect progress.

Save summary as: working/session-3-summary.md
```

**Checkpoint**: ✅ Session 3 complete

**END OF SESSION 3**

---

## SESSION 4: Success Criteria & Validation (45-60 minutes)

### STEP 4.1: Resume and Load Context (5 min)

**Action**: Start new AI session, load methodology + current state (same bridge prompt pattern).

**Checkpoint**: ✅ Session 4 resumed

---

### STEP 4.2: Define Success Criteria (15 min)

**Action**: Step 6 of workflow - Success Criteria Definition.

**PROMPT TO USE**:

```
We are at STEP 6: SUCCESS CRITERIA DEFINITION.

Based on our final problem statement and stakeholder interviews,
please define measurable success criteria.

Requirements:
1. Criteria must be SMART (Specific, Measurable, Achievable, Relevant, Time-bound)
2. Include both quantitative and qualitative metrics
3. Align with the "Success Vision" from stakeholder interviews
4. Must be achievable given our feasibility assessment
5. Should address all dimensions (technical, business, user experience, operational)

Categories to cover:
- Business metrics (revenue, cost savings, customer satisfaction)
- Technical metrics (performance, reliability, scalability)
- User metrics (adoption rate, engagement, satisfaction)
- Operational metrics (support tickets, uptime, efficiency)

Create: working/success-criteria-v1.md
```

**Expected Output**: Comprehensive, measurable success criteria.

**What You Do**: Save to: `working/success-criteria-v1.md`

**Checkpoint**: ✅ Success criteria defined

---

### STEP 4.3: Validate Phase 0 Completion (20 min)

**Action**: Step 7 of workflow - Completion Validation.

**PROMPT TO USE**:

```
We are at STEP 7: VALIDATION.

Now we need to validate that Phase 0 is complete and ready for handoff
to Phase 1.

Please load the Phase 0 completion checklist:
[PASTE: test/.sdlc/primitives/checklists/phase-0-completion_checklist.md]

Then, review ALL our artifacts:
1. session.meta.md
2. phase0-context.md
3. All [N] interview transcripts
4. problem-statement.final.md
5. feasibility-report-v1.md
6. risk-register-v1.md
7. success-criteria-v1.md

For EACH item on the completion checklist, indicate:
✅ PASS - Fully satisfied
⚠️ PARTIAL - Partially satisfied (explain gap)
❌ FAIL - Not satisfied (explain why)

Generate: validation/phase0-completion-validation.md
```

**Expected Output**: Detailed validation report showing pass/fail for each checklist item.

**What You Do**: Save to: `validation/phase0-completion-validation.md`

**Checkpoint**: ✅ Completion validated

---

### STEP 4.4: Calculate Methodology Adherence Score (10 min)

**Action**: Assess how well we followed the methodology.

**PROMPT TO USE**:

```
Calculate our Methodology Adherence Score.

Score the following categories (each worth 3 points, total 12 points):

1. AGENT INSTRUCTIONS (0-3 points)
   - Did we load discovery-facilitator instructions? (1 pt)
   - Did we load feasibility-analyzer instructions? (1 pt)
   - Did we follow agent guidance? (1 pt)

2. WORKFLOWS (0-3 points)
   - Did we follow discovery-workflow steps 1-7? (1.5 pts)
   - Did we use interview-workflow for interviews? (1.5 pts)

3. TEMPLATES (0-3 points)
   - Did we use interview transcript template? (1 pt)
   - Did we use problem statement template? (1 pt)
   - Did we use feasibility/risk templates? (1 pt)

4. VALIDATION (0-3 points)
   - Did we run completion checklist? (1 pt)
   - Did we create validation report? (1 pt)
   - Did we track state in phase0-context.md? (1 pt)

Provide:
- Score for each category
- Total score out of 12
- Percentage
- Grade (A=11-12, B=9-10, C=7-8, D=5-6, F=0-4)
- Gaps identified

Generate: validation/methodology-adherence-report.md
```

**Expected Output**: Detailed adherence scorecard.

**What You Do**: Save to: `validation/methodology-adherence-report.md`

**Checkpoint**: ✅ Methodology adherence scored

---

### STEP 4.5: Package for Phase 1 Handoff (10 min)

**Action**: Prepare all artifacts for transition to Phase 1.

**PROMPT TO USE**:

```
Create a Phase 1 Handoff Package document that includes:

1. EXECUTIVE SUMMARY
   - Problem statement (1 paragraph)
   - Feasibility score and recommendation
   - Top 3 risks
   - Success criteria summary

2. ARTIFACTS INVENTORY
   - List of all files in phase0/artifacts/
   - List of all files in phase0/validation/
   - Brief description of each

3. KEY FINDINGS
   - Major themes from discovery
   - Critical contradictions resolved
   - Constraints to consider in Phase 1

4. RECOMMENDATIONS FOR PHASE 1
   - Suggested next steps
   - Stakeholders to involve
   - Areas requiring deeper specification

Generate: validation/phase1-handoff-package.md
```

**Expected Output**: Comprehensive handoff document.

**What You Do**: Save to: `validation/phase1-handoff-package.md`

**Checkpoint**: ✅ Handoff package created

---

### STEP 4.6: Move Final Artifacts (5 min)

**Action**: Move validated artifacts from working/ to artifacts/

**What You Do Manually**:

```bash
# Move finalized artifacts
cp working/problem-statement-v2.md artifacts/problem-statement.final.md
cp working/feasibility-report-v1.md artifacts/feasibility-report.md
cp working/risk-register-v1.md artifacts/risk-register.md
cp working/success-criteria-v1.md artifacts/success-criteria.md
```

**Checkpoint**: ✅ Artifacts organized

---

### STEP 4.7: Final Context Update (5 min)

**PROMPT TO USE**:

```
Update phase0-context.md one final time:

- Status: COMPLETE
- All 7 workflow steps: COMPLETE
- All interviews: COMPLETE
- All artifacts: FINALIZED and in artifacts/
- Validation: PASSED (or list any gaps)
- Methodology adherence: [X]/12 ([Y]%)
- Ready for Phase 1: YES/NO (with justification)

Provide the final phase0-context.md content.
```

**What You Do**: Update phase0-context.md with final status.

**Checkpoint**: ✅ Context finalized

---

### SESSION 4 COMPLETE - Test Complete! (5 min)

**PROMPT TO USE**:

```
Phase 0 Test Complete!

Create FINAL TEST SUMMARY including:

1. TEST EXECUTION SUMMARY
   - Total sessions: 4
   - Total time: ~X hours
   - Interviews conducted: [N]
   - Artifacts created: [list]

2. METHODOLOGY VALIDATION
   - Did we follow all 7 workflow steps? YES/NO
   - Methodology adherence score: [X]/12 ([Y]%)
   - Quality of artifacts: [assessment]

3. WHAT WORKED WELL
   - [List 3-5 things]

4. WHAT DIDN'T WORK WELL / GAPS FOUND
   - [List 3-5 issues]

5. RECOMMENDED IMPROVEMENTS TO FRAMEWORK
   - [List specific suggestions]

6. TEST OUTCOME
   - Framework validation: PASS/FAIL
   - Ready for production use: YES/NO
   - Next steps: [recommendations]

Save as: validation/FINAL-TEST-SUMMARY.md
```

**Expected Output**: Comprehensive test summary with findings.

**What You Do**: Save and review.

**Checkpoint**: ✅ **PHASE 0 TEST COMPLETE!**

**END OF SESSION 4**

---

## Post-Test Activities

### Review All Artifacts

**Files You Should Have**:

```
test/projects/002-[project-name]/
└── phase0/
    ├── session.meta.md
    ├── phase0-context.md
    ├── interviews/
    │   ├── 001-[role]-interview.md
    │   ├── 002-[role]-interview.md
    │   └── ... (7-9 total interviews)
    ├── working/
    │   ├── session-1-summary.md
    │   ├── session-2-summary.md
    │   ├── session-3-summary.md
    │   ├── problem-statement-v1.md
    │   ├── problem-statement-v2.md
    │   ├── feasibility-report-v1.md
    │   ├── risk-register-v1.md
    │   └── success-criteria-v1.md
    ├── artifacts/
    │   ├── problem-statement.final.md
    │   ├── feasibility-report.md
    │   ├── risk-register.md
    │   └── success-criteria.md
    └── validation/
        ├── phase0-completion-validation.md
        ├── methodology-adherence-report.md
        ├── phase1-handoff-package.md
        └── FINAL-TEST-SUMMARY.md
```

### Analyze Findings

**Questions to Answer**:

1. **Was the methodology usable?**
   - Were instructions clear?
   - Were workflows easy to follow?
   - Were templates helpful?

2. **What gaps did we find?**
   - Missing steps in workflows?
   - Unclear instructions?
   - Template sections that were confusing?
   - Validation criteria too vague?

3. **What improvements are needed?**
   - Specific changes to prompts?
   - New templates needed?
   - Better examples?
   - Clarifications?

### Update Framework

Based on test findings, update:
- Agent instructions (if unclear)
- Workflows (if missing steps)
- Templates (if incomplete)
- Checklists (if gaps found)
- Config (if thresholds wrong)

---

## Troubleshooting

### Issue: "I lost context and don't know where I am"

**Solution**: Look at phase0-context.md - it should tell you:
- Current step in workflow
- Interviews completed
- Artifacts created
- Next action

### Issue: "Claude isn't following the methodology"

**Solution**: Check you loaded:
- Agent instructions ✅
- Workflows ✅
- Config ✅
- Templates ✅

If anything missing, reload and explicitly say: "Please follow [X] workflow step-by-step."

### Issue: "Interview feels unnatural/forced"

**Solution**: That's okay! This is a test. The goal is to:
- Validate the interview workflow works
- Test Five Whys application
- Ensure documentation is complete

Naturalness is secondary to methodology validation.

### Issue: "Running out of tokens in Claude"

**Solution**: 
1. Complete current step
2. Save all artifacts
3. Create session summary
4. Start new session with bridge prompt
5. Load only essential context (phase0-context.md + recent summaries)

### Issue: "Not sure if artifact is 'good enough'"

**Solution**: Use the completion checklist! It has objective criteria for each artifact type. If checklist says ✅, it's good enough.

---

## Success Metrics for This Test

You'll know the test was successful if:

✅ You followed all 7 workflow steps in order  
✅ Methodology adherence score ≥ 10/12 (83%)  
✅ All required artifacts created using templates  
✅ Completion checklist shows mostly ✅ (>80%)  
✅ You identified 3+ specific improvements to framework  
✅ The process felt systematic (not ad-hoc)  
✅ Artifacts are professional quality  
✅ You could hand this to someone else and they'd understand the project  

---

## Final Checklist

Before declaring test complete, verify:

- [ ] All 7 workflow steps executed
- [ ] 7-9 stakeholder interviews conducted and documented
- [ ] Problem statement finalized using template
- [ ] Feasibility assessed (score calculated)
- [ ] Risks identified and assessed
- [ ] Success criteria defined (SMART)
- [ ] Completion checklist run
- [ ] Methodology adherence calculated
- [ ] Phase 1 handoff package created
- [ ] All artifacts in proper folders
- [ ] phase0-context.md shows COMPLETE status
- [ ] Final test summary written with recommendations

---

**END OF TEST EXECUTION GUIDE**

This guide should enable anyone to conduct a rigorous Phase 0 test that fully exercises the methodology. Follow it exactly and you'll have comprehensive validation of the framework.
