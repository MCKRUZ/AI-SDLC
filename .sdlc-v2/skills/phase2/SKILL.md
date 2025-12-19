---
name: phase2
description: >
  Phase 2 Planning & Setup. Activities for task planning, sprint planning,
  infrastructure setup, and quality planning. Transforms specifications
  into actionable work plans. Use after Phase 1 completion.
---

# Phase 2: Planning & Setup

## Purpose

Transform specifications into actionable plans and prepare infrastructure
for implementation.

## Activities

| Activity             | When to Use                           | Location                                                                 |
| -------------------- | ------------------------------------- | ------------------------------------------------------------------------ |
| Task Planning        | Breaking down work, estimating        | [task-planning-activity/](task-planning-activity/SKILL.md)               |
| Sprint Planning      | Planning sprints, allocating work     | [sprint-planning-activity/](sprint-planning-activity/SKILL.md)           |
| Infrastructure Setup | Setting up repos, CI/CD, environments | [infrastructure-setup-activity/](infrastructure-setup-activity/SKILL.md) |
| Quality Planning     | Defining test strategy                | [quality-planning-activity/](quality-planning-activity/SKILL.md)         |

## Phase Flow

┌─────────────────┐ ┌─────────────────┐
│ Task Planning │────▶│ Sprint Planning │
└─────────────────┘ └─────────────────┘
│ │
▼ ▼
┌─────────────────┐ ┌─────────────────┐
│ Infrastructure │ │ Quality │
│ Setup │ │ Planning │
└─────────────────┘ └─────────────────┘

## Entry Criteria

- Phase 1 complete with validated specs
- Architecture approved
- PRD with MVP defined

## Exit Criteria

- [ ] Tasks decomposed with estimates
- [ ] Dependencies mapped
- [ ] Sprints planned
- [ ] Repository created
- [ ] CI/CD configured
- [ ] Test plan complete
- [ ] Team ready to execute
