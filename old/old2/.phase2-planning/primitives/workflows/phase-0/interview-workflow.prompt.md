# Interview Workflow - Structured Stakeholder Interviews

**Purpose**: This workflow provides a detailed, repeatable process for conducting individual stakeholder interviews during Phase 0 discovery. It guides the Discovery Facilitator through preparation, execution, and documentation of interviews.

---

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│              Phase 0: Stakeholder Interview Process              │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Pre-Interview        │
                 │  - Identify stakeholder  │
                 │  - Research background   │
                 │  - Prepare questions     │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  2. Opening              │
                 │  - Set context           │
                 │  - Establish rapport     │
                 │  - Explain process       │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  3. Problem Exploration  │
                 │  - Open-ended questions  │
                 │  - Active listening      │
                 │  - Follow curiosity      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Root Cause Analysis  │
                 │  - Apply Five Whys       │
                 │  - Dig deeper            │
                 │  - Validate understanding│
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. Impact & Context     │
                 │  - Quantify impact       │
                 │  - Identify constraints  │
                 │  - Gather success metrics│
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  6. Closing              │
                 │  - Summarize key points  │
                 │  - Clarify ambiguities   │
                 │  - Next steps            │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  7. Post-Interview       │
                 │  - Document transcript   │
                 │  - Extract insights      │
                 │  - Update synthesis      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  8. Synthesis Update     │
                 │  - Add to patterns       │
                 │  - Flag contradictions   │
                 │  - Plan next interview   │
                 └──────────────────────────┘
```

---

## Step 1: Pre-Interview Preparation

### Objective
Prepare for an effective interview by understanding the stakeholder, their role, and what information we need.

### Agent: Discovery Facilitator (preparation mode)

### Time Required
15-30 minutes before interview

### Actions

#### 1.1 Stakeholder Identification & Research

**Gather Basic Information**:
```markdown
## Stakeholder Profile

**Name**: [Full name]
**Role**: [Job title]
**Department**: [Department/team]
**Tenure**: [How long at organization]
**Contact**: [Email/phone]

**Relationship to Problem**:
- [ ] Problem originator (identified the issue)
- [ ] Problem sufferer (directly impacted)
- [ ] Problem solver (would implement solution)
- [ ] Decision maker (approves/funds solution)
- [ ] Subject matter expert (deep domain knowledge)
- [ ] End user (uses current/proposed system)
- [ ] Other: [Specify]

**Prior Context**:
- Previous projects worked on: [List]
- Known perspectives/biases: [Notes]
- Technical proficiency: [High/Medium/Low]
```

#### 1.2 Review Prior Interviews

If this is not the first interview:

```markdown
## Pre-Interview Context Review

**Themes Identified So Far**:
1. [Theme 1] - Mentioned by [X stakeholders]
2. [Theme 2] - Mentioned by [Y stakeholders]

**Contradictions to Explore**:
1. [Stakeholder A] says [X] but [Stakeholder B] says [Y]
   → Ask this stakeholder about: [Specific question]

**Open Questions from Previous Interviews**:
1. [Question that needs answering]
   → Could this stakeholder answer it?

**Hypotheses to Test**:
1. [Hypothesis]: We think [X] because [reasons]
   → Questions to validate: [List]
```

#### 1.3 Prepare Interview Guide

**Create Stakeholder-Specific Question Set**:

```markdown
## Interview Guide - [Stakeholder Name]

**Time Allocated**: 45-60 minutes

**Opening Questions** (5-10 min):
1. Can you tell me about your role and how you interact with [problem domain]?
2. How long have you been dealing with [the problem area]?

**Problem Exploration** (15-20 min):
1. What challenges do you face with [problem domain]?
2. Can you walk me through a recent example of this problem?
3. How often does this happen? [Daily/Weekly/Monthly]
4. What workarounds have you developed?

**Root Cause Exploration** (15-20 min):
[Prepare Five Whys framework - see Step 4]

**Impact & Context** (10-15 min):
1. How does this problem affect your work/team/customers?
2. Can you quantify the impact? [Time lost, money lost, customers affected]
3. What constraints should we be aware of?
4. How would you define success?

