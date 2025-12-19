# Pattern Recognition Reference

## Overview

Pattern recognition synthesizes individual interview findings into
coherent themes. Strong patterns (mentioned by multiple stakeholders)
indicate validated insights.

---

## Pattern Identification Process

### Step 1: Extract Raw Findings

From each interview, extract:
- Pain points mentioned
- Needs expressed
- Constraints identified
- Success criteria suggested
- Risks/concerns raised

### Step 2: Normalize Language

Different stakeholders use different words for the same concept:

| Stakeholder A | Stakeholder B | Normalized Term |
|---------------|---------------|-----------------|
| "The system is slow" | "Performance issues" | **Response time** |
| "Can't find data" | "Search doesn't work" | **Data discoverability** |
| "Too many steps" | "Process is clunky" | **Workflow efficiency** |

### Step 3: Group by Theme

Cluster related findings into themes:

```
Theme: Data Quality Issues
├── "Reports have wrong numbers" (CFO)
├── "Don't trust the dashboard" (VP Sales)
├── "Manual corrections daily" (Analyst)
└── "Source systems out of sync" (IT Director)
```

### Step 4: Count Support

Track how many stakeholders mentioned each theme:

| Theme | Stakeholders | Count | Strength |
|-------|--------------|-------|----------|
| Data Quality | CFO, VP Sales, Analyst, IT | 4 | Strong |
| Performance | IT, Users (3) | 4 | Strong |
| Training | HR, Users (2) | 3 | Moderate |
| Mobile Access | Sales (1) | 1 | Weak |

### Step 5: Validate Patterns

A pattern is validated when:
- 3+ stakeholders mention it independently
- Evidence is consistent across sources
- Root cause analysis converges

---

## Pattern Strength Scale

| Strength | Criteria | Confidence |
|----------|----------|------------|
| **Strong** | 4+ stakeholders, consistent evidence | High |
| **Moderate** | 3 stakeholders, mostly consistent | Medium |
| **Emerging** | 2 stakeholders, needs validation | Low |
| **Weak** | 1 stakeholder only | Very Low |

### Decision Rules

| Pattern Strength | Action |
|------------------|--------|
| Strong | Include in problem statement |
| Moderate | Include, note confidence level |
| Emerging | Investigate further or note as assumption |
| Weak | Don't include unless critical |

---

## Common Pattern Categories

### Pain Point Patterns

| Category | Examples |
|----------|----------|
| **Performance** | Slow, timeout, lag, waiting |
| **Data Quality** | Wrong, inaccurate, stale, inconsistent |
| **Usability** | Confusing, too many clicks, can't find |
| **Integration** | Manual entry, copy/paste, doesn't sync |
| **Reliability** | Crashes, errors, downtime |
| **Access** | Can't get to, permissions, mobile |

### Need Patterns

| Category | Examples |
|----------|----------|
| **Efficiency** | Faster, automated, streamlined |
| **Visibility** | Dashboard, reports, real-time |
| **Control** | Approval, audit, permissions |
| **Flexibility** | Customizable, configurable |
| **Scalability** | Handle more, grow with us |

### Constraint Patterns

| Category | Examples |
|----------|----------|
| **Technical** | Legacy system, vendor lock-in |
| **Organizational** | Process, approval, politics |
| **Resource** | Budget, people, time |
| **Compliance** | Regulation, security, audit |

---

## Pattern Analysis Template

```markdown
## Pattern: [Theme Name]

### Summary
[One sentence describing the pattern]

### Evidence

| Source | Quote/Observation | Context |
|--------|-------------------|---------|
| [Stakeholder 1] | "[Direct quote]" | [Interview context] |
| [Stakeholder 2] | "[Direct quote]" | [Interview context] |
| [Stakeholder 3] | "[Direct quote]" | [Interview context] |

### Strength Assessment

- **Stakeholder Count**: [N]
- **Consistency**: [High/Medium/Low]
- **Pattern Strength**: [Strong/Moderate/Emerging/Weak]

### Root Cause Analysis

Using Five Whys from interviews:
1. Why: [First level]
2. Why: [Second level]
3. Why: [Third level]
4. Why: [Fourth level]
5. Why: [Root cause]

**Root Cause**: [Summary]

### Impact

- **Who affected**: [User groups]
- **How often**: [Frequency]
- **Severity**: [High/Medium/Low]
- **Quantified impact**: [If available]

### Related Patterns

- [Related pattern 1]
- [Related pattern 2]
```

---

## Pattern Synthesis Matrix

Use this matrix to visualize patterns across stakeholders:

```
                    Stakeholders
Pattern         | CEO | CTO | Users | Ops | Sales |
----------------|-----|-----|-------|-----|-------|
Data Quality    |  ●  |  ●  |   ●   |  ●  |   ○   |  4/5
Performance     |  ○  |  ●  |   ●   |  ●  |   ●   |  4/5
Integration     |  ○  |  ●  |   ○   |  ●  |   ●   |  3/5
Training        |  ○  |  ○  |   ●   |  ●  |   ●   |  3/5
Mobile Access   |  ○  |  ○  |   ○   |  ○  |   ●   |  1/5

● = Mentioned    ○ = Not mentioned
```

---

## Avoiding Pattern Recognition Pitfalls

### Pitfall 1: Confirmation Bias

**Problem**: Seeing patterns that confirm preconceptions

**Solution**:
- Document patterns you DIDN'T expect
- Actively look for contradicting evidence
- Have someone else review your synthesis

### Pitfall 2: Loudest Voice Bias

**Problem**: Weighting senior stakeholders more heavily

**Solution**:
- Count stakeholders, not seniority
- One CEO mention = one user mention
- Note seniority separately from pattern strength

### Pitfall 3: Premature Pattern Lock

**Problem**: Stopping interviews once a pattern emerges

**Solution**:
- Continue until saturation (no new patterns in 2-3 interviews)
- Explicitly seek disconfirming evidence
- Interview skeptics and edge cases

### Pitfall 4: Missing Implicit Patterns

**Problem**: Only capturing explicit statements

**Solution**:
- Note what stakeholders DIDN'T say
- Capture body language, hesitation
- Ask "what else?" multiple times

### Pitfall 5: Conflating Correlation

**Problem**: Assuming related mentions are the same pattern

**Solution**:
- Verify stakeholders mean the same thing
- Use their language when validating
- Split patterns that have different root causes

---

## Pattern Validation Techniques

### Technique 1: Mirror Back

In subsequent interviews, describe the pattern and ask:
> "We're hearing that [pattern]. Does that match your experience?"

### Technique 2: Seek Exceptions

Ask stakeholders:
> "When does this NOT happen? Are there situations where this works well?"

### Technique 3: Quantify

Ask stakeholders:
> "How often does this happen? Can you estimate the impact?"

### Technique 4: Root Cause Convergence

If Five Whys analysis from different stakeholders converges on the same root cause, the pattern is likely valid.

---

## Quick Reference

### Pattern Recognition Checklist

- [ ] All interviews extracted into findings
- [ ] Language normalized across stakeholders
- [ ] Findings grouped into themes
- [ ] Stakeholder count per theme
- [ ] Pattern strength assessed
- [ ] Root causes identified
- [ ] Contradictions noted
- [ ] Patterns validated (3+ stakeholders)

### Pattern Strength Quick Guide

| Count | Strength | Action |
|-------|----------|--------|
| 4+ | Strong | Include with confidence |
| 3 | Moderate | Include, note assumptions |
| 2 | Emerging | Validate further |
| 1 | Weak | Don't include |
