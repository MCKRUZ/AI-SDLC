# Validation Rules Reference

## Overview

Validation ensures Phase 1 artifacts are complete, consistent, and ready
for Phase 2 planning. This reference defines the rules for validating
each artifact type.

---

## Specification Validation Rules

### Completeness Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| SPEC-001 | All user types have personas | Count personas ≥ user types |
| SPEC-002 | All personas have stories | Every persona has ≥ 1 story |
| SPEC-003 | All stories have acceptance criteria | No story missing AC |
| SPEC-004 | All stories have INVEST score | Score recorded for each |
| SPEC-005 | Critical path requirements identified | Priority = Critical marked |
| SPEC-006 | Dependencies documented | Dependency section complete |
| SPEC-007 | Data requirements defined | Data entities listed |
| SPEC-008 | Integration requirements complete | All integrations specified |
| SPEC-009 | Error scenarios documented | Error handling per feature |
| SPEC-010 | Glossary provided | Terms defined |

### Quality Rules

| Rule ID | Rule | Threshold |
|---------|------|-----------|
| SPEC-Q01 | INVEST score minimum | ≥ 9 for all stories |
| SPEC-Q02 | Acceptance criteria testable | 100% pass test |
| SPEC-Q03 | Requirements atomic | 1 requirement per story |
| SPEC-Q04 | No ambiguous language | No "should", "might", "etc." |
| SPEC-Q05 | Quantified where possible | Numbers not "fast", "many" |

### Traceability Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| SPEC-T01 | Traced to Phase 0 | Every story → problem statement |
| SPEC-T02 | Priority justified | Priority linked to business need |
| SPEC-T03 | Constraints respected | No violation of Phase 0 constraints |

---

## Architecture Validation Rules

### Completeness Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| ARCH-001 | C4 Context diagram exists | Level 1 present |
| ARCH-002 | C4 Container diagram exists | Level 2 present |
| ARCH-003 | All containers have technology | Tech specified |
| ARCH-004 | All integrations shown | External systems documented |
| ARCH-005 | Data stores identified | All databases shown |
| ARCH-006 | Communication protocols specified | Arrows labeled |
| ARCH-007 | NFRs have architecture support | Each NFR addressed |
| ARCH-008 | Security architecture documented | AuthN/AuthZ shown |
| ARCH-009 | Deployment architecture documented | Environments defined |
| ARCH-010 | Component diagrams for complex containers | Level 3 where needed |

### Quality Rules

| Rule ID | Rule | Threshold |
|---------|------|-----------|
| ARCH-Q01 | ADR for major decisions | ≥ 1 ADR per technology choice |
| ARCH-Q02 | NFRs are measurable | All NFRs have targets |
| ARCH-Q03 | No single points of failure | Redundancy documented |
| ARCH-Q04 | Scalability approach defined | Scale strategy per tier |
| ARCH-Q05 | Security review complete | No open security concerns |

### Consistency Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| ARCH-C01 | Matches spec requirements | All FRs can be built |
| ARCH-C02 | NFRs from constitution | All constitution NFRs addressed |
| ARCH-C03 | Data model supports stories | Entities cover data needs |
| ARCH-C04 | API supports integrations | Endpoints match integration needs |

---

## PRD Validation Rules

### Completeness Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| PRD-001 | Vision statement present | Clear, inspiring vision |
| PRD-002 | Target users defined | User segments identified |
| PRD-003 | User personas documented | Detailed personas |
| PRD-004 | MVP scope clearly defined | Explicit in/out list |
| PRD-005 | Prioritization documented | Framework and scores |
| PRD-006 | Success metrics defined | Measurable outcomes |
| PRD-007 | Roadmap outlined | Beyond MVP phases |
| PRD-008 | Risks documented | Product risks identified |
| PRD-009 | Dependencies identified | External dependencies |
| PRD-010 | Go-to-market considerations | If applicable |

### Quality Rules

| Rule ID | Rule | Threshold |
|---------|------|-----------|
| PRD-Q01 | MVP is minimal | ≤ 10 features in MVP |
| PRD-Q02 | Success metrics are SMART | Specific, Measurable, etc. |
| PRD-Q03 | Prioritization consistent | Single framework used |
| PRD-Q04 | Timeline is realistic | Fits resource constraints |
| PRD-Q05 | Vision inspires | Team understands "why" |

