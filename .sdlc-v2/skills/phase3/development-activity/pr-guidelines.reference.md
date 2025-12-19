# PR Guidelines Reference

## Overview

Good pull requests are easy to review, well-tested, and clearly documented.
These guidelines help ensure quality code gets merged efficiently.

---

## PR Size Guidelines

### Ideal Size

| Metric | Guideline |
|--------|-----------|
| Lines changed | 200-400 |
| Files changed | 5-10 |
| Review time | 30-60 minutes |

### If Too Large

- Split into multiple PRs
- Use feature flags for partial work
- Create stacked PRs (base → feature → enhancement)

---

## PR Checklist

### Before Creating

- [ ] Code compiles and runs locally
- [ ] All tests pass
- [ ] Linting passes with no warnings
- [ ] Self-reviewed all changes
- [ ] Removed debug code and console.logs
- [ ] Updated documentation if needed

### PR Description

- [ ] Links to related story/ticket
- [ ] Describes what changed and why
- [ ] Lists testing performed
- [ ] Notes any breaking changes
- [ ] Screenshots for UI changes

---

## Review Process

### For Authors

1. **Create draft PR early** - Get early feedback
2. **Request specific reviewers** - Those familiar with the area
3. **Respond promptly** - Don't let PRs go stale
4. **Be open to feedback** - Reviews improve code

### For Reviewers

1. **Review within 24 hours** - Keep flow moving
2. **Be constructive** - Suggest improvements, not just problems
3. **Approve when ready** - Don't block on nitpicks
4. **Ask questions** - If something is unclear, ask

---

## Code Review Focus Areas

### Must Check

| Area | What to Look For |
|------|------------------|
| Correctness | Does it do what it should? |
| Tests | Are changes tested? |
| Security | Any vulnerabilities? |
| Performance | Any obvious issues? |

### Should Check

| Area | What to Look For |
|------|------------------|
| Design | Is the approach sound? |
| Readability | Easy to understand? |
| Maintainability | Will this be easy to change? |
| Consistency | Matches existing patterns? |

### Nice to Check

| Area | What to Look For |
|------|------------------|
| Style | Minor formatting issues |
| Naming | Could names be clearer? |
| Comments | Missing or excessive? |

---

## Comment Conventions

### Prefixes

| Prefix | Meaning | Blocks Merge? |
|--------|---------|---------------|
| `blocker:` | Must fix before merge | Yes |
| `suggestion:` | Consider this improvement | No |
| `nit:` | Minor/optional | No |
| `question:` | Need clarification | Maybe |

### Examples

```
blocker: This will cause a null pointer exception when user is undefined.

suggestion: Consider extracting this into a helper function for reusability.

nit: Prefer `const` over `let` here since the value doesn't change.

question: Why did you choose to use recursion here instead of iteration?
```

---

## Merging

### Merge Requirements

- [ ] At least 1 approval (2 for critical paths)
- [ ] All CI checks pass
- [ ] No unresolved blocker comments
- [ ] Branch is up to date with main

### Merge Strategy

| Strategy | When to Use |
|----------|-------------|
| Squash | Most PRs (clean history) |
| Merge | When commit history is important |
| Rebase | Linear history preference |

### After Merge

- Delete feature branch
- Verify deployment (if auto-deploy)
- Close related tickets
- Notify stakeholders if needed

---

## Quick Reference

**Good PR** = Small + Tested + Documented + Focused

**Review in 24 hours** - Keep momentum

**Use prefixes** - `blocker:`, `suggestion:`, `nit:`, `question:`
