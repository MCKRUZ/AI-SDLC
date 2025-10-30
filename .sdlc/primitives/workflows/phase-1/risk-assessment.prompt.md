# Risk Assessment Workflow

## Purpose

This workflow guides you through systematic risk identification, assessment, mitigation planning, and continuous monitoring throughout project execution. The output is a comprehensive risk register with proactive mitigation strategies that minimize project threats and maximize success probability.

**What This Workflow Accomplishes**:
- Identifies all project risks across technical, schedule, resource, and business domains
- Assesses risk probability and impact using structured criteria
- Prioritizes risks by severity for focused mitigation efforts
- Develops concrete mitigation and contingency strategies for high-priority risks
- Creates risk ownership and accountability structure
- Establishes continuous risk monitoring and escalation process
- Updates project plans to incorporate risk responses

**What This Workflow Does NOT Do**:
- Execute risk mitigation (that's Phase 3)
- Make architecture decisions (that's Phase 1)
- Change requirements or priorities (that's PM domain)
- Replace good project management (risk management is complementary)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Constitution** (`constitution.md`) - Constraints and quality standards
- [ ] **Requirements Specification** (`spec.md`) - All functional and non-functional requirements
- [ ] **Architecture Document** (`architecture.md`) - Technical design decisions
- [ ] **Task Breakdown** (`task-breakdown.md`) - All development tasks with estimates
- [ ] **Sprint Plan** (`sprint-plan.md`) - Sprint schedule and resource allocation
- [ ] **Quality Strategy** (`quality-strategy.md`) - Quality standards and testing approach
- [ ] **Team Context** (`team-context.md`) - Team capabilities and constraints
- [ ] **Prior Projects Memory** (`prior-projects.memory.md`) - Lessons learned from past projects
- [ ] **Lessons Learned** (`lessons-learned.memory.md`) - Known risk patterns

### Agent Setup

You should be in **Planning Agent** mode (risk assessment capability) with all context loaded:

```markdown
You are the Planning Agent operating in risk assessment mode, an expert in 
project risk management, risk quantification, and mitigation strategy development.

Context loaded:
- Constitution.md
- Spec.md
- Architecture.md
- Task-breakdown.md
- Sprint-plan.md
- Quality-strategy.md
- Team-context.md
- Prior-projects.memory.md
- Lessons-learned.memory.md

Your mission: Identify, assess, and plan mitigation for all significant project 
risks to minimize threats and maximize project success probability.

Ready to begin risk assessment.
```

---

## Workflow Steps

### Step 1: Risk Identification (2-3 hours)

#### Objective
Systematically identify all potential risks across all project domains.

#### Actions

**1.1 Identify Technical Risks**

Review the architecture, technology stack, and technical complexity to identify risks:

```markdown
## Technical Risks

### Architecture & Design Risks
Review architecture.md for potential risks:

**RISK-T001**: [Risk Title]
- **Description**: [Detailed description of the risk]
- **Trigger**: [What would cause this risk to occur]
- **Impact if Occurs**: [What happens if this risk materializes]
- **Category**: Architecture
- **Source**: Architecture complexity, unproven patterns, design decisions

**Example Architecture Risks**:
- Complex distributed system architecture may be difficult to implement
- Chosen database may not scale to required load
- Microservices architecture increases operational complexity
- Third-party API dependencies may be unreliable
- Technology stack is new to team
- Architecture decisions not yet validated with prototypes
- Performance requirements may be difficult to meet with chosen architecture
- Data consistency across distributed services
- Service orchestration complexity

### Technology Risks

**RISK-T002**: [Technology Stack Maturity Risk]
- **Description**: Team has limited experience with [Technology X]
- **Trigger**: Encountering complex scenarios requiring deep expertise
- **Impact**: Delays, quality issues, rework
- **Category**: Technology
- **Source**: Technology choice, team experience

**Example Technology Risks**:
- Team lacks deep expertise in chosen technology stack
- Framework/library has breaking changes or limited community support
- Development tools may have compatibility issues
- Library dependencies may have security vulnerabilities
- Technology choice may limit scalability
- Integration with existing systems may be complex
- Performance characteristics of technology unknown
- Learning curve steeper than anticipated
- Tooling and debugging difficult

### Integration Risks

**RISK-T003**: [Third-Party Integration Risk]
- **Description**: Integration with [External System X] has unknown complexity
- **Trigger**: API changes, rate limiting, downtime
- **Impact**: Feature delays, runtime failures
- **Category**: Integration
- **Source**: Dependency on external system

**Example Integration Risks**:
- Third-party API may change without notice
- External service may have reliability issues
- Authentication with external systems may be complex
- Data format mismatches between systems
- Network connectivity issues
- Rate limiting or quota restrictions
- External system downtime affects our system
- API documentation incomplete or inaccurate
- Version compatibility issues

### Security Risks

**RISK-T004**: [Security Vulnerability Risk]
- **Description**: Application may have security vulnerabilities
- **Trigger**: Security testing, penetration testing, production exposure
- **Impact**: Data breach, reputation damage, compliance violations
- **Category**: Security
- **Source**: Complexity, inexperience, time pressure

**Example Security Risks**:
- Insufficient input validation
- Inadequate authentication or authorization
- Sensitive data not properly encrypted
- Security vulnerabilities in dependencies
- OWASP Top 10 vulnerabilities
- Inadequate security testing
- Configuration vulnerabilities
- Insufficient logging and monitoring
```

**1.2 Identify Schedule Risks**

```markdown
## Schedule Risks

### Estimation Risks

**RISK-S001**: [Underestimated Complexity Risk]
- **Description**: Tasks may take longer than estimated
- **Trigger**: Implementation reveals hidden complexity
- **Impact**: Sprint delays, milestone slippage
- **Category**: Schedule
- **Source**: Estimates based on incomplete information

**Example Estimation Risks**:
- Technical complexity underestimated
- Integration effort underestimated
- Testing effort underestimated
- Team velocity assumptions too optimistic
- Learning curve not adequately factored
- Rework and bug fixing time underestimated
- Infrastructure setup time underestimated

### Dependency Risks

**RISK-S002**: [Critical Path Dependency Risk]
- **Description**: Task X is on critical path and blocks multiple features
- **Trigger**: Task X delayed or more complex than expected
- **Impact**: Cascading delays to dependent features
- **Category**: Schedule
- **Source**: Task dependencies, limited parallelization

**Example Dependency Risks**:
- Database schema changes block backend development
- Authentication system blocks all secured features
- Infrastructure setup delays all development
- External service integration blocks related features
- UI framework choice delays frontend development
- Design decisions pending delay implementation

### External Dependency Risks

**RISK-S003**: [External Dependency Risk]
- **Description**: Dependency on external team/vendor for deliverable
- **Trigger**: External delays, quality issues, miscommunication
- **Impact**: Project delays, scope changes
- **Category**: Schedule
- **Source**: Dependency on external entities

**Example External Dependency Risks**:
- Vendor deliverables delayed
- Third-party API not ready on time
- External team resource constraints
- Procurement process delays
- Contract negotiations delay start
- External approvals take longer than expected
```

**1.3 Identify Resource Risks**

```markdown
## Resource Risks

### Team Capacity Risks

**RISK-R001**: [Key Person Dependency Risk]
- **Description**: Critical expertise concentrated in one person
- **Trigger**: Person unavailable (vacation, sick, leaves company)
- **Impact**: Work stalled, knowledge loss, delays
- **Category**: Resource
- **Source**: Single point of failure, inadequate knowledge sharing

**Example Key Person Risks**:
- Only one person knows architecture deeply
- Critical system expertise not shared
- Single point of contact for external systems
- Specialized skill only one person has
- Person becomes bottleneck for reviews/decisions

**RISK-R002**: [Team Capacity Risk]
- **Description**: Team capacity may be insufficient
- **Trigger**: Multiple priorities, context switching, unplanned work
- **Impact**: Delays, burnout, quality issues
- **Category**: Resource
- **Source**: Team size, competing demands

**Example Team Capacity Risks**:
- Team members have multiple project responsibilities
- Production support consumes development capacity
- Meetings and ceremonies reduce available time
- Onboarding new team members slows velocity
- Technical debt work competes with features
- Unplanned work (bugs, urgent requests)
- Context switching between projects
- Vacation/holidays reduce capacity
```

**1.4 Identify Business Risks**

```markdown
## Business Risks

### Stakeholder Risks

**RISK-B001**: [Stakeholder Alignment Risk]
- **Description**: Stakeholders may have conflicting priorities or requirements
- **Trigger**: Decision points, priority changes, feedback sessions
- **Impact**: Rework, scope changes, delays
- **Category**: Stakeholders
- **Source**: Multiple stakeholders with different goals

**Example Stakeholder Risks**:
- Stakeholder availability for decisions/reviews
- Conflicting stakeholder priorities
- Stakeholder expectations not aligned with plan
- Late stakeholder feedback requires rework
- Stakeholder changes during project
- Product owner unavailable for clarifications
- Executive sponsor loses interest
- Business priorities shift

### Market Risks

**RISK-B002**: [Market Timing Risk]
- **Description**: Competitor may launch similar product before us
- **Trigger**: Competitive intelligence, market analysis
- **Impact**: Reduced market opportunity, pressure to accelerate
- **Category**: Market
- **Source**: Competitive market

**Example Market Risks**:
- Competitor launches similar product first
- Market conditions change
- Regulatory changes affect requirements
- Business priorities change
- Budget cuts or funding issues
- Organization restructuring
- Economic downturn affects project
```

**1.5 Identify Quality Risks**

```markdown
## Quality Risks

**RISK-Q001**: [Test Coverage Risk]
- **Description**: May not achieve 80% code coverage target
- **Trigger**: Time pressure, complex code, testing challenges
- **Impact**: Lower quality, more bugs in production
- **Category**: Quality
- **Source**: Aggressive timeline, testing expertise

**Example Quality Risks**:
- Inadequate testing due to time constraints
- Test automation difficult for some features
- Performance issues not discovered until late
- Security vulnerabilities not identified in testing
- Accessibility requirements not adequately tested
- Code quality standards not maintained
- Technical debt accumulates
- Insufficient user acceptance testing
- Integration testing incomplete
- Edge cases not adequately covered
```

**1.6 Review Historical Risks**

Review `prior-projects.memory.md` and `lessons-learned.memory.md` for patterns:

```markdown
## Historical Risk Patterns

**Risks from Similar Projects**:
- [Pattern 1]: On 3 previous projects, infrastructure setup took 2x longer than planned
- [Pattern 2]: External API integrations always have undocumented quirks
- [Pattern 3]: First sprint velocity is always 30% lower than planned

**Action**: Incorporate these patterns into current risk assessment
```

**Output**: Comprehensive list of 25-50 identified risks across all categories

---

### Step 2: Risk Assessment (1-2 hours)

#### Objective
Assess each identified risk for probability and impact, then calculate risk severity.

#### Actions

**2.1 Define Assessment Criteria**

```markdown
## Risk Assessment Criteria

### Probability Scale (Likelihood of Occurring)

**Very High (5)**: >75% probability
- Almost certain to occur
- Multiple indicators present
- Has occurred on similar projects
- No clear mitigation path

**High (4)**: 50-75% probability
- Likely to occur
- Several indicators present
- Occurred on some similar projects
- Mitigation path uncertain

**Medium (3)**: 25-50% probability
- May or may not occur
- Some indicators present
- Sometimes occurs on similar projects
- Mitigation path exists but untested

**Low (2)**: 10-25% probability
- Unlikely but possible
- Few indicators present
- Rarely occurs on similar projects
- Clear mitigation path

**Very Low (1)**: <10% probability
- Very unlikely
- No clear indicators
- Almost never occurs
- Easily mitigated

---

### Impact Scale (Consequence if Occurs)

**Critical (5)**: Catastrophic impact
- Project failure or cancellation
- Major data loss or security breach
- >4 weeks delay
- >50% budget overrun
- Severe reputation damage
- Legal/regulatory consequences

**High (4)**: Severe impact
- Major features cut
- 2-4 weeks delay
- 25-50% budget overrun
- Significant rework required
- Customer dissatisfaction
- Team morale severely affected

**Medium (3)**: Moderate impact
- Minor features cut or delayed
- 1-2 weeks delay
- 10-25% budget overrun
- Some rework required
- Some customer inconvenience
- Team stress increases

**Low (2)**: Minor impact
- Slight delays (<1 week)
- <10% budget overrun
- Minimal rework
- Minor inconvenience
- Easily absorbed

**Very Low (1)**: Negligible impact
- No noticeable delay
- No budget impact
- Easily worked around
- No customer impact

---

### Risk Severity Calculation

**Risk Score = Probability × Impact**

**Risk Severity Levels**:
- **Critical**: Score 20-25 (Red) - Immediate executive attention required
- **High**: Score 12-19 (Orange) - Immediate action required
- **Medium**: Score 6-11 (Yellow) - Monitor and plan mitigation
- **Low**: Score 3-5 (Green) - Accept or monitor
- **Very Low**: Score 1-2 (Green) - Accept

### Risk Priority Matrix

```
Impact │
   5   │  5   10  15  20  25
   4   │  4    8  12  16  20
   3   │  3    6   9  12  15
   2   │  2    4   6   8  10
   1   │  1    2   3   4   5
       └────────────────────
          1    2   3   4   5
              Probability

Legend:
■ 20-25: Critical (Immediate action)
■ 12-19: High (Action required)
■ 6-11: Medium (Monitor and plan)
■ 3-5: Low (Accept or monitor)
■ 1-2: Very Low (Accept)
```
```

**2.2 Assess Each Risk**

For each identified risk, assign probability and impact:

```markdown
## Risk Assessment Results

### Critical Risks (Score 20-25)

[If any exist, list here. Most projects shouldn't have critical risks if properly planned]

### High Risks (Score 12-19)

**RISK-T001: Complex Architecture Implementation**
- **Probability**: High (4) - Team new to distributed architecture
- **Impact**: High (4) - Could delay project by 3+ weeks
- **Risk Score**: 16 (High)
- **Rationale**: Team has limited microservices experience, architecture is complex, no prototype validation yet

**RISK-S002: Critical Path Dependency on Database Setup**
- **Probability**: Medium (3) - Database setup sometimes has issues
- **Impact**: Critical (5) - Blocks all backend development
- **Risk Score**: 15 (High)
- **Rationale**: All backend work depends on database being ready, setup has failed on 2 previous projects

**RISK-R001: Key Person Dependency (Senior Architect)**
- **Probability**: Medium (3) - People do leave or become unavailable
- **Impact**: High (4) - Would significantly delay architecture decisions and problem-solving
- **Risk Score**: 12 (High)
- **Rationale**: Only one person has deep architecture knowledge, no backup trained

[Continue for all high risks...]

### Medium Risks (Score 6-11)

**RISK-T003: Third-Party API Reliability**
- **Probability**: Medium (3) - External APIs sometimes have issues
- **Impact**: Medium (3) - Could delay related features by 1 week
- **Risk Score**: 9 (Medium)
- **Rationale**: Dependent on external service, history shows occasional issues but usually resolved quickly

**RISK-B001: Stakeholder Alignment**
- **Probability**: Medium (3) - Stakeholders sometimes have conflicting views
- **Impact**: Medium (3) - Could require rework of 1-2 features
- **Risk Score**: 9 (Medium)
- **Rationale**: Multiple stakeholders with different priorities, good process in place but misalignment can still occur

[Continue for all medium risks...]

### Low Risks (Score 3-5)

**RISK-Q002: Test Automation Framework Setup**
- **Probability**: Low (2) - Team has done this before successfully
- **Impact**: Low (2) - Minor delays, manual testing fallback exists
- **Risk Score**: 4 (Low)
- **Rationale**: Standard setup, team experienced, low impact if delayed

[Continue for all low risks...]

### Very Low Risks (Score 1-2)

[List very low risks - often these can be simply accepted]

---

### Risk Summary

**Total Risks Identified**: 42
- Critical: 0 (Scores 20-25)
- High: 5 (Scores 12-19)
- Medium: 12 (Scores 6-11)
- Low: 20 (Scores 3-5)
- Very Low: 5 (Scores 1-2)

**Average Risk Score**: 7.3 (Medium)

**Overall Project Risk Level**: **Medium** (5 high risks require immediate attention)

**Risk Concentration**: Highest risk concentration in Sprint 0 (infrastructure) and Sprint 1-2 (architecture implementation)
```

**Output**: All risks assessed with probability, impact, and severity scores

---

### Step 3: Risk Prioritization (30 minutes)

#### Objective
Prioritize risks to focus mitigation efforts on the most critical threats.

#### Actions

**3.1 Rank Risks by Severity**

```markdown
## Risk Priority Ranking

### Top 10 Risks (Ranked by Severity Score)

1. **RISK-T001**: Complex Architecture Implementation - Score 16 (High)
2. **RISK-S002**: Critical Path Dependency - Score 15 (High)
3. **RISK-T005**: Security Vulnerabilities - Score 12 (High)
4. **RISK-R001**: Key Person Dependency - Score 12 (High)
5. **RISK-S001**: Underestimated Complexity - Score 12 (High)
6. **RISK-B001**: Stakeholder Alignment - Score 9 (Medium)
7. **RISK-T003**: Third-Party API Reliability - Score 9 (Medium)
8. **RISK-Q001**: Test Coverage - Score 9 (Medium)
9. **RISK-T002**: Technology Learning Curve - Score 8 (Medium)
10. **RISK-R002**: Team Capacity - Score 6 (Medium)

### Risk Distribution by Category

**Technical**: 15 risks, Average score 8.2 (Medium-High)
**Schedule**: 8 risks, Average score 7.5 (Medium)
**Resource**: 6 risks, Average score 6.8 (Medium)
**Business**: 7 risks, Average score 6.2 (Medium)
**Quality**: 6 risks, Average score 7.0 (Medium)

**Analysis**: Technical risks are the highest concern - need focused mitigation

### Risk Concentration Analysis

**High Risk Areas** (where multiple risks concentrate):

1. **Sprint 0: Infrastructure Setup**
   - RISK-S002: Database setup blocks backend (Score 15)
   - RISK-T006: CI/CD pipeline complexity (Score 8)
   - RISK-T007: Cloud infrastructure setup issues (Score 6)
   - **Total Risk**: 3 risks, combined score 29
   - **Action**: Extra buffer in Sprint 0, daily monitoring

2. **Sprint 1-2: Architecture Implementation**
   - RISK-T001: Complex architecture (Score 16)
   - RISK-T002: Learning curve (Score 8)
   - RISK-R001: Key person dependency (Score 12)
   - **Total Risk**: 3 risks, combined score 36
   - **Action**: Architecture spike, pair programming, knowledge sharing

3. **Sprint 3-4: External Integrations**
   - RISK-T003: API reliability (Score 9)
   - RISK-T004: Integration complexity (Score 7)
   - **Total Risk**: 2 risks, combined score 16
   - **Action**: Early integration testing, mock services, fallback plans

### Risk Velocity Analysis

**Risks That May Escalate**:
- RISK-T002: Learning curve - May get worse as complexity increases
- RISK-R002: Team capacity - May worsen under time pressure
- RISK-Q001: Test coverage - Often drops when schedule pressure increases

**Risks That May Decrease**:
- RISK-T001: Architecture complexity - Will decrease after successful implementation
- RISK-R001: Key person dependency - Will decrease as knowledge sharing occurs

**Action**: Monitor escalating risks weekly, accelerate mitigation for these
```

**Output**: Prioritized list of risks with clear focus areas

---

### Step 4: Risk Mitigation Planning (2-4 hours)

#### Objective
Develop concrete mitigation strategies for high-priority risks (Scores 12+) and acceptance decisions for lower risks.

#### Actions

**4.1 Develop Mitigation Strategies for High Risks**

For each HIGH risk (score 12+), develop detailed mitigation plan:

```markdown
## High Risk Mitigation Plans

### RISK-T001: Complex Architecture Implementation (Score 16)

**Mitigation Strategy**: Reduce Probability
- **Action 1**: Conduct 5-day architecture spike in Sprint 0
  - Owner: Senior Architect
  - Timeline: Sprint 0, Days 1-5
  - Cost: 1 week delay to Sprint 1
  - Expected Impact: Reduces probability from 4 to 2 (50% reduction)
  
- **Action 2**: Implement proof-of-concept for riskiest components
  - Owner: Senior Architect + 1 Developer
  - Timeline: Sprint 0, Days 6-10
  - Cost: 1 additional week
  - Expected Impact: Further validates approach, reduces probability to 2

- **Action 3**: Pair programming for architecture implementation
  - Owner: Senior Architect + Dev Team
  - Timeline: Sprint 1-2, continuous
  - Cost: 20% productivity reduction (acceptable)
  - Expected Impact: Improves quality, reduces rework

- **Action 4**: Weekly architecture review meetings
  - Owner: Senior Architect leads, whole team attends
  - Timeline: Weekly through Sprint 2
  - Cost: 2 hours/week
  - Expected Impact: Catch issues early

**Contingency Plan** (if risk occurs):
- Fall back to simpler monolithic architecture
- Reduce feature scope to essential MVP
- Add 2 weeks to schedule
- Bring in external architecture consultant

**Residual Risk After Mitigation**:
- **New Probability**: 2 (was 4)
- **Impact**: 4 (unchanged)
- **New Risk Score**: 8 (Medium)
- **Acceptable**: Yes, score 8 is acceptable

---

### RISK-S002: Critical Path Dependency on Database Setup (Score 15)

**Mitigation Strategy**: Reduce Probability & Impact
- **Action 1**: Allocate most experienced DevOps engineer to database setup
  - Owner: DevOps Lead
  - Timeline: Sprint 0, start immediately
  - Cost: Reassign from other work
  - Expected Impact: Reduces probability from 3 to 2

- **Action 2**: Create detailed database setup runbook from previous project
  - Owner: DevOps Engineer
  - Timeline: Before Sprint 0
  - Cost: 1 day
  - Expected Impact: Reduces errors, improves reliability

- **Action 3**: Set up database in cloud sandbox environment first
  - Owner: DevOps Engineer
  - Timeline: Sprint -1 (before official Sprint 0)
  - Cost: 2 days early start
  - Expected Impact: Identify issues before critical path

- **Action 4**: Prepare local development database as fallback
  - Owner: DevOps Engineer
  - Timeline: Sprint 0, Day 1
  - Cost: 4 hours
  - Expected Impact: Reduces impact - team can work locally if cloud setup delayed

- **Action 5**: Daily standup focus on database setup progress
  - Owner: Project Manager
  - Timeline: Sprint 0, daily
  - Cost: None (existing standup)
  - Expected Impact: Early warning if issues arise

**Contingency Plan** (if risk occurs):
- Use local development databases while resolving cloud issues
- Bring in cloud database specialist
- Consider managed database service if setup too complex
- Add 1 week buffer to schedule

**Residual Risk After Mitigation**:
- **New Probability**: 2 (was 3)
- **Impact**: 3 (reduced from 5 by fallback option)
- **New Risk Score**: 6 (Medium)
- **Acceptable**: Yes

---

### RISK-T005: Security Vulnerabilities (Score 12)

**Mitigation Strategy**: Reduce Probability
- **Action 1**: Security training for all developers
  - Owner: Security Lead or external trainer
  - Timeline: Before Sprint 1
  - Cost: 1 day team time + training cost
  - Expected Impact: Reduces probability from 3 to 2

- **Action 2**: Implement automated security scanning in CI/CD
  - Owner: DevOps Engineer
  - Timeline: Sprint 0
  - Cost: 1 day setup + tool cost
  - Expected Impact: Catches issues early

- **Action 3**: Security code review checklist for all PRs
  - Owner: Security Champion (designated developer)
  - Timeline: Ongoing from Sprint 1
  - Cost: 10% increase in PR review time
  - Expected Impact: Prevents vulnerabilities from merging

- **Action 4**: Third-party security audit before production
  - Owner: Project Manager arranges
  - Timeline: After Sprint 5 (before production)
  - Cost: $5k-10k external audit
  - Expected Impact: Identifies remaining vulnerabilities

**Contingency Plan** (if vulnerabilities found):
- Allocate dedicated sprint for security fixes
- Delay production deployment until resolved
- Bring in security consultant if needed

**Residual Risk After Mitigation**:
- **New Probability**: 2 (was 3)
- **Impact**: 4 (unchanged - vulnerabilities are serious)
- **New Risk Score**: 8 (Medium)
- **Acceptable**: Yes, with ongoing monitoring

---

### RISK-R001: Key Person Dependency - Senior Architect (Score 12)

**Mitigation Strategy**: Reduce Probability & Impact
- **Action 1**: Architecture knowledge sharing sessions
  - Owner: Senior Architect
  - Timeline: Weekly in Sprint 0-2
  - Cost: 2 hours/week
  - Expected Impact: Reduces impact from 4 to 3

- **Action 2**: Document all architecture decisions in ADRs
  - Owner: Senior Architect
  - Timeline: Ongoing, real-time
  - Cost: 30 min per decision
  - Expected Impact: Knowledge preserved if person leaves

- **Action 3**: Pair programming on architecture implementation
  - Owner: Senior Architect + 2 designated developers
  - Timeline: Sprint 1-2
  - Cost: 20% productivity reduction
  - Expected Impact: Builds backup expertise

- **Action 4**: Identify backup architect (internal or consultant)
  - Owner: Engineering Manager
  - Timeline: Before Sprint 1
  - Cost: Time to identify and brief backup
  - Expected Impact: Reduces impact if key person unavailable

**Contingency Plan** (if key person becomes unavailable):
- Activate backup architect immediately
- Review all ADRs with backup
- Slow development pace until backup up to speed
- Consider bringing in external consultant

**Residual Risk After Mitigation**:
- **New Probability**: 3 (unchanged - people risks are hard to eliminate)
- **Impact**: 3 (reduced from 4 by knowledge sharing)
- **New Risk Score**: 9 (Medium)
- **Acceptable**: Yes, with continued knowledge sharing

---

### RISK-S001: Underestimated Task Complexity (Score 12)

**Mitigation Strategy**: Reduce Probability & Impact
- **Action 1**: Add 20% buffer to all Sprint 1-2 estimates
  - Owner: Planning Agent / Project Manager
  - Timeline: During sprint planning
  - Cost: Longer timeline (acceptable)
  - Expected Impact: Absorbs underestimation, reduces impact

- **Action 2**: Spike complex tasks before estimating
  - Owner: Technical leads
  - Timeline: Sprint 0 and ongoing
  - Cost: 1 day per complex task
  - Expected Impact: Better estimates, reduces probability

- **Action 3**: Re-estimate after Sprint 1 with actual velocity
  - Owner: Team + Project Manager
  - Timeline: After Sprint 1
  - Cost: 2 hours planning session
  - Expected Impact: Corrects estimates based on reality

- **Action 4**: Track actual vs. estimated for learning
  - Owner: Project Manager
  - Timeline: Ongoing
  - Cost: 30 min per sprint
  - Expected Impact: Improves future estimates

**Contingency Plan** (if complexity worse than expected):
- Reduce scope (nice-to-have features)
- Add resources if budget allows
- Extend timeline if acceptable to stakeholders
- Simplify architecture if necessary

**Residual Risk After Mitigation**:
- **New Probability**: 3 (unchanged - estimation is inherently uncertain)
- **Impact**: 3 (reduced from 4 by buffers)
- **New Risk Score**: 9 (Medium)
- **Acceptable**: Yes
```

**4.2 Develop Response Plans for Medium Risks**

For MEDIUM risks (score 6-11), develop lighter-weight response plans:

```markdown
## Medium Risk Response Plans

### RISK-B001: Stakeholder Alignment Issues (Score 9)

**Response Strategy**: Monitor & Prepare
- **Action 1**: Weekly stakeholder sync meetings
  - Owner: Product Manager
  - Cost: 1 hour/week
  
- **Action 2**: Document all stakeholder decisions in writing
  - Owner: Product Manager
  - Cost: 15 min per decision

**Trigger for Escalation**: If stakeholders disagree on priority or direction
**Escalation Plan**: Executive sponsor makes final decision

**Budget**: No budget needed unless escalation occurs

---

### RISK-T003: Third-Party API Reliability (Score 9)

**Response Strategy**: Prepare Fallback
- **Action 1**: Implement retry logic with exponential backoff
  - Owner: Backend developer
  - Timeline: During integration (Sprint 3)
  
- **Action 2**: Create mock API for testing
  - Owner: Backend developer
  - Timeline: Sprint 3

**Trigger for Activation**: API downtime >1 hour or >3 failures/day
**Contingency**: Switch to mock API, notify users of degraded functionality

---

### RISK-Q001: Insufficient Test Coverage (Score 9)

**Response Strategy**: Monitor & Adjust
- **Action 1**: Track code coverage weekly
  - Owner: Quality Lead
  - Target: 80% coverage
  
- **Action 2**: Block PRs below 70% coverage
  - Owner: CI/CD pipeline configuration
  - Timeline: Sprint 1

**Trigger for Escalation**: Coverage drops below 70% for two consecutive sprints
**Escalation Plan**: Dedicate one sprint to testing improvements

[Continue for remaining medium risks...]
```

**4.3 Accept Low Risks**

For LOW risks (score 3-5), generally accept or apply minimal response:

```markdown
## Low Risk Acceptance

### Accepted Low Risks
- **RISK-Q002**: Test Automation Framework Setup (Score 4) - ACCEPTED with monitoring
- **RISK-T008**: Third-party library updates (Score 4) - ACCEPTED, will handle if occurs
- **RISK-R003**: Developer learning curve for new IDE (Score 3) - ACCEPTED, minimal impact

**Monitoring**: Review quarterly to see if risks escalate
```

**Output**: Complete mitigation plans for all high risks, response plans for medium risks, acceptance for low risks

---

### Step 5: Risk Response Integration (1 hour)

#### Objective
Integrate risk mitigation actions into sprint plans as concrete tasks.

#### Actions

**5.1 Create Risk Mitigation Tasks**

```markdown
## Risk Mitigation Tasks

### Sprint 0 Mitigation Tasks

**Task R-001**: Conduct Architecture Spike (5 days)
- **Mitigates**: RISK-T001 (Score 16 → 8)
- **Owner**: Senior Architect
- **Priority**: Critical
- **Dependencies**: None
- **Definition of Done**: 
  - POC implemented for 3 riskiest components
  - Architecture decisions validated or adjusted
  - ADRs written for key decisions
  - Team briefed on findings

**Task R-002**: Setup Database in Sandbox Environment (2 days)
- **Mitigates**: RISK-S002 (Score 15 → 6)
- **Owner**: DevOps Engineer
- **Priority**: Critical
- **Dependencies**: None
- **Definition of Done**:
  - Database running in cloud sandbox
  - Schema created and tested
  - Connection from dev environment verified
  - Issues documented and resolved

**Task R-003**: Setup Local Development Databases (4 hours)
- **Mitigates**: RISK-S002 (fallback plan)
- **Owner**: DevOps Engineer
- **Priority**: High
- **Dependencies**: None
- **Definition of Done**:
  - Docker compose file for local DB
  - Setup script working on all dev machines
  - Data seeding script created

**Task R-004**: Setup Automated Security Scanning in CI/CD (1 day)
- **Mitigates**: RISK-T005 (Score 12 → 8)
- **Owner**: DevOps Engineer
- **Priority**: High
- **Dependencies**: CI/CD pipeline exists
- **Definition of Done**:
  - Security scanning tool integrated
  - Baseline scan completed
  - PR blocking configured for high severity issues
  - Team trained on reviewing results

### Sprint 1 Mitigation Tasks

**Task R-005**: Architecture Knowledge Sharing Session #1 (2 hours)
- **Mitigates**: RISK-R001 (Score 12 → 9)
- **Owner**: Senior Architect
- **Priority**: High
- **Recurring**: Weekly
- **Definition of Done**:
  - Session held with full team
  - Architecture concepts explained
  - Q&A addressed
  - Notes documented

**Task R-006**: Identify and Brief Backup Architect (4 hours)
- **Mitigates**: RISK-R001
- **Owner**: Engineering Manager
- **Priority**: High
- **Definition of Done**:
  - Backup identified (internal or external)
  - Backup briefed on architecture
  - Backup has access to all ADRs
  - Emergency contact process established

[Continue for all mitigation tasks...]

---

### Sprint Capacity Impact

**Sprint 0 Risk Mitigation Load**:
- Architecture spike: 5 days (1 person)
- Database setup activities: 3 days (1 person)
- Security scanning setup: 1 day (1 person)
- **Total**: 9 person-days of risk mitigation work
- **Impact**: Sprint 0 is primarily risk mitigation + infrastructure

**Sprint 1-2 Risk Mitigation Load**:
- Weekly knowledge sharing: 2 hours/week
- Pair programming overhead: 20% productivity reduction
- Re-estimation session: 2 hours
- **Total**: ~15% capacity reduction
- **Impact**: Factored into sprint planning

**Budget Impact**:
- Security training: $3,000
- Security audit (after Sprint 5): $8,000
- Buffer/contingency: 15% of budget
- **Total**: ~$15,000 additional + 15% buffer
```

**5.2 Update Sprint Plan with Risk Tasks**

```markdown
## Updated Sprint Plan with Risk Mitigation

### Sprint 0: Infrastructure + Risk Mitigation (2 weeks)

**Risk Mitigation Tasks** (Priority):
- [ ] R-001: Architecture spike (5 days) [CRITICAL]
- [ ] R-002: Database sandbox setup (2 days) [CRITICAL]
- [ ] R-003: Local dev database fallback (4 hrs) [HIGH]
- [ ] R-004: Security scanning setup (1 day) [HIGH]

**Infrastructure Tasks**:
- [ ] Setup CI/CD pipeline
- [ ] Configure environments
- [ ] Setup monitoring and logging

**Note**: Sprint 0 is risk-heavy by design - mitigating risks before development

---

### Sprint 1: Core Features + Ongoing Risk Mitigation (2 weeks)

**Ongoing Risk Mitigation**:
- [ ] R-005: Weekly architecture knowledge sharing (2 hrs/week)
- [ ] R-006: Identify backup architect (4 hrs)
- [ ] Monitor database stability daily

**Development Tasks**:
- [ ] [Regular sprint 1 tasks]

**Capacity Adjustment**: -20% for pair programming and knowledge sharing

[Continue for all sprints...]
```

**Output**: Sprint plans updated with concrete risk mitigation tasks and capacity adjustments

---

### Step 6: Risk Register Creation (1 hour)

#### Objective
Create comprehensive risk register document for ongoing tracking and management.

#### Actions

**6.1 Create Complete Risk Register**

Use `risk-register.template.md` and populate with all data:

```markdown
# Risk Register
**Project**: [Project Name]
**Date**: [Current Date]
**Owner**: Project Manager
**Status**: Active

---

## Executive Summary

**Total Risks**: 42
- Critical (20-25): 0
- High (12-19): 5
- Medium (6-11): 12
- Low (3-5): 20
- Very Low (1-2): 5

**Overall Project Risk Level**: MEDIUM

**Top 3 Risks**:
1. Complex Architecture Implementation (Score 16) - Mitigation in progress
2. Critical Path Database Dependency (Score 15) - Mitigation in progress
3. Security Vulnerabilities (Score 12) - Mitigation planned

**Risk Budget**: $15,000 + 15% schedule buffer
**Mitigation Status**: 5/5 high-risk mitigation plans in place

---

## High Risks (Score 12+)

### RISK-T001: Complex Architecture Implementation
- **Score**: 16 (High) → 8 (Medium) after mitigation
- **Probability**: 4 (High) → 2 (Low)
- **Impact**: 4 (High)
- **Category**: Technical / Architecture
- **Status**: MITIGATION IN PROGRESS
- **Owner**: Senior Architect
- **Date Identified**: [Date]
- **Last Updated**: [Date]

**Description**: 
Distributed microservices architecture is complex and team has limited experience with this pattern.

**Trigger**:
Implementation reveals unexpected complexity, integration issues arise, performance problems emerge.

**Impact if Occurs**:
- 3-4 week project delay
- Potential need to simplify architecture
- Quality issues from rushed implementation
- Team frustration and morale impact

**Mitigation Strategy**:
1. 5-day architecture spike in Sprint 0 (IN PROGRESS)
2. POC implementation of riskiest components (PLANNED)
3. Pair programming for architecture implementation (PLANNED)
4. Weekly architecture review meetings (PLANNED)

**Contingency Plan**:
- Fall back to simpler monolithic architecture
- Reduce feature scope to MVP essentials
- Add 2 weeks to schedule
- Engage external architecture consultant ($8k-12k)

**Residual Risk**: 8 (Medium) - ACCEPTABLE
**Review Frequency**: Weekly
**Next Review**: [Date]

**Status History**:
- [Date]: Risk identified, scored 16
- [Date]: Mitigation plan approved
- [Date]: Architecture spike started

---

[Continue for all 42 risks with full details...]

---

## Risk Monitoring Plan

### Daily Monitoring (Standup)
- Database setup progress (Sprint 0)
- Any blockers or new risks emerging
- Status of in-progress mitigation tasks

### Weekly Risk Review
- Review all HIGH risks (score 12+)
- Check if MEDIUM risks escalating
- Update risk scores if conditions change
- Review mitigation task progress

### Sprint Retrospective Risk Review
- What risks materialized?
- Were mitigation strategies effective?
- New risks identified?
- Update risk register

### Monthly Strategic Risk Review
- Overall project risk level trend
- Budget and schedule impact from risks
- Need for escalation to executives
- Update risk response strategies

---

## Risk Escalation Process

**Level 1 - Team** (Risks score 6-11):
- Team handles with PM oversight
- Documented in risk register
- Reviewed in sprint planning

**Level 2 - Project Manager** (Risks score 12-15):
- PM makes decisions and allocates resources
- May need to adjust schedule or scope
- Reports to stakeholders

**Level 3 - Executive** (Risks score 16+):
- Executive sponsor involved
- May require significant budget/schedule changes
- Strategic decisions needed

---

## Risk Budget Tracking

**Risk Mitigation Budget**: $15,000
- Security training: $3,000 (COMMITTED)
- Security audit: $8,000 (PLANNED - Sprint 5)
- Contingency: $4,000 (RESERVED)

**Schedule Buffer**: 15% (built into sprint planning)
- Sprint 0: 2 days buffer
- Sprint 1-2: 3 days buffer
- Sprint 3-5: 5 days buffer

**Status**: ON BUDGET, BUFFER ADEQUATE
```

**Output**: Complete risk register document ready for ongoing use

---

### Step 7: Validation and Sign-Off (30 minutes)

#### Objective
Validate risk assessment with stakeholders and get approval to proceed.

#### Actions

**7.1 Risk Assessment Validation**

Review your risk register against quality criteria:

```markdown
## Risk Assessment Quality Checklist

### Completeness
- [ ] All technical risks identified (architecture, technology, integration, security)
- [ ] All schedule risks identified (estimates, dependencies, external factors)
- [ ] All resource risks identified (team capacity, key person dependencies)
- [ ] All business risks identified (stakeholders, market, budget)
- [ ] All quality risks identified (testing, code quality, technical debt)
- [ ] Historical risk patterns incorporated

### Assessment Quality
- [ ] Every risk has clear description
- [ ] Every risk has defined trigger conditions
- [ ] Every risk has quantified impact
- [ ] Probability and impact scores are justified with rationale
- [ ] Risk scores calculated correctly (Probability × Impact)
- [ ] Risk severity levels assigned correctly

### Mitigation Planning
- [ ] All HIGH risks (12+) have detailed mitigation plans
- [ ] Mitigation strategies are concrete and actionable
- [ ] Mitigation tasks have owners and timelines
- [ ] Contingency plans exist for high risks
- [ ] Residual risk calculated after mitigation
- [ ] Mitigation tasks integrated into sprint plans

### Documentation Quality
- [ ] Risk register is complete and well-organized
- [ ] Risk descriptions are clear and unambiguous
- [ ] Mitigation strategies are detailed enough to execute
- [ ] Monitoring process is defined
- [ ] Escalation process is clear
- [ ] Status tracking mechanism in place

### Stakeholder Alignment
- [ ] PM reviewed and approved risk assessment
- [ ] Technical leads agree with technical risk assessment
- [ ] Stakeholders aware of top risks and mitigation strategies
- [ ] Executive sponsor briefed on overall risk level
- [ ] Budget and schedule impacts approved
```

**7.2 Stakeholder Review**

```markdown
## Risk Assessment Review Meeting

**Attendees**:
- Project Manager (required)
- Technical Lead / Senior Architect (required)
- Product Owner (required)
- Executive Sponsor (for high-risk projects)
- Key stakeholders (as needed)

**Agenda**:
1. Present overall project risk level (15 minutes)
   - Total risk count and distribution
   - Top 5 risks
   - Risk concentration areas

2. Deep dive on HIGH risks (30 minutes)
   - Present each high risk (score 12+)
   - Explain mitigation strategy
   - Discuss residual risk
   - Get feedback and approval

3. Review risk budget and schedule impact (15 minutes)
   - Mitigation costs
   - Schedule buffers
   - Capacity impacts

4. Review risk monitoring plan (10 minutes)
   - Daily, weekly, monthly reviews
   - Escalation process

5. Decision and sign-off (10 minutes)
   - Is overall risk level acceptable?
   - Are mitigation strategies adequate?
   - Approval to proceed with current plan?

**Decisions Required**:
- [ ] Overall risk assessment APPROVED
- [ ] Risk mitigation budget APPROVED ($15k + 15% buffer)
- [ ] Schedule impact from risk mitigation APPROVED
- [ ] Proceed to development: YES / NO / WITH MODIFICATIONS

**Sign-off**:
- Project Manager: __________________ Date: ______
- Technical Lead: __________________ Date: ______
- Product Owner: __________________ Date: ______
- Executive Sponsor: __________________ Date: ______
```

**Output**: Approved risk assessment with stakeholder sign-off

---

## Outputs

### Required Outputs

At the end of this workflow, you must have:

1. **Risk Register** (`risk-register.md`)
   - Complete register of all 25-50 identified risks
   - All risks assessed with probability, impact, score
   - Risk severity levels assigned
   - Detailed mitigation plans for high risks
   - Response plans for medium risks
   - Monitoring and escalation process defined

2. **Updated Sprint Plans** (`sprint-plan.md` updated)
   - Risk mitigation tasks integrated into sprints
   - Capacity adjustments for risk mitigation work
   - Sprint 0 loaded with infrastructure + risk mitigation
   - Buffers built into schedule

3. **Risk Budget**
   - Mitigation costs identified
   - Contingency budget allocated (typically 10-20%)
   - Schedule buffer defined (typically 15-25%)

4. **Stakeholder Approval**
   - Risk assessment reviewed with key stakeholders
   - Sign-off on risk level and mitigation approach
   - Approval to proceed with development

### Optional Outputs

- **Risk Dashboard** - Visual representation of risk status
- **Risk Heat Map** - Visual priority matrix
- **Monthly Risk Report Template** - For ongoing reporting

---

## Validation Criteria

Before marking risk assessment complete, verify:

### Risk Identification
- [ ] Minimum 20 risks identified across all categories
- [ ] All major project domains covered (technical, schedule, resource, business, quality)
- [ ] Historical risk patterns incorporated
- [ ] Team participated in risk brainstorming

### Risk Assessment
- [ ] All risks scored with probability and impact
- [ ] Risk scores have clear rationale documented
- [ ] Risk severity levels match scoring criteria
- [ ] At least 5-10 medium or high risks identified (if none, reassess)

### Mitigation Planning
- [ ] All HIGH risks have detailed mitigation plans
- [ ] Mitigation strategies are specific and actionable
- [ ] Owners assigned to all mitigation tasks
- [ ] Timelines set for all mitigation activities
- [ ] Contingency plans exist for major risks
- [ ] Residual risk calculated and acceptable

### Integration
- [ ] Mitigation tasks added to sprint backlogs
- [ ] Sprint capacity adjusted for mitigation work
- [ ] Budget includes mitigation costs
- [ ] Schedule includes risk buffers

### Documentation
- [ ] Risk register is complete and organized
- [ ] Monitoring plan is clear and actionable
- [ ] Escalation process is defined
- [ ] Status tracking mechanism established

### Approval
- [ ] Stakeholders reviewed and understand risks
- [ ] PM and technical leads approve assessment
- [ ] Executive sponsor (if required) approves
- [ ] Approval to proceed obtained

---

## Risk Management Ongoing Process

### Daily Risk Activities (During Standups)
- Quick check: Any new risks emerged?
- Status of in-progress mitigation tasks
- Any existing risks getting worse?
- Any blockers related to risks?

### Weekly Risk Reviews (15-30 minutes)
- Review all HIGH risks
- Check if any MEDIUM risks escalating
- Update risk scores if conditions changed
- Review mitigation task progress
- Update risk register

### Sprint Planning Risk Activities
- Consider risks when estimating tasks
- Allocate capacity for risk mitigation
- Prioritize risk mitigation tasks appropriately
- Build in appropriate buffers

### Sprint Retrospective Risk Activities
- Which risks materialized? How handled?
- Were mitigation strategies effective?
- Any new risks discovered during sprint?
- What would we do differently?
- Update lessons learned

### Monthly Strategic Risk Review
- Overall project risk level trend
- Cumulative impact of risks on budget/schedule
- Need for escalation or course correction?
- Update risk response strategies
- Report to executives

### Sprint 0 Risk Activities

During Sprint 0 (Infrastructure + Risk Mitigation):
- Execute high-priority mitigation tasks
- Monitor critical path risks daily
- Hold first weekly risk review
- Update risk register based on learnings

### Ongoing Risk Management

Remember:
- Risk management is continuous, not one-time
- Risk register is a living document - update it!
- When new risks emerge, add them immediately
- When risks are resolved, close them out
- When conditions change, re-assess scores
- Celebrate successful risk mitigation!

---

## Troubleshooting

### Issue: Team sees risk management as overhead

**Symptom**: Team resists risk planning, sees it as bureaucracy

**Solutions**:
- Keep risk reviews short and focused (15-30 min max)
- Only track HIGH and MEDIUM risks actively
- Show value by preventing problems early
- Integrate risk tasks into normal workflow naturally
- Don't make risk management a separate heavy process
- Focus on action, not documentation
- Celebrate when mitigation prevents problems

---

### Issue: Risks keep getting identified late

**Symptom**: New high-priority risks appear mid-project unexpectedly

**Solutions**:
- Encourage team to raise concerns early (psychological safety)
- Make risk identification part of every planning session
- Review risks in every sprint retrospective
- Create safe environment to discuss problems without blame
- Regular risk brainstorming sessions
- Look at adjacent teams' risk registers for patterns
- Review lessons learned from similar projects regularly

---

### Issue: Mitigation plans not executed

**Symptom**: Risk mitigation tasks get deprioritized or skipped

**Solutions**:
- Make risk tasks visible in sprint backlog with HIGH priority
- Assign clear owners and due dates to mitigation tasks
- Track mitigation progress in daily standups
- Link risks to sprint goals and success criteria
- Escalate if critical mitigations consistently skipped
- Explain risk impact to get team buy-in
- Protect mitigation tasks during sprint planning

---

### Issue: Risk scores never decrease

**Symptom**: Mitigation doesn't seem to reduce risk levels

**Solutions**:
- Re-assess risk scoring criteria (may be too conservative)
- Verify mitigation actions are being executed fully
- Some actions need time to show effect
- May need different mitigation strategy
- Some risks are inherent (accept higher baseline)
- Focus on impact reduction vs. probability if needed
- Ensure residual risk calculation is realistic

---

### Issue: Too many risks to manage

**Symptom**: Risk register has 100+ risks, team overwhelmed

**Solutions**:
- Focus on HIGH and MEDIUM risks only (accept low risks)
- Combine related risks into single risk
- Archive risks below certain threshold
- Use risk categories to group and simplify
- Don't track every possible thing that could go wrong
- Focus on actionable risks only
- Review and prune risk register monthly

---

### Issue: Risk assessment feels like guessing

**Symptom**: Team has no confidence in probability/impact scores

**Solutions**:
- Use historical data from similar projects
- Get input from experienced team members
- Use ranges instead of point estimates
- Focus on relative priority, not exact scores
- Accept that estimation is inherently uncertain
- Adjust scores as you learn more
- What matters is identifying and mitigating, not perfect scoring

---

## Summary

**This workflow provides a systematic approach to risk management that protects project success while remaining lightweight and practical.**

**Key Success Factors**:
1. Comprehensive risk identification across all domains
2. Structured assessment using clear criteria
3. Focused mitigation on high-priority risks
4. Integration of risk responses into project plans
5. Continuous monitoring and adaptation
6. Stakeholder awareness and buy-in

**Remember**: Risk management isn't about eliminating all risks (impossible). It's about:
- Knowing what could go wrong
- Being prepared with responses
- Reducing probability and impact where possible
- Accepting risks consciously when necessary
- Adapting as conditions change

**Follow this workflow to identify, assess, and proactively manage project risks, maximizing your probability of project success.**