**Closing** (5 min):
1. Is there anything I haven't asked that I should know?
2. Who else should I talk to about this?
```

#### 1.4 Set Up Recording/Documentation

**Before the Interview**:
- [ ] Confirm stakeholder availability
- [ ] Send calendar invite with clear purpose
- [ ] Prepare transcript template
- [ ] Set up note-taking system
- [ ] Test recording equipment (if applicable)
- [ ] Review confidentiality/permission protocols

**Create Interview Workspace**:
```bash
# Create dedicated interview file
mkdir -p discovery-sessions/[project]/interviews/
touch discovery-sessions/[project]/interviews/[NNN]-[role]-[name]-interview.md
```

---

## Step 2: Opening (First 5-10 minutes)

### Objective
Establish rapport, set context, and create a comfortable environment for honest discussion.

### Agent: Discovery Facilitator (interviewer mode)

### Actions

#### 2.1 Welcome & Introduction

**Opening Script** (customize as appropriate):

```markdown
Agent: Thank you for taking time to speak with me today. I really appreciate your 
insights. Before we dive in, let me give you some context on why we're talking.

We're in the discovery phase for [project/initiative name]. Our goal right now 
is to deeply understand the problem space - not to jump to solutions. I'm here 
to listen and learn from your experience.

A few things about this conversation:
- There are no wrong answers - I want your honest perspective
- We'll take about [45-60] minutes
- I'll be taking notes as we talk
- Everything you share will be documented for the project team
- If I ask something unclear, please tell me to rephrase

Does that sound good? Do you have any questions before we start?
```

#### 2.2 Set Expectations

**Clarify Interview Style**:
```markdown
Agent: I want to set expectations about my interview style. You'll notice I ask 
"why" quite a bit. I'm not questioning your judgment - I'm trying to understand 
root causes. If you feel like I'm being repetitive or annoying, that's intentional! 
I want to dig deep.

Also, I might paraphrase what you say back to you. That's me checking that I 
understand correctly. Please correct me if I get it wrong.

And one more thing: I may take brief pauses to gather my thoughts or take notes. 
Those silences are okay - they give you time to think too.

Ready to get started?
```

#### 2.3 Establish Baseline Context

**Warm-Up Questions**:
1. "Tell me about your role - what does a typical day look like for you?"
2. "How long have you been in this role?"
3. "How does [problem domain] fit into your responsibilities?"

**Purpose**: Build rapport, get stakeholder talking, establish their perspective

**CRITICAL**: Listen actively. Let them talk. Don't interrupt.

---

## Step 3: Problem Exploration (15-20 minutes)

### Objective
Understand the problem from the stakeholder's perspective using open-ended questions.

### Agent: Discovery Facilitator (explorer mode)

### Actions

#### 3.1 Open-Ended Problem Exploration

**Discovery Questions Framework**:

```markdown
## Core Discovery Questions

**The Opening**:
"I'd like to understand the challenges you face with [problem domain]. 
Can you tell me about that?"

**Follow-Up Probes**:
→ "Can you give me a specific example?"
→ "Walk me through what happened..."
→ "What did you do next?"
→ "How did that make you feel?"
→ "What were you trying to accomplish?"

**Frequency & Severity**:
→ "How often does this happen?"
→ "Is this getting worse, better, or staying the same?"
→ "Was there a time when this wasn't a problem?"

**Current Workarounds**:
→ "What do you do now when this problem occurs?"
→ "Have you found any tricks or workarounds?"
→ "What would happen if you did nothing?"

**Stakeholder's Attempts**:
→ "Have you tried to fix this before?"
→ "What happened when you tried [X]?"
→ "Why didn't that work?"
```

#### 3.2 Active Listening Techniques

**While Stakeholder is Talking**:

✅ **DO**:
- Take notes on key phrases (use their exact words)
- Note emotional words (frustrated, excited, confused)
- Mark contradictions or ambiguities with [?]
- Let silences happen (don't rush to fill them)
- Nod, give verbal acknowledgment ("I see," "Interesting")
- Note what they DON'T say (missing perspectives)

❌ **DON'T**:
- Interrupt with solutions
- Defend current systems
- Get defensive
- Lead the witness ("Wouldn't you say that...")
- Jump to conclusions
- Talk about your own experiences

**Paraphrasing for Validation**:
```markdown
Agent: "Let me make sure I understand. You're saying that [paraphrase]. 
Is that right?"

