# Enterprise Track Configuration

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Configuration for Enterprise Track methodology (full SDLC)  
**Location**: `.sdlc/config/enterprise-track_config.md`

---

## Overview

Enterprise Track is the full methodology for complex, high-stakes initiatives. It includes complete discovery, comprehensive specification, detailed planning with cost estimation, and full implementation lifecycle support. Use this track when the stakes are high and shortcuts are unacceptable.

---

## Track Parameters

### Time Budgets

| Phase | Activity | Time Budget |
|-------|----------|-------------|
| **Phase 0** | Stakeholder identification | 2-4 hours |
| | Structured interviews (5-11+) | 20-40 hours |
| | Synthesis and analysis | 8-16 hours |
| | Feasibility assessment | 4-8 hours |
| | Risk analysis | 4-8 hours |
| | Documentation | 4-8 hours |
| | Stakeholder review | 4-8 hours |
| **Phase 0 Total** | | **46-92 hours (1-2 weeks)** |
| **Phase 1** | PRD creation | 8-16 hours |
| | Architecture design | 16-32 hours |
| | Constitution definition | 4-8 hours |
| | Technical specification | 8-16 hours |
| | Data modeling | 4-8 hours |
| | API specification | 4-8 hours |
| | ADR documentation | 4-8 hours |
| | Validation | 8-16 hours |
| **Phase 1 Total** | | **56-112 hours (1.5-3 weeks)** |
| **Phase 2** | Cost estimation | 8-16 hours |
| | Resource planning | 8-16 hours |
| | Task breakdown | 8-16 hours |
| | Sprint planning | 4-8 hours |
| | Test planning | 8-16 hours |
| | Environment setup | 8-16 hours |
| | Quality planning | 4-8 hours |
| **Phase 2 Total** | | **48-96 hours (1-2.5 weeks)** |
| **Grand Total** | | **150-300 hours (1-3 weeks planning)** |

### Effort Limits

- **Minimum project effort**: 12 weeks (480 hours)
- **No maximum**: Enterprise Track scales to any size
- **If below minimum**: Consider Standard Track

---

## Phase 0: Full Discovery

### Interview Requirements

```yaml
interviews:
  minimum: 5
  recommended: 7-11
  structure: formal  # Structured interviews with transcripts
  stakeholder_coverage:
    required:
      - executive_sponsor
      - technical_lead
      - end_users (2-3)
    recommended:
      - operations_team
      - support_team
      - compliance_officer
      - finance_representative
```

### Required Artifacts

```yaml
phase0_artifacts:
  required:
    - name: problem-statement
      template: problem-statement_template.md
      detail_level: comprehensive
      includes:
        - full_five_whys_analysis
        - impact_quantification
        - stakeholder_alignment_summary
        
    - name: interview-transcripts
      template: interview-transcript_template.md
      location: interviews/
      count: 5-11+
      
    - name: feasibility-report
      template: feasibility-report_template.md
      detail_level: full
      dimensions:
        - technical_feasibility
        - business_feasibility
        - resource_feasibility
        - timeline_feasibility
        
    - name: risk-register
      template: risk-register_template.md
      detail_level: comprehensive
      minimum_risks: 10
      
    - name: success-criteria
      template: success-criteria_template.md
      
    - name: constraints
      template: constraints_template.md
      
    - name: stakeholder-alignment
      template: stakeholder-alignment_template.md
      includes:
        - stakeholder_matrix
        - approval_chain
        - communication_plan
        
    - name: discovery-synthesis
      template: synthesis-report_template.md
```

### Agent Configuration

```yaml
phase0_agents:
  discovery-facilitator:
    mode: full_interview
    methodology:
      - five_whys
      - jobs_to_be_done
      - structured_interviews
    artifacts:
      - interview_transcripts
      - synthesis_notes
      
  feasibility-analyzer:
    mode: full
    dimensions: 4
    scoring: quantitative
    
  synthesis-agent:
    mode: full
    outputs:
      - problem_statement
      - contradiction_analysis
      - theme_synthesis
```

### Quality Gates

```yaml
phase0_gates:
  discovery_complete:
    checks:
      - minimum_interviews_conducted: 5
      - all_stakeholder_groups_covered: true
      - contradictions_resolved: true
      - problem_statement_approved: true
      
  feasibility_approved:
    checks:
      - recommendation: [GO, CONDITIONAL_GO]
      - all_conditionals_documented: true
      - blocker_mitigations_identified: true
      
  stakeholder_signoff:
    checks:
      - executive_sponsor_approved: true
      - technical_lead_approved: true
```

