# Risk Register - Azure Modernization Initiative

**Last Updated**: 2025-11-04 (After Interview 2)  
**Status**: Active Discovery Phase  
**Review Frequency**: After each interview, weekly during planning

---

## Risk Scoring Matrix

**Probability Scale**: 1 (Very Low) to 5 (Very High)  
**Impact Scale**: 1 (Minor) to 5 (Critical)  
**Risk Score**: Probability × Impact  
**Priority**: 15-25 = Critical | 10-14 = High | 5-9 = Medium | 1-4 = Low

---

## Critical Risks (Score 15-25)

### RISK-001: Project Budget Cut Mid-Flight
- **Category**: Financial
- **Description**: CFO Jennifer Walsh assumes 3X cost overruns based on SAP trauma. If short-term costs exceed expectations (which Sarah says is inevitable), Jennifer may kill funding before ROI is realized.
- **Probability**: 4 (High) - CFO is known skeptic, controls purse strings
- **Impact**: 5 (Critical) - Would halt project entirely, waste investment made
- **Risk Score**: 20 (CRITICAL)
- **Root Cause**: Misaligned expectations - Michael promises savings, Sarah predicts investment-before-savings
- **Trigger Events**: Q2 budget review, unexpected cost overrun, negative board sentiment
- **Mitigation Strategy**:
  - Interview CFO immediately to understand budget reality
  - Reset expectations BEFORE project starts about short-term costs
  - Create detailed cost model with timeline (investment phase → savings phase)
  - Secure multi-year budget commitment upfront
  - Establish early wins that demonstrate progress
- **Contingency Plan**: If budget cut appears imminent, pivot to minimal viable scope that preserves gains made
- **Owner**: Discovery Facilitator → CTO Michael Chen
- **Status**: Open - Interview 3 with CFO is CRITICAL
- **Source**: Interview 2 (Sarah Mitchell), Interview 1 (Michael Chen)

---

### RISK-002: Unknown Shadow IT System Breaks Production
- **Category**: Technical
- **Description**: 30+ undocumented Access databases and unknown integrations exist. Will likely discover critical systems AFTER migration breaks them. Example: CFO has scheduled task on "decommissioned" server.
- **Probability**: 5 (Very High) - Sarah says "we discover systems after we break them"
- **Impact**: 4 (High) - Could halt business operations, damage credibility, cause rollback
- **Risk Score**: 20 (CRITICAL)
- **Root Cause**: Years of departments building solutions because IT couldn't deliver; no central inventory
- **Trigger Events**: Database migration, server decommissioning, API changes
- **Mitigation Strategy**:
  - Phase 0: Comprehensive shadow IT discovery BEFORE any migration
  - Network traffic analysis to identify database connections
  - Survey all department heads for their "critical Access databases"
  - Create comprehensive integration inventory
  - Test migrations in isolated environment first
- **Contingency Plan**: Rapid rollback capability; parallel run old and new systems longer than planned
- **Owner**: IT Director Sarah Mitchell → Infrastructure team
- **Status**: Open - Must start discovery immediately
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-003: Lost Institutional Knowledge During Migration
- **Category**: Organizational
- **Description**: Best people are actively job hunting. Key developers know undocumented systems. If they leave during migration, project loses critical knowledge when most needed.
- **Probability**: 4 (High) - Sarah confirms best people are looking
- **Impact**: 5 (Critical) - Could make migration impossible, cost months in knowledge recovery
- **Risk Score**: 20 (CRITICAL)
- **Root Cause**: Burnout from years of firefighting; lack of modern tech stack; better opportunities elsewhere
- **Trigger Events**: Key developer resignation, multiple departures, knowledge concentration
- **Mitigation Strategy**:
  - Retention bonuses for critical staff through migration completion
  - Aggressive documentation of tribal knowledge
  - Pair programming/shadowing to spread knowledge
  - Make Azure training attractive (resume building)
  - External augmentation to reduce dependency on key individuals
