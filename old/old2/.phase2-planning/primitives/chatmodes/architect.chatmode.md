# Architect Chatmode

## Purpose
Focused technical architecture and system design sessions using the Architect Agent.

## When to Use This Mode
- Designing system architecture
- Creating data models and schemas
- Designing APIs and integrations
- Planning infrastructure and deployment
- Addressing performance and scalability
- Defining security architecture
- Evaluating technical risks
- Creating architecture documentation

## Session Setup

### Before Starting
Load these artifacts into context:
1. Constitution (./constitution.md) - Quality standards and principles
2. Spec (./spec.md) - All functional and non-functional requirements
3. PRD (./prd.md) - Product priorities and roadmap
4. Organization context (../../.memory/organization.context.md)
5. Technical stack context (../../.memory/technical-stack.context.md)
6. Feasibility report from Phase 0

### Agent Instructions
Load: `architect-agent.instructions.md`

### Session Goal
Define a clear goal for the session:
- "Design high-level system architecture"
- "Create data model for [domain]"
- "Design API for [feature area]"
- "Plan infrastructure for [requirements]"
- "Address performance requirements"
- "Design security architecture"

## Interaction Patterns

### Pattern 1: System Architecture Design Session

**Opening Prompt:**
```
Design the high-level system architecture for this project using 
the Architect Agent instructions.

Based on:
- Requirements from spec.md (especially NFRs)
- Product priorities from prd.md
- Technical constraints from org context
- Constitution standards

Create:
1. Architecture style recommendation (monolith/microservices/modular/etc)
2. Component diagram with responsibilities
3. Communication patterns between components
4. Technology stack selection with rationale
5. Scalability strategy
6. Deployment architecture

Focus on [specific aspect if any, e.g., "scalability to handle 10x growth"]
```

**Architecture Validation:**
```
Validate this architecture against:
- All NFRs from spec.md (performance, security, scalability)
- Constitution quality standards
- Team capabilities from org context
- Budget and timeline constraints

Identify any risks or concerns.
```

**Architecture Refinement:**
```
For [Component X], provide more detail on:
- Internal structure
- Data flow
- Dependencies
- Failure modes and handling
- Scaling approach
```

### Pattern 2: Data Architecture Session

**Opening Prompt:**
```
Design the data architecture based on requirements in spec.md.

Create:
1. Entity Relationship Diagram (ERD)
2. All entities with attributes, types, and constraints
3. Relationships and cardinality
4. Indexes for key access patterns
5. Data volume estimates
6. Database technology selection with rationale
7. Caching strategy
8. Data retention and archival approach

Ensure normalization and scalability for [expected growth].
```

**Specific Entity Design:**
```
For the [Entity Name] entity, detail:
- All attributes with data types and constraints
- Relationships to other entities
- Indexes needed for these access patterns: [list patterns]
- Data validation rules
- Estimated row counts (year 1, year 3)
```

**Database Technology Selection:**
```
Compare [PostgreSQL vs. MongoDB vs. SQL Server] for this use case.
Consider:
- Data model fit (relational vs. document)
- Query patterns from requirements
- Org technical stack preference
- Team expertise
- Scalability requirements
- Cost

Provide recommendation with clear rationale.
```

### Pattern 3: API Design Session

**Opening Prompt:**
```
Design the API architecture for the requirements in spec.md.

Decisions needed:
1. API style (REST/GraphQL/gRPC) - recommend based on use case
2. Versioning strategy
3. Authentication/authorization approach
4. Error handling and response format
5. Rate limiting strategy

Then create OpenAPI 3.0 specification for:
- All endpoints required by functional requirements
- Request/response schemas
- Authentication requirements
- Error responses

Follow RESTful best practices and constitution standards.
```

**Endpoint Design:**
```
Design the API endpoints for [feature area]:

Requirements to support: [FR-001, FR-002, FR-003]

For each endpoint, specify:
- HTTP method and path
- Purpose
- Request parameters/body
- Response format
- Authentication requirements
- Error scenarios
- Performance target (response time)
- Rate limit
```

