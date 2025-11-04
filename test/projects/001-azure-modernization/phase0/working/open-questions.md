# Open Questions - Azure Modernization Discovery

**Last Updated**: 2025-11-04 (After Interview 2)

---

## Questions Answered by Interview 2 (Sarah Mitchell)

- ✅ **Why does environment provisioning take 6 weeks?**
  - Answer: Manual process, many approvals, often 3+ months not 6 weeks
- ✅ **What are the hidden shadow IT systems?**

  - Answer: 30+ Access databases, departmental solutions, undocumented integrations

- ✅ **How does the team feel about cloud modernization?**

  - Answer: Mixed - younger developers excited, mid-career pragmatic, senior resistant

- ✅ **What actually happened during SAP failure?**

  - Answer: Big bang approach, stale requirements, data migration disaster, no rollback

- ✅ **Where are the integration nightmares?**
  - Answer: 17 direct database connections, no API layer, real-time + batch conflicts

---

## Critical New Questions Generated

### Budget & Cost Questions (FOR CFO JENNIFER WALSH)

- ❓ **What is the REAL budget for this transformation?**
  - Who should know: CFO Jennifer Walsh
  - Priority: CRITICAL
  - Needed by: Before any detailed planning
- ❓ **What would make this different from SAP in your eyes?**
  - Who should know: CFO Jennifer Walsh
  - Priority: HIGH
  - Context: Need to understand her risk tolerance and what builds confidence
- ❓ **What level of cost overrun would trigger project cancellation?**
  - Who should know: CFO Jennifer Walsh
  - Priority: HIGH
  - Context: Sarah says Jennifer assumes 3X overruns
- ❓ **How do you want to see ROI demonstrated?**
  - Who should know: CFO Jennifer Walsh
  - Priority: HIGH
  - Context: Need to align on success metrics and measurement

### Operational Questions (FOR VP OPERATIONS ROBERT TURNER)

- ❓ **What is the TRUE tolerance for downtime during migration?**
  - Who should know: VP Operations Robert Turner
  - Priority: CRITICAL
  - Context: Michael says "zero," Sarah says "4 hours Sunday morning"
- ❓ **How will union react to automation and workflow changes?**
  - Who should know: VP Operations Robert Turner
  - Priority: HIGH
  - Context: Sarah flagged union as blocker risk
- ❓ **Which manufacturing processes are absolutely sacrosanct?**
  - Who should know: VP Operations Robert Turner
  - Priority: HIGH
  - Context: Need to know true "cannot change" boundaries
- ❓ **What operational improvements would have biggest business impact?**
  - Who should know: VP Operations Robert Turner
  - Priority: MEDIUM
  - Context: Align modernization to business value

### Technical Deep Dive Questions (FOR KEVIN MARTINEZ - INFRASTRUCTURE)

- ❓ **What is the complete hardware EOL risk assessment?**
  - Who should know: Kevin Martinez (Infrastructure Manager)
  - Priority: HIGH
  - Context: 60% of servers past EOL, buying parts on eBay
- ❓ **What would infrastructure replacement cost on-prem vs. cloud?**
  - Who should know: Kevin Martinez (Infrastructure Manager)
  - Priority: HIGH
  - Context: Need cost comparison for CFO
- ❓ **What is current DR capability and gap to requirements?**
  - Who should know: Kevin Martinez (Infrastructure Manager)
  - Priority: MEDIUM
  - Context: Last DR test was partial failure

### Application Complexity Questions (FOR RAJ PATEL - LEAD DEVELOPER)

- ❓ **Complete inventory of black box COM+ components?**
  - Who should know: Raj Patel (Lead ERP Developer)
  - Priority: CRITICAL
  - Context: No source code, cannot recompile - must work around or replace
- ❓ **What would break if we modernize database schema?**
  - Who should know: Raj Patel (Lead ERP Developer)
  - Priority: HIGH
  - Context: 47 stored procedures for one field, 847 Crystal Reports
- ❓ **How to prioritize technical debt items?**
  - Who should know: Raj Patel (Lead ERP Developer)
  - Priority: MEDIUM
  - Context: Must fix some things before migration possible

### Manufacturing IT Questions (FOR LISA CHEN)

- ❓ **What are the shop floor system dependencies and risks?**
  - Who should know: Lisa Chen (Manufacturing IT)
  - Priority: HIGH
  - Context: PLC integration cannot break
- ❓ **What MES system constraints do we have to work with?**
  - Who should know: Lisa Chen (Manufacturing IT)
  - Priority: HIGH
  - Context: ShopFloor Pro vendor lock-in

### Customer Requirements (FOR DETROIT DYNAMICS CONTACT)

- ❓ **What are EXACT SOC 2 requirements and timeline flexibility?**
  - Who should know: Detroit Dynamics contact (customer)
  - Priority: HIGH
  - Context: 30% of revenue at stake, need to verify requirements
- ❓ **What other modern capabilities do large customers need?**
  - Who should know: Detroit Dynamics + other customers
  - Priority: MEDIUM
  - Context: Align modernization to customer value

---

## Still Open Questions (From Interview 1)

- ⏳ **How much is the board actually willing to invest upfront?**
  - Potential sources: CFO Jennifer Walsh
  - Priority: CRITICAL
- ⏳ **What happens if Detroit Dynamics timeline can't be met?**
  - Potential sources: CEO, VP Sales, Detroit Dynamics contact
  - Priority: HIGH
- ⏳ **What's the real budget for training and upskilling?**
  - Potential sources: CFO Jennifer Walsh, HR
  - Priority: HIGH

---

## Research Questions (No Single Source)

- ❓ **Complete shadow IT discovery - how do we find what we don't know exists?**
  - Approach: Audit network traffic, interview all department heads, survey end users
  - Priority: CRITICAL
  - Timeline: Must complete before migration planning
- ❓ **What are industry benchmarks for manufacturing cloud migrations?**
  - Approach: Research analyst reports, case studies, peer companies
  - Priority: MEDIUM
  - Context: Calibrate expectations and timeline
- ❓ **What are proven patterns for SQL Server 2008 to Azure migration with zero downtime?**
  - Approach: Microsoft Azure documentation, migration partners, case studies
  - Priority: HIGH
  - Context: Database migration is highest risk
