# Estimation Standards Context

**Purpose**: Defines organizational policies, best practices, and standards for software project estimation.

**Last Updated**: 2025-11-07  
**Owner**: Delivery Excellence / PMO  
**Review Cycle**: Semi-Annual

---

## 🔧 CONFIGURATION GUIDE

This file defines **how your organization estimates projects**. Customize:

1. **Estimation Techniques** - Which methods for which project types
2. **Accuracy Targets** - Expected precision by estimation fidelity
3. **Contingency Standards** - Risk buffer policies
4. **Validation Gates** - Quality checkpoints and approval thresholds
5. **Historical Baseline** - Reference data from past projects

**All estimation workflows reference this file** for organizational standards.

---

## Estimation Philosophy

### Core Principles

**1. Progressive Elaboration**
- Estimates improve as information increases
- Early estimates have wider ranges
- Refinement happens at phase gates

**2. Multiple Fidelity Levels**
- ROM (Rough Order of Magnitude): ±50% accuracy
- Budget: ±25% accuracy
- Detailed: ±10% accuracy
- Rolling Wave: Continuous refinement

**3. Evidence-Based Estimation**
- Use historical data when available
- Analogous projects provide baselines
- Industry benchmarks supplement
- Gut feel is last resort

**4. Risk-Informed Contingency**
- Contingency based on uncertainty factors
- Documented assumptions
- Clear accountability for reserve usage

**5. Estimation ≠ Commitment**
- Estimates are forecasts, not promises
- Commitments require estimates + negotiation
- Approved contingency is part of commitment

---

## 🔧 Estimation Technique Selection

### By Project Size (Total Investment)

| Project Size | ROM Technique | Budget Technique | Detailed Technique |
|--------------|---------------|------------------|--------------------|
| **<$250K** | Expert judgment + historical | Parametric (story points) | Bottom-up (task-based) |
| **$250K-$1M** | Analogous projects | Parametric + analogous | Bottom-up (work packages) |
| **$1M-$5M** | Parametric (size drivers) | Analogous + bottom-up | Bottom-up (granular WBS) |
| **>$5M** | Reference class + parametric | Bottom-up (high-level) | Bottom-up + Monte Carlo |

### By Project Type

| Type | Primary Technique | Secondary Technique | Validation Method |
|------|-------------------|---------------------|-------------------|
| **New Development** | Story points → hours | Analogous reference | Expert review |
| **Cloud Migration** | Asset inventory parametric | Analogous projects | Technical validation |
| **System Integration** | Interface points × complexity | Analogous + parametric | Architecture review |
| **Legacy Modernization** | Code volume analysis | Historical rewrites | Technical spike |
| **Product Customization** | Customization % × base | Vendor estimates | Proof of concept |
| **Data Migration** | Record volume × complexity | Historical migrations | Pilot migration |

### By Estimation Phase

**Phase 0 (Discovery)**:
- **Technique**: Analogous + expert judgment
- **Accuracy Target**: ±50% (ROM)
- **Purpose**: Go/no-go decision, budget planning
- **Effort**: 2-5% of estimated project cost

**Phase 1 (Specification)**:
- **Technique**: Parametric + analogous
- **Accuracy Target**: ±25% (Budget)
- **Purpose**: Funding approval, contract negotiation
- **Effort**: 5-10% of estimated project cost

**Phase 2 (Planning)**:
- **Technique**: Bottom-up WBS
- **Accuracy Target**: ±10% (Detailed)
- **Purpose**: Baseline, resource allocation, tracking
- **Effort**: Included in project execution

**During Execution**:
- **Technique**: Rolling wave
- **Accuracy Target**: ±5% for next 2 sprints
- **Purpose**: Sprint planning, adaptive management
- **Effort**: Continuous, part of ceremonies

---

## 🔧 Accuracy Standards by Fidelity

### ROM (Rough Order of Magnitude)

**Accuracy Target**: -25% to +75% (or -40% to +100% for high uncertainty)

**Definition**: Initial estimate based on limited information

**Typical Range Expression**:
- Point Estimate: $2M
- Range: $1.5M - $3.5M
- With Confidence: "$1.5M to $3.5M at 80% confidence"

**Required Inputs** (Minimum):
- High-level scope description
- Major system components identified
- Analogous project reference (if available)
- Key constraints understood