**API Evolution:**
```
How should we handle versioning and backward compatibility?
Consider:
- MVP will launch with v1
- Phase 2 will add breaking changes
- Need to support legacy clients for X months

Recommend strategy and provide example.
```

### Pattern 4: Security Architecture Session

**Opening Prompt:**
```
Design the security architecture based on security requirements 
in spec.md and constitution.

Address:
1. Authentication and authorization model
2. Data protection (encryption at rest and in transit)
3. Security controls (input validation, CSRF, etc.)
4. Compliance requirements [GDPR/HIPAA/SOC2/etc.]
5. Security monitoring and logging
6. Threat model and mitigations

Reference compliance requirements: [list applicable regulations]
```

**Authentication Design:**
```
Design the authentication system:
- Method: JWT/OAuth2/API Keys/etc (recommend based on use case)
- Token management (expiry, refresh)
- Session handling
- MFA requirements
- Password policies

Ensure it meets constitution security standards.
```

**Data Protection:**
```
For [sensitive data type: PII/PHI/financial], design:
- Encryption at rest (method and key management)
- Encryption in transit (TLS configuration)
- Field-level vs. database-level encryption trade-offs
- Access logging and audit trail
- Data masking for non-production environments
```

### Pattern 5: Infrastructure & Deployment Session

**Opening Prompt:**
```
Design the infrastructure and deployment architecture.

Environment: [Azure/AWS/GCP/On-premise]

Create:
1. Cloud architecture diagram
2. Compute resources (sizing and auto-scaling)
3. Database and cache infrastructure
4. Networking and security groups
5. CI/CD pipeline design
6. Monitoring and observability setup
7. Disaster recovery plan
8. Cost estimates

Target: [Production load expectations from NFRs]
```

**CI/CD Pipeline:**
```
Design the CI/CD pipeline including:
- Build steps and quality gates
- Test automation (unit, integration, E2E)
- Deployment strategy (blue-green/canary/rolling)
- Environment promotion (dev → staging → prod)
- Rollback procedures

Ensure all constitution quality gates are enforced.
```

**Monitoring Strategy:**
```
Design comprehensive monitoring for:
- Application metrics (response time, error rate, throughput)
- Infrastructure metrics (CPU, memory, disk, network)
- Business metrics (from PRD success metrics)
- Logging strategy (what to log, retention)
- Alerting rules (critical vs. warning)
- Dashboard layouts for different audiences

Integrate with: [Org monitoring tools]
```

### Pattern 6: Performance Architecture Session

**Opening Prompt:**
```
Design the performance architecture to meet these NFRs:
[List specific performance requirements from spec.md]

Address:
1. Caching strategy (browser, CDN, application, database)
2. Database optimization (indexes, query patterns, connection pooling)
3. API optimization (pagination, compression, HTTP/2)
4. Asynchronous processing (background jobs, queues)
5. Frontend optimization (code splitting, lazy loading, assets)
6. Performance testing strategy

Target: [95th percentile response time < X ms at Y concurrent users]
```

**Bottleneck Analysis:**
```
Identify potential performance bottlenecks:
1. Database queries for [specific feature]
2. External API calls to [system]
3. Heavy computation for [process]

For each bottleneck, provide:
- Why it's a bottleneck
- Mitigation strategy
- Expected performance improvement
- Implementation complexity
```

### Pattern 7: Integration Architecture Session

**Opening Prompt:**
```
Design integration architecture for external systems:
[List systems from spec.md integration requirements]

For each integration:
1. Integration pattern (REST API/Message queue/Webhook/File/etc.)
2. Data flow (inbound and outbound)
3. Authentication method
4. Error handling and retry logic
5. Circuit breaker configuration
6. Data mapping
7. Testing strategy

Ensure resilience and observability.
```

**Specific Integration:**
```
Design integration with [External System]:

Requirements: [FR-XXX that depends on this]
Data needed: [Inbound and outbound]
Frequency: [Real-time/Batch/Event-driven]

Provide:
- Integration pattern recommendation
- Error handling strategy
- Fallback behavior if system is down
- Data transformation logic
- Monitoring approach
```

