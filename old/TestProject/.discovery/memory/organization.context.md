# Organizational Context - TechFlow Solutions

**Organization**: TechFlow Solutions Inc.
**Industry**: B2B SaaS (Project Management Software)
**Founded**: 2018
**Size**: 150 employees
**Headquarters**: Austin, Texas
**Annual Revenue**: $15M ARR

## Key Characteristics

**Company Stage**: Series B (raised $25M in 2023)
**Growth Rate**: 120% YoY
**Customer Base**: 800 business customers (SMB to Mid-Market)
**Product**: Cloud-based project management platform

**Culture**:
- Customer-obsessed (NPS is a key metric)
- Move fast, but quality matters
- Data-driven decision making
- Remote-first company

## Technology Stack

**Frontend**:
- React 18
- TypeScript
- Tailwind CSS
- Next.js

**Backend**:
- .NET 8 (C#)
- Azure Cloud
- SQL Server
- Redis for caching

**Infrastructure**:
- Azure App Service
- Azure SQL Database
- Azure Service Bus
- GitHub for source control
- GitHub Actions for CI/CD

**Current Tech Debt**:
- Support portal built in 2019 (React 16, outdated patterns)
- No real-time features
- Mobile experience is poor
- Performance issues at scale

## Current Priorities (Q1 2025)

1. **Reduce Customer Churn** (Currently 8% monthly - too high)
2. **Improve Support Efficiency** (Currently 3-day avg response time)
3. **Scale Engineering Team** (Hiring 10 engineers this quarter)
4. **Launch Mobile App** (Planned for Q2)

## Past Projects

**Project 1: API v2 Rewrite (2023)**
- Outcome: Success
- Timeline: 4 months (planned 3)
- Learning: Underestimated migration complexity

**Project 2: Real-time Collaboration (2024)**
- Outcome: Moderate success
- Timeline: 6 months (planned 4)
- Learning: Should have done more discovery - changed requirements mid-flight

**Project 3: Enterprise Dashboard (2024)**
- Outcome: Failure (shelved)
- Timeline: 3 months spent, then cancelled
- Learning: Didn't validate problem with enough customers first

## Team Structure

**Engineering**: 25 people
- Frontend: 8
- Backend: 10
- DevOps: 3
- QA: 4

**Product**: 5 people
- Product Managers: 3
- Product Designers: 2

**Customer Success**: 12 people
- Support Agents: 8
- Customer Success Managers: 4

**Leadership**: CEO, CTO, CPO, VP Sales, VP Customer Success

## Decision-Making Process

- Small projects (<$50k, <2 months): CTO approval
- Medium projects ($50k-$250k, 2-6 months): Executive team approval
- Large projects (>$250k, >6 months): Board approval

**Project Initiation Requirements**:
- Problem statement
- Business case
- Resource estimate
- Risk assessment

## Constraints

**Budget Constraints**:
- Q1 engineering budget: $400k (includes salaries + tools)
- Preference for build vs buy (to maintain IP)

**Technical Constraints**:
- Must stay on Azure (committed contract)
- Must maintain .NET backend (team expertise)
- Must support SSO (enterprise requirement)
- Must maintain 99.9% uptime SLA

**Timeline Constraints**:
- Q1 focus: Support improvements (board priority)
- Q2 blocked: Mobile app launch
- Q3: Enterprise feature development planned

**Regulatory Constraints**:
- SOC 2 Type II compliant (annual audit)
- GDPR compliant (EU customers)
- Data residency requirements for some customers

## Success Metrics (Company-Wide)

- **Revenue**: $15M → $25M ARR by end of 2025
- **Customer Count**: 800 → 1,200 customers
- **Net Revenue Retention**: 110% (currently 95%)
- **NPS**: 35 (currently 28)
- **Support Response Time**: <24 hours (currently 3 days)
- **Customer Churn**: <5% monthly (currently 8%)

## Current Pain Points

1. **Support Backlog**: 200+ tickets open at any time
2. **Engineering Burnout**: On-call issues, technical debt
3. **Customer Complaints**: Slow support, can't find answers
4. **Support Team Frustration**: Tools are manual, inefficient
5. **Leadership Concern**: Churn is hurting growth

---

**Last Updated**: January 15, 2025
**Maintained By**: Product Team
