# Phase 2: Planning & Setup Configuration

**Version**: 1.0  
**Last Updated**: 2025-10-31  
**Status**: Active  
**Scope**: Phase 2 - Planning & Setup

---

## Purpose of This Configuration

This configuration file controls all aspects of the Phase 2 planning and infrastructure setup process, including:
- Agent behavior and preferences (Planning Agent, DevOps Scaffolder, Quality Architect)
- Task decomposition methodologies
- Sprint planning approaches
- Repository and infrastructure setup standards
- Quality planning frameworks
- Workflow orchestration settings
- Artifact creation and validation
- Traceability requirements
- Handoff criteria to Phase 3

---

## General Phase 2 Settings

### Phase 2 Mode

**Current Mode**: `parallel-workstream`

**Available Modes**:
- `parallel-workstream` - Planning and infrastructure setup proceed concurrently
- `sequential-setup` - Complete planning before infrastructure
- `infrastructure-first` - Set up infrastructure then plan sprints (rarely used)

**Mode Selection Criteria**:
- Use `parallel-workstream` for: Most projects, faster time-to-development
- Use `sequential-setup` for: Complex planning requiring full focus first
- Use `infrastructure-first` for: Known scope, straightforward planning

---

### Session Management

**Session Duration Preferences**:
- **Task decomposition sessions**: 120-180 minutes for initial breakdown
- **Sprint planning sessions**: 90-120 minutes per sprint
- **Repository setup sessions**: 60-90 minutes
- **Quality planning sessions**: 90-120 minutes
- **Dependency mapping sessions**: 60-90 minutes
- **Validation sessions**: 90-120 minutes for full Phase 2 validation

**Session Splitting Strategy**:
- **Maximum context window usage**: 70% (keep room for large artifacts)
- **Auto-split triggers**:
  - Conversation exceeds 18,000 tokens
  - Switching between major activities (planning → infrastructure)
  - Moving from creation to validation mode
  - Phase transition (Phase 2 → Phase 3)

**Session Naming Convention**: `session-NNN-[project-name]-phase2-[activity]`
- Examples: `session-010-customer-portal-phase2-task-decomp`, `session-011-customer-portal-phase2-sprint1-plan`

**Concurrent Sessions**:
- **Allowed**: Yes (up to 3 concurrent workstreams)
- **Typical Split**:
  - Workstream 1: Task decomposition and sprint planning
  - Workstream 2: Repository and infrastructure setup
  - Workstream 3: Quality planning and test strategy
- **Coordination**: Weekly sync to align workstreams

---

### Version Control

**Working File Strategy**: `[artifact]-v[N].md` in `working/` directory

**Version Numbering**:
- **v1**: Initial draft
- **v2-vN**: Refinements based on feedback
- **vFinal**: Validated version moved to `artifacts/`

**When to Increment Version**:
- Major restructuring of tasks or sprints
- Significant dependency changes
- Infrastructure approach changes
- Stakeholder feedback incorporation

**Retention Policy**: Keep all versions until Phase 3 completion

---

## Agent-Specific Settings

### Planning Agent Configuration

**Task Decomposition Methodology**: `story-driven-with-dependencies`

**Available Methodologies**:
- `story-driven-with-dependencies` - Start with user stories, decompose to tasks
- `feature-first` - Group by features, then decompose
- `layer-first` - Split by technical layers (frontend, backend, data)
- `vertical-slice` - End-to-end features across all layers

**Task Sizing Approach**: `story-points-fibonacci`

**Available Approaches**:
- `story-points-fibonacci` - 1, 2, 3, 5, 8, 13 (Agile standard)
- `t-shirt-sizes` - XS, S, M, L, XL
- `ideal-hours` - Actual time estimates
- `complexity-only` - Low, Medium, High complexity without time

**Sprint Duration**: `2-weeks`

**Available Durations**:
- `1-week` - Very small teams, simple projects
- `2-weeks` - Standard Agile (recommended)
- `3-weeks` - Larger teams, complex integration
- `4-weeks` - Large enterprise projects

**Velocity Estimation**: `conservative`

