# Phase 3 Agents - Implementation

This directory contains agent instructions for **Phase 3: Implementation**.

## Purpose

Phase 3 agents execute sprints, implement features, and deliver working software.

## Agents

| Agent | File | Purpose |
|-------|------|---------|
| **Scrum Master** | `scrum-master.instructions.md` | Creates story files, manages sprint execution, facilitates handoffs |
| **Developer** | `developer.instructions.md` | Implements features based on story files |
| **QA Engineer** | `qa-engineer.instructions.md` | Validates implementations, executes tests, provides signoff |

## Key Concepts

### Story Files
Phase 3 uses **story files** as self-contained context carriers. The Scrum Master creates them from Phase 2 task breakdowns, sharding relevant architecture context. Developers load ONE story file to implement.

### Story Lifecycle
```
Draft → Ready → In Progress → In Review → Done
```

Each agent adds their notes to the story file as it progresses.

## Related Files

- **Templates**: `.sdlc/primitives/templates/phase3/`
- **Workflows**: `.sdlc/primitives/workflows/phase3/`
- **Config**: `.sdlc/config/phase3.config.md`
- **Phase Definition**: `phases/phase3.json`

## When to Use

Load Phase 3 agents after Phase 2 is complete and:
- Task breakdown exists
- Sprint plan is approved
- Repository is set up
- CI/CD is functional
- Team is ready
