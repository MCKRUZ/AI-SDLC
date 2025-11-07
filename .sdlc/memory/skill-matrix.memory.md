# Skill Matrix Context

**Purpose**: Defines skills, competencies, and proficiency levels required for software delivery roles.

**Last Updated**: 2025-11-07  
**Owner**: Practice Management / Talent Development  
**Review Cycle**: Quarterly

---

## 🔧 CONFIGURATION GUIDE

This file defines **skills and competencies** for your organization. Customize:

1. **Skill Categories** - Technical, leadership, domain skills for your context
2. **Proficiency Levels** - How to assess skill mastery (1-5 scale)
3. **Role Profiles** - Expected skills by role and level
4. **Skill Shapes** - T-shaped, π-shaped, comb-shaped profiles
5. **Gap Analysis Criteria** - How to identify and prioritize skill gaps
6. **Development Paths** - How people grow skills over time

**Resource Planner agent references this file** when:
- Validating team capability for project requirements
- Identifying skill gaps in proposed pods
- Recommending training or hiring needs
- Assessing team readiness for project types

---

## Skill Framework Philosophy

### Core Principles

**1. Skill Shapes Matter**
- **T-shaped**: Deep expertise in one area, broad general knowledge
- **π-shaped**: Deep expertise in two areas, broad general knowledge
- **Comb-shaped**: Multiple areas of moderate depth, broad knowledge
- **I-shaped**: Deep in one area, narrow elsewhere (specialist)

**2. Proficiency Is Context-Dependent**
- Level 3 in React for a junior developer ≠ Level 3 for a senior architect
- Proficiency must be calibrated to role expectations
- "Expert" means different things at different levels

**3. Balance Depth and Breadth**
- Junior roles: Focus on breadth (learning many things)
- Mid-level: Develop one deep specialty (T-shape)
- Senior: Add second deep area (π-shape) or broaden
- Leadership: Strategic knowledge across domains

**4. Skills Decay Without Use**
- Technical skills especially decay rapidly (6-12 months)
- Assume 20% skill erosion per year without active use
- "I used to know X" ≠ "I know X"

**5. Cultural Fit Is Also a Skill**
- Collaboration, communication, adaptability matter
- Technical brilliance without teamwork creates problems
- Assess "how" someone works, not just "what" they know

---

## 🔧 Proficiency Scale Definition

### Universal 5-Level Scale

| Level | Name | Definition | Can They... | Typical Experience |
|-------|------|------------|-------------|-------------------|
| **1** | **Awareness** | Has heard of it, basic understanding | Explain what it is, when it's used | 0-6 months |
| **2** | **Novice** | Can use with guidance, learning actively | Perform basic tasks with help | 6 months - 1 year |
| **3** | **Competent** | Independent on standard tasks | Work autonomously on typical problems | 1-3 years |
| **4** | **Proficient** | Handles complex scenarios, mentors others | Design solutions, troubleshoot edge cases | 3-5 years |
| **5** | **Expert** | Recognized authority, innovates, leads | Set standards, solve novel problems | 5+ years |

### Calibration by Role Level

**L1 (Staff Consultant)**:
- Expected max proficiency: Level 3
- Target: 2-3 skills at Level 3, rest at Level 2
- Expert (5) not expected at this level

**L2 (Consultant)**:
- Expected max proficiency: Level 4
- Target: 1-2 skills at Level 4, 3-4 at Level 3
- Developing T-shape

**L3 (Senior Consultant)**:
- Expected max proficiency: Level 4-5
- Target: 1 skill at Level 5, 2-3 at Level 4
- Established T-shape

**L4 (Manager)**:
- Expected max proficiency: Level 5 (strategic depth)
- Target: 2 skills at Level 5, broad Level 3+ across domain
- π-shaped or comb-shaped

**L5-L6 (Senior Leadership)**:
- Expected max proficiency: Level 5 (strategic + architectural)
- Target: Strategic expertise across domain, deep in 2-3 areas
- Comb-shaped

---

## 🔧 Skill Categories

### 1. Core Technical Skills

#### Programming Languages

**Modern Backend**:
- C# / .NET
- Java / Spring
- Python
- Node.js / TypeScript
- Go
- Rust

**Frontend**:
- JavaScript / TypeScript
- React
- Angular
- Vue.js
- HTML5 / CSS3
- Web Components

**Mobile**:
- Swift (iOS)
- Kotlin (Android)
- React Native
- Flutter

