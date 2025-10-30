# Validator Chatmode

## Purpose
Focused validation and quality assurance sessions using the Validator Agent to ensure Phase 1 completeness and readiness for Phase 2.

## When to Use This Mode
- Validating Phase 1 artifact completeness
- Checking consistency across all artifacts
- Verifying requirements traceability
- Assessing constitution compliance
- Evaluating Phase 2 readiness
- Identifying gaps and issues before implementation
- Creating comprehensive validation reports

## Session Setup

### Before Starting
Load ALL Phase 1 artifacts into context:
1. Constitution (./constitution.md)
2. Spec (./spec.md)
3. Clarifications (./clarifications.md) - if exists
4. PRD (./prd.md)
5. Architecture (./architecture.md)
6. Data Model (./data-model.md)
7. API Spec (./api-spec.json)
8. Phase 0 outputs (problem statement, feasibility report)

### Agent Instructions
Load: `validator-agent.instructions.md`

### Session Goal
Define what you're validating:
- "Full Phase 1 validation for Phase 2 readiness"
- "Validate constitution compliance"
- "Check requirements traceability"
- "Validate [specific artifact] completeness"
- "Assess technical feasibility"

## Interaction Patterns

### Pattern 1: Full Phase 1 Validation Session

**Opening Prompt:**
```
Perform a comprehensive Phase 1 validation using the Validator Agent 
instructions. Review all artifacts and assess:

1. Artifact Completeness (all required sections present)
2. Consistency (cross-artifact alignment)
3. Requirements Traceability (Phase 0 → Phase 1)
4. Constitution Compliance
5. Technical Feasibility
6. Phase 2 Readiness
7. Overall Quality

Generate a complete validation report with:
- Executive summary with overall status
- Detailed findings by category (Critical/Major/Minor)
- Artifact-by-artifact assessment
- Traceability matrix
- Phase 2 readiness checklist
- Recommendations

Be thorough and specific in identifying issues.
```

**Follow-up on Issues:**
```
For Critical Issue #X, provide:
- More details on why this blocks Phase 2
- Specific location in artifacts
- Step-by-step recommendation for resolution
- Who should address this (Analyst/PM/Architect)
```

### Pattern 2: Focused Artifact Validation

**Opening Prompt:**
```
Validate [specific artifact: constitution.md / spec.md / prd.md / 
architecture.md] for:

Completeness:
- All required sections present
- Sufficient detail for Phase 2

Quality:
- Clear and unambiguous language
- Measurable criteria where applicable
- Professional standards

Compliance:
- Follows template structure
- Meets constitution standards (if not constitution itself)
- Aligns with other artifacts

Identify specific gaps, issues, or concerns.
```

**Detailed Section Review:**
```
Review the [specific section] in [artifact]:

Check for:
- Completeness of information
- Clarity of language
- Internal consistency
- Alignment with requirements/constitution
- Missing edge cases or scenarios

Provide specific line-by-line feedback if issues found.
```

### Pattern 3: Consistency Validation Session

**Opening Prompt:**
```
Validate consistency across all Phase 1 artifacts:

1. Spec.md ↔ PRD:
   - All requirements addressed in PRD?
   - PRD priorities align with requirement priorities?
   - MVP scope includes critical requirements?

2. Spec.md ↔ Architecture:
   - All FRs have architectural support?
   - All NFRs addressed in architecture?
   - Data model matches data requirements?

3. PRD ↔ Architecture:
   - MVP features are architecturally feasible?
   - Roadmap aligns with architectural complexity?
   - Product metrics can be tracked?

4. Constitution ↔ All:
   - Architecture meets constitution standards?
   - Quality gates align?
   - Testing strategy matches constitution?

5. Terminology Consistency:
   - Terms used consistently across docs?
   - User roles named consistently?
   - Component names consistent?

Create a consistency report with specific conflicts identified.
```

**Conflict Resolution:**
```
I found these inconsistencies:
[Paste inconsistencies from validation]

For each, recommend:
- Which artifact should be updated
- Specific change needed
- Rationale for the change
```

### Pattern 4: Traceability Validation Session

