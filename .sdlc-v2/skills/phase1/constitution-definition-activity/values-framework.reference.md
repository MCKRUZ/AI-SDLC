# Values Framework Reference

## Overview

A project constitution establishes the principles, constraints, and
decision-making frameworks that guide the team. Values are the foundation
that inform all other decisions.

---

## Core Value Categories

### Quality Values

Define what "good" means for your project:

| Value | Description | Trade-off |
|-------|-------------|-----------|
| **Reliability** | System works correctly | vs. Speed of delivery |
| **Performance** | Fast response times | vs. Development cost |
| **Security** | Protected from threats | vs. User convenience |
| **Maintainability** | Easy to change | vs. Initial velocity |
| **Usability** | Easy to use | vs. Feature richness |

### Delivery Values

Define how you work:

| Value | Description | Trade-off |
|-------|-------------|-----------|
| **Speed** | Deliver quickly | vs. Quality/completeness |
| **Predictability** | Meet commitments | vs. Flexibility |
| **Simplicity** | Keep it simple | vs. Completeness |
| **Innovation** | Try new approaches | vs. Risk |
| **Consistency** | Follow standards | vs. Best-fit solutions |

### Team Values

Define how you interact:

| Value | Description | Trade-off |
|-------|-------------|-----------|
| **Transparency** | Open communication | vs. Efficiency |
| **Autonomy** | Team decides | vs. Alignment |
| **Collaboration** | Work together | vs. Individual speed |
| **Ownership** | Take responsibility | vs. Specialization |
| **Learning** | Continuous improvement | vs. Delivery focus |

---

## Value Prioritization

### Stack Rank Values

Force prioritization by creating a stack rank:

```markdown
## Value Priority (High to Low)

1. **Security** - Never compromise user data
2. **Reliability** - System must work correctly
3. **Usability** - Users must be able to accomplish goals
4. **Performance** - Response times matter but aren't critical
5. **Aesthetics** - Nice to have, not essential

### What This Means

When security and usability conflict → Security wins
When reliability and performance conflict → Reliability wins
```

### Decision Framework

Create explicit guidance for common conflicts:

```markdown
## Decision Framework

### Speed vs Quality
Default: Quality wins
Exception: Hotfixes for production issues can skip some testing

### Build vs Buy
Default: Buy if solution exists and fits
Exception: Build if core differentiator

### Consistency vs Best-Fit
Default: Consistency with existing patterns
Exception: When measurably better by 50%+

### Documentation vs Code
Default: Code is documentation
Exception: Architecture decisions, APIs, and onboarding require docs
```

---

## Non-Negotiables

### Defining Non-Negotiables

Things that NEVER change regardless of pressure:

```markdown
## Non-Negotiables

### Security
- ❌ NEVER store passwords in plain text
- ❌ NEVER expose PII without encryption
- ❌ NEVER skip security review for external APIs
- ❌ NEVER commit secrets to source control

### Data Integrity
- ❌ NEVER delete data without backup
- ❌ NEVER deploy without database migration plan
- ❌ NEVER bypass validation for "convenience"

### Quality
- ❌ NEVER deploy without passing tests
- ❌ NEVER merge without code review
- ❌ NEVER ignore production errors

### User Experience
- ❌ NEVER lose user data without warning
- ❌ NEVER change functionality without notice
- ❌ NEVER make irreversible actions easy
```

### Anti-Patterns

Explicitly document what you will NOT do:

```markdown
## Anti-Patterns (What We Avoid)

### Code Anti-Patterns
- God classes/functions
- Copy-paste reuse
- Magic numbers/strings
- Ignored exceptions
- Commented-out code

### Process Anti-Patterns
- Cowboy coding (direct to production)
- Hero culture (one person knows everything)
- Meeting overload
- Documentation as afterthought
- "We'll fix it later"

### Architecture Anti-Patterns
- Big ball of mud
- Golden hammer (one solution for everything)
- Vendor lock-in without strategy
- Premature optimization
- Over-engineering
```

---

## Constraint Documentation

### Technical Constraints

```markdown
## Technical Constraints

### Technology Stack
- **Languages**: TypeScript (frontend), C# (backend), Python (ML)
- **Frameworks**: React, .NET 8, FastAPI
- **Databases**: PostgreSQL (primary), Redis (cache)
- **Cloud**: Azure (no multi-cloud)
- **Rationale**: Existing team expertise, enterprise agreements

### Integration Constraints
- All external APIs must go through API gateway
- No direct database access from frontend
- All inter-service communication via message queue or gRPC

### Compliance Constraints
- GDPR: Data residency in EU
- SOC 2: Audit logging required
- Accessibility: WCAG 2.1 AA
```

