# Pod Templates Context

**Purpose**: Defines standard team structures (pods) for different project types, sizes, and phases.

**Last Updated**: 2025-11-07  
**Owner**: Delivery Excellence / Resource Management  
**Review Cycle**: Quarterly

---

## 🔧 CONFIGURATION GUIDE

This file defines **standard team structures** for your organization. Customize:

1. **Pod Definitions** - Standard team compositions by project type
2. **Sizing Guidelines** - How to scale pods based on project characteristics
3. **Role Definitions** - What each role does within a pod
4. **Staffing Ratios** - Level mix and capacity allocation
5. **Specialty Roles** - When to add architects, security experts, etc.

**Resource Planner agent references this file** when designing team structures.

---

## Pod Design Philosophy

### Core Principles

**1. Autonomous Teams**
- Pods are self-sufficient delivery units
- Contain all skills needed to deliver value
- Minimize external dependencies
- Own their work end-to-end

**2. Right-Sized for Context**
- Small pods (3-5) for simple projects
- Medium pods (6-10) for standard delivery
- Large pods (10-15) for complex programs
- Pod networks (15+) for enterprise transformations

**3. Balanced Skill Mix**
- Senior leadership for direction
- Mid-level talent for execution
- Junior members for capacity and growth
- Specialists when needed

**4. Sustainable Staffing**
- Account for admin overhead (20-40% at senior levels)
- Plan for ramp-up time (1-4 weeks)
- Include buffer for attrition (5-10% annual)
- Avoid 100% utilization (target 70-85%)

**5. Scalable Design**
- Pods can grow/shrink over project lifecycle
- Multiple pods can work in parallel
- Clear handoff between pods
- Standard interfaces for coordination

---

## 🔧 Pod Types by Purpose

### 1. Delivery Pod (Most Common)

**Purpose**: Core feature development and delivery

**Typical Composition** (8-person pod):

| Role | Level | Count | Allocation | Primary Responsibilities |
|------|-------|-------|------------|-------------------------|
| **Delivery Lead** | L5-L6 | 0.5 | 20 hrs/week | Direction, client engagement, escalations |
| **Technical Lead** | L4-L5 | 1 | 40 hrs/week | Architecture decisions, code review, mentoring |
| **Senior Developers** | L3 | 2 | 80 hrs/week | Complex features, design, mentoring |
| **Mid Developers** | L2 | 3 | 120 hrs/week | Feature development, testing, documentation |
| **Junior Developers** | L1 | 1-2 | 40-80 hrs/week | Support features, testing, learning |

**Total Capacity**: 280-320 hrs/week (7-8 FTE equivalent)

**When to Use**:
- Standard application development
- Defined requirements with moderate complexity
- 3-18 month timeline projects
- Budget range: $500K-$5M

**Pod Characteristics**:
- 70% execution (L1-L3)
- 25% leadership (L4-L5)
- 5% oversight (L5-L6)
- Autonomy: High
- Specialization: Generalist T-shaped skills

---

### 2. Architecture Pod

**Purpose**: System design, technical strategy, complex problem-solving

**Typical Composition** (5-person pod):

| Role | Level | Count | Allocation | Primary Responsibilities |
|------|-------|-------|------------|-------------------------|
| **Chief Architect** | L6-L7 | 0.25 | 10 hrs/week | Strategic direction, executive briefings |
| **Lead Architect** | L5-L6 | 1 | 40 hrs/week | Architecture design, ADRs, technical leadership |
| **Senior Architects** | L4-L5 | 2 | 80 hrs/week | Detailed design, spike solutions, reviews |
| **Solution Designers** | L3-L4 | 1-2 | 40-80 hrs/week | Component design, prototyping, documentation |

**Total Capacity**: 170-210 hrs/week (4.25-5.25 FTE equivalent)

**When to Use**:
- Complex system design required
- Multiple integration points
- Technology selection/evaluation
- Legacy modernization planning
- High technical risk projects

**Pod Characteristics**:
- 20% strategy (L6-L7)
- 60% design (L4-L5)
- 20% execution (L3-L4)
- Autonomy: Very High
- Specialization: Deep technical expertise

