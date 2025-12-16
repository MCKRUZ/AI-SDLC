# Quick Track Configuration

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Configuration for Quick Track methodology  
**Location**: `.sdlc/config/quick-track_config.md`

---

## Overview

Quick Track is designed for well-understood, low-risk changes that don't require formal discovery or extensive planning. It optimizes for speed while maintaining minimum quality standards.

---

## Track Parameters

### Time Budgets

| Activity | Maximum Time |
|----------|--------------|
| Problem clarification | 30 minutes |
| Tech spec creation | 1-2 hours |
| Technical review | 30 minutes |
| Total planning | 4 hours max |

### Effort Limits

- **Maximum project effort**: 2 weeks (80 hours)
- **If exceeds**: Escalate to Standard Track

---

## Artifact Requirements

### Required Artifacts

```yaml
artifacts:
  required:
    - name: tech-spec-lite
      template: tech-spec-lite_template.md
      location: projects/[project]/artifacts/
      approvers: [tech-lead]
      
  optional:
    - name: rollback-plan
      condition: production-change
      template: rollback-plan_template.md
      
    - name: architecture-impact
      condition: shared-components-affected
      template: architecture-impact_template.md
```

### Tech Spec Lite Structure

```markdown
# Tech Spec: [Title]

## Problem Summary
[2-3 sentences max]

## Proposed Solution
[Bullet points - what we're building]

## Implementation Approach
[How we'll build it - key technical decisions]

## Files/Components Affected
[List of files/modules that will change]

## Testing Approach
[How we'll verify it works]

## Risks & Concerns
[Any risks, even if minor]

## Estimated Effort
[Hours/days]
```

---

## Agent Configuration

### Active Agents

```yaml
agents:
  active:
    - name: analyst
      mode: lite
      instructions: analyst-agent_instructions.md
      sections_to_use:
        - "Quick Assessment"
        - "Tech Spec Creation"
        - "Risk Identification"
      sections_to_skip:
        - "Full Requirements Discovery"
        - "User Story Creation"
        - "Acceptance Criteria Development"
        
  inactive:
    - discovery-facilitator
    - feasibility-analyzer
    - pm-agent
    - architect-agent (unless architecture-impact needed)
    - constitution-agent
    - cost-estimator
    - resource-planner
```

### Agent Behavior Modifiers

```yaml
behavior:
  analyst:
    verbosity: low
    artifact_detail: minimal
    question_depth: shallow
    iteration_limit: 1
    skip_validation: false
```

---

## Quality Gates

### Minimum Quality Checks

```yaml
quality_gates:
  - name: tech-spec-complete
    checks:
      - problem_stated: true
      - solution_defined: true
      - implementation_outlined: true
      - testing_approach_defined: true
      - effort_estimated: true
    required: true
    
  - name: technical-review
    checks:
      - reviewed_by_tech_lead: true
      - no_blocking_concerns: true
    required: true
    
  - name: risk-acknowledged
    checks:
      - risks_identified_or_none: true
    required: true
```

### Skip These Validations

```yaml
skip_validations:
  - feasibility_assessment
  - stakeholder_alignment
  - cost_estimation
  - resource_planning
  - sprint_planning
  - full_architecture_review
```

---

## Escalation Triggers

### Automatic Escalation to Standard Track

If any of these occur during Quick Track execution:

```yaml
escalation_triggers:
  automatic:
    - condition: effort_exceeds_2_weeks
      action: pause_and_recommend_standard
      
    - condition: stakeholder_disagreement_discovered
      action: pause_and_recommend_standard
      
    - condition: significant_architecture_impact
      action: pause_and_recommend_standard
      
    - condition: compliance_requirement_discovered
      action: pause_and_recommend_standard
      
    - condition: problem_more_complex_than_expected
      action: pause_and_recommend_standard

  recommended:
    - condition: multiple_integration_points_discovered
      action: suggest_standard_track
      
    - condition: data_model_changes_needed
      action: suggest_standard_track
```

### Escalation Message Template

```markdown
## Track Escalation Recommendation

During Quick Track execution, I've identified factors suggesting this project 
needs more planning depth:

**Trigger**: [What triggered the escalation]

**Details**: [Specific information]

**Recommendation**: Escalate to Standard Track

**Impact of Escalation**:
- Additional planning time: 2-5 days
- Additional artifacts: PRD, Architecture
- Better risk mitigation

**Your Options**:
1. Accept escalation → Switch to Standard Track
2. Continue Quick Track → Acknowledge increased risk
3. Descope → Reduce project scope to fit Quick Track

What would you like to do?
```

---

## Workflow Shortcuts

### Quick Track Workflow

```markdown
## Quick Track Workflow (4 hours max)

1. **Problem Clarification** (30 min)
   - What exactly needs to change?
   - Why is this change needed?
   - What's the expected outcome?

2. **Solution Design** (1 hour)
   - What's the technical approach?
   - What files/components are affected?
   - Are there any dependencies?

3. **Tech Spec Creation** (1 hour)
   - Document using tech-spec-lite template
   - Keep it concise - bullet points preferred

4. **Technical Review** (30 min)
   - Review with tech lead
   - Address any concerns
   - Get approval

5. **Implementation Planning** (30 min)
   - Break into tasks (if needed)
   - Estimate hours
   - Identify testing approach

→ Ready for Implementation
```

---

## Templates

### Tech Spec Lite Template Location

```
.sdlc/primitives/templates/quick-track/tech-spec-lite_template.md
```

### Rollback Plan Template Location

```
.sdlc/primitives/templates/quick-track/rollback-plan_template.md
```

---

## Session Management

### Context Loading

```yaml
context_loading:
  always_load:
    - organization_context.md (summary only)
    - technical-stack_context.md (relevant sections)
    
  never_load:
    - prior-projects_memory.md
    - lessons-learned_memory.md
    - full phase configs
    
  load_on_demand:
    - specific component documentation
    - API specifications
```

### Session Length

- **Target**: Single session (2-4 hours)
- **Maximum**: 2 sessions
- **If exceeds**: Consider escalation

---

## Reporting

### Quick Track Completion Report

```markdown
# Quick Track Completion

**Project**: [Name]
**Date**: [Date]
**Track**: Quick

## Summary
- Problem: [1 sentence]
- Solution: [1 sentence]
- Effort: [X hours]
- Duration: [Y days]

## Artifacts Produced
- [x] Tech Spec Lite

## Quality Checks Passed
- [x] Tech spec complete
- [x] Technical review approved
- [x] Risks acknowledged

## Notes
[Any relevant notes for future reference]
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
