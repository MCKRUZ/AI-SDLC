# Phase 1 Completion Checklist

**Project Name**: [Project name]  
**Review Date**: [YYYY-MM-DD]  
**Reviewer(s)**: [Names]  
**Session ID**: [Session folder name]

---

## Purpose
This checklist ensures Phase 1 (Requirements & Architecture) is complete before transitioning to Phase 2 (Implementation). Each criterion must be satisfied for successful handoff to the development team.

**Completion Standard**: All items in Critical Criteria must be checked. 80%+ of Important Criteria should be checked.

---

## Critical Criteria (All Required)

### Constitution Completeness

- [ ] **Constitution document exists** and is accessible
- [ ] **Project principles clearly defined** (3-7 core principles)
- [ ] **Non-functional requirements documented** with measurable criteria:
  - [ ] Performance requirements (response time, throughput, capacity)
  - [ ] Security requirements (authentication, authorization, data protection)
  - [ ] Reliability requirements (uptime, fault tolerance, recovery)
  - [ ] Scalability requirements (growth projections, load handling)
  - [ ] Maintainability requirements (code quality, documentation standards)
- [ ] **Technical constraints documented** and validated
  - [ ] Technology stack constraints (with rationale)
  - [ ] Infrastructure constraints (with rationale)
  - [ ] Regulatory/compliance constraints (with requirements)
- [ ] **Quality attributes prioritized** using explicit framework (e.g., Quality Attribute Workshop)
- [ ] **Trade-offs documented** between conflicting attributes
- [ ] **Constitution traces back to Phase 0** problem statement and constraints
  - Evidence: [Link to traceability matrix]

### Requirements Specification

- [ ] **Requirements specification document (spec.md) exists**
- [ ] **All functional requirements documented** using consistent format
- [ ] **Requirements categorized** by functional area or module
- [ ] **Each requirement has unique identifier** (e.g., REQ-001)
- [ ] **Requirements written clearly** - no ambiguous language
  - [ ] Uses "shall/must" for mandatory, "should" for recommended
  - [ ] Specifies actor, action, and outcome
  - [ ] Free of implementation details
- [ ] **User stories documented** for all user-facing features:
  - [ ] Format: As a [role], I want [capability], so that [benefit]
  - [ ] Acceptance criteria defined for each story
  - [ ] Story points or complexity estimated
- [ ] **Acceptance criteria are testable** and objective
- [ ] **Business rules documented** with logic and conditions
- [ ] **Edge cases and error conditions** identified
- [ ] **All requirements trace to Phase 0** stakeholder needs
  - Evidence: [Link to requirements traceability matrix]

### Product Requirements Document (PRD)

- [ ] **PRD document exists** and is current
- [ ] **Product vision clearly articulated** (1-2 paragraphs)
- [ ] **Target users/personas defined** with demographics and goals
  - [ ] Primary persona documented
  - [ ] Secondary personas documented (if applicable)
- [ ] **User journeys mapped** for key workflows (min 3 journeys)
- [ ] **Feature list documented** and prioritized
- [ ] **MVP scope explicitly defined** - what's in/out
- [ ] **Feature prioritization criteria documented** (RICE, MoSCoW, or equivalent)
- [ ] **Success metrics defined** with baseline and targets:
  - Metric 1: [_______________] - Baseline: [____] Target: [____]
  - Metric 2: [_______________] - Baseline: [____] Target: [____]
  - Metric 3: [_______________] - Baseline: [____] Target: [____]
- [ ] **Product roadmap created** with phases and timeline
- [ ] **Go-to-market strategy outlined** (if applicable)
- [ ] **PRD reviewed and approved** by product stakeholders
  - Evidence: [Link to approval]

### Architecture Design

- [ ] **Architecture document exists** (architecture.md)
- [ ] **System context diagram present** - shows system boundaries
- [ ] **Architecture style/pattern documented** (monolith, microservices, event-driven, etc.)
- [ ] **Component/module breakdown provided** with clear responsibilities
- [ ] **Component interaction patterns documented** (sync/async, protocols)
- [ ] **Technology stack fully specified**:
  - [ ] Frontend technologies (frameworks, libraries, tools)
  - [ ] Backend technologies (languages, frameworks, runtime)
  - [ ] Database technologies (RDBMS, NoSQL, caching)
  - [ ] Infrastructure technologies (cloud, containers, orchestration)
  - [ ] Third-party services (auth, payments, monitoring, etc.)