**Data & Analytics**:
- SQL (PostgreSQL, SQL Server, MySQL)
- Python (pandas, NumPy)
- R
- Spark / PySpark

**Proficiency Expectations by Level**:

| Role Level | Expected Languages | Proficiency | Notes |
|------------|-------------------|-------------|-------|
| **L1** | 1 language | Level 2-3 | Learning primary language |
| **L2** | 1-2 languages | Level 3-4 (primary) | Competent in primary, awareness in second |
| **L3** | 2-3 languages | Level 4-5 (primary), 3 (others) | Expert in primary, competent in others |
| **L4** | 2-4 languages | Level 4-5 (multiple) | Strategic understanding of language choice |
| **L5+** | Language-agnostic | Level 3-5 (multiple) | Conceptual mastery, can learn new quickly |

---

#### Frameworks & Libraries

**Backend Frameworks**:
- ASP.NET Core
- Entity Framework
- Spring Boot
- Django / Flask
- Express.js
- FastAPI

**Frontend Frameworks**:
- React (Hooks, Context, Redux)
- Next.js
- Angular (RxJS, NgRx)
- Vue.js (Vuex, Composition API)

**Testing Frameworks**:
- Jest / Vitest
- Pytest
- NUnit / xUnit
- Mocha / Chai
- Selenium / Playwright
- Cypress

**Proficiency Expectations**:
- **L1-L2**: 1-2 frameworks at Level 2-3
- **L3**: Primary framework at Level 4-5, secondary at Level 3
- **L4+**: Framework-agnostic thinking, can evaluate and select

---

#### Cloud Platforms

**Major Platforms**:
- **Azure**: VMs, App Service, Functions, AKS, Storage, SQL Database, CosmosDB, Event Grid, Logic Apps
- **AWS**: EC2, Lambda, ECS/EKS, S3, RDS, DynamoDB, EventBridge, Step Functions
- **GCP**: Compute Engine, Cloud Functions, GKE, Cloud Storage, Cloud SQL, BigQuery

**Core Cloud Skills**:
- Infrastructure as Code (Terraform, Bicep, CloudFormation)
- Identity & Access Management (Azure AD, AWS IAM, GCP IAM)
- Networking (VNets, VPCs, Subnets, Load Balancers)
- Security (Key Vault, Secrets Manager, Security Center)
- Monitoring & Logging (Application Insights, CloudWatch, Cloud Monitoring)
- Cost Management & Optimization

**Proficiency by Role**:

| Role | Expected Proficiency | Typical Skills |
|------|----------------------|----------------|
| **General Developer (L1-L3)** | Level 2-3 on one platform | Deploy apps, use managed services, basic troubleshooting |
| **Cloud Engineer (L3-L4)** | Level 4 on one, Level 2-3 on another | Design solutions, IaC, security, cost optimization |
| **Cloud Architect (L5-L6)** | Level 4-5 on primary, Level 3+ on others | Multi-cloud strategy, advanced patterns, governance |

---

#### DevOps & Site Reliability

**CI/CD**:
- Azure DevOps (Pipelines, Repos, Boards)
- GitHub Actions
- GitLab CI/CD
- Jenkins
- CircleCI

**Infrastructure as Code**:
- Terraform
- Azure Bicep / ARM Templates
- AWS CloudFormation
- Pulumi
- Ansible

**Containerization & Orchestration**:
- Docker
- Kubernetes (AKS, EKS, GKE)
- Helm
- Docker Compose

**Monitoring & Observability**:
- Application Insights / Azure Monitor
- Prometheus / Grafana
- Datadog
- New Relic
- ELK Stack (Elasticsearch, Logstash, Kibana)

**Proficiency by Role**:
- **Developers (L1-L3)**: Level 2-3 (can use CI/CD, understand containers)
- **DevOps Engineers (L3-L5)**: Level 4-5 (design pipelines, manage infrastructure)
- **SRE (L4-L6)**: Level 4-5 (production operations, incident response, SLOs)

---

#### Databases & Data Storage

**Relational Databases**:
- SQL Server
- PostgreSQL
- MySQL
- Oracle

**NoSQL Databases**:
- MongoDB
- CosmosDB
- DynamoDB
- Redis
- Cassandra

**Data Warehousing**:
- Azure Synapse Analytics
- Snowflake
- Amazon Redshift
- Google BigQuery

**Core Database Skills**:
- Query optimization
- Indexing strategies
- Transaction management
- Backup and recovery
- Replication and sharding
- Data modeling (normalization, denormalization)

