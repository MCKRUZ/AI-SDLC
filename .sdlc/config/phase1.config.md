# Phase 1: Specification & Design Configuration

**Version**: 1.0  
**Last Updated**: 2025-10-31  
**Status**: Active  
**Scope**: Phase 1 - Specification & Design

---

## Purpose of This Configuration

This configuration file controls all aspects of the Phase 1 specification and design process, including:
- Agent behavior and preferences (Analyst, PM, Architect, Constitution Agent, Validator)
- Requirements discovery methodologies
- Architecture design approaches
- Quality standards and thresholds
- Workflow orchestration settings
- Artifact creation and validation
- Traceability requirements
- Handoff criteria to Phase 2

---

## General Phase 1 Settings

### Phase 1 Mode

**Current Mode**: `collaborative-iterative`

**Available Modes**:
- `collaborative-iterative` - Agents work together with human oversight and iteration
- `sequential-handoff` - Complete one artifact before starting next
- `parallel-tracks` - Requirements and architecture proceed in parallel (advanced)

**Mode Selection Criteria**:
- Use `collaborative-iterative` for: Most projects, balanced approach, good for learning
- Use `sequential-handoff` for: Simple projects, waterfall-style, risk-averse orgs
- Use `parallel-tracks` for: Experienced teams, time-constrained, well-understood domains

---

### Session Management

**Session Duration Preferences**:
- **Requirements sessions**: 90-120 minutes per major feature area
- **Architecture sessions**: 120-180 minutes for initial design, 60-90 for refinement
- **Constitution sessions**: 60-90 minutes for initial creation
- **PRD sessions**: 90-120 minutes
- **Validation sessions**: 60-90 minutes per artifact, 120-180 for full Phase 1 validation

**Session Splitting Strategy**:
- **Maximum context window usage**: 75% (leave room for refinement)
- **Auto-split triggers**: 
  - Conversation exceeds 20,000 tokens
  - Switching between major artifacts (spec → architecture)
  - Moving from creation to validation mode
  - Phase transition (Phase 1 → Phase 2)

**Session Naming Convention**: `session-NNN-[project-name]-[artifact]-[activity]`
- Examples: `session-003-customer-portal-spec-requirements`, `session-004-customer-portal-architecture-design`

**Concurrent Sessions**: 
- **Allowed**: Yes (up to 2 artifacts in parallel)
- **Limitation**: Don't create constitution and spec simultaneously (spec informs constitution)
- **Isolation**: Separate sessions per artifact type

---

### Version Control

**Working File Strategy**: `[artifact]-v[N].md` in `working/` directory

**Version Numbering**:
- **v1**: Initial draft
- **v2-vN**: Iterative refinements based on feedback
- **vFinal**: Validated and approved version moved to `artifacts/`

**When to Increment Version**:
- Major structural changes
- Significant additions/removals
- Stakeholder feedback incorporation
- Phase gate validation

**Retention Policy**: Keep all versions until project completion

---

## Agent-Specific Settings

### Analyst Agent Configuration

**Requirements Methodology**: `jobs-to-be-done + user-stories`

**Available Methodologies**:
- `jobs-to-be-done` - Focus on user motivations and outcomes
- `user-stories` - Traditional agile user stories
- `use-cases` - Detailed scenario-based requirements
- `jobs-to-be-done + user-stories` (recommended) - Hybrid approach

**Requirements Elicitation Technique**: `five-whys + scenario-walkthrough`

**Story Format**: `As a [persona], I want to [action], so that [outcome]`

**Acceptance Criteria Format**: `Given-When-Then` (Gherkin-style)

**Quality Standards**:
- **INVEST compliance**: Minimum score 12/18 (all criteria scored 2+)
- **Acceptance criteria**: Minimum 3 per user story
- **Edge cases**: Minimum 2 identified per complex story
- **Dependencies**: Explicitly documented for all stories

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `prior-projects_memory.md` - Load if similar projects exist
- ✅ `phase0/artifacts/problem-statement.final.md` - Always load
- ✅ `phase0/artifacts/success-criteria.md` - Always load

---

### PM Agent Configuration

**Prioritization Framework**: `RICE`

**Available Frameworks**:
- `RICE` - Reach, Impact, Confidence, Effort
- `MoSCoW` - Must have, Should have, Could have, Won't have
- `Value-vs-Effort` - 2x2 matrix prioritization
- `Kano Model` - Delighters vs. performance vs. basic needs

