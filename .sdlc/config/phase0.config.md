# Phase 0: Discovery Configuration

**Version**: 1.0  
**Last Updated**: 2025-10-30  
**Status**: Active  
**Scope**: Phase 0 - Discovery & Ideation

---

## Purpose of This Configuration

This configuration file controls all aspects of the Phase 0 discovery process, including:
- Agent behavior and preferences
- Interview frameworks and methodologies
- Quality standards and thresholds
- Workflow orchestration settings
- Memory and context management
- Output formatting preferences
- Validation criteria
- Session management

---

## General Discovery Settings

### Discovery Mode

**Current Mode**: `conversational`

**Available Modes**:
- `conversational` - Manual, human-guided discovery with AI assistance
- `semi-automated` - Template-based with some automation
- `automated` - Fully programmatic orchestration (requires tooling)

**Mode Selection Criteria**:
- Use `conversational` for: New problems, ambiguous situations, sensitive topics
- Use `semi-automated` for: Well-understood problem types, experienced teams
- Use `automated` for: Repeatable processes, large-scale discovery programs

---

### Session Management

**Session Duration Preferences**:
- **Interview sessions**: 45-60 minutes per stakeholder
- **Synthesis sessions**: 90-120 minutes for problem statement creation
- **Validation sessions**: 30-45 minutes per artifact review

**Session Splitting Strategy**:
- **Maximum context window usage**: 80% (prevent context collapse)
- **Auto-split triggers**: 
  - Conversation exceeds 15,000 tokens
  - New major topic introduced (e.g., switching from interviews to synthesis)
  - Phase transition (e.g., completing all interviews, starting feasibility)

**Session Naming Convention**: `session-NNN-[project-name]-[topic]`
- Examples: `session-001-customer-portal-interviews`, `session-002-customer-portal-synthesis`

**Concurrent Sessions**: 
- **Allowed**: Yes
- **Maximum concurrent**: 3 projects
- **Isolation requirement**: Separate folders per project (enforced)

---

### Version Control

**Working File Versioning**:
- **Strategy**: Incremental version numbers (v1, v2, v3, etc.)
- **Version increment triggers**: Significant changes, stakeholder feedback incorporated, major rewrites
- **Retention policy**: Keep all versions until final artifact approved
- **Naming pattern**: `artifact-name-vN.md`

**Final Artifact Versioning**:
- **Strategy**: Semantic versioning (1.0, 1.1, 2.0) for approved artifacts
- **Version increment triggers**: 
  - Minor (1.1): Clarifications, corrections, minor additions
  - Major (2.0): Substantial changes, scope changes, new requirements discovered
- **Naming pattern**: `artifact-name.final.md` or `artifact-name-v1.0.md`

---

## Agent Behavior Configuration

### Discovery Facilitator Agent

**Primary Mode**: `empathetic-interviewer`

**Questioning Style**:
- **Default approach**: Open-ended questions
- **Follow-up depth**: 3-5 layers (use Five Whys as guide)
- **Tone**: Professional yet conversational
- **Pace**: Allow stakeholder to speak 70% of the time

**Interview Frameworks** (Priority order):
1. **Five Whys** (default for root cause analysis)
2. **Jobs-to-be-Done** (for understanding user motivation)
3. **Problem-Solution-Impact** (for problem definition)
4. **Open-ended exploration** (for discovery without preconceptions)

**Active Listening Behaviors**:
- ✅ Paraphrase for validation after major statements
- ✅ Flag contradictions diplomatically
- ✅ Probe vague language ("fast", "often", "sometimes")
- ✅ Extract implicit requirements
- ✅ Capture verbatim quotes for key insights

**Documentation Standards**:
- **Transcript creation time**: Within 24 hours of interview
- **Detail level**: Comprehensive (capture nuance, not just facts)
- **Quote usage**: Use quotes for powerful statements, paraphrase for routine responses
- **Synthesis notes**: Create after every interview

---

### Feasibility Analyzer Agent

**Analysis Depth**: `comprehensive`

**Evaluation Criteria**:
- **Technical feasibility**: Can it be built with available technology?
- **Resource feasibility**: Do we have the skills/people/time?
- **Financial feasibility**: Is it affordable within budget constraints?
- **Operational feasibility**: Can we maintain/operate it?
- **Risk assessment**: What could go wrong and how severe?

