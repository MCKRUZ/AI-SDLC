# Architecture Design Workflow - Phase 1

**Purpose**: This workflow orchestrates the architecture design process in Phase 1, coordinating the Architect Agent and Validator Agent to transform requirements into detailed technical designs ready for implementation.

---

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│         Phase 1: Architecture Design & Validation                │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  1. Initiate Design      │
                 │  - Load requirements     │
                 │  - Review constraints    │
                 │  - Set up structure      │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  2. Constitution         │
                 │  (Architect Agent)       │
                 │  - Define principles     │
                 │  - Specify NFRs          │
                 │  - Document constraints  │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  3. System Architecture  │
                 │  (Architect Agent)       │
                 │  - Choose patterns       │
                 │  - Define components     │
                 │  - Document ADRs         │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  4. Data Model           │
                 │  (Architect Agent)       │
                 │  - Design entities       │
                 │  - Define relationships  │
                 │  - Specify constraints   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  5. API Design           │
                 │  (Architect Agent)       │
                 │  - Define endpoints      │
                 │  - Specify contracts     │
                 │  - Document API          │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  6. Supporting Designs   │
                 │  (Architect Agent)       │
                 │  - Security architecture │
                 │  - Deployment design     │
                 │  - Integration design    │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  7. Architecture Review  │
                 │  - Technical review      │
                 │  - Stakeholder feedback  │
                 │  - Update designs        │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  8. Comprehensive Valid. │
                 │  (Validator Agent)       │
                 │  - Validate completeness │
                 │  - Check consistency     │
                 │  - Verify traceability   │
                 └──────────────────────────┘
                                │
                                ▼
                 ┌──────────────────────────┐
                 │  9. Final Approval       │
                 │  - Stakeholder sign-off  │
                 │  - Phase 1 complete      │
                 │  - Ready for Phase 2     │
                 └──────────────────────────┘
```

---

## Step 1: Initiate Architecture Design

### Objective
Set up architecture design session with all Phase 1 requirements artifacts.

### Time Required
30 minutes

### Actions

#### 1.1 Load Requirements Artifacts

**Required Inputs from Requirements Discovery**:
```markdown
## Phase 1 Requirements Artifacts

**MUST HAVE**:
- [ ] `spec.md` - Functional Requirements Specification (APPROVED)
- [ ] `prd.md` - Product Requirements Document (APPROVED)
- [ ] `user-stories.md` - User stories with acceptance criteria
- [ ] `business-rules.md` - Business logic documentation
- [ ] `clarifications.md` - Known questions and assumptions

**FROM PHASE 0**:
- [ ] `problem-statement.final.md` - Original validated problem
- [ ] `feasibility-report.md` - Technical feasibility analysis
- [ ] `constraints.md` - All constraints to respect

**Create Architecture Workspace**:
```bash
mkdir -p phase-1-sessions/[project]/architecture/{drafts,diagrams,adrs,reviews}
mkdir -p phase-1-sessions/[project]/architecture/diagrams/{context,component,sequence,deployment}
mkdir -p phase-1-sessions/[project]/architecture/adrs/
```

#### 1.2 Create Architecture Session Metadata

```markdown
# Architecture Design Session Metadata

**Project Name**: [Name]
**Session ID**: [NNN-project-name]
**Requirements Session**: [Link to requirements session]
**Start Date**: [YYYY-MM-DD]
**Status**: [Active]

**Team**:
- Solutions Architect: [Name/Agent]
- Validator: [Name/Agent]
- Technical Lead: [Name - for review]
- Security Architect: [Name - for review]

**Requirements Summary** (from spec.md):
- Total Requirements: [N]
- Must-Have Requirements: [N]
- MVP Scope: [Brief description]

**Key NFRs to Address**:
1. Performance: [Target from Phase 0]
2. Security: [Requirements from Phase 0]
3. Scalability: [Requirements from Phase 0]
4. Reliability: [Requirements from Phase 0]

**Key Constraints**:
1. [Constraint 1 from Phase 0]
2. [Constraint 2 from Phase 0]
3. [Constraint 3 from Phase 0]

**Key Integration Requirements**:
- [System 1]: [Integration need]
- [System 2]: [Integration need]

**Architecture Goals**:
1. Design system that meets all functional requirements
2. Address all non-functional requirements
3. Respect all constraints
4. Minimize technical debt
5. Enable future scalability

**Timeline**: [Estimated weeks]
```

**Save as**: `architecture/session.meta.md`

#### 1.3 Review Technical Landscape

**Assess Technical Context**:
```markdown
## Technical Landscape Assessment

### Current Systems (from Phase 0)
- [System 1]: [Technology, integration points]
- [System 2]: [Technology, integration points]

### Technology Constraints (from Phase 0)
- **Must Use**: [Technologies required]
- **Must Integrate With**: [Systems required]
- **Cannot Use**: [Prohibited technologies]

### Team Capabilities
- **Languages**: [C#, Python, JavaScript, etc.]
- **Frameworks**: [.NET, React, etc.]
- **Cloud Experience**: [AWS, Azure, GCP]
- **Database Experience**: [SQL Server, PostgreSQL, etc.]

### Infrastructure Constraints
- **Cloud Provider**: [Required provider or on-premise]
- **Budget**: [Infrastructure budget constraints]
- **Compliance**: [Regulatory requirements affecting infrastructure]
```

---

## Step 2: Constitution Creation (Architect Agent)

### Objective
Create the project constitution defining principles, non-functional requirements, and technical constraints.

### Agent: Architect Agent
Load: `.primitives/agents/architect-agent.instructions.md`

### Time Required
2-3 hours

### Context to Provide Agent

```markdown
## Context for Architect Agent - Constitution

You are creating the technical constitution for [Project Name].

**Your Mission**: Define the principles, non-functional requirements, and 
constraints that will govern all technical decisions.

**Inputs Provided**:
- Phase 0 problem statement (business context)
- Phase 0 feasibility report (technical analysis)
- Phase 0 constraints (what we must respect)
- Requirements spec (what system must do)
- PRD (product vision and goals)

**Your Output**: 
- constitution.md (complete technical constitution)

**What Constitution Must Include**:
1. Project Principles (3-7 core principles)
2. Non-Functional Requirements (measurable, testable)
3. Technical Constraints (documented and validated)
4. Quality Attributes (prioritized)
5. Trade-offs (documented decisions)

**Quality Standards**:
- Every NFR must be measurable
- Every constraint must have rationale
- Quality attributes must be prioritized
- Trade-offs must be explicit

Begin with project principles.
```

### Actions

#### 2.1 Define Project Principles

**Establish Core Principles**:

```markdown
## Project Principles - [Project Name]

### Principle 1: [Principle Name]

**Description**: [What this principle means]

**Rationale**: [Why this principle matters for this project]

**Implications**:
- ✅ **Do**: [What this principle encourages]
- ❌ **Don't**: [What this principle discourages]
- 💡 **Example**: [Concrete example of applying this principle]

**Related Requirements**: REQ-XXX, REQ-YYY

**Priority**: [High/Medium/Low]

---

### Principle 2: [Principle Name]
[Same structure]

---

### Principle Examples for Reference:

**Example - User-Centric Design**:
- Description: Every technical decision must consider the end-user experience
- Rationale: Phase 0 showed users are frustrated with complexity
- Implications:
  - Do: Choose simple, intuitive solutions even if more work
  - Don't: Add technical complexity that users must understand
  - Example: Use convention over configuration to reduce user setup

**Example - Performance First** (if performance is critical NFR):
- Description: Performance is a feature, not an afterthought
- Rationale: Phase 0 identified slow response time as primary pain point
- Implications:
  - Do: Measure performance at every stage
  - Don't: Defer performance optimization to "later"
  - Example: Set performance budgets for every API endpoint

**Example - Security by Design** (if security is critical):
- Description: Security must be designed in, not bolted on
- Rationale: Handling sensitive customer data requires proactive security
- Implications:
  - Do: Apply defense in depth at every layer
  - Don't: Assume perimeter security is sufficient
  - Example: Encrypt data at rest and in transit always
```

#### 2.2 Specify Non-Functional Requirements

**Define Measurable NFRs**:

```markdown
## Non-Functional Requirements - [Project Name]

### Performance Requirements

**Response Time**:
- **REQ-NFR-PERF-001**: The system shall respond to user requests within 
  2 seconds for 95% of requests under normal load
  - **Measurement**: 95th percentile response time
  - **Normal Load**: [Define: e.g., 100 concurrent users]
  - **Priority**: Must-have
  - **Source**: Phase 0 success criteria

**Throughput**:
- **REQ-NFR-PERF-002**: The system shall process at least [N] transactions 
  per second
  - **Measurement**: TPS under load test
  - **Priority**: Must-have
  - **Source**: Phase 0 volume projections

**Capacity**:
- **REQ-NFR-PERF-003**: The system shall support [N] concurrent users
  - **Measurement**: Concurrent users without degradation
  - **Growth Plan**: [X% growth per quarter]
  - **Priority**: Must-have

---

### Security Requirements

**Authentication**:
- **REQ-NFR-SEC-001**: The system shall authenticate all users before granting 
  access to protected resources
  - **Method**: [OAuth 2.0, SAML, etc.]
  - **MFA Required**: [Yes/No/For sensitive operations]
  - **Priority**: Must-have
  - **Source**: Phase 0 constraints (compliance)

**Authorization**:
- **REQ-NFR-SEC-002**: The system shall implement role-based access control (RBAC)
  - **Roles**: [List key roles]
  - **Granularity**: [Resource-level, feature-level]
  - **Priority**: Must-have

**Data Protection**:
- **REQ-NFR-SEC-003**: The system shall encrypt sensitive data at rest
  - **Algorithm**: [AES-256 or equivalent]
  - **Key Management**: [Strategy]
  - **Priority**: Must-have

- **REQ-NFR-SEC-004**: The system shall encrypt all data in transit
  - **Protocol**: TLS 1.3 or higher
  - **Priority**: Must-have

**Audit Logging**:
- **REQ-NFR-SEC-005**: The system shall log all security-relevant events
  - **Events**: Authentication, authorization failures, data access
  - **Retention**: [Duration per compliance requirements]
  - **Priority**: Must-have

---

### Reliability Requirements

**Availability**:
- **REQ-NFR-REL-001**: The system shall maintain 99.9% uptime during business hours
  - **Measurement**: Uptime percentage (scheduled maintenance excluded)
  - **Business Hours**: [Define timezone and hours]
  - **Priority**: Must-have
  - **Downtime Allowance**: ~43 minutes/month

**Fault Tolerance**:
- **REQ-NFR-REL-002**: The system shall continue operating with degraded 
  functionality when non-critical components fail
  - **Critical Components**: [List]
  - **Graceful Degradation Strategy**: [Approach]
  - **Priority**: Should-have

**Recovery Time Objective (RTO)**:
- **REQ-NFR-REL-003**: The system shall recover from failures within [X] minutes
  - **Measurement**: Time from failure detection to service restoration
  - **Priority**: Must-have

**Recovery Point Objective (RPO)**:
- **REQ-NFR-REL-004**: The system shall limit data loss to [X] minutes of 
  transactions
  - **Measurement**: Maximum acceptable data loss window
  - **Backup Frequency**: [Determined by RPO]
  - **Priority**: Must-have

---

### Scalability Requirements

**Horizontal Scalability**:
- **REQ-NFR-SCALE-001**: The system shall scale horizontally by adding instances
  - **Stateless Design**: Required for web/API tiers
  - **Load Distribution**: Automatic via load balancer
  - **Priority**: Must-have

**Vertical Scalability**:
- **REQ-NFR-SCALE-002**: The system shall support vertical scaling of database
  - **Maximum Size**: [Storage and compute limits]
  - **Priority**: Should-have

**Growth Support**:
- **REQ-NFR-SCALE-003**: The system architecture shall support 10x growth 
  without major redesign
  - **Current**: [Baseline numbers]
  - **Future**: [10x projections]
  - **Priority**: Must-have
  - **Source**: Phase 0 business projections

---

### Maintainability Requirements

**Code Quality**:
- **REQ-NFR-MAINT-001**: The system shall maintain [X%] automated test coverage
  - **Target Coverage**: 80% for critical paths, 60% overall
  - **Test Types**: Unit, integration, end-to-end
  - **Priority**: Must-have

**Documentation**:
- **REQ-NFR-MAINT-002**: The system shall include inline code documentation 
  for all public APIs
  - **Format**: XML documentation comments (for C#)
  - **Coverage**: 100% of public interfaces
  - **Priority**: Must-have

**Modularity**:
- **REQ-NFR-MAINT-003**: The system shall be organized in loosely coupled, 
  highly cohesive modules
  - **Measurement**: Coupling metrics < [threshold]
  - **Priority**: Should-have

---

### Usability Requirements

**Learnability**:
- **REQ-NFR-USE-001**: New users shall complete key tasks within [X] minutes 
  without training
  - **Key Tasks**: [List 3-5 primary tasks]
  - **Measurement**: User testing
  - **Priority**: Should-have

**Accessibility**:
- **REQ-NFR-USE-002**: The system shall comply with WCAG 2.1 Level AA
  - **Standard**: [WCAG 2.1 AA]
  - **Testing**: Automated and manual accessibility testing
  - **Priority**: Must-have (if regulatory requirement)

---

### Compatibility Requirements

**Browser Support**:
- **REQ-NFR-COMPAT-001**: The system shall support the following browsers:
  - Chrome (last 2 versions)
  - Firefox (last 2 versions)
  - Safari (last 2 versions)
  - Edge (last 2 versions)
  - **Priority**: Must-have

**Integration Compatibility**:
- **REQ-NFR-COMPAT-002**: The system shall integrate with [System X] version [Y] or higher
  - **API Version**: [Specific version]
  - **Backward Compatibility**: [Required/Not Required]
  - **Priority**: Must-have (from Phase 0 constraints)
```

#### 2.3 Document Constraints

**Formalize All Constraints**:

```markdown
## Technical Constraints - [Project Name]

### Technology Stack Constraints

**Constraint 1: Programming Language**
- **Constraint**: Backend must be implemented in C# (.NET 8 or higher)
- **Type**: Hard constraint
- **Source**: Organizational standard, existing team expertise
- **Rationale**: [Why this constraint exists]
- **Impact**: 
  - ✅ Benefits: Team productivity, maintainability
  - ⚠️ Limitations: [Any limitations this creates]
- **Alternatives Considered**: [Other options and why rejected]

**Constraint 2: Database Technology**
- **Constraint**: Must use SQL Server 2019 or higher OR PostgreSQL 14+
- **Type**: Hard constraint
- **Source**: Enterprise licensing, DBA support
- **Rationale**: [Why this constraint exists]
- **Impact**: [How this affects design]

**Constraint 3: Cloud Provider**
- **Constraint**: Must deploy to [Azure/AWS/GCP] or on-premise
- **Type**: Hard constraint
- **Source**: [Business decision, existing infrastructure]
- **Rationale**: [Why this constraint exists]
- **Impact**: [How this affects architecture choices]

---

### Integration Constraints

**Constraint 4: External System Integration**
- **Constraint**: Must integrate with [Legacy System X] via SOAP
- **Type**: Hard constraint
- **Source**: Phase 0 constraints, existing system limitation
- **Rationale**: Cannot modify legacy system
- **Impact**: 
  - Must build adapter layer
  - Performance implications
  - Error handling complexity

---

### Regulatory/Compliance Constraints

**Constraint 5: Data Residency**
- **Constraint**: Customer data must remain in [geographic region]
- **Type**: Hard constraint
- **Source**: [Regulatory requirement - specify]
- **Rationale**: Legal compliance
- **Impact**: 
  - Cloud region selection limited
  - Data replication strategies constrained

**Constraint 6: Audit Trail**
- **Constraint**: All data access must be logged for [X] years
- **Type**: Hard constraint
- **Source**: [Compliance requirement]
- **Rationale**: Regulatory audit requirements
- **Impact**: Storage costs, logging infrastructure

---

### Budget/Resource Constraints

**Constraint 7: Infrastructure Budget**
- **Constraint**: Monthly infrastructure costs must not exceed $[X]
- **Type**: Soft constraint (can be negotiated if justified)
- **Source**: Budget allocation
- **Rationale**: [Business reasoning]
- **Impact**: Influences technology choices, limits redundancy

**Constraint 8: Timeline**
- **Constraint**: MVP must be delivered within [X] weeks
- **Type**: Soft constraint
- **Source**: Business need
- **Rationale**: [Market window, commitment to customer]
- **Impact**: Influences MVP scope, technical debt trade-offs

---

### Organizational Constraints

**Constraint 9: Support Hours**
- **Constraint**: DevOps team only available [hours/timezone]
- **Type**: Soft constraint
- **Source**: Team structure
- **Rationale**: Current team size and distribution
- **Impact**: Influences deployment windows, automation needs
```

#### 2.4 Prioritize Quality Attributes

**Quality Attribute Workshop Results**:

```markdown
## Quality Attributes Prioritization - [Project Name]

### Framework: Quality Attribute Workshop (QAW)

**Scenario-Based Prioritization**:

### Top Priority Quality Attributes (1-3)

**1. Security**
- **Rationale**: Handling sensitive customer data, regulatory requirements
- **Evidence**: Phase 0 identified security breach risk as high-impact
- **Scenarios**:
  - System prevents unauthorized access to customer records (99.99% effectiveness)
  - System detects and logs security incidents in real-time
  - System recovers from security breach within RTO
- **Trade-offs**: May impact performance (encryption overhead)

**2. Performance**
- **Rationale**: Phase 0 showed slow response time is #1 user complaint
- **Evidence**: Current system 15-second response time → Target: 2 seconds
- **Scenarios**:
  - User queries return results in < 2 seconds (95th percentile)
  - System handles 3x current load without degradation
  - Dashboard refreshes in real-time (< 500ms)
- **Trade-offs**: May increase infrastructure costs

**3. Maintainability**
- **Rationale**: Frequent feature requests, need to evolve quickly
- **Evidence**: Phase 0 identified agility as competitive advantage
- **Scenarios**:
  - Developer adds new feature in < 2 days
  - Bug fixes deployed in < 4 hours
  - New developer productive within 1 week
- **Trade-offs**: More upfront architecture work

---

### Secondary Quality Attributes (4-6)

**4. Scalability**
- **Rationale**: Projected 5x growth in 2 years
- **Acceptable Level**: Support 10x growth without redesign

**5. Reliability**
- **Rationale**: Business-critical system
- **Acceptable Level**: 99.9% uptime

**6. Usability**
- **Rationale**: Reducing training costs
- **Acceptable Level**: Key tasks completable in < 5 minutes

---

### Lower Priority (but still addressed)

**7. Testability**: Automated testing essential but not differentiating
**8. Portability**: Low priority - committed to cloud provider

---

### Trade-off Matrix

| Decision | Favors | Sacrifices | Rationale |
|----------|--------|------------|-----------|
| Caching layer | Performance | Consistency (eventual) | Users prioritize speed |
| Microservices | Maintainability | Complexity | Need independent deployability |
| Encryption at rest | Security | Performance (small) | Regulatory requirement |
```

#### 2.5 Create Constitution Document

**Use Template**: `constitution.template.md`

**Save as**: `artifacts/constitution.md`

---

## Step 3: System Architecture (Architect Agent)

### Objective
Design the overall system architecture including component structure, interactions, and technology selections.

### Agent: Architect Agent (system design mode)

### Time Required
4-6 hours

### Actions

#### 3.1 Choose Architecture Style

**Architecture Style Decision**:

```markdown
## Architecture Style Selection - [Project Name]

### Options Considered

**Option 1: Monolithic Architecture**
- **Pros**:
  - Simple deployment
  - Lower initial complexity
  - Good for small team
  - Easier debugging
- **Cons**:
  - Harder to scale specific components
  - Tight coupling over time
  - Single point of failure
  - All-or-nothing deployments
- **Fit**: [Good/Moderate/Poor] for this project

**Option 2: Microservices Architecture**
- **Pros**:
  - Independent scaling
  - Technology flexibility
  - Team autonomy
  - Fault isolation
- **Cons**:
  - Operational complexity
  - Network latency
  - Data consistency challenges
  - Requires mature DevOps
- **Fit**: [Good/Moderate/Poor] for this project

**Option 3: Modular Monolith**
- **Pros**:
  - Clear boundaries
  - Simpler than microservices
  - Can evolve to microservices
  - Single deployment initially
- **Cons**:
  - Discipline required
  - Module boundaries can erode
  - Scaling less flexible than microservices
- **Fit**: [Good/Moderate/Poor] for this project

**Option 4: [Other Pattern]**
[If considering event-driven, layered, hexagonal, etc.]

---

### Decision: [Selected Architecture Style]

**Rationale**:
1. [Reason 1 based on requirements]
2. [Reason 2 based on NFRs]
3. [Reason 3 based on constraints]
4. [Reason 4 based on team capabilities]

**Trade-offs Accepted**:
- Giving up: [What we're sacrificing]
- Gaining: [What we're prioritizing]

**Evolution Path**:
[How this can evolve if needs change]
```

**Save as ADR**: `architecture/adrs/ADR-001-architecture-style.md`

#### 3.2 Define System Context

**System Context Diagram**:

```markdown
## System Context - [Project Name]

### Context Diagram
[Create diagram showing system boundary, external actors, external systems]

```
┌─────────────────────────────────────────────────────────────┐
│                     External Context                         │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   [External User] ──────────┐                              │
│                             │                               │
│   [Admin User] ─────────────┤                              │
│                             │                               │
│                             ▼                               │
│                   ┌──────────────────┐                      │
│                   │                  │                      │
│                   │  [System Name]   │                      │
│                   │                  │                      │
│                   └──────────────────┘                      │
│                             │                               │
│                             ├──────────► [External System 1]│
│                             │                               │
│                             ├──────────► [External System 2]│
│                             │                               │
│                             └──────────► [Third-party API]  │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### External Actors

**End Users**:
- **Description**: [Who they are]
- **Interactions**: [What they do with the system]
- **Requirements Supported**: REQ-XXX, REQ-YYY

**Administrators**:
- **Description**: [Who they are]
- **Interactions**: [What they do with the system]
- **Requirements Supported**: REQ-AAA, REQ-BBB

---

### External Systems

**System 1: [Legacy System X]**
- **Purpose**: [Why we integrate]
- **Integration Method**: [SOAP, REST, File transfer, etc.]
- **Data Exchanged**: [What flows in/out]
- **Frequency**: [Real-time, batch, etc.]
- **Constraints**: [From Phase 0]
- **Requirements**: REQ-INT-001

**System 2: [Payment Gateway]**
- **Purpose**: [Why we integrate]
- **Integration Method**: [REST API]
- **Data Exchanged**: [Payment transactions]
- **SLA**: [Response time, availability]
- **Requirements**: REQ-INT-002
```

**Save diagram**: `architecture/diagrams/context/system-context.png`
**Save description**: `architecture/diagrams/context/system-context.md`

#### 3.3 Define Component Architecture

**Component Breakdown**:

```markdown
## Component Architecture - [Project Name]

### Component Diagram

[Create component diagram showing major components and dependencies]

### Components

#### Component 1: [Name, e.g., "API Gateway"]

**Responsibility**: [What this component does]

**Type**: [Infrastructure/Business Logic/Data Access/UI]