**MVP Definition Approach**: `core-value-first`

**Available Approaches**:
- `core-value-first` - Minimal features to deliver core value
- `walking-skeleton` - End-to-end but minimal functionality
- `feature-parity` - Match existing solution minimally

**PRD Style**: `concise-actionable`

**Available Styles**:
- `concise-actionable` - Brief with clear action items
- `comprehensive-detailed` - In-depth with extensive context
- `executive-focused` - High-level with business emphasis

**Success Metrics**:
- **Business metrics**: Minimum 3 quantifiable KPIs
- **User metrics**: Minimum 2 behavioral/satisfaction metrics
- **Technical metrics**: Minimum 2 performance/quality metrics

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `phase0/artifacts/problem-statement.final.md` - Always load
- ✅ `phase0/artifacts/feasibility-report.md` - Always load
- ✅ `phase1/working/spec-vN.md` - Always load latest
- ✅ `decisions_memory.md` - Always load

---

### Architect Agent Configuration

**Architecture Style**: `pragmatic-evolutionary`

**Available Styles**:
- `pragmatic-evolutionary` - Start simple, evolve as needed
- `enterprise-upfront` - Comprehensive design before implementation
- `microservices-first` - Service-oriented from the start
- `monolith-first` - Start monolithic, extract services later

**Documentation Framework**: `C4-model`

**Available Frameworks**:
- `C4-model` - Context, Container, Component, Code
- `4+1-views` - Logical, Process, Physical, Development, Scenarios
- `arc42` - Comprehensive template-based documentation

**Technology Selection Criteria**:
- **Team familiarity**: Weight 30%
- **Community support**: Weight 20%
- **Performance requirements**: Weight 25%
- **Long-term viability**: Weight 15%
- **Cost considerations**: Weight 10%

**Decision Documentation**: `architecture-decision-records (ADRs)`

**ADR Format**: 
```markdown
# ADR NNN: [Decision Title]
Date: [YYYY-MM-DD]
Status: [Proposed|Accepted|Superseded]
Context: [What led to this decision]
Decision: [What we decided]
Consequences: [Positive and negative impacts]
Alternatives Considered: [Other options evaluated]
```

**NFR Decomposition**: `required`

**NFR Categories** (all must be addressed):
- ✅ Performance (response times, throughput)
- ✅ Scalability (user load, data volume)
- ✅ Security (authentication, authorization, data protection)
- ✅ Reliability (uptime, fault tolerance)
- ✅ Maintainability (code quality, documentation)
- ✅ Operability (monitoring, deployment, support)

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `prior-projects_memory.md` - Load for patterns/lessons
- ✅ `phase0/artifacts/feasibility-report.md` - Always load
- ✅ `phase1/working/spec-vN.md` - Always load latest
- ✅ `decisions_memory.md` - Always load

---

### Constitution Agent Configuration

**Constitution Scope**: `comprehensive`

**Available Scopes**:
- `minimal` - Core values and must-haves only
- `balanced` - Values, must-haves, and key anti-patterns
- `comprehensive` - Full coverage including nice-to-haves

**Decision Framework**: `explicit-criteria`

**Framework Style**:
- `explicit-criteria` - Structured decision trees with thresholds
- `principle-based` - High-level principles guide decisions
- `example-driven` - Case studies and precedents

**Constraint Documentation**: `exhaustive`

**Levels**:
- `exhaustive` - Document all constraints with rationale
- `critical-only` - Focus on blockers and must-haves
- `practical` - Balance detail with usability

**Update Frequency**: As decisions emerge (living document)

**Context Loading**:
- ✅ `organization_context.md` - Always load
- ✅ `technical-stack_context.md` - Always load
- ✅ `phase0/artifacts/` - All Phase 0 artifacts
- ✅ `phase1/working/spec-vN.md` - Latest spec
- ✅ `phase1/working/architecture-vN.md` - Latest architecture
- ✅ `decisions_memory.md` - Always load

---

### Validator Agent Configuration

**Validation Approach**: `comprehensive-with-recommendations`

**Available Approaches**:
- `comprehensive-with-recommendations` - Full validation plus improvement suggestions
- `compliance-only` - Pass/fail against standards
- `risk-focused` - Prioritize high-risk areas

**Validation Depth**: `deep`

**Levels**:
- `surface` - Structure and completeness
- `standard` - Structure, completeness, and consistency
- `deep` - Full quality assessment with cross-artifact traceability