---

### 3. Support Pod

**Purpose**: Operations, maintenance, bug fixes, user support

**Typical Composition** (6-person pod):

| Role | Level | Count | Allocation | Primary Responsibilities |
|------|-------|-------|------------|-------------------------|
| **Support Manager** | L4-L5 | 0.5 | 20 hrs/week | Triage, escalations, process improvement |
| **Senior Support Engineers** | L3 | 1-2 | 40-80 hrs/week | Complex issues, knowledge base, training |
| **Support Engineers** | L2 | 2-3 | 80-120 hrs/week | Ticket resolution, user assistance, documentation |
| **Junior Support Engineers** | L1 | 1-2 | 40-80 hrs/week | Basic tickets, monitoring, learning |

**Total Capacity**: 180-300 hrs/week (4.5-7.5 FTE equivalent)

**When to Use**:
- Production systems requiring ongoing support
- Post-go-live stabilization
- Steady-state maintenance
- User training and adoption

**Pod Characteristics**:
- 10% management (L4-L5)
- 30% expertise (L3)
- 60% capacity (L1-L2)
- Autonomy: Medium
- Specialization: Product/system knowledge

---

### 4. Specialty Pod (Cloud, Data, Security, etc.)

**Purpose**: Deep expertise in specific domain for complex initiatives

**Typical Composition** (4-6 person pod):

| Role | Level | Count | Allocation | Primary Responsibilities |
|------|-------|-------|------------|-------------------------|
| **Practice Lead** | L6-L7 | 0.25 | 10 hrs/week | Strategic guidance, standards, escalations |
| **Principal Specialist** | L5-L6 | 1 | 40 hrs/week | Deep expertise, design, best practices |
| **Senior Specialists** | L4 | 1-2 | 40-80 hrs/week | Implementation, mentoring, documentation |
| **Specialists** | L3 | 1-2 | 40-80 hrs/week | Configuration, automation, support |

**Total Capacity**: 130-210 hrs/week (3.25-5.25 FTE equivalent)

**When to Use**:
- Cloud migration/modernization
- Data platform implementation
- Security/compliance programs
- DevOps/SRE transformation
- AI/ML initiatives

**Pod Characteristics**:
- 5% strategy (L6-L7)
- 40% leadership (L5-L6)
- 55% execution (L3-L4)
- Autonomy: High
- Specialization: Domain expert (π-shaped)

---

### 5. Program Management Pod

**Purpose**: Coordination, governance, stakeholder management for large programs

**Typical Composition** (4-5 person pod):

| Role | Level | Count | Allocation | Primary Responsibilities |
|------|-------|-------|------------|-------------------------|
| **Program Director** | L7-L8 | 0.25 | 10 hrs/week | Executive engagement, strategy, escalations |
| **Program Manager** | L5-L6 | 1 | 40 hrs/week | Overall coordination, risk management, reporting |
| **Workstream Managers** | L4-L5 | 2-3 | 80-120 hrs/week | Workstream delivery, dependency management |
| **PMO Coordinator** | L2-L3 | 1 | 40 hrs/week | Tracking, reporting, documentation, tooling |

**Total Capacity**: 170-210 hrs/week (4.25-5.25 FTE equivalent)

**When to Use**:
- Multi-workstream programs (>3 delivery pods)
- Budget >$5M or duration >12 months
- Multiple stakeholder groups
- High organizational complexity
- Cross-functional dependencies

**Pod Characteristics**:
- 5% executive (L7-L8)
- 60% management (L5-L6)
- 35% coordination (L2-L4)
- Autonomy: Low (orchestration role)
- Specialization: Program management expertise

---

## 🔧 Pod Sizing Guidelines

### By Project Size (Total Budget)