### Pattern 8: Technical Risk Assessment Session

**Opening Prompt:**
```
Identify and assess technical risks in the proposed architecture.

Consider:
1. Scalability risks (what breaks at 10x load?)
2. Integration risks (external system dependencies)
3. Performance risks (can we meet NFRs?)
4. Security risks (threat scenarios)
5. Complexity risks (team capability gaps)
6. Timeline risks (unknowns and estimates)

For each risk:
- Probability (High/Medium/Low)
- Impact (High/Medium/Low)
- Mitigation strategy
- Contingency plan
```

**Risk Deep Dive:**
```
For risk: [Specific risk], develop:
1. Detailed risk scenario
2. Triggers (how we'll know it's happening)
3. Proactive mitigation steps
4. Reactive contingency plan
5. Validation approach (spikes, POCs, load tests)
6. Owner and timeline
```

## Best Practices for This Mode

### Do's
- ✅ Ground decisions in requirements (especially NFRs)
- ✅ Research patterns and precedents
- ✅ Consider team capabilities
- ✅ Design for failure and resilience
- ✅ Keep it simple (YAGNI principle)
- ✅ Document architectural decisions with rationale
- ✅ Think about operations and debugging
- ✅ Validate against constitution standards

### Don'ts
- ❌ Don't over-engineer for imagined future needs
- ❌ Don't choose technologies outside org stack without justification
- ❌ Don't ignore NFRs (they're requirements too)
- ❌ Don't design without considering team skills
- ❌ Don't skip monitoring and observability
- ❌ Don't forget about cost implications
- ❌ Don't design in a vacuum (validate with stakeholders)

## Session Outputs

### Primary Artifacts
- **architecture.md** with:
  - System architecture (style, components, patterns)
  - Component responsibilities and interfaces
  - Technology stack with rationale
  - Security architecture
  - Infrastructure and deployment design
  - Integration patterns
  - Performance strategy
  - Monitoring and observability plan
  - Technical risks and mitigations

- **data-model.md** with:
  - Entity Relationship Diagram
  - All entities with complete schemas
  - Indexes and access patterns
  - Database technology selection
  - Caching strategy
  - Data volumes and growth

- **api-spec.json**:
  - OpenAPI 3.0 specification
  - All endpoints with schemas
  - Authentication/authorization
  - Error responses
  - Examples

### Supporting Diagrams
- Architecture diagrams
- Component diagrams
- Sequence diagrams
- Data flow diagrams
- Deployment diagrams
- Network diagrams

## Quality Checks Before Ending Session

- [ ] All NFRs have architectural support
- [ ] All functional requirements can be implemented
- [ ] Technology choices align with org tech stack (or justified)
- [ ] Architecture meets constitution standards
- [ ] Security architecture is comprehensive
- [ ] Performance targets are achievable
- [ ] Monitoring and observability planned
- [ ] CI/CD pipeline includes quality gates
- [ ] Disaster recovery planned
- [ ] Technical risks identified and mitigated
- [ ] Cost estimates provided
- [ ] Team has skills (or training planned)

## Example Session Flow

```
USER: Design the system architecture for our customer support portal.

AGENT (Architect): I'll design the architecture based on your requirements. 
Let me start by analyzing the key architectural drivers from your NFRs:

From spec.md, I see:
- Performance: API responses < 200ms (95th percentile)
- Scalability: Support 800 concurrent users → 2000 in year 2
- Security: PII encryption, RBAC, audit logging
- Availability: 99.9% uptime
- Integration: Zendesk API, Azure Active Directory

From prd.md:
- MVP in 3 months
- Team: 3 developers (.NET experience)
- Budget: $200K

Given these constraints and your org's Azure/.NET stack, I recommend:

**Architecture Style**: Modular Monolith (not microservices)
**Rationale**: 
- Team size and timeline don't support microservices complexity
- Can decompose later if needed
- Easier to maintain initially
- Meets performance requirements

**High-Level Architecture**:
```
Frontend (React 18)
    ↓