- [ ] **Architecture decisions recorded** (ADRs) with context and rationale
- [ ] **Security architecture defined**:
  - [ ] Authentication mechanism specified
  - [ ] Authorization model documented
  - [ ] Data encryption approach (at rest, in transit)
  - [ ] Security controls documented
- [ ] **Performance architecture specified**:
  - [ ] Caching strategy documented
  - [ ] Load balancing approach
  - [ ] Performance bottlenecks identified with mitigation
- [ ] **Deployment architecture documented**:
  - [ ] Environment strategy (dev, staging, production)
  - [ ] CI/CD pipeline design
  - [ ] Deployment topology
- [ ] **Architecture validates against NFRs** in constitution
  - Evidence: [Link to validation matrix]

### Data Model

- [ ] **Data model document exists** (data-model.md)
- [ ] **All entities/tables documented** with descriptions
- [ ] **Entity relationships mapped** (ER diagram or equivalent)
- [ ] **Attributes/columns documented** with data types
- [ ] **Primary keys and foreign keys defined**
- [ ] **Indexes identified** for performance
- [ ] **Constraints documented** (unique, not null, check constraints)
- [ ] **Data validation rules specified**
- [ ] **Data retention policies documented**
- [ ] **Data privacy requirements addressed** (PII, sensitive data)
- [ ] **Migration strategy documented** (if applicable)
  - [ ] Existing data migration plan
  - [ ] Data transformation logic
  - [ ] Rollback procedures
- [ ] **Data model supports all requirements** in spec
  - Evidence: [Link to coverage matrix]

### API Specification

- [ ] **API specification exists** (api-spec.json or equivalent)
- [ ] **API follows standard format** (OpenAPI/Swagger, GraphQL schema, gRPC proto)
- [ ] **All endpoints documented** with:
  - [ ] HTTP method (GET, POST, PUT, DELETE)
  - [ ] URL pattern/path
  - [ ] Request parameters (path, query, body)
  - [ ] Request schemas with validation rules
  - [ ] Response schemas for success cases
  - [ ] Error response schemas
  - [ ] Status codes (200, 400, 401, 404, 500, etc.)
- [ ] **Authentication/authorization documented** per endpoint
- [ ] **Rate limiting strategy documented**
- [ ] **API versioning strategy documented**
- [ ] **Error handling patterns documented**
- [ ] **Pagination strategy documented** (for list endpoints)
- [ ] **API supports all user stories** in spec
  - Evidence: [Link to API-to-story mapping]

---

## Important Criteria (80%+ Required)

### Requirements Quality

- [ ] **Requirements completeness verified** - no major gaps
- [ ] **Requirements are atomic** - each represents single concern
- [ ] **Requirements are implementation-independent**
- [ ] **Requirements avoid design decisions**
- [ ] **Requirements prioritized** by business value and risk
- [ ] **Dependencies between requirements identified**
- [ ] **Assumptions documented** for each requirement area
- [ ] **Clarifications document exists** addressing ambiguities from Phase 0
- [ ] **Requirements reviewed** by technical and business stakeholders

**Score**: [__]/9 important requirements criteria met

### Product Definition Quality

- [ ] **User personas based on research** (Phase 0 interviews)
- [ ] **User journeys show complete workflows** (happy path + alternatives)
- [ ] **Feature prioritization justified** with data or framework scores
- [ ] **MVP scope is achievable** within constraints
- [ ] **Success metrics are SMART** (Specific, Measurable, Achievable, Relevant, Time-bound)
- [ ] **Success metrics align with Phase 0** business impact goals
- [ ] **Product roadmap is realistic** given team capacity
- [ ] **Competitive analysis included** (if applicable)
- [ ] **Market/user validation planned** (beta, early access, etc.)

**Score**: [__]/9 important product criteria met

### Architecture Quality