| Budget Range | Recommended Pod Mix | Total Team Size | Typical Duration |
|--------------|---------------------|-----------------|------------------|
| **<$250K** | 1 small delivery pod | 3-5 people | 2-6 months |
| **$250K-$1M** | 1 standard delivery pod | 6-10 people | 6-12 months |
| **$1M-$3M** | 1 delivery + 0.5 architecture | 8-12 people | 9-18 months |
| **$3M-$5M** | 2 delivery + architecture + PMO | 15-20 people | 12-24 months |
| **$5M-$10M** | 3-4 pods + full PMO | 25-35 people | 18-36 months |
| **>$10M** | Multiple pod networks | 40+ people | 24-60 months |

**Adjustment Factors**:
- **High Complexity**: +20-30% team size
- **Low Team Experience**: +15-25% for mentoring overhead
- **Distributed Team**: +10-15% for coordination overhead
- **Regulatory Requirements**: +10-20% for compliance activities
- **Legacy Systems**: +15-30% for integration complexity

---

### By Project Complexity

#### Simple Projects
**Characteristics**: Well-defined scope, standard tech stack, minimal integration

**Pod Recommendation**: Small Delivery Pod (3-5 people)
- 1 × L4-L5 (Lead) @ 50% = 20 hrs/week
- 2-3 × L2-L3 (Developers) @ 100% = 80-120 hrs/week
- 1 × L1 (Junior) @ 50-100% = 20-40 hrs/week

**Total**: 120-180 hrs/week (3-4.5 FTE)

---

#### Moderate Projects
**Characteristics**: Clear scope, some unknowns, moderate integration, standard tech

**Pod Recommendation**: Standard Delivery Pod (6-10 people)
- 0.5 × L5-L6 (Delivery Lead) @ 50% = 20 hrs/week
- 1 × L4-L5 (Tech Lead) @ 100% = 40 hrs/week
- 2-3 × L3 (Senior Devs) @ 100% = 80-120 hrs/week
- 2-4 × L2 (Mid Devs) @ 100% = 80-160 hrs/week
- 1-2 × L1 (Junior Devs) @ 100% = 40-80 hrs/week

**Total**: 260-420 hrs/week (6.5-10.5 FTE)

---

#### Complex Projects
**Characteristics**: Significant unknowns, multiple integrations, new tech, high risk

**Pod Recommendation**: Multi-Pod Structure
- 1 × Architecture Pod (5 people) @ 100%
- 2 × Delivery Pods (16 people total) @ 100%
- 0.5 × PMO Pod (2-3 people) @ 50-100%

**Total**: 23-24 people (920-960 hrs/week)

**Pod Allocation**:
- Architecture Pod: 30% discovery/design, 40% spikes, 30% support
- Delivery Pod 1: Core platform features
- Delivery Pod 2: User-facing features
- PMO: Coordination, risk, reporting

---

#### Enterprise Transformation
**Characteristics**: Multiple systems, org change, compliance, phased rollout

**Pod Recommendation**: Program-Level Structure
- 1 × Program Management Pod (5 people)
- 1-2 × Architecture Pods (5-10 people)
- 3-5 × Delivery Pods (24-40 people)
- 1-2 × Specialty Pods (4-8 people)
- 1 × Support Pod (6 people) - for existing systems

**Total**: 44-69 people (1,760-2,760 hrs/week)

---

## 🔧 Role Definitions

### Delivery Roles

**Staff Consultant (L1)**
- **Years Experience**: 0-2 years
- **Primary Activities**: Task execution, learning, documentation
- **Autonomy**: Low (requires daily oversight)
- **Typical Allocation**: 
  - 70% hands-on work (coding, testing, config)
  - 20% learning and ramp-up
  - 10% meetings and collaboration
- **Capacity Factor**: 60-70% effective (learning curve)
- **Mentoring Need**: High (4-8 hrs/week from senior)

**Consultant (L2)**
- **Years Experience**: 2-5 years
- **Primary Activities**: Feature development, testing, peer review
- **Autonomy**: Medium (weekly oversight)
- **Typical Allocation**:
  - 75% hands-on delivery
  - 10% design and problem-solving
  - 10% mentoring juniors
  - 5% meetings
- **Capacity Factor**: 75-85% effective
- **Mentoring Need**: Medium (2-4 hrs/week from senior)

