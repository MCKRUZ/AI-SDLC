# Organizational Context

**Organization**: Contoso Manufacturing Inc.
**Industry**: Manufacturing & Distribution
**Founded**: 1978
**Size**: 1,500 employees
**Headquarters**: Cleveland, Ohio
**Annual Revenue**: $300M USD

## Key Characteristics

**Company Stage**: Established mid-market, private (family-founded, now private equity owned)
**Growth Rate**: 8% YoY (slowing from 15% three years ago)
**Customer Base**: 450+ B2B customers (automotive, aerospace, industrial equipment)
**Product/Service**: Precision metal components, custom fabrication, JIT manufacturing

**Culture**:
- Traditional, hierarchical structure with long-tenured workforce
- Quality-focused, "measure twice, cut once" mentality
- Risk-averse, especially regarding production systems
- Slow technology adoption, "if it ain't broke, don't fix it"
- On-site work culture (manufacturing requires physical presence)
- Union workforce on factory floor (UAW)

## Technology Stack

### Current State (Legacy)

**Frontend**:
- Windows Forms applications (internal tools)
- Classic ASP customer portal (circa 2021)
- SharePoint 2013 for intranet
- No mobile applications

**Backend**:
- .NET Framework 4.0 (custom ERP)
- Classic ASP/VBScript (customer portal)
- Windows Services for batch processing
- COM+ components for business logic
- SOAP web services for limited integrations

**Database**:
- SQL Server 2008 R2 (primary ERP database)
- SQL Server 2014 (customer portal)
- MS Access databases (departmental solutions)
- Flat files for EDI transactions

**Infrastructure**:
- Physical servers (200+, Dell PowerEdge, 60% past EOL)
- VMware vSphere 5.5 (limited virtualization)
- Windows Server 2008/2012 primarily
- SAN storage (EMC VNX, nearing capacity)
- Cisco network infrastructure (aging)
- Barracuda firewall appliances
- Tape backup system (LTO-6)

**Development Practices**:
- Waterfall SDLC (6-12 month releases)
- Manual deployments via RDP
- TFS 2013 for source control
- Manual testing only
- No CI/CD pipeline
- Limited documentation
- Tribal knowledge prevalent

### Cloud Footprint (Minimal)

**Current Cloud Services**:
- Office 365 (email and basic collaboration)
- Workday (HR system, SaaS)
- Salesforce (CRM, limited adoption)

## Team Structure

**IT Department** (45 people total):

**Engineering/Development**: 12 developers
- 8 .NET developers (maintaining ERP)
- 2 database developers
- 2 report developers (Crystal Reports/SSRS)

**Infrastructure**: 15 staff
- 6 server administrators
- 4 network engineers
- 3 desktop support
- 2 help desk

**Applications Support**: 8 staff
- 4 ERP support specialists
- 2 business analysts
- 2 data analysts

**Management**: 5 staff
- IT Director
- Development Manager
- Infrastructure Manager
- 2 Team Leads

**Security**: 2 staff (reporting to IT Director)

**Other Departments**:
- **Operations**: 950 employees (manufacturing, warehouse, logistics)
- **Sales & Marketing**: 75 employees
- **Finance**: 45 employees
- **HR**: 25 employees
- **Quality & Compliance**: 35 employees
- **Engineering (Product)**: 125 employees
- **Executive & Admin**: 20 employees

## Strategic Goals (2025-2026)

1. **Digital Transformation**: Modernize core systems to improve agility and reduce technical debt
2. **Cost Optimization**: Reduce IT operational costs by 30% over 3 years
3. **Customer Experience**: Launch modern customer portal with mobile capabilities
4. **Operational Excellence**: Achieve real-time visibility into manufacturing operations
5. **Compliance**: Achieve SOC 2 Type II certification for key customers
6. **Talent**: Attract younger workforce with modern technology stack
7. **M&A Readiness**: Prepare systems for potential acquisition or merger

## Current Challenges

### Technology Challenges
1. **Legacy System Risk**: Core ERP on unsupported SQL 2008, high failure risk
2. **Integration Nightmares**: Point-to-point integrations, data silos, no real-time data
3. **Scalability Issues**: Cannot handle peak loads, batch processes failing
4. **Security Vulnerabilities**: Outdated OS/software, no patch management
5. **Developer Productivity**: 6-month lead time for new environments
6. **Skills Gap**: Difficulty finding COBOL/VB6 expertise for legacy systems

### Business Challenges
1. **Competitive Pressure**: Competitors offering better digital experiences
2. **Customer Demands**: Large customers requiring SOC 2, API integrations
3. **Cost Pressures**: IT costs growing faster than revenue
4. **Agility**: Cannot respond quickly to market changes
5. **Data Insights**: No real-time analytics, decisions based on week-old data
6. **Remote Work**: COVID exposed inability to work remotely

