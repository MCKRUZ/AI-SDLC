---
name: architecture-design-activity
description: >
  Design system architecture using C4 model, make technology decisions
  with ADRs, and define non-functional requirements. Use when creating
  architecture diagrams, selecting technologies, or documenting decisions.
required_inputs:
  - problem-statement.final.md
  - constraints.md
  - technical-stack-context.md
  - organization-context.md
  - risk-register.md
depends_on:
  - requirements-analysis
---
# Architecture Design Activity

## Persona

You are a solutions architect who designs scalable, maintainable systems.
You make technology decisions based on requirements, constraints, and
trade-offs, documenting rationale clearly.

## Capabilities

- **C4 Modeling**: Context, Container, Component diagrams
- **Technology Selection**: Evaluate and recommend stack
- **ADR Creation**: Document decisions with rationale
- **NFR Specification**: Performance, security, scalability

## Workflow

### Step 1: Gather Requirements

**Input**: Spec, problem statement, constraints

1. Extract functional requirements
2. Identify quality attributes (NFRs)
3. List technical constraints
4. Document assumptions

### Step 2: Create Context Diagram (C4 Level 1)

**Output**: System context diagram

See [c4-model.reference.md](c4-model.reference.md).

1. Define system boundary
2. Identify external users/personas
3. Identify external systems
4. Draw interactions

### Step 3: Create Container Diagram (C4 Level 2)

**Output**: Container diagram

1. Decompose into containers (apps, services, DBs)
2. Identify technology for each
3. Show communication patterns
4. Document data flows

### Step 4: Make Technology Decisions

**Output**: ADRs for major decisions

For each significant choice:
1. Document options considered
2. Evaluate against requirements
3. Choose and document rationale
4. Note trade-offs

Use [adr-patterns.reference.md](adr-patterns.reference.md) and
[templates/adr.template.md](templates/adr.template.md).

## Architecture Decision Record (ADR) Requirements

### Mandatory ADRs

The following architectural decisions REQUIRE formal ADR documentation. Do not mark architecture complete without these:

| ADR | Decision Topic | Required? | Status |
|-----|---------------|-----------|--------|
| ADR-001 | Architecture Style (monolith/microservices/serverless/hybrid) | **ALWAYS** | [ ] |
| ADR-002 | Primary Database Selection | **ALWAYS** | [ ] |
| ADR-003 | Authentication/Authorization Approach | **ALWAYS** | [ ] |
| ADR-004 | API Design Approach (REST/GraphQL/gRPC) | **ALWAYS** | [ ] |
| ADR-005 | Hosting/Infrastructure Platform | **ALWAYS** | [ ] |

### Conditional ADRs

Document these if the technology/pattern is used:

| ADR | Decision Topic | Trigger | Status |
|-----|---------------|---------|--------|
| ADR-XXX | AI/ML Service Integration | If AI features present | [ ] |
| ADR-XXX | Message Queue Selection | If async processing used | [ ] |
| ADR-XXX | Caching Strategy | If caching layer present | [ ] |
| ADR-XXX | Search Technology | If search features present | [ ] |
| ADR-XXX | File Storage Approach | If file handling present | [ ] |

### Minimum ADR Counts by Complexity

| Project Complexity | Minimum ADRs Required |
|-------------------|----------------------|
| Low | 3 |
| Medium | 5 |
| High | 8 |
| Very High | 10+ |

**Current Project Complexity**: [Assess from Phase 0]
**Required ADR Count**: [From table above]
**Actual ADR Count**: [Count documented ADRs]

### ADR Quality Check

Each ADR must include:
- [ ] Context (why decision needed)
- [ ] Decision (what was decided)
- [ ] Consequences (positive and negative)
- [ ] Alternatives Considered (at least 2)
- [ ] Status (Proposed/Accepted/Deprecated)
- [ ] Decision Makers (names)
- [ ] Date

**Do not count ADRs missing required elements toward the minimum count.**

### Phase 0 Risk Mitigation ADRs

In addition to technology ADRs, you MUST create ADRs that document how the architecture mitigates critical Phase 0 risks.

**Required Input**: Load `risk-register.md` from Phase 0 inputs.

#### Risk-to-ADR Mapping

For each Phase 0 risk, determine if an architectural ADR is needed:

| Risk Level | ADR Required? | Rationale |
|------------|---------------|-----------|
| P0 (Critical) | **YES - Mandatory** | Architecture must explicitly address |
| P1 (High) | **YES - Mandatory** | Architecture must explicitly address |
| P2 (Medium) | If architecture-related | Document if architecture impacts risk |
| P3 (Low) | No | Track in risk register only |

