# Pull Request: [Title]

## PR Information

| Field | Value |
|-------|-------|
| Story | US-XXX |
| Type | Feature / Bug Fix / Refactor / Docs / Chore |
| Priority | P1 / P2 / P3 |

---

## Summary

[2-3 sentence summary of what this PR does and why]

---

## Related Items

- **Story**: [US-XXX - Story Title](link-to-story)
- **Design**: [Link to design/figma if applicable]
- **Related PRs**: #XXX, #YYY

---

## Changes Made

### What Changed

- [Change 1 - e.g., "Added user authentication endpoint"]
- [Change 2 - e.g., "Created UserService with login/logout methods"]
- [Change 3 - e.g., "Added JWT token validation middleware"]

### Files Changed

| File | Change Type | Description |
|------|-------------|-------------|
| `src/auth/AuthController.ts` | Added | New auth endpoints |
| `src/services/UserService.ts` | Modified | Added login method |
| `src/middleware/auth.ts` | Added | JWT validation |

---

## Implementation Details

### Approach

[Explain the technical approach taken and why]

### Key Decisions

| Decision | Rationale |
|----------|-----------|
| [Decision 1] | [Why this approach] |
| [Decision 2] | [Why this approach] |

### Alternatives Considered

[What other approaches were considered and why they were rejected]

---

## Testing

### Automated Tests

- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] E2E tests added/updated

**Test Coverage**: [X]% → [Y]%

### Manual Testing

**Tested Scenarios**:

| Scenario | Result |
|----------|--------|
| [Happy path scenario] | ✅ Pass |
| [Edge case scenario] | ✅ Pass |
| [Error scenario] | ✅ Pass |

### Test Instructions

To test this PR locally:

1. Checkout this branch: `git checkout [branch-name]`
2. Install dependencies: `npm install`
3. Run locally: `npm run dev`
4. [Specific test steps]

---

## Checklist

### Code Quality

- [ ] Code follows project coding standards
- [ ] No console.log or debugging code left
- [ ] No commented-out code
- [ ] Functions/methods are appropriately sized
- [ ] Variable/function names are clear and descriptive

### Testing

- [ ] Unit tests cover new functionality
- [ ] All tests pass locally
- [ ] Manual testing completed
- [ ] Edge cases considered and tested

### Documentation

- [ ] Code comments added where necessary
- [ ] README updated if needed
- [ ] API documentation updated if needed
- [ ] Changelog entry added if needed

### Security

- [ ] No secrets or credentials in code
- [ ] Input validation implemented
- [ ] No SQL injection vulnerabilities
- [ ] Authentication/authorization properly checked

### Performance

- [ ] No N+1 query issues
- [ ] No unnecessary database calls
- [ ] Large data sets handled efficiently
- [ ] No memory leaks introduced

---

## Screenshots

[If UI changes, include before/after screenshots]

### Before

![Before](path/to/before.png)

### After

![After](path/to/after.png)

---

## Breaking Changes

**Has Breaking Changes**: Yes / No

[If yes, describe what breaks and how to migrate]

---

## Deployment Notes

### Configuration Changes

| Setting | Change | Action Required |
|---------|--------|-----------------|
| [Setting] | [Change] | [Action] |

### Database Migrations

- [ ] Migration required: [Description]
- [ ] Migration is backward compatible
- [ ] Rollback migration tested

### Feature Flags

| Flag | State | Purpose |
|------|-------|---------|
| [Flag name] | [On/Off] | [Purpose] |

---

## Rollback Plan

If issues are found after deployment:

1. [Rollback step 1]
2. [Rollback step 2]

---

## Review Notes

### Areas Needing Extra Attention

- [File/area that needs careful review]
- [Complex logic that should be scrutinized]

### Questions for Reviewers

- [Question 1]
- [Question 2]

---

## Definition of Done

- [ ] All acceptance criteria met
- [ ] Code reviewed and approved
- [ ] All tests passing
- [ ] No critical/high bugs
- [ ] Documentation updated
- [ ] Ready for merge

---

*PR created: [Date]*