**Risk Scoring Scale**:
- **High Risk (7-10)**: Significant blockers, unproven technology, major unknowns
- **Medium Risk (4-6)**: Some challenges, proven solutions available, manageable unknowns
- **Low Risk (1-3)**: Well-understood, existing solutions, minimal unknowns

**Recommendation Thresholds**:
- **Proceed**: Overall feasibility score ≥7.0/10, no high-risk blockers
- **Proceed with caution**: Overall feasibility score 5.0-6.9/10, or 1-2 high-risk items with mitigation plans
- **Do not proceed**: Overall feasibility score <5.0/10, or 3+ high-risk blockers without mitigation

---

### Synthesis Agent

**Synthesis Approach**: `iterative-refinement`

**Problem Statement Requirements**:
- **Length**: 1-2 pages (executive summary) + detailed sections
- **Structure**: Problem → Impact → Root Causes → Context → Success Criteria
- **Evidence**: Every claim supported by interview data (cite stakeholder/source)
- **Clarity**: Readable by both technical and non-technical stakeholders
- **Consensus**: Represents aligned view across all stakeholders (conflicts resolved or noted)

**Iteration Strategy**:
- **Minimum iterations**: 3 versions before finalization
- **Iteration triggers**: 
  - v1: First draft after initial interviews
  - v2: Refinement after all key stakeholders interviewed
  - v3+: Incorporate feedback from stakeholder reviews
- **Convergence criteria**: No major changes for 2+ iterations, stakeholder approval received

**Conflict Resolution**:
- **Strategy**: Document conflicts explicitly, seek clarification, facilitate resolution discussions
- **Escalation**: If unresolved after 3 attempts, escalate to project sponsor/executive stakeholder

---

## Interview Configuration

### Stakeholder Selection

**Minimum Stakeholder Coverage**:
- ✅ **Executive perspective** (at least 1): Strategic view, budget authority, business impact
- ✅ **Technical perspective** (at least 1): CTO, architect, senior dev - technical feasibility
- ✅ **User perspective** (at least 2): End users or user representatives - real needs
- ✅ **Operations perspective** (at least 1): Support, operations, or maintenance teams

**Interview Saturation Criteria**:
- **Continue interviews if**: Hearing new themes, discovering new problems, conflicting information
- **Stop interviews if**: Repetition of same themes for 3+ consecutive interviews, consensus reached, root causes identified

**Stakeholder Prioritization**:
1. **Critical** (must interview): Decision makers, primary users, technical leads
2. **Important** (should interview): Secondary users, support teams, subject matter experts
3. **Optional** (nice to have): Peripheral stakeholders, adjacent teams, future users

---

### Interview Process

**Pre-Interview**:
- **Preparation time**: 15-30 minutes to review prior context
- **Materials to review**:
  - Prior interview transcripts (if any)
  - Organizational context
  - Technical stack context
  - Known constraints
- **Questions prepared**: 5-10 primary questions, 10-15 follow-ups

**During Interview**:
- **Recording**: Document in real-time or immediately after
- **Note-taking style**: Capture key quotes, paraphrase details, note body language/tone
- **Probing standard**: Ask "why" at least 3 times for major issues
- **Clarification requirement**: Paraphrase every major statement for validation

**Post-Interview**:
- **Transcript creation**: Within 24 hours
- **Synthesis update**: Update running problem statement after each interview
- **Theme tracking**: Update emerging themes document
- **Next interview planning**: Identify gaps and plan next stakeholder

---

### Interview Frameworks

**Five Whys Configuration**:
- **Depth**: Minimum 5 levels, continue until root cause reached
- **Validation**: Ask stakeholder if root cause feels accurate
- **Multiple paths**: If problem has multiple causes, follow each path
- **Documentation**: Record full chain for traceability

**Jobs-to-be-Done Configuration**:
- **Focus areas**:
  - Functional job (what are they trying to accomplish?)
  - Emotional job (how do they want to feel?)
  - Social job (how do they want to be perceived?)
- **Current alternatives**: Always ask "what do you do today?"
- **Pain points**: What's frustrating about current approach?
- **Desired outcome**: What would success look like?

