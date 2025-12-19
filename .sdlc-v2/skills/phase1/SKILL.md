---
name: phase1
description: >
  Phase 1 Specification & Design. Activities for requirements analysis,
  architecture design, product definition, and validation. Transforms
  validated problems into detailed specifications. Use after Phase 0
  completion.
---
# Phase 1: Specification & Design

## Purpose

Transform validated problem statements into detailed specifications
that guide implementation.

## Activities

| Activity | When to Use | Location |
|----------|-------------|----------|
| Requirements Analysis | Writing specs and user stories | [requirements-analysis-activity/](requirements-analysis-activity/SKILL.md) |
| Architecture Design | Designing system architecture | [architecture-design-activity/](architecture-design-activity/SKILL.md) |
| Product Definition | Creating PRD and defining MVP | [product-definition-activity/](product-definition-activity/SKILL.md) |
| Constitution Definition | Establishing project values | [constitution-definition-activity/](constitution-definition-activity/SKILL.md) |
| Specification Validation | Validating all Phase 1 artifacts | [specification-validation-activity/](specification-validation-activity/SKILL.md) |

## Phase Flow
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ Requirements │     │ Architecture │     │   Product    │
│   Analysis   │────▶│    Design    │────▶│  Definition  │
└──────────────┘     └──────────────┘     └──────────────┘
│                   │                     │
└───────────────────┴──────────────┬──────┘
▼
┌──────────────────────┐
│    Constitution      │
│     Definition       │
└──────────────────────┘
│
▼
┌──────────────────────┐
│   Specification      │
│    Validation        │
└──────────────────────┘

## Entry Criteria

- Phase 0 complete with validated problem statement
- Feasibility confirmed
- Stakeholder alignment achieved

## Exit Criteria

- [ ] Technical specification complete with user stories
- [ ] Architecture documented with ADRs
- [ ] PRD complete with MVP defined
- [ ] Constitution established
- [ ] All artifacts validated
- [ ] Stakeholder sign-off obtained