**Senior Consultant (L3)**
- **Years Experience**: 5-8 years
- **Primary Activities**: Complex features, design, mentoring, code review
- **Autonomy**: High (bi-weekly check-ins)
- **Typical Allocation**:
  - 60% hands-on delivery
  - 20% design and architecture
  - 15% mentoring and code review
  - 5% meetings
- **Capacity Factor**: 80-90% effective
- **Mentoring Capacity**: Can mentor 2-3 junior/mid developers

---

### Leadership Roles

**Manager (L4)**
- **Years Experience**: 8-12 years
- **Primary Activities**: Workstream leadership, client engagement, technical decisions
- **Autonomy**: Very High (monthly reviews)
- **Typical Allocation**:
  - 40% technical work (architecture, complex features)
  - 30% team leadership and mentoring
  - 20% client/stakeholder engagement
  - 10% admin and reporting
- **Capacity Factor**: 70-80% effective (context switching)
- **Team Capacity**: Can lead 4-6 people directly

**Senior Manager (L5)**
- **Years Experience**: 12-15 years
- **Primary Activities**: Delivery management, risk mitigation, program coordination
- **Autonomy**: Full (escalation only)
- **Typical Allocation**:
  - 30% strategic technical oversight
  - 30% team management and development
  - 30% client relationship and escalations
  - 10% internal initiatives
- **Capacity Factor**: 60-70% effective (high admin overhead)
- **Team Capacity**: Can manage 2-3 workstreams (10-15 people)

**Director (L6)**
- **Years Experience**: 15-20 years
- **Primary Activities**: Program leadership, strategy, business development
- **Autonomy**: Full (self-directed)
- **Typical Allocation**:
  - 40% program oversight and governance
  - 30% client executive engagement
  - 20% people and practice development
  - 10% business development
- **Capacity Factor**: 50-60% effective (high meeting load)
- **Team Capacity**: Can oversee 3-5 workstreams (20-40 people)

---

### Specialty Roles

**Cloud Architect (L4-L6)**
- **When Needed**: Cloud migration, modernization, cloud-native development
- **Allocation**: 25-100% depending on cloud complexity
- **Works With**: Architecture pod or embedded in delivery pod
- **Key Deliverables**: Cloud architecture, landing zone design, cost optimization

**Security Engineer (L3-L5)**
- **When Needed**: Compliance requirements (HIPAA, PCI, SOC2), high-security systems
- **Allocation**: 10-50% depending on security posture
- **Works With**: Architecture pod, security reviews across delivery pods
- **Key Deliverables**: Threat models, security architecture, compliance documentation

**Data Engineer (L3-L5)**
- **When Needed**: Data migration, analytics platforms, ML/AI implementations
- **Allocation**: 25-100% depending on data complexity
- **Works With**: Specialty pod or embedded in delivery pod
- **Key Deliverables**: Data architecture, ETL pipelines, data quality frameworks

**DevOps/SRE Engineer (L3-L5)**
- **When Needed**: Infrastructure automation, CI/CD, production operations
- **Allocation**: 25-100% based on infrastructure complexity
- **Works With**: All delivery pods (shared service)
- **Key Deliverables**: CI/CD pipelines, infrastructure as code, monitoring/alerting

**UX/UI Designer (L2-L4)**
- **When Needed**: User-facing applications, complex workflows
- **Allocation**: 25-75% based on UX complexity
- **Works With**: Delivery pods (embedded or floating)
- **Key Deliverables**: Wireframes, prototypes, design system, user research

---

## 🔧 Staffing Level Ratios

### Recommended Mix by Pod Type

**Delivery Pod** (Balanced Execution)
- **L6+**: 5% (strategy, oversight)
- **L4-L5**: 25% (leadership, complex work)
- **L2-L3**: 50% (core execution)
- **L1**: 20% (capacity, growth)

**Architecture Pod** (Top-Heavy)
- **L6-L7**: 20% (strategic direction)
- **L4-L5**: 60% (design and leadership)
- **L2-L3**: 20% (execution support)
- **L1**: 0% (not typical)