**Opening Prompt:**
```
Validate complete traceability from Phase 0 through Phase 1:

1. Phase 0 Problem Statement → Spec.md:
   - Every pain point addressed by requirements?
   - All Phase 0 success criteria have corresponding requirements?
   - Scope aligns with Phase 0 recommendations?

2. Spec.md → PRD:
   - All requirements mentioned in PRD (in scope or deferred)?
   - MVP scope covers critical requirements?
   - Deferred items documented with rationale?

3. Spec.md → Architecture:
   - Every FR has implementation support?
   - Every NFR has architectural solution?
   - All integrations designed?

4. Create Traceability Matrix:
   | Phase 0 Item | Spec Requirement | PRD Feature | Architecture Component |
   |--------------|------------------|-------------|------------------------|

Identify coverage gaps.
```

**Gap Analysis:**
```
These Phase 0 pain points don't seem addressed:
[List gaps]

Verify if this is intentional (out of scope) or an oversight.
Recommend action for each.
```

### Pattern 5: Constitution Compliance Check

**Opening Prompt:**
```
Validate all artifacts comply with constitution standards:

For each standard in constitution.md:

**Code Quality Standards**:
- Architecture specifies linting, coverage, complexity limits?
- Standards are measurable?

**Testing Requirements**:
- Architecture includes unit/integration/E2E strategy?
- Coverage targets match constitution?
- Test environments planned?

**Performance Requirements**:
- Architecture meets performance targets?
- Performance testing plan exists?
- Monitoring addresses performance?

**Security Requirements**:
- Security architecture meets constitution policies?
- Auth/encryption designed per standards?
- Security monitoring planned?

**Quality Gates**:
- CI/CD pipeline includes constitution gates?
- Deployment process follows standards?

Report compliance status and specific violations.
```

**Standards Gap:**
```
Constitution requires [specific standard] but I don't see it 
addressed in architecture. Verify if:
1. It's documented elsewhere
2. It's an oversight that needs correction
3. There's a justified exception
```

### Pattern 6: Technical Feasibility Assessment

**Opening Prompt:**
```
Assess technical feasibility of the proposed architecture:

1. Architecture Soundness:
   - Components well-designed?
   - Appropriate design patterns?
   - Scalability approach viable?

2. Technology Choices:
   - Technologies mature and proven?
   - Team has necessary skills?
   - Within budget constraints?

3. NFR Achievement:
   - Performance targets realistic?
   - Security architecture robust?
   - Reliability achievable?

4. Risk Assessment:
   - High-risk areas identified?
   - Mitigations adequate?
   - Contingencies planned?

5. Resource Requirements:
   - Infrastructure costs reasonable?
   - Timeline realistic for complexity?
   - Team size sufficient?

Rate confidence level: High / Medium / Low
Identify feasibility concerns.
```

**Deep Dive on Concerns:**
```
I'm concerned about [specific technical aspect]. Please:
1. Explain the concern in detail
2. Assess probability and impact
3. Recommend mitigation or alternative approach
4. Estimate effort to address
```

### Pattern 7: Phase 2 Readiness Assessment

**Opening Prompt:**
```
Assess readiness to proceed to Phase 2 (Implementation):

Can implementation begin with current artifacts?

Check:
1. Requirements Clarity:
   - FRs are unambiguous?
   - Acceptance criteria are testable?
   - Edge cases documented?

2. Technical Design Clarity:
   - Architecture detailed enough to implement?
   - API contracts complete?
   - Data model implementation-ready?

3. Scope Clarity:
   - MVP features clearly defined?
   - Priorities clear?
   - Dependencies identified?

4. Infrastructure Readiness:
   - Infrastructure requirements defined?
   - CI/CD pipeline designed?
   - Environments planned?

5. Critical Blockers:
   - Any must-resolve issues before starting Phase 2?

Provide clear GO / CONDITIONAL GO / NO-GO recommendation with rationale.
```

**Blockers Analysis:**
```
You identified [X] critical blockers. For each:
1. Why does this block implementation?
2. How long to resolve?
3. Who needs to resolve it?
4. Can work proceed on non-blocked items?
5. What's the risk if we proceed without resolving?
```

### Pattern 8: Quality Assessment Session

**Opening Prompt:**
```
Assess overall quality of Phase 1 artifacts:

For each artifact, rate (Excellent / Good / Acceptable / Needs Improvement / Poor):

**Constitution**: 
- Clarity, completeness, measurability

**Spec**:
- Clarity, completeness, testability

**PRD**:
- Vision clarity, prioritization rationale, metrics

**Architecture**:
- Design soundness, detail level, feasibility

**Data Model**:
- Normalization, completeness, scalability

**API Spec**:
- Completeness, consistency, documentation

Identify quality issues and improvement recommendations.
```

