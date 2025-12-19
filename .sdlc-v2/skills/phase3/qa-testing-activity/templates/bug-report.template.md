# Bug Report: [BUG-XXX]

## Bug Information

| Field | Value |
|-------|-------|
| Bug ID | BUG-XXX |
| Title | [Clear, descriptive title] |
| Severity | Critical / High / Medium / Low |
| Priority | P1 / P2 / P3 / P4 |
| Status | Open / In Progress / Fixed / Verified / Closed |
| Reporter | [Name] |
| Assignee | [Name] |
| Found In | v[X.Y.Z] / Sprint [N] |
| Found Date | [YYYY-MM-DD] |

---

## Related Items

| Relationship | ID | Title |
|--------------|-----|-------|
| Story | US-XXX | [Story title] |
| Test Case | TC-XXX | [Test case title] |
| Related Bug | BUG-YYY | [Related bug title] |

---

## Summary

[One paragraph summary of the bug - what's wrong and its impact]

---

## Severity Justification

**Severity**: [Critical / High / Medium / Low]

**Justification**: [Why this severity level?]

### Severity Guidelines

- **Critical**: System crash, data loss, security vulnerability, no workaround
- **High**: Major feature broken, significant user impact, workaround is difficult
- **Medium**: Feature partially broken, moderate impact, workaround exists
- **Low**: Minor issue, cosmetic, edge case, easy workaround

---

## Steps to Reproduce

### Environment

| Component | Value |
|-----------|-------|
| Environment | Dev / Staging / Production |
| Browser | [Browser and version] |
| OS | [Operating system] |
| Device | Desktop / Mobile / Tablet |
| User Role | [Role/permissions] |
| Build/Version | [Version number] |

### Reproduction Steps

1. [Prerequisite/Setup - e.g., "Log in as admin user"]
2. [Step 1 - e.g., "Navigate to Settings > Users"]
3. [Step 2 - e.g., "Click 'Add New User' button"]
4. [Step 3 - e.g., "Enter email: test@example.com"]
5. [Step 4 - e.g., "Click 'Save'"]

**Reproduction Rate**: Always / Sometimes ([X]%) / Intermittent

---

## Expected vs Actual Behavior

### Expected Behavior

[What should happen when following the steps above]

### Actual Behavior

[What actually happens - be specific]

---

## Evidence

### Screenshots

[Attach screenshots showing the issue]

![Screenshot description](path/to/screenshot.png)

### Error Messages

```
[Paste any error messages, console errors, or log entries]
```

### Logs

```
[Relevant log entries]
```

### Video

[Link to screen recording if helpful]

---

## Impact Analysis

### Users Affected

- **User Types**: [Which user roles are affected]
- **Scope**: All users / Subset ([describe]) / Single user
- **Frequency**: [How often users encounter this]

### Business Impact

[Describe business impact - lost revenue, blocked workflows, reputation, etc.]

### Workaround

**Workaround Available**: Yes / No

**Workaround Steps**:
1. [Step 1]
2. [Step 2]

**Workaround Limitations**: [Any limitations of the workaround]

---

## Technical Analysis

### Suspected Root Cause

[Developer's analysis of what might be causing the issue]

### Affected Components

- [ ] Frontend - [Specific area]
- [ ] Backend - [Specific service/endpoint]
- [ ] Database - [Specific table/query]
- [ ] Third-party - [Service name]
- [ ] Infrastructure - [Component]

### Related Code

```
[Relevant code snippets or file references]
```

**Files to Investigate**:
- `src/...`
- `api/...`

---

## Fix Information

### Fix Description

[Description of the fix implemented]

### Code Changes

**PR Link**: [URL to pull request]

**Files Changed**:
- `file1.ts` - [Change description]
- `file2.ts` - [Change description]

### Fixed In

- **Version**: v[X.Y.Z]
- **Sprint**: Sprint [N]
- **Date**: [YYYY-MM-DD]

---

## Verification

### Verification Steps

1. [Step to verify fix]
2. [Step to verify fix]
3. [Confirm expected behavior]

### Verification Results

**Verified By**: [Name]  
**Verified Date**: [YYYY-MM-DD]  
**Verified In**: [Environment]  
**Result**: ✅ Fixed / ❌ Not Fixed / ⚠️ Partially Fixed

### Regression Testing

- [ ] Related functionality tested
- [ ] No new issues introduced
- [ ] Automated tests added/updated

---

## History

| Date | Action | By | Notes |
|------|--------|-----|-------|
| [Date] | Created | [Name] | Initial report |
| [Date] | Assigned | [Name] | Assigned to [Developer] |
| [Date] | In Progress | [Name] | Started investigation |
| [Date] | Fixed | [Name] | PR #XXX merged |
| [Date] | Verified | [Name] | Verified in staging |
| [Date] | Closed | [Name] | Deployed to production |

---

*Last updated: [Date]*