Agent: "So the core issue is [summary]. Do I have that correct?"

Agent: "It sounds like the main impact is [impact]. Am I understanding that 
correctly?"
```

#### 3.3 Follow Your Curiosity

**When Something Sounds Important**:
```markdown
Agent: "That's interesting. Can you tell me more about [that specific thing]?"

Agent: "Hold on, I want to make sure I understand [X]. Can you explain that 
a bit more?"

Agent: "You mentioned [interesting point] - that sounds significant. 
What's the story there?"
```

**When Something Doesn't Make Sense**:
```markdown
Agent: "I'm confused about [X]. Can you help me understand?"

Agent: "I thought you said [A], but now you're saying [B]. Can you clarify?"

Agent: "What do you mean by '[ambiguous term]'? Can you give me an example?"
```

#### 3.4 Document As You Go

**Real-Time Note Taking**:
```markdown
## Interview Notes - [Stakeholder Name]

**Key Quotes** (verbatim):
- "[Exact quote that captures essence]"
- "[Quote showing emotion or priority]"

**Themes Emerging**:
- [Theme]: [Evidence from this conversation]

**Specific Examples Shared**:
- Example 1: [Brief description]
  - Context: [When, where, why]
  - Impact: [What happened]

**Contradictions/Ambiguities**:
- [?] Said [X] but also said [Y] - need to clarify

**Questions Generated**:
- Need to ask: [Question for this stakeholder]
- Need to explore with others: [Question for different perspective]
```

---

## Step 4: Root Cause Analysis (15-20 minutes)

### Objective
Go beyond symptoms to identify underlying root causes using structured frameworks.

### Agent: Discovery Facilitator (analyst mode)

### Actions

#### 4.1 Apply Five Whys Framework

**The Five Whys Technique**:

```markdown
## Five Whys Template

**Symptom/Problem Statement**:
[The problem as stakeholder describes it]

**Why #1**: Why does [problem] occur?
Answer: [Stakeholder response]

**Why #2**: Why does [previous answer] happen?
Answer: [Stakeholder response]

**Why #3**: Why is that the case?
Answer: [Stakeholder response]

**Why #4**: Why does [previous answer] happen?
Answer: [Stakeholder response]

**Why #5**: Why is that?
Answer: [Stakeholder response] ← ROOT CAUSE

**Validation**: Does this root cause ring true? If we fixed THIS, would the 
original problem go away?
```

**Example Conversation**:
```markdown
Stakeholder: "Our customer service response time is too slow."

Agent: "Why is the response time too slow?"
Stakeholder: "Because the team is overwhelmed with tickets."

Agent: "Why is the team overwhelmed?"
Stakeholder: "Because we get a lot of questions about how to use the product."

Agent: "Why do customers have so many questions?"
Stakeholder: "Because the product interface isn't intuitive."

Agent: "Why isn't the interface intuitive?"
Stakeholder: "Because it was designed for internal users, not external customers."

Agent: "Why was it designed for internal users?"
Stakeholder: "Because when we built it 5 years ago, we were only selling B2B 
and customers had training. Now we're B2C with no training program."

→ ROOT CAUSE: Product was designed for a different user base and hasn't evolved
```

#### 4.2 Alternative Root Cause Frameworks

**If Five Whys Isn't Working, Try**:

**Fishbone Diagram (Categories)**:
```markdown
What categories might be contributing to the problem?

- **People**: Skills, training, capacity, motivation?
- **Process**: Workflow, approval chains, handoffs?
- **Technology**: Tools, systems, integration?
- **Environment**: Physical space, organizational structure?
- **Materials/Data**: Information availability, quality?
```

**Jobs-to-be-Done** (for user-facing problems):
```markdown
When [situation], I want to [motivation], so I can [desired outcome].

Current Job: What is the user actually trying to accomplish?
Desired Outcome: What does success look like from their perspective?
Constraints: What's preventing them from achieving it?
Workarounds: What do they do instead?

Example:
"When I need to review our sales pipeline, I want to see accurate real-time 
data, so I can make informed decisions about resource allocation. But our 
CRM is out of date so I spend 2 hours manually pulling reports from 4 systems."

Root Cause: Lack of data integration creates manual work
```

#### 4.3 Validate Root Cause Understanding

**Test Your Understanding**:
```markdown
Agent: "Based on what you've shared, it seems like the root cause is [summary]. 
If we addressed [root cause], would that solve [original problem]?"