**Quality Improvement:**
```
You rated [artifact] as "Needs Improvement" due to [reasons].

Provide specific, actionable recommendations:
1. What should be improved?
2. How should it be improved?
3. Why is this important?
4. Priority: Must fix / Should fix / Nice to fix
```

### Pattern 9: Iterative Validation Session

**Opening Prompt:**
```
This is a re-validation after addressing previous issues.

Previous validation found:
- [X] Critical issues
- [Y] Major issues
- [Z] Minor issues

Review the updated artifacts and verify:
1. All critical issues resolved?
2. Major issues resolved or accepted as risks?
3. New issues introduced by changes?
4. Overall quality improved?

Generate updated validation report showing:
- Issues resolved
- Issues remaining
- New issues
- Updated readiness assessment
```

## Best Practices for This Mode

### Do's
- ✅ Be thorough and systematic
- ✅ Be specific about issues (location, impact)
- ✅ Distinguish critical from nice-to-have
- ✅ Provide actionable recommendations
- ✅ Think about implementation team's perspective
- ✅ Validate against reality, not perfection
- ✅ Check everything, but be practical
- ✅ Document findings clearly

### Don'ts
- ❌ Don't rubber-stamp without thorough review
- ❌ Don't be pedantic about minor issues
- ❌ Don't block on nice-to-haves
- ❌ Don't provide vague feedback
- ❌ Don't suggest new requirements (validate what exists)
- ❌ Don't ignore context and constraints
- ❌ Don't forget about Phase 2 developers' needs

## Session Outputs

### Primary Artifact
- **validation-report.md** with:
  - Executive summary (status, confidence, key findings)
  - Validation results by category
  - Detailed findings (Critical/Major/Minor)
  - Artifact-by-artifact assessment
  - Traceability matrix
  - Constitution compliance report
  - Technical feasibility assessment
  - Phase 2 readiness checklist
  - Recommendations

### Supporting Documents
- Issue logs categorized by severity
- Consistency matrices
- Traceability matrices
- Compliance checklists

## Quality Checks Before Ending Session

- [ ] All artifacts reviewed systematically
- [ ] Issues categorized by severity (Critical/Major/Minor)
- [ ] Each issue has specific location and recommendation
- [ ] Consistency across artifacts validated
- [ ] Traceability from Phase 0 verified
- [ ] Constitution compliance checked
- [ ] Technical feasibility assessed
- [ ] Phase 2 readiness determined
- [ ] Overall status is clear (GO/CONDITIONAL/NO-GO)
- [ ] Validation report is comprehensive and actionable

## Example Session Flow

```
USER: Validate all Phase 1 artifacts for readiness to proceed to Phase 2.

AGENT (Validator): I'll perform a comprehensive Phase 1 validation. Let me 
systematically review all artifacts...

**Step 1: Artifact Completeness Check**

Constitution.md: ✅ Complete
- All 9 required sections present
- Core principles defined (6 principles)
- Quality standards measurable

Spec.md: ⚠️ Mostly complete
- 15 functional requirements documented
- All have acceptance criteria
- ❌ ISSUE: FR-007 missing edge cases
- ❌ ISSUE: NFR-003 not measurable ("fast" is vague)

PRD.md: ✅ Complete
- Product vision clear
- 3 personas defined
- RICE prioritization applied
- MVP scope defined

Architecture.md: ⚠️ Needs review
- System architecture designed
- ✅ Components well-defined
- ❌ CRITICAL: NFR-003 performance target not addressed
- ⚠️ MAJOR: Integration with Legacy System lacks error handling

[Continues through all artifacts]

**Step 2: Consistency Validation**

Cross-checking Spec.md ↔ Architecture.md:
- ❌ CRITICAL: FR-012 (real-time notifications) in spec but no 
  architecture for push notifications in architecture.md
- ✅ All other FRs have architectural support

[Continues with consistency checks]

**Step 3: Traceability**

Phase 0 Pain Point #1: "Manual data entry causes errors"
→ Spec.md: FR-004 (Auto-populate fields)
→ PRD: MVP Phase 1
→ Architecture: Customer Service component
✅ Full traceability

Phase 0 Pain Point #2: "Slow response times"
→ Spec.md: NFR-001 (API < 200ms)
→ PRD: Primary success metric
→ Architecture: ❌ NO SPECIFIC ARCHITECTURE FOR THIS
❌ CRITICAL: Traceability break

[Continues]

**VALIDATION SUMMARY**:

Critical Issues: 3
1. FR-012 real-time notifications has no architecture
2. NFR-001 performance target not addressed in architecture
3. NFR-003 is not measurable

Major Issues: 2
1. Legacy system integration lacks error handling
2. FR-007 missing edge cases

Minor Issues: 4
[List]

**Phase 2 Readiness: CONDITIONAL GO**

Can proceed IF:
1. Critical issues #1 and #2 resolved (add architecture)
2. Critical issue #3 resolved (make NFR measurable)
3. Major issues accepted as known risks OR resolved

Timeline to resolve: 2-3 days
Owner: Architect Agent for #1, #2; Analyst Agent for #3

USER: For Critical Issue #1, what specifically needs to be added?

AGENT: For FR-012 (real-time notifications), the architecture.md needs:

1. **Component Addition**: WebSocket service or SignalR hub
2. **Infrastructure**: WebSocket support in Azure App Service
3. **Client Connection**: How frontend maintains connection
4. **Message Flow**: Sequence diagram of notification flow
5. **Scalability**: How it scales with Redis backplane
6. **Failure Handling**: Reconnection logic, missed notifications

This should be added to architecture.md Section 3 (System Architecture)
and possibly Section 8 (Integration Architecture).

Estimated effort: 4-6 hours of architecture work.

[Validation continues]
```