- **Contingency Plan**: Emergency consulting support; delay migration phases if critical people leave
- **Owner**: IT Director Sarah Mitchell + HR
- **Status**: Open - Need retention plan immediately
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-004: Timeline Expectations vs. Reality Collision
- **Category**: Organizational
- **Description**: Michael promises 90-day wins and 18-month transformation. Sarah says "years, not quarters" with even Phase 1 at 9-12 months. When board doesn't see promised results, confidence collapses.
- **Probability**: 5 (Very High) - Expectations are fundamentally misaligned
- **Impact**: 4 (High) - Loss of executive support, project cancellation, career damage to Michael
- **Risk Score**: 20 (CRITICAL)
- **Root Cause**: Michael managing board expectations without full understanding of technical complexity
- **Trigger Events**: 90-day checkpoint with no visible wins, board presentation, quarterly reviews
- **Mitigation Strategy**:
  - Align Michael and Sarah on realistic timeline BEFORE board presentation
  - Define what "90-day win" actually means (POC vs. production system)
  - Identify genuine quick wins that are achievable (e.g., cloud dev environments)
  - Reset board expectations with credible, detailed timeline
  - Show incremental progress at each checkpoint
- **Contingency Plan**: Redefine success criteria; extend timeline with board buy-in; pivot to smaller scope
- **Owner**: Discovery Facilitator → CTO Michael Chen
- **Status**: Open - MUST resolve before Phase 1
- **Source**: Interview 1 (Michael Chen), Interview 2 (Sarah Mitchell)

---

### RISK-005: COM+ Black Box Components Block Migration
- **Category**: Technical
- **Description**: Critical COM+ components with no source code cannot be recompiled or modified. Must work around them or completely replace underlying systems. Example: 47 stored procedures for one field, 23 break if column added in wrong position.
- **Probability**: 4 (High) - Known to exist, unclear how many
- **Impact**: 5 (Critical) - Could make certain migrations impossible or require complete system rewrites
- **Risk Score**: 20 (CRITICAL)
- **Root Cause**: Developer who wrote them left in 2013, source code never recovered
- **Trigger Events**: Database schema changes, system modernization attempts, integration updates
- **Mitigation Strategy**:
  - Complete inventory of black box components (Interview Raj Patel)
  - Reverse engineer or replace before migration
  - Design migration to avoid touching these systems initially
  - Allocate budget for complete replacement if necessary
  - Consider wrapping in abstraction layer
- **Contingency Plan**: Accept some systems cannot be modernized; build integration layers around them
- **Owner**: Lead ERP Developer Raj Patel
- **Status**: Open - Need complete inventory
- **Source**: Interview 2 (Sarah Mitchell)

---

## High Risks (Score 10-14)

### RISK-006: Union Work Stoppage Over Automation
- **Category**: Organizational
- **Description**: Operations workforce is unionized (UAW). Automation or workflow changes could trigger labor action. Work stoppages would halt production and doom project politically.
- **Probability**: 3 (Medium) - Depends on how changes are positioned
- **Impact**: 4 (High) - Production halt, board panic, project cancellation
- **Risk Score**: 12 (HIGH)
- **Mitigation Strategy**:
  - Interview VP Operations early to understand union dynamics
  - Engage union leadership proactively about technology changes
  - Frame modernization as "augmentation" not "replacement"
  - Commit to no layoffs, retrain affected workers
  - Negotiate changes that affect seniority or job classifications
