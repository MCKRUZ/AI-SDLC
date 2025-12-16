# Discovery Facilitator Chatmode

## Purpose
Focused stakeholder interview and problem discovery sessions using the Discovery Facilitator Agent.

## When to Use This Mode
- Conducting stakeholder interviews
- Exploring problem space with users, executives, or technical staff
- Using Five Whys for root cause analysis
- Applying Jobs-to-be-Done framework
- Synthesizing findings across multiple interviews
- Creating or refining problem statements

## Session Setup

### Before Starting
Load these artifacts into context:
1. Discovery Facilitator instructions (`discovery-facilitator_instructions.md`)
2. Organization context (`../../memory/organization_context.md`)
3. Technical stack context (`../../memory/technical-stack_context.md`)
4. Interview transcript template (`../templates/phase0/interview-transcript_template.md`)
5. Problem statement template (`../templates/phase0/problem-statement_template.md`)
6. Phase 0 config (`../../config/phase0_config.md`)

If resuming an existing discovery:
- Load `phase0-context.md` from project folder
- Load any existing interview transcripts
- Load working problem statement drafts

### Agent Instructions
Load: `discovery-facilitator_instructions.md`

### Session Goal
Define a clear goal for the session:
- "Interview [stakeholder role] about [problem area]"
- "Synthesize findings from completed interviews"
- "Apply Five Whys to [symptom/issue]"
- "Create initial problem statement draft"
- "Validate problem statement with [stakeholder]"

---

## Interaction Patterns

### Pattern 1: Stakeholder Interview Session

**When to Use**: Conducting a new stakeholder interview

**Opening Prompt**:
```
I need to conduct a discovery interview with [stakeholder role: CEO/CTO/User/Support Lead/etc.] 
for [project or problem area].

Please use the Discovery Facilitator Agent instructions to conduct this interview using:
- Five Whys for root cause analysis
- Jobs-to-be-Done framework for understanding motivations
- Open-ended questions to surface hidden constraints

Stakeholder context:
- Name: [Name]
- Role: [Role]
- Perspective: [What unique viewpoint they bring]
- Key areas to explore: [Specific topics]

I'll provide their responses. Document everything in the interview transcript format.
```

**During Interview**:
- Let the agent ask probing questions
- Provide stakeholder responses (you can roleplay or relay actual answers)
- Agent will follow up on interesting threads
- Agent will document key quotes and insights

**Closing Prompt**:
```
Let's wrap up this interview. Please:
1. Summarize the key insights discovered
2. Identify any contradictions with previous interviews (if applicable)
3. List follow-up questions for other stakeholders
4. Rate the interview quality (information density, new insights)
5. Format the complete transcript using the template
```

---

### Pattern 2: Five Whys Deep Dive

**When to Use**: A stakeholder mentions a symptom or problem that needs root cause analysis

**Opening Prompt**:
```
I need to apply the Five Whys framework to understand the root cause of:

"[Symptom or stated problem]"

This was mentioned by [stakeholder] in the context of [situation].

Please guide me through the Five Whys analysis:
1. Ask "Why?" for each level
2. I'll provide the answer based on stakeholder input
3. Continue until we reach a root cause (or identify where we need more information)
4. Document the chain of causation
```

**Example Flow**:
```
Agent: Why is [symptom] happening?
You: [Provide answer from stakeholder knowledge]
Agent: Why is [that cause] happening?
You: [Provide next level answer]
... continue until root cause or unknown ...
```

**Closing Prompt**:
```
Based on our Five Whys analysis, please:
1. Summarize the root cause(s) identified
2. Note any points where we hit "unknown" (needs more research)
3. Suggest which stakeholder might have answers for unknowns
4. Rate confidence in the root cause (High/Medium/Low)
```

---

### Pattern 3: Jobs-to-be-Done Analysis

**When to Use**: Understanding user motivations and desired outcomes

**Opening Prompt**:
```
I need to understand the Jobs-to-be-Done for [user role/persona] 
in the context of [problem area].

Please guide me through JTBD analysis:
1. Identify the functional job (what they're trying to accomplish)
2. Identify emotional jobs (how they want to feel)
3. Identify social jobs (how they want to be perceived)
4. Understand the current solution and its shortcomings
5. Identify hiring/firing criteria for solutions

Context from interviews so far:
[Paste relevant interview excerpts or summaries]
```

**During Analysis**:
- Agent will ask clarifying questions about user context
- Provide information from interviews or your knowledge
- Agent will build the JTBD canvas

**Closing Prompt**:
```
Please create a JTBD summary including:
1. Main job statement: "When [situation], I want to [motivation], so I can [outcome]"
2. Related jobs (functional, emotional, social)
3. Current solutions and why they're being "fired"
4. Success criteria for a new solution
5. Opportunities identified
```

---

### Pattern 4: Interview Synthesis Session

**When to Use**: After completing multiple interviews, synthesizing findings

**Opening Prompt**:
```
I have completed [N] stakeholder interviews and need to synthesize the findings.

Interviews completed:
1. [Role] - [Name] - [Key focus area]
2. [Role] - [Name] - [Key focus area]
3. [Role] - [Name] - [Key focus area]

[Paste interview summaries or key excerpts]

Please synthesize these interviews:
1. Identify common themes across stakeholders
2. Surface contradictions or conflicting perspectives
3. Map stakeholder alignment on key issues
4. Identify gaps (what we still don't know)
5. Draft initial problem statement elements
```