Agent: "Am I right in thinking that [root cause] is the core issue, not just 
a symptom of something else?"

Agent: "Are there other root causes contributing to this, or is this the 
main one?"
```

#### 4.4 Identify Multiple Root Causes

**CRITICAL**: Many problems have multiple root causes!

```markdown
## Root Cause Analysis Summary

**Primary Root Cause**:
[The main underlying issue]
- Evidence: [What the stakeholder said that led you here]
- Confidence: [High/Medium/Low]

**Secondary Root Causes**:
1. [Contributing factor]
   - Evidence: [Supporting quotes or examples]
2. [Contributing factor]
   - Evidence: [Supporting quotes or examples]

**Contributing Factors** (not root causes but relevant):
- [Factor that makes problem worse]
- [Factor that prevents fixes]
```

---

## Step 5: Impact & Context (10-15 minutes)

### Objective
Quantify the impact of the problem and gather contextual information about constraints and success criteria.

### Agent: Discovery Facilitator (context gatherer mode)

### Actions

#### 5.1 Quantify Business Impact

**Impact Quantification Framework**:

```markdown
## Business Impact Assessment

**Quantitative Impact**:

Time/Efficiency Impact:
- Q: "How much time does this problem cost you per [day/week/month]?"
- Q: "How many people are affected?"
- Q: "What's the time cost per incident?"
- Answer: [Specific numbers]

Financial Impact:
- Q: "Can you estimate the cost of this problem?"
  - Lost revenue: $[___] per [time period]
  - Wasted costs: $[___] per [time period]  
  - Lost opportunities: $[___] per [time period]
- Q: "What would solving this be worth financially?"
- Answer: [Specific numbers with reasoning]

Quality/Customer Impact:
- Q: "How does this affect customer satisfaction?"
- Q: "Have you lost customers because of this?"
- Q: "What's the NPS/CSAT impact?" (if they track it)
- Answer: [Specific metrics]

**Qualitative Impact**:

Team/Morale Impact:
- Q: "How does this problem affect team morale?"
- Q: "Have people left because of frustration with this?"
- Q: "What's the emotional toll?"
- Answer: [Description with examples]

Strategic Impact:
- Q: "How does this problem affect broader business goals?"
- Q: "What strategic initiatives are blocked by this?"
- Q: "What opportunities are you missing?"
- Answer: [Strategic implications]
```

**IMPORTANT**: Push for specific numbers, not vague descriptions!

❌ "It wastes a lot of time" → ✅ "Each incident takes 2 hours, happens 3x per week = 6 hours/week = 312 hours/year"

❌ "Customers are unhappy" → ✅ "NPS dropped from 45 to 32 after this issue started"

#### 5.2 Identify Constraints

**Constraint Discovery Questions**:

```markdown
## Constraints Assessment

**Technology Constraints**:
- Q: "What technology constraints do we need to work within?"
- Q: "Are there systems we must integrate with?"
- Q: "What technology can't we change or replace?"
- Answers: [List specific constraints with reasons]

**Organizational Constraints**:
- Q: "What organizational constraints should we know about?"
- Q: "Who needs to approve any changes?"
- Q: "What's the approval process like?"
- Answers: [List constraints]

**Budget/Resource Constraints**:
- Q: "What's the budget situation?"
- Q: "How much investment would be justified?"
- Q: "Are there resource constraints (people, time, skills)?"
- Answers: [List constraints]

**Regulatory/Compliance Constraints**:
- Q: "Are there compliance or regulatory requirements?"
- Q: "What standards must we adhere to?"
- Q: "What are the consequences of non-compliance?"
- Answers: [List requirements]

**Timeline Constraints**:
- Q: "How urgent is this problem?"
- Q: "Are there deadlines we need to meet?"
- Q: "What's the cost of delay?"
- Answers: [Timeline information]
```

#### 5.3 Define Success Criteria

**Success Criteria Framework**:

```markdown
## Success Definition

Agent: "Let's say we solve this problem perfectly. What does success look like?"

**Stakeholder's Vision of Success**:
[Let them describe in their own words]

**Measurable Success Criteria**:

