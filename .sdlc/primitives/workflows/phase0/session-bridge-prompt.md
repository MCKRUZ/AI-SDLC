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

Copy the prompt below and fill in the bracketed sections with actual file contents from your project.

```markdown
I am resuming a Phase 0 discovery session that was previously in progress.
I need you to act as the Discovery Facilitator agent and continue where we left off.

---

## CONTEXT TO LOAD

### Current Session State

I need you to review the current state of this Phase 0 discovery:

[PASTE CONTENTS OF: discovery-sessions/session-XXX-project-name/phase0-context.md]

---

## METHODOLOGY COMPONENTS

Please load and internalize the following methodology components:

### 1. Agent Instructions - Discovery Facilitator

[PASTE CONTENTS OF: test/.sdlc/primitives/agents/phase0/discovery-facilitator_instructions.md]

---

### 2. Phase 0 Configuration

[PASTE CONTENTS OF: test/.sdlc/config/phase0_config.md]

---

### 3. Discovery Workflow

[PASTE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/discovery-workflow.prompt.md]

---

### 4. Interview Workflow

[PASTE CONTENTS OF: test/.sdlc/primitives/workflows/phase0/interview-workflow.prompt.md]

---

## WORKING ARTIFACTS

These are the current versions of our working artifacts:

### Problem Statement (Current Version)

[PASTE CONTENTS OF: discovery-sessions/session-XXX-project-name/working/problem-statement-v[N].md]

---

### Feasibility Assessment (Current Version)

[PASTE CONTENTS OF: discovery-sessions/session-XXX-project-name/working/feasibility-assessment-v[N].md]

---

### Risk Register (Current Version)

[PASTE CONTENTS OF: discovery-sessions/session-XXX-project-name/working/risk-register-v[N].md]

---

## INTERVIEW TRANSCRIPTS COMPLETED

Here are the interviews we've completed so far:

[PASTE EACH COMPLETED INTERVIEW TRANSCRIPT OR PROVIDE SUMMARY]

---

## WHAT HAPPENS NEXT

Based on the phase0-context.md file above, you can see:
- Current Step: [Step N - Name]
- Progress: [X]% complete
- Next Milestone: [Description]

Please:
1. Confirm you understand where we are in the process
2. Summarize the current state in 2-3 sentences
3. Identify the next action we should take
4. Proceed with that action when I confirm

---

Ready to continue the Phase 0 discovery?
```

---

## Usage Instructions

### How to Use This Bridge

**Step 1: Locate Your Session Files**
- Find your session directory: `discovery-sessions/session-XXX-project-name/`
- Locate the phase0-context.md file
- Locate current working artifacts
- Locate interview transcripts

**Step 2: Copy the Template**
- Copy the entire bridge prompt template above
- Paste into a new AI conversation

**Step 3: Fill in the Placeholders**
- Replace `[PASTE CONTENTS OF: ...]` with actual file contents
- Use actual session ID and project name
- Include FULL file contents, not summaries

**Step 4: Start New Conversation**
- Paste the completed bridge prompt
- AI will acknowledge context
- Continue work seamlessly

---

## What Gets Loaded

### Essential Context (Always Load)
1. **phase0-context.md** - Current state, progress, next actions
2. **discovery-facilitator_instructions.md** - Agent role and responsibilities
3. **phase0_config.md** - How Phase 0 operates
4. **discovery-workflow.prompt.md** - 7-step workflow
5. **interview-workflow.prompt.md** - Interview protocol

### Working Artifacts (Always Load)
1. **problem-statement** (current version)
2. **feasibility-assessment** (current version)
3. **risk-register** (current version)

### Interview Transcripts (Conditional)
- **If <5 interviews**: Load all transcripts
- **If 5-10 interviews**: Load summaries + last 2 transcripts
- **If >10 interviews**: Load phase0-context.md which has synthesis

### Optional (Load if Needed)
- **contradiction-log** - If many contradictions exist
- **stakeholder-map** - If political dynamics are complex
- **delta-updates** - If you need to understand how things evolved
- **success-criteria** - If working on validation

---

## Example Bridge Prompt (Excerpt)

