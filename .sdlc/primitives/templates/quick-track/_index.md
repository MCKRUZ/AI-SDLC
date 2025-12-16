# Quick Track Templates

This directory contains templates for **Quick Track** projects.

## Purpose

Quick Track is designed for well-understood, low-risk changes that don't require formal discovery or extensive planning. These templates provide the minimum documentation needed for small projects.

## When to Use Quick Track

- Effort < 2 weeks
- Requirements are crystal clear
- No stakeholder alignment needed
- Low technical risk
- Bug fixes, small features, well-understood changes

## Templates

| Template | File | Required | Purpose |
|----------|------|----------|---------|
| **Tech Spec Lite** | `tech-spec-lite.template.md` | ✅ Yes | Lightweight technical specification |
| **Rollback Plan** | `rollback-plan.template.md` | ⚠️ If production change | Rollback strategy for production deployments |

## Tech Spec Lite

A streamlined technical specification that captures:
- Problem summary (2-3 sentences)
- Proposed solution (bullet points)
- Implementation approach
- Files/components affected
- Testing approach
- Risks/concerns
- Effort estimate

**Target length**: 1-2 pages

## Rollback Plan

For production changes, document:
- Rollback triggers
- Step-by-step rollback procedure
- Contacts for emergencies

## Quick Track Workflow

```
Problem → Tech Spec (1-2 hrs) → Review (30 min) → Implementation
```

Total planning time: 1-4 hours

## Escalation

If during Quick Track you discover:
- Requirements aren't as clear as expected
- Multiple stakeholders have different views
- Technical complexity is higher than anticipated
- Timeline pressure increases significantly

→ Consider escalating to **Standard Track**

## Related Files

- **Config**: `.sdlc/config/quick-track.config.md`
- **Scale Selection**: `.sdlc/primitives/workflows/scale-selection.workflow.prompt.md`
