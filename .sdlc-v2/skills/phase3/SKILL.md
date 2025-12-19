---
name: phase3
description: >
  Phase 3 Implementation. Activities for sprint execution, development,
  and QA testing. Executes planned sprints and delivers working software.
  Use during active development.
---

# Phase 3: Implementation

## Purpose

Execute sprints to deliver working software according to specifications.

## Activities

| Activity         | When to Use                              | Location                                                         |
| ---------------- | ---------------------------------------- | ---------------------------------------------------------------- |
| Sprint Execution | Running sprints, facilitating ceremonies | [sprint-execution-activity/](sprint-execution-activity/SKILL.md) |
| Development      | Writing code, creating PRs               | [development-activity/](development-activity/SKILL.md)           |
| QA Testing       | Testing features, reporting bugs         | [qa-testing-activity/](qa-testing-activity/SKILL.md)             |

## Phase Flow

For each sprint:
┌─────────────────────────────────────────────────────────┐
│ Sprint Execution │
│ ┌─────────────┐ ┌─────────────┐ ┌───────────┐ │
│ │ Development │────▶│ QA Testing │────▶│ Review │ │
│ └─────────────┘ └─────────────┘ └───────────┘ │
└─────────────────────────────────────────────────────────┘
│ │
└────────────────────────────────────────┘
Repeat until done

## Entry Criteria

- Phase 2 complete
- Sprint plans approved
- Infrastructure ready
- Team onboarded

## Exit Criteria

- [ ] All MVP features implemented
- [ ] Tests passing
- [ ] Quality gates met
- [ ] Documentation complete
- [ ] Deployment successful
