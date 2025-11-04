# Working Notes - Azure Modernization Discovery

**Last Updated**: 2025-11-04 (After Interview 1 - CTO)

## After Interview 1 (Michael Chen - CTO)

### New Themes Emerged

- **PE Ownership Pressure**: Stratton Partners has specific playbook and timeline expectations (30% efficiency in 3 years)
- **Customer Compliance Mandates**: Detroit Dynamics SOC 2 requirement is existential (30% of revenue)
- **Insurance/Security Crisis**: Cyber insurance at risk, ransomware near-miss
- **SAP Trauma**: Failed implementation created organizational PTSD about large transformations
- **Technical Debt Criticality**: SQL 2008, no logging, shared accounts - complete security failure
- **Operational Fragility**: 6-hour batch processes failing twice monthly, affecting production
- **Hero Culture Problem**: IT team keeping things alive through heroic efforts, but burning out

### Key Insights

1. **This is NOT optional** - Three forcing functions: PE ownership, customer requirements, security/insurance
2. **Phased approach is mandatory** - SAP failure makes big-bang impossible politically
3. **90-day wins required** - Need visible success to maintain support
4. **People challenge as big as technical** - Sarah's buy-in critical, team lacks cloud skills
5. **Cost reduction pressure intense** - 50% operational cost reduction expected in 18 months
6. **Zero tolerance for production impact** - $10,000 per minute downtime

### Contradictions/Tensions Identified

- **Speed vs. Safety**: PE wants fast results, but operations can't tolerate disruption
- **Innovation vs. Capability**: Need cloud transformation but team lacks skills
- **Cost Reduction vs. Investment**: Expected to cut costs while spending on transformation
- **Modernize vs. Maintain**: Must keep brittle integrations working while rebuilding

### Critical Success Factors Emerging

1. Phased migration with early wins
2. Sarah Mitchell's support and knowledge
3. Board confidence (presentation success)
4. No production disruption
5. Meet SOC 2 timeline
6. Show cost reduction quickly

### Risk Factors Identified

- Unknown shadow IT systems
- Undocumented integrations
- Team resistance/capability gaps
- CFO skepticism from past failure
- Timeline pressure vs. complexity reality
- Brittle EDI partner integrations

### Questions for Next Interviews

**For Sarah Mitchell (IT Director)**:

- What are the truly critical "cannot fail" systems?
- Where are the undocumented dependencies hiding?
- What would need to happen for you to feel confident about cloud migration?
- What specific concerns do you have about your team's future?
- What broke during the SAP implementation that we must avoid?

**For Jennifer Walsh (CFO)**:

- What would you need to see to believe this won't be another SAP?
- What's the realistic budget envelope for this transformation?
- How do you want to see ROI demonstrated?
- What cost reduction is truly expected vs. aspirational?

**For Robert Turner (VP Operations)**:

- What's the real tolerance for downtime?
- Which systems absolutely cannot change?
- What operational improvements would make the biggest impact?
- How do we handle union concerns about automation?

## Problem Statement - Initial Fragments

### The Problem (Emerging Understanding)

Contoso Manufacturing's 15-year-old custom ERP and supporting systems have reached a critical inflection point where technical debt, security vulnerabilities, and operational limitations threaten the company's viability. Three converging factors make immediate action necessary:

1. **Revenue at Risk**: Largest customer (30% of revenue) mandating SOC 2 compliance by 2026, which current systems cannot achieve
2. **Operational Degradation**: Core batch processes taking 6+ hours nightly, failing bi-monthly, impacting production
3. **Security/Insurance Crisis**: Cyber insurance at risk of cancellation, ransomware near-miss, zero security controls

### Root Cause (Preliminary)

Years of deferred maintenance and incremental band-aids created a brittle, undocumented system architecture where any change risks production. The 2018 SAP failure created organizational paralysis around transformation, leading to "heroic maintenance" culture rather than modernization.

### Business Impact (Quantifying)

- **Revenue Risk**: $90M (30% of $300M) at stake with Detroit Dynamics
- **Productivity Loss**: ~$250K/month from batch processing delays
- **Operational Cost**: IT spending growing 15% YoY while business grows 8%
- **Opportunity Cost**: Unable to capture real-time operational data for decision making
- **Security Exposure**: Potential for total business disruption from ransomware

### Success Criteria (Early Definition)

- Achieve SOC 2 Type II certification by Q4 2026
- Reduce IT operational costs by 50% within 18 months
- Achieve 99.9% uptime for customer-facing systems
- Enable real-time operational visibility
- Reduce batch processing time by 75%
- Zero production disruption during migration

## Next Interview Priority

**Sarah Mitchell (IT Director)** - Critical to understand:

- Technical reality and hidden complexities
- Her genuine readiness for change
- Where the bodies are buried
- What can actually be done vs. aspirational goals

