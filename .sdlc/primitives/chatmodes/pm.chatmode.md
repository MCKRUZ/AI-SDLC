# PM Chatmode

## Purpose
Focused product strategy and PRD creation sessions using the Product Manager Agent.

## When to Use This Mode
- Creating product vision and strategy
- Prioritizing features using frameworks (RICE/MoSCoW)
- Defining MVP scope
- Creating product roadmap
- Developing user personas
- Mapping user journeys
- Establishing product metrics

## Session Setup

### Before Starting
Load these artifacts into context:
1. Constitution (./constitution.md)
2. Spec (./spec.md) - All requirements
3. Clarifications (./clarifications.md) - Requirements clarifications
4. Problem statement from Phase 0
5. Feasibility report from Phase 0

### Agent Instructions
Load: `pm-agent.instructions.md`

### Session Goal
Define a clear goal for the session:
- "Create product vision for [project]"
- "Prioritize features for MVP"
- "Develop user personas"
- "Map user journey for [specific flow]"
- "Define success metrics"

## Interaction Patterns

### Pattern 1: Product Vision Session

**Opening Prompt:**
```
Based on the problem statement and requirements in spec.md, 
help me craft a compelling product vision using the Product 
Manager Agent instructions.

Create:
1. Product vision statement (For/Who/The/Is a/That/Unlike/Our product format)
2. Target user description
3. Key value proposition
4. Differentiators from current state

Context to consider:
[Add any specific business context, competitive info, or strategic goals]
```

**Refinement:**
```
The vision needs to emphasize [aspect] more strongly because [reason].
Please revise with this in mind.
```

### Pattern 2: Feature Prioritization Session

**Opening Prompt:**
```
I need to prioritize the features from spec.md using the RICE framework.

For each feature, help me assess:
- Reach: How many users per time period?
- Impact: Massive(3) / High(2) / Medium(1) / Low(0.5) / Minimal(0.25)
- Confidence: High(100%) / Medium(80%) / Low(50%)
- Effort: Person-weeks estimate

Create a prioritized list with RICE scores and rationale.

Constraints:
- MVP must deliver in [X weeks]
- Team size: [Y people]
- Budget: [Z]
```

**Alternative - MoSCoW:**
```
Use MoSCoW prioritization to categorize features from spec.md:
- Must Have (critical for MVP)
- Should Have (important but not blocking)
- Could Have (nice to have)
- Won't Have (future releases)

Provide clear rationale for each categorization.
```

**Follow-up:**
```
I disagree with [Feature X] being [priority]. It should be [other priority] 
because [business reason]. Please re-evaluate and update the prioritization.
```

### Pattern 3: MVP Scoping Session

**Opening Prompt:**
```
Based on the prioritized features, help me define the MVP scope.

Constraints:
- Timeline: [X weeks/months]
- Team: [Y developers]
- Budget: [Z]
- Must address: [core pain points from Phase 0]

Create:
1. Clear MVP goal statement
2. Success criteria for MVP
3. Features in scope (with rationale)
4. Features explicitly out of scope (with rationale)
5. Key assumptions
6. Critical risks

Be ruthless about scope - what's the MINIMUM that's still VIABLE?
```

**Scope Validation:**
```
Walk through how a user would accomplish [key job-to-be-done] 
with only the MVP features. Are there any gaps that would make 
it non-viable?
```

### Pattern 4: Persona Development Session

**Opening Prompt:**
```
Based on stakeholder interviews from Phase 0 and user roles in spec.md, 
create 2-4 primary personas.

For each persona include:
- Name and role
- Demographics and tech savviness
- Goals and motivations
- Pain points and frustrations
- Needs from the product
- Success scenario
- Characteristic quote

Make them realistic and data-backed, not stereotypes.
```

**Persona Validation:**
```
For [Persona Name], add more detail about:
- Their typical workflow
- Their biggest frustration
- How they currently work around the problem
```

### Pattern 5: User Journey Mapping Session

**Opening Prompt:**
```
Create a user journey map for [Persona Name] accomplishing [goal].

Show:
1. Current experience (As-Is):
   - Each step they take
   - Pain points at each step
   - Time spent, error rate, tools required

2. Future experience (To-Be):
   - How our product improves each step
   - Time saved, errors reduced
   - Which requirements enable this improvement

Map the journey to specific requirements from spec.md.
```

**Multiple Journeys:**
```
Create journey maps for these key scenarios:
1. [Scenario 1]
2. [Scenario 2]
3. [Scenario 3]

Prioritize by frequency and importance.
```

### Pattern 6: Success Metrics Session

**Opening Prompt:**
```
Define success metrics for this product based on the problem 
statement goals and business objectives.

For each metric:
- Definition (exactly what's measured)
- Why it matters (business justification)
- Current baseline (if known)
- Target value and timeframe
- How we'll measure it
- Tracking frequency
- Owner

Categorize as:
- Primary metrics (core product success)
- Secondary metrics (supporting indicators)
- User experience metrics
- Business metrics
- Technical health metrics
```

**Metrics Validation:**
```
For the metric "[Metric Name]", verify:
1. Is it aligned with Phase 0 success criteria?
2. Can architecture support tracking this?
3. Is the target realistic?
4. Who will monitor and act on this metric?
```

### Pattern 7: Product Roadmap Session

**Opening Prompt:**
```
Create a product roadmap with 3 phases based on the prioritized features.

For each phase:
- Phase goal (what value is delivered)
- Features included
- Success metrics
- Key milestones
- Dependencies
- Estimated timeline

Phase 1: MVP (Months 1-X)
Phase 2: Enhancement (Months Y-Z)
Phase 3: Scale (Months A-B)

Balance technical feasibility, business value, and user needs.
```

