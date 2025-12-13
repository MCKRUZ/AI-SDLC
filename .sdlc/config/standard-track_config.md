# Standard Track Configuration

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Configuration for Standard Track methodology  
**Location**: `.sdlc/config/standard-track_config.md`

---

## Overview

Standard Track provides balanced planning depth for typical projects. It includes abbreviated discovery, full specification, and standard planning phases. This is the default track for most feature work and small-to-medium projects.

---

## Track Parameters

### Time Budgets

| Phase | Activity | Time Budget |
|-------|----------|-------------|
| Phase 0 | Problem exploration | 4-8 hours |
| Phase 0 | Stakeholder conversations | 2-4 hours (2-3 conversations) |
| Phase 0 | Feasibility quick check | 1-2 hours |
| Phase 1 | PRD creation | 4-8 hours |
| Phase 1 | Architecture design | 4-8 hours |
| Phase 1 | Specification | 4-8 hours |
| Phase 1 | Validation | 2-4 hours |
| Phase 2 | Task breakdown | 2-4 hours |
| Phase 2 | Sprint planning | 2-4 hours |
| **Total** | | **2-5 days** |

### Effort Limits

- **Minimum project effort**: 2 weeks
- **Maximum project effort**: 12 weeks (480 hours)
- **If below minimum**: Consider Quick Track
- **If exceeds maximum**: Consider Enterprise Track

---

## Phase 0: Abbreviated Discovery

### Differences from Enterprise Track

| Aspect | Standard Track | Enterprise Track |
|--------|----------------|------------------|
| Interviews | 2-3 conversations (informal) | 5-11+ structured interviews |
| Transcripts | Summary notes | Full transcripts |
| Feasibility | Quick 1-page check | Full 4-dimension assessment |
| Risk register | Top 3-5 risks | Comprehensive register |
| Stakeholder alignment | Verbal confirmation | Formal sign-off |

### Required Artifacts

```yaml
phase0_artifacts:
  required:
    - name: problem-statement
      template: problem-statement_template.md
      detail_level: standard
      sections:
        - problem_description
        - root_cause_summary  # Single level why, not full Five Whys
        - impact_summary
        - success_criteria_draft
        
    - name: stakeholder-input
      template: stakeholder-input_template.md
      detail_level: summary
      content:
        - key_quotes
        - main_concerns
        - priorities
        # NOT full transcripts
        
    - name: feasibility-quick
      template: feasibility-quick_template.md
      detail_level: abbreviated
      sections:
        - technical_feasibility  # High/Medium/Low with 2-3 bullets
        - business_feasibility   # High/Medium/Low with 2-3 bullets
        - resource_feasibility   # High/Medium/Low with 2-3 bullets
        - recommendation         # GO/CONDITIONAL/POC/NO-GO
        
  optional:
    - name: risk-register-lite
      condition: elevated_risk_identified
      template: risk-register-lite_template.md
```

### Agent Modes

```yaml
phase0_agents:
  discovery-facilitator:
    mode: conversation  # Not interview mode
    skip:
      - formal_interview_protocol
      - jobs_to_be_done_deep_dive
      - full_five_whys_cascade
    include:
      - problem_exploration
      - stakeholder_perspective_gathering
      - quick_root_cause_identification
      
  feasibility-analyzer:
    mode: quick
    skip:
      - detailed_technical_spikes
      - comprehensive_resource_analysis
      - formal_scoring_matrix
    include:
      - high_level_assessment
      - blocker_identification
      - go_no_go_recommendation
```

---

## Phase 1: Full Specification

### Required Artifacts

```yaml
phase1_artifacts:
  required:
    - name: prd
      template: prd_template.md
      detail_level: full
      
    - name: architecture
      template: architecture_template.md
      detail_level: full
      
    - name: constitution
      template: constitution_template.md
      detail_level: full
      
    - name: spec
      template: spec_template.md
      detail_level: full
      
  optional:
    - name: data-model
      condition: significant_data_changes
      template: data-model_template.md
      
    - name: api-spec
      condition: new_api_endpoints
      template: api-spec_template.json
      
    - name: adrs
      condition: significant_architectural_decisions
      location: adrs/
```

### Agent Configuration

```yaml
phase1_agents:
  analyst-agent:
    mode: full
    
  pm-agent:
    mode: full
    
  architect-agent:
    mode: full
    
  constitution-agent:
    mode: full
    
  validator-agent:
    mode: full
```

---

## Phase 2: Standard Planning

### Required Artifacts

```yaml
phase2_artifacts:
  required:
    - name: task-breakdown
      template: task-breakdown_template.md
      detail_level: standard
      
    - name: sprint-plan
      template: sprint-plan_template.md
      detail_level: standard
      
  optional:
    - name: dependency-map
      condition: complex_dependencies
      
    - name: test-plan
      condition: elevated_risk_or_complexity
```

### Agent Configuration