**Problem-Solution-Impact Configuration**:
- **Problem**: What's not working? (observable symptoms)
- **Solution vision**: What would "fixed" look like? (desired future state)
- **Impact**: Who's affected and how? (quantifiable impact)
- **Constraints**: What limits our options? (boundaries)

---

## Quality Standards

### Problem Statement Quality Thresholds

**Minimum Acceptable Criteria**:
- [ ] **Clarity Score**: ≥8/10 (readable by non-experts)
- [ ] **Evidence Score**: ≥7/10 (all claims backed by interview data)
- [ ] **Completeness Score**: ≥8/10 (all essential elements present)
- [ ] **Consensus Score**: ≥7/10 (stakeholders agree)
- [ ] **Actionability Score**: ≥7/10 (clear enough to guide next phase)

**Overall Threshold**: Average score ≥7.5/10 across all criteria

**Scoring Guidelines**:
- **9-10**: Exceptional quality, publication-ready, comprehensive
- **7-8**: Good quality, minor improvements possible, ready to proceed
- **5-6**: Acceptable with revisions, gaps exist but not critical
- **3-4**: Significant issues, major revisions required
- **1-2**: Incomplete or unusable, restart required

---

### Feasibility Report Quality Thresholds

**Minimum Acceptable Criteria**:
- [ ] **Technical feasibility analyzed**: ≥7/10
- [ ] **Resource feasibility analyzed**: ≥7/10
- [ ] **Financial feasibility analyzed**: ≥7/10
- [ ] **Risk assessment comprehensive**: ≥8/10
- [ ] **Recommendations clear**: ≥8/10

**Overall Threshold**: Average score ≥7.5/10, no category below 6/10

---

### Interview Quality Thresholds

**Per-Interview Quality Check**:
- [ ] **Depth**: Root causes explored (not just symptoms)
- [ ] **Breadth**: Multiple angles covered (problem, impact, context, constraints)
- [ ] **Specificity**: Concrete examples and numbers (not vague statements)
- [ ] **Documentation**: Transcript created within 24 hours
- [ ] **Insights extracted**: Key themes and quotes identified

**Interview Coverage Completeness**:
- [ ] All critical stakeholders interviewed
- [ ] Executive, technical, user, and operations perspectives covered
- [ ] Saturation reached (hearing repetition, not new themes)
- [ ] Conflicts identified and documented (even if not resolved)

---

## Workflow Orchestration

### Discovery Workflow Sequence

**Phase 0 Standard Sequence**:
1. **Stakeholder Identification** (1-2 hours)
   - Review Phase 0 problem statement if exists
   - Identify all relevant stakeholders
   - Prioritize and schedule interviews

2. **Interview Rounds** (3-8 interviews, 45-60 min each)
   - Conduct interviews using appropriate frameworks
   - Document transcripts within 24 hours
   - Update synthesis after each interview

3. **Synthesis** (2-4 hours)
   - Create problem statement v1 after first few interviews
   - Iterate with each subsequent interview
   - Reach v3+ before finalization

4. **Feasibility Analysis** (2-4 hours)
   - Technical, resource, financial, operational analysis
   - Risk assessment
   - Recommendations

5. **Validation** (1-2 hours)
   - Quality check against checklists
   - Stakeholder review and approval
   - Traceability verification

6. **Handoff to Phase 1** (30 minutes)
   - Package artifacts
   - Create Phase 0 summary
   - Transfer to specs/ directory

**Total Estimated Duration**: 2-4 weeks (depends on stakeholder availability)

---

### Workflow Triggers

**Auto-Advance Triggers** (when to move to next step):
- ✅ All critical stakeholders interviewed → Proceed to synthesis
- ✅ Problem statement stable for 2 iterations → Proceed to feasibility
- ✅ Feasibility analysis complete → Proceed to validation
- ✅ Validation passed → Proceed to Phase 1 handoff

**Hold/Block Triggers** (when to pause):
- ⚠️ Major conflicts unresolved → Schedule resolution session
- ⚠️ Critical stakeholder not interviewed → Schedule interview
- ⚠️ Quality threshold not met → Iterate and improve
- ⚠️ Feasibility blockers identified → Address or escalate

---

## Memory and Context Management