**Technology**: [Specific technology choice]
- Framework: [e.g., ASP.NET Core for C#]
- Version: [e.g., .NET 8]
- **Rationale**: [Why this technology]

**Interfaces**:
- **Provided**: [What services/APIs this component offers]
  - Interface 1: [Description]
  - Interface 2: [Description]
- **Required**: [What dependencies this component has]
  - Dependency 1: [Component it depends on]
  - Dependency 2: [Component it depends on]

**Data**: [What data this component owns/manages]

**NFR Responsibilities**:
- **Performance**: [How this component contributes to performance NFR]
- **Security**: [Security controls in this component]
- **Scalability**: [Scaling characteristics]

**Supporting Requirements**: REQ-XXX, REQ-YYY, REQ-ZZZ

---

#### Component 2: [Name, e.g., "Core Business Logic"]
[Same structure]

#### Component 3: [Name, e.g., "Data Access Layer"]
[Same structure]

---

### Component Interaction Patterns

**Synchronous Communication**:
- **Pattern**: Request/Response (HTTP REST)
- **Used Between**: [Component A] ↔ [Component B]
- **Rationale**: [Why synchronous is appropriate]
- **Error Handling**: [Strategy]

**Asynchronous Communication**:
- **Pattern**: Message Queue (e.g., RabbitMQ, Azure Service Bus)
- **Used Between**: [Component C] → [Component D]
- **Rationale**: [Why async is appropriate]
- **Message Types**: [Types of messages]
- **Error Handling**: [Dead letter queue, retry logic]

**Data Flow**:
```
User Request → API Gateway → Business Logic → Data Access → Database
                    ↓                              ↓
               Cache Layer                    Message Queue
                    ↓                              ↓
             Response Cache                Integration Service
```
```

**Save diagram**: `architecture/diagrams/component/component-architecture.png`
**Save description**: `architecture/component-architecture.md`

#### 3.4 Technology Stack Selection

**Complete Technology Stack**:

```markdown
## Technology Stack - [Project Name]

### Frontend

**Framework**: [e.g., React 18+ or Blazor for C#]
- **Rationale**: [Why chosen]
- **Constraints Satisfied**: [From Phase 0]

**State Management**: [e.g., Redux, Context API, or built-in]
- **Rationale**: [Why chosen]

**UI Library**: [e.g., Material-UI, Ant Design, or custom]
- **Rationale**: [Why chosen]

**Build Tools**: [e.g., Vite, Webpack]

---

### Backend

**Language & Runtime**: C# with .NET 8
- **Rationale**: Constraint from Phase 0, team expertise
- **Framework**: ASP.NET Core 8 Web API

**API Style**: RESTful APIs (with OpenAPI/Swagger documentation)
- **Rationale**: Industry standard, excellent tooling

**Additional Libraries**:
- **Authentication**: [e.g., IdentityServer, Azure AD]
- **Validation**: FluentValidation
- **Mapping**: AutoMapper
- **Logging**: Serilog
- **Testing**: xUnit, NUnit, or MSTest

---

### Database

**Primary Database**: [SQL Server 2022 or PostgreSQL 15]
- **Rationale**: Constraint from Phase 0, ACID requirements
- **ORM**: Entity Framework Core 8
- **Migration Tool**: EF Core Migrations

**Caching Layer**: Redis 7+
- **Rationale**: Performance NFR (2-second response time)
- **Use Cases**: Session data, frequently accessed data, query results

**Search Engine** (if needed): Elasticsearch 8+
- **Rationale**: Full-text search requirements (REQ-SEARCH-001)

---

### Infrastructure

**Cloud Provider**: [Azure / AWS / GCP per constraint]
- **Rationale**: [Constraint from Phase 0 or decision]

**Container Platform**: Docker
- **Orchestration**: Kubernetes or Azure Container Apps
- **Rationale**: Scalability NFR, consistent deployment

**CI/CD**: [Azure DevOps / GitHub Actions / GitLab CI]
- **Rationale**: [Existing tools or new selection]

**Monitoring & Logging**:
- **APM**: Application Insights or New Relic
- **Logging**: Serilog → Elasticsearch → Kibana (ELK Stack)
- **Metrics**: Prometheus + Grafana
- **Rationale**: Observability for NFR monitoring

---

### Integration

**Message Broker**: [RabbitMQ / Azure Service Bus / AWS SQS]
- **Rationale**: Async processing requirements

**API Gateway**: [Azure API Management / Kong / custom]
- **Rationale**: Security, rate limiting, API versioning

---

### Security

**Identity Provider**: [Azure AD / Auth0 / IdentityServer]
- **Rationale**: SSO requirements, security NFR

**Secrets Management**: [Azure Key Vault / AWS Secrets Manager / HashiCorp Vault]
- **Rationale**: Security NFR (protect credentials)

---

### Development Tools

**Version Control**: Git (GitHub / Azure Repos)
**IDE**: Visual Studio 2022 / VS Code / Rider
**API Testing**: Postman / Insomnia
**Load Testing**: k6 / JMeter / Azure Load Testing
```

**Save as**: `architecture/technology-stack.md`

#### 3.5 Document Architecture Decisions (ADRs)

**Create ADRs for Key Decisions**:

```markdown
# ADR-002: Database Technology Selection

**Status**: Accepted
**Date**: [YYYY-MM-DD]
**Deciders**: [Names]
**Consulted**: [Names]

## Context

We need to select a primary database technology for the system. The system 
requires ACID transactions, complex queries, and will handle [X] transactions 
per day.

**Requirements**:
- REQ-NFR-PERF-002: Handle [X] TPS
- REQ-NFR-REL-004: RPO of [Y] minutes
- REQ-DATA-001: Support for complex relational queries

**Constraints**:
- Must use SQL Server OR PostgreSQL (organizational constraint)
- Must be supportable by existing DBA team

## Decision

We will use **PostgreSQL 15** as our primary database.

## Rationale

1. **Performance**: Excellent performance for our read-heavy workload
2. **Cost**: Lower licensing costs than SQL Server Enterprise
3. **Features**: Advanced features (JSONB, full-text search) reduce need 
   for additional data stores
4. **Team Expertise**: Team has PostgreSQL experience
5. **Open Source**: No vendor lock-in, strong community

## Consequences

**Positive**:
+ Lower infrastructure costs
+ Modern features (JSONB) enable flexible schema
+ Strong full-text search reduces need for Elasticsearch
+ Excellent tooling (pgAdmin, DataGrip)

**Negative**:
- Less integrated with Microsoft ecosystem than SQL Server
- DBA team needs additional PostgreSQL training
- Some internal tools built for SQL Server will need adaptation

**Neutral**:
- Both options would have met requirements

## Alternatives Considered

**SQL Server 2022**:
- Pros: Existing DBA expertise, tool integration
- Cons: Higher licensing costs, less flexible data types
- Why not chosen: Cost and JSONB features valuable

## Compliance

**NFRs Supported**: REQ-NFR-PERF-002 (TPS), REQ-NFR-REL-004 (RPO via replication)
**Constraints Respected**: Yes (within allowed options)

## Notes

- Will use Entity Framework Core 8 as ORM (database-agnostic)
- Migration path to SQL Server available if needed (EF Core abstraction)
```

**Create ADRs for**:
- ADR-001: Architecture Style
- ADR-002: Database Technology
- ADR-003: Frontend Framework
- ADR-004: API Design Style (REST vs GraphQL vs gRPC)
- ADR-005: Authentication Strategy
- ADR-006: Caching Strategy
- ADR-007: Async Communication Pattern
- [Additional ADRs as needed]

**Save all ADRs**: `architecture/adrs/ADR-XXX-title.md`

---

## Step 4: Data Model Design (Architect Agent)

### Objective
Design the complete data model including entities, relationships, and constraints.

### Agent: Architect Agent (data modeling mode)

### Time Required
3-4 hours

### Actions

#### 4.1 Identify Entities

**Extract Entities from Requirements**:

```markdown
## Entity Identification - [Project Name]

### From Requirements Analysis

**From REQ-USER-001** (User management):
→ **Entity**: User
→ **Entity**: Role
→ **Entity**: Permission

**From REQ-ORDER-001** (Order processing):
→ **Entity**: Order
→ **Entity**: OrderItem
→ **Entity**: Product

**From REQ-PAYMENT-001** (Payment handling):
→ **Entity**: Payment
→ **Entity**: PaymentMethod

[Continue for all requirements]

### Entity List
1. User
2. Role
3. Permission
4. Order
5. OrderItem
6. Product
7. Category
8. Payment
9. PaymentMethod
10. [Complete list]

Total Entities: [N]
```

#### 4.2 Define Entity Details

**Complete Entity Definitions**:

```markdown
## Entity Definitions - [Project Name]

### Entity: User

**Description**: Represents a user of the system (customer or administrator)

**Attributes**:

| Attribute | Data Type | Nullable | Default | Description |
|-----------|-----------|----------|---------|-------------|
| UserId | Guid (PK) | No | NewGuid() | Unique identifier |
| Email | String(255) | No | - | User's email (unique) |
| PasswordHash | String(255) | No | - | Hashed password |
| FirstName | String(100) | No | - | User's first name |
| LastName | String(100) | No | - | User's last name |
| PhoneNumber | String(20) | Yes | - | Contact phone |
| CreatedAt | DateTime | No | GETDATE() | Account creation time |
| UpdatedAt | DateTime | No | GETDATE() | Last update time |
| LastLoginAt | DateTime | Yes | - | Last login timestamp |
| IsActive | Boolean | No | true | Account active status |
| EmailVerified | Boolean | No | false | Email verification status |

**Constraints**:
- PRIMARY KEY: UserId
- UNIQUE: Email
- CHECK: Email matches email format
- CHECK: PasswordHash length >= 60 (bcrypt)

**Indexes**:
- IX_User_Email (UNIQUE, for login lookups)
- IX_User_CreatedAt (for analytics)

**Supporting Requirements**: REQ-USER-001, REQ-USER-002, REQ-SEC-001

---

### Entity: Order
[Same detailed structure]

---

### Entity: Product
[Same detailed structure]
```

#### 4.3 Define Relationships

**Entity Relationship Diagram (ERD)**:

```markdown
## Entity Relationships - [Project Name]

### Relationships

**User ↔ Role** (Many-to-Many):
- **Description**: Users can have multiple roles
- **Implementation**: UserRole junction table
- **Cardinality**: User (1...*) ↔ (0...*) Role
- **Cascade**: ON DELETE CASCADE (remove role assignments when user deleted)
- **Supporting**: REQ-SEC-002 (RBAC)

**Role ↔ Permission** (Many-to-Many):
- **Description**: Roles grant multiple permissions
- **Implementation**: RolePermission junction table
- **Cardinality**: Role (1...*) ↔ (0...*) Permission
- **Supporting**: REQ-SEC-002 (RBAC)

**User → Order** (One-to-Many):
- **Description**: User places multiple orders
- **Implementation**: Foreign key Order.UserId → User.UserId
- **Cardinality**: User (1) → (0...*) Order
- **Cascade**: ON DELETE RESTRICT (cannot delete user with orders)
- **Supporting**: REQ-ORDER-001

**Order → OrderItem** (One-to-Many):
- **Description**: Order contains multiple items
- **Implementation**: Foreign key OrderItem.OrderId → Order.OrderId
- **Cardinality**: Order (1) → (1...*) OrderItem
- **Cascade**: ON DELETE CASCADE (delete items when order deleted)
- **Supporting**: REQ-ORDER-002

**OrderItem → Product** (Many-to-One):
- **Description**: Order items reference products
- **Implementation**: Foreign key OrderItem.ProductId → Product.ProductId
- **Cardinality**: OrderItem (*) → (1) Product
- **Cascade**: ON DELETE RESTRICT (cannot delete product in orders)
- **Supporting**: REQ-ORDER-003

[Continue for all relationships]

---

### ERD Diagram

[Create Entity Relationship Diagram showing all entities and relationships]
```

**Save diagram**: `architecture/diagrams/data-model/erd.png`

#### 4.4 Define Database Schema

**Complete Database Schema (for C# / Entity Framework)**:

```csharp
// User.cs
namespace [ProjectName].Domain.Entities
{
    /// <summary>
    /// Represents a user in the system
    /// </summary>
    public class User
    {
        /// <summary>
        /// Unique identifier for the user
        /// </summary>
        public Guid UserId { get; set; }

        /// <summary>
        /// User's email address (unique, used for login)
        /// </summary>
        [Required]
        [EmailAddress]
        [MaxLength(255)]
        public string Email { get; set; }

        /// <summary>
        /// Hashed password (never store plain text)
        /// </summary>
        [Required]
        [MaxLength(255)]
        public string PasswordHash { get; set; }

        // ... other properties

        // Navigation properties
        public virtual ICollection<UserRole> UserRoles { get; set; }
        public virtual ICollection<Order> Orders { get; set; }
    }
}

// Order.cs
namespace [ProjectName].Domain.Entities
{
    public class Order
    {
        public Guid OrderId { get; set; }
        public Guid UserId { get; set; }
        
        // ... other properties
        
        // Navigation properties
        public virtual User User { get; set; }
        public virtual ICollection<OrderItem> OrderItems { get; set; }
    }
}

// Entity Framework Configuration
namespace [ProjectName].Data.Configurations
{
    public class UserConfiguration : IEntityTypeConfiguration<User>
    {
        public void Configure(EntityTypeBuilder<User> builder)
        {
            builder.ToTable("Users");
            
            builder.HasKey(u => u.UserId);
            
            builder.Property(u => u.Email)
                .IsRequired()
                .HasMaxLength(255);
            
            builder.HasIndex(u => u.Email)
                .IsUnique()
                .HasDatabaseName("IX_User_Email");
            
            // Relationships
            builder.HasMany(u => u.Orders)
                .WithOne(o => o.User)
                .HasForeignKey(o => o.UserId)
                .OnDelete(DeleteBehavior.Restrict);
        }
    }
}
```

**Save schema files**: `architecture/data-model/schema/`

#### 4.5 Create Data Model Document

**Use Template**: `data-model.template.md`

**Save as**: `artifacts/data-model.md`

---

## Step 5: API Design (Architect Agent)

### Objective
Design the API contracts including endpoints, request/response formats, and error handling.

### Agent: Architect Agent (API design mode)

### Time Required
3-4 hours

### Actions

#### 5.1 Define API Design Principles

**API Design Philosophy**:

```markdown
## API Design Principles - [Project Name]

### RESTful API Principles

1. **Resource-Oriented**: URLs represent resources, not actions
   - ✅ Good: `GET /users/123`
   - ❌ Bad: `GET /getUser?id=123`

2. **HTTP Methods**: Use correct HTTP verbs
   - GET: Retrieve resource(s)
   - POST: Create new resource
   - PUT: Update entire resource
   - PATCH: Partial update
   - DELETE: Remove resource

3. **Status Codes**: Use appropriate HTTP status codes
   - 200: Success
   - 201: Created
   - 204: No Content
   - 400: Bad Request
   - 401: Unauthorized
   - 403: Forbidden
   - 404: Not Found
   - 500: Internal Server Error

4. **Versioning**: API versioning strategy
   - Method: URL path versioning
   - Format: `/api/v1/resource`
   - Rationale: Clear, explicit, easy to route

5. **Consistency**: Consistent naming conventions
   - Plural nouns for collections: `/users`, `/orders`
   - Lowercase with hyphens: `/order-items`
   - Consistent parameter names

6. **Pagination**: For collection endpoints
   - Query parameters: `?page=1&size=20`
   - Response includes: total count, current page, total pages
   - Default page size: 20, max: 100

7. **Filtering & Sorting**:
   - Filter: `?status=active&category=electronics`
   - Sort: `?sortBy=createdAt&sortOrder=desc`

8. **Error Responses**: Consistent error format
   ```json
   {
     "error": {
       "code": "VALIDATION_ERROR",
       "message": "Invalid input data",
       "details": [
         {
           "field": "email",
           "message": "Email format is invalid"
         }
       ],
       "timestamp": "2025-01-15T10:30:00Z",
       "requestId": "abc-123-def"
     }
   }
   ```

9. **Security**: All endpoints require authentication (except public endpoints)

10. **Documentation**: OpenAPI 3.0 specification for all endpoints
```

#### 5.2 Map Requirements to API Endpoints

**Endpoint Mapping**:

```markdown
## API Endpoints Mapping - [Project Name]

### From Requirements to Endpoints

**REQ-USER-001**: System shall allow user registration
→ `POST /api/v1/users/register`

**REQ-USER-002**: System shall allow user authentication
→ `POST /api/v1/auth/login`
→ `POST /api/v1/auth/logout`
→ `POST /api/v1/auth/refresh`

**REQ-USER-003**: System shall allow password reset
→ `POST /api/v1/auth/forgot-password`
→ `POST /api/v1/auth/reset-password`

**REQ-ORDER-001**: System shall allow order creation
→ `POST /api/v1/orders`

**REQ-ORDER-002**: System shall allow order retrieval
→ `GET /api/v1/orders/{orderId}`
→ `GET /api/v1/orders` (list user's orders)

**REQ-ORDER-003**: System shall allow order cancellation
→ `DELETE /api/v1/orders/{orderId}`

[Continue mapping all requirements to endpoints]

### Endpoint Summary
- Total Endpoints: [N]
- Public Endpoints: [N]
- Authenticated Endpoints: [N]
- Admin-only Endpoints: [N]
```

#### 5.3 Define API Specification (OpenAPI)

**Use Template**: `api-spec.template.json`

**API Specification Example** (OpenAPI 3.0):

```json
{
  "openapi": "3.0.3",
  "info": {
    "title": "[Project Name] API",
    "description": "RESTful API for [Project Name]",
    "version": "1.0.0",
    "contact": {
      "name": "API Support",
      "email": "api@example.com"
    }
  },
  "servers": [
    {
      "url": "https://api.example.com/v1",
      "description": "Production server"
    },
    {
      "url": "https://api-staging.example.com/v1",
      "description": "Staging server"
    }
  ],
  "paths": {
    "/users/register": {
      "post": {
        "summary": "Register new user",
        "description": "Creates a new user account",
        "tags": ["Authentication"],
        "operationId": "registerUser",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/UserRegistrationRequest"
              },
              "example": {
                "email": "user@example.com",
                "password": "SecureP@ssw0rd",
                "firstName": "John",
                "lastName": "Doe"
              }
            }
          }
        },
        "responses": {
          "201": {
            "description": "User created successfully",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/UserResponse"
                }
              }
            }
          },
          "400": {
            "description": "Invalid input",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/ErrorResponse"
                }
              }
            }
          },
          "409": {
            "description": "Email already exists"
          }
        }
      }
    },
    "/auth/login": {
      "post": {
        "summary": "User login",
        "description": "Authenticates user and returns JWT token",
        "tags": ["Authentication"],
        "operationId": "login",
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/LoginRequest"
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "Login successful",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/LoginResponse"
                }
              }
            }
          },
          "401": {
            "description": "Invalid credentials"
          }
        }
      }
    },
    "/orders": {
      "get": {
        "summary": "List orders",
        "description": "Get list of orders for authenticated user",
        "tags": ["Orders"],
        "operationId": "listOrders",
        "security": [
          {
            "bearerAuth": []
          }
        ],
        "parameters": [
          {
            "name": "page",
            "in": "query",
            "schema": {
              "type": "integer",
              "default": 1
            }
          },
          {
            "name": "size",
            "in": "query",
            "schema": {
              "type": "integer",
              "default": 20,
              "maximum": 100
            }
          },
          {
            "name": "status",
            "in": "query",
            "schema": {
              "type": "string",
              "enum": ["pending", "processing", "shipped", "delivered", "cancelled"]
            }
          }
        ],
        "responses": {
          "200": {
            "description": "List of orders",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/OrderListResponse"
                }
              }
            }
          }
        }
      },
      "post": {
        "summary": "Create order",
        "description": "Create a new order",
        "tags": ["Orders"],
        "operationId": "createOrder",
        "security": [
          {
            "bearerAuth": []
          }
        ],
        "requestBody": {
          "required": true,
          "content": {
            "application/json": {
              "schema": {
                "$ref": "#/components/schemas/CreateOrderRequest"
              }
            }
          }
        },
        "responses": {
          "201": {
            "description": "Order created",
            "content": {
              "application/json": {
                "schema": {
                  "$ref": "#/components/schemas/OrderResponse"
                }
              }
            }
          }
        }
      }
    }
  },
  "components": {
    "securitySchemes": {
      "bearerAuth": {
        "type": "http",
        "scheme": "bearer",
        "bearerFormat": "JWT"
      }
    },
    "schemas": {
      "UserRegistrationRequest": {
        "type": "object",
        "required": ["email", "password", "firstName", "lastName"],
        "properties": {
          "email": {
            "type": "string",
            "format": "email",
            "maxLength": 255
          },
          "password": {
            "type": "string",
            "format": "password",
            "minLength": 8,
            "maxLength": 100
          },
          "firstName": {
            "type": "string",
            "maxLength": 100
          },
          "lastName": {
            "type": "string",
            "maxLength": 100
          }
        }
      },
      "UserResponse": {
        "type": "object",
        "properties": {
          "userId": {
            "type": "string",
            "format": "uuid"
          },
          "email": {
            "type": "string"
          },
          "firstName": {
            "type": "string"
          },
          "lastName": {
            "type": "string"
          },
          "createdAt": {
            "type": "string",
            "format": "date-time"
          }
        }
      },
      "ErrorResponse": {
        "type": "object",
        "properties": {
          "error": {
            "type": "object",
            "properties": {
              "code": {
                "type": "string"
              },
              "message": {
                "type": "string"
              },
              "details": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "field": {
                      "type": "string"
                    },
                    "message": {
                      "type": "string"
                    }
                  }
                }
              },
              "timestamp": {
                "type": "string",
                "format": "date-time"
              },
              "requestId": {
                "type": "string"
              }
            }
          }
        }
      }
    }
  }
}
```

**Save as**: `artifacts/api-spec.json`

---

## Step 6: Supporting Architecture Designs (Architect Agent)

### Objective
Complete remaining architecture specifications: security, deployment, integration, monitoring.

### Time Required
3-4 hours

### Actions

#### 6.1 Security Architecture

```markdown
## Security Architecture - [Project Name]