**Proficiency by Role**:
- **Developers (L1-L3)**: Level 3-4 on SQL, Level 2 on NoSQL
- **Data Engineers (L3-L5)**: Level 4-5 on multiple DB types
- **Architects (L4-L6)**: Level 4-5 strategic (data architecture, storage selection)

---

#### Security & Compliance

**Core Security Skills**:
- Authentication & Authorization (OAuth, OIDC, SAML)
- Encryption (at rest, in transit)
- Security headers (CORS, CSP, HSTS)
- Input validation & sanitization
- SQL injection prevention
- XSS prevention
- CSRF protection
- Secrets management

**Compliance Frameworks**:
- GDPR
- HIPAA
- PCI DSS
- SOC 2
- ISO 27001

**Security Tools**:
- OWASP ZAP / Burp Suite
- SonarQube / Snyk
- Vault (HashiCorp)
- Azure Key Vault / AWS Secrets Manager

**Proficiency by Role**:
- **All Developers (L1+)**: Level 2-3 (secure coding practices)
- **Senior Developers (L3+)**: Level 3-4 (design secure systems)
- **Security Engineers (L3-L5)**: Level 4-5 (security architecture, penetration testing)

---

### 2. Software Engineering Practices

#### Design Patterns & Architecture

**Common Patterns**:
- SOLID principles
- Design patterns (Factory, Singleton, Observer, Strategy, etc.)
- Dependency Injection
- Repository pattern
- CQRS (Command Query Responsibility Segregation)
- Event Sourcing
- Saga pattern (distributed transactions)

**Architectural Styles**:
- Monolithic
- N-tier / Layered
- Microservices
- Event-driven architecture
- Serverless
- Hexagonal / Clean Architecture

**Proficiency by Role**:
- **L1-L2**: Level 1-2 (awareness, can apply simple patterns)
- **L3**: Level 3-4 (can design using patterns appropriately)
- **L4-L6**: Level 4-5 (choose architecture style, create patterns)

---

#### Testing & Quality Assurance

**Testing Types**:
- Unit testing
- Integration testing
- End-to-end testing
- Performance testing
- Security testing
- Accessibility testing

**Testing Practices**:
- Test-Driven Development (TDD)
- Behavior-Driven Development (BDD)
- Test automation
- Continuous testing
- Shift-left testing

**Quality Metrics**:
- Code coverage
- Defect density
- Mean time to recovery (MTTR)
- Change failure rate

**Proficiency by Role**:
- **L1-L2**: Level 2-3 (write unit tests, follow test plans)
- **L3**: Level 3-4 (design test strategies, automate)
- **L4+**: Level 4-5 (quality architecture, testing frameworks)

---

#### Version Control & Collaboration

**Version Control**:
- Git (branching, merging, rebasing, cherry-picking)
- Git workflows (GitFlow, trunk-based development)
- Pull request / code review processes
- Merge conflict resolution

**Collaboration Tools**:
- GitHub / Azure Repos / GitLab / Bitbucket
- Code review tools
- Documentation (Markdown, wikis, ADRs)

**Proficiency by Role**:
- **L1**: Level 2 (basic git operations, commits, branches)
- **L2**: Level 3 (branching strategies, effective PRs)
- **L3+**: Level 4 (manage branching models, resolve complex conflicts)

---

### 3. Domain & Business Skills

#### Industry Domains

**Examples** (Customize for Your Organization):
- **Financial Services**: Banking, payments, trading, compliance (KYC, AML)
- **Healthcare**: EHR, HIPAA, clinical workflows, medical devices
- **Manufacturing**: ERP, MES, supply chain, IoT/OT systems
- **Retail**: E-commerce, inventory, POS, customer loyalty
- **Technology/SaaS**: Multi-tenancy, subscription billing, usage analytics

**Domain Proficiency**:
- **Level 1-2**: Understands basic terminology and workflows
- **Level 3**: Can design solutions that fit industry norms
- **Level 4-5**: Deep industry expertise, anticipates domain-specific challenges

**Value of Domain Knowledge**:
- Reduces miscommunication with stakeholders
- Better requirements elicitation
- Appropriate solution design (not over-engineering)
- Credibility with subject matter experts

---

#### Business & Product Thinking

**Core Skills**:
- Business case development
- Cost-benefit analysis
- ROI calculation
- Product roadmapping
- User research and personas
- Jobs-to-be-Done framework
- Prioritization (RICE, MoSCoW, Kano)
- Stakeholder management