**Approaches**:
- `conservative` - Assume 60-70% capacity for development
- `moderate` - Assume 70-80% capacity
- `aggressive` - Assume 80-90% capacity (risky)

**Default Team Capacity**: 
- **Sprint points capacity**: 40 points per 2-week sprint (5-person team)
- **Adjustment factors**:
  - Meetings/overhead: -20%
  - Bug fixes/support: -10%
  - Context switching: -10%
  - Net capacity: ~60% of theoretical maximum

**Dependency Management**: `explicit-critical-path`

**Approaches**:
- `explicit-critical-path` - Identify and document critical path dependencies
- `just-in-time` - Document dependencies as they arise
- `full-pert` - Complete PERT/CPM analysis (overkill for most projects)

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `phase1/artifacts/spec.md` - Always load
- ✅ `phase1/artifacts/architecture.md` - Always load
- ✅ `phase1/artifacts/prd.md` - Always load
- ✅ `phase1/artifacts/constitution.md` - Always load
- ✅ `decisions_memory.md` - Always load
- ✅ `lessons-learned_memory.md` - Load for historical velocity data

---

### DevOps Scaffolder Configuration

**Repository Structure Style**: `modular-by-feature`

**Available Styles**:
- `modular-by-feature` - Organize by business features
- `layer-based` - Organize by technical layers (common but not recommended)
- `domain-driven` - Organize by domain/bounded contexts
- `monorepo-workspaces` - Single repo with multiple packages

**Branching Strategy**: `github-flow-simplified`

**Available Strategies**:
- `github-flow-simplified` - Main + feature branches (recommended for small teams)
- `git-flow` - Main, develop, feature, release, hotfix branches
- `trunk-based` - Frequent commits to main with feature flags
- `release-branches` - Main + release branches for long-term support

**CI/CD Pipeline Approach**: `progressive-automation`

**Approaches**:
- `progressive-automation` - Start simple, add automation incrementally
- `full-automation-upfront` - Complete CI/CD before development (time-consuming)
- `manual-then-automate` - Manual processes first, automate in Phase 3

**Infrastructure as Code**: `required`

**Requirement Level**:
- `required` - All infrastructure defined as code (recommended)
- `preferred` - IaC encouraged but not mandatory
- `optional` - Document infrastructure manually

**Environment Strategy**: `dev-staging-prod`

**Available Strategies**:
- `dev-staging-prod` - Three standard environments
- `dev-qa-staging-prod` - Four environments with dedicated QA
- `dev-prod-only` - Minimal (small projects only)
- `per-developer-staging-prod` - Developer-specific environments

**Container Strategy**: `docker-compose-local-k8s-prod`

**Strategies**:
- `docker-compose-local-k8s-prod` - Docker Compose for dev, Kubernetes for prod
- `docker-everywhere` - Docker Compose for all environments
- `kubernetes-everywhere` - Kubernetes from dev to prod
- `no-containers` - Traditional deployment (not recommended)

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `phase1/artifacts/architecture.md` - Always load
- ✅ `phase1/artifacts/constitution.md` - Always load
- ✅ `prior-projects_memory.md` - Load for infrastructure patterns
- ✅ `lessons-learned_memory.md` - Load for deployment lessons

---

### Quality Architect Configuration

**Testing Strategy**: `test-pyramid-with-e2e`

**Available Strategies**:
- `test-pyramid-with-e2e` - Many unit, some integration, few E2E
- `testing-trophy` - More integration tests than pure pyramid
- `unit-heavy` - Focus on unit tests primarily
- `e2e-focused` - More E2E tests (slower, more brittle)

**Test Coverage Goals**:
- **Unit Test Coverage**: 80% minimum
- **Integration Test Coverage**: 60% of critical paths
- **E2E Test Coverage**: 100% of critical user journeys

**Test Data Strategy**: `synthetic-with-anonymized-production`

**Strategies**:
- `synthetic-with-anonymized-production` - Generated + anonymized real data
- `synthetic-only` - All test data generated
- `production-subset` - Anonymized subset of production data
- `production-copy` - Full production copy (not recommended for sensitive data)

**Quality Gates**: `automated-with-manual-review`