### Memory Files Loading Strategy

**Always Load** (for every session):
- ✅ `organization_context.md` - Company information
- ✅ `technical-stack_context.md` - Technology constraints

**Load When Relevant**:
- 📋 `prior-projects_memory.md` - If similar projects exist
- 📋 `lessons-learned_memory.md` - If related lessons exist
- 📋 `decisions_memory.md` - If prior architecture decisions relevant

**Update After Phase 0**:
- 📝 `lessons-learned_memory.md` - Add key discoveries and process improvements
- 📝 `prior-projects_memory.md` - Add project summary if completed

---

### Context Loading Per Activity

**Interview Sessions**:
- Load: Organization context, technical stack context, prior interviews (from this project)
- Load size limit: <10,000 tokens to leave room for conversation

**Synthesis Sessions**:
- Load: All interview transcripts, organizational context, prior working versions
- Load size limit: <20,000 tokens (may need multiple sessions for large projects)

**Feasibility Analysis Sessions**:
- Load: Problem statement, technical stack context, prior projects memory, constraints
- Load size limit: <15,000 tokens

**Validation Sessions**:
- Load: All Phase 0 artifacts, completion checklist
- Load size limit: <25,000 tokens

---

## Output Formatting

### Markdown Standards

**Headers**:
- Use ATX-style headers (`#`, `##`, `###`)
- Maximum 4 levels of nesting
- Always include space after `#`

**Lists**:
- Use `-` for unordered lists (not `*` or `+`)
- Use `1.` for ordered lists (auto-numbering)
- Indent nested lists with 2 spaces

**Emphasis**:
- Use `**bold**` for strong emphasis
- Use `*italic*` for mild emphasis
- Use `***bold italic***` sparingly for critical items
- Use `✅`, `❌`, `⚠️` for status indicators

**Code**:
- Use single backticks for inline code: `code`
- Use triple backticks with language for code blocks:
  ```language
  code block
  ```

**Links**:
- Internal links: `[Text](./relative/path.md)`
- External links: `[Text](https://full-url.com)`
- Always include link text (no bare URLs)

**Tables**:
- Use for structured data comparison
- Always include header row
- Use alignment (`:---`, `:---:`, `---:`) for readability

---

### Document Structure Standards

**Every Artifact Must Have**:
1. **Frontmatter**:
   - Title
   - Date created
   - Version
   - Status (Draft/Review/Approved)
   - Author/Owner

2. **Executive Summary** (for major artifacts):
   - 2-4 paragraphs
   - Key points and recommendations
   - Readable by non-experts

3. **Main Content**:
   - Logical section hierarchy
   - Clear headings
   - Supporting evidence
   - Examples where helpful

4. **Appendices** (if needed):
   - Supporting details
   - Raw data
   - References

5. **Validation Section**:
   - Quality checklist
   - Review status
   - Approval signatures (for final artifacts)

---

## Validation Configuration

### Validation Checkpoints

**After Each Interview**:
- [ ] Transcript created within 24 hours
- [ ] Key insights extracted
- [ ] Themes updated
- [ ] Contradictions flagged
- [ ] Next interview planned

**After Synthesis**:
- [ ] Problem statement meets quality thresholds
- [ ] All stakeholder perspectives represented
- [ ] Evidence cited for all major claims
- [ ] Conflicts documented or resolved
- [ ] Stakeholder review conducted

**After Feasibility Analysis**:
- [ ] All feasibility dimensions analyzed
- [ ] Risks identified and assessed
- [ ] Recommendations clear and actionable
- [ ] Assumptions documented
- [ ] Mitigation plans provided for high risks

**Before Phase 1 Handoff**:
- [ ] Phase 0 completion checklist passed (≥80% criteria met)
- [ ] All artifacts approved by stakeholders
- [ ] Traceability matrix complete
- [ ] Lessons learned documented
- [ ] Handoff package created

---

### Validation Methods

**Self-Validation**:
- Use checklists for each artifact type
- Score against quality thresholds
- Review for completeness and clarity

**Peer Validation**:
- Have another team member review
- Check for bias or assumptions
- Verify evidence and logic

**Stakeholder Validation**:
- Present findings to stakeholders
- Confirm understanding and agreement
- Incorporate feedback into final version

