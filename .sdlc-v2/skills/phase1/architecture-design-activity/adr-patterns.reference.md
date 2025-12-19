# Architecture Decision Records (ADR) Patterns

## Overview

ADRs document significant architecture decisions with context, rationale,
and consequences. They capture the "why" behind decisions for future reference.

---

## Standard ADR Template

```markdown
# ADR-NNN: [Decision Title]

**Status**: [Proposed | Accepted | Deprecated | Superseded by ADR-XXX]
**Date**: YYYY-MM-DD
**Deciders**: [List of people involved in the decision]

## Context

[Describe the situation and forces at play. What problem are we trying
to solve? What constraints exist? What are the requirements?]

## Decision

[State the decision clearly. Use active voice: "We will use..." not
"It was decided that..."]

## Consequences

### Positive
- [Benefit 1]
- [Benefit 2]

### Negative
- [Drawback 1]
- [Drawback 2]

### Neutral
- [Trade-off or implication]

## Alternatives Considered

### [Alternative 1 Name]
- **Description**: [What this option entails]
- **Pros**: [Benefits]
- **Cons**: [Drawbacks]
- **Why Rejected**: [Reason not chosen]

### [Alternative 2 Name]
- **Description**: [What this option entails]
- **Pros**: [Benefits]
- **Cons**: [Drawbacks]
- **Why Rejected**: [Reason not chosen]

## Related Decisions

- [ADR-XXX: Related decision]
- [ADR-YYY: Prerequisite decision]
```

---

## When to Write an ADR

### Always Document

- Technology stack selection (language, framework, database)
- Integration patterns (sync vs async, protocols)
- Security approaches (authentication, authorization)
- Data architecture (storage, caching, partitioning)
- Deployment strategy (containerization, orchestration)
- Major library/package choices

### Consider Documenting

- Coding conventions and patterns
- Testing strategies
- Monitoring and observability approaches
- API versioning strategy
- Error handling patterns

### Don't Document

- Trivial decisions easily changed
- Decisions already standardized org-wide
- Implementation details within components

---

## ADR Categories

### Technology Selection

```markdown
# ADR-001: Use PostgreSQL for Primary Database

**Status**: Accepted
**Date**: 2024-01-15

## Context

We need a primary database for our e-commerce platform. Requirements:
- ACID compliance for financial transactions
- Support for complex queries and reporting
- Horizontal read scaling capability
- Team expertise

## Decision

We will use PostgreSQL 15 as our primary relational database.

## Consequences

### Positive
- Strong ACID compliance for order/payment integrity
- Excellent query optimization and performance
- Read replicas for scaling read operations
- Team has 5+ years PostgreSQL experience

### Negative
- Write scaling requires more complex solutions
- Operational overhead vs managed NoSQL options

## Alternatives Considered

### MongoDB
- **Pros**: Flexible schema, easy horizontal scaling
- **Cons**: Weaker consistency guarantees, less SQL expertise on team
- **Why Rejected**: Financial transactions require strong consistency

### MySQL
- **Pros**: Team familiarity, good performance
- **Cons**: Less advanced features, weaker JSON support
- **Why Rejected**: PostgreSQL offers better feature set for our needs
```

### Integration Pattern

```markdown
# ADR-002: Use Event-Driven Architecture for Service Communication

**Status**: Accepted
**Date**: 2024-01-20

## Context

Our microservices need to communicate for order processing workflows.
Requirements:
- Loose coupling between services
- Resilience to service failures
- Ability to replay events
- Audit trail of all changes

## Decision

We will use an event-driven architecture with Apache Kafka as the
message broker for inter-service communication.

## Consequences

### Positive
- Services decoupled; can evolve independently
- Events persisted; supports replay and recovery
- Natural audit trail of all system events
- Handles traffic spikes via buffering

### Negative
- Increased complexity (eventual consistency)
- Requires investment in Kafka operations
- Debugging distributed flows more difficult

### Neutral
- Team needs training on event-driven patterns
- Need to design event schemas carefully
```