**Traceability Requirements**: `full-forward-backward`

**Options**:
- `none` - No traceability validation
- `forward-only` - Phase 0 → Phase 1 tracing
- `full-forward-backward` - Bidirectional tracing with coverage

**Failure Threshold**: `zero-critical`

**Thresholds**:
- `zero-critical` - No critical issues allowed (recommended)
- `low-risk` - Max 2 critical issues with mitigation plan
- `balanced` - Max 3 critical, max 10 major issues

**Scoring System**:

**Issue Severity**:
- **Critical** (9-10): Blocks Phase 2, must fix
- **Major** (6-8): Significant risk, should fix
- **Minor** (3-5): Quality improvement, fix if time
- **Trivial** (1-2): Optional enhancement

**Artifact Quality Scoring** (0-100 scale):
- **90-100**: Excellent - Proceed to Phase 2
- **80-89**: Good - Minor refinements recommended
- **70-79**: Acceptable - Requires improvements before Phase 2
- **Below 70**: Inadequate - Significant rework required

**Context Loading**:
- ✅ ALL Phase 0 artifacts
- ✅ ALL Phase 1 working and artifact files
- ✅ `organization_context.md`
- ✅ `technical-stack_context.md`
- ✅ `phase1_config.md` (this file)
- ✅ All relevant checklists

---

## Workflow Orchestration Settings

### Requirements Discovery Workflow

**Entry Criteria**:
- ✅ Phase 0 completed and validated
- ✅ Problem statement finalized
- ✅ Feasibility confirmed
- ✅ Stakeholder availability confirmed

**Process Steps** (from `requirements-discovery_prompt.md`):
1. Context loading and orientation
2. Stakeholder interviews and elicitation
3. Requirements documentation (user stories)
4. Acceptance criteria definition
5. Edge case identification
6. Dependencies mapping
7. INVEST validation
8. Review and refinement iteration

**Iteration Limit**: 3 major iterations maximum

**Approval Gate**: 
- **Reviewers**: Product Owner, Key Stakeholders
- **Criteria**: INVEST score ≥12, all critical edge cases covered
- **Format**: Written approval in `validation/spec-approval.md`

**Output Artifacts**:
- ✅ `spec.md` (final version in `artifacts/`)
- ✅ `requirements-traceability.md` (links to Phase 0)

---

### Architecture Design Workflow

**Entry Criteria**:
- ✅ Requirements specification validated (spec.md in artifacts/)
- ✅ Technical stack confirmed
- ✅ NFRs defined in spec

**Process Steps** (from `architecture-design_prompt.md`):
1. Context and requirements review
2. C4 Context diagram (system in environment)
3. C4 Container diagram (major components)
4. Technology selection with ADRs
5. Data model design
6. API specification
7. NFR decomposition and design decisions
8. Validation against requirements

**Technology Selection**:
- **Spike required if**: Confidence < 70% on key technology choice
- **Spike duration**: 2-5 days maximum
- **Spike output**: `technical-spike-[name].md` with findings and recommendation

**Approval Gate**:
- **Reviewers**: Technical Lead, Principal Architect (if available)
- **Criteria**: All NFRs addressed, technologies justified, patterns validated
- **Format**: Written approval in `validation/architecture-approval.md`

**Output Artifacts**:
- ✅ `architecture.md` (C4 diagrams and decisions)
- ✅ `data-model.md`
- ✅ `api-spec.json` (OpenAPI format)
- ✅ `adrs/` directory with all ADRs

---

### Constitution Creation Workflow

**Entry Criteria**:
- ✅ Spec validated
- ✅ Architecture at least 70% complete

**Process Steps**:
1. Review all Phase 0 and Phase 1 artifacts
2. Extract key decisions and constraints
3. Document values and principles
4. Define quality standards
5. Create decision frameworks
6. Document anti-patterns
7. Validate completeness

**Constitution Sections** (all required):
- ✅ Project Vision & Values
- ✅ Non-Negotiables (Must Haves)
- ✅ Nice-to-Haves (Aspirational)
- ✅ Anti-Patterns (Must Not Do)
- ✅ Decision Framework (How to Decide)
- ✅ Quality Standards
- ✅ Dependencies & Constraints

**Approval Gate**:
- **Reviewers**: Project Sponsor, Technical Lead, Product Owner
- **Criteria**: Aligned with Phase 0/1, comprehensive, actionable
- **Format**: Written approval in `validation/constitution-approval.md`

