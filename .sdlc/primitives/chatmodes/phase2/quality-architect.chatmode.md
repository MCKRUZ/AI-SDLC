# Quality Architect Chatmode

## Purpose
Focused quality strategy, test planning, and quality standards sessions using the Quality Architect Agent.

## When to Use This Mode
- Designing test strategy (unit, integration, E2E)
- Creating test plans
- Defining quality metrics and KPIs
- Setting up quality gates
- Creating Definition of Done
- Planning performance and security testing
- Establishing code quality standards

## Session Setup

### Before Starting
Load these artifacts into context:
1. Quality Architect instructions (`quality-architect_instructions.md`)
2. Phase 2 config (`../../config/phase2_config.md`)
3. From Phase 1:
   - Constitution (`phase1/artifacts/constitution.md`) - quality standards
   - Specification (`phase1/artifacts/spec.md`) - acceptance criteria
   - Architecture (`phase1/artifacts/architecture.md`) - testability
   - PRD (`phase1/artifacts/prd.md`) - success metrics
4. Task breakdown (`phase2/artifacts/task-breakdown.md`)
5. Test plan template (`../templates/phase2/test-plan_template.md`)

### Agent Instructions
Load: `quality-architect_instructions.md`

### Session Goal
Define a clear goal for the session:
- "Create test strategy for [project]"
- "Design test plan for [feature/epic]"
- "Define quality metrics and KPIs"
- "Set up quality gates for CI/CD"
- "Create Definition of Done"
- "Plan performance testing approach"

---

## Interaction Patterns

### Pattern 1: Test Strategy Session

**When to Use**: Designing the overall testing approach for the project

**Opening Prompt**:
```
I need to create a test strategy for [project].

Architecture Overview:
[Paste key points from architecture - components, integrations]

Quality Requirements from Constitution:
[Paste relevant quality standards]

Team Context:
- Team size: [N] developers
- QA resources: [Dedicated QA / Developer testing / Both]
- Testing experience: [High / Medium / Low]
- Automation maturity: [High / Medium / Low]

Please design a test strategy covering:
1. Test levels (unit, integration, E2E, etc.)
2. Test types (functional, performance, security, accessibility)
3. Automation vs. manual testing balance
4. Test environment requirements
5. Test data strategy
6. Tools and frameworks
7. Coverage targets
8. Risk-based testing approach
```

**Test Pyramid Deep Dive**:
```
Let's define the test pyramid for this project.

Architecture components:
[List components]

Please specify for each level:

UNIT TESTS:
- What to test at unit level
- Coverage target
- Mocking strategy
- Framework recommendation

INTEGRATION TESTS:
- Integration points to test
- Test environment needs
- Data management
- Framework recommendation

E2E TESTS:
- Critical user journeys to cover
- Browser/device coverage
- Test environment
- Framework recommendation
```

**Closing Prompt**:
```
Please finalize the test strategy:
1. Test pyramid with coverage targets per level
2. Test types and their application
3. Automation approach
4. Tool recommendations
5. Resource requirements
6. Risks and mitigations
```

---

### Pattern 2: Test Plan Creation

**When to Use**: Creating detailed test plan for a feature or epic

**Opening Prompt**:
```
I need to create a test plan for [feature/epic].

Feature Requirements:
[Paste from spec.md - functional requirements and acceptance criteria]

Architecture Context:
[Relevant components and integrations]

Please create a test plan including:
1. Test scope (what's in / out)
2. Test scenarios derived from requirements
3. Test cases for each scenario
4. Test data requirements
5. Environment requirements
6. Entry/exit criteria
7. Risk assessment
```

**Test Case Development**:
```
Let's develop test cases for [specific requirement/scenario].

Requirement:
[Paste requirement with acceptance criteria]

Please create:
1. Positive test cases (happy path)
2. Negative test cases (error handling)
3. Edge cases
4. Boundary conditions
5. For each test case:
   - Preconditions
   - Test steps
   - Expected results
   - Test data needed
```

**Closing Prompt**:
```
Please finalize the test plan:
1. Complete test case inventory
2. Test data requirements
3. Environment setup needs
4. Estimated test execution effort
5. Priority/risk ranking of test cases
6. Format using test plan template
```