**Validation Criteria**:
- ✓ Based on at least one analogous project or parametric model
- ✓ Major assumptions documented
- ✓ Scope boundaries clear
- ✓ Range appropriately wide

**Approval Authority**:
- <$1M: Practice Lead (L5)
- $1M-$5M: Director (L6)
- >$5M: Managing Director (L8)

---

### Budget Estimate

**Accuracy Target**: -15% to +30% (or -10% to +25% with detailed scope)

**Definition**: Refined estimate for funding approval and contracting

**Typical Range Expression**:
- Point Estimate: $2M
- Range: $1.7M - $2.6M
- With Confidence: "$1.7M to $2.6M at 75% confidence"

**Required Inputs** (Minimum):
- Detailed scope definition
- Major user stories or use cases
- Architecture approach defined
- Technology stack selected
- Team structure identified
- Risk register with top 10 risks

**Validation Criteria**:
- ✓ Bottom-up or parametric with historical data
- ✓ All major work streams estimated
- ✓ Dependencies mapped
- ✓ Contingency calculated from risk register
- ✓ Independent review completed

**Approval Authority**:
- <$500K: Senior Manager (L5)
- $500K-$3M: Director (L6)
- >$3M: Senior Director (L7) + Finance

---

### Detailed Estimate

**Accuracy Target**: -5% to +15% (or -5% to +10% for well-understood work)

**Definition**: Comprehensive bottom-up estimate for baseline and tracking

**Typical Range Expression**:
- Point Estimate: $2M
- Range: $1.9M - $2.3M
- With Confidence: "$1.9M to $2.3M at 90% confidence"

**Required Inputs** (Minimum):
- Complete work breakdown structure (WBS)
- All user stories estimated
- Resource plan with named individuals
- Schedule with dependencies
- Risk-adjusted contingency
- Change control process defined

**Validation Criteria**:
- ✓ Bottom-up from task level (<80-hour tasks)
- ✓ All resources identified by name or role
- ✓ Schedule validated with critical path
- ✓ Historical productivity data applied
- ✓ Expert review + team validation

**Approval Authority**:
- <$1M: Program Manager (L5)
- >$1M: Director (L6) + Delivery Lead

---

## 🔧 Contingency Standards

### Contingency Calculation Method

**Formula**:
```
Contingency = Base Estimate × Risk Factor × Confidence Adjustment
```

**Risk Factor** (from risk register):
- Low Risk (1-2 medium risks): 10-15%
- Medium Risk (3-5 medium, 1 high): 20-30%
- High Risk (2+ high, or 1 critical): 35-50%
- Very High Risk (multiple critical): 50-75%

**Confidence Adjustment** (estimation quality):
- High Confidence (>80%, historical data available): 0.8× factor
- Medium Confidence (60-80%, analogous data): 1.0× factor
- Low Confidence (<60%, novel work): 1.2× factor

**Example**: 10,000-hour estimate, 3 medium + 1 high risk, 70% confidence
- Base: 10,000 hours
- Risk Factor: 25% (medium-high risk)
- Confidence: 1.0× (medium confidence)
- **Contingency: 10,000 × 0.25 × 1.0 = 2,500 hours (25%)**

---

### Contingency by Phase

Contingency typically decreases as project progresses:

| Phase | Typical Contingency | Rationale |
|-------|---------------------|-----------|
| **Phase 0 (ROM)** | 40-60% | High uncertainty, limited scope definition |
| **Phase 1 (Budget)** | 25-35% | Scope defined, architecture in progress |
| **Phase 2 (Detailed)** | 15-25% | Detailed planning complete, team formed |
| **Execution Start** | 10-20% | Baselined, but unknowns remain |
| **50% Complete** | 5-10% | Reduced uncertainty, trends established |
| **>75% Complete** | 0-5% | Most risks retired, clear to completion |

**Management Reserve** (Separate from Contingency):
- Contingency: For known-unknown risks (in project estimate)
- Management Reserve: For unknown-unknown risks (held by leadership)
- Typical Management Reserve: 10-15% of (base estimate + contingency)

---

### Contingency Allocation by Risk Type

