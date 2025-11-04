# Technical Stack Context

**Organization**: Contoso Manufacturing Inc.
**Document Type**: Technical Stack Inventory
**Last Updated**: 2025-11-03
**Classification**: Internal - Discovery Phase

---

## Core Business Systems

### ERP System (Custom Built)
**Name**: ContosoERP
**Age**: 15 years (2010 initial deployment)
**Technology Stack**:
- **Platform**: .NET Framework 4.0
- **Language**: C#, VB.NET
- **Database**: SQL Server 2008 R2 (800GB)
- **Architecture**: 3-tier monolith
- **UI**: Windows Forms, some ASP.NET Web Forms
- **Integration**: SOAP web services, flat file exchanges

**Key Characteristics**:
- 2.5 million lines of custom code
- 450+ database tables
- 1,200+ stored procedures
- Extensive customization, minimal documentation
- Business logic mixed between application and database
- Tightly coupled with manufacturing systems

**Dependencies**:
- Crystal Reports for reporting
- ActiveX controls for UI components
- COM+ components for business services
- Windows authentication
- MSMQ for async processing

**Issues**:
- SQL Server 2008 out of support
- No horizontal scaling capability
- 15-minute report generation times
- Batch processes taking 4-6 hours nightly
- Single point of failure

### Customer Portal
**Age**: 3 years (2021 refresh)
**Technology Stack**:
- **Platform**: Classic ASP
- **Database**: SQL Server 2014 (50GB)
- **Hosting**: IIS 7.5 on Windows Server 2012
- **Integration**: Direct database queries to ERP

**Issues**:
- Not mobile responsive
- No API layer
- Security concerns (SQL injection vulnerabilities)
- Performance issues (page loads >5 seconds)

### Manufacturing Execution System (MES)
**Name**: ShopFloor Pro (COTS)
**Version**: 8.5 (2018)
**Database**: Oracle 11g
**Integration**: File-based with ERP (hourly batch)

### Inventory Management
**Name**: WarehouseMaster 2015
**Type**: COTS with customizations
**Database**: SQL Server 2012
**Integration**: Real-time with ERP via MSMQ

---

## Infrastructure

### Data Centers

**Primary Data Center** (Cleveland, OH):
- **Servers**: 140 physical servers
  - 60 x Dell PowerEdge R710 (2011-2013 era)
  - 50 x Dell PowerEdge R720 (2013-2015 era)  
  - 30 x Dell PowerEdge R740 (2018-2019 era)
- **Virtualization**: VMware vSphere 5.5 (40% virtualized)
- **Storage**: EMC VNX 5400 (250TB raw, 85% utilized)
- **Network**: Cisco Catalyst 6500 series
- **Backup**: Commvault 11 to LTO-6 tape

**DR Data Center** (Columbus, OH):
- **Servers**: 60 physical servers (older equipment)
- **Replication**: Manual/scripted (RPO: 24 hours, RTO: 72 hours)
- **Last DR Test**: Partial failure (Q3 2024)

### Operating Systems
- Windows Server 2008 R2: 45% of servers
- Windows Server 2012/2012 R2: 35% of servers
- Windows Server 2016: 15% of servers
- Windows Server 2019: 5% of servers
- Linux (RHEL 6/7): 10 servers (Oracle, specific apps)

### Databases
- **SQL Server Instances**: 
  - SQL 2008 R2: 8 instances
  - SQL 2012: 5 instances
  - SQL 2014: 3 instances
  - SQL 2017: 1 instance
- **Oracle**: 11g (2 instances for MES)
- **MS Access**: 25+ departmental databases

### Network
- **WAN**: MPLS (100Mbps primary, 50Mbps backup)
- **Internet**: 500Mbps business fiber
- **Firewall**: Barracuda X800
- **VPN**: Cisco AnyConnect (100 concurrent users max)
- **Load Balancers**: F5 Big-IP (2, end-of-life)

---

## Development Environment

### Source Control
- **Primary**: TFS 2013 (on-premises)
- **Usage**: 60% of code in source control
- **Branching**: No formal strategy