## Tips for Effective Sessions

### Be Systematic
- Follow the validation process step-by-step
- Use checklists
- Don't skip sections
- Document as you go

### Prioritize Ruthlessly
- Not all issues are equal
- Critical = blocks Phase 2
- Major = significant impact
- Minor = quality improvement

### Think Like an Implementer
- Will developers understand this?
- Are there hidden ambiguities?
- Will they have questions?
- Is anything missing?

### Be Specific
- Point to exact locations
- Explain the impact
- Provide actionable recommendations
- Show examples of good alternatives

### Validate Iteratively
- Don't wait until everything is done
- Validate artifacts as they're completed
- Catch issues early
- Re-validate after fixes

## Common Challenges & Solutions

**Challenge**: Too many issues to track
**Solution**: Use severity categories, focus on critical first

**Challenge**: Unsure if something is an issue or acceptable
**Solution**: Document as concern, let stakeholders decide

**Challenge**: Issues span multiple artifacts
**Solution**: Document in all affected artifacts, cross-reference

**Challenge**: Pressure to approve despite issues
**Solution**: Clearly state risks of proceeding, let stakeholders decide

**Challenge**: Unclear who should fix issues
**Solution**: Assign to appropriate agent role (Analyst/PM/Architect)

**Challenge**: Validation taking too long
**Solution**: Focus on critical path, use checklists, timebox

## Session Templates

### Full Validation Template
```
Perform comprehensive Phase 1 validation:

1. Completeness Check (all artifacts, all sections)
2. Consistency Validation (cross-artifact alignment)
3. Traceability Verification (Phase 0 → Phase 1)
4. Constitution Compliance (all standards met)
5. Technical Feasibility (architecture sound)
6. Phase 2 Readiness (can implementation start)
7. Quality Assessment (professional standards)

Generate complete validation report with:
- Executive summary
- Issues by severity
- Recommendations
- GO/CONDITIONAL/NO-GO decision
```

### Quick Artifact Review Template
```
Review [specific artifact] for:
- Completeness (all sections present)
- Quality (clarity, detail, professionalism)
- Consistency (aligns with other artifacts)
- Compliance (follows template and standards)

Provide:
- Status (Approved / Needs Revision / Rejected)
- Strengths
- Issues found
- Recommendations
```

### Readiness Check Template
```
Quick Phase 2 readiness check:

Critical questions:
1. Are all requirements clear and testable?
2. Is architecture detailed enough to implement?
3. Are there any must-resolve blockers?
4. Do we have everything needed to start coding?

Answer: GO / CONDITIONAL GO / NO-GO
If conditional or no-go, list blockers and resolution path.
```

---

*Chatmode for: Validator Agent*
*Use for: Phase 1 validation and quality assurance*
*Session length: 60-90 minutes for full validation*