| Risk Category | % of Total Contingency | Example Allocation (2,500 hrs) |
|---------------|------------------------|-------------------------------|
| **Technical Risks** | 40-50% | 1,000-1,250 hrs |
| **Integration Risks** | 20-30% | 500-750 hrs |
| **Resource Risks** | 15-20% | 375-500 hrs |
| **External Dependencies** | 10-15% | 250-375 hrs |
| **Scope Creep** | 5-10% | 125-250 hrs |

**Contingency Drawdown Process**:
1. Risk materializes → Impact assessed
2. Team proposes mitigation → Effort estimated
3. Manager approves drawdown → Contingency reduced
4. Tracking updated → Remaining contingency visible
5. If contingency depleted → Escalate to change control

---

## 🔧 Historical Baseline Data

### Productivity Benchmarks (Hours per Complexity Point)

**Web Application Development** (per story point):

| Team Experience | Simple (1-3 pts) | Medium (5-8 pts) | Complex (13+ pts) |
|-----------------|------------------|------------------|-------------------|
| **Junior (<2 years avg)** | 8-10 hrs/pt | 10-12 hrs/pt | 12-16 hrs/pt |
| **Mid-level (2-5 years)** | 6-8 hrs/pt | 8-10 hrs/pt | 10-14 hrs/pt |
| **Senior (>5 years)** | 4-6 hrs/pt | 6-8 hrs/pt | 8-12 hrs/pt |

**Example**: 100-point backlog, mid-level team
- Avg: 8 hrs/pt × 100 pts = 800 development hours
- + Testing (30%): 240 hrs
- + Rework/bugs (15%): 150 hrs
- + Requirements clarification (10%): 100 hrs
- **Total: 1,290 hours**

---

### Cloud Migration (per server/application)

| Application Complexity | Assessment | Refactoring | Testing | Migration | Total |
|------------------------|------------|-------------|---------|-----------|-------|
| **Simple** (stateless web) | 20 hrs | 40 hrs | 30 hrs | 10 hrs | 100 hrs |
| **Medium** (DB-backed app) | 40 hrs | 80 hrs | 60 hrs | 20 hrs | 200 hrs |
| **Complex** (integrated system) | 80 hrs | 200 hrs | 120 hrs | 40 hrs | 440 hrs |
| **Critical** (core platform) | 160 hrs | 400 hrs | 240 hrs | 80 hrs | 880 hrs |

**Adjustment Factors**:
- Legacy tech stack (COBOL, AS/400): ×1.5-2.0
- Compliance requirements (HIPAA, PCI): ×1.3-1.5
- Custom protocols/interfaces: ×1.2-1.4
- 24/7 uptime requirement: ×1.3-1.5

**Example**: 50-application portfolio
- 20 simple (20 × 100): 2,000 hrs
- 20 medium (20 × 200): 4,000 hrs
- 8 complex (8 × 440): 3,520 hrs
- 2 critical (2 × 880): 1,760 hrs
- **Subtotal: 11,280 hrs**
- **With PCI compliance (×1.3): 14,664 hrs**

---

### Data Migration (per million records)

| Data Complexity | Profile | Cleanse | Transform | Validate | Load | Total |
|-----------------|---------|---------|-----------|----------|------|-------|
| **Simple** (flat files) | 10 hrs | 20 hrs | 30 hrs | 20 hrs | 10 hrs | 90 hrs |
| **Medium** (relational) | 20 hrs | 40 hrs | 80 hrs | 40 hrs | 20 hrs | 200 hrs |
| **Complex** (hierarchical) | 40 hrs | 100 hrs | 200 hrs | 100 hrs | 40 hrs | 480 hrs |

**Additional Factors**:
- Data quality issues (>10% bad data): +30-50%
- Real-time sync requirements: +40-60%
- Legacy format conversion: +25-40%
- Regulatory validation: +20-30%

---

### Integration Development (per interface)

| Integration Type | Design | Development | Testing | Total |
|------------------|--------|-------------|---------|-------|
| **REST API** (standard) | 16 hrs | 40 hrs | 24 hrs | 80 hrs |
| **SOAP/WS** (enterprise) | 24 hrs | 60 hrs | 36 hrs | 120 hrs |
| **File-based** (batch) | 20 hrs | 50 hrs | 30 hrs | 100 hrs |
| **Message Queue** (async) | 32 hrs | 80 hrs | 48 hrs | 160 hrs |
| **Custom Protocol** | 80 hrs | 200 hrs | 120 hrs | 400 hrs |