### Development Tools
- Visual Studio 2013/2015 (primary)
- SQL Server Management Studio 2014
- Crystal Reports Designer XI
- Notepad++ (scripting)

### Development Practices
- **Build Process**: Manual builds on developer machines
- **Deployment**: Manual via RDP and xcopy
- **Testing**: Manual testing only, no automation
- **Documentation**: Minimal, outdated

### Environments
- **Development**: 1 shared environment (often broken)
- **Test**: Sometimes available (refreshed quarterly)
- **Staging**: Non-existent
- **Production**: Direct deployments after hours

**Environment Provisioning**: 
- 4-6 weeks for new server
- 2-3 months for new full environment
- Manual process, many approvals needed

---

## Integrations

### B2B Integrations
- **EDI**: Sterling Commerce (AS2 protocol)
- **Partners**: 50+ trading partners
- **Formats**: X12, EDIFACT, custom flat files
- **Volume**: 10,000+ transactions/day

### Internal Integrations
- **Pattern**: Point-to-point, no ESB
- **Methods**: 
  - Database links (most common)
  - Flat file drops
  - SOAP web services (limited)
  - Scheduled SQL jobs
- **Documentation**: Sparse, tribal knowledge

### External Services
- **Banking**: SFTP file transfers (ACH, wire transfers)
- **Shipping**: FedEx/UPS APIs (SOAP, outdated versions)
- **Credit Services**: Dun & Bradstreet (batch file)

---

## Security

### Current Security Stack
- **Firewall**: Barracuda X800
- **Antivirus**: Symantec Endpoint Protection 12
- **Email Security**: Barracuda Email Gateway
- **Backup**: Commvault 11
- **Monitoring**: Limited (Windows Event Logs)
- **SIEM**: None
- **Vulnerability Management**: Annual pen test only

### Authentication & Access
- **Internal**: Active Directory (2008 R2 forest level)
- **External**: Local application accounts
- **MFA**: Not implemented
- **SSO**: Not implemented
- **Password Policy**: 90-day rotation, 8 characters

### Security Gaps
- No centralized logging
- No security incident response plan
- Outdated SSL certificates (TLS 1.0 still enabled)
- Service accounts with excessive privileges
- No network segmentation
- Shadow IT not monitored

---

## Cloud Services (Current)

### Microsoft 365
- **Services**: Exchange Online, Teams, SharePoint Online
- **Users**: All employees
- **Adoption**: Email (100%), Teams (60%), SharePoint (30%)
- **Integration**: Azure AD Connect for hybrid identity

### Workday (HR)
- **Type**: Full SaaS
- **Users**: HR team + all employees (self-service)
- **Integration**: File-based with payroll system

### Salesforce (CRM)
- **Edition**: Professional
- **Users**: 75 (sales & marketing)
- **Adoption**: Limited (50% features used)
- **Integration**: Manual data entry from ERP

---

## Technical Debt Inventory

### Critical (Address Immediately)
1. SQL Server 2008 end-of-support (security risk)
2. Windows Server 2008 (40% of infrastructure)
3. No disaster recovery capability
4. No backup testing regimen
5. Customer portal security vulnerabilities

### High Priority
1. Manual deployment processes
2. No test environments
3. Point-to-point integrations
4. No monitoring/alerting
5. Limited VPN capacity
6. Storage approaching capacity

### Medium Priority
1. Technical documentation gaps
2. No API strategy
3. Legacy reporting architecture
4. No mobile capabilities
5. Manual data reconciliation

### Low Priority
1. User interface modernization
2. Code refactoring opportunities
3. Database optimization
4. Archive strategy
5. Print management

---

## Performance Metrics

### Current System Performance
- **ERP Response Time**: 3-5 seconds average, 15+ seconds for reports
- **Batch Processing**: 4-6 hours nightly, impacting morning shift
- **Database Growth**: 20% annually
- **Storage Growth**: 30% annually
- **Network Utilization**: 70% at peak
- **CPU Utilization**: 60-80% sustained on database servers