API Gateway (Azure Application Gateway)
    ↓
Application Layer (.NET 8 Web API)
├── Customer Module
├── Ticket Module
└── Analytics Module
    ↓
Data Layer
├── SQL Server (Primary)
├── Redis Cache
└── Azure AI Search
    ↓
External Integrations
├── Zendesk API
└── Azure AD
```

**Component: Customer Module**
- Responsibilities: Customer CRUD, profile management, unified view
- Endpoints: GET/POST/PUT /api/customers
- Data: Customer table, relationships to tickets
- Performance: Cache frequently accessed profiles in Redis
...

USER: How do we handle if Zendesk API is down?

AGENT: Excellent question. Let's design resilience into that integration...

[Session continues with detailed integration design]

AGENT: Here's the error handling strategy for Zendesk integration:

1. **Circuit Breaker Pattern**:
   - After 5 consecutive failures, open circuit for 60 seconds
   - During open circuit, return cached data with staleness indicator
   
2. **Retry Logic**:
   - Exponential backoff: 1s, 2s, 4s
   - Max 3 retries
   - Timeout: 5 seconds per request

3. **Fallback**:
   - Use cached ticket data (up to 5 minutes stale)
   - Display "Real-time sync unavailable" message
   - Queue failed updates for retry when service recovers

4. **Monitoring**:
   - Alert when circuit opens
   - Track failure rate, response time
   - Dashboard showing integration health

[Session continues]
```

## Tips for Effective Sessions

### Research First
- Search for similar architecture patterns
- Look up best practices for specific tech
- Review case studies of scale
- Check org's past architectural decisions

### Think in Layers
- Start high-level (system components)
- Then go deep into each component
- Design interfaces between components
- Consider failure modes at each layer

### Validate Continuously
- Check against NFRs frequently
- Verify team can build this
- Confirm budget/timeline fit
- Get feedback on complexity

### Document Decisions
- Capture why, not just what
- Note alternatives considered
- Explain trade-offs
- Record assumptions

## Common Challenges & Solutions

**Challenge**: Requirements don't specify performance targets
**Solution**: Work with PM to define based on Phase 0 success criteria

**Challenge**: Team lacks skills for recommended technology
**Solution**: Either choose alternative or plan training + external help

**Challenge**: Architecture too complex for timeline
**Solution**: Simplify, defer advanced features, or extend timeline

**Challenge**: Multiple NFRs conflict (performance vs. security)
**Solution**: Document trade-offs, get stakeholder decision

**Challenge**: Integration with legacy system is unclear
**Solution**: Schedule technical spike, document risks, plan contingencies

**Challenge**: Cost exceeds budget
**Solution**: Identify cost optimizations, simpler alternatives, or phased approach

## Session Templates

### Architecture Design Template
```
Requirements: [Link to spec.md sections]
Constraints: [Team, budget, timeline, tech stack]

Design:
1. Architecture style (with rationale)
2. Components (with responsibilities)
3. Technology stack (with rationale)
4. Key patterns (caching, async, etc.)
5. Scalability approach
6. Security measures
7. Monitoring strategy

Validate against all NFRs and constitution.
```

### API Design Template
```
Feature area: [Name]
Requirements: [FR-XXX, FR-YYY]

Design endpoints:
1. List resources: GET /api/[resource]
2. Get single: GET /api/[resource]/{id}
3. Create: POST /api/[resource]
4. Update: PUT /api/[resource]/{id}
5. Delete: DELETE /api/[resource]/{id}

Specify schemas, auth, errors, performance targets.
Output as OpenAPI 3.0 spec.
```

### Risk Assessment Template
```
Assess technical risks:

For each risk:
- Description
- Category (scalability/security/integration/etc.)
- Probability (H/M/L)
- Impact (H/M/L)
- Mitigation (proactive)
- Contingency (reactive)
- Validation approach
- Owner
```

---

*Chatmode for: Architect Agent*
*Use for: Technical architecture and system design*
*Session length: 60-120 minutes per focused area*
