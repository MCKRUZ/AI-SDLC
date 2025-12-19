# Capacity Planning Reference

## Overview

Capacity planning ensures sprint commitments are realistic based on 
available team time and skills.

---

## Calculating Capacity

### Basic Formula

```
Sprint Capacity = Team Members × Working Days × Hours/Day × Focus Factor
```

### Focus Factor

The percentage of time available for planned sprint work.

| Factor | Range | Typical |
|--------|-------|---------|
| Focus Factor | 0.6 - 0.8 | 0.7 |

**Deductions from 100%**:
- Meetings: 10-15%
- Email/Slack: 5-10%
- Support/bugs: 5-10%
- Context switching: 5-10%
- Breaks/admin: 5%

### Example Calculation

**Team**: 4 developers  
**Sprint**: 2 weeks (10 working days)  
**Hours/day**: 8  
**Focus Factor**: 0.7  

```
Capacity = 4 × 10 × 8 × 0.7 = 224 hours
With 20% buffer = 224 × 0.8 = 179 usable hours
```

---

## Story Point Capacity

### Converting to Story Points

If team velocity is known:

```
SP Capacity = Historical Velocity (rolling average)
```

### New Team Estimation

Without velocity history, estimate:

| Team Experience | SP/Dev/Sprint |
|-----------------|---------------|
| Junior heavy | 5-8 |
| Mixed experience | 8-12 |
| Senior heavy | 12-16 |

**Example**: 4 developers, mixed = 4 × 10 = **40 SP/sprint**

---

## Individual Capacity

### Availability Matrix

| Team Member | Days Available | % Allocation | Effective Days |
|-------------|----------------|--------------|----------------|
| Alice | 10 | 100% | 10 |
| Bob | 10 | 80% | 8 |
| Charlie | 8 | 100% | 8 |
| Diana | 10 | 50% | 5 |
| **Total** | | | **31 days** |

### Skill-Based Capacity

| Skill | Team Members | Capacity |
|-------|--------------|----------|
| Frontend | Alice, Bob | 18 days |
| Backend | Charlie, Diana | 13 days |
| DevOps | Bob | 8 days |

---

## Buffer Planning

### Recommended Buffers

| Buffer Type | Amount | Purpose |
|-------------|--------|---------|
| Sprint buffer | 20% | Unknowns, scope creep |
| Risk buffer | 10% | Identified risks |
| Technical debt | 10% | Maintenance, cleanup |

### Capacity Allocation

```
Total Capacity: 100%
├── Committed Work: 60-70%
├── Buffer: 20%
├── Technical Debt: 10%
└── Unplanned: 0-10%
```

---

## Sprint 0 Considerations

Sprint 0 has different capacity dynamics:

| Activity | % of Sprint 0 |
|----------|---------------|
| Infrastructure setup | 30-40% |
| Environment configuration | 20-30% |
| Onboarding/learning | 15-25% |
| Documentation | 10-15% |
| Initial scaffolding | 10-20% |

**Expectation**: No velocity tracking in Sprint 0

---

## Adjustments

### Capacity Adjustments

| Situation | Adjustment |
|-----------|------------|
| New team member | -20% first sprint, -10% second |
| Team member leaving | -20% (knowledge transfer) |
| New technology | -30% learning curve |
| Holidays | Pro-rate available days |
| On-call rotation | -10-20% for on-call person |

### Load Balancing

**Warning Signs**:
- Any individual > 90% utilized
- Skill bottleneck (single person for critical skill)
- Uneven distribution (some idle, some overloaded)

**Solutions**:
- Pair programming to spread knowledge
- Move work to adjacent sprints
- Cross-training investment

---

## Capacity Planning Checklist

- [ ] Count available working days per person
- [ ] Apply focus factor (0.6-0.8)
- [ ] Account for known absences
- [ ] Reserve 20% buffer minimum
- [ ] Check skill coverage for planned work
- [ ] Verify no individual > 80% utilized
- [ ] Document assumptions

---

## Quick Reference

**Simple capacity**: `Team Size × 10 SP/person × 0.8 buffer`

**Detailed capacity**:
1. List team members and availability
2. Calculate hours: `days × 8 × focus_factor`
3. Convert to SP using velocity or `1 SP ≈ 4-6 hours`
4. Apply 20% buffer
5. Verify skill distribution