**Follow-up Prompts**:
```
For the contradiction between [Stakeholder A] and [Stakeholder B] 
regarding [topic], please:
1. Articulate both perspectives clearly
2. Identify the underlying assumptions
3. Suggest how to resolve or document this contradiction
4. Recommend who to ask for clarification
```

---

### Pattern 5: Problem Statement Drafting

**When to Use**: Creating or refining the problem statement artifact

**Opening Prompt**:
```
Based on our discovery work, I need to draft a problem statement.

Inputs:
- Interview synthesis: [Summary or paste]
- Key stakeholders: [List]
- Organizational context: [Relevant details]

Please create a problem statement draft following the template structure:
1. Problem Summary (2-3 sentences)
2. Current State (what exists today)
3. Pain Points (specific, evidence-based)
4. Impact (quantified where possible)
5. Desired Future State
6. Success Criteria
7. Scope Boundaries (in/out)
8. Key Stakeholders
9. Constraints Discovered
```

**Refinement Prompt**:
```
This problem statement needs refinement. Specifically:
- [Area 1] is too vague - make it more specific
- [Area 2] lacks evidence - add stakeholder quotes
- [Area 3] scope is unclear - clarify boundaries

Please revise and explain your changes.
```

---

### Pattern 6: Problem Statement Validation

**When to Use**: Validating problem statement with stakeholders

**Opening Prompt**:
```
I need to validate our problem statement with [stakeholder role].

Current problem statement:
[Paste problem statement]

Please help me:
1. Create validation questions to confirm accuracy
2. Identify areas most likely to get pushback
3. Prepare alternative framings for contentious points
4. Define what "validated" means (what responses indicate success)
```

**Post-Validation Prompt**:
```
Here's the feedback from [stakeholder] on our problem statement:
[Paste feedback]

Please:
1. Categorize feedback (confirmation, correction, addition, concern)
2. Recommend specific changes to the problem statement
3. Identify any feedback that contradicts other stakeholders
4. Update the problem statement draft
```

---

## Best Practices for This Mode

### Do's
- ✅ Let stakeholders talk - use open-ended questions
- ✅ Capture direct quotes for key insights
- ✅ Follow interesting threads even if off-script
- ✅ Document contradictions explicitly (don't smooth them over)
- ✅ Track what you still don't know
- ✅ Validate understanding before moving on
- ✅ Use evidence from interviews in problem statement

### Don'ts
- ❌ Don't lead stakeholders to your preferred answer
- ❌ Don't skip the "why" behind symptoms
- ❌ Don't assume you understand - verify
- ❌ Don't ignore contradictions between stakeholders
- ❌ Don't write problem statement without evidence
- ❌ Don't rush to solutions during discovery

---

## Session Outputs

### Primary Artifacts
- **Interview Transcripts** (one per stakeholder):
  - Stakeholder information
  - Questions asked and responses
  - Key quotes captured
  - Insights and themes identified
  - Follow-up items

- **Problem Statement** (iteratively refined):
  - Evidence-based problem description
  - Stakeholder-validated content
  - Clear scope boundaries
  - Success criteria

### Work-in-Progress Outputs
- Five Whys analysis documents
- JTBD canvases
- Synthesis notes
- Contradiction logs
- Gap analysis (what we still need to learn)

---

## Quality Checks Before Ending Session

- [ ] All planned interview questions addressed
- [ ] Key quotes captured verbatim
- [ ] Insights documented with evidence
- [ ] Contradictions explicitly noted
- [ ] Follow-up items identified
- [ ] Transcript follows template format
- [ ] Session notes saved to project folder

---

## Example Session Flow

```
USER: I need to interview our CTO about the legacy system modernization problem.

AGENT: I'll help facilitate this discovery interview with your CTO. Before we begin, 
let me understand the context:

1. What's the CTO's name and how long have they been in the role?
2. What's their technical background?
3. What specific aspects of "legacy modernization" should we focus on?
4. Have other stakeholders mentioned the CTO's perspective already?

[User provides context]

AGENT: Great. I'll structure this interview to explore:
- Their understanding of the current system's limitations
- Technical debt they're most concerned about
- Past modernization attempts and why they succeeded/failed
- Resource and timeline constraints
- Their vision for the target state

Let's begin. First question for the CTO:

"Can you walk me through the biggest technical challenges you face 
with the current system on a day-to-day basis?"

[Interview continues...]
```

---

## Transitioning Out of This Mode

**When Discovery is Complete**:
- All required stakeholder groups interviewed
- Problem statement validated
- No major contradictions unresolved
- Ready for feasibility assessment

**Next Mode**: `feasibility-analyzer.chatmode.md`

**Handoff Prompt**:
```
Discovery interviews are complete. Please create a handoff summary for 
the Feasibility Analyzer including:
1. Final problem statement
2. Key constraints discovered
3. Stakeholder alignment status
4. Open questions that need research
5. Recommended feasibility dimensions to investigate
```

---

*Created for: Phase 0 - Discovery & Ideation*
*Works with: Discovery Facilitator Agent*
*Last Updated: 2025-12-15*