---

### Pattern 3: Quality Metrics Definition

**When to Use**: Establishing measurable quality KPIs

**Opening Prompt**:
```
I need to define quality metrics for [project].

Quality Goals from Constitution:
[Paste quality standards]

Success Metrics from PRD:
[Paste relevant metrics]

Please help me define:
1. Code quality metrics
2. Test quality metrics
3. Defect metrics
4. Performance metrics
5. Security metrics
6. User experience metrics

For each metric:
- Definition
- How to measure
- Target threshold
- Warning threshold
- Collection frequency
```

**Dashboard Design**:
```
Let's design a quality dashboard.

Key stakeholders:
- Developers (daily visibility)
- QA (test execution tracking)
- Management (release readiness)

Please design dashboard views for each audience:
1. What metrics to show
2. Visualization type
3. Drill-down capabilities
4. Alert thresholds
5. Tool recommendations
```

**Closing Prompt**:
```
Please finalize quality metrics:
1. Complete metrics catalog with definitions
2. Target and warning thresholds
3. Measurement approach for each
4. Dashboard design
5. Reporting cadence
```

---

### Pattern 4: Quality Gates Setup

**When to Use**: Defining automated quality checkpoints in CI/CD

**Opening Prompt**:
```
I need to set up quality gates for CI/CD.

CI/CD Pipeline:
[Summary of pipeline from DevOps setup]

Quality Requirements:
[From constitution]

Please design quality gates including:
1. Pre-commit checks (what developers must pass locally)
2. PR checks (what must pass for merge)
3. Build gate (what fails the build)
4. Deploy gate (what blocks deployment)
5. Production readiness gate

For each gate:
- Checks performed
- Pass/fail thresholds
- Blocking vs. warning
- Override process (if any)
```

**Specific Gate Configuration**:
```
Let's configure the [PR / Build / Deploy] quality gate.

Current tools:
[List CI/CD and quality tools]

Please provide:
1. Specific checks to include
2. Configuration for each check
3. Threshold settings
4. Failure behavior
5. Notification approach
6. Actual configuration (YAML/JSON if applicable)
```

**Closing Prompt**:
```
Please finalize quality gates:
1. All gates defined with checks
2. Thresholds documented
3. Override/exception process
4. Configuration files ready
5. Integration with CI/CD pipeline
```

---

### Pattern 5: Definition of Done

**When to Use**: Creating clear completion criteria for work items

**Opening Prompt**:
```
I need to create a Definition of Done for [project].

Team Context:
- Development approach: [Agile/Scrum/Kanban]
- Code review requirements: [From constitution]
- Testing requirements: [From test strategy]
- Documentation requirements: [From standards]

Please create Definition of Done for:
1. Task/Story level
2. Sprint level
3. Release level

Each DoD should include:
- Coding standards
- Testing requirements
- Documentation
- Review/approval
- Deployment readiness
```

**DoD Refinement**:
```
Let's refine the Story-level Definition of Done.

Current draft:
[Paste draft]

Please ensure it covers:
1. Code quality (lint, format, complexity)
2. Testing (unit, integration as applicable)
3. Code review approval
4. Documentation updated
5. Acceptance criteria verified
6. No regressions introduced
7. Ready for demo
```

**Closing Prompt**:
```
Please finalize Definition of Done:
1. Task/Story DoD (checklist format)
2. Sprint DoD (checklist format)
3. Release DoD (checklist format)
4. How to validate DoD is met
5. What happens if DoD is not met
```

---

### Pattern 6: Performance Testing Strategy

**When to Use**: Planning performance, load, and stress testing

**Opening Prompt**:
```
I need to plan performance testing for [project].

Performance Requirements (from spec.md NFRs):
[Paste performance requirements]

Architecture Context:
[Key components and potential bottlenecks]

Expected Load:
- Concurrent users: [N]
- Transactions per second: [N]
- Data volume: [Size]

Please design performance testing approach:
1. Types of performance tests (load, stress, soak, spike)
2. Key scenarios to test
3. Metrics to capture
4. Tools recommendation
5. Test environment requirements
6. Performance budgets
7. Baseline and target thresholds
```