**Approaches**:
- `automated-with-manual-review` - Automated checks + human review
- `fully-automated` - All quality gates automated
- `manual-only` - Human review for everything (slow)

**Quality Metrics Tracking**: `required`

**Metrics to Track**:
- ✅ Code coverage (unit, integration)
- ✅ Static analysis results (linting, complexity)
- ✅ Security scan results
- ✅ Performance test results
- ✅ Defect density
- ✅ Technical debt score

**Code Review Requirements**:
- **All code**: Peer review required before merge
- **Critical code**: Two reviewers required
- **Architecture changes**: Architecture lead review required
- **Security-sensitive**: Security review required

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `phase1/artifacts/spec.md` - Always load
- ✅ `phase1/artifacts/architecture.md` - Always load
- ✅ `phase1/artifacts/constitution.md` - Always load
- ✅ `lessons-learned_memory.md` - Load for quality lessons

---

## Workflow Orchestration Settings

### Phase 2 Orchestration Workflow

**Entry Criteria**:
- ✅ Phase 1 completed and validated
- ✅ All Phase 1 artifacts approved
- ✅ Development team assembled
- ✅ Infrastructure accounts/access available

**Orchestration Approach**: `parallel-converge`

**Process Steps** (from `phase2-orchestration_prompt.md`):
1. Phase 2 kickoff and context loading
2. **Parallel Track A**: Task Decomposition → Sprint Planning
3. **Parallel Track B**: Repository Setup → Infrastructure Provisioning
4. **Parallel Track C**: Quality Planning → Test Strategy
5. Convergence: Integrate all plans
6. Dependency resolution and adjustment
7. Phase 2 validation
8. Phase 3 readiness review

**Coordination Frequency**: Weekly sync meetings across tracks

**Approval Gate**:
- **Reviewers**: Technical Lead, Product Owner, DevOps Lead
- **Criteria**: All plans complete, dependencies resolved, infrastructure ready
- **Format**: Written approval in `validation/phase2-approval.md`

---

### Task Decomposition Workflow

**Entry Criteria**:
- ✅ Phase 1 spec.md validated
- ✅ Phase 1 architecture.md validated
- ✅ Team capacity estimated

**Process Steps** (from `task-decomposition_prompt.md`):
1. Load spec and architecture
2. Extract user stories (from spec)
3. For each user story:
   - Decompose to technical tasks
   - Identify dependencies
   - Estimate effort (story points)
   - Assign to technical layer/component
4. Create dependency map
5. Identify critical path
6. Validate against constitution constraints
7. Review and refine

**Task Granularity**: 
- **Ideal task size**: 3-8 story points (half-day to 1.5 days)
- **Maximum task size**: 13 points (2-3 days)
- **Tasks > 13 points**: Must be further decomposed

**Estimation Approach**: **Planning Poker** (team-based consensus)

**Output Artifacts**:
- ✅ `task-breakdown.md` (all tasks with estimates)
- ✅ `dependency-map.md` (visual/matrix of dependencies)

---

### Sprint Planning Workflow

**Entry Criteria**:
- ✅ Task breakdown complete and validated
- ✅ Dependencies mapped
- ✅ Team capacity calculated

**Process Steps** (from `sprint-planning_prompt.md`):
1. Review task breakdown and dependencies
2. Calculate team velocity (capacity)
3. Sprint 0: Infrastructure and scaffolding
4. For each subsequent sprint:
   - Select tasks respecting dependencies
   - Stay within velocity capacity
   - Balance work across team members
   - Ensure sprint goal is coherent
5. Assign buffer for unknowns (10-15% capacity)
6. Validate sprint sequence makes sense
7. Review with team

**Sprint Goals**: Each sprint must have clear, achievable goal

**Sprint Capacity**:
- **Team size**: [N] developers
- **Sprint duration**: 2 weeks
- **Capacity per developer**: 8-10 story points per sprint
- **Total sprint capacity**: [N * 8] - [N * 10] story points
- **Reserved buffer**: 10-15% for bugs/unknowns

