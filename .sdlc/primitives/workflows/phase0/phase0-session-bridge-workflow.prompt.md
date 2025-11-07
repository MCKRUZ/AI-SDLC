# Session Bridge Prompt - Phase 0 Discovery

**Purpose**: Resume an interrupted Phase 0 discovery session with proper context restoration.

**Version**: 1.0  
**Last Updated**: 2025-11-07  
**Location**: `test/.sdlc/primitives/workflows/phase0/session-bridge.prompt.md`

---

## When to Use This Prompt

Use this bridge prompt when:
- Starting a new AI conversation to continue Phase 0 work
- Context was lost (token limits, conversation timeout, etc.)
- Handing off to another facilitator
- Resuming after a break (days/weeks later)

**DO NOT use if**: You're still in the original conversation with full context.

---

## The Bridge Prompt Template

Copy the prompt below and fill in the bracketed sections with actual file contents.

```markdown
I am resuming a Phase 0 discovery session that was previously in progress.
I need you to act as the Discovery Facilitator agent and continue where
we left off.

---

## METHODOLOGY COMPONENTS TO LOAD

Please load and internalize the following methodology components that
define your role and process:

### 1. AGENT INSTRUCTIONS - Discovery Facilitator

You are the Discovery Facilitator. Here are your complete instructions:

[PASTE ENTIRE CONTENTS OF: test/.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md]

---

### 2. PHASE 0 CONFIGURATION

Here is how Phase 0 operates in this organization:

[PASTE ENTIRE CONTENTS OF: test/.sdlc/config/phase0_config.md]

---

### 3. DISCOVERY WORKFLOW

Here is the 7-step workflow you are following:

[PASTE ENTIRE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md]

---

### 4. INTERVIEW WORKFLOW

Here is the detailed interview protocol:

[PASTE ENTIRE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/interview-workflow.prompt.md]

---

### 5. TEMPLATES (for reference)

You will use these templates when creating artifacts:

**Interview Transcript Template:**
[PASTE: test/.sdlc/primitives/templates/phase0/interview-transcript_template.md]

**Problem Statement Template:**
[PASTE: test/.sdlc/primitives/templates/phase0/problem-statement_template.md]

**Feasibility Report Template:**
[PASTE: test/.sdlc/primitives/templates/phase0/feasibility-report_template.md]

**Risk Register Template:**
[PASTE: test/.sdlc/primitives/templates/phase0/risk-register_template.md]

---

## CURRENT PROJECT STATE

Now that you have loaded the methodology, here is where we are in the
current project:

### PROJECT CONTEXT

[PASTE ENTIRE CONTENTS OF: test/projects/[project-name]/phase0/phase0-context.md]

---

### SESSION SUMMARY

Here is what was accomplished in the most recent session:

[PASTE ENTIRE CONTENTS OF: test/projects/[project-name]/phase0/working/session-[N]-summary.md]

---

### COMPLETED INTERVIEW SUMMARIES

We have completed [N] interviews so far. Here are the key points from each:

**Interview #1 - [Role]:**
[Paste executive summary section from interview 1 transcript]

**Interview #2 - [Role]:**
[Paste executive summary section from interview 2 transcript]

**Interview #3 - [Role]:**
[Paste executive summary section from interview 3 transcript]

[Continue for all completed interviews, OR if too long, paste just the most recent 3 interviews]

---

### ARTIFACTS CREATED SO FAR

Current artifact status:

**Problem Statement:**
- Latest version: [e.g., working/problem-statement-v2.md]
- Status: [In progress / Ready for review / Finalized]
- Key points: [Brief 2-3 sentence summary if exists]

**Feasibility Report:**
- Latest version: [e.g., working/feasibility-report-v1.md]
- Current score: [X/100 if calculated]
- Status: [Not started / In progress / Complete]

**Risk Register:**
- Latest version: [e.g., working/risk-register-v1.md]
- Risk count: [N risks identified]
- Critical risks: [Number with severity >20]

**Success Criteria:**
- Status: [Not started / In progress / Complete]

---

## RESUME INSTRUCTIONS

Now that you have full context, please:

1. **Confirm Your Understanding**
   - What workflow step are we currently on? (Step X of 7)
   - How many interviews have we completed? ([N] of [Target])
   - What is our current feasibility assessment? (if calculated)
   - What are the top 3 themes emerging from discovery?

2. **Identify Next Action**
   - What is the immediate next step according to the workflow?
   - Are there any blockers or open questions?
   - Do we need to complete any pending tasks before proceeding?

3. **Confirm Readiness**
   - Confirm you are ready to continue as Discovery Facilitator
   - Ask me if there are any updates or changes since the last session
   - Proceed with the next workflow step

---

Please confirm you have loaded all methodology components, understand
the current project state, and are ready to continue.
```

---

## How to Use This Bridge Prompt

### Step 1: Identify What to Load

Before using the bridge prompt, gather these files:

**Always Load**:
- Discovery facilitator instructions
- Phase 0 config
- Discovery workflow
- Interview workflow
- Templates (all 4)
- phase0-context.md
- Most recent session summary