### Authentication Flow

```
1. User submits credentials → API Gateway
2. API Gateway → Authentication Service
3. Authentication Service validates → Database
4. Return JWT token (access + refresh)
5. Client includes JWT in Authorization header for subsequent requests
```

**Token Structure**:
- Access Token: Short-lived (15 minutes), contains claims
- Refresh Token: Long-lived (7 days), stored securely
- Claims: userId, roles, permissions, issuedAt, expiresAt

---

### Authorization Model (RBAC)

**Roles**:
- SuperAdmin: Full system access
- Admin: Manage users, view all data
- Manager: Manage team data
- User: Own data only
- Guest: Read-only public data

**Permission Checking**:
```csharp
// C# Example
[Authorize(Policy = "RequireAdminRole")]
public async Task<IActionResult> DeleteUser(Guid userId)
{
    // Only admins can delete users
}
```

---

### Data Protection

**Encryption at Rest**:
- Database: Transparent Data Encryption (TDE)
- File Storage: AES-256 encryption
- Backups: Encrypted before storage

**Encryption in Transit**:
- TLS 1.3 for all HTTP traffic
- Certificate management via Let's Encrypt (automated renewal)

**Sensitive Data Handling**:
- Passwords: bcrypt hashing (cost factor 12)
- PII: Encrypted at column level
- Credit Cards: Not stored (tokenization via payment gateway)

