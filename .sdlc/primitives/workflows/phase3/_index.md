# Phase 3 Workflows - Implementation

This directory contains workflow prompts for **Phase 3: Implementation**.

## Purpose

Phase 3 workflows orchestrate sprint execution, story management, and release delivery.

## Workflows

| Workflow | File | Purpose |
|----------|------|---------|
| **Story Lifecycle** | `story-lifecycle.workflow.prompt.md` | Manages story flow from creation to completion |
| **Sprint Execution** | `sprint-execution.workflow.prompt.md` | Guides daily sprint activities |
| **Release** | `release-workflow.prompt.md` | Orchestrates release preparation and delivery |

## Story Lifecycle Workflow

The core Phase 3 workflow. Defines how stories progress:

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│  Draft   │───▶│  Ready   │───▶│InProgress│───▶│ InReview │───▶│   Done   │
└──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘
     │               │               │               │               │
     ▼               ▼               ▼               ▼               ▼
SM creates      SM reviews     Dev implements   Code review     Merged,
story file      & prioritizes  & adds notes     + QA testing    archived
```

### Agent Handoffs

| From | To | Trigger | What's Passed |
|------|----|---------|---------------|
| SM | Dev | Sprint starts | Story file (Ready) |
| Dev | Reviewer | PR created | Story file + code |
| Reviewer | QA | PR approved | Story file |
| QA | SM | QA approved | Story file (with notes) |

## Key Principles

1. **Story File is Single Source of Truth**
2. **Notes Accumulate, Never Delete**
3. **Sharding Prevents Context Bloat**
4. **Clear Status Transitions**

## Related Files

- **Agents**: `.sdlc/primitives/agents/phase3/`
- **Templates**: `.sdlc/primitives/templates/phase3/`
- **Config**: `.sdlc/config/phase3.config.md`
- **Phase Definition**: `phases/phase3.json`