**Support Pod** (Bottom-Heavy)
- **L4-L5**: 15% (management)
- **L3**: 25% (expertise)
- **L2**: 40% (execution)
- **L1**: 20% (capacity)

**Specialty Pod** (Expertise-Heavy)
- **L6+**: 10% (practice leadership)
- **L5**: 30% (deep expertise)
- **L4**: 35% (implementation)
- **L3**: 25% (execution)

---

### Cost Impact of Staff Mix

**Example: 10,000-hour project with different mixes**

| Mix Profile | L1% | L2% | L3% | L4% | L5% | L6% | Blended Rate | Total Cost |
|-------------|-----|-----|-----|-----|-----|-----|--------------|------------|
| **Junior-Heavy** | 30% | 40% | 20% | 8% | 2% | 0% | $185/hr | $1,850,000 |
| **Balanced** | 15% | 35% | 30% | 15% | 4% | 1% | $215/hr | $2,150,000 |
| **Senior-Heavy** | 5% | 20% | 35% | 25% | 10% | 5% | $260/hr | $2,600,000 |
| **Expert-Heavy** | 0% | 10% | 30% | 35% | 20% | 5% | $295/hr | $2,950,000 |

**Trade-offs**:
- **Junior-Heavy**: Lower cost, higher risk, slower velocity, more rework
- **Balanced**: Standard approach, predictable outcomes, manageable risk
- **Senior-Heavy**: Higher cost, faster velocity, lower risk, less mentoring capacity
- **Expert-Heavy**: Highest cost, fastest for complex work, minimal risk, no bench development

---

## 🔧 Pod Lifecycle Management

### Ramp-Up Phase (Weeks 1-4)

**Week 1: Onboarding**
- **Capacity**: 25% effective
- **Activities**: Access setup, tool training, codebase familiarization
- **Focus**: Administrative tasks, environment setup

**Week 2: Orientation**
- **Capacity**: 40% effective
- **Activities**: Architecture review, backlog review, process training
- **Focus**: Understanding, shadowing, pair programming

**Week 3: Integration**
- **Capacity**: 60% effective
- **Activities**: First small tasks, code reviews, ceremonies
- **Focus**: Contributing with support

**Week 4: Full Engagement**
- **Capacity**: 75-80% effective
- **Activities**: Normal workload, autonomy increasing
- **Focus**: Independent contributions

**Ramp-Up Adjustment for Estimates**:
- Month 1: Assume 50% average capacity for new team members
- Include ramp-up time in overall schedule
- Senior members ramp faster (2-3 weeks vs 4-6 weeks for juniors)

---

### Steady-State Operations (Months 2-N)

**Target Capacity by Level**:
- L1: 70% billable (high learning overhead)
- L2: 80% billable (standard productivity)
- L3: 85% billable (high productivity, some mentoring)
- L4: 75% billable (leadership overhead)
- L5: 65% billable (high admin/management overhead)
- L6+: 50% billable (strategic, oversight focus)

**Capacity Factors to Account For**:
- Meetings: 10-20% (higher for senior levels)
- Email/Slack: 5-10%
- Context switching: 10-15% (multiple active workstreams)
- Administrative: 5-15% (timesheets, expenses, reviews)
- Learning/growth: 5-10% (training, certifications)

**Recommended Utilization Targets**:
- **Sprint Capacity**: Plan to 70-75% of theoretical max
- **Annual Utilization**: Target 75-80% billable on average
- **Peak Periods**: Max 90% for short durations (2-4 weeks)
- **Recovery**: Build in 60-65% utilization after peak periods

---

### Ramp-Down Phase (Phased Transition)

**4 Weeks Before Transition**:
- Begin knowledge transfer documentation
- Identify critical knowledge holders
- Cross-train on key components
- **Capacity**: 90% effective (documentation overhead)

**2 Weeks Before Transition**:
- Intensive knowledge transfer sessions
- Shadowing/pair programming with successor team
- Document all tribal knowledge
- **Capacity**: 75% effective (training overhead)

**Final Week**:
- Handoff ceremonies
- Final questions and clarification
- Archive working materials
- **Capacity**: 50% effective (transition focus)

