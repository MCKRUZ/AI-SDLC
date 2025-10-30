# Task Decomposition Workflow

## Purpose

This workflow guides you through the systematic process of decomposing requirements from `spec.md` into implementable, estimable, and traceable tasks. The output is a comprehensive task breakdown that serves as the foundation for sprint planning and implementation.

**What This Workflow Accomplishes**:
- Breaks down all requirements into actionable tasks (2-5 days each)
- Groups tasks into logical feature areas (epics)
- Assigns story point and time estimates to each task
- Identifies technical dependencies between tasks
- Maps critical path through implementation
- Flags high-risk and uncertain tasks
- Ensures 100% traceability from requirements to tasks

**What This Workflow Does NOT Do**:
- Make architecture decisions (that's Phase 1)
- Assign specific people to tasks (that's sprint planning)
- Schedule tasks into sprints (that's sprint planning workflow)
- Change requirements or priorities (that's PM's domain)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Constitution** (`constitution.md`) - Quality standards and constraints
- [ ] **Requirements Specification** (`spec.md`) - All functional and non-functional requirements
- [ ] **Product Requirements Document** (`prd.md`) - Priorities, MVP scope, user personas
- [ ] **Architecture Document** (`architecture.md`) - Component structure and technical design
- [ ] **Data Model** (`data-model.md`) - Database schema and relationships
- [ ] **API Specification** (`api-spec.json`) - Integration contracts
- [ ] **Team Context** (`team-context.md`) - Team size, skills, velocity
- [ ] **Estimation History** (`estimation-history.memory.md`) - Historical velocity data
- [ ] **Prior Projects Memory** (`prior-projects.memory.md`) - Past project patterns

### Agent Setup

You should be in **Planning Agent** mode with all context loaded:

```markdown
You are the Planning Agent, an expert in agile planning, task decomposition, 
estimation, and dependency analysis.

Context loaded:
- Constitution.md
- Spec.md  
- PRD.md
- Architecture.md
- Data-model.md
- API-spec.json
- Team-context.md
- Estimation-history.md
- Prior-projects.memory.md

Your mission: Decompose all requirements into implementable tasks with 
realistic estimates and clear dependencies.

Ready to begin task decomposition.
```

### Session Setup

Create a focused planning session:

```bash
# Create working directory for task decomposition
mkdir -p .phase2/sessions/[project-name]/working/task-decomposition

# Navigate to working directory
cd .phase2/sessions/[project-name]/working/task-decomposition

# This is where you'll iterate on task breakdown
```

---

## Overview: The Task Decomposition Process

```
Requirements (from spec.md)
           ↓
    [Step 1: Analyze & Group]
           ↓
Feature Areas (logical grouping)
           ↓
    [Step 2: Create Epics]
           ↓
Epics (major features)
           ↓
    [Step 3: Create User Stories]
           ↓
User Stories (from requirements)
           ↓
    [Step 4: Decompose into Tasks]
           ↓
Tasks (implementable units)
           ↓
    [Step 5: Estimate Tasks]
           ↓
Tasks with Story Points & Hours
           ↓
    [Step 6: Map Dependencies]
           ↓
Dependency Graph & Critical Path
           ↓
    [Step 7: Assess Risk]
           ↓
Risk-Flagged Task Breakdown
           ↓
    [Step 8: Validate & Refine]
           ↓
Complete Task Breakdown
```

**Estimated Time**: 2-3 days (depending on project complexity)

---

## Step 1: Requirements Analysis & Grouping (4-6 hours)

### Objective

Understand all requirements and group them into logical feature areas that will become epics.

### Actions

#### 1.1 Review All Requirements

Read through the entire `spec.md` systematically:

```markdown
## Requirements Review Checklist

**Functional Requirements**:
- [ ] Total functional requirements: [N]
- [ ] Must-have requirements: [N]
- [ ] Should-have requirements: [N]
- [ ] Could-have requirements: [N]
- [ ] Won't-have (for now): [N]

**Non-Functional Requirements**:
- [ ] Performance requirements: [N]
- [ ] Security requirements: [N]
- [ ] Scalability requirements: [N]
- [ ] Usability requirements: [N]
- [ ] Accessibility requirements: [N]
- [ ] Compliance requirements: [N]

**Special Considerations**:
- [ ] Integration requirements: [N]
- [ ] Migration requirements: [N]
- [ ] Data requirements: [N]
- [ ] Reporting requirements: [N]
```

**Output**: List of all requirements with IDs

#### 1.2 Identify Natural Feature Groupings

Look for requirements that naturally belong together:

```markdown
## Feature Grouping Criteria

**Group by User Workflow**:
- Requirements that support the same user journey
- Example: "User Registration" (sign up, email verification, profile setup)

**Group by Domain Concept**:
- Requirements related to the same business entity
- Example: "Product Management" (create product, update product, delete product)

**Group by System Component**:
- Requirements that affect the same architectural component
- Example: "Payment Processing" (payment gateway, receipts, refunds)

**Group by Priority**:
- MVP must-haves might form one group
- Post-MVP enhancements another
- Example: "MVP Core Features" vs "Enhanced Features"

**Group by Technical Concern**:
- Requirements with similar technical complexity
- Example: "Authentication & Authorization" (login, permissions, roles)
```

#### 1.3 Create Initial Feature Map

Document your groupings:

```markdown
## Feature Area Map

### Feature Area 1: [Name]
**Description**: [Brief description of what this feature area encompasses]

**Requirements Included**:
- REQ-001: [Requirement description]
- REQ-002: [Requirement description]
- REQ-005: [Requirement description]
- REQ-008: [Requirement description]

**Priority**: [Must-have / Should-have / Could-have]  
**Estimated Complexity**: [Simple / Moderate / Complex]  
**Technical Dependencies**: [List other feature areas this depends on]

---

### Feature Area 2: [Name]
**Description**: [Brief description]

**Requirements Included**:
- REQ-003: [Requirement description]
- REQ-004: [Requirement description]
- REQ-006: [Requirement description]

**Priority**: [Must-have / Should-have / Could-have]  
**Estimated Complexity**: [Simple / Moderate / Complex]  
**Technical Dependencies**: [List dependencies]

---

[Continue for all feature areas...]
```

**Validation Questions**:
- ✅ Does every requirement belong to a feature area?
- ✅ Are feature areas cohesive (logically related)?
- ✅ Are feature areas loosely coupled (minimal dependencies)?
- ✅ Is each feature area demonstrable on its own?

#### 1.4 Order Feature Areas by Priority & Dependencies

Create a logical order for implementation:

```markdown
## Feature Area Implementation Order

**Foundation Layer** (Must complete first):
1. Authentication & Authorization - Needed by everything
2. Database Schema & Migrations - Data foundation
3. Core API Framework - Integration foundation

**Core Features Layer** (MVP):
4. User Management - Primary users
5. Product Catalog - Main business entities
6. Order Processing - Core business workflow

**Enhanced Features Layer** (Post-MVP):
7. Reporting & Analytics - Business insights
8. Admin Tools - Internal management
9. Integrations - Third-party connections

**Polish Layer** (Nice to have):
10. Advanced Search - Enhanced discoverability
11. Recommendations - Personalization
12. Mobile Optimization - Cross-platform
```

**Decision Criteria**:
- Technical dependencies (B needs A)
- Business value (high-value first)
- Risk reduction (risky features early)
- Team learning (complex features when team is ramped up)

**Output**: Ordered list of feature areas with rationale

---

## Step 2: Create Epics (2-3 hours)

### Objective

Transform feature areas into formal epics with clear goals, scope, and acceptance criteria.

### Actions

#### 2.1 Define Epic Structure

For each feature area, create a formal epic:

```markdown
## Epic Template

**Epic ID**: EPIC-001  
**Epic Name**: [Short, descriptive name]  
**Feature Area**: [From Step 1]

### Description
[2-3 paragraphs explaining what this epic encompasses, why it's important, and what value it delivers]

### User Value
**As a** [user persona]  
**I want** [capability]  
**So that** [business value]

### Scope

**In Scope**:
- [Specific functionality included]
- [Specific functionality included]
- [Specific functionality included]

**Out of Scope** (explicitly):
- [Functionality NOT included, to avoid scope creep]
- [Functionality NOT included]
- [Functionality NOT included]

### Requirements Included
- REQ-001: [Brief description]
- REQ-002: [Brief description]
- REQ-005: [Brief description]
- REQ-008: [Brief description]

### Epic Acceptance Criteria

Epic is complete when:
1. [High-level criterion 1]
2. [High-level criterion 2]
3. [High-level criterion 3]
4. [High-level criterion 4]
5. All requirements (REQ-001, REQ-002, REQ-005, REQ-008) met

### Technical Approach (High-Level)
[Brief overview of how this will be built, referencing architecture]

**Components Involved**:
- [Component 1 from architecture.md]
- [Component 2 from architecture.md]

**Key Technologies**:
- [Technology / Framework]
- [Technology / Framework]

### Dependencies

**Prerequisites** (must be complete before starting):
- EPIC-000: [Dependency epic]
- Infrastructure: [Infrastructure requirement]

**Enables** (other epics that need this):
- EPIC-003: [Dependent epic]
- EPIC-005: [Dependent epic]

### Estimated Effort
**Story Points**: [Rough estimate, e.g., 40-60]  
**Ideal Sprints**: [Number of sprints if focused, e.g., 2-3]  
**Team Members**: [Number of developers, e.g., 2-3]

### Priority
**MoSCoW**: [Must-have / Should-have / Could-have / Won't-have]  
**Business Value**: [High / Medium / Low]  
**Risk**: [High / Medium / Low]  
**Complexity**: [High / Medium / Low]

### Success Metrics
How we'll measure if this epic succeeded:
- [Metric 1: e.g., User sign-up rate increases by X%]
- [Metric 2: e.g., Time to complete workflow reduced by Y minutes]
- [Metric 3: e.g., Error rate < Z%]

### Risks
- **Risk 1**: [Description] - **Mitigation**: [Strategy]
- **Risk 2**: [Description] - **Mitigation**: [Strategy]
- **Risk 3**: [Description] - **Mitigation**: [Strategy]

### Notes
[Any additional context, constraints, or considerations]
```

#### 2.2 Create All Epics

Apply the template to all feature areas:

```markdown
## Epic List

1. **EPIC-001: Authentication & Authorization**
   - Priority: Must-have
   - Effort: 25-35 SP
   - Sprints: 1-2
   - Dependencies: None

2. **EPIC-002: Database Schema & Core Data Layer**
   - Priority: Must-have
   - Effort: 20-30 SP
   - Sprints: 1
   - Dependencies: None

3. **EPIC-003: User Management**
   - Priority: Must-have
   - Effort: 35-45 SP
   - Sprints: 2-3
   - Dependencies: EPIC-001, EPIC-002

4. **EPIC-004: Product Catalog**
   - Priority: Must-have
   - Effort: 40-50 SP
   - Sprints: 2-3
   - Dependencies: EPIC-002

5. **EPIC-005: Order Processing**
   - Priority: Must-have
   - Effort: 55-70 SP
   - Sprints: 3-4
   - Dependencies: EPIC-003, EPIC-004

[Continue for all epics...]

**Total MVP Epics**: [N]  
**Total MVP Effort**: [X-Y] story points  
**Total Post-MVP Epics**: [N]  
**Total Post-MVP Effort**: [X-Y] story points
```

#### 2.3 Validate Epic Definitions

Check each epic against quality criteria:

```markdown
## Epic Validation Checklist

**For Each Epic**:

**Clarity**:
- [ ] Epic name is clear and descriptive
- [ ] Description explains what and why
- [ ] User value statement is compelling
- [ ] Scope is explicit (in-scope and out-of-scope)

**Traceability**:
- [ ] All requirements from this feature area included
- [ ] No requirements orphaned (missing from all epics)
- [ ] Requirement IDs correctly referenced

**Completeness**:
- [ ] Acceptance criteria are measurable
- [ ] Dependencies identified
- [ ] Technical approach outlined
- [ ] Risks documented

**Sizing**:
- [ ] Epic is not too large (>100 SP)
- [ ] Epic is not too small (<10 SP)
- [ ] Epic fits in 1-4 sprints ideally
- [ ] Can be broken into user stories

**Value**:
- [ ] Epic delivers demonstrable user value
- [ ] Success metrics defined
- [ ] Business priority clear
```

**Output**: Complete set of validated epics

---

## Step 3: Create User Stories from Requirements (6-8 hours)

### Objective

Transform each requirement into one or more user stories using INVEST principles.

### Actions

#### 3.1 Understand User Story Quality (INVEST)

Ensure all stories meet INVEST criteria:

```markdown
## INVEST Principles for User Stories

**I - Independent**:
- Story can be developed and tested independently
- Minimal dependencies on other stories
- Can be prioritized and scheduled separately

**N - Negotiable**:
- Story describes the problem, not the solution
- Leaves room for discussion and collaboration
- Implementation details can be refined during development

**V - Valuable**:
- Delivers clear value to users or business
- Someone cares about this being done
- Not purely technical (unless infrastructure)

**E - Estimable**:
- Team can estimate effort with reasonable confidence
- If not estimable, may need to be split or researched

**S - Small**:
- Completable within one sprint
- Typically 1-8 story points
- Large stories (epics) should be broken down

**T - Testable**:
- Clear acceptance criteria
- Can verify when story is done
- Objective pass/fail criteria
```

#### 3.2 Write User Stories for Each Requirement

Use the standard user story template:

```markdown
## User Story Template

**Story ID**: STORY-001  
**Epic**: EPIC-001 [Epic Name]  
**Requirement**: REQ-001 [Brief description]

### User Story

**As a** [user persona from PRD.md]  
**I want** [capability or feature]  
**So that** [benefit or value]

### Context
[Additional background, business rules, or constraints that developers need to know]

### Acceptance Criteria

Given [precondition],  
When [action],  
Then [expected outcome]

1. **Given** [scenario context]  
   **When** [user action]  
   **Then** [system response]  
   **And** [additional outcome]

2. **Given** [different scenario]  
   **When** [user action]  
   **Then** [system response]

3. **Given** [edge case scenario]  
   **When** [user action]  
   **Then** [system handles gracefully]

[Include 3-7 acceptance criteria covering happy path, edge cases, and error conditions]

### Technical Notes
[Any technical implementation hints, API endpoints involved, database tables, etc.]

**API Endpoints**:
- [Endpoint from api-spec.json]

**Database Tables**:
- [Table from data-model.md]

**Architecture Components**:
- [Component from architecture.md]

### Definition of Done (Story Level)

- [ ] Code written and meets code standards
- [ ] Unit tests written (>80% coverage)
- [ ] Integration tests written
- [ ] All acceptance criteria met
- [ ] Code reviewed and approved
- [ ] Documentation updated
- [ ] Deployed to dev/staging environment
- [ ] Tested by QA (if applicable)
- [ ] No critical or high-priority defects

### Story Points (Estimated)
**Estimate**: [1, 2, 3, 5, 8, 13] story points

**Justification**: [Why this estimate? Complexity factors, unknowns, dependencies]

### Priority
**MoSCoW**: [Must / Should / Could / Won't]  
**Sprint Target**: [Which sprint ideally]

### Dependencies
**Prerequisites**:
- STORY-000: [Dependency story must be complete first]

**Enables**:
- STORY-003: [Stories that need this complete]

### Risks
- [Risk 1 and mitigation]
- [Risk 2 and mitigation]

### Notes
[Additional context, links to designs, mockups, or discussions]
```

#### 3.3 Generate User Stories Systematically

Work through each requirement:

```markdown
## Story Generation Process

**For Each Requirement in spec.md**:

1. **Read the requirement carefully**
   - Understand what it asks for
   - Identify the user persona it serves
   - Determine the business value

2. **Determine if one story or multiple**
   - Simple requirement → 1 story
   - Complex requirement → Split into multiple stories
   - Split by: workflow steps, user roles, CRUD operations, etc.

3. **Write the user story using template**
   - Clear "As a / I want / So that" structure
   - Detailed acceptance criteria (Given/When/Then)
   - Technical notes from architecture/data model
   - Traceability to requirement

4. **Validate against INVEST**
   - Can it be developed independently?
   - Is it valuable to someone?
   - Can we estimate it?
   - Is it small enough for one sprint?
   - Is it testable?

5. **Document dependencies**
   - What must be done before this?
   - What does this enable?

6. **Estimate story points**
   - Use planning poker approach
   - Reference similar past stories
   - Consider: complexity, uncertainty, effort
```

**Example: Splitting a Complex Requirement**

```markdown
## Example: REQ-042 "User can manage products"

This requirement is too large for one story. Split into:

**STORY-042A**: User can create a new product
- As a store owner
- I want to create a new product listing
- So that customers can purchase it

**STORY-042B**: User can edit existing product
- As a store owner
- I want to update product details
- So that information stays current

**STORY-042C**: User can delete product
- As a store owner
- I want to remove products no longer available
- So that customers don't see outdated listings

**STORY-042D**: User can view product history
- As a store owner
- I want to see change history for products
- So that I can track modifications

Each story is now:
- Independent (can build in any order)
- Valuable (delivers specific capability)
- Estimable (clearer scope)
- Small (fits in sprint)
- Testable (clear acceptance criteria)
```

#### 3.4 Validate User Stories

Check each story against quality criteria:

```markdown
## User Story Validation Checklist

**For Each Story**:

**Format**:
- [ ] Has unique Story ID (STORY-XXX)
- [ ] References parent Epic (EPIC-XXX)
- [ ] References source Requirement (REQ-XXX)
- [ ] Uses "As a / I want / So that" format
- [ ] Has Given/When/Then acceptance criteria

**Quality (INVEST)**:
- [ ] Independent: Can be developed separately
- [ ] Negotiable: Describes problem, not solution
- [ ] Valuable: Delivers user/business value
- [ ] Estimable: Team can estimate with confidence
- [ ] Small: Fits within one sprint
- [ ] Testable: Has clear pass/fail criteria

**Completeness**:
- [ ] Context provides adequate background
- [ ] Acceptance criteria cover happy path
- [ ] Acceptance criteria cover edge cases
- [ ] Acceptance criteria cover error handling
- [ ] Technical notes reference architecture/data model
- [ ] Definition of Done is clear

**Traceability**:
- [ ] Traces back to requirement in spec.md
- [ ] Rolls up to epic
- [ ] Dependencies documented
- [ ] Enables other stories documented (if applicable)

**Estimation**:
- [ ] Story points assigned (1, 2, 3, 5, 8, 13)
- [ ] Estimate justified with reasoning
- [ ] Confidence level noted (if low, flag for spike)
```

**Output**: Complete set of user stories for all requirements

---

## Step 4: Decompose Stories into Technical Tasks (8-10 hours)

### Objective

Break down each user story into concrete, technical implementation tasks that developers can execute.

### Actions

#### 4.1 Understand Task Characteristics

Tasks are the lowest level of breakdown:

```markdown
## What Makes a Good Task?

**Characteristics**:
- **Concrete**: Specific technical work, not ambiguous
- **Completable**: Can be finished in 0.5-5 days
- **Testable**: Can verify when done
- **Assignable**: One person can own it
- **Trackable**: Progress can be measured

**Size Guidelines**:
- **Too Small**: <2 hours (overhead > value)
- **Sweet Spot**: 0.5-2 days (half day to two days)
- **Too Large**: >5 days (risk of hidden complexity)

**Types of Tasks**:
- **Feature tasks**: Implementing functionality
- **Infrastructure tasks**: Setup, configuration, tooling
- **Testing tasks**: Writing tests, test data
- **Documentation tasks**: README, API docs, comments
- **Research tasks**: Spikes, investigations
- **Refactoring tasks**: Improving existing code
- **Bug fix tasks**: Addressing defects
```

#### 4.2 Decompose Each Story into Tasks

For each user story, create its tasks:

```markdown
## Task Decomposition Template

**Story ID**: STORY-001  
**Story**: [Brief user story description]

### Tasks for This Story

---

**Task ID**: TASK-001  
**Task Name**: [Short, action-oriented name]  
**Story**: STORY-001

**Description**:
[Detailed description of what needs to be done. Be specific about what files, components, or systems are involved]

**Technical Details**:
- File(s): [Specific files to create/modify]
- Component: [From architecture.md]
- Dependencies: [External libraries, services, etc.]

**Acceptance Criteria** (Task Level):
1. [Specific criterion 1]
2. [Specific criterion 2]
3. [Specific criterion 3]

**Estimate**:
- **Story Points**: [1, 2, 3, 5, 8]
- **Time**: [0.5, 1, 2, 3, 5] days
- **Confidence**: [High / Medium / Low]

**Skill Level**: [Junior / Mid / Senior]

**Dependencies**:
- **Prerequisites**: TASK-000 (must complete first)
- **Enables**: TASK-003 (unblocks this task)

**Risk**: [High / Medium / Low]  
**Risk Notes**: [If high/medium, explain why]

**Definition of Done** (Task):
- [ ] [Criterion 1 specific to this task]
- [ ] [Criterion 2]
- [ ] [Criterion 3]
- [ ] Code committed and pushed
- [ ] Tests passing

---

[Repeat for all tasks in this story]
```

#### 4.3 Standard Task Patterns

Most stories follow predictable patterns:

```markdown
## Common Task Breakdown Patterns

### Pattern 1: CRUD Feature Story

For a story like "User can create a product":

**Backend Tasks**:
1. TASK-XXX-001: Create database migration for product table
2. TASK-XXX-002: Create Product model/entity
3. TASK-XXX-003: Create Product repository/data access
4. TASK-XXX-004: Create Product service/business logic
5. TASK-XXX-005: Create POST /api/products endpoint
6. TASK-XXX-006: Add validation for product creation
7. TASK-XXX-007: Add authorization (who can create products)
8. TASK-XXX-008: Write unit tests for Product service
9. TASK-XXX-009: Write integration tests for API endpoint

**Frontend Tasks**:
10. TASK-XXX-010: Create ProductForm component
11. TASK-XXX-011: Create product creation page/route
12. TASK-XXX-012: Add form validation on frontend
13. TASK-XXX-013: Integrate with POST /api/products API
14. TASK-XXX-014: Add error handling and user feedback
15. TASK-XXX-015: Write component tests for ProductForm

**Testing & Documentation**:
16. TASK-XXX-016: Write end-to-end test for product creation flow
17. TASK-XXX-017: Update API documentation
18. TASK-XXX-018: Update user documentation

---

### Pattern 2: Read/Display Feature Story

For a story like "User can view product list":

**Backend Tasks**:
1. TASK-XXX-001: Create GET /api/products endpoint
2. TASK-XXX-002: Add filtering support (by category, price, etc.)
3. TASK-XXX-003: Add pagination support
4. TASK-XXX-004: Add sorting support
5. TASK-XXX-005: Optimize query performance (indexes)
6. TASK-XXX-006: Write unit tests for service layer
7. TASK-XXX-007: Write integration tests for API

**Frontend Tasks**:
8. TASK-XXX-008: Create ProductList component
9. TASK-XXX-009: Create ProductCard component (individual item)
10. TASK-XXX-010: Integrate with GET /api/products API
11. TASK-XXX-011: Implement filtering UI
12. TASK-XXX-012: Implement pagination UI
13. TASK-XXX-013: Implement sorting UI
14. TASK-XXX-014: Add loading states and error handling
15. TASK-XXX-015: Write component tests

**Testing & Documentation**:
16. TASK-XXX-016: Write end-to-end test for product browsing
17. TASK-XXX-017: Update documentation

---

### Pattern 3: Integration Feature Story

For a story like "System sends order confirmation email":

**Integration Tasks**:
1. TASK-XXX-001: Research email service provider API
2. TASK-XXX-002: Configure email service credentials
3. TASK-XXX-003: Create EmailService wrapper class
4. TASK-XXX-004: Create email template for order confirmation
5. TASK-XXX-005: Add email sending to order creation flow
6. TASK-XXX-006: Add retry logic for failed emails
7. TASK-XXX-007: Add email sending to background job queue
8. TASK-XXX-008: Write unit tests (with mocking)
9. TASK-XXX-009: Write integration tests (with test emails)

**Testing & Monitoring**:
10. TASK-XXX-010: Add logging for email operations
11. TASK-XXX-011: Add monitoring/alerting for failed emails
12. TASK-XXX-012: Test with real email service (staging)

---

### Pattern 4: Infrastructure/Setup Story

For a story like "CI/CD pipeline deploys to staging":

**Infrastructure Tasks**:
1. TASK-XXX-001: Create staging environment (cloud setup)
2. TASK-XXX-002: Configure CI/CD pipeline definition
3. TASK-XXX-003: Add build step (compile, lint, test)
4. TASK-XXX-004: Add deployment step (staging)
5. TASK-XXX-005: Configure environment variables for staging
6. TASK-XXX-006: Set up database migrations in pipeline
7. TASK-XXX-007: Add smoke tests post-deployment
8. TASK-XXX-008: Configure rollback strategy

**Testing & Documentation**:
9. TASK-XXX-009: Test full pipeline end-to-end
10. TASK-XXX-010: Document deployment process
```

#### 4.4 Task Naming Conventions

Use consistent, descriptive task names:

```markdown
## Task Naming Best Practices

**Format**: [Action Verb] + [Object] + [Context]

**Good Examples**:
- ✅ "Create Product database migration"
- ✅ "Implement POST /api/products endpoint"
- ✅ "Write unit tests for ProductService"
- ✅ "Add pagination to product list API"
- ✅ "Configure staging environment variables"

**Bad Examples**:
- ❌ "Products" (not actionable)
- ❌ "Work on API" (too vague)
- ❌ "Fix stuff" (not specific)
- ❌ "Database" (not actionable)
- ❌ "Testing" (too broad)

**Action Verbs to Use**:
- Create, Implement, Build, Develop
- Add, Integrate, Connect
- Update, Modify, Refactor
- Configure, Set up, Initialize
- Write, Document
- Test, Validate, Verify
- Fix, Debug, Resolve
- Research, Investigate, Spike
```

#### 4.5 Validate Task Decomposition

Check tasks against quality criteria:

```markdown
## Task Validation Checklist

**For Each Task**:

**Clarity**:
- [ ] Task name is action-oriented and specific
- [ ] Description clearly explains what to do
- [ ] Technical details specify files/components involved
- [ ] Acceptance criteria are concrete and verifiable

**Sizing**:
- [ ] Task is 0.5-5 days (not too small, not too large)
- [ ] If >5 days, break down further
- [ ] Estimate includes time for testing and documentation
- [ ] Confidence level matches complexity/uncertainty

**Traceability**:
- [ ] Task traces to user story
- [ ] Story traces to requirement
- [ ] Requirement traces to epic

**Dependencies**:
- [ ] Prerequisites clearly identified
- [ ] Blockers documented
- [ ] Order of tasks makes logical sense

**Assignability**:
- [ ] Skill level specified (Junior/Mid/Senior)
- [ ] One person can own this task
- [ ] Task is concrete enough to start immediately

**Completeness**:
- [ ] Definition of Done is clear
- [ ] Testing approach specified
- [ ] Documentation needs included
```

**Output**: Complete task breakdown for all user stories

---

## Step 5: Estimate All Tasks (4-6 hours)

### Objective

Assign realistic story point and time estimates to all tasks based on team velocity and historical data.

### Actions

#### 5.1 Understand Estimation Approaches

Choose your estimation method:

```markdown
## Estimation Methods

### Method 1: Story Points (Relative Sizing)

**Fibonacci Scale**: 1, 2, 3, 5, 8, 13, 21

**What it means**:
- **1 point**: Trivial, obvious how to implement, <4 hours
- **2 points**: Simple, clear approach, half-day
- **3 points**: Straightforward, some complexity, 1 day
- **5 points**: Moderate complexity, some unknowns, 2 days
- **8 points**: Complex, multiple components, 3-4 days
- **13 points**: Very complex, significant unknowns, 5+ days (consider splitting)
- **21+ points**: Epic, must be broken down

**Advantages**:
- Accounts for complexity, not just time
- Easier to estimate relative to other tasks
- Less affected by individual developer speed

---

### Method 2: Time Estimates (Hours/Days)

**Scale**: 0.5, 1, 2, 3, 5 days

**What it means**:
- **0.5 days**: 4 hours, trivial task
- **1 day**: 8 hours, simple task
- **2 days**: 16 hours, moderate task
- **3 days**: 24 hours, complex task
- **5 days**: 40 hours, very complex (upper limit)

**Advantages**:
- Easier to understand for stakeholders
- Directly maps to sprint capacity
- Clearer for timeline estimation

---

### Hybrid Approach (Recommended)

Use both:
- **Story points** for relative sizing and velocity tracking
- **Time estimates** for capacity planning and scheduling

**Example**:
- Task: "Implement user authentication"
- Story points: 8 (complex, multiple components)
- Time estimate: 3 days (for an experienced developer)
```

#### 5.2 Calibrate Against Historical Data

Use past projects to calibrate:

```markdown
## Estimation Calibration

**Review Estimation History** (from estimation-history.memory.md):

Look for similar tasks from past projects:

**Example**:
- **Past task**: "Implement JWT authentication"
- **Original estimate**: 5 story points / 2 days
- **Actual effort**: 3 days (1.5x estimate)
- **Complexity factors**: Token refresh logic was underestimated
- **Learning**: Add buffer for authentication tasks

**Calibration Questions**:
1. How accurate were past estimates?
   - If consistently under: Add 20-30% buffer
   - If consistently over: Reduce estimates 10-20%

2. Is this team faster or slower than historical team?
   - Adjust estimates based on team velocity difference

3. Are there unfamiliar technologies?
   - Add 30-50% buffer for learning curve

4. Are there known unknowns?
   - Flag for technical spike or higher estimate
```

#### 5.3 Estimate Each Task Systematically

Work through all tasks:

```markdown
## Task Estimation Process

**For Each Task**:

1. **Identify Complexity Factors**
   - How many files need to be created/modified?
   - How many components interact?
   - Are there external dependencies?
   - Is the approach clear or uncertain?
   - Are there similar past examples?

2. **Estimate Story Points** (Relative to Other Tasks)
   - Compare to already-estimated tasks
   - Use reference tasks from past projects
   - Consider: complexity, unknowns, risk

3. **Estimate Time** (Absolute Duration)
   - How long would a mid-level developer take?
   - Include time for: coding, testing, review, documentation
   - Add buffer for unknowns (10-30%)

4. **Assign Skill Level**
   - Junior: Straightforward, well-documented tasks
   - Mid: Standard complexity tasks
   - Senior: Complex, novel, or high-risk tasks

5. **Assess Confidence**
   - High: Clear approach, done before, low risk
   - Medium: Some uncertainty, but manageable
   - Low: Significant unknowns, may need spike

6. **Document Estimate**
   ```markdown
   **Estimate**:
   - Story Points: 5
   - Time: 2 days
   - Skill Level: Mid
   - Confidence: Medium
   
   **Rationale**: 
   Similar to past task TASK-123 from Project X, but adds 
   pagination which increases complexity. Estimate includes 
   time for unit tests and integration tests.
   ```
```

#### 5.4 Validate Estimates

Check estimates for consistency and realism:

```markdown
## Estimation Validation Checklist

**Story-Level Validation**:
- [ ] Sum of task estimates ≈ story estimate
- [ ] No individual task >5 days (break down if so)
- [ ] Tasks with similar complexity have similar estimates
- [ ] Junior tasks are genuinely junior-appropriate

**Epic-Level Validation**:
- [ ] Sum of story estimates ≈ epic estimate
- [ ] Epic total is 10-100 story points (not too small/large)
- [ ] Epic fits in 1-4 sprints at team velocity

**Project-Level Validation**:
- [ ] Total estimate aligns with timeline expectations
- [ ] MVP scope is achievable in available time
- [ ] Estimates account for testing and documentation
- [ ] Buffer included for unknowns (10-20%)

**Reality Checks**:
- [ ] Compare to similar past projects
- [ ] Sanity check with team members
- [ ] Does timeline feel aggressive or comfortable?
- [ ] Are there any "sounds too easy" tasks? (Investigate)
- [ ] Are there any "sounds too hard" tasks? (Break down)
```

**Estimation Anti-Patterns to Avoid**:

```markdown
## Common Estimation Mistakes

❌ **Anchoring**: First estimate biases subsequent estimates
- Solution: Estimate independently, then compare

❌ **Optimism Bias**: Assuming everything goes perfectly
- Solution: Add 10-20% buffer for unexpected issues

❌ **Hidden Tasks**: Forgetting testing, documentation, review
- Solution: Use task breakdown patterns that include all work

❌ **Inconsistent Scale**: Some tasks sized by complexity, others by time
- Solution: Agree on estimation method and stick to it

❌ **Precision Illusion**: Estimating 17.5 hours for a complex task
- Solution: Use Fibonacci scale, embrace uncertainty

❌ **Ignoring Learning**: Not accounting for unfamiliar technology
- Solution: Add explicit learning buffer or spike tasks
```

**Output**: All tasks have validated estimates

---

## Step 6: Map Dependencies & Critical Path (3-4 hours)

### Objective

Identify all dependencies between tasks and determine the critical path through the project.

### Actions

#### 6.1 Identify Task Dependencies

For each task, document what it depends on:

```markdown
## Dependency Identification

**Types of Dependencies**:

### 1. Hard Dependencies (Technical Blockers)
Task B literally cannot start until Task A is complete.

**Examples**:
- "Implement user profile" depends on "Create user database schema"
- "Add payment processing" depends on "Integrate payment gateway"
- "Build admin dashboard" depends on "Implement authentication"

### 2. Soft Dependencies (Preferential Order)
Task B could start before Task A, but it's easier/better if A is done first.

**Examples**:
- "Add product search" easier after "Implement product listing"
- "Performance optimization" easier after "Initial implementation"
- "Advanced features" easier after "Basic features working"

### 3. Resource Dependencies (Same Person)
Tasks that could be parallel but require same specialized person.

**Examples**:
- Two database tasks requiring the DBA
- Two frontend tasks when only one frontend developer
- Tasks requiring security expertise when one security expert

### 4. External Dependencies (Outside Team Control)
Waiting on something outside the development team.

**Examples**:
- Waiting for third-party API access
- Waiting for infrastructure provisioning
- Waiting for design mockups
- Waiting for legal approval
```

#### 6.2 Create Dependency Matrix

Document all dependencies systematically:

```markdown
## Task Dependency Matrix

| Task ID | Task Name | Depends On | Enables | Dependency Type |
|---------|-----------|------------|---------|----------------|
| TASK-001 | Create DB schema | - | TASK-005, TASK-008 | - |
| TASK-002 | Implement auth | - | TASK-010, TASK-015 | - |
| TASK-005 | Create User model | TASK-001 | TASK-010 | Hard |
| TASK-008 | Create Product model | TASK-001 | TASK-015 | Hard |
| TASK-010 | User registration API | TASK-002, TASK-005 | TASK-020 | Hard |
| TASK-015 | Product creation API | TASK-002, TASK-008 | TASK-025 | Hard |
| TASK-020 | User profile page | TASK-010 | - | Hard |
| TASK-025 | Product listing page | TASK-015 | TASK-030 | Hard |
| TASK-030 | Product search | TASK-025 | - | Soft |

**Dependency Legend**:
- **Hard**: Cannot start until prerequisite complete
- **Soft**: Preferably after prerequisite, but not required
- **Resource**: Same person needed
- **External**: Waiting on outside party
```

#### 6.3 Visualize Dependency Graph

Create a visual representation:

```markdown
## Dependency Graph

```
                    ┌──────────────┐
                    │  TASK-001    │
                    │  DB Schema   │
                    └──────┬───────┘
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       ┌──────────────┐          ┌──────────────┐
       │  TASK-005    │          │  TASK-008    │
       │  User Model  │          │  Prod Model  │
       └──────┬───────┘          └──────┬───────┘
              │                         │
              │        ┌──────────────┐ │
              │        │  TASK-002    │ │
              │        │  Auth System │ │
              │        └──────┬───────┘ │
              │               │         │
              └───────┬───────┴─────┬───┘
                      │             │
                      ▼             ▼
              ┌──────────────┐ ┌──────────────┐
              │  TASK-010    │ │  TASK-015    │
              │  User Reg API│ │  Prod API    │
              └──────┬───────┘ └──────┬───────┘
                     │                │
                     ▼                ▼
              ┌──────────────┐ ┌──────────────┐
              │  TASK-020    │ │  TASK-025    │
              │  User Page   │ │  Prod List   │
              └──────────────┘ └──────┬───────┘
                                      │
                                      ▼
                               ┌──────────────┐
                               │  TASK-030    │
                               │  Search      │
                               └──────────────┘
```

**Critical Path** (longest path through project):
TASK-001 → TASK-008 → TASK-015 → TASK-025 → TASK-030
Total duration: 15 days

This is the minimum project duration if everything goes perfectly.
```

#### 6.4 Identify Critical Path

Calculate the longest path through the project:

```markdown
## Critical Path Analysis

**Definition**: The sequence of dependent tasks that determines the minimum project duration.

**Finding the Critical Path**:

1. **Calculate Early Start/Finish** (forward pass):
   - Start: Day 0
   - For each task: Early Start = Max(Early Finish of all prerequisites)
   - Early Finish = Early Start + Task Duration

2. **Calculate Late Start/Finish** (backward pass):
   - End: Project deadline
   - For each task: Late Finish = Min(Late Start of all dependents)
   - Late Start = Late Finish - Task Duration

3. **Calculate Slack** (float):
   - Slack = Late Start - Early Start
   - Tasks with 0 slack are on critical path

**Example**:

| Task | Duration | Early Start | Early Finish | Late Start | Late Finish | Slack | Critical? |
|------|----------|-------------|--------------|------------|-------------|-------|-----------|
| TASK-001 | 2 days | Day 0 | Day 2 | Day 0 | Day 2 | 0 | ✅ Yes |
| TASK-002 | 3 days | Day 0 | Day 3 | Day 1 | Day 4 | 1 | ❌ No |
| TASK-005 | 1 day | Day 2 | Day 3 | Day 4 | Day 5 | 2 | ❌ No |
| TASK-008 | 1 day | Day 2 | Day 3 | Day 2 | Day 3 | 0 | ✅ Yes |
| TASK-010 | 2 days | Day 3 | Day 5 | Day 5 | Day 7 | 2 | ❌ No |
| TASK-015 | 3 days | Day 3 | Day 6 | Day 3 | Day 6 | 0 | ✅ Yes |
| TASK-020 | 2 days | Day 5 | Day 7 | Day 7 | Day 9 | 2 | ❌ No |
| TASK-025 | 2 days | Day 6 | Day 8 | Day 6 | Day 8 | 0 | ✅ Yes |
| TASK-030 | 1 day | Day 8 | Day 9 | Day 8 | Day 9 | 0 | ✅ Yes |

**Critical Path**: TASK-001 → TASK-008 → TASK-015 → TASK-025 → TASK-030  
**Project Duration**: 9 days minimum

**Implications**:
- Delays in critical path tasks delay entire project
- Non-critical tasks have slack (can be delayed without impacting project)
- Focus risk mitigation on critical path tasks
- Optimize critical path tasks for performance
```

#### 6.5 Identify Parallelization Opportunities

Find tasks that can be done simultaneously:

```markdown
## Parallelization Analysis

**Independent Task Streams**:

**Stream 1 (User Management)**:
- TASK-001 (DB Schema)
- TASK-005 (User Model)
- TASK-010 (User API)
- TASK-020 (User Page)

**Stream 2 (Product Management)** [Can run parallel to Stream 1 after DB]:
- TASK-001 (DB Schema) [shared dependency]
- TASK-008 (Product Model)
- TASK-015 (Product API)
- TASK-025 (Product Page)

**Stream 3 (Authentication)** [Can run parallel after DB]:
- TASK-001 (DB Schema) [shared dependency]
- TASK-002 (Auth System)
- Can enable both Streams 1 and 2

**Maximum Parallelization**:
With 3 developers:
- Dev 1: Stream 1 (User features)
- Dev 2: Stream 2 (Product features)
- Dev 3: Stream 3 (Auth) → then help Stream 1 or 2

**Realistic Parallelization**:
With 2 developers:
- Week 1: Both work on foundation (DB, Auth)
- Week 2: Dev 1 on User features, Dev 2 on Product features
- Week 3: Both integrate and test

**Constraints**:
- Can't parallelize beyond team size
- Some tasks require specific expertise
- Code review requires multiple people
- Integration testing requires features complete
```

**Output**: 
- Complete dependency matrix
- Dependency graph visualization
- Critical path identified
- Parallelization opportunities documented

---

## Step 7: Assess Risk for Each Task (2-3 hours)

### Objective

Identify tasks with high uncertainty, complexity, or potential to cause delays.

### Actions

#### 7.1 Risk Assessment Criteria

Evaluate each task across risk dimensions:

```markdown
## Task Risk Assessment Framework

**Risk Dimensions**:

### 1. Complexity Risk
- How many components does this task touch?
- How intricate is the logic?
- Are there many edge cases?

**Scoring**:
- Low: Simple, straightforward implementation
- Medium: Moderate complexity, some edge cases
- High: Complex logic, many interactions

---

### 2. Uncertainty Risk
- How clear is the approach?
- Have we done this before?
- Are there unknowns?

**Scoring**:
- Low: Clear approach, done many times
- Medium: Some unknowns, but manageable
- High: Significant uncertainty, may need spike

---

### 3. Dependency Risk
- Does this task depend on external factors?
- Is it on the critical path?
- Does it block many other tasks?

**Scoring**:
- Low: Independent or non-critical
- Medium: Some dependencies, moderate blocking
- High: Many dependencies or blocks critical path

---

### 4. Technology Risk
- Are we using unfamiliar technology?
- Is the technology mature/stable?
- Is there good documentation?

**Scoring**:
- Low: Familiar, mature technology
- Medium: Some new tech, good docs available
- High: Unfamiliar or cutting-edge technology

---

### 5. Integration Risk
- Does this integrate with external systems?
- How reliable is the integration point?
- How complex is the integration?

**Scoring**:
- Low: No external integration or simple
- Medium: Standard integration, some complexity
- High: Complex integration, unreliable third-party

---

**Overall Risk Calculation**:
- **High Risk**: Any dimension scores High OR 3+ dimensions score Medium
- **Medium Risk**: 1-2 dimensions score Medium
- **Low Risk**: All dimensions score Low
```

#### 7.2 Flag High-Risk Tasks

Identify and document all high-risk tasks:

```markdown
## High-Risk Task Register

**Task ID**: TASK-015  
**Task Name**: Integrate payment gateway  
**Overall Risk**: HIGH

**Risk Analysis**:
- **Complexity**: Medium (standard integration pattern)
- **Uncertainty**: High (never integrated this gateway before)
- **Dependency**: High (blocks all payment features)
- **Technology**: Medium (API documentation available)
- **Integration**: High (external service, authentication required)

**Risk Factors**:
1. Unfamiliar payment gateway API
2. Requires PCI compliance understanding
3. Blocks multiple high-value features
4. External dependency (service availability)
5. Security-critical functionality

**Mitigation Strategy**:
1. **Technical Spike**: 1-day spike to prototype integration (SPIKE-001)
2. **Early Start**: Schedule in Sprint 1 to allow time for issues
3. **Expert Review**: Have security team review implementation
4. **Sandbox Testing**: Extensive testing in sandbox environment
5. **Fallback Plan**: Design for graceful degradation if service unavailable

**Contingency Plan**:
- If integration is more complex than expected: Add 1 sprint buffer
- If service is unreliable: Implement queue-based async processing
- If cannot complete in time: Mock payment for MVP, integrate post-MVP

**Monitoring**:
- Check spike findings before committing to timeline
- Daily standup updates during implementation
- Escalate immediately if blockers emerge

---

[Repeat for all high-risk tasks]

**Summary**:
- Total high-risk tasks: [N]
- On critical path: [N]
- Require spikes: [N]
- External dependencies: [N]
```

#### 7.3 Recommend Technical Spikes

For tasks with high uncertainty:

```markdown
## Technical Spike Recommendations

**What is a Technical Spike?**
Time-boxed research or prototyping to reduce uncertainty before committing to implementation.

**When to Spike**:
- Unfamiliar technology or framework
- Uncertain if approach will work
- Third-party integration with unclear documentation
- Performance concerns that need validation
- Architectural decision needs proof-of-concept

**Recommended Spikes**:

---

**SPIKE-001: Payment Gateway Integration Feasibility**
- **Purpose**: Validate we can integrate with chosen payment gateway
- **Time Box**: 1 day
- **Activities**:
  - Create sandbox account
  - Make test API calls
  - Implement basic charge workflow
  - Test error scenarios
  - Validate PCI compliance requirements
- **Success Criteria**:
  - Can successfully process test payment
  - Understand authentication model
  - Documented gotchas and best practices
- **Before Task**: TASK-015 (Integrate payment gateway)

---

**SPIKE-002: Real-time Notification Architecture**
- **Purpose**: Determine best approach for real-time updates (WebSockets vs SSE vs polling)
- **Time Box**: 1 day
- **Activities**:
  - Prototype each approach
  - Load test with expected user count
  - Evaluate complexity and maintainability
  - Document pros/cons
- **Success Criteria**:
  - Confident recommendation on approach
  - Performance validated for scale
  - Implementation complexity understood
- **Before Task**: TASK-042 (Implement real-time notifications)

---

[Continue for all recommended spikes]
```

**Output**: 
- Risk assessment for all tasks
- High-risk task register
- Technical spike recommendations
- Mitigation strategies

---

## Step 8: Validate & Refine Task Breakdown (2-3 hours)

### Objective

Ensure task breakdown is complete, consistent, and ready for sprint planning.

### Actions

#### 8.1 Run Comprehensive Validation

Use the master validation checklist:

```markdown
## Task Breakdown Validation Checklist

### Completeness

**Requirements Coverage**:
- [ ] Every requirement in spec.md has at least one user story
- [ ] Every user story has at least one task
- [ ] No requirements are orphaned (without stories/tasks)
- [ ] MVP requirements clearly identified

**Task Types Included**:
- [ ] Feature implementation tasks present
- [ ] Testing tasks included (unit, integration, E2E)
- [ ] Documentation tasks included
- [ ] Infrastructure tasks included
- [ ] Migration tasks included (if applicable)
- [ ] Deployment tasks included

### Quality

**Traceability**:
- [ ] Every task traces to a story
- [ ] Every story traces to a requirement
- [ ] Every requirement traces to an epic
- [ ] Cross-references are correct and bidirectional

**Estimates**:
- [ ] Every task has story points
- [ ] Every task has time estimate
- [ ] Estimates are justified
- [ ] Estimates calibrated against historical data
- [ ] Total estimates align with timeline expectations

**Dependencies**:
- [ ] All task dependencies documented
- [ ] Dependency graph is acyclic (no circular dependencies)
- [ ] Critical path identified
- [ ] Parallelization opportunities identified

**Risk Assessment**:
- [ ] Every task has risk level (High/Medium/Low)
- [ ] High-risk tasks have mitigation plans
- [ ] Technical spikes recommended for uncertain tasks
- [ ] External dependencies flagged

### Consistency

**Naming**:
- [ ] Task IDs follow convention (TASK-XXX)
- [ ] Story IDs follow convention (STORY-XXX)
- [ ] Epic IDs follow convention (EPIC-XXX)
- [ ] Names are descriptive and action-oriented

**Formatting**:
- [ ] All artifacts use standard templates
- [ ] Acceptance criteria use Given/When/Then
- [ ] Priority uses MoSCoW (Must/Should/Could/Won't)
- [ ] Estimates use Fibonacci scale (1, 2, 3, 5, 8, 13)

**Architecture Alignment**:
- [ ] Tasks reference correct components from architecture.md
- [ ] Repository structure will match component design
- [ ] API endpoints align with api-spec.json
- [ ] Database tasks align with data-model.md

### Realism

**Sizing**:
- [ ] No task is >5 days (break down if so)
- [ ] Most tasks are 0.5-3 days
- [ ] Task size distribution is reasonable

**Capacity**:
- [ ] Total effort fits within project timeline
- [ ] MVP scope is achievable
- [ ] Buffer included for unknowns (10-20%)

**Team Fit**:
- [ ] Skill level assignments match team composition
- [ ] Not too many senior-only tasks
- [ ] Junior developers have appropriate tasks
- [ ] Specializations considered (frontend/backend/etc.)
```

#### 8.2 Conduct Peer Review

Have the task breakdown reviewed:

```markdown
## Peer Review Process

**Reviewers**:
- Development team lead
- Solutions architect
- Senior developers
- Product manager (for priorities)

**Review Focus Areas**:

**For Development Lead**:
- Are estimates realistic for our team?
- Are dependencies correctly identified?
- Is the breakdown implementable?
- Any missing technical tasks?

**For Architect**:
- Does breakdown align with architecture?
- Are components correctly understood?
- Any architectural risks?
- Any missing infrastructure tasks?

**For Senior Developers**:
- Are tasks clear enough to start immediately?
- Are there hidden complexities?
- Are estimates consistent?
- Any gotchas we've seen before?

**For Product Manager**:
- Are priorities correctly reflected?
- Is MVP scope bounded correctly?
- Are user stories valuable?
- Any missing user-facing features?

**Review Checklist**:
- [ ] Task breakdown is comprehensive
- [ ] Estimates seem reasonable
- [ ] Dependencies make sense
- [ ] No major gaps identified
- [ ] Critical path is clear
- [ ] Risk assessment is thorough
```

#### 8.3 Address Review Feedback

Iterate based on feedback:

```markdown
## Feedback Incorporation

**Common Feedback Types**:

### 1. Missing Tasks
"You forgot about database indexes for performance"
**Action**: Add TASK-XXX for index creation

### 2. Underestimated Tasks
"That integration is more complex than you think"
**Action**: Increase estimate, add spike if needed

### 3. Incorrect Dependencies
"Task B doesn't actually need Task A complete"
**Action**: Update dependency matrix

### 4. Unclear Task Description
"What does 'implement user management' mean?"
**Action**: Break down into more specific tasks

### 5. Architectural Misalignment
"That's not how the component is designed"
**Action**: Review architecture.md, correct misunderstanding

**Feedback Log**:

| Reviewer | Feedback | Action Taken | Status |
|----------|----------|--------------|--------|
| [Name] | [Feedback] | [Action] | [Complete/Pending] |
| [Name] | [Feedback] | [Action] | [Complete/Pending] |
| [Name] | [Feedback] | [Action] | [Complete/Pending] |
```

#### 8.4 Generate Summary Statistics

Create a high-level summary:

```markdown
## Task Breakdown Summary Statistics

### Scope

**Epics**: [N] total
- MVP: [N] epics
- Post-MVP: [N] epics

**User Stories**: [N] total
- MVP: [N] stories
- Post-MVP: [N] stories

**Tasks**: [N] total
- Feature tasks: [N]
- Testing tasks: [N]
- Documentation tasks: [N]
- Infrastructure tasks: [N]
- Migration tasks: [N]

### Effort

**Story Points**: [Total] SP
- MVP: [N] SP ([X]%)
- Post-MVP: [N] SP ([Y]%)

**Time Estimate**: [Total] days
- MVP: [N] days ([X]%)
- Post-MVP: [N] days ([Y]%)

**Average Task Size**:
- Story points: [N] SP
- Time: [N] days

### Distribution

**By Priority**:
- Must-have: [N] tasks ([X]% of total)
- Should-have: [N] tasks ([Y]% of total)
- Could-have: [N] tasks ([Z]% of total)

**By Skill Level**:
- Junior: [N] tasks ([X]% of total)
- Mid: [N] tasks ([Y]% of total)
- Senior: [N] tasks ([Z]% of total)

**By Risk**:
- High risk: [N] tasks ([X]% of total)
- Medium risk: [N] tasks ([Y]% of total)
- Low risk: [N] tasks ([Z]% of total)

### Dependencies

**Critical Path**:
- Duration: [N] days
- Tasks on critical path: [N]
- Slack available: [N] days

**Parallelization**:
- Maximum parallel streams: [N]
- Independent feature areas: [N]
- Bottleneck tasks: [N]

### Risk

**High-Risk Tasks**: [N]
- On critical path: [N]
- Require spikes: [N]
- External dependencies: [N]

**Recommended Spikes**: [N]
- Total spike effort: [N] days

### Velocity

**Estimated Team Velocity**: [N] SP/sprint  
**Estimated Sprints Needed**: [N] sprints
- MVP: [N] sprints
- Post-MVP: [N] sprints

**Timeline**:
- MVP target: Sprint [N] ([Date])
- Full completion: Sprint [N] ([Date])
```

#### 8.5 Create Traceability Matrix

Ensure complete traceability:

```markdown
## Traceability Matrix

| Epic | Stories | Requirements | Tasks | Total SP | Total Days |
|------|---------|--------------|-------|----------|-----------|
| EPIC-001 | STORY-001, STORY-002, STORY-003 | REQ-001, REQ-002, REQ-003 | TASK-001 to TASK-025 | 35 | 18 |
| EPIC-002 | STORY-004, STORY-005 | REQ-004, REQ-005, REQ-006 | TASK-026 to TASK-042 | 28 | 14 |
| EPIC-003 | STORY-006, STORY-007, STORY-008 | REQ-007, REQ-008 | TASK-043 to TASK-067 | 45 | 22 |
| ... | ... | ... | ... | ... | ... |

**Validation**:
- ✅ All requirements covered
- ✅ All stories have tasks
- ✅ All tasks roll up to stories
- ✅ No gaps in traceability
```

**Output**: 
- Validated and refined task breakdown
- Summary statistics
- Traceability matrix
- Ready for sprint planning

---

## Final Outputs

### Primary Artifact: Task Breakdown Document

Create the comprehensive `task-breakdown.md`:

```markdown
# Task Breakdown - [Project Name]

**Version**: 1.0  
**Date**: [Date]  
**Author**: Planning Agent  
**Status**: Validated and Ready for Sprint Planning

---

## Executive Summary

**Total Scope**:
- [N] Epics
- [N] User Stories
- [N] Tasks
- [X] Story Points
- [Y] Days Estimated Effort

**MVP Scope**:
- [N] Epics
- [N] Stories  
- [N] Tasks
- [X] Story Points (Z% of total)
- [Y] Days (Z% of total)

**Critical Path**: [N] days  
**Recommended Sprints**: [N] sprints for MVP

---

## Epics

[Include all epic definitions from Step 2]

---

## User Stories

[Include all user stories from Step 3]

---

## Technical Tasks

[Include all tasks from Step 4]

---

## Estimates

[Include estimation summary from Step 5]

---

## Dependencies

[Include dependency matrix and critical path from Step 6]

---

## Risk Assessment

[Include risk analysis from Step 7]

---

## Traceability Matrix

[Include complete traceability from Step 8]

---

## Appendices

### Appendix A: Estimation Methodology
[How estimates were derived]

### Appendix B: Historical Calibration
[Reference to past projects used for calibration]

### Appendix C: Assumptions
[Key assumptions made during decomposition]

### Appendix D: Open Questions
[Any unresolved questions that need answers]
```

### Supporting Artifact: Dependency Map

Create `dependency-map.md`:

```markdown
# Task Dependency Map - [Project Name]

[Include complete dependency analysis from Step 6]
```

---

## Success Criteria

This task decomposition workflow is complete when:

✅ **All requirements decomposed**: Every requirement in spec.md has corresponding stories and tasks  
✅ **Tasks are implementable**: Each task is concrete, estimated, and has clear acceptance criteria  
✅ **Estimates are realistic**: Based on historical data and peer-reviewed  
✅ **Dependencies mapped**: Critical path identified, parallelization opportunities found  
✅ **Risks assessed**: High-risk tasks flagged with mitigation strategies  
✅ **Traceability complete**: Requirements → Stories → Tasks fully linked  
✅ **Peer-reviewed**: Development team, architect, and PM have validated  
✅ **Ready for sprint planning**: Task breakdown can be used to plan sprints immediately

---

## Handoff to Sprint Planning

With task decomposition complete, you're ready for sprint planning:

**What Sprint Planning Needs**:
1. ✅ Complete task breakdown with estimates
2. ✅ Dependency map with critical path
3. ✅ Risk assessment for high-risk tasks
4. ✅ Team velocity and capacity data

**Next Workflow**: `sprint-planning.prompt.md`

**Inputs to Sprint Planning**:
- `task-breakdown.md` (from this workflow)
- `dependency-map.md` (from this workflow)
- `team-context.md` (team capacity and velocity)
- `prd.md` (priorities for sprint planning)

Sprint planning will:
- Organize tasks into executable sprints
- Assign tasks based on skills and capacity
- Create demo-driven sprint goals
- Validate feasibility with team

---

## Troubleshooting

### Issue: Task breakdown taking too long

**Symptom**: Spending >5 days on task decomposition

**Solution**:
- Stop trying to be perfect
- Plan to 80% confidence level
- Remember estimates will be refined during planning
- Focus on MVP scope first, post-MVP later

---

### Issue: Tasks keep getting bigger

**Symptom**: Discovering tasks are more complex than initially thought

**Solution**:
- This is normal discovery
- Break down the large tasks
- Adjust estimates upward if needed
- Flag for technical spike if uncertainty is high

---

### Issue: Can't estimate because too many unknowns

**Symptom**: Low confidence in estimates for several tasks

**Solution**:
- Recommend technical spikes for high-uncertainty tasks
- Use wide estimate ranges (e.g., 5-8 SP instead of 5 SP)
- Schedule uncertain tasks early so you have time to adjust
- Get expert input from someone who has done similar work

---

### Issue: Dependencies create gridlock

**Symptom**: Everything depends on everything, can't parallelize

**Solution**:
- Re-examine architecture for excessive coupling
- Define interfaces early so teams can work in parallel
- Consider reordering work to break bottlenecks
- Use mocking to enable parallel development

---

**This workflow provides a systematic approach to decomposing requirements into implementable tasks. Follow it step-by-step to create a comprehensive task breakdown that serves as the foundation for successful sprint planning and execution.**
