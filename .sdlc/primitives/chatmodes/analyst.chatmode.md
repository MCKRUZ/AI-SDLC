# Analyst Chatmode

## Purpose
Focused requirements discovery and specification sessions using the Business Analyst Agent.

## When to Use This Mode
- Conducting stakeholder interviews for requirements
- Documenting functional and non-functional requirements
- Clarifying ambiguous requirements
- Creating or refining spec.md
- Resolving requirements conflicts

## Session Setup

### Before Starting
Load these artifacts into context:
1. Constitution (./constitution.md)
2. Organization context (../../.memory/organization.context.md)
3. Technical stack context (../../.memory/technical-stack.context.md)
4. Problem statement from Phase 0
5. Feasibility report from Phase 0

### Agent Instructions
Load: `analyst-agent.instructions.md`

### Session Goal
Define a clear goal for the session:
- "Document requirements for [feature area]"
- "Clarify ambiguous requirements from initial discovery"
- "Interview [stakeholder role] about [topic]"
- "Create acceptance criteria for [user stories]"

## Interaction Patterns

### Pattern 1: Stakeholder Interview Session

**Opening Prompt:**
```
I need to conduct a requirements discovery interview with [stakeholder role] 
for [feature/area]. Please use the Business Analyst Agent instructions to 
facilitate this interview using:
- Five Whys for root cause analysis
- Jobs-to-be-Done framework for understanding motivations
- User Story Mapping for structuring requirements

Focus on: [specific area or questions]
```

**During Interview:**
- Let the agent ask probing questions
- Provide stakeholder responses
- Agent will document requirements as you go
- Agent will identify edge cases and follow up on ambiguities

**Closing:**
```
Please summarize the key requirements discovered, identify any 
gaps or ambiguities that need follow-up, and format the output 
according to the spec.md template.
```

### Pattern 2: Requirements Documentation Session

**Opening Prompt:**
```
I have gathered the following information from stakeholders:
[Paste interview notes, email threads, or discussion summaries]

Please use the Business Analyst Agent instructions to:
1. Extract functional requirements with user stories
2. Define acceptance criteria for each requirement
3. Identify non-functional requirements
4. Document business rules
5. Flag any ambiguities or gaps

Format output according to spec.md template.
```

**Iterative Refinement:**
```
For requirement FR-XXX, please:
- Add acceptance criteria for [edge case]
- Clarify the business rule about [topic]
- Define the integration requirement with [system]
```

### Pattern 3: Clarification Session

**Opening Prompt:**
```
Review the current spec.md and identify:
1. Ambiguous requirements that need clarification
2. Conflicting requirements
3. Missing information or gaps
4. Requirements that lack sufficient acceptance criteria

Organize these into clarification questions for stakeholders.
```

**Follow-up:**
```
Here are the stakeholder responses to the clarification questions:
[Paste responses]

Please update the spec.md sections and document the clarifications 
in clarifications.md.
```

### Pattern 4: Requirements Validation Session

**Opening Prompt:**
```
Review the following requirements against the constitution and 
Phase 0 problem statement:
[Paste requirements section]

Check for:
- Testability (every requirement must be testable)
- Completeness (all necessary details provided)
- Clarity (no ambiguous language)
- Traceability (links to problem statement)
- Constitution compliance
```

## Best Practices for This Mode

### Do's
- ✅ Focus on understanding the "what" not the "how"
- ✅ Ask follow-up questions when answers are unclear
- ✅ Document edge cases and error scenarios
- ✅ Use specific, measurable language
- ✅ Validate requirements with stakeholders
- ✅ Keep sessions focused on one feature area at a time

### Don'ts
- ❌ Don't jump into technical solutions
- ❌ Don't accept vague requirements ("fast", "user-friendly")
- ❌ Don't skip edge cases
- ❌ Don't make assumptions without validating
- ❌ Don't try to cover too much in one session

## Session Outputs

### Primary Artifacts
- **spec.md** sections with:
  - Functional requirements (FR-XXX format)
  - Non-functional requirements (NFR-XXX format)
  - Business rules
  - User stories with acceptance criteria
  - Edge cases
  - Integration requirements

- **clarifications.md** entries with:
  - Questions asked
  - Responses received
  - Resolutions made
  - Stakeholders consulted

### Work-in-Progress Outputs
- Interview transcripts
- Raw notes to be refined
- Questions for follow-up
- Identified gaps

## Quality Checks Before Ending Session

- [ ] All functional requirements have acceptance criteria
- [ ] Non-functional requirements are measurable
- [ ] Business rules are clearly stated
- [ ] Edge cases are documented
- [ ] No ambiguous language remains
- [ ] Requirements trace to problem statement
- [ ] Integration points are identified
- [ ] Data requirements are complete

## Example Session Flow

```
USER: I need to gather requirements for the customer dashboard feature.

AGENT (Analyst): I'll help facilitate requirements discovery for the customer 
dashboard. Let me start with some key questions:

1. What is the primary job-to-be-done for users of this dashboard?
2. What decisions do they need to make using this dashboard?
3. What's currently frustrating about how they accomplish this today?

[User provides responses]

AGENT: Let me dig deeper using Five Whys on the pain point you mentioned...

[Agent conducts interview]

AGENT: Based on our discussion, I've documented the following requirements:

FR-001: Customer Overview Widget
User Story: As a support agent, I want to see a customer's key information 
at a glance, so that I can quickly understand their account status.

Acceptance Criteria:
- Given I'm viewing a customer dashboard
- When the page loads
- Then I see: customer name, account type, subscription status, last activity date

Business Rules:
- Subscription status must reflect real-time data
- Last activity includes: login, support ticket, or purchase

[Continues with more requirements]

USER: What about when the customer data is missing?

AGENT: Good question - that's an edge case we need to document...

[Session continues]
```

## Tips for Effective Sessions

### Keep Sessions Focused
- Limit to 1-2 feature areas per session
- Timebox to 60-90 minutes
- Take breaks for complex areas

### Iterate Progressively
- Start broad (high-level user stories)
- Then go deep (detailed acceptance criteria)
- Validate at each level

### Use Visual Aids
- Ask agent to create process flows
- Request data flow diagrams
- Have agent suggest user journey maps

### Document Continuously
- Don't wait until end to document
- Keep running spec.md updated
- Note open questions as you go

## Common Challenges & Solutions

**Challenge**: Stakeholder gives solution instead of requirement
**Solution**: Ask "What problem are you trying to solve?" (Five Whys)

**Challenge**: Requirements are too vague
**Solution**: Ask for specific examples, metrics, or scenarios

**Challenge**: Conflicting requirements from different stakeholders
**Solution**: Document both, flag conflict, schedule resolution session

**Challenge**: Too many requirements emerging
**Solution**: Document all, but flag for PM prioritization

**Challenge**: Technical constraints unclear
**Solution**: Flag for Architect review, continue with requirement gathering

## Session Templates

### Quick Interview Template
```
Stakeholder: [Name/Role]
Feature Area: [Area]
Duration: [Time]

Key Questions:
1. What are you trying to accomplish?
2. What's the current process?
3. What's frustrating about it?
4. What would success look like?
5. What are the edge cases?

[Agent conducts interview following these questions]
```

### Batch Requirements Template
```
I have these user stories that need acceptance criteria:
1. [User story 1]
2. [User story 2]
3. [User story 3]

For each, please provide:
- Given/When/Then acceptance criteria
- Business rules
- Edge cases
- Data requirements
```

---

*Chatmode for: Business Analyst Agent*
*Use for: Requirements discovery and specification*
*Session length: 30-90 minutes per focused area*