**Output Artifacts**:
- ✅ `constitution.md` (final version in `artifacts/`)

---

### PRD Creation Workflow

**Entry Criteria**:
- ✅ Spec validated
- ✅ Architecture validated
- ✅ Constitution created

**Process Steps**:
1. Synthesize spec and architecture into product narrative
2. Define MVP scope using prioritization framework
3. Document success metrics (business, user, technical)
4. Create release strategy
5. Document assumptions and dependencies
6. Risk assessment
7. Validate against constitution

**MVP Definition**:
- **Must include**: All "Must Have" requirements from spec
- **Should include**: High-RICE "Should Have" requirements
- **May defer**: "Could Have" and "Won't Have" requirements

**Approval Gate**:
- **Reviewers**: Product Owner, Business Stakeholder
- **Criteria**: MVP viable, metrics measurable, risks acceptable
- **Format**: Written approval in `validation/prd-approval.md`

**Output Artifacts**:
- ✅ `prd.md` (final version in `artifacts/`)
- ✅ `mvp-scope.md` (explicit MVP boundaries)

---

### Phase 1 Validation Workflow

**Entry Criteria**:
- ✅ All Phase 1 artifacts in `artifacts/` directory
- ✅ All individual artifact approvals obtained

**Process Steps** (from `phase-1-completion_checklist.md`):
1. Load all Phase 1 artifacts and Phase 0 artifacts
2. Validate completeness (all required artifacts present)
3. Validate consistency (no contradictions across artifacts)
4. Validate traceability (Phase 0 → Phase 1 → requirements)
5. Validate quality (all artifacts meet scoring thresholds)
6. Generate traceability matrix
7. Create validation report
8. Obtain final Phase 1 approval

**Traceability Matrix Requirements**:
- **Phase 0 → Phase 1**: Every problem/need has corresponding requirements
- **Phase 1 Internal**: Requirements → Architecture components
- **Coverage**: 100% of critical requirements, 90%+ of all requirements

**Validation Report Contents**:
- ✅ Checklist completion status
- ✅ Quality scores per artifact
- ✅ Issue summary (by severity)
- ✅ Traceability coverage metrics
- ✅ Recommendation (Proceed | Revise | Block)

**Approval Gate**:
- **Reviewers**: Phase 1 Validator + All prior approvers
- **Criteria**: 
  - All checklists 100% complete
  - All artifacts score ≥80
  - Zero critical issues
  - Traceability ≥90%
- **Format**: Written approval in `validation/phase1-validation-report.md`

**Output Artifacts**:
- ✅ `validation/phase1-completion-checklist.md` (completed)
- ✅ `validation/phase1-validation-report.md`
- ✅ `validation/traceability-matrix.md`
- ✅ `validation/phase1-approval.md` (final sign-off)

---

## Quality Standards and Thresholds

### Artifact Quality Scoring

**Spec.md**:
- **Structure** (20 points): All required sections present and well-organized
- **Clarity** (20 points): Clear, unambiguous language
- **Completeness** (20 points): All user stories, acceptance criteria, edge cases
- **Consistency** (15 points): No contradictions, consistent terminology
- **Traceability** (15 points): Links to Phase 0 artifacts
- **Quality** (10 points): INVEST compliance (avg ≥2 per story)

**Minimum Passing Score**: 80/100

---

**Architecture.md**:
- **Coverage** (20 points): All architectural concerns addressed
- **Clarity** (20 points): C4 diagrams clear and complete
- **Justification** (20 points): Technology choices well-reasoned (ADRs)
- **NFRs** (20 points): All non-functional requirements addressed
- **Consistency** (10 points): Aligned with spec and constitution
- **Practicality** (10 points): Feasible to implement

**Minimum Passing Score**: 80/100

---

**Constitution.md**:
- **Comprehensiveness** (25 points): All required sections complete
- **Clarity** (20 points): Clear, actionable guidance
- **Alignment** (25 points): Consistent with Phase 0 and Phase 1
- **Practicality** (15 points): Realistic and enforceable
- **Completeness** (15 points): Decision framework covers common scenarios

**Minimum Passing Score**: 80/100

---

**PRD.md**:
- **Clarity** (20 points): Product vision and scope clear
- **MVP Definition** (20 points): MVP well-defined and justified
- **Metrics** (20 points): Success metrics specific and measurable
- **Completeness** (20 points): All required sections complete
- **Alignment** (10 points): Consistent with spec, arch, constitution
- **Feasibility** (10 points): Realistic timeline and scope