**Sprint 0 Focus**: 
- Repository setup complete
- Infrastructure provisioned
- CI/CD pipeline working
- Development environment documented
- Team onboarded

**Approval Gate**:
- **Reviewers**: Product Owner, Technical Lead, Team
- **Criteria**: All sprints planned, dependencies honored, achievable
- **Format**: Written approval in `validation/sprint-plan-approval.md`

**Output Artifacts**:
- ✅ `sprint-plan.md` (all sprints with tasks and goals)
- ✅ `sprint-N-plan.md` (individual sprint plans)

---

### Repository Setup Workflow

**Entry Criteria**:
- ✅ Architecture validated
- ✅ Technology stack confirmed
- ✅ Team members identified (for access)

**Process Steps** (from `repository-setup_prompt.md`):
1. Review architecture and technology decisions
2. Design repository structure
3. Create base directory layout
4. Set up dependency management (package.json, etc.)
5. Configure linting and formatting
6. Add .gitignore and other config files
7. Create README with setup instructions
8. Initialize CI/CD configuration
9. Set up branch protection rules
10. Document conventions and standards

**Repository Structure Requirements**:
- ✅ Clear separation of concerns
- ✅ Modular organization
- ✅ Consistent naming conventions
- ✅ Comprehensive README
- ✅ Contributing guidelines
- ✅ Code style guides

**Branch Protection**:
- **Main branch**: Protected, require PR reviews
- **Feature branches**: Created from main
- **Review requirements**: [1-2] approvals before merge
- **Status checks**: CI must pass before merge

**Output Artifacts**:
- ✅ `repository-structure.md` (documentation)
- ✅ Actual repository with base structure
- ✅ `setup-guide.md` (developer onboarding)

---

### Infrastructure Setup Workflow

**Entry Criteria**:
- ✅ Architecture validated
- ✅ Environment strategy defined
- ✅ Access credentials available

**Process Steps**:
1. Review architecture and infrastructure requirements
2. Provision environments (dev, staging, prod)
3. Set up database(s)
4. Configure networking and security
5. Set up monitoring and logging
6. Configure backup and disaster recovery
7. Document access and credentials (securely)
8. Validate infrastructure
9. Create infrastructure-as-code definitions

**Infrastructure-as-Code Requirements**:
- ✅ All infrastructure defined in code
- ✅ Version controlled
- ✅ Documented clearly
- ✅ Tested and validated

**Output Artifacts**:
- ✅ `environment-config.md` (all environments documented)
- ✅ Infrastructure-as-code files (Terraform, CloudFormation, etc.)
- ✅ `infrastructure-guide.md` (operations documentation)

---

### Quality Planning Workflow

**Entry Criteria**:
- ✅ Spec and architecture validated
- ✅ Test strategy approach selected

**Process Steps** (from `quality-planning_prompt.md`):
1. Review requirements and architecture
2. Identify testable scenarios
3. Design test strategy (unit, integration, E2E)
4. Define test data strategy
5. Plan quality gates
6. Set up test frameworks and tools
7. Create initial test scaffolding
8. Document testing conventions
9. Define quality metrics and targets
10. Plan code review process

**Test Types and Coverage**:
- **Unit Tests**: 80% coverage minimum
- **Integration Tests**: 60% of critical paths
- **E2E Tests**: 100% of critical user journeys
- **Performance Tests**: Key scenarios under load
- **Security Tests**: Vulnerability scanning, penetration testing

**Quality Gates**:
1. **Code Commit**: Linting, formatting checks pass
2. **Pull Request**: Unit tests pass, coverage threshold met
3. **CI Build**: All tests pass, static analysis clean
4. **Deployment to Staging**: Integration tests pass
5. **Production Deployment**: E2E tests pass, performance acceptable

**Output Artifacts**:
- ✅ `test-plan.md` (comprehensive testing strategy)
- ✅ `quality-gates.md` (definition and automation)
- ✅ Test framework scaffolding in repository
- ✅ `testing-guide.md` (conventions and standards)

---

### Phase 2 Validation Workflow

**Entry Criteria**:
- ✅ All Phase 2 artifacts in `artifacts/` directory
- ✅ Infrastructure provisioned and validated
- ✅ Repository set up with base structure