### Security Decision

```markdown
# ADR-003: Use OAuth 2.0 with JWT for API Authentication

**Status**: Accepted
**Date**: 2024-01-25

## Context

We need to authenticate API requests from our SPA, mobile app, and
third-party integrations. Requirements:
- Stateless authentication for scalability
- Support for multiple client types
- Integration with enterprise SSO
- Token refresh capability

## Decision

We will implement OAuth 2.0 authorization with JWT access tokens:
- Authorization Code flow with PKCE for web/mobile
- Client Credentials flow for service-to-service
- JWT tokens with 15-minute expiry
- Refresh tokens with 7-day sliding window

## Consequences

### Positive
- Industry standard; well-understood security model
- Stateless; scales horizontally
- Supports SSO integration
- Libraries available for all platforms

### Negative
- JWT tokens cannot be revoked instantly
- Token size larger than session IDs
- Complexity in token refresh handling
```

---

## ADR Status Lifecycle

```
┌──────────┐     ┌──────────┐     ┌────────────┐
│ Proposed │────▶│ Accepted │────▶│ Deprecated │
└──────────┘     └──────────┘     └────────────┘
                      │                  │
                      │                  ▼
                      │           ┌─────────────┐
                      └──────────▶│ Superseded  │
                                  │ by ADR-XXX  │
                                  └─────────────┘
```

### Status Definitions

| Status | Meaning |
|--------|---------|
| **Proposed** | Under discussion, not yet decided |
| **Accepted** | Decision made, currently in effect |
| **Deprecated** | No longer applies, but not replaced |
| **Superseded** | Replaced by a newer decision |

---

## Naming Conventions

### File Naming

```
adrs/
├── 001-use-postgresql-database.md
├── 002-event-driven-architecture.md
├── 003-oauth-jwt-authentication.md
├── 004-kubernetes-deployment.md
└── README.md (index of decisions)
```

### Numbering

- Use sequential numbers: 001, 002, 003
- Never reuse numbers (even for deprecated ADRs)
- Prefix with category (optional): `SEC-001`, `DATA-001`

---

## Writing Tips

### Context Section

**Do:**
- Explain the problem being solved
- List requirements and constraints
- Mention relevant stakeholders
- Include technical context

**Don't:**
- Include the decision here
- List alternatives here
- Be vague about constraints

### Decision Section

**Do:**
- State clearly what we WILL do
- Use active voice
- Be specific about the choice
- Include key parameters/configuration

**Don't:**
- Repeat the context
- Include extensive justification
- Hedge or be ambiguous

### Consequences Section

**Do:**
- Be honest about trade-offs
- Include operational implications
- Consider long-term effects
- Note what changes are needed

**Don't:**
- Only list positives
- Ignore operational burden
- Forget team impact

---

## ADR Review Checklist

Before accepting an ADR:

- [ ] Context clearly explains the problem
- [ ] Decision is specific and actionable
- [ ] At least 2 alternatives were considered
- [ ] Consequences include positives AND negatives
- [ ] Relevant stakeholders were consulted
- [ ] Decision aligns with constitution/principles
- [ ] Related ADRs are linked

---

## ADR Index Template

Create `adrs/README.md`:

```markdown
# Architecture Decision Records

## Index

| ADR | Title | Status | Date |
|-----|-------|--------|------|
| [001](001-use-postgresql-database.md) | Use PostgreSQL Database | Accepted | 2024-01-15 |
| [002](002-event-driven-architecture.md) | Event-Driven Architecture | Accepted | 2024-01-20 |
| [003](003-oauth-jwt-authentication.md) | OAuth 2.0 with JWT | Accepted | 2024-01-25 |

## By Category

### Data
- ADR-001: PostgreSQL Database

### Integration
- ADR-002: Event-Driven Architecture

### Security
- ADR-003: OAuth 2.0 with JWT

## Superseded Decisions

| ADR | Superseded By | Date |
|-----|---------------|------|
| - | - | - |
```