**Multipliers**:
- Error handling/retry logic: ×1.2
- Security (OAuth, certificates): ×1.3
- High throughput (>1000 TPS): ×1.4
- Legacy system integration: ×1.5-2.0

---

## 🔧 Validation Gate Standards

### ROM Estimate Validation

**Required Checks**:
- [ ] At least one analogous project reference identified
- [ ] Major scope inclusions/exclusions documented
- [ ] Key assumptions listed (max 10 critical assumptions)
- [ ] Range reflects uncertainty (-25% to +75% minimum)
- [ ] One senior expert has reviewed (L5+)

**Rejection Criteria**:
- ✗ No historical reference or rationale
- ✗ Point estimate without range
- ✗ Assumptions undocumented
- ✗ Outside team's experience domain with no expert input

---

### Budget Estimate Validation

**Required Checks**:
- [ ] Bottom-up or parametric with historical data
- [ ] All major work streams estimated
- [ ] Resource plan shows feasibility (capacity exists)
- [ ] Risk register has ≥10 risks identified
- [ ] Contingency calculated from risks (not arbitrary %)
- [ ] Schedule shows critical path
- [ ] Independent review by non-team expert
- [ ] Client/stakeholder assumptions validated

**Rejection Criteria**:
- ✗ Only top-down estimate without validation
- ✗ Missing major work streams
- ✗ Contingency <15% or >40% without justification
- ✗ No risk register
- ✗ No independent review

---

### Detailed Estimate Validation

**Required Checks**:
- [ ] Complete WBS to task level (<80 hrs per task)
- [ ] All tasks assigned to specific resources or roles
- [ ] Schedule validated with critical path analysis
- [ ] Historical productivity rates applied
- [ ] Risk-adjusted contingency (not flat %)
- [ ] Variance analysis vs. budget estimate (<30% delta)
- [ ] Team has reviewed and validated estimates
- [ ] Expert review completed (architect + PM)
- [ ] Change control process established

**Rejection Criteria**:
- ✗ Tasks >80 hours without breakdown
- ✗ Resources unidentified beyond "TBD"
- ✗ >30% variance from budget without explanation
- ✗ No team validation session
- ✗ Missing critical path

---

## Escalation Thresholds

### When to Escalate Estimates

**Automatic Escalation Triggers**:

| Condition | Escalate To | Action Required |
|-----------|-------------|-----------------|
| **>20% increase from last estimate** | Director (L6) | Variance analysis, re-validation |
| **>$5M total project cost** | Senior Director (L7) | Full review, external validation |
| **Contingency >40%** | Program Manager (L5) | Risk mitigation plan, de-risk |
| **Confidence <60%** | Technical Architect (L5) | Technical spike, proof of concept |
| **Novel technology (no history)** | Practice Lead (L5) | Expert consultation, research |
| **Fixed-price with high risk** | Delivery Lead (L6) | Contract review, risk transfer |

**Escalation Response SLAs**:
- Director review: Within 3 business days
- Senior Director approval: Within 5 business days
- External validation: Within 10 business days

---

## Estimation Anti-Patterns

### Common Mistakes to Avoid

**❌ Anchoring Bias**
- **Problem**: First estimate becomes "truth" regardless of new info
- **Prevention**: Always re-estimate when new information emerges
- **Example**: Discovery reveals 2× complexity → Must update estimate

**❌ Optimism Bias**
- **Problem**: "Best case" becomes "expected case"
- **Prevention**: Force consideration of pessimistic scenarios
- **Example**: "Everything goes perfectly" is not a realistic baseline

**❌ Planning Fallacy**
- **Problem**: Underestimate time for own tasks vs. others' tasks
- **Prevention**: Use external reference classes, historical data
- **Example**: "I can do this in 2 weeks" → Check: Last 5 similar took 4 weeks

**❌ Scope Creep Amnesia**
- **Problem**: Forgetting that scope always grows
- **Prevention**: Include scope creep contingency (5-10%)
- **Example**: "Requirements are locked" → They never are

**❌ Hidden Work Blindness**
- **Problem**: Estimating features, forgetting infrastructure/ops
- **Prevention**: Checklist of non-functional work (DevOps, security, etc.)
- **Example**: Estimated 200 hrs for features, forgot 100 hrs for CI/CD