**Process Steps** (from `phase-2-completion_checklist.md`):
1. Load all Phase 2 artifacts and Phase 1 artifacts
2. Validate completeness (all required artifacts present)
3. Validate task breakdown (all requirements covered)
4. Validate sprint plan (achievable, dependencies honored)
5. Validate repository structure (standards compliant)
6. Validate infrastructure (environments working)
7. Validate quality plan (comprehensive coverage)
8. Generate validation report
9. Obtain final Phase 2 approval

**Validation Report Contents**:
- ✅ Checklist completion status
- ✅ Traceability: Requirements → Tasks → Sprints
- ✅ Dependency analysis
- ✅ Infrastructure readiness
- ✅ Quality gate definitions
- ✅ Issue summary
- ✅ Recommendation (Proceed to Phase 3 | Address Issues)

**Approval Gate**:
- **Reviewers**: Planning Agent + DevOps Lead + Quality Architect
- **Criteria**:
  - All checklists 100% complete
  - All requirements mapped to tasks
  - Dependencies resolved
  - Infrastructure ready
  - Quality gates defined
  - Zero critical blockers
- **Format**: Written approval in `validation/phase2-validation-report.md`

**Output Artifacts**:
- ✅ `validation/phase2-completion-checklist.md` (completed)
- ✅ `validation/phase2-validation-report.md`
- ✅ `validation/phase2-approval.md` (final sign-off)

---

## Quality Standards and Thresholds

### Task Breakdown Quality

**Task Breakdown Scoring** (0-100 scale):
- **Coverage** (30 points): All requirements have tasks
- **Granularity** (20 points): Tasks sized appropriately (3-13 points)
- **Dependencies** (20 points): Dependencies identified and mapped
- **Clarity** (15 points): Task descriptions clear and actionable
- **Estimation** (15 points): Estimates reasonable and justified

**Minimum Passing Score**: 80/100

**Traceability Requirements**:
- **Requirements → Tasks**: 100% coverage of critical requirements, 95% of all
- **Tasks → Sprint**: All tasks assigned to a sprint
- **Orphaned tasks**: 0 tasks without parent requirement

---

### Sprint Plan Quality

**Sprint Plan Scoring** (0-100 scale):
- **Feasibility** (25 points): Within team capacity
- **Dependencies** (25 points): Dependencies respected in sequence
- **Balance** (20 points): Work distributed evenly across team
- **Goals** (15 points): Each sprint has clear, achievable goal
- **Buffer** (15 points): Appropriate buffer for unknowns (10-15%)

**Minimum Passing Score**: 80/100

**Sprint Health Metrics**:
- **Overcommitment**: Sprints should be at 85-95% of capacity (not 100%+)
- **Dependency violations**: 0 sprints with unresolved dependencies
- **Goal clarity**: 100% of sprints have defined goals

---

### Repository Structure Quality

**Repository Scoring** (0-100 scale):
- **Organization** (25 points): Clear, logical structure
- **Documentation** (25 points): README, setup guide, conventions
- **Configuration** (20 points): Proper config files, tooling set up
- **Standards** (15 points): Consistent naming, formatting
- **Conventions** (15 points): Clear conventions documented

**Minimum Passing Score**: 80/100

---

### Infrastructure Readiness

**Infrastructure Scoring** (0-100 scale):
- **Completeness** (25 points): All environments provisioned
- **Configuration** (20 points): Properly configured and secured
- **Documentation** (20 points): Operations guide complete
- **IaC** (20 points): Infrastructure-as-code defined
- **Validation** (15 points): Environments tested and working

**Minimum Passing Score**: 85/100

---

### Quality Plan Completeness

**Quality Plan Scoring** (0-100 scale):
- **Coverage** (25 points): All test types addressed
- **Strategy** (20 points): Clear testing strategy
- **Gates** (20 points): Quality gates defined and automated
- **Tools** (15 points): Test frameworks set up
- **Metrics** (20 points): Quality metrics defined and trackable

**Minimum Passing Score**: 80/100

---

## Handoff Criteria to Phase 3