**Roadmap Adjustment:**
```
If we need to launch MVP 2 months earlier, what would you 
recommend removing from Phase 1 and deferring to Phase 2?
Explain the trade-offs.
```

## Best Practices for This Mode

### Do's
- ✅ Ground decisions in user value
- ✅ Use data to support prioritization
- ✅ Be ruthless about MVP scope
- ✅ Make trade-offs explicit
- ✅ Connect features to business goals
- ✅ Think about the full user experience
- ✅ Plan for measurement from day one

### Don'ts
- ❌ Don't prioritize by stakeholder volume (loudest voice)
- ❌ Don't include "nice to haves" in MVP
- ❌ Don't set vague metrics ("improve satisfaction")
- ❌ Don't ignore technical complexity
- ❌ Don't plan more than 3 phases ahead
- ❌ Don't forget about post-launch iteration

## Session Outputs

### Primary Artifacts
- **prd.md** with:
  - Product vision statement
  - User personas (2-4)
  - User journey maps
  - Feature prioritization (RICE or MoSCoW)
  - MVP definition
  - Product roadmap (3 phases)
  - Success metrics with baselines and targets
  - Assumptions and risks
  - Analytics requirements

### Supporting Artifacts
- Prioritization worksheets
- Persona profiles
- Journey maps
- Roadmap timeline
- Metrics dashboard specs

## Quality Checks Before Ending Session

- [ ] Product vision is clear and compelling
- [ ] Personas are realistic and data-backed
- [ ] User journeys connect to requirements
- [ ] Prioritization uses a clear framework with rationale
- [ ] MVP scope is minimal yet viable
- [ ] Roadmap shows clear evolution
- [ ] Metrics are specific and measurable
- [ ] Assumptions are documented
- [ ] Risks have mitigation strategies
- [ ] Analytics requirements are complete

## Example Session Flow

```
USER: I need to prioritize features for our customer portal MVP.

AGENT (PM): Let's use the RICE framework to prioritize systematically. 
I'll need to understand your constraints first:

1. What's your target launch date?
2. How many developers on the team?
3. What's the core problem from Phase 0 we MUST solve?

[User provides context]

AGENT: Based on spec.md, I see 15 functional requirements. Let me 
analyze each using RICE:

FR-001: Customer dashboard overview
- Reach: 800 users/month (all customers)
- Impact: 3 (Massive - addresses core pain of slow data access)
- Confidence: 100% (validated in Phase 0 interviews)
- Effort: 3 person-weeks
- RICE Score: (800 × 3 × 1.0) / 3 = 800

FR-002: Ticket submission form
- Reach: 400 users/month (50% of customers file tickets)
- Impact: 2 (High - improves support workflow)
- Confidence: 80% (some uncertainty on complexity)
- Effort: 2 person-weeks
- RICE Score: (400 × 2 × 0.8) / 2 = 320

[Continues through all features]

AGENT: Here's the prioritized list. For MVP with 12 weeks and 3 developers, 
I recommend the top 6 features which total 18 person-weeks...

USER: FR-005 seems high priority but you ranked it low. Why?

AGENT: FR-005 has high impact but very low reach - only 20 power users per 
month. For MVP, we're optimizing for reach × impact. I recommend deferring 
to Phase 2 once we've proven value with the broader user base. However, if 
those 20 power users are business-critical, we can reconsider...

[Session continues with MVP definition]
```

## Tips for Effective Sessions

### Start with Why
- Always ground in user value
- Connect to Phase 0 problem statement
- Reference business goals

### Use Frameworks Consistently
- Stick to one prioritization method
- Apply it consistently across features
- Document the framework used

### Challenge Assumptions
- Ask "how do we know this?"
- Identify highest-risk assumptions
- Plan validation early

### Think in Outcomes
- Focus on user outcomes, not outputs
- "Users can accomplish X" not "We ship Y"
- Metrics should measure outcomes

### Be Comfortable with Trade-offs
- Everything is a trade-off
- Make them explicit
- Document what you're sacrificing

## Common Challenges & Solutions

**Challenge**: Too many features for MVP
**Solution**: Ask "Can we launch without this?" for each feature

**Challenge**: Stakeholders disagree on priorities
**Solution**: Use objective framework (RICE), show the math

**Challenge**: MVP doesn't feel "viable"
**Solution**: Validate users can complete key job-to-be-done

**Challenge**: Unclear what metrics matter
**Solution**: Start with Phase 0 success criteria, work backward

**Challenge**: Roadmap too detailed for future phases
**Solution**: Phase 1 detailed, Phase 2 directional, Phase 3 themes only

**Challenge**: Technical complexity not considered
**Solution**: Consult with architect before finalizing priorities

## Session Templates

### Quick Prioritization Template
```
Features to prioritize:
1. [Feature 1]
2. [Feature 2]
3. [Feature 3]

Framework: RICE
Constraints: [Timeline, team size, budget]

For each feature, assess and calculate RICE score.
Create prioritized list with recommendations.
```

### MVP Definition Template
```
Based on prioritized features, define MVP:

Goal: [What makes this viable and valuable]
Success Criteria: [Measurable outcomes]
In Scope: [Features with rationale]
Out of Scope: [Features deferred with rationale]
Assumptions: [What must be true]
Risks: [What could go wrong]

Validate: Can user accomplish [core job] with MVP?
```

### Persona Template
```
Create persona for: [User type]
Based on: [Research source]

Include:
- Role and responsibilities
- Goals and motivations
- Pain points
- Needs from product
- Success scenario
- Quote

Make it realistic, not a stereotype.
```

---

*Chatmode for: Product Manager Agent*
*Use for: Product strategy and PRD creation*
*Session length: 45-90 minutes per focused area*