### Alignment Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| PRD-A01 | Solves Phase 0 problem | Links to problem statement |
| PRD-A02 | Meets success criteria | Addresses Phase 0 criteria |
| PRD-A03 | Respects constraints | No constraint violations |
| PRD-A04 | Features in spec | All MVP features have stories |

---

## Constitution Validation Rules

### Completeness Rules

| Rule ID | Rule | Check |
|---------|------|-------|
| CON-001 | Values defined | Core values listed |
| CON-002 | Values prioritized | Stack rank exists |
| CON-003 | Non-negotiables listed | ≥ 3 non-negotiables |
| CON-004 | Decision frameworks present | ≥ 3 frameworks |
| CON-005 | Technical constraints documented | Stack, integrations |
| CON-006 | Resource constraints documented | Team, budget, time |
| CON-007 | Governance defined | Decision rights clear |
| CON-008 | Anti-patterns documented | What to avoid |
| CON-009 | Definition of Done present | Quality criteria |
| CON-010 | Amendment process defined | How to change |

### Quality Rules

| Rule ID | Rule | Threshold |
|---------|------|-----------|
| CON-Q01 | Values are actionable | Each has decision impact |
| CON-Q02 | Constraints are specific | No vague statements |
| CON-Q03 | Governance is clear | No ambiguity in decisions |
| CON-Q04 | Team agrees | Sign-off from team |

---

## Cross-Artifact Validation Rules

### Consistency Rules

| Rule ID | Artifacts | Rule | Check |
|---------|-----------|------|-------|
| CROSS-001 | Spec ↔ PRD | Features match | All PRD features in spec |
| CROSS-002 | Spec ↔ Arch | Requirements buildable | Architecture supports all FRs |
| CROSS-003 | Arch ↔ Constitution | Standards met | Architecture meets NFRs |
| CROSS-004 | PRD ↔ Phase 0 | Problem solved | PRD addresses root cause |
| CROSS-005 | All ↔ Constitution | Constraints respected | No violations |
| CROSS-006 | Spec ↔ Data Model | Data covered | All data requirements have entities |
| CROSS-007 | Spec ↔ API | Endpoints exist | All integration needs covered |

### Terminology Consistency

| Rule ID | Rule | Check |
|---------|------|-------|
| TERM-001 | Same terms everywhere | No synonyms for same concept |
| TERM-002 | Glossary terms used | Terms match glossary |
| TERM-003 | Entity names match | Data model = Spec = API |
| TERM-004 | User roles match | Same role names across docs |

---

## Validation Process

### Step 1: Individual Artifact Validation

For each artifact:
1. Run completeness rules
2. Run quality rules
3. Run specific rules for artifact type
4. Document findings

### Step 2: Cross-Artifact Validation

1. Check consistency between artifact pairs
2. Verify terminology consistency
3. Validate traceability chains
4. Document inconsistencies

### Step 3: Traceability Validation

```
Phase 0                Phase 1
─────────────────────────────────────────
Problem Statement  →   User Stories
Success Criteria   →   Success Metrics
Constraints        →   Constitution Constraints
Risks              →   Architecture decisions
Stakeholder needs  →   Features/PRD
```

### Step 4: Quality Gate Review

| Gate | Criteria | Pass Threshold |
|------|----------|----------------|
| Completeness | All required sections | 100% |
| Quality | Quality rules pass | 90% |
| Consistency | No contradictions | 0 critical |
| Traceability | Links verified | 100% |

---

## Validation Checklist

### Quick Validation (30 min)

- [ ] All artifacts exist
- [ ] Major sections complete
- [ ] No obvious contradictions
- [ ] MVP clearly defined
- [ ] INVEST scores recorded

### Full Validation (2-4 hours)

- [ ] All completeness rules pass
- [ ] All quality rules pass
- [ ] Cross-artifact consistency verified
- [ ] Traceability matrix complete
- [ ] Terminology consistent
- [ ] Stakeholder approval obtained

---

## Common Validation Failures

| Failure | Symptom | Fix |
|---------|---------|-----|
| Missing AC | Stories without criteria | Add testable criteria |
| Vague NFRs | "Fast", "scalable" | Add specific targets |
| Orphan features | PRD feature not in spec | Add stories or remove |
| Terminology drift | Different names for same thing | Standardize in glossary |
| Missing traceability | Can't trace to problem | Add requirement IDs |
| Constraint violation | Design violates limits | Redesign or update constraint |