Phase 2 is **complete and ready for Phase 3** when:

### Artifact Completion
- ✅ `task-breakdown.md` in `artifacts/` with approval
- ✅ `dependency-map.md` in `artifacts/`
- ✅ `sprint-plan.md` in `artifacts/` with approval
- ✅ All individual `sprint-N-plan.md` files in `artifacts/sprints/`
- ✅ `repository-structure.md` in `artifacts/`
- ✅ `environment-config.md` in `artifacts/`
- ✅ `test-plan.md` in `artifacts/` with approval
- ✅ `quality-gates.md` in `artifacts/`

### Infrastructure Readiness
- ✅ Repository created with base structure
- ✅ All environments provisioned (dev, staging, prod)
- ✅ CI/CD pipeline configured (basic)
- ✅ Database(s) set up
- ✅ Monitoring and logging configured
- ✅ Developer onboarding documentation complete

### Planning Completeness
- ✅ All requirements mapped to tasks
- ✅ All tasks estimated and assigned to sprints
- ✅ Dependencies identified and respected in sprint sequence
- ✅ Critical path identified
- ✅ Team capacity allocated
- ✅ Sprint 0 (setup sprint) fully defined

### Quality Framework
- ✅ Test strategy defined
- ✅ Test frameworks set up in repository
- ✅ Quality gates defined and documented
- ✅ Code review process established
- ✅ Quality metrics and targets defined

### Validation Complete
- ✅ Phase 2 validation report generated
- ✅ All checklists 100% complete
- ✅ Traceability validated (Requirements → Tasks → Sprints)
- ✅ All artifacts score ≥80
- ✅ Zero critical blockers
- ✅ Infrastructure validated as working

### Approvals Obtained
- ✅ Task breakdown approval
- ✅ Sprint plan approval
- ✅ Infrastructure sign-off
- ✅ Quality plan approval
- ✅ Final Phase 2 approval from all stakeholders

### Team Readiness
- ✅ Development team assembled
- ✅ Team members have repository access
- ✅ Team members have environment access
- ✅ Developer setup guide validated (at least one dev successfully set up)
- ✅ Team briefed on sprint 0 goals

---

## Customization Guidelines

### When to Modify This Config

**Adjust Agent Settings** when:
- Team size changes significantly
- Project complexity varies
- Infrastructure requirements change
- Organizational standards evolve

**Adjust Workflows** when:
- Process inefficiencies identified
- New tools or practices adopted
- Integration requirements change
- Team feedback suggests improvements

**Adjust Quality Standards** when:
- Risk tolerance changes
- Team maturity evolves
- Time constraints require adjustment
- Historical data informs better thresholds

### How to Modify

1. **Document the change**: Why, what, expected impact
2. **Update this config**: Make changes explicit
3. **Communicate to team**: Ensure all stakeholders aware
4. **Update related files**: Agents, workflows, templates
5. **Record in decisions**: Add to `decisions_memory.md`
6. **Validate**: Test on next project phase
7. **Retrospective**: Evaluate effectiveness after 1-2 sprints

---

## Version History

| Version | Date | Changed By | Changes | Reason |
|---------|------|------------|---------|--------|
| 1.0 | 2025-10-31 | System Architect | Initial creation | Phase 2 system establishment |

---

## Related Files

**Agent Instructions**:
- `planning-agent_instructions.md`
- `devops-scaffolder_instructions.md`
- `quality-architect_instructions.md`

**Workflow Prompts**:
- `phase2-orchestration_prompt.md`
- `task-decomposition_prompt.md`
- `sprint-planning_prompt.md`
- `repository-setup_prompt.md`
- `quality-planning_prompt.md`

**Templates**:
- `task-breakdown_template.md`
- `sprint-plan_template.md`
- `dependency-map_template.md`
- `test-plan_template.md`
- `repository-structure_template.md`
- `environment-config_template.md`

**Checklists**:
- `phase-2-completion_checklist.md`

**Context**:
- `phase2-context.md` (current state of Phase 2)

---

*This configuration file governs Phase 2 execution. Treat as living document - update based on learnings and evolving needs.*
