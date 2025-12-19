# Quality Metrics Reference

## Overview

Quality metrics provide objective measures of code and product quality,
enabling data-driven decisions and continuous improvement.

---

## Code Quality Metrics

### Coverage

| Metric | Target | Measurement |
|--------|--------|-------------|
| Line Coverage | ≥ 80% | Lines executed by tests |
| Branch Coverage | ≥ 75% | Decision paths tested |
| Function Coverage | ≥ 90% | Functions called by tests |

**Note**: High coverage doesn't guarantee quality—tests must be meaningful.

### Complexity

| Metric | Target | Meaning |
|--------|--------|---------|
| Cyclomatic Complexity | ≤ 10 per function | Number of decision paths |
| Cognitive Complexity | ≤ 15 per function | Mental effort to understand |
| Nesting Depth | ≤ 4 levels | How deeply nested |

### Maintainability

| Metric | Target | Meaning |
|--------|--------|---------|
| Technical Debt Ratio | ≤ 5% | Time to fix issues / dev time |
| Duplicated Lines | ≤ 3% | Copy-pasted code |
| Code Smells | 0 critical | Design issues |

---

## Defect Metrics

### Defect Density

```
Defect Density = Defects Found / Size Unit

Example: 2 bugs per 1,000 lines of code
```

### Defect Distribution

| Severity | Definition | Target |
|----------|------------|--------|
| Critical | System unusable | 0 in production |
| High | Major feature broken | < 2 per release |
| Medium | Feature impaired | < 10 per release |
| Low | Minor issue | Track and batch |

### Defect Removal Efficiency

```
DRE = Defects found before release / Total defects × 100

Target: ≥ 95%
```

---

## Process Metrics

### Lead Time

```
Lead Time = Time from commit to production

Target: < 1 day (high performers)
```

### Deployment Frequency

| Category | Frequency |
|----------|-----------|
| Elite | Multiple per day |
| High | Daily to weekly |
| Medium | Weekly to monthly |
| Low | Monthly or slower |

### Change Failure Rate

```
CFR = Failed deployments / Total deployments × 100

Target: < 15%
```

### Mean Time to Recovery (MTTR)

```
MTTR = Average time to restore service after failure

Target: < 1 hour
```

---

## Sprint Metrics

### Velocity

```
Velocity = Story Points completed per sprint

Use: Planning future sprints based on history
```

### Sprint Burndown

Track remaining work daily:
```
Day 1:  ████████████████████  40 SP
Day 5:  ████████████         24 SP
Day 10: ████                   8 SP (on track)
```

### Commitment Reliability

```
Reliability = Completed SP / Committed SP × 100

Target: 80-100%
```

---

## Testing Metrics

### Test Pass Rate

```
Pass Rate = Passing tests / Total tests × 100

Target: 100% before merge
```

### Test Execution Time

| Test Type | Target |
|-----------|--------|
| Unit tests | < 2 minutes |
| Integration | < 5 minutes |
| E2E | < 15 minutes |
| Full suite | < 20 minutes |

### Flaky Test Rate

```
Flaky Rate = Inconsistent tests / Total tests × 100

Target: 0% (eliminate flaky tests)
```

---

## Performance Metrics

### Response Time

| Percentile | Target | Meaning |
|------------|--------|---------|
| p50 | < 200ms | Median user experience |
| p95 | < 500ms | Most users |
| p99 | < 1000ms | Nearly all users |

### Availability

```
Availability = (Total time - Downtime) / Total time × 100

Target: 99.9% (8.76 hours downtime/year)
```

### Error Rate

```
Error Rate = Failed requests / Total requests × 100

Target: < 0.1%
```

---

## Quality Dashboards

### Development Dashboard

| Metric | Current | Target | Trend |
|--------|---------|--------|-------|
| Code Coverage | 82% | 80% | ⬆️ |
| Defect Density | 1.2 | < 2 | ✅ |
| Build Success | 95% | 95% | ➡️ |
| Test Pass Rate | 100% | 100% | ✅ |

### Operations Dashboard

| Metric | Current | Target | Trend |
|--------|---------|--------|-------|
| Availability | 99.95% | 99.9% | ✅ |
| p95 Response | 320ms | 500ms | ✅ |
| Error Rate | 0.05% | 0.1% | ✅ |
| MTTR | 45 min | 60 min | ⬆️ |

---

## Setting Targets

### Start Realistic

1. Measure current state
2. Set achievable improvement (10-20%)
3. Gradually increase over time
4. Adjust based on context

### Industry Benchmarks

| Metric | Good | Better | Best |
|--------|------|--------|------|
| Coverage | 60% | 80% | 90%+ |
| Deploy Freq | Weekly | Daily | Multiple/day |
| Lead Time | 1 week | 1 day | < 1 hour |
| MTTR | 1 day | 1 hour | < 10 min |

---

## Quick Reference

**Essential metrics to track**:
- Coverage (≥ 80%)
- Defect density (declining)
- Velocity (stable or increasing)
- Lead time (decreasing)
- Availability (≥ 99.9%)

**Review cadence**:
- Daily: Build/test status
- Sprint: Velocity, defects
- Monthly: Trends, targets
- Quarterly: Strategic review