- **Contingency Plan**: Delay automation features; focus on back-office modernization first
- **Owner**: VP Operations Robert Turner
- **Status**: Open - Need VP Ops interview
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-007: Skills Gap Makes Team Unable to Execute
- **Category**: Organizational
- **Description**: Zero Azure experience across 45-person IT team. Minimum 6 months training needed. Some senior staff won't/can't adapt to cloud. Forced retraining creates resentment and failure.
- **Probability**: 4 (High) - Skill gap is confirmed, training time is long
- **Impact**: 3 (Medium) - Delays, quality issues, but not fatal if augmented
- **Risk Score**: 12 (HIGH)
- **Mitigation Strategy**:
  - Honest skills assessment of current team
  - Identify who CAN/WILL adapt vs. who can't/won't
  - External augmentation (contractors, new hires) to fill gaps
  - Comprehensive training program (6 months minimum)
  - Create transition plan for those who can't adapt
  - Start with small pilot team, expand as skills grow
- **Contingency Plan**: Heavier reliance on external partners; accept slower pace; hire new cloud-native talent
- **Owner**: IT Director Sarah Mitchell + HR
- **Status**: Open - Need skills assessment
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-008: Vendor Lock-in Constraints Migration Options
- **Category**: Technical / Financial
- **Description**: MES system (ShopFloor Pro) is 2-year/$1M to replace. EDI partners won't change. PLC integration vendor out of business. These create immovable constraints.
- **Probability**: 5 (Very High) - Constraints are real and confirmed
- **Impact**: 2 (Low-Medium) - Limits options but doesn't block entire project
- **Risk Score**: 10 (HIGH)
- **Mitigation Strategy**:
  - Accept some systems as "Do Not Touch" and design around them
  - Build integration layers to modernize around immovable objects
  - Factor vendor constraints into architecture decisions
  - Negotiate with MES vendor for API access or schedule coordination
  - Long-term plan to reduce vendor dependencies
- **Contingency Plan**: Accept constraints as permanent; focus modernization elsewhere
- **Owner**: IT Director Sarah Mitchell
- **Status**: Accepted - Design around constraints
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-009: Test Environment Inadequacy Prevents Validation
- **Category**: Technical
- **Description**: Test environment is 6 months stale with 30% missing data. Testing proves nothing because it doesn't match production. Environment provisioning takes 3+ months. Cannot safely test migrations.
- **Probability**: 5 (Very High) - Current state confirmed
- **Impact**: 3 (Medium) - Increases risk but solvable with cloud
- **Risk Score**: 15 (HIGH)
- **Mitigation Strategy**:
  - Cloud environments as Phase 0 / early win
  - Provision production-equivalent test environments immediately
  - Automate environment refresh with anonymized production data
  - Make environment modernization prerequisite for migration
- **Contingency Plan**: Extended pilot phases; more conservative cutover approach
- **Owner**: Infrastructure Manager Kevin Martinez
- **Status**: Open - Should be early priority
- **Source**: Interview 2 (Sarah Mitchell)

---

### RISK-010: SOC 2 Deadline Pressure Creates Shortcuts
- **Category**: Compliance / Timeline
- **Description**: Detroit Dynamics SOC 2 mandate by end of 2026 is immovable (30% of revenue). Deadline pressure could force shortcuts that create technical debt or security issues.
- **Probability**: 3 (Medium) - Depends on actual timeline feasibility
- **Impact**: 4 (High) - Could lose customer or create new problems
- **Risk Score**: 12 (HIGH)
- **Mitigation Strategy**:
  - Interview Detroit Dynamics to verify requirements and timeline flexibility
  - Understand minimum viable compliance vs. full modernization
  - Separate "compliance requirements" from "nice-to-have modernization"
  - Prioritize compliance-critical changes first
  - Get external SOC 2 consultant early to guide requirements
- **Contingency Plan**: Implement compliance controls in existing system if modernization timeline slips
- **Owner**: CTO Michael Chen
- **Status**: Open - Need customer interview
- **Source**: Interview 1 (Michael Chen)

---

