---
version: 1.0
created: YYYY-MM-DD
status: draft
tech-stack:
  backend: []
  frontend: []
  database: []
  infrastructure: []
---

# System Architecture

## Architecture Principles

[From constitution]

## System Context

[High-level system diagram - text description or Mermaid]

## Component Architecture

### Component 1: [Name]

- **Responsibility**: [What it does]
- **Technology**: [Tech stack]
- **Dependencies**: [What it depends on]
- **Exposed APIs**: [What it provides]

## Data Model

### Entity: [Name]

| Field | Type | Constraints  | Description       |
| ----- | ---- | ------------ | ----------------- |
| id    | Guid | PK, Required | Unique identifier |

### Relationships

- [Entity A] → [Entity B]: [Relationship type and cardinality]

## API Design

### Endpoint: POST /api/resource

**Purpose**: [What it does]  
**Authentication**: [Required/Not required]  
**Rate Limit**: [e.g., 100 requests/minute]

**Request**:

```json
{
  "field": "type"
}
```

**Response**:

```json
{
  "field": "type"
}
```

## Infrastructure Architecture

### Deployment Model

[How the system deploys]

### Scalability Strategy

[How the system scales]

### Security Architecture

[Security measures]

## Technology Decisions

### Decision 1: [Technology Choice]

**Options Considered**:

1. Option A - Pros: [], Cons: []
2. Option B - Pros: [], Cons: []

**Decision**: Option A  
**Rationale**: [Why chosen]  
**Trade-offs**: [What we're accepting]

````

---

## Step 2: Create Agent Primitives (15 minutes)

### Constitution Agent Instructions

**File**: `.primitives/instructions/constitution-agent.instructions.md`

```markdown
---
applyTo: ".phase1/constitution.md"
description: "Constitution creation agent instructions"
---

# Constitution Agent Instructions

You are an expert in establishing software project governance. Your role is to create comprehensive project constitutions that guide all technical decisions.

## Context Loading
Before starting, always review:
- [Organization context](../../organization_context.md)
- [Problem statement](../../problem-statement-final.md)

## Your Capabilities
- Define code quality standards (must be measurable)
- Establish testing requirements (must be specific)
- Set performance benchmarks (must be quantifiable)
- Create security policies (must be clear)
- Define documentation standards (must be actionable)

## Your Constraints
- ❌ Cannot make technical implementation decisions
- ❌ Cannot define specific architectures
- ❌ Cannot create requirements or user stories
- ✅ Can define standards that architecture must meet
- ✅ Can establish quality gates

## Output Format
Create constitution following `.primitives/templates/constitution.template.md`

## Validation Before Completion
- [ ] All quality standards are measurable (include numbers/percentages)
- [ ] Testing requirements are specific (not "adequate testing")
- [ ] Security policies are clear (not "should be secure")
- [ ] Performance targets are defined (include response times/thresholds)
- [ ] Documentation standards are actionable (specific requirements)
- [ ] All sections complete (no [TBD] or placeholders)
````