```markdown
I am resuming a Phase 0 discovery session that was previously in progress.
I need you to act as the Discovery Facilitator agent and continue where we left off.

---

## CONTEXT TO LOAD

### Current Session State

# Phase 0 Discovery Context - Contoso Azure Modernization

**Last Updated**: 2024-10-15 14:30  
**Updated By**: Discovery Team  
**Session ID**: session-001-contoso-azure  
**Project**: Azure Cloud Modernization for Manufacturing Operations

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

[... rest of context file ...]

---

## METHODOLOGY COMPONENTS

### 1. Agent Instructions - Discovery Facilitator

# Discovery Facilitator Agent Instructions

You are the Discovery Facilitator, a specialized agent for Phase 0 discovery...

[... full agent instructions ...]

---

[... continue with all other sections ...]

---

## WHAT HAPPENS NEXT

Based on the phase0-context.md file above, you can see:
- Current Step: Step 2 - Problem Exploration
- Progress: 55% complete
- Next Milestone: Complete floor supervisor interviews

We've completed 6 of 11 planned interviews. Last interview was with Maria Rodriguez
(Floor Supervisor) which revealed critical training gaps and shift dynamics issues.

Next up is Interview 7: Tom Brennan (Support Lead).

Please:
1. Confirm you understand where we are in the process
2. Summarize the current state in 2-3 sentences
3. Identify the next action we should take
4. Proceed with that action when I confirm

Ready to continue the Phase 0 discovery?
```

---

## Best Practices

### DO:
✅ Load FULL file contents (not summaries)  
✅ Include phase0-context.md first (sets the stage)  
✅ Load methodology components (ensures consistency)  
✅ Load current working artifacts (not old versions)  
✅ Summarize "what happens next" clearly

### DON'T:
❌ Paste partial files or summaries (context will be incomplete)  
❌ Skip methodology components (agent behavior will drift)  
❌ Load old artifact versions (will create confusion)  
❌ Forget to specify next action (ambiguity causes waste)  
❌ Load everything (token limits - be strategic)

---

## Token Budget Management

If you're approaching token limits:

**Priority 1 (Must Load)**:
- phase0-context.md
- discovery-facilitator_instructions.md
- Current working artifacts (latest versions)

**Priority 2 (Should Load)**:
- phase0_config.md
- discovery-workflow.prompt.md
- interview-workflow.prompt.md

**Priority 3 (Load if Space)**:
- Recent interview transcripts (last 2-3)
- Delta updates (last 2-3)
- Contradiction log

**Can Skip**:
- Old interview transcripts (info is in phase0-context.md)
- Old artifact versions (current version is enough)
- Templates (agent already knows these)

---

## Troubleshooting

**Problem**: AI doesn't seem to have context despite loading files  
**Solution**: Make sure you loaded phase0-context.md FIRST - it orients everything else

**Problem**: AI behavior differs from original session  
**Solution**: Ensure discovery-facilitator_instructions.md is loaded completely

**Problem**: AI doesn't know next steps  
**Solution**: Check that phase0-context.md has "Next Actions" section filled out

**Problem**: Too much content to paste  
**Solution**: Use priority loading strategy above; summarize less critical items

**Problem**: AI asks questions already answered in artifacts  
**Solution**: Confirm all working artifacts are current versions and fully loaded

---

## Success Criteria

You'll know the bridge worked when:
- ✅ AI acknowledges where you are in Phase 0 (step, progress)
- ✅ AI knows what interviews are complete
- ✅ AI knows current feasibility score and risk count
- ✅ AI can identify next action without asking
- ✅ AI maintains consistent methodology adherence
- ✅ AI references specific prior interviews when relevant

---

## File Metadata

**Prompt Version**: 1.0  
**Intended For**: Resuming interrupted Phase 0 discovery sessions  
**Token Budget**: High (plan for 30-50k tokens depending on session size)  
**Maintenance**: Update if methodology changes  
**Related**: 
- `phase0-context-tracker_template.md` (the file this prompt loads)
- `discovery-facilitator_instructions.md` (agent role this activates)
- `discovery-workflow.prompt.md` (workflow this follows)