**Backfill Strategy**:
- Plan for 4-8 week overlap for critical roles (L4+)
- Junior roles can often transition with 2-week overlap
- Specialty roles may need 6-12 week knowledge transfer

---

## Pod Composition Templates

### Template 1: Small Web Application

**Project Characteristics**:
- Simple CRUD application
- Standard tech stack (React + Node + PostgreSQL)
- 3-6 month timeline
- $250K-$500K budget

**Pod Structure** (5 people):
```
Delivery Lead (L5) @ 25%         = 10 hrs/week
Tech Lead (L4) @ 100%            = 40 hrs/week
Senior Developer (L3) @ 100%     = 40 hrs/week
Developers (L2) × 2 @ 100%       = 80 hrs/week
--------------------------------
Total:                           170 hrs/week (4.25 FTE)
```

**Blended Rate**: ~$210/hr  
**Weekly Cost**: $35,700  
**16-Week Project**: ~$571,200 total

---

### Template 2: Cloud Migration

**Project Characteristics**:
- 50-application portfolio migration
- Azure cloud platform
- 12-18 month timeline
- $2M-$4M budget

**Pod Structure** (12 people):
```
Program Manager (L6) @ 25%       = 10 hrs/week
Cloud Architect (L5) @ 100%      = 40 hrs/week
Migration Lead (L5) @ 100%       = 40 hrs/week
Senior Cloud Engineers (L4) × 2  = 80 hrs/week
Cloud Engineers (L3) × 3         = 120 hrs/week
Junior Engineers (L2) × 2        = 80 hrs/week
DevOps Engineers (L3) × 2        = 80 hrs/week
--------------------------------
Total:                           450 hrs/week (11.25 FTE)
```

**Blended Rate**: ~$245/hr  
**Weekly Cost**: $110,250  
**52-Week Project**: ~$5,733,000 total (adjust to fit budget with scope)

---

### Template 3: Enterprise Platform Development

**Project Characteristics**:
- Multi-tenant SaaS platform
- Microservices architecture
- Complex integrations
- 18-24 month timeline
- $8M-$12M budget

**Pod Structure** (28 people):
```
Program Director (L7) @ 15%              = 6 hrs/week
Program Manager (L6) @ 100%              = 40 hrs/week

Architecture Pod:
  Chief Architect (L6) @ 50%             = 20 hrs/week
  Lead Architect (L5) @ 100%             = 40 hrs/week
  Senior Architects (L4) × 2             = 80 hrs/week

Delivery Pod 1 (Platform Core) - 8 people:
  Tech Lead (L5) @ 100%                  = 40 hrs/week
  Senior Devs (L3) × 2                   = 80 hrs/week
  Mid Devs (L2) × 4                      = 160 hrs/week
  Junior Dev (L1) × 1                    = 40 hrs/week

Delivery Pod 2 (Features) - 8 people:
  Tech Lead (L4) @ 100%                  = 40 hrs/week
  Senior Devs (L3) × 2                   = 80 hrs/week
  Mid Devs (L2) × 4                      = 160 hrs/week
  Junior Dev (L1) × 1                    = 40 hrs/week

DevOps Pod - 4 people:
  DevOps Lead (L4) @ 100%                = 40 hrs/week
  SRE Engineers (L3) × 3                 = 120 hrs/week

QA Pod - 4 people:
  QA Lead (L4) @ 100%                    = 40 hrs/week
  Test Engineers (L3) × 3                = 120 hrs/week
----------------------------------------
Total:                                   1,106 hrs/week (27.65 FTE)
```

**Blended Rate**: ~$235/hr  
**Weekly Cost**: $260,000  
**80-Week Project**: ~$20,800,000 total (over budget - requires scope reduction)

---

## 🔧 Pod Design Decision Tree

### Step 1: Determine Base Pod Type

**Question: What's the primary objective?**
- Feature development → Delivery Pod
- System design → Architecture Pod
- Production support → Support Pod
- Specialized capability → Specialty Pod
- Coordination → PMO Pod

### Step 2: Size the Pod