---

## Phase 1: Full Specification

### Required Artifacts

```yaml
phase1_artifacts:
  required:
    - name: prd
      template: prd_template.md
      detail_level: comprehensive
      
    - name: architecture
      template: architecture_template.md
      detail_level: comprehensive
      includes:
        - c4_all_levels
        - component_specifications
        - integration_designs
        - nfr_decomposition
        
    - name: constitution
      template: constitution_template.md
      detail_level: comprehensive
      
    - name: spec
      template: spec_template.md
      detail_level: comprehensive
      
    - name: data-model
      template: data-model_template.md
      
    - name: api-spec
      template: api-spec_template.json
      format: openapi_3.0
      
    - name: adrs
      location: adrs/
      minimum: 3
      template: adr_template.md
      
    - name: security-review
      template: security-review_template.md
      
    - name: validation-report
      template: phase1-validation_template.md
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
    deliverables:
      - c4_diagrams
      - component_specs
      - integration_designs
      - adrs
      
  constitution-agent:
    mode: full
    
  validator-agent:
    mode: full
    validation_depth: comprehensive
```

### Quality Gates

```yaml
phase1_gates:
  prd_complete:
    checks:
      - all_sections_complete: true
      - mvp_defined: true
      - priorities_set: true
      - approved_by_product_owner: true
      
  architecture_complete:
    checks:
      - c4_diagrams_complete: true
      - all_components_specified: true
      - all_integrations_designed: true
      - nfrs_addressed: true
      - security_review_passed: true
      - approved_by_architecture_lead: true
      
  specification_complete:
    checks:
      - all_user_stories_defined: true
      - acceptance_criteria_complete: true
      - invest_scores_acceptable: true
      - approved_by_team: true
      
  phase1_validation:
    checks:
      - traceability_complete: true
      - no_gaps_identified: true
      - validator_approved: true
```

---

## Phase 2: Full Planning

### Required Artifacts

```yaml
phase2_artifacts:
  required:
    - name: cost-estimate
      template: cost-estimate_template.md
      detail_level: detailed  # ±25% accuracy
      includes:
        - rom_comparison
        - detailed_breakdown
        - assumptions
        - confidence_analysis
        
    - name: resource-plan
      template: resource-plan_template.md
      includes:
        - pod_structure
        - staffing_plan
        - skill_matrix
        - ramp_up_plan
        - ramp_down_plan
        
    - name: task-breakdown
      template: task-breakdown_template.md
      detail_level: comprehensive
      
    - name: sprint-plan
      template: sprint-plan_template.md
      includes:
        - multi_sprint_overview
        - individual_sprint_plans
        - milestones
        
    - name: dependency-map
      template: dependency-map_template.md
      
    - name: test-plan
      template: test-plan_template.md
      detail_level: comprehensive
      
    - name: repository-structure
      template: repository-structure_template.md
      
    - name: environment-config
      template: environment-config_template.md
      
    - name: quality-gates
      template: quality-gates_template.md
```

### Agent Configuration

```yaml
phase2_agents:
  cost-estimator:
    mode: detailed
    fidelity: 25_percent
    methodology:
      - bottom_up
      - parametric_validation
      
  resource-planner:
    mode: full
    pod_sizing: detailed
    includes:
      - skill_matrices
      - ramp_schedules
      - retention_planning
      
  planning-agent:
    mode: full
    
  devops-scaffolder:
    mode: full
    
  quality-architect:
    mode: full
```

### Quality Gates

```yaml
phase2_gates:
  cost_approved:
    checks:
      - within_budget_tolerance: true
      - assumptions_validated: true
      - approved_by_finance: true
      - approved_by_sponsor: true
      
  resource_plan_approved:
    checks:
      - capacity_validated: true
      - skills_available: true
      - ramp_plan_realistic: true
      - approved_by_resource_manager: true
      
  planning_complete:
    checks:
      - all_tasks_estimated: true
      - dependencies_mapped: true
      - sprint_plan_accepted: true
      - team_committed: true
      
  ready_for_implementation:
    checks:
      - repository_created: true
      - environments_configured: true
      - team_onboarded: true
      - kickoff_complete: true
```

---

## Phase 3: Full Implementation Lifecycle

### Enabled Features