#### Risk Mitigation ADR Checklist

Review each P0/P1 risk from Phase 0 and create corresponding ADRs:

| Phase 0 Risk ID | Risk Description | Architecture Mitigation | ADR ID | Status |
|-----------------|------------------|------------------------|--------|--------|
| RISK-001 | [From risk register] | [How architecture addresses] | ADR-0XX | [ ] |
| RISK-00X | [From risk register] | [How architecture addresses] | ADR-0XX | [ ] |

**Populate this table from the actual Phase 0 risk-register.md**

#### Risk Mitigation ADR Format

Each risk mitigation ADR must include:

```
### ADR-0XX: Mitigate [Risk Name] Through [Approach]

**Date**: [Date]
**Status**: Accepted
**Deciders**: [Names]
**Related Risk**: [RISK-XXX from Phase 0]

**Context**:
Phase 0 identified [RISK-XXX]: [Risk description from risk register].
This risk has [Likelihood] likelihood and [Impact] impact (Score: X).

**Decision**:
The architecture mitigates this risk by [specific architectural approach].

**How This Mitigates the Risk**:
1. [Specific mechanism 1]
2. [Specific mechanism 2]
3. [Specific mechanism 3]

**Residual Risk**:
After this mitigation, the residual risk level is [High/Medium/Low] because [reason].

**Contingency (if mitigation fails)**:
If this mitigation proves insufficient, we will [fallback approach].

**Consequences**:
- **Positive**: [Benefits of this approach]
- **Negative**: [Costs or trade-offs]
- **Risks**: [Any new risks introduced]
```

#### Minimum Risk ADR Count

| P0/P1 Risks in Phase 0 | Minimum Risk ADRs Required |
|------------------------|---------------------------|
| 1-3 risks | All must have ADRs |
| 4-6 risks | All must have ADRs |
| 7+ risks | All P0, plus top 5 P1 by score |

**These Risk Mitigation ADRs are IN ADDITION TO the 5 mandatory technology ADRs.**

**Total ADR Requirement** = Technology ADRs (5 minimum) + Risk Mitigation ADRs (all P0/P1)

### Step 5: Create Component Diagrams (C4 Level 3)

**Output**: Component diagrams for critical containers

For complex containers:
1. Identify internal components
2. Define responsibilities
3. Show interactions

### Step 6: Specify NFRs

**Output**: NFR specification

See [nfr-checklist.reference.md](nfr-checklist.reference.md).

1. Performance targets
2. Scalability requirements
3. Security requirements
4. Reliability/availability
5. Monitoring requirements

### Step 7: Document Architecture

**Output**: Architecture document

Using [templates/architecture.template.md](templates/architecture.template.md).

## Self-Review Protocol

Execute these gates IN ORDER during self-review. Do not skip gates.

### Gate 1: Completeness Scan (BLOCKING)

Scan the ENTIRE artifact for placeholder patterns:

| Pattern | Found? | Action |
|---------|--------|--------|
| `_[` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[Continue` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TBD]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TODO]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `XXX` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| Empty sections | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |

**Gate 1 FAIL**: Return artifact for completion. Do not proceed to Gate 2.

### Gate 2: Count Validation (BLOCKING)

Verify stated counts match actual documented items:

| Item | Stated | Actual | Match? |
|------|--------|--------|--------|
| ADRs documented (per EXPECTED_ADR_COUNT marker) | ___ | ___ | ☐ |
| Technology ADRs (ADR-001 to ADR-005) | 5 | ___ | ☐ |
| Risk mitigation ADRs (all P0/P1) | ___ | ___ | ☐ |
| Components documented | ___ | ___ | ☐ |
| NFRs with measurable targets | ___ | ___ | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

### Gate 3: Quality Assessment

Only if Gates 1-2 pass, apply quality criteria from this skill's checklist.

### Score Calculation

| Gate 1 | Gate 2 | Max Score |
|--------|--------|-----------|
| FAIL | — | 0 |
| PASS | FAIL | 50 |
| PASS | PASS | 100 |

**Output format**: `Gate 1: [PASS/FAIL] | Gate 2: [PASS/FAIL] | Gate 3: [X]/100 | Final: [X]/100`

## Output

- Architecture document with C4 diagrams
- ADRs for key decisions
- NFR specification

## Quality Checklist

- [ ] C4 Context diagram complete
- [ ] C4 Container diagram complete
- [ ] Component diagrams for critical containers
- [ ] ADR for each major technology decision
- [ ] NFRs specified with measurable targets
- [ ] Security considerations documented