**Question: What's the project budget?**
- <$250K → Small (3-5 people)
- $250K-$1M → Standard (6-10 people)
- $1M-$5M → Large (10-15 people)
- >$5M → Multiple pods

### Step 3: Adjust for Complexity

**Question: How complex is the work?**
- Simple → Use base sizing
- Moderate → +20% capacity
- Complex → +30-50% capacity or add Architecture Pod
- Very Complex → Multi-pod structure

### Step 4: Add Specialty Roles

**Question: Are specialized skills needed?**
- Cloud migration → Add Cloud Architect
- Data-heavy → Add Data Engineer
- Compliance → Add Security Engineer
- Complex infrastructure → Add DevOps/SRE
- User-facing → Add UX/UI Designer

### Step 5: Validate Feasibility

**Checkpoints**:
- Does blended rate fit budget? (Budget / Hours = Max Rate)
- Can we source the required skills?
- Is the timeline realistic with this capacity?
- Do we have enough senior oversight? (Need 1 × L5+ per 8-10 people)

---

## Common Pod Anti-Patterns

### ❌ Anti-Pattern 1: All-Junior Team

**Problem**: No experienced leadership, high rework, slow velocity

**Example**:
```
Tech Lead (L3) @ 100%
Developers (L1-L2) × 6 @ 100%
```

**Why It Fails**:
- L3 can't provide sufficient mentoring for 6 juniors
- Architecture decisions suffer
- Quality issues compound
- Burnout of tech lead

**Fix**: Add L4-L5 leadership, reduce junior ratio to max 30%

---

### ❌ Anti-Pattern 2: Top-Heavy Structure

**Problem**: High cost, insufficient execution capacity

**Example**:
```
Director (L6) @ 50%
Senior Managers (L5) × 3 @ 100%
Developers (L2-L3) × 2 @ 100%
```

**Why It Fails**:
- Too much management, not enough execution
- High blended rate
- Frustrated seniors with no team to lead

**Fix**: Invert pyramid - 70% execution, 30% leadership

---

### ❌ Anti-Pattern 3: Lone Wolf Specialist

**Problem**: Single point of failure, no knowledge transfer

**Example**:
```
Cloud Architect (L5) @ 100% (only cloud person)
[Rest of team has no cloud skills]
```

**Why It Fails**:
- Bus factor of 1
- Bottleneck on all cloud decisions
- No redundancy if person leaves

**Fix**: Pair specialists (primary + secondary), or hire 2× at 50% each

---

### ❌ Anti-Pattern 4: 100% Utilization

**Problem**: No buffer, unsustainable, quality suffers

**Example**:
```
All team members @ 100% allocation
No slack for meetings, learning, or unexpected work
```

**Why It Fails**:
- Burnout inevitable
- No capacity for rework or bugs
- No time for knowledge sharing
- Team members feel overwhelmed

**Fix**: Plan to 70-75% capacity, build in slack time

---

## 🎯 Customization Quick Start

**To Adapt Pod Templates to Your Organization**:

1. **Update Pod Definitions** (30 minutes):
   - Adjust team sizes for your standard project types
   - Modify role titles to match your organization
   - Update level definitions if different

2. **Calibrate Ratios** (20 minutes):
   - Review your historical staffing mixes
   - Adjust recommended ratios based on your reality
   - Update capacity factors for your team's productivity

3. **Add Organization-Specific Pods** (30 minutes):
   - Create templates for your unique project types
   - Document specialty pods for your tech stack
   - Add any organizational constraints (union rules, geographic requirements)

4. **Import Real Pod Data** (1 hour):
   - Replace example compositions with actual past projects
   - Calculate actual blended rates from your teams
   - Document what worked and what didn't

5. **Validate with Delivery Leadership** (30 minutes):
   - Review templates with people who staff projects
   - Ensure ratios reflect reality
   - Get buy-in on recommended structures

**Test Your Configuration**:
- Take a recent project and map it to a template
- Calculate whether the pod structure would have worked
- Adjust templates based on learnings
- Validate blended rates match expectations

**Total Customization Time**: ~3 hours for complete adaptation

---

**End of pod-templates_context.md**