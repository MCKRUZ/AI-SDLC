---
name: architecture-design-activity
activity_type: creation
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

**NOTE**: These are MINIMUM counts. Actual ADR count should be driven by:
1. Number of P0/P1 risks requiring architectural mitigation
2. Number of major technology selections beyond the 5 mandatory ones
3. Number of quality attribute trade-offs documented
4. Number of conditional technologies used

**Current Project Complexity**: [Assess from Phase 0]
**Minimum Required**: [From table above]
**Actual ADR Count**: [Count documented ADRs]

**Validation**: ADR count ≥ Minimum AND all P0/P1 risks covered

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

**These Risk Mitigation ADRs are IN ADDITION TO technology and architectural pattern ADRs.**

**Total ADR Requirement** = Technology ADRs (one per major choice) + Architectural Pattern ADR + Risk Mitigation ADRs (all P0/P1)

**Minimum Total**: 5 ADRs, but actual count should be driven by:
- Number of P0/P1 risks from Phase 0
- Number of major technology selections
- Number of quality attribute trade-offs

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
| Components documented | ___ | ___ | ☐ |
| NFRs with measurable targets | ___ | ___ | ☐ |

**ADR Coverage Validation** (instead of fixed count):

| Requirement | Check | Found? |
|-------------|-------|--------|
| ADR for each P0 risk | Cross-reference feasibility report | ☐ |
| ADR for each P1 risk | Cross-reference feasibility report | ☐ |
| ADR for primary technology choices | At least: language, framework, database, cloud | ☐ |
| ADR for architectural pattern | e.g., microservices, monolith, serverless | ☐ |
| Minimum 5 ADRs total | Count actual ADRs | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

**ADR Scoring:**
- Missing P0 risk ADR: -20 points (BLOCKING if any missing)
- Missing P1 risk ADR: -10 points each
- Below minimum 5 ADRs: -15 points
- Missing primary technology ADR: -10 points
- Missing architectural pattern ADR: -10 points

**Count Resolution Rule** (if mismatch persists after iteration 2):
1. If actual count < stated count by MORE than 50%: Generate additional items to reach stated count
2. If actual count < stated count by LESS than 50%: Update stated count to match actual
3. If actual count > stated count: Update stated count to match actual
4. After resolution, re-verify counts match before proceeding to Gate 3

Example:
- Stated: 12, Actual: 5 (58% gap) → Generate 7 more items
- Stated: 12, Actual: 10 (17% gap) → Change stated to 10
- Stated: 8, Actual: 12 → Change stated to 12

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