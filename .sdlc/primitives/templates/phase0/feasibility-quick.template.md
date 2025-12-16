# Quick Feasibility Assessment

**Version**: 1.0  
**Purpose**: Abbreviated feasibility check for Standard Track projects  
**Location**: `.sdlc/primitives/templates/phase0/feasibility-quick.template.md`

---

## When to Use

Use this template for **Standard Track** projects that need feasibility validation but don't require the full Enterprise-level assessment. This template provides a 1-2 page feasibility check versus the comprehensive multi-page report.

For Quick Track: Skip feasibility (requirements are crystal clear)  
For Enterprise Track: Use the full `feasibility-report.template.md`

---

## Template

```markdown
# Quick Feasibility Assessment

**Project**: [Project name]  
**Date**: [YYYY-MM-DD]  
**Assessor**: [Name/Agent]  
**Track**: Standard

---

## Project Summary

**Problem Statement** (2-3 sentences):
[What problem are we solving?]

**Proposed Solution** (2-3 sentences):
[What are we building to solve it?]

**Estimated Effort**: [X weeks/months]  
**Estimated Team Size**: [X people]

---

## Technical Feasibility

**Can we build this?**

| Factor | Assessment | Notes |
|--------|------------|-------|
| Technology maturity | ✅ Proven / ⚠️ Emerging / ❌ Experimental | [Brief note] |
| Team expertise | ✅ Strong / ⚠️ Learning needed / ❌ Gap | [Brief note] |
| Integration complexity | ✅ Low / ⚠️ Medium / ❌ High | [Brief note] |
| Technical risk | ✅ Low / ⚠️ Medium / ❌ High | [Brief note] |

**Technical Verdict**: ✅ Feasible / ⚠️ Feasible with caveats / ❌ Not feasible

**Key Technical Concerns** (if any):
- [Concern 1]
- [Concern 2]

---

## Business Feasibility

**Should we build this?**

| Factor | Assessment | Notes |
|--------|------------|-------|
| Business value | ✅ Clear / ⚠️ Moderate / ❌ Unclear | [Brief note] |
| User need validated | ✅ Yes / ⚠️ Partially / ❌ No | [Brief note] |
| ROI expectation | ✅ Positive / ⚠️ Break-even / ❌ Negative | [Brief note] |
| Strategic alignment | ✅ Aligned / ⚠️ Tangential / ❌ Misaligned | [Brief note] |

**Business Verdict**: ✅ Feasible / ⚠️ Feasible with caveats / ❌ Not feasible

**Key Business Concerns** (if any):
- [Concern 1]
- [Concern 2]

---

## Resource Feasibility

**Do we have capacity?**

| Factor | Assessment | Notes |
|--------|------------|-------|
| Team availability | ✅ Available / ⚠️ Constrained / ❌ Unavailable | [Brief note] |
| Skills coverage | ✅ Complete / ⚠️ Gaps exist / ❌ Major gaps | [Brief note] |
| Budget (if applicable) | ✅ Sufficient / ⚠️ Tight / ❌ Insufficient | [Brief note] |
| Dependencies | ✅ None/Low / ⚠️ Some / ❌ Many | [Brief note] |

**Resource Verdict**: ✅ Feasible / ⚠️ Feasible with caveats / ❌ Not feasible

**Key Resource Concerns** (if any):
- [Concern 1]
- [Concern 2]

---

## Timeline Feasibility

**Can we deliver in time?**

| Factor | Assessment | Notes |
|--------|------------|-------|
| Deadline pressure | ✅ Comfortable / ⚠️ Tight / ❌ Unrealistic | [Brief note] |
| Scope vs time | ✅ Balanced / ⚠️ Ambitious / ❌ Impossible | [Brief note] |
| External dependencies | ✅ None/Low / ⚠️ Some / ❌ Blocking | [Brief note] |

**Timeline Verdict**: ✅ Feasible / ⚠️ Feasible with caveats / ❌ Not feasible

**Key Timeline Concerns** (if any):
- [Concern 1]
- [Concern 2]

---

## Overall Assessment

### Feasibility Summary

| Dimension | Verdict |
|-----------|---------|
| Technical | [✅/⚠️/❌] |
| Business | [✅/⚠️/❌] |
| Resource | [✅/⚠️/❌] |
| Timeline | [✅/⚠️/❌] |

### Recommendation

**[ ] GO** - Proceed to Phase 1 specification

**[ ] CONDITIONAL GO** - Proceed with these conditions:
- [Condition 1]
- [Condition 2]

**[ ] POC NEEDED** - Validate these unknowns first:
- [Unknown 1]
- [Unknown 2]

**[ ] NO-GO** - Do not proceed because:
- [Reason 1]
- [Reason 2]

---

## Key Risks (Top 3)

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Risk 1] | H/M/L | H/M/L | [Brief mitigation] |
| [Risk 2] | H/M/L | H/M/L | [Brief mitigation] |
| [Risk 3] | H/M/L | H/M/L | [Brief mitigation] |

---

## Next Steps

If GO or CONDITIONAL GO:
1. [Next step 1]
2. [Next step 2]
3. [Next step 3]

If POC NEEDED:
1. [POC activity 1]
2. [POC activity 2]
3. Reassess after POC

---

## Sign-off

| Role | Name | Date | Decision |
|------|------|------|----------|
| Technical Lead | [Name] | [Date] | [GO/NO-GO] |
| Product Owner | [Name] | [Date] | [GO/NO-GO] |
```

---

## Completion Checklist

Before finalizing this assessment:

- [ ] All four dimensions assessed (Technical, Business, Resource, Timeline)
- [ ] Each dimension has a clear verdict
- [ ] Key concerns documented
- [ ] Top 3 risks identified
- [ ] Clear recommendation made
- [ ] Next steps defined
- [ ] Appropriate stakeholders signed off

---

## When to Escalate to Full Feasibility

Consider using the full `feasibility-report.template.md` if:

- Multiple ❌ verdicts appear
- More than 5 significant concerns identified
- Stakeholders request deeper analysis
- Project is being considered for Enterprise Track upgrade
- Budget approval requires formal documentation

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
