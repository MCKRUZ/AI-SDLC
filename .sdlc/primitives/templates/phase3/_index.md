# Phase 3 Templates - Implementation

This directory contains templates for **Phase 3: Implementation** artifacts.

## Purpose

Phase 3 templates support sprint execution, story management, and release delivery.

## Templates

| Template | File | Purpose |
|----------|------|---------|
| **Story File** | `story-file.template.md` | Self-contained context carrier for implementation |
| **Sprint Summary** | `sprint-summary.template.md` | End-of-sprint summary and metrics |
| **Release Notes** | `release-notes.template.md` | User-facing release documentation |

## Story File Template

The **story file** is the core artifact of Phase 3. It contains:

- User story with acceptance criteria
- Sharded architecture context (NOT full documents)
- Implementation guidance
- Test guidance
- Dependencies
- Lifecycle notes (SM → Dev → QA)

### Key Principles

1. **Self-Contained**: Developer loads ONLY the story file
2. **Sharded Context**: Only relevant architecture sections included
3. **Living Document**: Notes accumulate through lifecycle
4. **Traceable**: Links back to source artifacts

### Size Targets

| Section | Target | Maximum |
|---------|--------|---------|
| Architecture Context | 50-100 lines | 200 lines |
| Implementation Guidance | 20-50 lines | 100 lines |
| Test Guidance | 10-30 lines | 50 lines |
| **Total Story File** | 200-400 lines | 600 lines |

## Related Files

- **Agents**: `.sdlc/primitives/agents/phase3/`
- **Workflows**: `.sdlc/primitives/workflows/phase3/`
- **Config**: `.sdlc/config/phase3.config.md`