For each aspect of success, ask:
- Q: "How would we measure that?"
- Q: "What's the current baseline?"
- Q: "What's the target?"
- Q: "What's the timeline?"

| Success Metric | Current State | Target State | Timeline | How to Measure |
|----------------|---------------|--------------|----------|----------------|
| [Metric 1] | [Baseline] | [Goal] | [When] | [Method] |
| [Metric 2] | [Baseline] | [Goal] | [When] | [Method] |
| [Metric 3] | [Baseline] | [Goal] | [When] | [Method] |

**Minimum Acceptable Success**:
Q: "What's the minimum improvement that would make this worthwhile?"
Answer: [Minimum bar for success]
```

#### 5.4 Gather Contextual Information

**Additional Context to Capture**:

```markdown
## Additional Context

**Prior Attempts**:
- Q: "Have you tried to solve this before?"
- Q: "What happened? Why didn't it work?"
- Answers: [History of attempts]

**Related Initiatives**:
- Q: "Are there other projects or initiatives related to this?"
- Q: "How does this fit into broader strategy?"
- Answers: [Related context]

**Stakeholder Preferences**:
- Q: "If you could wave a magic wand, what would the solution look like?"
- Q: "What solutions would you definitely NOT want?"
- Answers: [Preferences and anti-patterns]

**Political/Organizational Context**:
- Q: "Who are the champions for solving this?"
- Q: "Who might resist change?"
- Q: "What's the history here that we should know?"
- Answers: [Political landscape]
```

---

## Step 6: Closing (5 minutes)

### Objective
Summarize key takeaways, clarify any ambiguities, and establish next steps.

### Agent: Discovery Facilitator (synthesizer mode)

### Actions

#### 6.1 Summarize Key Points

**Closing Summary**:
```markdown
Agent: "Before we wrap up, let me summarize what I heard to make sure I got it right:

**The Problem**:
[1-2 sentence summary of the problem]

**Root Causes**:
[Key root causes identified]

**Impact**:
[Quantified impact summary]

**Key Constraints**:
[Main constraints to remember]

**Success Would Look Like**:
[Summary of success criteria]

Did I capture that correctly? Is there anything I missed or misunderstood?"
```

#### 6.2 Clarify Ambiguities

**Review Your [?] Marks**:
```markdown
Agent: "I have a few things I want to clarify:

1. Earlier you mentioned [ambiguous statement]. Can you elaborate on that?
2. I wasn't clear on [unclear point]. Can you explain that again?
3. You said both [A] and [B] - how do those fit together?
```

#### 6.3 Final Open-Ended Question

**The Magic Question**:
```markdown
Agent: "This is always my last question: Is there anything important that I 
haven't asked about? Anything you think I should know that we haven't discussed?"

[Often reveals crucial information]
```

#### 6.4 Identify Next Stakeholders

**Referral Questions**:
```markdown
Agent: "Who else should I talk to about this?"

Follow-ups:
- Q: "Who has a different perspective on this problem?"
- Q: "Who would be most affected by changes?"
- Q: "Who is the decision-maker for this area?"
- Q: "Is there a subject matter expert I should consult?"

Document referrals:
- [Name, Role, Why interview them, Contact info]
```

#### 6.5 Set Expectations for Next Steps

**Closing Statement**:
```markdown
Agent: "Thank you so much for your time and insights. Here's what happens next:

1. I'll document this conversation in an interview transcript
2. I'll combine your input with other stakeholder interviews
3. We'll synthesize everything into a problem statement
4. I'll come back to you to validate we got it right
5. Expected timeline: [X weeks]

Is it okay if I follow up with you if I have additional questions?

Do you have any questions for me?"
```

---

## Step 7: Post-Interview Documentation (Within 24 hours)

### Objective
Document the interview while details are fresh, extract key insights, and organize information.

### Agent: Discovery Facilitator (documenter mode)

### Actions

#### 7.1 Create Interview Transcript

**Use Template**: `interview-transcript.template.md`

**Interview Transcript Structure**:
```markdown
# Interview Transcript - [Stakeholder Name]

**Metadata**:
- Stakeholder: [Name], [Role]
- Date: [YYYY-MM-DD]
- Duration: [X minutes]
- Interviewer: [Name/Agent]
- Session: [NNN-project-name]

---

## Executive Summary