---

### Security Controls

**Input Validation**:
- Server-side validation for all inputs
- Parameterized queries (prevent SQL injection)
- Request size limits
- Content-Type validation

**Output Encoding**:
- HTML encoding for display
- JSON encoding for API responses

**CORS Policy**:
- Whitelist allowed origins
- Credentials support: false (except for specific trusted domains)

**Rate Limiting**:
- Per IP: 100 requests/minute
- Per User: 1000 requests/hour
- Admin endpoints: 50 requests/minute

**Security Headers**:
- Content-Security-Policy
- X-Frame-Options: DENY
- X-Content-Type-Options: nosniff
- Strict-Transport-Security

---

### Audit Logging

**What to Log**:
- All authentication attempts (success/failure)
- All authorization failures
- All data access (who accessed what, when)
- All data modifications (who changed what, when)
- All admin actions

**Log Format** (JSON):
```json
{
  "timestamp": "2025-01-15T10:30:00Z",
  "eventType": "DATA_ACCESS",
  "userId": "guid",
  "resource": "/api/v1/orders/123",
  "action": "READ",
  "result": "SUCCESS",
  "ipAddress": "192.168.1.1",
  "userAgent": "...",
  "requestId": "abc-123"
}
```

**Log Retention**: 7 years (compliance requirement)
```

#### 6.2 Deployment Architecture

```markdown
## Deployment Architecture - [Project Name]

### Deployment Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                         Cloud Environment                    │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   ┌─────────────────────────────────────────────────┐      │
│   │            Load Balancer / CDN                   │      │
│   └──────────────────┬──────────────────────────────┘      │
│                      │                                       │
│         ┌────────────┴────────────┐                         │
│         │                         │                         │
│   ┌─────▼──────┐           ┌─────▼──────┐                 │
│   │  Web App   │           │  Web App   │                  │
│   │  Instance  │           │  Instance  │                  │
│   └─────┬──────┘           └─────┬──────┘                 │
│         │                         │                         │
│         └────────────┬────────────┘                         │
│                      │                                       │
│                ┌─────▼──────┐                               │
│                │  API Gateway│                               │
│                └─────┬──────┘                               │
│                      │                                       │
│         ┌────────────┴────────────┐                         │
│         │                         │                         │
│   ┌─────▼──────┐           ┌─────▼──────┐                 │
│   │  API       │           │  API       │                  │
│   │  Instance  │           │  Instance  │                  │
│   └─────┬──────┘           └─────┬──────┘                 │
│         │                         │                         │
│         └────────────┬────────────┘                         │
│                      │                                       │
│            ┌─────────┼─────────┐                           │
│            │         │         │                             │
│      ┌─────▼─┐  ┌───▼───┐  ┌─▼────┐                       │
│      │Database│  │ Redis │  │Message│                       │
│      │(Primary│  │(Cache)│  │ Queue │                       │
│      │Replica)│  └───────┘  └───────┘                       │
│      └────────┘                                              │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### Environment Strategy

**Development**:
- Local development: Docker Compose
- Shared dev environment: Kubernetes cluster

**Testing/QA**:
- Automated test environment: Spins up/down with CI/CD
- Manual QA environment: Persistent, refreshed weekly

**Staging**:
- Production-like environment
- Subset of production data (anonymized)
- Final validation before production

**Production**:
- High availability: Multi-AZ deployment
- Auto-scaling: CPU > 70% triggers scale-out
- Blue-green deployment for zero-downtime

---

### CI/CD Pipeline

**Pipeline Stages**:
1. **Build**: Compile code, restore dependencies
2. **Test**: Unit tests, integration tests (must pass 100%)
3. **Quality Gate**: Code coverage > 80%, no critical issues
4. **Package**: Create Docker images
5. **Deploy to Dev**: Automatic on main branch
6. **Deploy to Staging**: Automatic on release branch
7. **Deploy to Prod**: Manual approval required

