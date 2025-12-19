# Dependency Mapping Reference

## Overview

Dependency mapping identifies relationships between tasks that affect
scheduling. Understanding dependencies enables realistic planning.

---

## Dependency Types

### Finish-to-Start (FS)

**Most common**: Task B cannot start until Task A finishes.

```
[Task A] ──────> [Task B]
```

**Example**: "Create database schema" must finish before "Write data access layer"

### Start-to-Start (SS)

Tasks can start together but must begin simultaneously.

```
[Task A] ─┐
          ├──> Both start together
[Task B] ─┘
```

**Example**: "Backend development" and "API documentation" start together

### Finish-to-Finish (FF)

Tasks must complete together.

```
[Task A] ─┐
          ├──> Both finish together  
[Task B] ─┘
```

**Example**: "Feature implementation" and "Feature tests" finish together

### Start-to-Finish (SF)

Task B cannot finish until Task A starts. (Rare)

---

## Dependency Categories

### Technical Dependencies

| Type | Example |
|------|---------|
| Data | Database must exist before queries |
| API | Endpoint must exist before client integration |
| Infrastructure | CI/CD before automated deployment |
| Library | Shared component before consumers |

### Resource Dependencies

| Type | Example |
|------|---------|
| Skill | Only one person knows legacy system |
| Equipment | Limited test devices |
| Environment | Shared staging server |

### External Dependencies

| Type | Example |
|------|---------|
| Third-party API | Vendor integration readiness |
| Approval | Security review sign-off |
| Data | Customer-provided test data |
| Timeline | External team delivery |

---

## Identifying Dependencies

### Questions to Ask

For each task, ask:
1. What must be complete before this can start?
2. What other tasks need this to be complete?
3. Who else needs to be involved?
4. What external factors affect this?
5. Are there shared resources?

### Dependency Matrix

| Task | Depends On | Blocks |
|------|------------|--------|
| T1: Setup database | - | T2, T3 |
| T2: Create schema | T1 | T4, T5 |
| T3: Setup API project | T1 | T4 |
| T4: User endpoints | T2, T3 | T7 |
| T5: Data access layer | T2 | T4 |

---

## Critical Path

### Definition

The longest sequence of dependent tasks that determines minimum project duration.

### Finding Critical Path

1. Map all dependencies
2. Calculate duration for each path
3. Longest path = critical path
4. Tasks on critical path have zero slack

### Example

```
Path 1: T1(2d) → T2(3d) → T4(5d) = 10 days
Path 2: T1(2d) → T3(2d) → T4(5d) = 9 days
Path 3: T1(2d) → T2(3d) → T5(2d) = 7 days

Critical Path: Path 1 (10 days)
```

### Managing Critical Path

- Prioritize critical path tasks
- Add resources if possible
- Look for parallelization
- Identify and mitigate risks

---

## Visualizing Dependencies

### Gantt Chart

```
Week 1    Week 2    Week 3
T1 ████
T2      ██████
T3      ████
T4            ██████████
T5           ████
```

### Network Diagram

```
        ┌──> T2 ──> T5
       │      │
T1 ───┤       ├──> T4
       │      │
        └──> T3 ──┘
```

---

## Reducing Dependencies

### Strategies

| Strategy | How | Example |
|----------|-----|---------|
| Stub/Mock | Create placeholders | Mock API while backend develops |
| Interface-first | Define contracts early | API spec before implementation |
| Parallel tracks | Independent workstreams | Frontend and backend in parallel |
| Feature flags | Deploy incomplete features | Release with flag off |

### Breaking Dependencies

Before:
```
[Design] → [Frontend] → [Backend] → [Test]
Total: 20 days sequential
```

After:
```
[Design] → [API Contract]
              ├──> [Frontend] ─┐
              └──> [Backend]  ─┼──> [Integration] → [Test]
                               │
Total: 14 days with parallelization
```

---

## Risk from Dependencies

### High-Risk Patterns

| Pattern | Risk | Mitigation |
|---------|------|------------|
| Single point | Bottleneck | Cross-train, parallel tasks |
| External wait | Delays | Early engagement, fallback |
| Long chain | Cascading delays | Break dependencies |
| Circular | Deadlock | Redesign approach |

### Dependency Risk Assessment

| Dependency | Probability of Delay | Impact | Mitigation |
|------------|---------------------|--------|------------|
| D1: API ready | Medium | High | Mock API |
| D2: Security review | High | Medium | Early submission |

---

## Quick Reference

**Mapping Steps**:
1. List all tasks
2. For each task, identify predecessors
3. Build dependency matrix
4. Draw network diagram
5. Calculate critical path
6. Identify risks

**Key Questions**:
- What must happen first?
- What can happen in parallel?
- Where are the bottlenecks?
- What external factors exist?