- [ ] **Architecture style appropriate** for scale and complexity
- [ ] **Architecture supports NFRs** with specific design choices
- [ ] **Architecture allows for evolution** - not over-engineered or brittle
- [ ] **Architecture addresses known scalability bottlenecks**
- [ ] **Architecture addresses known security threats**
- [ ] **Single points of failure identified** and mitigated
- [ ] **Disaster recovery strategy documented**
- [ ] **Monitoring and observability strategy documented**:
  - [ ] Logging approach
  - [ ] Metrics collection
  - [ ] Distributed tracing (if applicable)
  - [ ] Alerting strategy
- [ ] **Architecture diagrams are clear** and use consistent notation (C4, UML, etc.)
- [ ] **External dependencies documented** with fallback strategies
- [ ] **Technology choices justified** with rationale (not just "we like X")

**Score**: [__]/11 important architecture criteria met

### Data Model Quality

- [ ] **Data model is normalized** (3NF or justified denormalization)
- [ ] **Denormalization justified** for performance with tradeoffs documented
- [ ] **Data model avoids redundancy** (no duplicate storage of truth)
- [ ] **Naming conventions consistent** across all entities
- [ ] **Data types optimized** for storage and performance
- [ ] **Referential integrity ensured** via constraints
- [ ] **Data archival strategy documented** (if needed)
- [ ] **Audit trail/history tracked** for critical entities (if needed)
- [ ] **Data model reviewed** for privacy compliance (GDPR, CCPA, etc.)

**Score**: [__]/9 important data model criteria met

### API Quality

- [ ] **API design follows REST principles** (or appropriate pattern for GraphQL/gRPC)
- [ ] **API is consistent** - similar endpoints follow similar patterns
- [ ] **Request/response schemas validated** with constraints
- [ ] **API provides clear error messages** with codes and descriptions
- [ ] **API supports filtering, sorting, searching** where appropriate
- [ ] **API supports bulk operations** where efficiency matters
- [ ] **API includes health check endpoint**
- [ ] **API documentation generated** from spec (Swagger UI, GraphQL playground, etc.)
- [ ] **Backward compatibility strategy** documented for breaking changes
- [ ] **API security reviewed** (OWASP Top 10 considerations)

**Score**: [__]/10 important API criteria met

### Integration & Dependencies

- [ ] **All external integrations identified**
- [ ] **Integration patterns documented** (webhook, polling, API, messaging)
- [ ] **Third-party API contracts reviewed** and understood
- [ ] **Authentication with external services documented**
- [ ] **Rate limits of external services documented** and respected
- [ ] **Failure modes of external services addressed**
- [ ] **Fallback/offline modes designed** where critical
- [ ] **Data synchronization strategy** documented for integrations

**Score**: [__]/8 important integration criteria met

---

## Documentation Quality

### Completeness

- [ ] **All required artifacts present**:
  - [ ] Constitution (constitution.md)
  - [ ] Requirements Specification (spec.md)
  - [ ] Product Requirements Document (prd.md)
  - [ ] Architecture Document (architecture.md)
  - [ ] Data Model (data-model.md)
  - [ ] API Specification (api-spec.json or equivalent)
- [ ] **All diagrams present and labeled**:
  - [ ] System context diagram
  - [ ] Component/architecture diagram
  - [ ] Data model/ER diagram
  - [ ] Deployment diagram
  - [ ] Key sequence/interaction diagrams
- [ ] **No placeholder content** or "TBD" in critical sections
- [ ] **All technical terms defined** in glossary or inline
- [ ] **Code examples provided** for complex algorithms or logic (if needed)
- [ ] **Decision log/ADRs documented** for significant architecture choices

**Score**: [__]/6 documentation completeness criteria met

### Traceability

- [ ] **Requirements trace to Phase 0** needs and interviews
  - Traceability matrix: [Link: _______________]
- [ ] **Features in PRD trace to requirements** in spec
  - Mapping document: [Link: _______________]
- [ ] **Architecture decisions trace to NFRs** in constitution
  - Validation matrix: [Link: _______________]
- [ ] **Data model entities trace to requirements**
  - Coverage matrix: [Link: _______________]
- [ ] **API endpoints trace to user stories**
  - API-to-story mapping: [Link: _______________]
- [ ] **Every Phase 0 constraint addressed** in Phase 1 design
  - Constraint coverage: [Link: _______________]
- [ ] **Every Phase 0 risk mitigated** in Phase 1 design
  - Risk mitigation matrix: [Link: _______________]

