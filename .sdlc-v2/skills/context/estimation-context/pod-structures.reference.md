# Pod Structures Reference

## Overview

Pod-based staffing provides predictable capacity and clear accountability.
Each pod is a self-contained team with the skills to deliver end-to-end.

---

## Staffing Levels

### Level Definitions

| Level | Title | Typical Experience | Key Responsibilities |
|-------|-------|-------------------|---------------------|
| **L1** | Staff Consultant | 0-2 years | Task execution, learning, mentored work |
| **L2** | Consultant | 2-4 years | Autonomous task delivery, some mentoring |
| **L3** | Senior Consultant | 4-7 years | Leads work streams, technical decisions |
| **L4** | Manager | 7-10 years | Client-facing, team leadership, architecture |
| **L5** | Senior Manager | 10-15 years | Multiple workstreams, program delivery |
| **L6** | Director | 15+ years | Program oversight, client relationships |
| **L7** | Senior Director | 15+ years | Portfolio management, strategic direction |
| **L8** | Managing Director | 20+ years | Engagement leadership, executive relationships |

### Productive Hours by Level

Higher levels have reduced billable capacity due to leadership responsibilities.

| Level | Weekly Productive Hours | Annual Capacity | Admin/Leadership % |
|-------|------------------------|-----------------|-------------------|
| L1-L2 (Staff) | 32-36 hrs | 1,800 hrs | 10-20% |
| L3 (Senior) | 30-34 hrs | 1,850 hrs | 15-25% |
| L4 (Manager) | 26-32 hrs | 1,600 hrs | 20-35% |
| L5 (Senior Manager) | 22-28 hrs | 1,400 hrs | 30-45% |
| L6 (Director) | 18-24 hrs | 1,200 hrs | 40-55% |
| L7 (Senior Director) | 14-20 hrs | 1,000 hrs | 50-65% |
| L8 (Managing Director) | 10-16 hrs | 800 hrs | 60-75% |

**Note**: Productive hours = time directly contributing to deliverables.
Non-productive time includes: meetings, admin, BD, mentoring, training.

---

## Standard Pod Models

### Core Delivery Pod (6-8 people)

**Purpose**: Feature development, end-to-end ownership

**Composition**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Tech Lead | L4 Manager | 1 | 75-100% |
| Senior Developers | L3 Senior | 2 | 100% |
| Developers | L1-L2 Staff | 3-4 | 100% |
| QA Engineer | L2-L3 | 1 | 100% |

**Capacity**: 200-240 productive hours/week

**Typical Work**:
- User story implementation
- Component development
- Unit and integration testing
- Code reviews

**Best For**: Standard feature development, maintenance, enhancements

---

### Architecture Pod (3-4 people)

**Purpose**: Technical design, standards, cross-cutting concerns

**Composition**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Lead Architect | L5 Senior Manager | 1 | 50-75% |
| Solution Architects | L4 Manager | 1-2 | 75-100% |
| Senior Developer | L3 Senior | 1 | 100% |

**Capacity**: 90-120 productive hours/week

**Typical Work**:
- Architecture decisions (ADRs)
- Technical POCs and spikes
- Design reviews
- Standards and patterns
- Cross-cutting concerns (security, performance)

**Best For**: Phase 1 design, complex technical decisions, governance

---

### Platform/DevOps Pod (3-5 people)

**Purpose**: Infrastructure, CI/CD, platform services

**Composition**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Platform Lead | L4 Manager | 1 | 75-100% |
| DevOps Engineers | L3 Senior | 1-2 | 100% |
| Cloud Engineers | L2-L3 | 1-2 | 100% |

**Capacity**: 100-150 productive hours/week

**Typical Work**:
- CI/CD pipeline development
- Infrastructure as Code
- Environment management
- Monitoring and observability
- Security tooling

**Best For**: Platform establishment, DevOps maturity, cloud migration

---

### Integration Pod (4-6 people)

**Purpose**: System integrations, APIs, data pipelines

**Composition**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Integration Lead | L4-L5 | 1 | 75-100% |
| Integration Developers | L3 Senior | 2-3 | 100% |
| Data Engineers | L2-L3 | 1-2 | 100% |

**Capacity**: 130-180 productive hours/week

**Typical Work**:
- API development and integration
- Data transformation
- Legacy system interfaces
- Event-driven architecture
- Integration testing

**Best For**: Complex integrations, legacy modernization, data migration

---

### Specialty Pod (3-5 people)

**Purpose**: Domain-specific expertise (AI/ML, Security, etc.)

**Composition**: Varies by specialty

**AI/ML Example**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| ML Lead | L5 Senior Manager | 1 | 50-75% |
| Data Scientists | L3-L4 | 1-2 | 100% |
| ML Engineers | L3 | 1-2 | 100% |

**Security Example**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Security Architect | L5 | 1 | 50% |
| Security Engineers | L3-L4 | 2 | 100% |
| Penetration Tester | L3 | 1 | 50-100% |

**Capacity**: 80-150 productive hours/week (varies by specialty)

---

### Leadership Pod (2-4 people)

**Purpose**: Program management, stakeholder engagement, governance