### Resource Constraints

```markdown
## Resource Constraints

### Team
- Team size: 6 developers (fixed)
- Skill gaps: No dedicated DevOps
- Availability: 80% (account for meetings, support)

### Budget
- Cloud: $10K/month maximum
- Third-party services: $2K/month
- No additional headcount approved

### Timeline
- MVP: 12 weeks from start
- Production: 16 weeks from start
- No extensions available (external deadline)
```

### Organizational Constraints

```markdown
## Organizational Constraints

### Approval Requirements
- Architecture changes: Tech Lead + CTO
- Third-party integrations: Security + Legal
- User-facing changes: Product + UX
- Infrastructure: DevOps + Finance

### Process Requirements
- All code must be peer-reviewed
- All deployments through CI/CD
- Change management for production
- On-call rotation required

### Communication Requirements
- Daily standup (async acceptable)
- Weekly stakeholder update
- Sprint reviews with demo
- Postmortem for incidents
```

---

## Governance Structure

### Decision-Making Matrix

| Decision Type | Who Decides | Who Approves | Who's Informed |
|---------------|-------------|--------------|----------------|
| Feature scope | Product Owner | Stakeholders | Dev Team |
| Technical approach | Tech Lead | CTO | Dev Team |
| Architecture | Architect | Tech Lead + CTO | All |
| Sprint commitment | Dev Team | Scrum Master | Product Owner |
| Production deploy | On-call | Tech Lead | All |
| Hotfix | On-call | Tech Lead | All + Stakeholders |

### Escalation Path

```
┌─────────────────┐
│ Team Member     │
└────────┬────────┘
         │ Can't resolve
         ▼
┌─────────────────┐
│ Tech Lead       │
└────────┬────────┘
         │ Can't resolve
         ▼
┌─────────────────┐
│ Engineering     │
│ Manager         │
└────────┬────────┘
         │ Can't resolve
         ▼
┌─────────────────┐
│ CTO / VP Eng    │
└─────────────────┘
```

### Dispute Resolution

```markdown
## Dispute Resolution Process

1. **Discussion**: Parties discuss and try to reach consensus
2. **Data**: Gather data/evidence if opinion-based
3. **Tech Lead**: Tech Lead makes call if no consensus
4. **Time-box**: Decision must be made within 24 hours
5. **Document**: Record decision and rationale in ADR
6. **Commit**: Everyone commits to decision regardless of position
```

---

## Constitution Template

```markdown
# Project Constitution

## Project: [Name]
## Version: [1.0]
## Date: [YYYY-MM-DD]
## Owners: [Names]

---

## Mission

[One sentence describing what we're building and why]

---

## Values (Stack Ranked)

1. [Value 1] - [Description]
2. [Value 2] - [Description]
3. [Value 3] - [Description]
4. [Value 4] - [Description]
5. [Value 5] - [Description]

---

## Non-Negotiables

- [Non-negotiable 1]
- [Non-negotiable 2]
- [Non-negotiable 3]

---

## Decision Frameworks

### [Decision Type 1]
- Default: [Default choice]
- Exception: [When to deviate]

### [Decision Type 2]
- Default: [Default choice]
- Exception: [When to deviate]

---

## Constraints

### Technical
- [Constraint 1]
- [Constraint 2]

### Resource
- [Constraint 1]
- [Constraint 2]

### Organizational
- [Constraint 1]
- [Constraint 2]

---

## Governance

### Decision Rights
[RACI or decision matrix]

### Escalation
[Escalation path]

---

## Anti-Patterns

- [Anti-pattern 1]
- [Anti-pattern 2]

---

## Amendment Process

[How this constitution can be changed]

---

## Signatures

| Role | Name | Date |
|------|------|------|
| Product Owner | | |
| Tech Lead | | |
| Team | | |
```

---

## Quick Reference

### Value Questions
1. What do we optimize for?
2. What do we sacrifice if needed?
3. What do we NEVER compromise?
4. How do we resolve conflicts?

### Constraint Questions
1. What can't we change?
2. What limits our options?
3. What must we comply with?
4. Who must approve what?

### Governance Questions
1. Who decides what?
2. How do we escalate?
3. How do we resolve disputes?
4. How does this evolve?