### Organizational Challenges
1. **Change Resistance**: Long-tenured staff fear job displacement
2. **Skills Mismatch**: Current IT staff lacks cloud expertise
3. **Budget Constraints**: Large CapEx for hardware refresh competing with modernization
4. **Risk Tolerance**: "One mistake could stop production" mentality
5. **Governance**: No formal EA or architecture review board

## Key Constraints

**Technical**:
- 24/7 manufacturing operations (99.9% uptime requirement)
- Legacy system dependencies (some source code lost)
- Integration with partner EDI systems (AS2 protocol)
- Regulatory requirements (FDA, ISO 9001, ITAR)
- Data residency requirements (some data must stay in US)
- Network limitations at manufacturing sites (limited bandwidth)

**Business**:
- Union agreements affecting workforce changes
- Long-term customer contracts with SLAs
- Seasonal production peaks (Q4 is 40% of revenue)
- Thin margins (8-12% EBITDA)
- PE ownership expecting ROI within 3 years

**Resource**:
- Limited budget (IT budget is 2.5% of revenue)
- Small IT team for company size (3% ratio)
- No dedicated architects or cloud engineers
- Training budget minimal ($500/person/year)
- Competing priorities (ERP upgrade vs. modernization)

## Compliance & Regulatory

**Current Compliance**:
- ISO 9001:2015 (Quality Management)
- ITAR (International Traffic in Arms Regulations)
- FDA 21 CFR Part 820 (Medical Device Quality System)
- OSHA requirements for manufacturing

**Required/Desired**:
- SOC 2 Type II (customer requirement, 18 months)
- ISO 27001 (information security, desired)
- NIST Cybersecurity Framework (insurance requirement)

## Decision Making

**Key Decision Makers**:
- **CEO**: Final authority on major investments (>$500K)
- **CFO**: Budget approval, ROI requirements (3-year payback)
- **CTO**: Technology strategy (new hire, cloud advocate)
- **IT Director**: Operational decisions, risk assessment

**Decision Process**:
- Business case required for >$100K
- Executive committee monthly reviews
- Board approval for >$1M investments
- Risk assessment mandatory for production systems

## External Relationships

**Key Vendors**:
- Microsoft (EA agreement, SQL/Windows/Office)
- Dell (hardware provider)
- CDW (VAR and integration partner)
- Local MSP (after-hours support)

**System Integrators Experience**:
- Failed SAP implementation (2018, $2M loss)
- Successful Workday implementation (2020)
- Mixed results with offshore development

## Previous Modernization Attempts

1. **2018 SAP Implementation** (Failed)
   - Attempted to replace custom ERP
   - Abandoned after 18 months, $2M spent
   - Lesson: Big-bang approaches don't work

2. **2020 Workday HR** (Success)
   - Replaced on-premise HR system
   - Phased rollout over 6 months
   - Lesson: SaaS works for non-core systems

3. **2022 SharePoint Online Migration** (Partial)
   - Moved from SharePoint 2013
   - Limited adoption, training issues
   - Lesson: Change management critical

## Success Patterns

**What Works**:
- Phased approaches with quick wins
- Strong vendor support and partnerships
- Clear ROI with measurable benefits
- Pilot programs before full rollout
- Executive sponsorship and communication

**What Doesn't Work**:
- Big-bang transformations
- Technology for technology's sake
- Ignoring change management
- Underestimating data migration
- Assuming staff will self-train

## Notes

**Special Considerations for Discovery**:
- Factory floor systems are sacred - any discussion of changes will create anxiety
- IT Director Sarah has institutional knowledge but also emotional investment in current systems
- New CTO Michael is on 90-day plan to present modernization strategy to board
- Recent private equity acquisition (2023) driving focus on operational efficiency
- Company pride in 45-year history and reputation for quality
- Manufacturing sites run 3 shifts, maintenance windows only Sunday 2 AM - 6 AM
- ERP system customizations are extensive and poorly documented
- Several "shadow IT" Access databases run critical departmental functions
- Previous failed projects have created skepticism about large IT initiatives

**Communication Preferences**:
- Executive team prefers face-to-face meetings
- Factory management communicates via daily huddles
- IT team uses Microsoft Teams (adoption growing)
- Formal communications require email with clear action items

**Political Dynamics**:
- Natural tension between new CTO (change) and IT Director (stability)
- VP of Operations has CEO's ear (golf buddies)
- CFO is most skeptical stakeholder (burned by SAP failure)
- Union leadership must be engaged early for workforce impacts
- Board expects quarterly updates on major initiatives

**Quick Wins Needed**:
- Executive dashboard for real-time KPIs
- Customer portal mobile app
- Automated report distribution
- Single sign-on for applications
- Dev/test environment provisioning

---

*This context should be loaded at the start of discovery sessions to provide agents with deep organizational understanding. Update after significant organizational changes or annually during planning cycles.*

*Last Updated: 2025-11-03 (Test Case Creation)*