**Deployment Strategy**: Rolling update
- Max surge: 1 (create 1 new instance)
- Max unavailable: 0 (zero downtime)
- Health check: 30-second timeout
- Rollback: Automatic on health check failure

---

### Infrastructure as Code

**Tool**: Terraform

**Resources Managed**:
- Kubernetes cluster
- Database instances
- Load balancers
- CDN configuration
- DNS records
- Monitoring/alerting rules
```

#### 6.3 Integration Architecture

```markdown
## Integration Architecture - [Project Name]

### Integration Patterns

**Pattern 1: REST API Integration** (with Legacy System X)
- **System**: Legacy ERP system
- **Protocol**: SOAP (wrapped in REST adapter)
- **Frequency**: Real-time
- **Data**: Order data
- **Error Handling**: Retry 3 times with exponential backoff, then dead-letter queue
- **Circuit Breaker**: Open after 5 consecutive failures

**Pattern 2: Event-Driven Integration** (with Inventory Service)
- **System**: Inventory Management
- **Protocol**: Message queue (RabbitMQ)
- **Event Types**: OrderCreated, OrderCancelled
- **Reliability**: At-least-once delivery
- **Error Handling**: Dead-letter queue for failed processing

**Pattern 3: File-Based Integration** (with Analytics Platform)
- **System**: Data Warehouse
- **Protocol**: SFTP
- **Frequency**: Daily batch (2 AM)
- **Format**: CSV files
- **Error Handling**: Email alert on failure, manual retry

---

### Integration Components

**API Gateway**:
- Route requests to appropriate services
- Rate limiting (per integration)
- API key management
- Request/response transformation

**Adapter Layer**:
- Converts between internal and external formats
- Protocol translation (REST ↔ SOAP)
- Error mapping

**Message Broker**:
- Asynchronous event distribution
- Guaranteed delivery
- Message ordering (per partition)
```

#### 6.4 Monitoring & Observability

```markdown
## Monitoring & Observability - [Project Name]

### Application Performance Monitoring (APM)

**Tool**: Application Insights (or New Relic)

**Metrics Collected**:
- Request rate (requests/second)
- Response time (p50, p95, p99)
- Error rate (%)
- Dependency performance (database, cache, external APIs)
- Custom business metrics (orders/minute, revenue/hour)

**Alerting Thresholds**:
- Response time p95 > 5 seconds → Warning
- Response time p95 > 10 seconds → Critical
- Error rate > 1% → Warning
- Error rate > 5% → Critical
- Availability < 99.5% → Critical

---

### Logging

**Structured Logging** (JSON format via Serilog):
```csharp
// C# Example
_logger.LogInformation(
    "Order created: {OrderId} by user {UserId} with total {Total}",
    orderId, userId, total
);
```

**Log Aggregation**: ELK Stack (Elasticsearch, Logstash, Kibana)

**Log Levels**:
- DEBUG: Development only
- INFO: Normal operations
- WARNING: Recoverable issues
- ERROR: Failures requiring attention
- CRITICAL: System down

---

### Metrics & Dashboards

**System Metrics** (Prometheus + Grafana):
- CPU utilization (%)
- Memory usage (%)
- Disk I/O
- Network throughput

**Business Metrics**:
- Active users
- Orders per minute
- Revenue per hour
- Conversion rate

**Dashboards**:
1. System Health: Infrastructure metrics
2. Application Health: APM metrics
3. Business KPIs: Revenue, orders, users
4. Security: Failed logins, suspicious activity

---

### Distributed Tracing

**Tool**: OpenTelemetry + Jaeger

**Trace Context**:
- Propagate correlation ID through all services
- Track request flow: API → Service → Database
- Identify performance bottlenecks

**Example Trace**:
```
Request ID: abc-123
├─ API Gateway (10ms)
├─ Authentication Service (50ms)
├─ Order Service (200ms)
│  ├─ Database Query (150ms)  ← BOTTLENECK
│  └─ Cache Check (5ms)
└─ Response (5ms)
Total: 265ms
```
```

---

## Step 7: Architecture Review

### Objective
Review architecture with technical stakeholders and incorporate feedback.

### Time Required
1-2 weeks (including review period)

### Actions

#### 7.1 Prepare Review Package

```markdown
# Architecture Review Package - [Project Name]

**Review Date**: [YYYY-MM-DD]
**Reviewers**: [Technical Lead, Security Architect, DBA, DevOps Lead]
**Review Duration**: [1-2 weeks]

## Documents for Review

**Primary Documents**:
1. constitution.md - Project principles, NFRs, constraints
2. architecture.md - System architecture, components, technology stack
3. data-model.md - Database schema, entities, relationships
4. api-spec.json - API contracts
5. All ADRs - Architecture decision records

**Supporting Documents**:
- spec.md - Functional requirements (for context)
- prd.md - Product vision (for context)

## Review Checklist

**Technical Review**:
- [ ] Architecture supports all functional requirements
- [ ] NFRs are addressable with proposed design
- [ ] Technology choices are appropriate
- [ ] Scalability approach is sound
- [ ] Performance targets are achievable
- [ ] No single points of failure (where possible)

**Security Review**:
- [ ] Authentication/authorization design is secure
- [ ] Data protection meets requirements
- [ ] Security controls are comprehensive
- [ ] Audit logging is complete
- [ ] Compliance requirements met

**Operational Review**:
- [ ] Deployment approach is feasible
- [ ] Monitoring/observability is sufficient
- [ ] Disaster recovery plan is adequate
- [ ] Infrastructure costs are acceptable

**Data Review**:
- [ ] Data model supports all requirements
- [ ] Relationships are correct
- [ ] Indexes are appropriate
- [ ] Migration strategy is defined

## Feedback Format

[Provide structured feedback form - similar to requirements review]
```

#### 7.2 Conduct Review

- Send review package to all reviewers
- Schedule review meeting
- Walk through architecture
- Answer questions
- Document feedback

#### 7.3 Update Architecture

```markdown
## Architecture Review - Feedback Summary

### Feedback Received

**From Technical Lead**:
1. Concern: Database single point of failure
   - **Action**: Add read replicas, document failover procedure
   - **Status**: Addressed in architecture.md v1.1

2. Suggestion: Consider GraphQL instead of REST for mobile clients
   - **Action**: Create ADR-008 evaluating GraphQL
   - **Decision**: Stick with REST for MVP, GraphQL in Phase 2
   - **Status**: Documented

**From Security Architect**:
1. Issue: Missing rate limiting on auth endpoints
   - **Action**: Add rate limiting section to security architecture
   - **Status**: Addressed

2. Concern: Insufficient PII protection
   - **Action**: Add column-level encryption for sensitive fields
   - **Status**: Updated data model

**From DBA**:
1. Suggestion: Add database partitioning strategy
   - **Action**: Document partitioning for Orders table
   - **Status**: Added to data model

**From DevOps Lead**:
1. Concern: Deployment rollback procedure unclear
   - **Action**: Document rollback steps in deployment architecture
   - **Status**: Addressed

### Changes Made

- architecture.md: v1.0 → v1.1 (database HA, rollback procedure)
- constitution.md: v1.0 → v1.1 (rate limiting NFR)
- data-model.md: v1.0 → v1.1 (partitioning, encryption)
- ADR-008: GraphQL evaluation (stick with REST)
```

---

## Step 8: Comprehensive Validation (Validator Agent)

### Objective
Comprehensive validation of all Phase 1 artifacts for completeness, consistency, and traceability.

### Agent: Validator Agent
Load: `.primitives/agents/validator-agent.instructions.md`

### Time Required
4-6 hours

### Context to Provide Agent

```markdown
## Context for Validator Agent

You are performing comprehensive Phase 1 validation for [Project Name].

**Your Mission**: Verify that all Phase 1 artifacts are complete, consistent, 
traceable to Phase 0, and ready for Phase 2 (Implementation).

**Artifacts to Validate**:
- constitution.md
- spec.md (from requirements workflow)
- prd.md (from requirements workflow)
- architecture.md
- data-model.md
- api-spec.json

**Validation Dimensions**:
1. **Completeness**: All required artifacts present and complete
2. **Consistency**: No contradictions within or between artifacts
3. **Traceability**: Everything traces to Phase 0
4. **Quality**: Meets all quality standards
5. **Readiness**: Ready for implementation

**Your Output**: validation-report.md

**Quality Standards**: Use phase-1-completion.checklist.md as validation criteria