**❌ False Precision**
- **Problem**: Claiming ±5% accuracy with incomplete information
- **Prevention**: Widen ranges when uncertainty high
- **Example**: ROM estimate given as "$2,347,285" → Use "$2-3M range"

**❌ Effort-Duration Confusion**
- **Problem**: 80 hours of effort ≠ 2 calendar weeks
- **Prevention**: Always factor in productivity (60-70%), meetings (10-20%), delays
- **Example**: 40-hour task ≠ 1 week for most people (more like 1.5-2 weeks)

---

## 🔧 Estimation Templates & Tools

### Quick Reference: Which Template When?

| Scenario | Use Template | Typical Duration to Complete |
|----------|--------------|------------------------------|
| **High-level ballpark** | ROM Estimate Template | 2-4 hours |
| **Funding approval** | Budget Estimate Template | 1-2 days |
| **Detailed baseline** | Detailed Estimate Template | 3-5 days |
| **Ongoing refinement** | Rolling Wave Update | 2-4 hours per sprint |

### Supporting Tools

**Provided in This System**:
- `cost-estimate.template.md` - All estimation fidelities
- `staffing-mix.template.md` - Resource level allocation
- `risk-register.template.md` - Risk-based contingency calculation

**External Tools (Not Included, But Compatible)**:
- Excel/Google Sheets for WBS and rollups
- Project management tools (Jira, ADO, MS Project)
- Monte Carlo simulation tools (Risk+ for complex projects)

---

## Continuous Improvement

### Estimation Accuracy Tracking

**Measure Estimation Quality**:
- Compare estimate to actual at project close
- Calculate variance: (Actual - Estimate) / Estimate
- Target accuracy by phase (see standards above)
- Track by estimator, project type, size

**Example Tracking Table**:

| Project | Estimate Type | Estimated | Actual | Variance | Within Target? |
|---------|---------------|-----------|--------|----------|----------------|
| Project A | Budget | $1.5M | $1.65M | +10% | ✓ Yes (target: ±25%) |
| Project B | Detailed | $800K | $920K | +15% | ✗ No (target: ±10%) |
| Project C | ROM | $3M | $4.2M | +40% | ✓ Yes (target: ±50%) |

**Root Cause Analysis for Variances**:
- What was missed in original estimate?
- Were assumptions invalidated?
- Did scope grow uncontrolled?
- Were productivity assumptions wrong?
- What would improve future estimates?

### Lessons Learned Integration

**After Each Project**:
1. **Capture Actuals** - Final hours/costs by work stream
2. **Compare to Estimate** - Variance analysis by category
3. **Identify Causes** - What drove differences?
4. **Update Baselines** - Incorporate learnings into historical data
5. **Share Knowledge** - Update this standards file quarterly

**Quarterly Standards Update**:
- Review last quarter's project actuals
- Update productivity benchmarks
- Adjust contingency guidelines if needed
- Incorporate new project types/technologies
- Publish updated standards

---

## 🎯 Customization Quick Start

**To Adapt Estimation Standards to Your Organization**:

1. **Update Technique Selection** (20 minutes):
   - Modify project size thresholds for your scale
   - Adjust technique preferences based on your team's strengths
   - Add any proprietary estimation methods you use

2. **Calibrate Accuracy Targets** (15 minutes):
   - Review your historical variance data
   - Adjust ROM/Budget/Detailed targets to your reality
   - Set targets that are challenging but achievable

3. **Revise Contingency Standards** (20 minutes):
   - Align risk factors with your risk tolerance
   - Update contingency ranges based on past over/under
   - Modify confidence adjustments for your context

4. **Import Historical Data** (30-60 minutes):
   - Replace benchmark tables with your actual project data
   - Calculate your team's productivity rates
   - Document your organization's velocity by technology

5. **Customize Validation Gates** (15 minutes):
   - Adjust approval thresholds for your governance
   - Modify escalation triggers for your organization size
   - Update rejection criteria to match your quality bar

**Test Your Configuration**:
- Walk through a recent project estimate using new standards
- Verify all technique selections make sense
- Check that contingency calculation produces reasonable results
- Validate approval thresholds with leadership

**Total Customization Time**: ~2-3 hours for complete adaptation

---

**End of estimation-standards.context.md**