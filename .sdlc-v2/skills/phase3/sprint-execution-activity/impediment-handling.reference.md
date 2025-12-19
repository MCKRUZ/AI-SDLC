# Impediment Handling Reference

## Overview

Impediments are blockers that prevent team members from making progress.
Effective impediment handling keeps sprints on track.

---

## Identifying Impediments

### Sources

| Source | Examples |
|--------|----------|
| Technical | Environment down, build broken, dependency issue |
| Process | Waiting for approval, unclear requirements |
| Resource | Missing access, unavailable SME |
| External | Vendor delay, third-party outage |
| Personal | Illness, emergency |

### Recognition Signals

- "I'm blocked on..."
- "I'm waiting for..."
- "I can't proceed until..."
- Task stuck for > 1 day
- Same update in multiple standups

---

## Impediment Categories

### Category 1: Team Can Resolve (< 1 day)

**Examples**: Code review needed, merge conflict, test environment issue

**Action**: Resolve immediately within team

### Category 2: Needs SM/Lead Help (1-2 days)

**Examples**: Cross-team dependency, access request, priority conflict

**Action**: Scrum Master escalates and tracks

### Category 3: Organizational (> 2 days)

**Examples**: Budget approval, vendor contract, policy change

**Action**: Escalate to management, track at program level

---

## Resolution Process

### Step 1: Log

| Field | Value |
|-------|-------|
| ID | IMP-XXX |
| Description | [Clear description] |
| Reported By | [Name] |
| Date Reported | [Date] |
| Affected Story | [US-XXX] |
| Impact | [Hours/days blocked] |

### Step 2: Assess

- **Severity**: How much is blocked?
- **Urgency**: How time-sensitive?
- **Owner**: Who can resolve?
- **Dependencies**: What else is affected?

### Step 3: Act

| Severity | Response Time | Action |
|----------|---------------|--------|
| Critical | Immediate | Drop everything, swarm |
| High | Same day | Prioritize resolution |
| Medium | 1-2 days | Schedule resolution |
| Low | Sprint | Address when convenient |

### Step 4: Track

Update daily until resolved. Communicate status to affected parties.

### Step 5: Close

- Verify resolution
- Update affected parties
- Document lessons learned
- Calculate total blocked time

---

## Escalation Path

```
Team → Scrum Master → Engineering Lead → Director → VP
       (< 4 hrs)      (< 1 day)        (< 2 days)
```

### When to Escalate

- Team cannot resolve within expected timeframe
- Impediment affects sprint goal
- Cross-team coordination needed
- Budget or policy decisions required

---

## Prevention

### Common Preventable Impediments

| Impediment | Prevention |
|------------|------------|
| Access issues | Pre-sprint access checklist |
| Environment problems | Dedicated DevOps support |
| Unclear requirements | Thorough refinement |
| Dependencies | Early coordination |

### Sprint Planning Prevention

- Identify potential blockers during planning
- Ensure all access/environments ready
- Confirm external dependencies
- Have backup tasks if blocked

---

## Quick Reference

**When blocked**:
1. Raise immediately (don't wait for standup)
2. Log with details
3. Identify potential owner
4. Work on alternate tasks
5. Follow up daily

**For Scrum Masters**:
1. Track all impediments visually
2. Daily follow-up on open items
3. Escalate promptly when needed
4. Report blocked time to stakeholders