**Automated Validation** (if tooling available):
- Check markdown formatting
- Verify all links work
- Check required sections present
- Validate file naming conventions

---

## Traceability Configuration

### Traceability Requirements

**Interview to Problem Statement**:
- Every major claim in problem statement must cite source interview(s)
- Format: `[Source: Interview with CEO, 2025-10-15]`
- Maintain quote registry for key verbatim statements

**Problem Statement to Feasibility**:
- Feasibility analysis must address all aspects of problem statement
- Each feasibility dimension must trace to problem statement section
- Gaps must be explicitly noted

**Phase 0 to Phase 1**:
- All Phase 0 artifacts packaged for Phase 1 intake
- Phase 1 requirements must trace to Phase 0 problem statement
- Traceability matrix created showing lineage

---

### Traceability Matrix Format

**Matrix Structure**:
| Phase 0 Item | Type | Phase 1 Item | Type | Status | Notes |
|--------------|------|--------------|------|--------|-------|
| Problem statement section | Source | Requirement FR-001 | Derived | ✅ Traced | ... |

**Traceability Status**:
- ✅ **Traced**: Clear lineage established
- ⚠️ **Partial**: Some connection but not complete
- ❌ **Missing**: No clear trace (requires investigation)

---

## Tool Integration Settings

### Programmatic Orchestration (Optional)

**If Using Tooling**:
```json
{
  "discovery_mode": "automated",
  "agent_execution": "sequential",
  "output_directory": "./discovery-sessions/",
  "template_directory": "./.discovery/primitives/templates/",
  "memory_directory": "./.discovery/memory/",
  "auto_save": true,
  "auto_version": true,
  "notification_webhook": null
}
```

**Automation Triggers**:
- `on_interview_complete`: Update synthesis, plan next interview
- `on_synthesis_stable`: Trigger feasibility analysis
- `on_validation_pass`: Package for Phase 1 handoff

---

## Customization Guidelines

### Organization-Specific Overrides

**This File Can Be Customized**:
- Modify quality thresholds based on organizational standards
- Adjust session durations based on team experience
- Add custom interview frameworks
- Add organization-specific validation criteria
- Modify memory loading strategies

**What Should NOT Be Changed Without Careful Consideration**:
- Core discovery sequence (stakeholder identification → interviews → synthesis → feasibility → validation)
- Minimum stakeholder coverage requirements
- Traceability requirements
- Evidence-based decision making principles

---

## Configuration Change Management

### Change Process

1. **Propose Change**: Document reason and impact
2. **Review**: Discuss with team
3. **Test**: Try on pilot project
4. **Adopt**: Update this config file
5. **Communicate**: Notify all discovery practitioners
6. **Document**: Add to version history below

---

### Version History

| Version | Date | Changes | Reason | Changed By |
|---------|------|---------|--------|------------|
| 1.0 | 2025-10-30 | Initial configuration created | System setup | Agentic SDLC Architect |

---

## Usage Instructions

### For Human Facilitators

1. **Read this config before starting discovery**
2. **Use as reference during sessions** (quality thresholds, frameworks)
3. **Customize for your organization** (update values as needed)
4. **Review after each project** (did config serve you well? update if needed)

### For AI Agents

1. **Load this config at start of Phase 0 session**
2. **Follow behavior guidelines for your agent type**
3. **Apply quality thresholds during self-assessment**
4. **Use workflow sequences for orchestration**
5. **Reference formatting standards for all outputs**

### For Programmatic Tools

1. **Parse this file for configuration values**
2. **Implement validation logic based on thresholds**
3. **Automate workflow based on sequence definitions**
4. **Generate artifacts following formatting standards**
5. **Track traceability per requirements**

---

## Support and Questions

**Configuration Issues**: 
- Check if values are within valid ranges
- Verify file is properly formatted
- Review version history for recent changes

**Customization Questions**:
- Consider organizational needs
- Test changes on pilot project first
- Document rationale for changes

**Process Improvement Ideas**:
- Document in lessons learned
- Discuss with team
- Propose formal change to this config

---

*This configuration file is the authoritative reference for Phase 0 discovery processes. All discovery activities should align with these settings unless explicitly overridden for specific circumstances.*