[2-3 paragraph summary of the conversation highlighting:
- Main problems discussed
- Key insights
- Root causes identified
- Important quotes
- Action items]

---

## Stakeholder Profile

**Role & Responsibilities**:
[What they do, how long they've been doing it]

**Relationship to Problem**:
[How they're affected or involved]

**Perspective**:
[Their unique viewpoint - technical, business, user, etc.]

---

## Interview Content

### Background & Context

Q: [Question asked]
A: [Stakeholder response - capture essence, use quotes for powerful statements]

**Insights**:
- [Key takeaway from this exchange]
- [Implicit information revealed]

### Problem Exploration

Q: [Question]
A: [Response]

**Example Shared**: [Specific story or example]

**Insights**:
- [What this reveals about the problem]

### Root Cause Analysis

[Document the Five Whys progression]

**Symptom**: [Surface problem]
→ **Why #1**: [First answer]
→ **Why #2**: [Second answer]
→ **Why #3**: [Third answer]
→ **Why #4**: [Fourth answer]
→ **Why #5**: [Fifth answer]

**Root Cause Identified**: [The underlying cause]

### Impact & Quantification

**Quantitative Impact**:
- Time: [Specific measurements]
- Cost: [Dollar figures]
- Volume: [How many affected, how often]

**Qualitative Impact**:
- [Morale, reputation, strategic impact]

### Constraints Identified

| Constraint Type | Description | Source | Impact |
|----------------|-------------|--------|--------|
| [Type] | [What it is] | [Why it exists] | [How it limits us] |

### Success Criteria

| Metric | Current | Target | Timeline | Measurement Method |
|--------|---------|--------|----------|-------------------|
| [Metric] | [Now] | [Goal] | [When] | [How] |

---

## Key Themes

### Themes Reinforced
[Themes that came up in this interview that others also mentioned]

### New Themes Identified
[New angles or perspectives that hadn't emerged before]

### Contradictions with Other Interviews
[Where this stakeholder's perspective differs from others]

---

## Quotes & Evidence

**Powerful Quotes** (use for problem statement):
> "[Exact quote that captures the essence of the problem]"
> -- [Stakeholder Name, Role]

> "[Quote showing impact or emotion]"
> -- [Stakeholder Name, Role]

**Data Points** (specific numbers or facts):
- [Stat 1]
- [Stat 2]
- [Stat 3]

---

## Insights & Analysis

### What We Learned
1. [Key insight #1]
2. [Key insight #2]
3. [Key insight #3]

### Assumptions to Validate
- [Assumption 1] - Need to verify with [different stakeholder/research]
- [Assumption 2] - Need to test with [method]

### Open Questions Generated
1. [Question that arose] - Should ask: [who]
2. [Question needing research]
3. [Ambiguity to resolve]

### Surprises or Unexpected Findings
- [Anything surprising or counter to expectations]

---

## Follow-Up Actions

### Immediate Actions
- [ ] [Action item from this interview]
- [ ] [Clarification needed]

### Future Interview Topics
- [ ] Explore [topic] with [different stakeholder type]
- [ ] Validate [assumption] with [stakeholder]

### Referrals
- [Name, Role, Why] - Contact: [Email]

---

## Interviewer Notes

[Any meta-observations about the interview itself:
- Was stakeholder open/guarded?
- Did they seem to have agenda?
- What wasn't said that's notable?
- Body language or tone indicators (if face-to-face)]

---

## Appendix

### Raw Notes
[Include rough notes taken during interview for reference]

### Supporting Documents
[Links to any documents stakeholder shared or referenced]
```

**Save**: `discovery-sessions/[project]/interviews/[NNN]-[role]-[name]-interview.md`

#### 7.2 Extract Structured Insights

**Create Insight Cards**:
```markdown
## Insight Extraction - [Stakeholder Name]

### Root Causes Identified
- **RC-001**: [Root cause description]
  - Source: [Stakeholder name]
  - Evidence: [Quote or example]
  - Confidence: [High/Medium/Low]

### Impact Data Points
- **IMP-001**: [Specific impact with numbers]
  - Source: [Stakeholder name]
  - Type: [Time/Cost/Quality/Strategic]

### Constraints
- **CON-001**: [Constraint description]
  - Type: [Technical/Budget/Regulatory/Timeline]
  - Hardness: [Hard/Soft]
  - Source: [Stakeholder name]

### Success Criteria
- **SUC-001**: [Success metric]
  - Current: [Baseline]
  - Target: [Goal]
  - Source: [Stakeholder name]
```

**Save**: `discovery-sessions/[project]/working/insights-[stakeholder-initials].md`

---

## Step 8: Synthesis Update (After documentation)

### Objective
Integrate this interview's findings into the broader discovery synthesis.

### Agent: Discovery Facilitator (synthesizer mode)

### Actions

#### 8.1 Update Pattern Tracking

**Theme Tracking Document**:
```markdown
## Theme Tracking - Updated [Date]

### Emerging Themes

**Theme 1: [Theme name]**
- Mentioned by: [Stakeholder A], [Stakeholder B], [New Stakeholder]
- Strength: [Strong - 3+ mentions / Moderate - 2 mentions / Weak - 1 mention]
- Evidence:
  - [Stakeholder A]: "[Quote or summary]"
  - [Stakeholder B]: "[Quote or summary]"
  - [New Stakeholder]: "[Quote or summary]"
- Pattern: [What's consistent across mentions]
- Variations: [How perspectives differ]

**Theme 2: [Theme name]**
[Same structure]

### New Themes (First mentioned in this interview)
- [New theme]: [Description] - Need to validate with other stakeholders

### Weakening Themes (Haven't heard recently)
- [Theme]: Only mentioned by early stakeholders, not recent ones - may be less important
```

**Save**: `discovery-sessions/[project]/working/theme-tracking.md`

#### 8.2 Flag Contradictions

**Contradiction Log**:
```markdown
## Contradictions - Updated [Date]

### Contradiction 1: [Topic]

**Stakeholder A** ([Name], [Role]) says:
"[Their perspective]"

**Stakeholder C** ([New Name], [New Role]) says:
"[Their different perspective]"

**Analysis**:
- Both valid from their viewpoint?
- Based on different information?
- Needs clarification/reconciliation?

**Resolution Strategy**:
- [ ] Ask Stakeholder B (neutral party) for perspective
- [ ] Bring both together to discuss
- [ ] Research to find objective truth
- [ ] Document as known disagreement

**Status**: [Open / In Progress / Resolved]
```

**Save**: `discovery-sessions/[project]/working/contradictions.md`

#### 8.3 Update Question List

**Open Questions Tracking**:
```markdown
## Open Questions - Updated [Date]

### Questions Answered by This Interview
- ✅ [Question] - Answered by [Stakeholder]: [Answer]

### New Questions Generated
- ❓ [Question] - Should ask: [specific role/person]
- ❓ [Question] - Need to research: [where/how]

### Still Open Questions
- ⏳ [Question from earlier interview] - Still need to answer
  - Potential sources: [Who might know]
  - Priority: [High/Medium/Low]
```

**Save**: `discovery-sessions/[project]/working/open-questions.md`

#### 8.4 Update Problem Statement Draft

**Incremental Problem Statement Updates**:
```markdown
## Problem Statement - Version [N] - Updated [Date]

### Changes in This Version

**NEW INFORMATION** (from [Stakeholder Name] interview):
+ [New element added with source]
+ [New metric or data point]

**REFINED UNDERSTANDING**:
~ Was: [Previous understanding]
~ Now: [Refined understanding based on new interview]

**VALIDATED ASSUMPTIONS**:
✓ [Assumption] confirmed by [Stakeholder Name]

**NEW QUESTIONS**:
? [Question that emerged]

### Current Problem Statement
[Working version of problem statement incorporating all interviews to date]
```

**Save**: `discovery-sessions/[project]/working/problem-statement-v[N].md`

#### 8.5 Plan Next Interview

**Next Interview Planning**:
```markdown
## Next Interview Planning

### Stakeholders Yet to Interview
1. [Name/Role] - Priority: [High/Medium/Low]
   - What we need to learn: [Information gaps they can fill]
   - Questions to prioritize: [Specific questions]

2. [Name/Role] - Priority: [High/Medium/Low]
   - What we need to learn: [Information gaps they can fill]

### Interview Completeness Assessment

**Coverage Check**:
- [ ] Executive perspective: [Done/Need more]
- [ ] Technical perspective: [Done/Need more]
- [ ] User perspective: [Done/Need more]
- [ ] Operations perspective: [Done/Need more]
- [ ] [Other perspective]: [Done/Need more]

**Saturation Check**:
- [ ] Are we hearing new themes or just repeating?
- [ ] Have we reached root causes or still on symptoms?
- [ ] Can we quantify impact with current data?
- [ ] Are major contradictions resolved?

**Decision**: 
- [ ] Continue interviewing - need [X] more interviews
- [ ] Ready to synthesize - have sufficient information
```

---

## Interview Quality Checklist

After each interview, validate quality:

### Did We Succeed?

**Depth**:
- [ ] Reached root causes (not just symptoms)
- [ ] Applied Five Whys or equivalent framework
- [ ] Explored multiple angles of the problem

**Breadth**:
- [ ] Covered problem definition
- [ ] Quantified impact
- [ ] Identified constraints
- [ ] Defined success criteria
- [ ] Got specific examples

**Quality**:
- [ ] Captured verbatim quotes for key points
- [ ] Documented specific numbers (not vague statements)
- [ ] Paraphrased to confirm understanding
- [ ] Clarified ambiguities
- [ ] Validated interpretation with stakeholder

**Documentation**:
- [ ] Transcript created within 24 hours
- [ ] Insights extracted and categorized
- [ ] Themes updated
- [ ] Contradictions flagged
- [ ] Questions tracked

**Next Steps**:
- [ ] Referrals documented
- [ ] Follow-up actions identified
- [ ] Next interview planned

---

## Common Pitfalls & How to Avoid

### Pitfall: Leading the Witness
❌ "Don't you think the problem is caused by [your theory]?"
✅ "What do you think causes this problem?"

### Pitfall: Jumping to Solutions
❌ "So we should build [solution], right?"
✅ "What would success look like, regardless of how we get there?"

### Pitfall: Accepting Vague Statements
❌ "It happens pretty often" → Moving on
✅ "Can you quantify 'pretty often'? Daily? Weekly? How many times?"

### Pitfall: Stopping at Symptoms
❌ "The system is slow" → Done
✅ "Why is the system slow?" → Keep asking why

### Pitfall: Missing Contradictions
❌ Ignoring when stakeholder says conflicting things
✅ "Earlier you said [A], now you're saying [B] - can you help me understand?"

### Pitfall: Interviewer Talking Too Much
❌ 50/50 or 60/40 interviewer/stakeholder talk time
✅ 20/80 or 10/90 - Stakeholder should talk most

### Pitfall: Not Documenting Soon Enough
❌ Waiting days to write transcript
✅ Document within 24 hours while fresh

---

## Tips for Effective Interviews

### Build Rapport
- Use stakeholder's name
- Show genuine interest
- Acknowledge their expertise
- Empathize with their frustrations
- Don't judge or criticize

### Ask Great Follow-Ups
- "Tell me more about that"
- "Can you give me an example?"
- "What happened next?"
- "How did that make you feel?"
- "Why do you think that is?"

### Use Silence Strategically
- After asking a question, wait
- Count to 5 in your head
- Let stakeholder think
- Often the best insights come after a pause

### Capture Emotion
- Note when stakeholder gets animated
- Pay attention to frustration, excitement, resignation
- Emotional responses indicate priorities

### Look for Inconsistencies
- Between what they say and do
- Between early and later statements
- Between their view and others' views

---

## Success Criteria for Interview Workflow

**A successful interview produces**:
✅ Clear understanding of problem from this stakeholder's perspective
✅ At least one root cause identified
✅ Quantified impact (numbers, not adjectives)
✅ Specific examples or stories
✅ Identified constraints
✅ Defined success criteria
✅ Verbatim quotes for problem statement
✅ Referrals to other stakeholders
✅ Complete transcript within 24 hours
✅ Insights integrated into synthesis

**Ready for next steps when**:
✅ Themes are emerging across multiple interviews
✅ Root causes are becoming clear
✅ Impact is quantified
✅ Contradictions are identified (even if not resolved)
✅ All stakeholder perspectives represented
✅ Diminishing returns on new interviews (hearing same things)

---

**Remember**: The goal isn't to interview as many people as possible. It's to deeply understand the problem from all relevant perspectives. Quality over quantity. Three excellent interviews beat ten superficial ones.