### RISK-011: Hardware EOL Failure Forces Emergency Response
- **Category**: Infrastructure
- **Description**: 60% of servers past EOL, buying parts on eBay. Critical hardware failure could force emergency cloud migration under worst conditions (reactive vs. planned).
- **Probability**: 3 (Medium) - Increasing over time
- **Impact**: 4 (High) - Unplanned migration is expensive and risky
- **Risk Score**: 12 (HIGH)
- **Mitigation Strategy**:
  - Complete hardware EOL risk assessment (Interview Kevin Martinez)
  - Identify highest-risk systems and prioritize their migration
  - Emergency cloud migration plan for critical systems
  - Maintain spare parts inventory for short-term
  - Accelerate infrastructure modernization workstream
- **Contingency Plan**: Emergency cloud lift-and-shift if hardware fails; accept sub-optimal architecture temporarily
- **Owner**: Infrastructure Manager Kevin Martinez
- **Status**: Open - Need infrastructure assessment
- **Source**: Interview 2 (Sarah Mitchell)

---

## Medium Risks (Score 5-9)

### RISK-012: SAP Trauma Paralyzes Decision-Making
- **Category**: Organizational
- **Description**: 2018 SAP failure created "transformation = failure" mindset. Any setback could trigger panic and project cancellation even if normal project challenge.
- **Probability**: 3 (Medium) - Depends on how well expectations are managed
- **Impact**: 3 (Medium) - Slows decisions, creates over-caution
- **Risk Score**: 9 (MEDIUM)
- **Mitigation Strategy**:
  - Explicitly acknowledge SAP lessons and how this is different
  - Apply documented lessons from SAP failure
  - Incremental approach with working software at each step
  - Transparent communication about challenges
  - Build confidence through early wins
- **Contingency Plan**: Bring in external credibility (consultants, peer company testimonials)
- **Owner**: CTO Michael Chen
- **Status**: Monitoring
- **Source**: Interview 1 (Michael Chen), Interview 2 (Sarah Mitchell)

---

### RISK-013: Unrealistic Cost Reduction Expectations
- **Category**: Financial
- **Description**: PE firm expects 50% operational cost reduction. Cloud will cost MORE short-term. If board expects immediate savings and gets bills, project could be killed.
- **Probability**: 4 (High) - Expectations are misaligned
- **Impact**: 2 (Low-Medium) - Can be managed with proper communication
- **Risk Score**: 8 (MEDIUM)
- **Mitigation Strategy**:
  - Model short-term costs vs. long-term savings with realistic timeline
  - Reset board expectations BEFORE project starts
  - Show cost reduction path: Year 1 = investment, Year 2 = break-even, Year 3+ = savings
  - Identify early cost reduction opportunities (eliminate redundant systems)
- **Contingency Plan**: Show ROI in operational efficiency rather than direct cost reduction initially
- **Owner**: CFO Jennifer Walsh + CTO Michael Chen
- **Status**: Open - CFO interview critical
- **Source**: Interview 1 (Michael Chen), Interview 2 (Sarah Mitchell)

---

### RISK-014: Downtime During Migration Violates Constraints
- **Category**: Operational
- **Description**: Michael promises "zero impact," but Sarah says only 4 hours Sunday morning available. Major migration in 208 hours/year (4hrs × 52 weeks) may be mathematically impossible.
- **Probability**: 3 (Medium) - Depends on migration strategy
- **Impact**: 3 (Medium) - Delays, costs, but manageable with parallel running
- **Risk Score**: 9 (MEDIUM)
- **Mitigation Strategy**:
  - Interview VP Operations for TRUE downtime tolerance
  - Design for parallel running (old + new systems simultaneously)
  - Accept temporary cost increase for zero-downtime approach
  - Regional/phased rollout to minimize risk per cutover
  - Advanced preparation to maximize use of maintenance windows
- **Contingency Plan**: Extended migration timeline; accept longer parallel running period
- **Owner**: VP Operations Robert Turner
- **Status**: Open - Need VP Ops interview
- **Source**: Interview 1 (Michael Chen), Interview 2 (Sarah Mitchell)

---

