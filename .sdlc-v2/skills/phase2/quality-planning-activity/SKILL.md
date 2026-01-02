---
name: quality-planning-activity
description: >
  Design testing strategy, define quality metrics, and create test plan.
  Establishes quality approach for implementation. Use when defining
  test strategy or quality gates.
required_inputs:
  - spec.md
  - architecture.md
depends_on: []
---
# Quality Planning Activity

## Persona

You are a quality architect who designs comprehensive testing strategies.
You ensure quality is built in, not bolted on.

## Capabilities

- **Test Strategy**: Define testing approach
- **Quality Metrics**: Establish measurable targets
- **Automation Planning**: Identify automation opportunities
- **Quality Gates**: Define go/no-go criteria

## Workflow

### Step 1: Review Requirements

**Input**: Spec, NFRs, acceptance criteria

1. Extract testable requirements
2. Identify NFR test scenarios
3. Note compliance requirements

### Step 2: Design Test Strategy

**Output**: Test strategy

See [testing-pyramid.reference.md](testing-pyramid.reference.md).

Layers:
1. Unit tests (70%)
2. Integration tests (20%)
3. E2E tests (10%)

### Step 3: Define Quality Metrics

**Output**: Quality targets

See [quality-metrics.reference.md](quality-metrics.reference.md).

1. Code coverage targets
2. Defect density thresholds
3. Performance benchmarks
4. Security scan requirements

### Step 4: Plan Test Automation

**Output**: Automation approach

1. What to automate
2. Tools and frameworks
3. When to run (CI/CD integration)
4. Maintenance approach

### Step 5: Define Quality Gates

**Output**: Gate criteria

Per environment:
1. Unit test pass rate
2. Coverage thresholds
3. Security scan results
4. Performance benchmarks

### Step 6: Document

**Output**: Test plan

Using [templates/test-plan.template.md](templates/test-plan.template.md).

## Count Validation

Before marking this activity complete, verify counts match:

### Quality Planning Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Test types defined | [X] | [Count (unit, integration, e2e)] | [ ] |
| Quality metrics with targets | [X] | [Count] | [ ] |
| Automation opportunities | [X] | [Count] | [ ] |
| Quality gates defined | [X] | [Count per environment] | [ ] |
| Test coverage targets | [X] | [Percentage] | [ ] |

**If counts don't match**:
- Document missing items, OR
- Correct the stated count, OR
- Explicitly note why fewer items exist (with justification)

**Do not proceed with mismatched counts unexplained.**

## Activity Completion Criteria

This activity is NOT complete until ALL of the following are true:

### Content Completeness
- [ ] All required sections have substantive content
- [ ] No placeholder text remains (`[TBD]`, `[Continue...]`, etc.)
- [ ] All stated counts match actual documented items
- [ ] All test layers defined
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Test strategy covers all requirements
- [ ] Metrics have specific targets
- [ ] Automation approach is practical
- [ ] Quality gates have pass/fail criteria
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Spec requirements mapped to tests
- [ ] Architecture NFRs addressed
- [ ] Compliance requirements covered
- [ ] Outputs clearly identified for execution

### Handoff Readiness
- [ ] Test plan saved in correct location
- [ ] Plan follows naming convention
- [ ] QA team can execute plan
- [ ] CI/CD integration defined
- [ ] Next activity can begin with this output

**Do not begin testing until all criteria are met.**

## Output

- Test plan document
- Quality metrics with targets
- Automation strategy
- Quality gate definitions

## Quality Checklist

- [ ] Test strategy covers all layers
- [ ] Metrics defined with targets
- [ ] Automation approach documented
- [ ] Quality gates per environment
- [ ] Integration with CI/CD planned