```yaml
phase2_agents:
  planning-agent:
    mode: standard
    skip:
      - cost_estimation  # Not required for Standard Track
      - resource_planning  # Not required for Standard Track
      - detailed_capacity_analysis
    include:
      - task_decomposition
      - sprint_planning
      - basic_dependency_identification
      
  # These agents NOT active in Standard Track:
  inactive:
    - cost-estimator
    - resource-planner
    - devops-scaffolder  # Optional, on-demand only
    - quality-architect  # Optional, on-demand only
```

---

## Quality Gates

### Phase 0 → Phase 1 Gate

```yaml
phase0_completion:
  required_checks:
    - problem_statement_exists: true
    - stakeholder_input_gathered: true
    - feasibility_assessment_complete: true
    - feasibility_recommendation: [GO, CONDITIONAL_GO]
    
  blocking_conditions:
    - feasibility_recommendation: NO_GO
    - critical_blocker_unresolved: true
```

### Phase 1 → Phase 2 Gate

```yaml
phase1_completion:
  required_checks:
    - prd_complete: true
    - architecture_complete: true
    - constitution_complete: true
    - spec_complete: true
    - prd_approved: true
    - architecture_reviewed: true
    
  blocking_conditions:
    - critical_requirement_unclear: true
    - architecture_concern_unresolved: true
```

### Phase 2 → Implementation Gate

```yaml
phase2_completion:
  required_checks:
    - task_breakdown_complete: true
    - sprint_plan_complete: true
    - team_capacity_confirmed: true
    
  blocking_conditions:
    - unestimated_tasks_exist: true
    - blocking_dependencies_unresolved: true
```

---

## Escalation Triggers

### Escalate to Enterprise Track

```yaml
escalation_triggers:
  automatic:
    - condition: stakeholder_misalignment_discovered
      action: pause_and_recommend_enterprise
      
    - condition: compliance_requirement_discovered
      action: pause_and_recommend_enterprise
      
    - condition: effort_exceeds_12_weeks
      action: pause_and_recommend_enterprise
      
    - condition: cost_estimate_required
      action: pause_and_recommend_enterprise
      
    - condition: formal_approval_required
      action: pause_and_recommend_enterprise

  recommended:
    - condition: problem_more_complex_than_expected
      action: suggest_enterprise_track
      
    - condition: multiple_competing_priorities
      action: suggest_enterprise_track
```

### De-escalate to Quick Track

```yaml
deescalation_triggers:
  - condition: scope_reduced_significantly
    action: suggest_quick_track
    
  - condition: problem_becomes_crystal_clear
    action: suggest_quick_track
```

---

## Session Management

### Context Loading

```yaml
context_loading:
  phase0:
    always_load:
      - organization_context.md
      - technical-stack_context.md
    optional:
      - prior-projects_memory.md (if similar project exists)
      
  phase1:
    always_load:
      - phase0 artifacts (problem-statement, feasibility-quick)
      - organization_context.md
      - technical-stack_context.md
    optional:
      - relevant prior project artifacts
      
  phase2:
    always_load:
      - phase1 artifacts (prd, architecture, spec)
      - constitution
    optional:
      - phase0 artifacts (for traceability)
```

### Session Recommendations

| Phase | Recommended Sessions | Max Sessions |
|-------|---------------------|--------------|
| Phase 0 | 1-2 | 3 |
| Phase 1 | 2-4 | 6 |
| Phase 2 | 1-2 | 3 |

### Bridge Prompts

Use bridge prompts when continuing across sessions:

```markdown
## Session Continuation

**Project**: [Name]
**Track**: Standard
**Current Phase**: [Phase]
**Session**: [N of M]

**Previous Session Summary**:
[Key accomplishments]

**Current State**:
[What's complete, what's in progress]

**This Session Focus**:
[What we're working on]

**Context Files Loaded**:
[List of loaded files]
```

---

## Workflow Summary

```markdown
## Standard Track Workflow Summary

### Phase 0: Abbreviated Discovery (4-8 hours)
1. Problem exploration conversation
2. 2-3 stakeholder input sessions
3. Quick feasibility assessment
4. Problem statement creation
→ Gate: Problem validated, feasibility GO/CONDITIONAL

### Phase 1: Full Specification (2-3 days)
1. PRD creation (with PM Agent)
2. Architecture design (with Architect Agent)
3. Constitution definition (with Constitution Agent)
4. Technical specification (with Analyst Agent)
5. Validation review (with Validator Agent)
→ Gate: All artifacts approved

### Phase 2: Standard Planning (0.5-1 day)
1. Task breakdown
2. Sprint planning
3. Team alignment
→ Gate: Ready for implementation

### Total: 2-5 days
```

---

## Artifact Connections

```
┌─────────────────┐
│ Problem         │
│ Statement       │
└────────┬────────┘
         │ informs
         ▼
┌─────────────────┐     ┌─────────────────┐
│ PRD             │────▶│ Architecture    │
│                 │     │                 │
└────────┬────────┘     └────────┬────────┘
         │                       │
         │ both inform           │
         ▼                       ▼
┌─────────────────────────────────────────┐
│              Specification               │
│  (User Stories + Acceptance Criteria)   │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│           Task Breakdown                 │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│            Sprint Plan                   │
└─────────────────────────────────────────┘
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
