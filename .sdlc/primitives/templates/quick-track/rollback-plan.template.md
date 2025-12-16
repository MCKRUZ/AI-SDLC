# Rollback Plan Template

**Version**: 1.0  
**Purpose**: Document rollback strategy for Quick Track production changes  
**Location**: `.sdlc/primitives/templates/quick-track/rollback-plan.template.md`

---

## When to Use

Use this template for **Quick Track** projects that:
- Deploy to production
- Modify existing functionality
- Could impact users if something goes wrong

This is an **optional** artifact for Quick Track but **recommended** for any production change.

---

## Template

```markdown
# Rollback Plan

**Project/Change**: [Brief description]  
**Date**: [YYYY-MM-DD]  
**Author**: [Name]  
**Related Tech Spec**: [Link to tech-spec-lite.md]

---

## Change Summary

**What's changing**:
[1-2 sentences describing the change]

**Affected systems/components**:
- [Component 1]
- [Component 2]

**Deployment method**:
- [ ] Feature flag
- [ ] Blue/green deployment
- [ ] Rolling deployment
- [ ] Direct deployment
- [ ] Database migration
- [ ] Other: [Specify]

---

## Pre-Deployment Checklist

Before deploying, verify:

- [ ] Backup of affected database tables (if applicable)
- [ ] Current configuration saved
- [ ] Rollback steps tested in staging (if applicable)
- [ ] Monitoring/alerting in place
- [ ] Communication sent to stakeholders
- [ ] On-call engineer aware of deployment

---

## Rollback Triggers

**Rollback immediately if**:
- [ ] Error rate exceeds [X]% (baseline: [Y]%)
- [ ] Response time exceeds [X]ms (baseline: [Y]ms)
- [ ] [Critical functionality] is broken
- [ ] [X] or more user complaints received
- [ ] [Other specific trigger]

**Rollback decision owner**: [Name/Role]

---

## Rollback Steps

### Option A: Feature Flag (Preferred if available)

```bash
# Disable feature flag
[Command to disable flag, e.g.:]
# az appconfig feature disable --name "feature-name" --connection-string $CONN
```

**Time to rollback**: ~1 minute  
**User impact during rollback**: None (instant)

---

### Option B: Revert Deployment

**Step 1**: Identify previous version
```bash
# Get previous deployment version
[Command to list deployments]
```

**Step 2**: Redeploy previous version
```bash
# Redeploy
[Deployment command with previous version]
```

**Step 3**: Verify rollback
```bash
# Health check
[Command to verify service health]
```

**Time to rollback**: ~[X] minutes  
**User impact during rollback**: [Brief description]

---

### Option C: Database Rollback (If applicable)

⚠️ **Warning**: Database rollbacks can cause data loss. Proceed carefully.

**Step 1**: Stop application traffic
```bash
[Command to stop traffic or enable maintenance mode]
```

**Step 2**: Restore database
```bash
# Restore from backup
[Database restore command]
```

**Step 3**: Redeploy previous application version
```bash
[Deployment command]
```

**Step 4**: Resume traffic
```bash
[Command to resume traffic]
```

**Time to rollback**: ~[X] minutes  
**User impact during rollback**: [Full outage / degraded service]  
**Data impact**: [Any data created after backup will be lost]

---

## Post-Rollback Actions

After rolling back:

1. [ ] Verify system is functioning normally
2. [ ] Check error rates returned to baseline
3. [ ] Notify stakeholders of rollback
4. [ ] Create incident ticket: [Link]
5. [ ] Document root cause
6. [ ] Plan fix before re-attempting deployment

---

## Contacts

| Role | Name | Contact |
|------|------|---------|
| Deployment Owner | [Name] | [Phone/Slack] |
| On-Call Engineer | [Name] | [Phone/Slack] |
| Database Admin | [Name] | [Phone/Slack] |
| Product Owner | [Name] | [Phone/Slack] |

---

## Notes

[Any additional context, known issues, or special considerations]
```

---

## Quick Reference Card

For emergency reference during incidents:

```
┌─────────────────────────────────────────────────────────────────┐
│                    ROLLBACK QUICK REFERENCE                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ROLLBACK TRIGGERS:                                             │
│  • Error rate > [X]%                                            │
│  • Response time > [X]ms                                        │
│  • [Critical function] broken                                   │
│                                                                  │
│  ROLLBACK COMMAND (Feature Flag):                               │
│  [Single command here]                                          │
│                                                                  │
│  ROLLBACK COMMAND (Deployment):                                 │
│  [Single command here]                                          │
│                                                                  │
│  DECISION OWNER: [Name] - [Phone]                               │
│                                                                  │
│  ON-CALL: [Name] - [Phone]                                      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