**Conditionally Load** (if they exist and context allows):
- Interview transcript summaries (at least the 3 most recent)
- Latest version of problem statement
- Latest version of feasibility report
- Latest version of risk register

### Step 2: Fill in the Template

Copy the bridge prompt template above into a text editor. Replace every `[PASTE ...]` section with the actual file contents.

### Step 3: Start New AI Conversation

Open a completely fresh AI conversation (new chat session).

### Step 4: Paste the Complete Bridge Prompt

Paste the entire filled-in bridge prompt (with all file contents) into the new conversation.

### Step 5: Verify Context Restoration

After Claude responds, verify it understands:
- Its role (Discovery Facilitator)
- Current workflow step
- Interview progress
- Artifact status
- Next action

If anything seems unclear, correct it before proceeding.

### Step 6: Continue Work

Once context is restored, continue with the next workflow step.

---

## Optimization Strategies

### If Context is Too Large

If the full bridge prompt exceeds token limits, use this prioritization:

**Must Include** (critical):
1. Discovery facilitator instructions (your role)
2. Discovery workflow (what steps to follow)
3. phase0-context.md (current state)
4. Most recent session summary

**Include if Space Allows** (helpful):
5. Interview workflow (how to conduct interviews)
6. Phase 0 config (quality standards)
7. Templates (for reference)
8. Recent interview summaries (last 3)

**Can Omit if Needed** (nice to have):
9. All interview transcripts (use summaries instead)
10. Full artifact contents (use status summaries)

### Progressive Context Loading

If even the prioritized version is too large:

**First Pass** (minimal restoration):
```
Load only:
- Discovery facilitator instructions
- phase0-context.md
- Most recent session summary

Ask Claude: "What is our current state and next action?"
```

**Second Pass** (add detail as needed):
```
If Claude needs more context, progressively add:
- Discovery workflow
- Interview summaries
- Artifact summaries

Only load on-demand, not preemptively.
```

---

## Context Verification Checklist

After using the bridge prompt, verify Claude knows:

- [ ] Role: Acting as Discovery Facilitator
- [ ] Workflow Step: Currently at Step [X] of 7
- [ ] Interview Status: [N] of [Target] complete
- [ ] Key Themes: Can list 3-5 main themes from discovery
- [ ] Contradictions: Aware of stakeholder conflicts
- [ ] Artifacts: Knows what exists and current status
- [ ] Next Action: Can state what to do next
- [ ] Quality Standards: Knows completion criteria

**If any ❌, provide additional context before continuing.**

---

## Example: Abbreviated Bridge Prompt

Here's a shorter version when token limits are tight:

```markdown
Resume Phase 0 discovery as Discovery Facilitator.

ROLE & PROCESS:
[Paste discovery-facilitator_instructions.md - 1st priority]

CURRENT STATE:
[Paste phase0-context.md - 2nd priority]

Project: [Name]
Step: [X] of 7
Interviews: [N] complete
Next: [Action]

KEY THEMES SO FAR:
1. [Theme 1]
2. [Theme 2]
3. [Theme 3]

KEY CONTRADICTIONS:
1. [Contradiction 1]
2. [Contradiction 2]

ARTIFACTS STATUS:
- Problem statement: [Status]
- Feasibility: [Status]
- Risks: [Status]

Confirm you understand current state and identify next action.
```

**Use this abbreviated version when**:
- Context limits are tight
- You're in the middle of a workflow step (not between steps)
- Recent work is fresh (same day/week)

---

## Common Issues & Solutions

### Issue: "Claude doesn't remember previous interviews"

**Solution**: 
- Ensure you pasted interview summaries
- If summaries too long, paste just the "Key Insights" sections
- As alternative, list themes rather than full summaries

### Issue: "Claude asks questions already answered"

**Solution**:
- Check that phase0-context.md is up to date
- Verify session summary includes open questions
- Explicitly state: "Note: We already covered [X] in Interview [N]"

### Issue: "Claude suggests restarting from beginning"

**Solution**:
- This means context restoration failed
- Try abbreviated bridge prompt first
- Be explicit: "Do NOT restart. Continue from current state."
- Worst case: Manually guide Claude to next step

### Issue: "Not sure what to include in bridge prompt"

**Solution**:
- Start with minimal version (instructions + context + summary)
- Let Claude ask for what it needs
- Add progressively

---

## Bridge Prompt Quality Checklist

Before using your bridge prompt, verify:

- [ ] All `[PASTE...]` sections filled with actual content
- [ ] File contents are current (not outdated versions)
- [ ] phase0-context.md reflects latest status
- [ ] Session summary is from most recent session
- [ ] Interview count is accurate
- [ ] Artifact status is accurate
- [ ] Next action is clearly stated

---

## Maintenance

**Update this bridge prompt template if**:
- New methodology components are added
- Workflow steps change
- Template formats change
- Quality standards change
- Context loading strategy improves

**Version History**:
- v1.0 (2025-11-07): Initial version

---

**END OF SESSION BRIDGE PROMPT**

This prompt enables seamless resumption of Phase 0 discovery across conversation breaks, ensuring methodology continuity and preventing context loss.
