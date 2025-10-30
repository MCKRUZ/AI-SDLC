# Quality Planning Workflow

## Purpose

This workflow guides you through the systematic process of defining a comprehensive quality strategy, test plan, and quality standards for the project. The output is a complete quality framework that ensures high-quality software delivery throughout all phases.

**What This Workflow Accomplishes**:
- Defines comprehensive test strategy across all testing levels
- Establishes quality metrics and success criteria
- Creates test automation approach and framework selection
- Defines code quality standards and review processes
- Establishes performance, security, and accessibility testing approaches
- Creates quality gates and checkpoints throughout SDLC
- Defines Definition of Done (DoD) and acceptance criteria standards
- Plans test data management and test environment strategy
- Establishes bug triage and quality escalation processes

**What This Workflow Does NOT Do**:
- Write actual test code (that's Phase 3)
- Execute tests (that's Phase 3)
- Fix quality issues (that's Phase 3)
- Make architecture decisions (that's Phase 1)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Constitution** (`constitution.md`) - Quality standards and constraints
- [ ] **Requirements Specification** (`spec.md`) - All functional and non-functional requirements
- [ ] **Architecture Document** (`architecture.md`) - Technical design and components
- [ ] **Task Breakdown** (`task-breakdown.md`) - All development tasks
- [ ] **Sprint Plan** (`sprint-plan.md`) - Sprint assignments and timeline
- [ ] **Technology Stack** - Chosen languages, frameworks, and tools
- [ ] **Risk Register** - Known risks that may impact quality
- [ ] **Team Context** (`team-context.md`) - Team skills and testing capabilities

### Agent Setup

You should be in **Quality Architect Agent** mode with all context loaded:

```markdown
You are the Quality Architect Agent, an expert in test strategy, quality 
assurance, test automation, performance testing, security testing, and 
quality management.

Context loaded:
- Constitution.md (quality standards)
- Spec.md (requirements to test)
- Architecture.md (technical design)
- Task-breakdown.md (development tasks)
- Sprint-plan.md (timeline)
- Team-context.md (testing capabilities)

Your mission: Create a comprehensive quality strategy that ensures high-quality 
software delivery through systematic testing, quality gates, and continuous 
quality improvement.

Ready to begin quality planning.
```

---

## Workflow Steps

### Step 1: Define Test Strategy (2-3 hours)

#### Objective
Create a comprehensive test strategy covering all testing levels and types.

#### Actions

**1.1 Define Testing Pyramid**

```markdown
## Testing Pyramid Strategy

### Level 1: Unit Tests (70% of tests)
**Purpose**: Test individual components in isolation
**Scope**: 
- All business logic functions
- All utility functions
- All data transformations
- All validation logic

**Target Coverage**: ≥80% code coverage
**Execution**: Every commit in CI pipeline
**Ownership**: Developers write alongside code
**Tools**: 
- Backend: xUnit, NUnit, or MSTest (C#), Jest (Node.js)
- Frontend: Vitest, Jest, Testing Library

**Success Criteria**:
- All unit tests pass
- Code coverage ≥80%
- Tests run in <2 minutes
- No flaky tests

---

### Level 2: Integration Tests (20% of tests)
**Purpose**: Test interactions between components
**Scope**:
- API endpoint testing (request/response)
- Database integration testing
- External service integration (with mocks)
- Message queue integration
- Authentication/authorization flows

**Target Coverage**: All critical integration points
**Execution**: Every PR in CI pipeline
**Ownership**: Developers write for their features
**Tools**:
- Backend: xUnit with WebApplicationFactory, Testcontainers
- Frontend: Testing Library with MSW (Mock Service Worker)

**Success Criteria**:
- All integration tests pass
- Critical paths validated
- Tests run in <5 minutes
- Real database used (Testcontainers)

---

### Level 3: End-to-End Tests (10% of tests)
**Purpose**: Test complete user workflows
**Scope**:
- Critical user journeys (happy paths)
- Key business processes
- Cross-cutting concerns (auth, error handling)

**Target Coverage**: Top 10 user workflows
**Execution**: 
- Every merge to develop
- Before every production deployment
**Ownership**: QA team or dedicated developers
**Tools**: Playwright, Cypress

**Success Criteria**:
- All E2E tests pass
- Tests run in <15 minutes
- Tests stable (not flaky)
- Run against production-like environment

---

### Testing Distribution Summary

```
Unit Tests:        70% (Fast, Many)
Integration Tests: 20% (Medium, Some)
E2E Tests:        10% (Slow, Few)
```

This pyramid ensures fast feedback while maintaining confidence in the system.
```

**1.2 Define Non-Functional Testing Strategy**

```markdown
## Non-Functional Testing Strategy

### Performance Testing

**Scope**:
- Load testing (expected load)
- Stress testing (beyond expected load)
- Endurance testing (sustained load)
- Spike testing (sudden load increases)

**Key Metrics**:
- Response time: p50, p95, p99
- Throughput: requests per second
- Error rate: <0.1% under normal load
- Resource utilization: CPU, memory, database connections

**Target Performance** (from NFRs in spec.md):
- API response time: p95 <500ms
- Page load time: p95 <2 seconds
- Concurrent users: 1000+ without degradation
- Database query time: p95 <100ms

**Tools**: 
- k6 for load testing
- JMeter as alternative
- Azure Load Testing (if using Azure)

**Execution**:
- Performance baseline: Sprint 1
- Performance tests: Every sprint
- Load tests: Before production releases

---

### Security Testing

**Scope**:
- OWASP Top 10 vulnerabilities
- Authentication/authorization testing
- Input validation and sanitization
- SQL injection, XSS, CSRF testing
- Dependency vulnerability scanning
- Secrets scanning
- Container security scanning

**Tools**:
- OWASP ZAP for dynamic scanning
- Trivy for container scanning
- GitHub Advanced Security (Dependabot, code scanning)
- SonarQube for static analysis

**Execution**:
- Static analysis: Every commit
- Dependency scanning: Daily
- Dynamic security scanning: Weekly
- Penetration testing: Before production launch, then quarterly

**Security Gates**:
- No critical or high vulnerabilities in production
- All secrets must be in vault (not in code)
- All inputs must be validated
- All API endpoints must have auth (except public endpoints)

---

### Accessibility Testing

**Scope**:
- WCAG 2.1 Level AA compliance
- Keyboard navigation
- Screen reader compatibility
- Color contrast
- ARIA attributes

**Tools**:
- axe DevTools
- Lighthouse accessibility audit
- NVDA or JAWS screen reader

**Execution**:
- Automated checks: Every PR
- Manual audit: Every major feature
- Full accessibility audit: Before production launch

**Target**: WCAG 2.1 Level AA compliance for all user-facing features

---

### Usability Testing

**Scope**:
- User task completion
- User satisfaction
- Interface intuitiveness
- Error recovery

**Methods**:
- Moderated usability sessions
- Unmoderated remote testing
- A/B testing
- User feedback surveys

**Execution**:
- Prototype testing: During design phase
- Feature testing: After Sprint Review
- Overall usability: Before production launch

---

### Compatibility Testing

**Scope**:
- Browser compatibility (Chrome, Firefox, Safari, Edge)
- Device compatibility (Desktop, tablet, mobile)
- Operating system compatibility
- Screen size responsiveness

**Tools**:
- BrowserStack or Sauce Labs
- Chrome DevTools device emulation
- Playwright (multi-browser)

**Execution**:
- Browser tests: Every sprint
- Device tests: Every major release

**Supported Browsers** (from constitution.md):
- Chrome (last 2 versions)
- Firefox (last 2 versions)
- Safari (last 2 versions)
- Edge (last 2 versions)
```

**1.3 Map Requirements to Tests**

```markdown
## Requirements Traceability Matrix

| Requirement ID | Type | Priority | Testing Level | Test Count | Owner |
|----------------|------|----------|---------------|------------|-------|
| REQ-001 | Functional | P0 | Unit + Integration + E2E | 15 | Dev Team |
| REQ-002 | Functional | P0 | Unit + Integration | 8 | Dev Team |
| REQ-003 | NFR - Performance | P0 | Performance | 5 | QA + DevOps |
| REQ-004 | NFR - Security | P0 | Security | 10 | Security + QA |
| ... | ... | ... | ... | ... | ... |

**Coverage Analysis**:
- Total requirements: [N]
- Requirements with tests: [M]
- Coverage: [M/N * 100]%

**Goal**: 100% of P0 requirements have tests, 90% of P1, 70% of P2

**Test Estimation**:
- Total estimated tests: [Sum]
- Unit tests: ~[70%]
- Integration tests: ~[20%]
- E2E tests: ~[10%]
```

**Output**: Comprehensive test strategy document

---

### Step 2: Define Quality Metrics and Success Criteria (1 hour)

#### Objective
Establish measurable quality metrics and success criteria.

#### Actions

**2.1 Define Code Quality Metrics**

```markdown
## Code Quality Metrics

### Code Coverage
- **Unit Test Coverage**: ≥80% line coverage
- **Branch Coverage**: ≥75%
- **Critical Path Coverage**: 100%
- **Measurement**: Coverlet (.NET), Istanbul (JavaScript)
- **Enforcement**: CI pipeline fails if below threshold

### Code Complexity
- **Cyclomatic Complexity**: ≤10 per method
- **Cognitive Complexity**: ≤15 per method
- **Class Complexity**: ≤50
- **Measurement**: SonarQube, code analyzers
- **Enforcement**: Warning in code review if exceeded

### Code Duplication
- **Duplication Rate**: <3%
- **Minimum Duplication Block**: 3 lines
- **Measurement**: SonarQube
- **Enforcement**: Addressed during code review

### Technical Debt
- **Technical Debt Ratio**: <5%
- **Blocker Issues**: 0
- **Critical Issues**: ≤5
- **Measurement**: SonarQube
- **Enforcement**: Blocker issues must be fixed before merge

### Code Review Metrics
- **PR Size**: ≤500 lines changed (recommended)
- **Review Time**: <24 hours for P0, <48 hours for P1
- **Approval Requirements**: 2 approvals for main, 1 for develop
- **Comments Addressed**: 100%
```

**2.2 Define Test Quality Metrics**

```markdown
## Test Quality Metrics

### Test Reliability
- **Test Flakiness**: <1% flake rate
- **Test Failure Rate**: <5% in CI
- **Test Retry Rate**: <10%
- **Measurement**: CI pipeline analytics
- **Action**: Flaky tests must be fixed or removed

### Test Execution Performance
- **Unit Tests**: <2 minutes total
- **Integration Tests**: <5 minutes total
- **E2E Tests**: <15 minutes total
- **Measurement**: CI pipeline timing
- **Action**: Optimize slow tests

### Test Maintenance
- **Test Update Frequency**: Tests updated with code changes
- **Test Deletion Rate**: Remove obsolete tests
- **Test Documentation**: All complex tests documented
- **Measurement**: Code review feedback
```

**2.3 Define Defect Metrics**

```markdown
## Defect Quality Metrics

### Defect Density
- **Target**: <0.5 defects per 100 lines of code
- **Critical Defects**: <1 per sprint
- **Measurement**: Bug tracking system

### Defect Leakage
- **Definition**: Defects found in production vs. pre-production
- **Target**: <10% defect leakage
- **Measurement**: Production bugs / Total bugs

### Defect Resolution Time
- **P0 (Blocker)**: <4 hours
- **P1 (Critical)**: <24 hours
- **P2 (Major)**: <1 week
- **P3 (Minor)**: <2 weeks
- **Measurement**: Bug tracking system

### Defect Categories
Track defects by category:
- **Functional**: Business logic errors
- **UI/UX**: Interface issues
- **Performance**: Slowness, timeouts
- **Security**: Vulnerabilities
- **Data**: Data corruption, loss
- **Integration**: Integration failures

**Goal**: Identify patterns to prevent future defects
```

**2.4 Define Release Quality Criteria**

```markdown
## Release Quality Gates

### Sprint Quality Gate (Before Sprint End)
- [ ] All planned tests pass
- [ ] Code coverage ≥80%
- [ ] No P0 or P1 bugs outstanding
- [ ] All code reviewed and approved
- [ ] Performance benchmarks met
- [ ] Security scan passed

### Pre-Production Quality Gate (Before Deploy to Staging)
- [ ] All sprint quality gates passed
- [ ] Integration tests pass
- [ ] E2E tests pass
- [ ] Load tests pass
- [ ] Security scan passed (no critical vulnerabilities)
- [ ] Accessibility scan passed
- [ ] Database migrations tested
- [ ] Rollback plan documented

### Production Quality Gate (Before Deploy to Production)
- [ ] All pre-production quality gates passed
- [ ] Smoke tests pass in staging
- [ ] Performance tests pass in staging
- [ ] UAT completed and signed off
- [ ] Release notes completed
- [ ] Monitoring and alerts configured
- [ ] Rollback tested in staging
- [ ] Change approval obtained
```

**Output**: Measurable quality metrics and clear success criteria

---

### Step 3: Plan Test Automation Framework (2-3 hours)

#### Objective
Design test automation approach and select testing frameworks.

#### Actions

**3.1 Select Testing Tools and Frameworks**

```markdown
## Testing Tools Selection

### Unit Testing
**Backend (C#/.NET)**:
- **Framework**: xUnit
- **Mocking**: Moq
- **Assertions**: FluentAssertions
- **Coverage**: Coverlet
- **Rationale**: Industry standard, excellent Visual Studio integration

**Frontend (TypeScript/React)**:
- **Framework**: Vitest
- **Testing Library**: React Testing Library
- **Mocking**: MSW (Mock Service Worker)
- **Coverage**: V8 (built into Vitest)
- **Rationale**: Fast, Vite-native, good DX

### Integration Testing
**Backend**:
- **Framework**: xUnit with WebApplicationFactory
- **Database**: Testcontainers (PostgreSQL)
- **HTTP Client**: HttpClient
- **Rationale**: Real dependencies, isolated test databases

**Frontend**:
- **Framework**: Vitest
- **API Mocking**: MSW
- **Rationale**: Test components with API integration

### End-to-End Testing
**Framework**: Playwright
- **Multi-browser**: Chromium, Firefox, WebKit
- **Parallel execution**: Yes
- **Visual comparison**: Yes (if needed)
- **Rationale**: Modern, fast, reliable, great debugging

### Performance Testing
**Framework**: k6
- **Load testing**: Yes
- **Stress testing**: Yes
- **Scripting**: JavaScript
- **Integrations**: Grafana, Prometheus
- **Rationale**: Modern, cloud-native, excellent for CI/CD

### Security Testing
**Tools**:
- **SAST**: SonarQube
- **DAST**: OWASP ZAP
- **Dependency Scanning**: GitHub Dependabot, Trivy
- **Secret Scanning**: GitHub Advanced Security
- **Container Scanning**: Trivy

### API Testing
**Framework**: xUnit with WebApplicationFactory (integrated with backend tests)
- **Or**: Postman/Newman for API testing

### Accessibility Testing
**Tools**:
- **Automated**: axe-core, Lighthouse
- **Manual**: NVDA screen reader
```

**3.2 Design Test Data Strategy**

```markdown
## Test Data Management Strategy

### Test Data Principles
1. **Isolation**: Each test uses independent data
2. **Repeatability**: Tests produce same results every run
3. **Maintainability**: Test data easy to update
4. **Realism**: Test data resembles production data (anonymized)

### Test Data Sources

**Unit Tests**:
- **Source**: Inline test data in test code
- **Strategy**: Builders, factories, or direct instantiation
- **Example**:
  ```csharp
  var user = new UserBuilder()
      .WithEmail("test@example.com")
      .WithRole("Admin")
      .Build();
  ```

**Integration Tests**:
- **Source**: Testcontainers with seed data
- **Strategy**: Fresh database per test class, seeded with minimal data
- **Cleanup**: Database reset between test classes

**E2E Tests**:
- **Source**: Dedicated test environment with stable seed data
- **Strategy**: Known test accounts and test data
- **Cleanup**: Data reset after test suite

**Performance Tests**:
- **Source**: Production-like data (anonymized)
- **Volume**: Sufficient data to simulate real load
- **Strategy**: Load data before test, cleanup after

### Test Data Examples

**User Data**:
```csharp
public class TestUsers
{
    public static User Admin => new()
    {
        Email = "admin@test.com",
        Password = "Test123!",
        Role = "Admin"
    };

    public static User RegularUser => new()
    {
        Email = "user@test.com",
        Password = "Test123!",
        Role = "User"
    };
}
```

**Database Seed Data**:
```sql
-- Test data for integration tests
INSERT INTO Users (Email, FirstName, LastName, Role)
VALUES 
    ('admin@test.com', 'Admin', 'User', 'Admin'),
    ('user@test.com', 'Regular', 'User', 'User');
```

### Test Data Security
- **No Production Data**: Never use real production data in tests
- **Anonymization**: If using production-like data, fully anonymize
- **Sensitive Data**: Never commit passwords, API keys, or PII to repo
- **Compliance**: Follow GDPR, CCPA, and other data regulations
```

**3.3 Design Test Environment Strategy**

```markdown
## Test Environment Strategy

### Environment Tier

**Local Development**:
- **Purpose**: Developer testing during development
- **Infrastructure**: Docker Compose
- **Database**: Testcontainers
- **Data**: Minimal seed data
- **Access**: All developers

**CI/CD Pipeline**:
- **Purpose**: Automated testing on every commit
- **Infrastructure**: GitHub Actions runners
- **Database**: Testcontainers (ephemeral)
- **Data**: Seed data in tests
- **Access**: Automated only

**Dev/Integration Environment**:
- **Purpose**: Integration testing, manual testing
- **Infrastructure**: Cloud-based (Azure, AWS)
- **Database**: Dedicated dev database
- **Data**: Sample data, refreshed weekly
- **Access**: Development team
- **URL**: https://dev.example.com

**Staging/Pre-Production**:
- **Purpose**: UAT, final testing before production
- **Infrastructure**: Production-like (same specs)
- **Database**: Production-like data (anonymized)
- **Data**: Production data snapshot (sanitized)
- **Access**: QA team, stakeholders
- **URL**: https://staging.example.com

**Production**:
- **Purpose**: Live system
- **Infrastructure**: Production
- **Database**: Production database
- **Data**: Real data
- **Access**: Limited, monitored
- **URL**: https://www.example.com

### Environment Configuration
Each environment has:
- Independent database
- Independent secrets/credentials
- Independent feature flags
- Monitoring and logging
- Backup and disaster recovery
```

**Output**: Complete test automation framework design

---

### Step 4: Define Code Quality Standards (1-2 hours)

#### Objective
Establish code quality standards and review processes.

#### Actions

**4.1 Define Coding Standards**

```markdown
## Coding Standards

### General Principles
1. **SOLID Principles**: Follow SOLID design principles
2. **DRY**: Don't Repeat Yourself
3. **KISS**: Keep It Simple, Stupid
4. **YAGNI**: You Aren't Gonna Need It
5. **Clean Code**: Write self-documenting code

### C# Backend Standards

**Naming Conventions**:
- Classes: PascalCase (e.g., `UserService`)
- Methods: PascalCase (e.g., `GetUserById`)
- Variables: camelCase (e.g., `userId`)
- Constants: PascalCase (e.g., `MaxRetryAttempts`)
- Private fields: _camelCase (e.g., `_repository`)
- Interfaces: IPascalCase (e.g., `IUserRepository`)

**Code Organization**:
- One class per file
- File name matches class name
- Keep classes focused (Single Responsibility)
- Limit class size to <500 lines
- Limit method size to <50 lines

**Error Handling**:
- Use exceptions for exceptional cases
- Don't swallow exceptions
- Log all errors with context
- Return Result<T> for expected failures

**Comments**:
- Use XML documentation for public APIs
- Write comments for "why", not "what"
- Keep comments up-to-date
- Remove commented-out code

**Example**:
```csharp
/// <summary>
/// Retrieves a user by their unique identifier.
/// </summary>
/// <param name="userId">The unique identifier of the user.</param>
/// <returns>The user if found, null otherwise.</returns>
public async Task<User?> GetUserByIdAsync(int userId)
{
    if (userId <= 0)
        throw new ArgumentException("User ID must be positive", nameof(userId));

    return await _context.Users
        .Include(u => u.Roles)
        .FirstOrDefaultAsync(u => u.Id == userId);
}
```

### TypeScript Frontend Standards

**Naming Conventions**:
- Components: PascalCase (e.g., `UserProfile`)
- Functions: camelCase (e.g., `fetchUserData`)
- Variables: camelCase (e.g., `userName`)
- Constants: UPPER_SNAKE_CASE (e.g., `MAX_RETRY_ATTEMPTS`)
- Types/Interfaces: PascalCase (e.g., `UserData`, `IUserService`)

**Code Organization**:
- One component per file
- File name matches component name
- Use named exports for clarity
- Keep components focused and small
- Limit component size to <300 lines

**React Best Practices**:
- Use functional components with hooks
- Extract custom hooks for reusable logic
- Use TypeScript for type safety
- Avoid prop drilling (use Context or state management)
- Memoize expensive computations

**Error Handling**:
- Use try-catch for async operations
- Handle errors at appropriate boundaries
- Show user-friendly error messages
- Log errors for debugging

**Comments**:
- Use JSDoc for exported functions
- Comment complex logic
- Remove unused code
- Keep comments updated

**Example**:
```typescript
interface User {
  id: number;
  email: string;
  firstName: string;
  lastName: string;
}

/**
 * Fetches user data from the API.
 * @param userId - The ID of the user to fetch
 * @returns The user data or null if not found
 */
async function fetchUser(userId: number): Promise<User | null> {
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) {
      if (response.status === 404) return null;
      throw new Error(`Failed to fetch user: ${response.statusText}`);
    }
    return await response.json();
  } catch (error) {
    console.error('Error fetching user:', error);
    throw error;
  }
}
```

### SQL Standards
- Use parameterized queries (prevent SQL injection)
- Name tables: PascalCase, plural (e.g., `Users`)
- Name columns: PascalCase (e.g., `FirstName`)
- Always use primary keys
- Index frequently queried columns
- Avoid SELECT *, specify columns

### Git Commit Standards
Follow Conventional Commits:
```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types**:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting)
- `refactor`: Code refactoring
- `test`: Test changes
- `chore`: Build, CI, dependencies

**Example**:
```
feat(auth): add password reset functionality

Implement password reset flow with email verification.
Users can now request a password reset link via email.

Closes #123
```
```

**4.2 Define Code Review Process**

```markdown
## Code Review Process

### Review Requirements

**All Code Must Be Reviewed**:
- 2 approvals required for main branch
- 1 approval required for develop branch
- Code owner approval required for core files
- No self-merge allowed

**Reviewer Responsibilities**:
1. Check code functionality and logic
2. Verify tests are adequate
3. Ensure code follows standards
4. Look for security issues
5. Verify error handling
6. Check for performance issues
7. Ensure documentation updated

### Review Checklist

**Functionality**:
- [ ] Code does what it's supposed to do
- [ ] Edge cases handled
- [ ] Error cases handled
- [ ] Business logic is correct

**Quality**:
- [ ] Code follows coding standards
- [ ] Code is readable and maintainable
- [ ] No unnecessary complexity
- [ ] No code duplication
- [ ] Good naming conventions

**Testing**:
- [ ] Unit tests included
- [ ] Integration tests if needed
- [ ] Tests are meaningful
- [ ] Tests pass locally
- [ ] Code coverage maintained

**Security**:
- [ ] No hardcoded secrets
- [ ] Input validation present
- [ ] Authentication/authorization correct
- [ ] No SQL injection vulnerabilities
- [ ] No XSS vulnerabilities

**Documentation**:
- [ ] API documentation updated
- [ ] README updated if needed
- [ ] Complex logic commented
- [ ] Breaking changes documented

### Review Best Practices

**For Authors**:
- Keep PRs small (<500 lines)
- Write clear PR description
- Self-review before requesting review
- Respond to feedback promptly
- Update based on feedback

**For Reviewers**:
- Review within 24 hours (48 hours max)
- Be respectful and constructive
- Explain the "why" behind suggestions
- Distinguish between blocking and non-blocking comments
- Approve when ready, even with minor suggestions

**Review Comments**:
- **MUST**: Blocking issue, must be fixed
- **SHOULD**: Strong suggestion, should be fixed
- **CONSIDER**: Non-blocking suggestion
- **QUESTION**: Need clarification
- **PRAISE**: Acknowledge good work

### Automated Checks (Must Pass Before Review)
- [ ] Build succeeds
- [ ] All tests pass
- [ ] Linting passes
- [ ] Code coverage maintained
- [ ] No security vulnerabilities introduced
```

**Output**: Clear code quality standards and review process

---

### Step 5: Define Quality Gates and Checkpoints (1 hour)

#### Objective
Establish quality gates at key SDLC checkpoints.

#### Actions

**5.1 Define Phase Quality Gates**

```markdown
## SDLC Quality Gates

### Phase 0 (Discovery) Quality Gate
- [ ] Problem statement validated
- [ ] Stakeholder alignment achieved
- [ ] Feasibility confirmed
- [ ] Risks identified and assessed
- [ ] Success criteria defined

### Phase 1 (Specification & Design) Quality Gate
- [ ] Requirements complete and reviewed
- [ ] Architecture reviewed and approved
- [ ] Non-functional requirements defined
- [ ] API contracts defined
- [ ] Data model reviewed
- [ ] All phase 1 artifacts validated

### Phase 2 (Project Planning) Quality Gate
- [ ] Task breakdown complete
- [ ] Sprint plan created and committed
- [ ] Quality strategy defined ← Current
- [ ] Repository infrastructure ready
- [ ] Team onboarded
- [ ] Sprint 0 ready to begin

### Phase 3 (Implementation) Quality Gate - Per Sprint
- [ ] All planned features completed
- [ ] All tests pass
- [ ] Code coverage ≥80%
- [ ] No P0/P1 bugs outstanding
- [ ] Code reviewed and approved
- [ ] Demo successful
- [ ] Retrospective completed

### Phase 4 (Testing & Deployment) Quality Gate
- [ ] All features tested
- [ ] UAT completed and signed off
- [ ] Performance targets met
- [ ] Security scan passed
- [ ] Accessibility audit passed
- [ ] Production deployment tested in staging
- [ ] Rollback plan tested
- [ ] Monitoring configured

### Phase 5 (Production Launch) Quality Gate
- [ ] All previous gates passed
- [ ] Smoke tests pass in production
- [ ] Monitoring shows healthy metrics
- [ ] No critical issues in first 24 hours
- [ ] Rollback plan ready
- [ ] Post-launch review scheduled
```

**5.2 Define CI/CD Quality Gates**

```markdown
## CI/CD Pipeline Quality Gates

### Commit Quality Gate (On Every Commit)
- [ ] Build succeeds
- [ ] Unit tests pass
- [ ] Linting passes
- [ ] Code formatting correct
- **Action if Fail**: Cannot merge PR

### Pull Request Quality Gate (On Every PR)
- [ ] All commit gates passed
- [ ] Integration tests pass
- [ ] Code coverage maintained or improved
- [ ] No new security vulnerabilities
- [ ] Code review approved
- **Action if Fail**: Cannot merge PR

### Develop Branch Quality Gate (After Merge to Develop)
- [ ] All PR gates passed
- [ ] E2E tests pass
- [ ] Deploy to dev environment succeeds
- [ ] Smoke tests pass in dev
- **Action if Fail**: Rollback merge, fix issues

### Main Branch Quality Gate (Before Merge to Main)
- [ ] All develop gates passed
- [ ] Deploy to staging succeeds
- [ ] Full regression tests pass
- [ ] Performance tests pass
- [ ] Security scan passed
- [ ] UAT signed off
- **Action if Fail**: Cannot merge to main

### Production Deployment Quality Gate
- [ ] All main branch gates passed
- [ ] Change approval obtained
- [ ] Deployment window approved
- [ ] Rollback plan documented
- [ ] Deploy to production succeeds
- [ ] Smoke tests pass in production
- **Action if Fail**: Execute rollback
```

**Output**: Quality gates defined at all key checkpoints

---

### Step 6: Plan Bug Triage and Management Process (1 hour)

#### Objective
Establish bug reporting, triage, and resolution processes.

#### Actions

**6.1 Define Bug Severity Levels**

```markdown
## Bug Severity Classification

### P0: Blocker (Critical)
**Definition**: System is completely unusable or data loss/corruption occurs
**Examples**:
- Application crashes on startup
- Complete system outage
- Data loss or corruption
- Security breach or vulnerability actively exploited

**Response Time**: Immediate (within 1 hour)
**Resolution Time**: 4 hours
**Who Fixes**: Senior developers drop everything
**Escalation**: Notify leadership immediately

---

### P1: Critical (High)
**Definition**: Major feature broken, but workaround exists
**Examples**:
- Login not working for some users
- Payment processing fails intermittently
- Major feature completely broken
- Performance severely degraded

**Response Time**: 4 hours
**Resolution Time**: 24 hours (1 business day)
**Who Fixes**: Senior developers prioritize
**Escalation**: Notify team lead if not resolved in 24h

---

### P2: Major (Medium)
**Definition**: Feature partially broken or degraded
**Examples**:
- Non-critical feature not working
- Visual bugs affecting user experience
- Performance degraded but usable
- Error messages confusing

**Response Time**: 24 hours
**Resolution Time**: 1 week
**Who Fixes**: Assigned to next sprint or current sprint if capacity
**Escalation**: Review in sprint planning

---

### P3: Minor (Low)
**Definition**: Cosmetic issues, minor inconveniences
**Examples**:
- Text alignment issues
- Minor UI inconsistencies
- Typos in UI
- Feature request disguised as bug

**Response Time**: 1 week
**Resolution Time**: 2 weeks or backlog
**Who Fixes**: Addressed when time permits
**Escalation**: None (unless becomes more severe)

---

### P4: Trivial
**Definition**: Very minor issues with no impact
**Examples**:
- Extremely rare edge case
- Barely noticeable UI issue
- Nice-to-have improvements

**Response Time**: Next sprint planning
**Resolution Time**: Backlog
**Who Fixes**: May not fix
**Escalation**: None
```

**6.2 Define Bug Triage Process**

```markdown
## Bug Triage Workflow

### Step 1: Bug Reported
**Who**: Anyone (user, tester, developer, stakeholder)
**Where**: Bug tracking system (GitHub Issues, Jira, Azure DevOps)
**Required Info**:
- Title: Clear, concise description
- Description: Steps to reproduce
- Expected behavior
- Actual behavior
- Environment (browser, OS, version)
- Screenshots/videos
- Logs/error messages

**Template**:
```
**Title**: [Component] Brief description

**Description**:
[Detailed description of the bug]

**Steps to Reproduce**:
1. Go to...
2. Click on...
3. See error...

**Expected Behavior**:
[What should happen]

**Actual Behavior**:
[What actually happens]

**Environment**:
- Browser: Chrome 120
- OS: Windows 11
- Version: v1.2.3

**Screenshots**:
[Attach screenshots]

**Additional Context**:
[Any other relevant information]
```

### Step 2: Initial Triage (Within 24 hours)
**Who**: QA lead or product manager
**Actions**:
1. Verify bug is reproducible
2. Assign severity (P0-P4)
3. Assign category (Functional, UI, Performance, Security)
4. Assign component/area
5. Add to appropriate sprint or backlog
6. Notify relevant team members

**Triage Criteria**:
- Is it really a bug? (vs. feature request)
- Is it reproducible?
- What's the impact? (users affected, frequency)
- What's the severity?
- Is there a workaround?

### Step 3: Assignment
**Who**: Team lead or project manager
**Assigned To**:
- P0: Senior developer immediately
- P1: Senior or mid developer in current sprint
- P2: Any developer in next sprint
- P3/P4: Backlog for future sprint

### Step 4: Investigation and Fix
**Who**: Assigned developer
**Actions**:
1. Reproduce the bug locally
2. Investigate root cause
3. Implement fix
4. Write regression test
5. Create pull request
6. Link PR to bug report

### Step 5: Verification
**Who**: Original reporter or QA
**Actions**:
1. Verify fix in dev/staging environment
2. Test related functionality (regression)
3. Confirm issue resolved
4. Close bug report

### Step 6: Retrospective (For P0/P1)
**Who**: Team
**Actions**:
1. Root cause analysis
2. Identify prevention measures
3. Update processes if needed
4. Document lessons learned
```

**6.3 Define Bug Metrics Tracking**

```markdown
## Bug Tracking Metrics

### Metrics to Track

**Bug Volume**:
- New bugs per sprint
- Open bugs total
- Closed bugs per sprint
- Bug backlog size

**Bug Severity Distribution**:
- P0: [count]
- P1: [count]
- P2: [count]
- P3/P4: [count]

**Bug Resolution Time**:
- Average time to fix by severity
- P0: Target <4 hours
- P1: Target <24 hours
- P2: Target <1 week
- P3/P4: Target <2 weeks

**Bug Escape Rate**:
- Bugs found in production vs. pre-production
- Target: <10% escape rate

**Bug Reopening Rate**:
- Bugs reopened after being closed
- Target: <5% reopening rate

**Bug by Category**:
- Functional
- UI/UX
- Performance
- Security
- Data

### Weekly Bug Report
```markdown
# Bug Report - Week [N]

## Summary
- New bugs: [X]
- Closed bugs: [Y]
- Open bugs: [Z]
- Critical/Blocker: [P0+P1 count]

## Critical Issues (P0/P1)
1. [BUG-XXX] - [Title] - [Status] - [Assigned to]
2. ...

## Trends
- [Observation about bug patterns]
- [Areas needing attention]

## Actions
- [Action items to prevent future bugs]
```

**Output**: Complete bug management process

---

### Step 7: Create Definition of Done (1 hour)

#### Objective
Establish clear Definition of Done for different work types.

#### Actions

**7.1 Define DoD for User Stories/Features**

```markdown
## Definition of Done - User Stories

A user story is "Done" when:

### Code Complete
- [ ] Code written and follows coding standards
- [ ] Code reviewed and approved by 2 developers
- [ ] All acceptance criteria met
- [ ] No hardcoded values or secrets
- [ ] Error handling implemented
- [ ] Logging added for key operations

### Testing Complete
- [ ] Unit tests written and passing (≥80% coverage)
- [ ] Integration tests written and passing (if applicable)
- [ ] Manual testing completed
- [ ] Acceptance criteria validated by QA or Product Owner
- [ ] No P0 or P1 bugs outstanding
- [ ] Performance tested (if performance-sensitive)

### Documentation Complete
- [ ] Code commented where necessary
- [ ] API documentation updated
- [ ] User documentation updated (if user-facing)
- [ ] README updated (if needed)

### Integration Complete
- [ ] Merged to develop branch
- [ ] All CI checks pass
- [ ] Deployed to dev environment
- [ ] Smoke tests pass in dev

### Demo Ready
- [ ] Feature can be demonstrated in sprint review
- [ ] Demo script prepared
- [ ] Test data prepared for demo
```

**7.2 Define DoD for Bugs**

```markdown
## Definition of Done - Bug Fixes

A bug is "Done" when:

### Fix Complete
- [ ] Root cause identified and documented
- [ ] Fix implemented and code reviewed
- [ ] Regression test added (to prevent recurrence)
- [ ] Related bugs checked (are there similar issues?)

### Verification Complete
- [ ] Bug verified fixed by original reporter
- [ ] Related functionality tested (regression)
- [ ] No new bugs introduced by fix
- [ ] Works in all supported environments

### Documentation Complete
- [ ] Bug report updated with resolution details
- [ ] Known issues documentation updated
- [ ] Release notes updated (if customer-facing)

### Deployment Complete
- [ ] Fix merged to appropriate branch
- [ ] CI checks pass
- [ ] Deployed to dev/staging (depending on severity)
```

**7.3 Define DoD for Sprints**

```markdown
## Definition of Done - Sprint

A sprint is "Done" when:

### Features Complete
- [ ] All committed user stories meet their DoD
- [ ] Sprint goal achieved
- [ ] All P0 and P1 bugs fixed
- [ ] Incomplete stories moved to next sprint or backlog

### Quality Complete
- [ ] All tests passing
- [ ] Code coverage ≥80%
- [ ] No critical security vulnerabilities
- [ ] Performance benchmarks met
- [ ] Code review queue empty

### Documentation Complete
- [ ] Sprint report created
- [ ] Demo prepared and delivered
- [ ] Retrospective completed
- [ ] Lessons learned documented

### Deployment Complete
- [ ] Code merged to develop
- [ ] Deployed to dev environment
- [ ] Smoke tests pass
- [ ] Ready for next sprint
```

**7.4 Define DoD for Releases**

```markdown
## Definition of Done - Release

A release is "Done" when:

### Development Complete
- [ ] All sprints in release meet sprint DoD
- [ ] All release features complete
- [ ] All P0 and P1 bugs fixed
- [ ] Code freeze in place

### Testing Complete
- [ ] Full regression test suite passed
- [ ] Performance tests passed
- [ ] Security scan passed (no critical vulnerabilities)
- [ ] Load tests passed
- [ ] UAT completed and signed off
- [ ] Exploratory testing completed

### Documentation Complete
- [ ] Release notes completed
- [ ] User documentation updated
- [ ] API documentation updated
- [ ] Known issues documented
- [ ] Migration guide created (if needed)

### Deployment Complete
- [ ] Deployed to staging and validated
- [ ] Rollback tested
- [ ] Production deployment plan finalized
- [ ] Monitoring and alerts configured
- [ ] Change approval obtained
- [ ] Deployed to production
- [ ] Smoke tests pass in production
- [ ] Post-deployment verification completed
```

**Output**: Clear Definition of Done for all work types

---

### Step 8: Compile Quality Strategy Document (1-2 hours)

#### Objective
Create comprehensive quality strategy document consolidating all quality planning.

#### Actions

**8.1 Create Final Quality Strategy Document**

Create `artifacts/quality-strategy.md`:

```markdown
# Quality Strategy - [Project Name]

**Project**: [Project Name]
**Created**: [Date]
**Created By**: Quality Architect Agent + Team
**Status**: Approved and Ready for Implementation

---

## Executive Summary

This document defines the comprehensive quality strategy for [Project Name],
including test strategy, quality metrics, quality gates, and quality processes.

**Quality Goal**: Deliver high-quality software that meets all functional and 
non-functional requirements with ≥80% code coverage, <10% defect escape rate,
and user satisfaction ≥4.5/5.

---

## Test Strategy

[Include full test strategy from Step 1]
- Testing pyramid (Unit 70%, Integration 20%, E2E 10%)
- Non-functional testing (Performance, Security, Accessibility)
- Requirements traceability

---

## Quality Metrics

[Include quality metrics from Step 2]
- Code quality metrics
- Test quality metrics
- Defect metrics
- Release quality criteria

---

## Test Automation Framework

[Include test automation framework from Step 3]
- Testing tools and frameworks
- Test data strategy
- Test environment strategy

---

## Code Quality Standards

[Include coding standards and code review process from Step 4]
- Coding standards (C#, TypeScript)
- Code review process and checklist

---

## Quality Gates

[Include quality gates from Step 5]
- Phase quality gates
- CI/CD quality gates

---

## Bug Management

[Include bug triage process from Step 6]
- Bug severity levels
- Bug triage workflow
- Bug metrics tracking

---

## Definition of Done

[Include DoD from Step 7]
- DoD for user stories
- DoD for bug fixes
- DoD for sprints
- DoD for releases

---

## Quality Roles and Responsibilities

### Quality Architect
- Define quality strategy
- Establish quality standards
- Review test plans
- Monitor quality metrics

### QA Engineers
- Write and execute test cases
- Perform manual testing
- Automate tests
- Report bugs
- Verify bug fixes

### Developers
- Write unit tests
- Write integration tests
- Fix bugs
- Conduct code reviews
- Maintain code quality

### Product Owner
- Define acceptance criteria
- Perform UAT
- Sign off on releases
- Prioritize bugs

---

## Testing Schedule

### Sprint 0 (Infrastructure)
- Set up test frameworks
- Configure CI/CD for tests
- Create test data
- Write first smoke tests

### Sprint 1
- Unit tests for all new code
- Integration tests for APIs
- Performance baseline tests

### Sprint 2+
- Continue unit and integration testing
- Add E2E tests for critical paths
- Weekly security scans
- Monthly performance tests

### Pre-Release
- Full regression testing
- Load and stress testing
- Security audit
- Accessibility audit
- UAT

---

## Continuous Improvement

### Sprint Retrospectives
- Review quality metrics
- Identify quality issues
- Plan improvements
- Track action items

### Quality Reviews
- Monthly quality metric review
- Quarterly quality strategy review
- Adjust processes based on learnings

### Automation Goals
- Sprint 0-2: Unit and integration test framework
- Sprint 3-5: E2E test framework
- Sprint 6+: Performance test automation
- Ongoing: Increase automation coverage

---

## Appendices

### Appendix A: Test Case Templates
[Templates for writing test cases]

### Appendix B: Bug Report Template
[Template for reporting bugs]

### Appendix C: Quality Metrics Dashboard
[Link to quality metrics dashboard]

---

## Approval

This quality strategy has been reviewed and approved by:

- **Quality Architect**: [Name] - [Date]
- **Tech Lead**: [Name] - [Date]
- **Product Owner**: [Name] - [Date]
- **Team**: [Consensus achieved] - [Date]

**Ready to Implement**: ✅ Yes
**Next Step**: Phase 3 - Implementation (Begin Sprint 0)
```

**8.2 Create Test Plan Document**

Create `artifacts/test-plan.md`:

```markdown
# Test Plan - [Project Name]

## Test Strategy Summary
[High-level summary of test approach]

## Test Scope

### In Scope
- [Features to be tested]
- [Test types to be executed]

### Out of Scope
- [What will NOT be tested]
- [Deferred testing]

## Test Schedule
[When each type of testing will occur]

## Test Environment
[Environments where testing will occur]

## Test Deliverables
- Test cases
- Test results
- Defect reports
- Test coverage reports
- Performance test results

## Entry and Exit Criteria

### Entry Criteria
- Code complete
- Build deployed to test environment
- Test environment ready
- Test data prepared

### Exit Criteria
- All tests executed
- ≥95% tests passed
- No P0 or P1 bugs open
- Coverage targets met
```

**Output**: Comprehensive quality strategy and test plan documents

---

## Success Criteria

This quality planning workflow is complete when:

✅ **Test strategy defined**: Comprehensive test strategy covering all levels  
✅ **Quality metrics established**: Measurable quality metrics and success criteria  
✅ **Test automation planned**: Test frameworks selected and automation approach defined  
✅ **Code quality standards set**: Coding standards and code review process established  
✅ **Quality gates defined**: Clear quality gates at all key checkpoints  
✅ **Bug management process**: Bug triage and resolution process documented  
✅ **Definition of Done created**: Clear DoD for all work types  
✅ **Documentation complete**: Quality strategy and test plan documents finalized  
✅ **Team alignment**: Team understands and commits to quality standards  
✅ **Ready for Sprint 0**: Can begin implementing quality framework in Sprint 0

---

## Handoff to Sprint 0

With quality planning complete, Sprint 0 can implement the quality framework:

**What Sprint 0 Needs from Quality Planning**:
1. ✅ Test frameworks identified
2. ✅ Quality standards documented
3. ✅ CI/CD quality gates defined
4. ✅ Test data strategy defined
5. ✅ DoD established

**Sprint 0 Quality Tasks**:
- Set up test frameworks
- Configure linting and formatting
- Configure CI/CD quality gates
- Create test data and seed scripts
- Write first smoke tests
- Set up code coverage reporting

**The team can now**:
- Implement tests alongside code
- Enforce code quality standards
- Track quality metrics
- Execute quality gates
- Manage bugs effectively

---

## Troubleshooting

### Issue: Team pushes back on 80% coverage requirement

**Symptom**: Developers say 80% coverage is too high or unrealistic

**Solutions**:
- Start with lower target (60-70%) and increase gradually
- Focus on critical paths first (100% coverage for core business logic)
- Allow exceptions for trivial code (getters/setters)
- Provide training on effective testing
- Show value of tests in catching bugs

---

### Issue: Too many flaky tests

**Symptom**: Tests pass/fail intermittently

**Solutions**:
- Identify and quarantine flaky tests
- Root cause analysis on flakiness
- Common causes: timing issues, shared state, external dependencies
- Use retry logic sparingly
- Fix or delete flaky tests (don't ignore)

---

### Issue: Tests take too long to run

**Symptom**: CI pipeline takes >15 minutes

**Solutions**:
- Parallelize test execution
- Optimize slow tests
- Split test suites (smoke, regression, full)
- Run only affected tests on PRs
- Run full suite nightly
- Consider test infrastructure upgrades

---

### Issue: Quality gates blocking development velocity

**Symptom**: Team complains gates slow them down

**Solutions**:
- Review if gates are too strict
- Ensure gates check things that matter
- Automate more checks (reduce manual steps)
- Provide faster feedback on failures
- Consider gate adjustments based on retrospectives
- Don't compromise on critical quality gates

---

**This workflow provides a systematic approach to quality planning that ensures high-quality software delivery. Follow it step-by-step to create a comprehensive quality strategy that the team can execute confidently.**