**Score**: [__]/7 traceability criteria met

### Consistency

- [ ] **No contradictions** between documents
- [ ] **Consistent terminology** used across all artifacts
- [ ] **Consistent naming conventions** (code style, database naming, API naming)
- [ ] **Consistent diagramming notation** across all diagrams
- [ ] **Consistent data formats** (date formats, currency, units)
- [ ] **Version numbers consistent** across all documents
- [ ] **Cross-references valid** - all internal links work

**Score**: [__]/7 consistency criteria met

### Clarity & Readability

- [ ] **Technical writing is clear** - no ambiguous or vague statements
- [ ] **Diagrams are readable** - not cluttered, proper labeling
- [ ] **Tables formatted properly** with headers and alignment
- [ ] **Code examples follow conventions** (if C# preferred, use C#)
- [ ] **Documents follow templates** or standard formats
- [ ] **Professional quality** - grammar, spelling, formatting
- [ ] **Documents are accessible** - proper heading hierarchy, alt text for images

**Score**: [__]/7 clarity criteria met

---

## Validation & Quality Gates

### Cross-Artifact Validation

- [ ] **Constitution validated against Phase 0**:
  - [ ] All Phase 0 NFRs addressed
  - [ ] All Phase 0 constraints respected
  - [ ] Quality attribute priorities align with Phase 0 business goals
- [ ] **Spec validated against Constitution**:
  - [ ] All requirements comply with technical constraints
  - [ ] No requirements violate defined principles
  - [ ] Requirements support defined quality attributes
- [ ] **PRD validated against Spec**:
  - [ ] All features map to requirements
  - [ ] MVP scope is subset of total requirements
  - [ ] Success metrics can verify requirement satisfaction
- [ ] **Architecture validated against Constitution**:
  - [ ] Design supports all NFRs with specific mechanisms
  - [ ] Architecture respects all constraints
  - [ ] Trade-offs documented where NFRs conflict
- [ ] **Data Model validated against Spec**:
  - [ ] All entities required by requirements are present
  - [ ] Data model supports all business rules
  - [ ] No orphaned entities (not used by any requirement)
- [ ] **API validated against Spec**:
  - [ ] All user stories can be fulfilled by API
  - [ ] API granularity appropriate (not too coarse or fine)
  - [ ] API matches architecture component boundaries

**Score**: [__]/6 cross-artifact validation criteria met

### Stakeholder Validation

- [ ] **Technical stakeholders reviewed** architecture and data model
  - Reviewers: [Names and dates: _______________]
- [ ] **Business stakeholders reviewed** spec and PRD
  - Reviewers: [Names and dates: _______________]
- [ ] **Security team reviewed** architecture and API spec (if separate team)
  - Reviewer: [Name and date: _______________]
- [ ] **Compliance reviewed** if regulatory requirements apply
  - Reviewer: [Name and date: _______________]
- [ ] **All stakeholder feedback incorporated** or explicitly deferred
  - Outstanding issues: [Link to issues log: _______________]
- [ ] **Stakeholder sign-off obtained** on final artifacts
  - Evidence: [Link to approvals: _______________]

**Score**: [__]/6 stakeholder validation criteria met

### Readiness for Phase 2

- [ ] **Development environment can be set up** from architecture doc
- [ ] **Database schema can be generated** from data model
- [ ] **API implementation can begin** from API spec
- [ ] **Test cases can be written** from acceptance criteria
- [ ] **CI/CD pipeline can be configured** from deployment architecture
- [ ] **No open questions** blocking implementation start
- [ ] **All high-priority risks mitigated** or have plans
- [ ] **Development team has reviewed** and understands artifacts
  - Team review: [Date: _______________]
- [ ] **Development team estimates created** for MVP scope
  - Estimates: [Link: _______________]
- [ ] **Resources committed** for Phase 2:
  - Team: [Committed: Yes/No/Partial - Details: _______________]
  - Infrastructure: [Provisioned: Yes/No/Planned - Details: _______________]
  - Budget: [Approved: Yes/No/Partial - Details: _______________]
  - Timeline: [Start date: ______ MVP target: ______]

**Score**: [__]/11 Phase 2 readiness criteria met

---

## Overall Assessment

### Scoring Summary

**Critical Criteria** (Must be 100%):
- Constitution Completeness: [__]/8
- Requirements Specification: [__]/11
- Product Requirements Document: [__]/10
- Architecture Design: [__]/11
- Data Model: [__]/7
- API Specification: [__]/6
- **Total Critical**: [__]/53 (Must be 53/53)

**Important Criteria** (Must be 80%+):
- Requirements Quality: [__]/9
- Product Definition Quality: [__]/9
- Architecture Quality: [__]/11
- Data Model Quality: [__]/9
- API Quality: [__]/10
- Integration & Dependencies: [__]/8
- **Total Important**: [__]/56 (Must be 45+/56)

**Documentation Quality**:
- Completeness: [__]/6
- Traceability: [__]/7
- Consistency: [__]/7
- Clarity & Readability: [__]/7
- **Total Documentation**: [__]/27

**Validation & Quality Gates**:
- Cross-Artifact Validation: [__]/6
- Stakeholder Validation: [__]/6
- Readiness for Phase 2: [__]/11
- **Total Validation**: [__]/23

### Final Determination

**Phase 1 Status**: [Choose one]

- [ ] ✅ **COMPLETE** - Ready to proceed to Phase 2
  - All critical criteria met (53/53)
  - 80%+ of important criteria met (45+/56)
  - Documentation is complete and traceable
  - All artifacts validated and consistent
  - Stakeholders have signed off
  - Development team is ready to begin
  
- [ ] ⚠️ **CONDITIONALLY COMPLETE** - Can proceed with managed risk
  - Missing criteria: [List specific items]
  - Percentage complete: Critical [__]/53, Important [__]/56
  - Conditions for proceeding: [List conditions that must be met]
  - Risk assessment: [Brief description of risks from gaps]
  - Mitigation plan: [How gaps will be addressed during Phase 2]
  - Sign-off: [Who approved conditional start and why]
  
- [ ] ❌ **NOT COMPLETE** - Cannot proceed to Phase 2 yet
  - Critical gaps: [List all critical criteria not met]
  - Important gaps: [List important criteria preventing start]
  - Impact: [Why these gaps block implementation]
  - Required actions: [Specific work needed]
  - Responsible parties: [Who will address gaps]
  - Estimated time to complete: [X days/weeks]
  - Re-review date: [Date for next checklist assessment]

---

## Gaps & Action Items

### Critical Gaps Identified
[List any critical criteria not met - these MUST be addressed before Phase 2]

| Gap ID | Gap Description | Impact if Not Fixed | Owner | Action Plan | Due Date | Status |
|--------|-----------------|---------------------|-------|-------------|----------|--------|
| CG-001 | [Gap description] | [Impact] | [Name] | [Action] | [Date] | [Open/In Progress/Blocked] |
| CG-002 | [Gap description] | [Impact] | [Name] | [Action] | [Date] | [Open/In Progress/Blocked] |

### Important Gaps Identified
[List important criteria not met - should be addressed but may not block start]

| Gap ID | Gap Description | Priority | Impact | Owner | Action Plan | Due Date | Status |
|--------|-----------------|----------|--------|-------|-------------|----------|--------|
| IG-001 | [Gap description] | [H/M/L] | [Impact] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |
| IG-002 | [Gap description] | [H/M/L] | [Impact] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |

### Documentation Gaps
[List documentation quality issues]

| Gap ID | Gap Description | Document | Owner | Action Plan | Due Date | Status |
|--------|-----------------|----------|-------|-------------|----------|--------|
| DG-001 | [Gap description] | [Document name] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |
| DG-002 | [Gap description] | [Document name] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |

### Validation Gaps
[List cross-artifact inconsistencies or validation failures]

| Gap ID | Gap Description | Artifacts Affected | Owner | Action Plan | Due Date | Status |
|--------|-----------------|-------------------|-------|-------------|----------|--------|
| VG-001 | [Gap description] | [Artifact 1, Artifact 2] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |
| VG-002 | [Gap description] | [Artifact 1, Artifact 2] | [Name] | [Action] | [Date] | [Open/In Progress/Resolved] |

---

## Reviewer Comments

### Strengths of This Requirements & Architecture Phase
[What went well? What was particularly thorough, clear, or well-designed?]

1. [Strength 1]
2. [Strength 2]
3. [Strength 3]
4. [Strength 4]
5. [Strength 5]

### Areas for Improvement
[What could have been done better? What was rushed, incomplete, or unclear?]

1. [Area 1]
2. [Area 2]
3. [Area 3]
4. [Area 4]
5. [Area 5]

### Specific Concerns or Risks
[Any technical debt being accepted? Any risky design choices? Any dependencies that worry you?]

1. [Concern/Risk 1]
2. [Concern/Risk 2]
3. [Concern/Risk 3]

### Recommendations for Phase 2
[What should the implementation team be aware of? Any warnings, suggestions, or things to watch?]

1. [Recommendation 1]
2. [Recommendation 2]
3. [Recommendation 3]
4. [Recommendation 4]
5. [Recommendation 5]

---

## Sign-off

### Phase 1 Team Sign-off
- [ ] Requirements Analyst: [Name] - Date: [___________] - Signature: [___________]
- [ ] Product Manager: [Name] - Date: [___________] - Signature: [___________]
- [ ] Solutions Architect: [Name] - Date: [___________] - Signature: [___________]
- [ ] Validator: [Name] - Date: [___________] - Signature: [___________]

### Technical Review Sign-off
- [ ] Technical Lead/Architect: [Name] - Date: [___________] - Signature: [___________]
- [ ] Database Lead: [Name] - Date: [___________] - Signature: [___________]
- [ ] API Lead: [Name] - Date: [___________] - Signature: [___________]
- [ ] Security Lead: [Name] - Date: [___________] - Signature: [___________]

### Business Stakeholder Sign-off
- [ ] Project Sponsor: [Name] - Date: [___________] - Signature: [___________]
- [ ] Product Owner: [Name] - Date: [___________] - Signature: [___________]
- [ ] Business Analyst: [Name] - Date: [___________] - Signature: [___________]

### Approval for Phase 2 Transition
- [ ] **Approved to proceed to Phase 2 (Implementation)**
  - Approver: [Name, Title]
  - Date: [___________]
  - Signature: [___________]
  - Conditions: [Any conditions attached to approval]
  
- [ ] **Conditional approval** (conditions documented in gaps section above)
  - Approver: [Name, Title]
  - Date: [___________]
  - Signature: [___________]
  - Conditions: [Summary of conditions]
  - Re-review required: [Yes/No] - Date: [___________]
  
- [ ] **Not approved** - Phase 1 must be completed before Phase 2 start
  - Approver: [Name, Title]
  - Date: [___________]
  - Signature: [___________]
  - Primary reasons: [Brief explanation]
  - Expected re-review date: [___________]

---

## Audit Trail

### Document Version History
| Version | Date | Author | Changes | Reviewers |
|---------|------|--------|---------|-----------|
| 0.1 | [Date] | [Name] | Initial draft | [Names] |
| 0.2 | [Date] | [Name] | Incorporated feedback | [Names] |
| 1.0 | [Date] | [Name] | Final version | [Names] |

### Review History
| Review Date | Reviewer(s) | Status | Comments |
|-------------|-------------|--------|----------|
| [Date] | [Names] | [Draft/In Review/Approved] | [Brief summary] |
| [Date] | [Names] | [Draft/In Review/Approved] | [Brief summary] |

---

## Notes

[Additional comments, observations, or context about this phase completion review]

### Lessons Learned for Future Projects
[What would we do differently in Phase 1 next time?]

1. [Lesson 1]
2. [Lesson 2]
3. [Lesson 3]

### Dependencies for Phase 2 Success
[What must be in place beyond this documentation for Phase 2 to succeed?]

1. [Dependency 1]
2. [Dependency 2]
3. [Dependency 3]

---

**Remember**: The goal of Phase 1 is to ensure Phase 2 implementation proceeds without needing to revisit requirements, architecture, or design decisions. If you're uncertain about any criteria, or if the implementation team expresses confusion, that's a signal to invest more time in Phase 1 before proceeding.

**Quality over Speed**: It's better to spend extra time in Phase 1 getting the design right than to rush into implementation and discover fundamental issues that require rework.

**Traceability is Key**: Every design decision should trace back to a requirement or constraint. Every requirement should trace back to Phase 0 stakeholder needs. If you can't draw that line, dig deeper.