**Proficiency by Role**:
- **L1-L2**: Level 1-2 (awareness, follows product direction)
- **L3**: Level 2-3 (contributes to product discussions)
- **L4**: Level 3-4 (shapes product strategy)
- **L5+**: Level 4-5 (leads product vision, business strategy)

---

#### Process & Methodologies

**Agile Methodologies**:
- Scrum
- Kanban
- SAFe (Scaled Agile Framework)
- Lean
- XP (Extreme Programming)

**Project Management**:
- Waterfall / Phase-Gate
- Hybrid approaches
- Risk management
- Change management
- Dependency management

**Proficiency by Role**:
- **L1-L2**: Level 2-3 (participates in ceremonies effectively)
- **L3**: Level 3-4 (can lead agile ceremonies)
- **L4+**: Level 4-5 (tailors process to context, organizational change)

---

### 4. Leadership & Soft Skills

#### Communication

**Core Skills**:
- Written communication (documentation, emails, specifications)
- Verbal communication (presentations, meetings, 1-on-1s)
- Active listening
- Storytelling and persuasion
- Executive communication (concise, outcome-focused)
- Technical to non-technical translation

**Proficiency by Role**:
- **L1-L2**: Level 2-3 (clear technical communication with team)
- **L3**: Level 3-4 (explains technical concepts to non-technical audiences)
- **L4+**: Level 4-5 (executive presence, influences without authority)

---

#### Collaboration & Teamwork

**Core Skills**:
- Conflict resolution
- Giving and receiving feedback
- Building consensus
- Cross-functional collaboration
- Remote/distributed team collaboration
- Pair programming / mob programming
- Code review etiquette

**Proficiency by Role**:
- **All Levels**: Minimum Level 3 (teamwork is table stakes)
- **L3+**: Level 4-5 (actively improves team dynamics)
- **L4+**: Level 4-5 (builds high-performing teams)

---

#### Mentoring & Development

**Core Skills**:
- Coaching and mentoring
- Knowledge transfer
- Technical teaching
- Career development guidance
- Performance feedback

**Proficiency by Role**:
- **L1-L2**: Level 1-2 (peer learning, pair programming)
- **L3**: Level 3-4 (formal mentoring of juniors)
- **L4+**: Level 4-5 (develops others, builds bench strength)

---

#### Problem-Solving & Critical Thinking

**Core Skills**:
- Root cause analysis (Five Whys, Fishbone)
- Analytical thinking
- Systems thinking
- Trade-off analysis
- Decision-making under uncertainty
- Debugging and troubleshooting

**Proficiency by Role**:
- **L1**: Level 2 (solves well-defined problems)
- **L2**: Level 3 (solves ambiguous problems with guidance)
- **L3**: Level 4 (independently tackles complex problems)
- **L4+**: Level 5 (solves novel, strategic problems)

---

## 🔧 Role Skill Profiles

### Staff Consultant (L1)

**Skill Shape**: Early T-shape (building depth in one area)

**Expected Skills**:

| Skill Category | Specific Skills | Target Proficiency |
|----------------|-----------------|-------------------|
| **Primary Language** | 1 language (e.g., C#, JavaScript, Python) | Level 3 |
| **Web Fundamentals** | HTML, CSS, HTTP, REST APIs | Level 2-3 |
| **Version Control** | Git basics (commit, push, pull, branch) | Level 2 |
| **Testing** | Unit testing in primary language | Level 2 |
| **Databases** | SQL basics (SELECT, INSERT, UPDATE, DELETE) | Level 2 |
| **Agile Practices** | Scrum ceremonies, user stories | Level 2 |
| **Communication** | Technical writing, team communication | Level 2-3 |
| **Problem-Solving** | Debugging, troubleshooting with guidance | Level 2 |

**Typical Gaps**:
- Limited experience with production systems
- Needs guidance on architecture decisions
- Learning code quality practices
- Building soft skills (communication, collaboration)

**Development Path**:
- Focus: Deepen primary language to Level 4
- Add: Framework proficiency (e.g., React, .NET Core)
- Develop: Independent problem-solving skills
- Grow: Mentoring skills (peer support)

---

### Consultant (L2)

**Skill Shape**: Developing T-shape (one area of depth, broadening)

**Expected Skills**:

| Skill Category | Specific Skills | Target Proficiency |
|----------------|-----------------|-------------------|
| **Primary Language** | 1 language + strong framework | Level 3-4 |
| **Secondary Language** | 1 additional language (awareness) | Level 2 |
| **Web Development** | Full-stack basics or frontend/backend depth | Level 3 |
| **Version Control** | Git workflows, code review, PR process | Level 3 |
| **Testing** | TDD, integration testing | Level 3 |
| **Databases** | Query optimization, basic data modeling | Level 3 |
| **Cloud** | One cloud platform (deploy, basic services) | Level 2-3 |
| **DevOps** | CI/CD concepts, containerization basics | Level 2 |
| **Agile Practices** | Effective sprint participation, estimates | Level 3 |
| **Communication** | Present work, document designs | Level 3 |
| **Collaboration** | Code review, pair programming | Level 3 |
| **Problem-Solving** | Independent on standard problems | Level 3 |

**Typical Gaps**:
- Limited architectural thinking
- Less experience with performance optimization
- Developing leadership skills
- Growing domain knowledge

**Development Path**:
- Focus: Achieve Level 4-5 in primary technical area
- Add: Second technical skill to Level 3 (π-shape foundation)
- Develop: Mentoring skills for juniors
- Grow: Start contributing to architecture discussions

---

### Senior Consultant (L3)

**Skill Shape**: Established T-shape (one area of mastery, broad competence)

**Expected Skills**:

| Skill Category | Specific Skills | Target Proficiency |
|----------------|-----------------|-------------------|
| **Primary Specialty** | 1 area of deep expertise (e.g., React, backend APIs) | Level 4-5 |
| **Secondary Skills** | 2-3 complementary skills | Level 3-4 |
| **Languages** | 2-3 languages | Level 4 (primary), 3 (others) |
| **Architecture** | Design patterns, component design | Level 3-4 |
| **Testing** | Test automation, testing strategy | Level 4 |
| **Cloud** | Cloud-native design, IaC basics | Level 3-4 |
| **DevOps** | CI/CD, containerization, monitoring | Level 3 |
| **Security** | Secure coding, OWASP Top 10 | Level 3-4 |
| **Performance** | Optimization, profiling, scalability | Level 3-4 |
| **Domain** | Industry knowledge relevant to projects | Level 2-3 |
| **Agile** | Lead ceremonies, mentor team on practices | Level 4 |
| **Communication** | Technical presentations, architecture docs | Level 4 |
| **Mentoring** | Formal mentoring of L1-L2 | Level 3-4 |
| **Problem-Solving** | Complex, ambiguous problems independently | Level 4 |

**Typical Gaps**:
- Strategic thinking (still tactical focus)
- Limited experience leading large initiatives
- Growing business acumen
- Developing executive communication

**Development Path**:
- Focus: Broaden to π-shape (add second depth area)
- Add: Leadership skills (influence, vision)
- Develop: Strategic thinking and business context
- Grow: Cross-functional collaboration

---

### Manager (L4)

**Skill Shape**: π-shaped or Comb-shaped (two areas of depth, broad leadership skills)

**Expected Skills**:

| Skill Category | Specific Skills | Target Proficiency |
|----------------|-----------------|-------------------|
| **Technical Depth** | 2 areas of expertise (e.g., architecture + cloud) | Level 4-5 |
| **Technical Breadth** | Broad understanding across stack | Level 3-4 |
| **Architecture** | System design, technology selection, ADRs | Level 4-5 |
| **Leadership** | Team leadership, conflict resolution | Level 4 |
| **People Management** | Performance management, career development | Level 3-4 |
| **Client Management** | Client relationships, expectation setting | Level 3-4 |
| **Project Management** | Timeline, scope, resource management | Level 3-4 |
| **Risk Management** | Risk identification, mitigation planning | Level 3-4 |
| **Domain** | Deep industry knowledge | Level 3-4 |
| **Business Thinking** | ROI, business case development | Level 3-4 |
| **Communication** | Executive communication, stakeholder management | Level 4 |
| **Mentoring** | Develop L1-L3, career guidance | Level 4-5 |
| **Strategy** | Workstream strategy, tactical planning | Level 3-4 |

**Typical Gaps**:
- Building organizational influence
- Portfolio/program-level thinking
- Advanced business/financial acumen
- Political navigation

**Development Path**:
- Focus: Strategic leadership over tactical execution
- Add: Business and financial management
- Develop: Organizational influence
- Grow: Portfolio/program management

---

### Senior Manager (L5) and Director (L6)

**Skill Shape**: Comb-shaped (broad strategic depth across domains)

**Expected Skills**:

| Skill Category | Specific Skills | Target Proficiency (L5/L6) |
|----------------|-----------------|----------------------------|
| **Technical Strategy** | Technology vision, roadmaps | Level 4-5 |
| **Architecture** | Enterprise architecture, strategic patterns | Level 4-5 |
| **Leadership** | Team building, cultural development | Level 4-5 |
| **People Development** | Talent strategy, succession planning | Level 4-5 |
| **Client Executive Engagement** | C-level relationships, advisory | Level 4-5 |
| **Program Management** | Multi-workstream coordination | Level 4-5 |
| **Financial Management** | P&L, budgeting, forecasting | Level 4-5 (L6) |
| **Risk Management** | Enterprise risk, mitigation strategy | Level 4-5 |
| **Domain Expertise** | Industry thought leadership | Level 4-5 |
| **Business Strategy** | Market positioning, growth strategy | Level 4-5 (L6) |
| **Change Management** | Organizational transformation | Level 4-5 |
| **Communication** | Executive presence, influence at all levels | Level 5 |
| **Mentoring** | Develop leaders (L3-L5) | Level 5 |
| **Strategic Thinking** | Long-term vision, portfolio strategy | Level 4-5 |

**Focus**:
- Strategic oversight over tactical execution
- Building organizational capability
- Client relationship and business development
- Thought leadership in domain

---

## 🔧 Skill Gap Analysis Framework

### How to Identify Skill Gaps

**Step 1: Define Required Skills**
- List all skills needed for the project
- Specify minimum proficiency levels
- Identify critical vs. nice-to-have skills

**Step 2: Assess Current Team**
- Inventory skills on proposed pod
- Rate proficiency levels honestly (not aspirational)
- Identify overlaps and unique capabilities

**Step 3: Calculate Gaps**
- **Critical Gap**: Required skill missing or below minimum proficiency
- **Moderate Gap**: Skill present but not at optimal level
- **Surplus**: More capability than needed (good for mentoring)

**Step 4: Prioritize Gaps**
- **Priority 1**: Critical gaps that block delivery (must close)
- **Priority 2**: Moderate gaps that slow delivery (should close)
- **Priority 3**: Nice-to-have gaps (accept or defer)

---

### Gap Closure Strategies

**Strategy 1: Hire/Contract**
- **When**: Critical skill, long timeline, no internal capacity
- **Timeline**: 4-12 weeks (recruiting + onboarding)
- **Cost**: High (full role cost + ramp-up time)
- **Best For**: Long-term need, specialized expertise

**Strategy 2: Train Existing Team**
- **When**: Moderate gap, team has capacity to learn
- **Timeline**: 2-8 weeks (training + practice)
- **Cost**: Medium (training costs + reduced velocity during learning)
- **Best For**: Skills adjacent to existing capabilities

**Strategy 3: Partner/Consultant**
- **When**: Short-term need, deep expertise required quickly
- **Timeline**: 1-2 weeks (engagement)
- **Cost**: High (premium rates) but time-boxed
- **Best For**: Short bursts, knowledge transfer, specialized work

**Strategy 4: Reduce Scope**
- **When**: Gap too large, timeline/budget too constrained
- **Timeline**: Immediate
- **Cost**: Opportunity cost (features deferred)
- **Best For**: When other options infeasible

**Strategy 5: Accept Risk**
- **When**: Gap is moderate, team can learn on the job
- **Timeline**: Throughout project (continuous learning)
- **Cost**: Low-medium (some rework, slower velocity)
- **Best For**: Acceptable risk, development opportunity for team

---

### Gap Analysis Template

**Project**: [Project Name]  
**Required Skills**: [List from requirements/architecture]  
**Proposed Pod**: [Team composition]

| Skill | Required Level | Current Level | Gap | Priority | Closure Strategy | Timeline | Cost |
|-------|----------------|---------------|-----|----------|------------------|----------|------|
| React (advanced) | 4 | 3 | -1 | P2 | Train L3 developer | 3 weeks | $5K training |
| Azure Functions | 3 | 0 | -3 | P1 | Hire L3 cloud engineer | 8 weeks | $120K annual |
| PostgreSQL optimization | 4 | 2 | -2 | P2 | Partner consultant | 2 weeks | $20K |
| Healthcare domain (HIPAA) | 3 | 1 | -2 | P1 | Train + consultant oversight | 4 weeks | $30K |

**Summary**:
- **Critical Gaps (P1)**: 2 (Azure Functions, HIPAA knowledge)
- **Moderate Gaps (P2)**: 2 (Advanced React, PostgreSQL)
- **Total Closure Cost**: $175K
- **Total Closure Timeline**: 8 weeks (limited by hiring)

**Recommendation**:
- Proceed with hiring cloud engineer (can't close P1 gap otherwise)
- Bring in HIPAA consultant for training + oversight
- Accept moderate gaps with mitigation (senior dev learns React advanced features, PostgreSQL consultant on-call)

---

## 🔧 T-Shaped vs π-Shaped Skill Development

### T-Shaped Professional

**Definition**: Deep expertise in one area, broad competence across related areas

**Visual**:
```
Broad Skills (Level 2-3)
━━━━━━━━━━━━━━━━━━━━━━━━━━
        ┃
   Deep ┃ Level 4-5
  Skill ┃
        ┃
        ┃
```

**Example 1: T-Shaped Frontend Developer (L3)**
- **Depth**: React (Level 5) - Expert in React, Hooks, Context, performance optimization
- **Breadth**: 
  - JavaScript/TypeScript (Level 4)
  - HTML/CSS (Level 3)
  - Node.js (Level 3)
  - Git (Level 3)
  - Testing (Jest, Cypress) (Level 3)
  - Design principles (Level 2)
  - Backend APIs (Level 2)

**Value**: Can solve most frontend problems independently, collaborate effectively with backend/design

---

### π-Shaped Professional

**Definition**: Deep expertise in TWO areas, broad competence across domain

**Visual**:
```
Broad Skills (Level 2-3)
━━━━━━━━━━━━━━━━━━━━━━━━━━
    ┃           ┃
Deep┃      Deep ┃ Level 4-5
    ┃           ┃
    ┃           ┃
```

**Example 1: π-Shaped Full-Stack Lead (L4)**
- **Depth 1**: React/Frontend (Level 5)
- **Depth 2**: .NET Core/Backend (Level 5)
- **Breadth**:
  - Azure (Level 4)
  - SQL/PostgreSQL (Level 3)
  - DevOps/CI-CD (Level 3)
  - Security (Level 3)
  - Architecture (Level 4)
  - Leadership (Level 4)

**Value**: Can lead full-stack teams, bridge frontend/backend, make informed architecture decisions

**Example 2: π-Shaped Cloud Architect (L5)**
- **Depth 1**: Azure Architecture (Level 5)
- **Depth 2**: Security & Compliance (Level 5)
- **Breadth**:
  - AWS (Level 3)
  - Networking (Level 4)
  - Cost optimization (Level 4)
  - DevOps (Level 3)
  - Enterprise architecture (Level 4)

---

### Comb-Shaped Professional

**Definition**: Multiple areas of moderate-to-deep expertise, very broad competence

**Visual**:
```
Broad Skills (Level 2-3)
━━━━━━━━━━━━━━━━━━━━━━━━━━
  ┃    ┃    ┃    ┃    ┃
  ┃    ┃    ┃    ┃    ┃  Level 3-4
  ┃    ┃    ┃    ┃    ┃  (Multiple)
```

**Example: Comb-Shaped Program Manager (L6)**
- **Multiple Depths (Level 3-4)**:
  - Program management
  - Cloud architecture
  - Agile/Lean practices
  - Financial management
  - Change management
  - Stakeholder management
- **Broad Competence (Level 2-3)**:
  - Various technologies
  - Industry domains
  - Business functions

**Value**: Can lead complex programs, connect across domains, strategic decision-making

---

### Development Paths

**L1 → L2: Building the T**
- Year 1: Focus on one technology (e.g., React) - reach Level 3
- Year 2: Broaden horizontally (learn backend, testing, DevOps basics) - reach Level 2-3
- Outcome: Competent in primary skill, collaborative across stack

**L2 → L3: Deepening the T**
- Years 3-4: Deepen primary skill to Level 4-5 (expert)
- Years 3-4: Selectively deepen complementary skills to Level 3
- Outcome: Expert in one area, strong competence in related areas

**L3 → L4: Adding Second Pillar (π)**
- Years 5-6: Identify second area of depth
- Years 5-6: Develop second area to Level 4-5
- Years 5-6: Broaden leadership skills (communication, mentoring)
- Outcome: Expert in two areas, can lead teams

**L4 → L5/L6: Broadening to Comb**
- Years 7-10: Add 2-3 more areas of moderate depth (Level 3-4)
- Years 7-10: Develop strategic and business skills
- Years 7-10: Build organizational influence
- Outcome: Strategic leader with deep expertise and broad competence

---

## Project-Skill Mapping

### By Project Type

#### Web Application Development

**Critical Skills** (Must have Level 3+):
- Frontend framework (React, Angular, or Vue)
- Backend language/framework
- RESTful API design
- SQL database
- Git/version control
- Agile practices

**Important Skills** (Should have Level 2+):
- Authentication/authorization
- Testing (unit, integration)
- DevOps/CI-CD basics
- Cloud deployment
- Security fundamentals

**Nice-to-Have Skills**:
- Advanced performance optimization
- Accessibility (WCAG)
- Design systems
- Progressive Web Apps

---

#### Cloud Migration

**Critical Skills** (Must have Level 3+):
- Target cloud platform (Azure, AWS, GCP)
- Infrastructure as Code
- Networking (VNets, load balancers)
- Migration patterns (lift-and-shift, refactor)
- Legacy system knowledge

**Important Skills** (Should have Level 2+):
- Security (IAM, encryption)
- Cost optimization
- Monitoring and logging
- Database migration
- Disaster recovery

**Nice-to-Have Skills**:
- Multi-cloud experience
- FinOps certification
- Compliance frameworks (HIPAA, PCI)

---

#### Data Platform / Analytics

**Critical Skills** (Must have Level 3+):
- SQL (advanced queries, optimization)
- ETL/ELT tools
- Data modeling
- One or more: Python, Spark, SQL Server, Snowflake
- Data warehousing concepts

**Important Skills** (Should have Level 2+):
- Data quality frameworks
- Data governance
- Cloud data services (Synapse, Redshift, BigQuery)
- BI tools (Power BI, Tableau)
- Performance tuning

**Nice-to-Have Skills**:
- Machine learning basics
- Real-time streaming (Kafka, Event Hubs)
- Data science (statistics, Python/R)

---

#### Legacy Modernization

**Critical Skills** (Must have Level 3+):
- Legacy technology (COBOL, AS/400, mainframe, etc.)
- Target modern stack
- Migration/refactoring strategies
- Integration patterns
- Risk management

**Important Skills** (Should have Level 2+):
- Business process analysis
- Change management
- Testing (regression especially)
- Incremental migration patterns
- Dual-run strategies

**Nice-to-Have Skills**:
- Automated code conversion tools
- Domain-driven design
- Strangler fig pattern expertise

---

## 🎯 Customization Quick Start

**To Adapt Skill Matrix to Your Organization**:

1. **Update Skill Categories** (45 minutes):
   - Replace example skills with your tech stack
   - Add domain-specific skills for your industry
   - Remove irrelevant technologies

2. **Calibrate Proficiency Levels** (30 minutes):
   - Adjust Level 3/4/5 definitions to your expectations
   - Provide specific examples from your context
   - Set standards based on your team's current capabilities

3. **Define Role Profiles** (1 hour):
   - Update role titles if different
   - Adjust expected skills per role for your context
   - Set realistic proficiency targets based on your talent market

4. **Create Project-Type Mappings** (45 minutes):
   - List your common project types
   - Define critical/important/nice-to-have skills for each
   - Reference actual past projects

5. **Build Assessment Process** (30 minutes):
   - Define how you assess skills (self-assessment, peer review, testing)
   - Create scoring rubrics for key skills
   - Establish review cadence (quarterly, annually)

6. **Import Your Team Data** (1-2 hours):
   - Survey current team skills
   - Build skill inventory
   - Identify existing gaps and strengths

**Test Your Configuration**:
- Take a recent project and do gap analysis
- Verify that skill requirements match reality
- Check that proficiency levels feel accurate
- Validate closure strategies would have worked

**Total Customization Time**: ~4-5 hours for complete adaptation

---

## Usage by Agents

### Resource Planner Agent

**Uses**:
- Validate team has required skills for project
- Identify skill gaps in proposed pods
- Recommend training or hiring
- Design balanced skill mixes

**How**:
1. Load project requirements (technical skills needed)
2. Load proposed pod composition
3. Reference skill-matrix_context.md for expected proficiency by role
4. Calculate gaps between required and available
5. Recommend closure strategies with timeline/cost

### Cost Estimator Agent

**Uses**:
- Understand when specialty skills justify premium rates
- Factor training costs into estimates
- Account for reduced velocity during skill development

**How**:
1. Reference skill requirements in estimation
2. Apply specialty premiums from rate-card when relevant
3. Include training costs if skill gaps identified
4. Adjust productivity assumptions for learning curves

---

**End of skill-matrix_context.md**