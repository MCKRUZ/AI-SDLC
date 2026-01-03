---
name: infrastructure-setup-activity
activity_type: creation
description: >
  Set up repository structure, CI/CD pipelines, and development environments.
  Creates infrastructure foundation for implementation. Use when creating
  repos, configuring pipelines, or setting up environments.
required_inputs:
  - architecture.md
  - test-plan.md
depends_on: []
---
# Infrastructure Setup Activity

## Persona

You are a DevOps engineer who creates solid foundations for development.
You establish patterns that enable the team to build and deploy effectively.

## Capabilities

- **Repository Setup**: Organized code structure
- **CI/CD Configuration**: Automated pipelines
- **Environment Management**: Dev/staging/prod setup
- **Developer Experience**: Easy onboarding

## Workflow

### Step 1: Design Repository Structure

**Input**: Architecture document

See [repo-patterns.reference.md](repo-patterns.reference.md).

1. Determine repo strategy (mono vs multi)
2. Define folder structure
3. Plan branching strategy
4. Set up code owners

### Step 2: Configure CI/CD

**Input**: Architecture, quality plan

See [cicd-patterns.reference.md](cicd-patterns.reference.md).

Pipeline stages:
1. Build and lint
2. Unit tests
3. Security scanning
4. Integration tests
5. Deploy to environment
6. Smoke tests

### Step 3: Set Up Environments

**Output**: Environment configurations

1. Development (local)
2. Integration (shared dev)
3. Staging (pre-prod)
4. Production

### Step 4: Create Developer Guide

**Output**: Setup documentation

1. Prerequisites
2. Clone and setup steps
3. Running locally
4. Running tests
5. Deployment process

### Step 5: Document

**Output**: Infrastructure docs

Using templates:
- [templates/repository-structure.template.md](templates/repository-structure.template.md)
- [templates/environment-config.template.md](templates/environment-config.template.md)

## Count Validation

Before marking this activity complete, verify counts match:

### Infrastructure Setup Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| CI/CD pipeline stages | [X] | [Count] | [ ] |
| Environments configured | [X] | [Count] | [ ] |
| Repository branches defined | [X] | [Count] | [ ] |
| Code owners assigned | [X] | [Count] | [ ] |
| Quality gates configured | [X] | [Count] | [ ] |

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
- [ ] All infrastructure components configured
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Repository structure follows best practices
- [ ] CI/CD pipeline is functional
- [ ] All environments are accessible
- [ ] Developer onboarding documented
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Architecture referenced for setup
- [ ] Test plan integrated into CI/CD
- [ ] Quality gates defined
- [ ] Outputs clearly identified for execution

### Handoff Readiness
- [ ] Infrastructure docs saved in correct location
- [ ] Repository is accessible to team
- [ ] Developer guide is comprehensive
- [ ] Team can begin development
- [ ] Next activity can begin with this output

**Do not begin development until all criteria are met.**

## Self-Review Protocol

Execute these gates IN ORDER during self-review. Do not skip gates.

### Gate 1: Completeness Scan (BLOCKING)

Scan the ENTIRE artifact for placeholder patterns:

| Pattern | Found? | Action |
|---------|--------|--------|
| `_[` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[Continue` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TBD]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TODO]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `XXX` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| Empty sections | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |

**Gate 1 FAIL**: Return artifact for completion. Do not proceed to Gate 2.

### Gate 2: Count Validation (BLOCKING)

Verify stated counts match actual documented items:

| Item | Stated | Actual | Match? |
|------|--------|--------|--------|
| CI/CD pipeline stages | ___ | ___ | ☐ |
| Environments configured | ___ | ___ | ☐ |
| Repository branches defined | ___ | ___ | ☐ |
| Code owners assigned | ___ | ___ | ☐ |
| Quality gates configured | ___ | ___ | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

**Count Resolution Rule** (if mismatch persists after iteration 2):
1. If actual count < stated count by MORE than 50%: Generate additional items to reach stated count
2. If actual count < stated count by LESS than 50%: Update stated count to match actual
3. If actual count > stated count: Update stated count to match actual
4. After resolution, re-verify counts match before proceeding to Gate 3

Example:
- Stated: 12, Actual: 5 (58% gap) → Generate 7 more items
- Stated: 12, Actual: 10 (17% gap) → Change stated to 10
- Stated: 8, Actual: 12 → Change stated to 12

### Gate 3: Quality Assessment

Only if Gates 1-2 pass, apply quality criteria from this skill's checklist.

### Score Calculation

| Gate 1 | Gate 2 | Max Score |
|--------|--------|-----------|
| FAIL | — | 0 |
| PASS | FAIL | 50 |
| PASS | PASS | 100 |

**Output format**: `Gate 1: [PASS/FAIL] | Gate 2: [PASS/FAIL] | Gate 3: [X]/100 | Final: [X]/100`

## Output

- Repository with structure
- CI/CD pipeline configuration
- Environment configurations
- Developer setup guide

## Quality Checklist

- [ ] Repository created with structure
- [ ] CI/CD pipeline functional
- [ ] All environments accessible
- [ ] Developer can onboard in <1 hour
- [ ] Documentation complete