```yaml
phase3_features:
  story_management:
    enabled: true
    template: story-file_template.md
    lifecycle: full  # Draft → Ready → InProgress → InReview → Done
    
  document_sharding:
    enabled: true
    auto_shard: true
    max_shard_size: 2000_tokens
    
  sprint_management:
    enabled: true
    ceremonies:
      - planning
      - daily_standup
      - review
      - retrospective
      
  metrics_tracking:
    enabled: true
    metrics:
      - velocity
      - cycle_time
      - defect_rate
      - burndown
```

### Agent Configuration

```yaml
phase3_agents:
  scrum-master:
    mode: full
    
  developer:
    mode: full
    
  qa-engineer:
    mode: full
```

---

## Governance & Compliance

### Approval Requirements

```yaml
approvals:
  phase0_completion:
    required:
      - executive_sponsor
      - technical_lead
    optional:
      - compliance_officer
      
  phase1_completion:
    required:
      - product_owner
      - architecture_lead
      - technical_lead
    optional:
      - security_officer
      
  phase2_completion:
    required:
      - finance_approver
      - resource_manager
      - project_sponsor
      
  sprint_release:
    required:
      - qa_lead
      - tech_lead
```

### Compliance Documentation

```yaml
compliance:
  audit_trail:
    enabled: true
    retention: 7_years
    
  change_control:
    enabled: true
    approval_required: true
    
  traceability:
    requirement_to_code: required
    requirement_to_test: required
```

---

## Document Sharding (Enterprise-Specific)

### Sharding Requirements

```yaml
sharding:
  required: true  # Mandatory for Enterprise Track
  
  architecture:
    shard_by: component
    include_overview: always
    max_per_shard: 200_lines
    
  prd:
    shard_by: epic
    include_vision: always
    max_per_shard: 150_lines
    
  spec:
    shard_by: story
    group_by: epic
    max_per_shard: 100_lines
```

### Shard Management

```yaml
shard_management:
  regeneration:
    trigger: source_major_version_change
    validation: before_each_sprint
    
  indexing:
    required: true
    location: shards/_index.md
    
  versioning:
    track_source_version: true
    include_hash: true
```

---

## Session Management

### Context Loading Strategy

```yaml
context_loading:
  phase0:
    always:
      - organization_context.md
      - technical-stack_context.md
      - prior-projects_memory.md
      - lessons-learned_memory.md
    per_interview:
      - previous_interview_transcripts
      - emerging_themes_synthesis
      
  phase1:
    always:
      - phase0_artifacts (all)
      - organization_context.md
      - technical-stack_context.md
    per_artifact:
      - related_prior_artifacts
      - relevant_adrs
      
  phase2:
    always:
      - phase1_artifacts (summary)
      - architecture_overview_shard
    on_demand:
      - detailed_architecture_shards
      - detailed_spec_shards
      
  phase3:
    per_story:
      - story_file_only (self-contained)
    never_full:
      - architecture.md
      - spec.md
      - prd.md
```

### Session Limits

| Phase | Sessions | Hours/Session | Total Hours |
|-------|----------|---------------|-------------|
| Phase 0 | 8-15 | 2-4 | 20-40 |
| Phase 1 | 10-20 | 2-4 | 25-50 |
| Phase 2 | 5-10 | 2-4 | 12-25 |
| Phase 3 | Per sprint | Varies | Varies |

---

## Escalation Triggers

### No De-escalation

Enterprise Track does not de-escalate. Once committed, full methodology applies.

### Emergency Shortcuts

In exceptional circumstances (with executive approval):

```yaml
emergency_shortcuts:
  allowed_with_approval:
    - reduce_interview_count (min 3)
    - skip_some_adrs
    - defer_non_critical_nfrs
    
  never_skip:
    - feasibility_assessment
    - cost_estimation
    - security_review
    - stakeholder_approval_gates
```

---

## Reporting Requirements

### Status Reports

```yaml
reporting:
  frequency: weekly
  
  phase0_reports:
    - interview_progress
    - emerging_themes
    - risk_identification
    
  phase1_reports:
    - artifact_completion
    - validation_status
    - blocker_summary
    
  phase2_reports:
    - planning_progress
    - budget_status
    - resource_readiness
    
  phase3_reports:
    - sprint_status
    - velocity_trends
    - quality_metrics
    - burndown_charts
```

### Steering Committee

```yaml
steering_committee:
  frequency: bi_weekly
  attendees:
    - executive_sponsor
    - project_lead
    - technical_lead
    - finance_representative
  agenda:
    - status_summary
    - risk_review
    - decision_requests
    - timeline_review
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