### Availability Metrics
- **ERP Uptime**: 98.5% (target 99.9%)
- **Portal Uptime**: 97% (customer-facing)
- **Planned Maintenance**: 8 hours/month
- **Unplanned Outages**: 2-3 per month
- **MTTR**: 4 hours average

---

## Licensing

### Major Software Licenses
- **Microsoft EA**: $850K/year
  - Windows Server Datacenter
  - SQL Server Enterprise
  - Office 365 E3
  - Visual Studio Professional
- **VMware vSphere**: $125K/year
- **Oracle Database**: $200K/year
- **Commvault**: $75K/year
- **Various COTS**: $450K/year

### License Compliance Issues
- SQL Server over-deployed (audit risk)
- VMware version out of support
- Several applications on extended support
- Shadow IT creating compliance gaps

---

## Skills Inventory

### Current IT Skills
- **.NET Development**: Strong (8 developers)
- **SQL Server Admin**: Strong (2 DBAs)
- **Windows Server**: Strong (6 admins)
- **VMware**: Moderate (2 certified)
- **Networking**: Moderate (4 engineers)
- **Security**: Weak (no dedicated staff)
- **Cloud**: Minimal (1 person learning)
- **DevOps**: None
- **Containers**: None
- **Modern Web**: Minimal

### Training Needs for Cloud
- Azure fundamentals (entire team)
- Cloud architecture patterns
- Infrastructure as Code
- CI/CD pipelines
- Container technologies
- Security best practices
- Cost optimization
- Modern development practices

---

## Migration Considerations

### Migration Complexities
1. **Data Volume**: 2TB+ of production data
2. **Data Gravity**: Cross-system queries and dependencies
3. **Customizations**: Extensive, undocumented
4. **Integrations**: 100+ integration points
5. **Compliance**: Data residency, audit trails
6. **24/7 Operations**: Minimal maintenance windows
7. **Legacy Dependencies**: ActiveX, COM+, Windows Auth
8. **Network**: Limited bandwidth at remote sites

### Migration Priorities (Initial Assessment)
1. **Quick Wins**: Dev/test environments, backup modernization
2. **Phase 1 Candidates**: Customer portal, reporting infrastructure
3. **Phase 2 Candidates**: Peripheral systems, file shares
4. **Phase 3 Candidates**: Core ERP (requires re-architecture)
5. **Stay On-Premises**: Manufacturing systems (initially)

### Technical Prerequisites for Cloud
- Network upgrade (bandwidth, ExpressRoute)
- Identity management (Azure AD)
- Security baseline (MFA, conditional access)
- Monitoring strategy
- Backup/DR strategy
- Cost management approach
- Governance framework
- Skills development program

---

## Architecture Patterns (Current State)

### Anti-Patterns in Use
- Monolithic architecture
- Database as integration hub
- No service boundaries
- Synchronous processing for everything
- No caching strategy
- Hard-coded configurations
- Shared database accounts
- No retry logic

### Missing Capabilities
- API management
- Event-driven architecture
- Microservices
- Containerization
- Service mesh
- Circuit breakers
- Distributed tracing
- Feature flags

---

## Notes for Discovery

**Key Technical Insights**:
- The ERP system is the heart of everything - all roads lead to/from it
- Database-level integration means high coupling between systems
- No true development or test environments creates huge risk
- The "it works, don't touch it" mentality has created significant technical debt
- Shadow IT exists because central IT can't respond quickly enough
- Performance issues are often band-aided rather than properly fixed
- The failed SAP implementation has made everyone gun-shy about ERP changes
- Manual processes everywhere indicate lack of automation maturity

**Critical Questions for Stakeholders**:
1. What keeps you up at night about the current systems?
2. If you could wave a magic wand and fix three things, what would they be?
3. What would happen if the ERP was down for 24 hours?
4. How do you handle peak loads during busy season?
5. What workarounds have become standard practice?
6. What data do you need but can't get easily?
7. What's your tolerance for downtime during migration?
8. Which systems absolutely cannot change?

---

*This technical context should be loaded during discovery to provide comprehensive understanding of the current technical landscape, constraints, and migration considerations.*

*Classification: Internal Use Only - Contains sensitive technical architecture information*
