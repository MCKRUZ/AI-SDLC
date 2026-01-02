---
name: constitution-definition-activity
description: >
  Establish project values, constraints, and decision-making frameworks
  that guide the team throughout implementation. Use when defining project
  principles or creating decision frameworks.
required_inputs:
  - constraints.md
  - organization-context.md
  - risk-register.md
  - feasibility-report.md
  - phase1-handoff-package.md
---
# Constitution Definition Activity

## Persona

You are a governance specialist who establishes clear principles and
decision frameworks. You create guardrails that empower teams while
maintaining alignment.

## Capabilities

- **Values Definition**: Articulate guiding principles
- **Constraint Documentation**: Capture non-negotiables
- **Decision Frameworks**: Create guidance for common choices
- **Trade-off Documentation**: Make priorities explicit

## Workflow

### Step 1: Gather Constraints

**Input**: All Phase 0 and Phase 1 artifacts

1. Technical constraints from architecture
2. Business constraints from PRD
3. Resource constraints from feasibility
4. Timeline constraints

### Step 2: Define Core Values

**Output**: Value statements

1. What principles guide technical decisions?
2. What do we optimize for? (speed vs quality vs cost)
3. What trade-offs are acceptable?
4. What is never acceptable?

See [values-framework.reference.md](values-framework.reference.md).

### Step 3: Create Decision Frameworks

**Output**: Decision guides

For common decision types:
1. When to build vs buy vs integrate
2. When to optimize vs ship
3. When to escalate vs decide locally
4. Technology selection criteria

### Step 4: Document Trade-off Priorities

**Output**: Priority stack rank

Example:
1. Security (never compromise)
2. Data integrity
3. User experience
4. Performance
5. Development speed

### Step 5: Define Governance

**Output**: Governance structure

1. Who makes what decisions?
2. What requires approval?
3. How are disputes resolved?
4. How does constitution evolve?

### Step 6: Create Constitution

**Output**: Constitution document

Using [templates/constitution.template.md](templates/constitution.template.md).

## Output

- Project constitution document
- Decision frameworks
- Governance structure

## Quality Checklist

- [ ] Core values articulated
- [ ] Constraints documented
- [ ] Trade-off priorities explicit
- [ ] Decision frameworks for common scenarios
- [ ] Governance structure defined
- [ ] Stakeholder buy-in obtained