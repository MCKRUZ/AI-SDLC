# Bug Reporting Reference

## Overview

Good bug reports enable quick diagnosis and resolution. A well-written
bug report includes everything needed to reproduce and understand the issue.

---

## Essential Information

### Minimum Required

| Field | Why It Matters |
|-------|----------------|
| Title | Quick identification |
| Steps to reproduce | How to see the bug |
| Expected behavior | What should happen |
| Actual behavior | What actually happens |
| Environment | Where it occurs |

---

## Writing Good Titles

### Pattern

`[Area] Brief description of the problem`

### Examples

| Bad | Good |
|-----|------|
| "It doesn't work" | "[Login] Error 500 when submitting with empty email" |
| "Bug in checkout" | "[Checkout] Tax not calculated for international orders" |
| "Crash" | "[iOS] App crashes when opening camera on iPhone 12" |

---

## Steps to Reproduce

### Guidelines

1. Start from a known state (e.g., "Logged in as admin")
2. Be specific (e.g., "Click the blue 'Save' button", not "Click save")
3. Include test data used
4. Number each step
5. Indicate which step causes the issue

### Example

```markdown
1. Log in as test@example.com / password123
2. Navigate to Settings > Profile
3. Change email to "invalid-email" (no @ symbol)
4. Click "Save Changes"

**Result**: Error 500 appears
**Expected**: Validation error "Invalid email format"
```

---

## Environment Details

### Web Applications

| Info | Example |
|------|---------|
| Browser | Chrome 120.0.6099.109 |
| OS | macOS 14.2 |
| Screen size | 1920x1080 |
| URL | https://staging.example.com/profile |

### Mobile Applications

| Info | Example |
|------|---------|
| Device | iPhone 15 Pro |
| OS Version | iOS 17.2 |
| App Version | 2.3.1 (build 456) |
| Network | WiFi |

---

## Severity Guidelines

| Severity | Definition | Examples |
|----------|------------|----------|
| Critical | System unusable, data loss | Crash, security breach, data corruption |
| High | Major feature broken, no workaround | Cannot checkout, cannot login |
| Medium | Feature broken, workaround exists | Export fails but can copy/paste |
| Low | Minor issue, cosmetic | Typo, alignment off by 1px |

---

## Evidence

### Screenshots

- Capture the entire relevant area
- Highlight the problem if not obvious
- Include any error messages
- Show before/after if relevant

### Console Errors

```javascript
// Copy from browser console
Uncaught TypeError: Cannot read property 'id' of undefined
    at UserService.getUser (user-service.js:45)
    at async ProfilePage.load (profile.js:23)
```

### Network Requests

```
POST /api/users/123
Status: 500
Response: {"error": "Internal server error", "code": "DB_CONNECTION_FAILED"}
```

### Logs

```
[2024-01-15 10:23:45] ERROR: Failed to process payment
    Transaction ID: txn_abc123
    User ID: usr_456
    Error: Card declined
```

---

## Reproducibility

| Rate | Meaning | Action |
|------|---------|--------|
| Always (100%) | Happens every time | Straightforward to fix |
| Often (50-99%) | Happens frequently | May need more investigation |
| Sometimes (10-50%) | Intermittent | Note conditions when it occurs |
| Rarely (<10%) | Hard to reproduce | Provide as much detail as possible |

---

## What NOT to Include

- Opinions about whose fault it is
- Speculation about the cause (unless helpful)
- Multiple unrelated bugs in one report
- Excessive screenshots of unrelated screens
- Personal information or production data

---

## Quick Reference

**Good bug report** = 
Clear title + 
Numbered repro steps + 
Expected vs actual + 
Environment + 
Evidence

**Ask yourself**: Could a developer who has never seen this bug reproduce it from my report?