## After Interview 2 (Sarah Mitchell - IT Director)

### New Themes Emerged

- **Hidden Technical Debt**: Hundreds of band-aid solutions, not just a few
- **Black Box Components**: Lost source code for critical COM+ components
- **Shadow IT Crisis**: 30+ Access databases, unknown critical dependencies
- **Team Burnout & Attrition**: Best people leaving, can't attract talent
- **Vendor Lock-ins**: MES system is 2-year/$M to replace, EDI partners won't change
- **Skills Gap is Massive**: Zero Azure experience, 6 months training minimum needed
- **Union Considerations**: Operations is unionized, automation could trigger work stoppages
- **Budget Misalignment**: Michael promises 50% cost reduction, Sarah says short-term costs will increase
- **CFO as Critical Blocker**: Jennifer controls budget and is SAP-traumatized

### Key Insights

1. **Technical Reality is Worse Than Michael Knows**: 47 stored procedures for one field, 847 Crystal Reports, undocumented midnight hotfixes
2. **Sarah is Exhausted but Capable**: She's been proposing solutions for years that were ignored
3. **Team is Fragile**: Losing good people, senior people won't adapt, junior people want cloud resume
4. **"Do Not Touch" List Exists**: PLCs, EDI gateway, payroll, and others that cannot change
5. **Environment Crisis**: Test environment 6 months stale, 30% missing data, testing proves nothing
6. **Capacity is Zero**: 80% maintenance, 20% new work (and she's being generous)
7. **Timeline is Unrealistic**: Michael's 90-day wins vs Sarah's "years not quarters" reality
8. **SAP Lessons are Deep**: She has specific, actionable lessons learned

### Contradictions Identified

- **Michael**: "6 weeks for environment" → **Sarah**: "6 weeks if we're lucky, often 3+ months"
- **Michael**: "50% cost reduction" → **Sarah**: "Cloud will cost MORE short-term"
- **Michael**: "No layoffs, retrain everyone" → **Sarah**: "Some won't/can't adapt, what happens to them?"
- **Michael**: "Sarah must embrace change" → **Sarah**: "I want change, but realistic change"
- **Michael**: "90-day wins" → **Sarah**: "That's marketing, not engineering reality"
- **Michael**: "Phased approach" → **Sarah**: "Yes, but even 'phase 1' is probably 9-12 months"

### Critical New Risks Surfaced

1. **Lost Source Code**: COM+ components cannot be recompiled
2. **Shadow IT Discovery**: Will find critical systems AFTER we break them
3. **Union Work Stoppage**: Automation could trigger labor action
4. **CFO Veto Risk**: Jennifer can kill funding mid-project
5. **Team Exodus During Migration**: Best people leaving right when needed most
6. **Vendor Blackmail**: MES vendor wants $75K/year for schedule coordination
7. **EDI Partner Constraints**: 50+ partners who won't change their side
8. **PLC Protocol Proprietary**: Vendor out of business, can't risk touching it

### Technical Details Uncovered

- 17 systems connect directly to ERP database (no integration layer)
- 3 systems query real-time (every 30 seconds)
- 8 batch integrations (hourly/nightly)
- 847 Crystal Reports (unknown which are critical)
- 30+ Access databases (departmental, mission-critical, undocumented)
- 4-hour maintenance window (Sunday 2-6 AM) - only window available
- $10K+ per minute downtime cost (probably conservative)
- 60% of servers past EOL, buying parts on eBay
- Test environment 6 months stale, 30% missing data
- No automated testing, all manual
- No CI/CD, manual deployments via RDP

### Sarah's Success Criteria (Personal)

- Build things again instead of firefighting
- Team learning and growing, not just surviving
- Proactive dashboards instead of 3 AM pages
- Present solutions instead of constraints
- Modern tech stack to retain talent

### Questions for Next Interviews

**For Jennifer Walsh (CFO)**:

- What's the REAL budget tolerance for this?
- What would make this different from SAP in your eyes?
- How do you want to see ROI demonstrated?
- What level of cost overrun would trigger project kill?

**For Kevin Martinez (Infrastructure Manager)**:

- Hardware EOL details and actual risk level
- What's the real timeline for infrastructure refresh?
- Cloud vs on-prem cost analysis
- DR capability assessment

**For Raj Patel (Lead ERP Developer)**:

- Complete inventory of black box components
- COM+ components that can't be recompiled
- Database dependencies and schema change impact
- Technical debt prioritization

**For Lisa Chen (Manufacturing IT)**:

- Shop floor system dependencies
- PLC integration details and risk
- What absolutely cannot change
- Union concerns about automation

**For Robert Turner (VP Operations)**:

- Real downtime tolerance
- Union perspective on automation
- Which processes are sacrosanct
- Operational improvement priorities