Begin comprehensive validation.
```

### Actions

#### 8.1 Run Validation Checks

(Validator Agent performs comprehensive checks using its instructions)

#### 8.2 Generate Validation Report

```markdown
# Phase 1 Validation Report - [Project Name]

**Validation Date**: [YYYY-MM-DD]
**Validator**: [Name/Agent]
**Phase 1 Session**: [NNN-project-name]

---

## Executive Summary

**Overall Status**: [PASS / PASS WITH CONDITIONS / FAIL]

**Summary**:
[2-3 paragraphs summarizing validation results]

**Critical Issues**: [N]
**Important Issues**: [N]
**Minor Issues**: [N]

**Recommendation**: [Ready for Phase 2 / Needs rework / Not ready]

---

## Completeness Validation

### Artifact Presence
- [✓] constitution.md present and complete
- [✓] spec.md present and complete
- [✓] prd.md present and complete
- [✓] architecture.md present and complete
- [✓] data-model.md present and complete
- [✓] api-spec.json present and complete

### Content Completeness
[Details from validator agent's analysis]

**Score**: [X/Y] criteria met

---

## Consistency Validation

### Internal Consistency
[Check each document for contradictions]

### Cross-Document Consistency
[Check consistency between documents]

**Issues Found**: [List]

**Score**: [X/Y] criteria met

---

## Traceability Validation

### Phase 0 → Phase 1 Traceability
- [ ] All Phase 0 problems addressed
- [ ] All Phase 0 constraints respected
- [ ] All Phase 0 success criteria supported

### Requirements → Architecture Traceability
- [ ] All requirements architecturally feasible
- [ ] All NFRs addressed in architecture
- [ ] All requirements have data model support
- [ ] All requirements have API support

**Score**: [X/Y] criteria met

---

## Quality Validation

### Technical Quality
[Assess architecture decisions, design patterns, etc.]

### Documentation Quality
[Assess clarity, completeness, professionalism]

**Score**: [X/Y] criteria met

---

## Issues & Recommendations

### Critical Issues (Must Fix)
[List with severity, impact, recommendation]

### Important Issues (Should Fix)
[List]

### Minor Issues (Nice to Fix)
[List]

---

## Conclusion

**Phase 1 Status**: [Ready / Needs Rework / Not Ready]

**Next Steps**:
[What needs to happen before Phase 2]
```

**Save as**: `validation/validation-report.md`

---

## Step 9: Final Approval & Handoff

### Objective
Obtain stakeholder approvals and package artifacts for Phase 2.

### Actions

#### 9.1 Stakeholder Sign-offs

(Use phase-1-completion.checklist.md for formal sign-offs)

#### 9.2 Package for Phase 2

```bash
# Create Phase 2 handoff package
mkdir -p phase-2-handoff/

# Copy all finalized artifacts
cp artifacts/*.md phase-2-handoff/
cp artifacts/*.json phase-2-handoff/

# Copy diagrams
cp -r architecture/diagrams/ phase-2-handoff/diagrams/

# Copy ADRs
cp architecture/adrs/*.md phase-2-handoff/adrs/

# Create handoff document
```

```markdown
# Phase 2 (Implementation) Handoff Package

**From**: Phase 1 Team (Requirements & Architecture)
**To**: Phase 2 Team (Implementation)
**Date**: [YYYY-MM-DD]

## Artifacts Ready for Implementation

**Core Documents**:
- ✅ constitution.md - Technical principles, NFRs, constraints (APPROVED)
- ✅ spec.md - Functional requirements (APPROVED)
- ✅ prd.md - Product vision, MVP scope (APPROVED)
- ✅ architecture.md - System design (APPROVED)
- ✅ data-model.md - Database schema (APPROVED)
- ✅ api-spec.json - API contracts (APPROVED)

**Supporting Materials**:
- Architecture Decision Records (ADRs/)
- Diagrams (diagrams/)
- Validation Report

## Implementation Guidance

**Technology Stack**: [Summary]

**MVP Scope**: [Brief description]

**Critical NFRs**:
- Performance: [Target]
- Security: [Requirements]
- Reliability: [Uptime target]

**Key Constraints**:
1. [Constraint 1]
2. [Constraint 2]
3. [Constraint 3]

**Architecture Highlights**:
- Style: [Monolith/Microservices/etc.]
- Database: [Technology]
- Authentication: [Method]
- Deployment: [Approach]

## Development Priorities

1. [Priority 1 - e.g., Core authentication]
2. [Priority 2 - e.g., Key user workflows]
3. [Priority 3 - e.g., Admin features]

## Success Criteria

Implementation will be successful when:
- All Must-Have requirements implemented
- All NFRs met (performance, security, etc.)
- All acceptance criteria passing
- System deployed to production

## Contact Information

- Architecture questions: [Name, email]
- Requirements questions: [Name, email]
- Product questions: [Name, email]

**Ready to build!** 🚀
```

---

## Workflow Completion Checklist

### Constitution Complete
- [ ] Project principles defined (3-7 principles)
- [ ] All NFRs documented with measurable criteria
- [ ] All constraints documented with rationale
- [ ] Quality attributes prioritized
- [ ] Trade-offs documented
- [ ] Constitution traces to Phase 0
- [ ] Stakeholders approved constitution

### Architecture Design Complete
- [ ] Architecture style selected and justified (ADR)
- [ ] System context defined (actors, external systems)
- [ ] Components identified with clear responsibilities
- [ ] Component interactions documented
- [ ] Technology stack fully specified
- [ ] ADRs created for key decisions (min 5)
- [ ] Security architecture defined
- [ ] Deployment architecture documented
- [ ] Integration patterns specified
- [ ] Monitoring/observability strategy defined

### Data Model Complete
- [ ] All entities identified from requirements
- [ ] Entity attributes defined with data types
- [ ] Relationships defined (cardinality, cascade)
- [ ] Constraints documented (PK, FK, unique, check)
- [ ] Indexes identified for performance
- [ ] ERD created and clear
- [ ] Database schema documented (C# entities if applicable)
- [ ] Data model supports all requirements

### API Design Complete
- [ ] API design principles established
- [ ] All requirements mapped to endpoints
- [ ] API specification created (OpenAPI 3.0)
- [ ] Request/response formats defined
- [ ] Error handling specified
- [ ] Authentication/authorization per endpoint
- [ ] API versioning strategy defined
- [ ] API documentation complete

### Validation Complete
- [ ] All Phase 1 artifacts validated
- [ ] Completeness verified
- [ ] Consistency verified (internal and cross-document)
- [ ] Traceability verified (Phase 0 → Phase 1)
- [ ] Quality standards met
- [ ] Validation report created
- [ ] All critical issues resolved
- [ ] Phase 1 ready for Phase 2

### Approvals & Handoff
- [ ] All stakeholders signed off
- [ ] Phase 1 completion checklist complete
- [ ] Handoff package prepared
- [ ] Phase 2 team briefed
- [ ] Architecture ready for implementation

---

## Common Pitfalls & How to Avoid

### Pitfall: Over-Engineering
❌ Adding complexity not justified by requirements
✅ YAGNI principle - build what's needed for MVP

### Pitfall: Ignoring NFRs
❌ Focusing only on functional requirements
✅ Design specifically to address each NFR with measurable targets

### Pitfall: Technology-Driven Design
❌ "Let's use [trendy technology] because it's cool"
✅ Choose technologies based on requirements and constraints

### Pitfall: Missing ADRs
❌ Making decisions without documentation
✅ Document every significant decision with context and alternatives

### Pitfall: Weak Traceability
❌ Architecture doesn't clearly support requirements
✅ Explicit mapping: Requirement → Component → API → Data Model

### Pitfall: Ignoring Phase 0 Constraints
❌ Designing ideal solution without respecting constraints
✅ Constraints are non-negotiable (unless renegotiated)

### Pitfall: Insufficient Detail
❌ High-level diagrams without implementation guidance
✅ Enough detail that developers can start coding

---

## Success Criteria for Architecture Design Workflow

**Ready to proceed to Phase 2 (Implementation) when**:
✅ All Phase 1 artifacts complete and approved
✅ Every requirement has architectural support
✅ Every NFR has specific design approach
✅ All constraints respected in design
✅ Technology stack fully specified
✅ Data model supports all requirements
✅ API contracts fully defined
✅ No critical validation issues
✅ All stakeholders approved
✅ Development team has clarity to begin coding

---

**Remember**: Good architecture enables good implementation. The time invested in Phase 1 prevents costly rework in Phase 2. A clear, complete architecture lets developers focus on building, not figuring out what to build.

**Next Phase**: Phase 2 (Implementation) - Turn designs into working software!