**Minimum Passing Score**: 80/100

---

### INVEST Scoring (User Stories)

Each criterion scored 0-3:
- **3**: Excellent - fully meets criterion
- **2**: Good - mostly meets criterion
- **1**: Weak - partially meets criterion
- **0**: Poor - does not meet criterion

**Criteria**:
- **I**ndependent: Can be developed/tested without dependencies
- **N**egotiable: Flexible, can adjust implementation details
- **V**aluable: Delivers user/business value
- **E**stimable: Can reasonably estimate effort
- **S**mall: Completable in one sprint
- **T**estable: Clear acceptance criteria enable testing

**Minimum Story Score**: 12/18 (all criteria ≥2)
**Target Average**: 15/18

---

### Traceability Coverage

**Phase 0 → Phase 1 Spec**:
- **Critical items**: 100% coverage required
- **High items**: 95% coverage required
- **Medium/Low items**: 85% coverage required

**Spec → Architecture**:
- **Functional requirements**: 100% coverage required
- **Non-functional requirements**: 100% coverage required
- **Constraints**: 100% coverage required

**Untraceable Items**: Require explicit justification (documented as decision)

---

## Handoff Criteria to Phase 2

Phase 1 is **complete and ready for Phase 2** when:

### Artifact Completion
- ✅ `spec.md` in `artifacts/` with approval
- ✅ `architecture.md` in `artifacts/` with approval
- ✅ `data-model.md` in `artifacts/`
- ✅ `api-spec.json` in `artifacts/`
- ✅ `constitution.md` in `artifacts/` with approval
- ✅ `prd.md` in `artifacts/` with approval
- ✅ All ADRs documented in `adrs/`

### Validation Complete
- ✅ Phase 1 validation report generated
- ✅ All checklists 100% complete
- ✅ Traceability matrix shows ≥90% coverage
- ✅ All artifacts score ≥80
- ✅ Zero critical issues (severity 9-10)
- ✅ All major issues (severity 6-8) have mitigation plans

### Approvals Obtained
- ✅ Spec approval from Product Owner
- ✅ Architecture approval from Technical Lead
- ✅ Constitution approval from Project Sponsor
- ✅ PRD approval from Business Stakeholder
- ✅ Final Phase 1 approval from Validator

### Context Prepared
- ✅ `phase1-context.md` updated with final state
- ✅ `decisions_memory.md` updated with Phase 1 decisions
- ✅ Phase 2 transition brief created
- ✅ Phase 2 team notified and briefed

---

## Customization Guidelines

### When to Modify This Config

**Adjust Agent Settings** when:
- Team expertise changes (different methodologies)
- Project complexity varies significantly
- Organizational standards evolve
- Lessons learned suggest improvements

**Adjust Workflows** when:
- Process inefficiencies identified
- New phase gates needed
- Integration points change
- Tool capabilities change

**Adjust Quality Standards** when:
- Historical data shows thresholds too strict/lenient
- Risk tolerance changes
- Time constraints require adjustment
- Team maturity improves

### How to Modify

1. **Document the change**: Why, what, expected impact
2. **Update this config**: Make changes explicit
3. **Communicate to team**: Ensure all stakeholders aware
4. **Update related files**: Agents, workflows, templates
5. **Record in decisions**: Add to `decisions_memory.md`
6. **Validate**: Test on next project phase
7. **Retrospective**: Evaluate effectiveness after 1-2 projects

---

## Version History

| Version | Date | Changed By | Changes | Reason |
|---------|------|------------|---------|--------|
| 1.0 | 2025-10-31 | System Architect | Initial creation | Phase 1 system establishment |

---

## Related Files

**Agent Instructions**:
- `analyst-agent_instructions.md`
- `pm-agent_instructions.md`
- `architect-agent_instructions.md`
- `constitution-agent_instructions.md`
- `validator-agent_instructions.md`

**Workflow Prompts**:
- `requirements-discovery_prompt.md`
- `architecture-design_prompt.md`
- `risk-assessment_prompt.md`

**Templates**:
- `spec_template.md`
- `prd_template.md`
- `constitution_template.md`
- `architecture_template.md`

**Checklists**:
- `phase-1-completion_checklist.md`

**Context**:
- `phase1-context.md` (current state of Phase 1)

---

*This configuration file governs Phase 1 execution. Treat as living document - update based on learnings and evolving needs.*
