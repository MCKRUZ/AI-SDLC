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