### RISK-015: Factory Floor Systems Integration Breaks Manufacturing
- **Category**: Technical / Operational
- **Description**: PLC integration uses proprietary protocol, vendor out of business. MES system constraints. Any changes to shop floor systems could halt production.
- **Probability**: 2 (Low) - Can be avoided with proper design
- **Impact**: 5 (Critical) - Production halt is existential
- **Risk Score**: 10 (MEDIUM-HIGH)
- **Mitigation Strategy**:
  - Interview Lisa Chen (Manufacturing IT) for detailed constraints
  - Designate shop floor systems as "Do Not Touch" initially
  - Build abstraction layer for future flexibility
  - Extensive testing in non-production environment
  - Pilot on non-critical production line first
- **Contingency Plan**: Never touch factory floor systems; modernize everything around them
- **Owner**: Manufacturing IT Lisa Chen
- **Status**: Open - Need manufacturing IT interview
- **Source**: Interview 2 (Sarah Mitchell)

---

## Risk Trends

**Increasing Risks**:
- RISK-011: Hardware EOL (failure probability increases monthly)
- RISK-003: Knowledge loss (best people actively looking)

**Stable Risks**:
- RISK-008: Vendor constraints (not changing)
- RISK-005: Black box components (known issue)

**Decreasing Risks** (with mitigation):
- RISK-009: Test environment (solvable with cloud)
- RISK-012: SAP trauma (fades with early wins)

---

## Risk Acceptance

Some risks must be accepted as constraints:
- Vendor lock-ins (RISK-008) - Design around them
- Factory floor constraints (RISK-015) - Don't touch initially
- Union considerations (RISK-006) - Work within framework

---

## Next Risk Review

**After Interview 3 (CFO Jennifer Walsh)**:
- Update RISK-001 (Budget cut) with CFO perspective
- Update RISK-013 (Cost expectations) with budget reality
- Add any new financial risks identified

**After Interview 4 (VP Operations Robert Turner)**:
- Update RISK-006 (Union) with operational perspective
- Update RISK-014 (Downtime) with true tolerance
- Add any operational risks identified

---

## Risk Response Summary

| Risk ID | Risk Name | Response Strategy | Owner | Target Date |
|---------|-----------|-------------------|-------|-------------|
| RISK-001 | Budget Cut | Interview CFO, reset expectations | Michael Chen | Interview 3 |
| RISK-002 | Shadow IT | Comprehensive discovery | Sarah Mitchell | Phase 0 |
| RISK-003 | Knowledge Loss | Retention plan, documentation | Sarah Mitchell | Immediate |
| RISK-004 | Timeline Mismatch | Align expectations | Michael Chen | Before board |
| RISK-005 | Black Box Components | Complete inventory | Raj Patel | Interview 6 |
| RISK-006 | Union Issues | Engage union early | Robert Turner | Interview 4 |
| RISK-007 | Skills Gap | Assessment + training plan | Sarah Mitchell | Phase 0 |
| RISK-008 | Vendor Lock-in | Accept as constraint | Sarah Mitchell | Accepted |
| RISK-009 | Test Environment | Cloud environments | Kevin Martinez | Early priority |
| RISK-010 | SOC 2 Deadline | Verify with customer | Michael Chen | Soon |
| RISK-011 | Hardware EOL | Infrastructure assessment | Kevin Martinez | Interview 5 |
| RISK-012 | SAP Trauma | Apply lessons, early wins | Michael Chen | Ongoing |
| RISK-013 | Cost Expectations | Model costs accurately | Jennifer Walsh | Interview 3 |
| RISK-014 | Downtime | Parallel running strategy | Robert Turner | Interview 4 |
| RISK-015 | Factory Floor | Don't touch initially | Lisa Chen | Interview 7 |

---

**Document Control**  
**Created**: 2025-11-04  
**Last Updated**: 2025-11-04  
**Next Review**: After Interview 3 (CFO)  
**Version**: 1.0