**Performance Test Design**:
```
Let's design performance tests for [specific scenario/endpoint].

Requirements:
- Response time: [Target]
- Throughput: [Target]
- Concurrent users: [Target]

Please create:
1. Test scenario description
2. Load profile (ramp-up, steady, ramp-down)
3. Think times
4. Data requirements
5. Pass/fail criteria
6. Script outline (for JMeter/Gatling/k6/etc.)
```

**Closing Prompt**:
```
Please finalize performance testing strategy:
1. Performance test plan
2. Key scenarios with load profiles
3. Tool configuration
4. Environment requirements
5. Integration with CI/CD (if applicable)
6. Reporting approach
```

---

### Pattern 7: Security Testing Strategy

**When to Use**: Planning security testing approach

**Opening Prompt**:
```
I need to plan security testing for [project].

Security Requirements (from constitution/spec):
[Paste security requirements]

Architecture Context:
[Authentication, authorization, data handling]

Compliance Requirements:
[GDPR, HIPAA, SOC2, etc. if applicable]

Please design security testing approach:
1. Security test types (SAST, DAST, penetration, etc.)
2. OWASP Top 10 coverage
3. Authentication/authorization testing
4. Data protection verification
5. Tools recommendation
6. Frequency (CI vs. periodic)
7. Remediation workflow
```

**Security Gate Configuration**:
```
Let's configure security scanning in CI/CD.

Current pipeline:
[Summary]

Please configure:
1. SAST tool and rules
2. Dependency vulnerability scanning
3. Container scanning (if applicable)
4. Severity thresholds (what blocks deployment)
5. False positive management
6. Actual configuration
```

---

## Best Practices for This Mode

### Do's
- ✅ Align test strategy with architecture
- ✅ Automate what can be automated
- ✅ Define clear pass/fail criteria
- ✅ Plan test data management
- ✅ Consider test environment parity
- ✅ Include non-functional testing
- ✅ Make quality visible (dashboards)
- ✅ Build quality gates into CI/CD

### Don'ts
- ❌ Don't test everything at E2E level
- ❌ Don't skip security testing
- ❌ Don't ignore performance until late
- ❌ Don't set coverage targets without context
- ❌ Don't create tests that are hard to maintain
- ❌ Don't let quality gates be easily bypassed

---

## Session Outputs

### Primary Artifacts
- **Test Strategy**:
  - Test pyramid and approach
  - Test types coverage
  - Tool decisions
  - Resource requirements

- **Test Plan** (`test-plan.md`):
  - Test scenarios and cases
  - Test data requirements
  - Entry/exit criteria

- **Quality Metrics**:
  - Metrics catalog
  - Thresholds
  - Dashboard design

- **Quality Gates**:
  - Gate definitions
  - Configurations
  - Integration with CI/CD

- **Definition of Done**:
  - Story/Sprint/Release checklists

---

## Quality Checks Before Ending Session

- [ ] Test strategy covers all test levels
- [ ] Quality requirements from constitution addressed
- [ ] Test plan covers critical requirements
- [ ] Quality metrics are measurable
- [ ] Quality gates configured
- [ ] Definition of Done is clear
- [ ] Performance testing planned (if NFRs exist)
- [ ] Security testing planned
- [ ] All artifacts follow templates

---

## Transitioning Out of This Mode

**When Quality Planning is Complete**:
- Test strategy approved
- Quality gates configured
- Definition of Done agreed
- Team understands quality expectations

**Handoff to Development**:
```
Quality planning is complete. Please create a quality onboarding summary:
1. Test strategy overview (what to test where)
2. Quality gates developers will encounter
3. Definition of Done checklist
4. How to run tests locally
5. Quality metrics developers should watch
6. Where to get help with quality questions
```

**Integration Verification**:
```
Please verify quality integration with other Phase 2 outputs:
1. Quality gates integrated with CI/CD pipeline
2. Test plan aligned with sprint plan
3. Definition of Done included in task breakdown
4. Quality metrics dashboard accessible
5. Test environment ready
```

---

*Created for: Phase 2 - Planning & Setup*
*Works with: Quality Architect Agent*
*Last Updated: 2025-12-15*