**Composition**:
| Role | Level | Count | Allocation |
|------|-------|-------|------------|
| Engagement Lead | L7-L8 MD | 1 | 25-50% |
| Program Manager | L5-L6 Director | 1 | 75-100% |
| Delivery Manager | L4-L5 | 1 | 100% |
| Scrum Master | L3-L4 | 0-1 | 100% |

**Capacity**: 60-100 productive hours/week

**Typical Work**:
- Stakeholder management
- Risk and issue management
- Status reporting
- Resource coordination
- Governance and escalation

**Best For**: Large programs, multiple delivery pods, executive visibility

---

## Pod Capacity Calculation

### Formula

```
Weekly Capacity = Σ (Person × Productive Hrs × Allocation × Utilization)
```

**Where**:
- Productive Hrs = Weekly hours by level (see table above)
- Allocation = % dedicated to this pod
- Utilization = 0.75-0.85 (accounts for PTO, meetings, overhead)

### Example: Core Delivery Pod

```
Team:
- 1 Tech Lead (L4): 30 hrs × 1.0 × 0.80 = 24 hrs
- 2 Senior Devs (L3): 32 hrs × 1.0 × 0.80 = 51 hrs
- 3 Developers (L2): 34 hrs × 1.0 × 0.80 = 82 hrs
- 1 QA (L3): 32 hrs × 1.0 × 0.80 = 26 hrs

Weekly Capacity: 183 hrs/week

Sprint Capacity (2 weeks): 366 hrs
Monthly Capacity (4 weeks): 732 hrs
```

### Capacity Planning Table

| Pod Type | Size | Weekly Hrs | Sprint Hrs | Monthly Hrs |
|----------|------|------------|------------|-------------|
| Core Delivery | 6-8 | 180-220 | 360-440 | 720-880 |
| Architecture | 3-4 | 90-120 | 180-240 | 360-480 |
| Platform/DevOps | 3-5 | 100-150 | 200-300 | 400-600 |
| Integration | 4-6 | 130-180 | 260-360 | 520-720 |
| Specialty | 3-5 | 80-150 | 160-300 | 320-600 |
| Leadership | 2-4 | 60-100 | 120-200 | 240-400 |

---

## Pod Sizing Guidelines

### Sizing by Project Scale

| Project Size | Duration | Total Effort | Recommended Pods |
|--------------|----------|--------------|------------------|
| Small | 2-3 months | 2,000-4,000 hrs | 1 Core + partial Leadership |
| Medium | 4-6 months | 5,000-10,000 hrs | 2 Core + Architecture + Leadership |
| Large | 6-12 months | 15,000-30,000 hrs | 3-4 Core + Arch + Platform + Leadership |
| Enterprise | 12+ months | 40,000+ hrs | 5+ Core + multiple specialty + full Leadership |

### Pod-to-Hour Conversion

For ROM estimation, use these benchmarks:

| Pod Type | Monthly Output (hrs) | 6-Month Output |
|----------|---------------------|----------------|
| Core Delivery | 700-800 hrs | 4,200-4,800 hrs |
| Architecture | 350-450 hrs | 2,100-2,700 hrs |
| Platform | 450-550 hrs | 2,700-3,300 hrs |

---

## Staffing Mix Guidelines

### By Work Complexity

| Complexity | Staff (L1-L2) | Senior (L3) | Manager+ (L4+) |
|------------|---------------|-------------|----------------|
| Low (CRUD, standard) | 50% | 35% | 15% |
| Medium (Integration) | 35% | 40% | 25% |
| High (Architecture) | 20% | 40% | 40% |
| Very High (Innovation) | 10% | 35% | 55% |

### By Project Phase

| Phase | Staff | Senior | Manager+ | Notes |
|-------|-------|--------|----------|-------|
| Phase 0 (Discovery) | 0% | 30% | 70% | Senior-heavy for analysis |
| Phase 1 (Design) | 10% | 40% | 50% | Architecture focus |
| Phase 2 (Planning) | 20% | 40% | 40% | Mixed for planning |
| Phase 3 (Build) | 45% | 35% | 20% | Execution-heavy |
| Phase 4+ (Stabilize) | 40% | 40% | 20% | Testing and fixes |

---

## Pod Health Indicators

### Healthy Pod Signs

- Utilization: 75-85%
- Sprint velocity: stable ±15%
- Defect rate: decreasing
- Team retention: >90%
- Knowledge distribution: no single points of failure

### Warning Signs

- Utilization > 90%: Burnout risk
- Utilization < 70%: Underutilized, cost concern
- Single expert dependency: Knowledge risk
- High turnover: Continuity risk
- Velocity variance > 30%: Estimation issues

---

## Quick Reference

### Pod Selection Guide

| Need | Primary Pod | Support Pods |
|------|-------------|--------------|
| Feature development | Core Delivery | - |
| System design | Architecture | Core Delivery |
| Infrastructure | Platform | Core Delivery |
| Legacy integration | Integration | Architecture |
| AI/ML capabilities | Specialty (ML) | Core Delivery |
| Program governance | Leadership | All others |

### Capacity Quick Calc

```
Rough Monthly Hours = Team Size × 120

Example: 6-person pod ≈ 720 hrs/month
```
