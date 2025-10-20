# Phase 0: Discovery & Ideation - Complete Implementation Package

A tool-agnostic, specification-driven framework for AI-native software development that ensures you deeply understand the problem before building solutions.

---

## What is This?

This package provides everything you need to conduct **Phase 0 (Discovery & Ideation)** of the AI-Native Software Development Lifecycle—a systematic, repeatable process for understanding problems before jumping to solutions.

### Key Principles

1. **Specifications as Executable Artifacts**: Requirements become the source of truth that drive all downstream work
2. **Human-AI Collaboration**: AI agents facilitate structured discovery, with humans maintaining control
3. **Context Engineering**: Strategic information management prevents context collapse
4. **Incremental Refinement**: Multi-phase approach over single-pass attempts
5. **Validation Before Implementation**: Built-in checkpoints ensure completeness
6. **Tool Agnostic**: Works with or without code—can be enhanced programmatically

---

## What's Included

### 📄 Documentation Files

**Architecture & Strategy**:
- `phase-0-architecture.html` - Educational overview of the methodology (open in browser)
- `DIRECTORY-STRUCTURE.md` - Optimal file organization guide
- `IMPLEMENTATION-GUIDE.md` - How to use all the files together

**Process Orchestration**:
- `discovery-workflow.prompt.md` - Complete step-by-step workflow

### 🤖 Agent Instructions

**AI Agent Behavior Definitions**:
- `discovery-facilitator.instructions.md` - Interview and problem exploration agent
- `feasibility-analyzer.instructions.md` - Technical viability assessment agent

### 📋 Templates

**Artifact Structures**:
- `problem-statement.template.md` - Final problem documentation structure
- `interview-transcript.template.md` - Interview documentation format
- `feasibility-report.template.md` - Feasibility assessment structure

### ✅ Quality Gates

**Validation Checklists**:
- `phase-0-completion.checklist.md` - Comprehensive completion validation

---

## Quick Start

### Option 1: Read First (Recommended)

1. **Open** `phase-0-architecture.html` in your browser
2. **Read** the Core Philosophy and Three-Layer Framework sections
3. **Review** the Discovery Workflow section
4. **Return here** when ready to implement

### Option 2: Jump Right In

```bash
# 1. Create directory structure
mkdir -p .discovery/primitives/{agents,templates,workflows,checklists}
mkdir -p .discovery/memory
mkdir -p discovery-sessions/my-project/{interviews,working,artifacts,validation}

# 2. Copy agent instructions
cp discovery-facilitator.instructions.md .discovery/primitives/agents/
cp feasibility-analyzer.instructions.md .discovery/primitives/agents/

# 3. Copy templates
cp *template.md .discovery/primitives/templates/

# 4. Copy workflow and checklist
cp discovery-workflow.prompt.md .discovery/primitives/workflows/
cp phase-0-completion.checklist.md .discovery/primitives/checklists/

# 5. Start your first interview!
# See IMPLEMENTATION-GUIDE.md for detailed steps
```

---

## Three Implementation Patterns

Choose based on your team's needs:

### Pattern 1: Conversational (No Code Required)
**Best for**: Small teams, first-time users, exploratory projects  
**Tools**: Any AI chat interface (Claude, ChatGPT, etc.) + text editor  
**Complexity**: Low  
**Time**: Manual execution, high flexibility

**Quick Start**:
1. Load agent instructions into chat
2. Conduct interviews following protocol
3. Save transcripts manually
4. Use agents to synthesize findings

**Full Guide**: See `IMPLEMENTATION-GUIDE.md` → Pattern 1

---

### Pattern 2: Template-Based (Semi-Automated)
**Best for**: Standardized processes, medium teams, compliance needs  
**Tools**: Claude Code, Gemini CLI, or GitHub Copilot + templates  
**Complexity**: Medium  
**Time**: Semi-automated with human validation

**Quick Start**:
```bash
/discovery.init "my-project"
/discovery.interview role="CEO"
/discovery.synthesize
/discovery.feasibility
/discovery.check
```

**Full Guide**: See `IMPLEMENTATION-GUIDE.md` → Pattern 2

---

### Pattern 3: Programmatic (Fully Automated)
**Best for**: Enterprise scale, complex integrations, analytics  
**Tools**: Custom C# application + LLM API + project management integration  
**Complexity**: High  
**Time**: High setup, automated execution with checkpoints

**Quick Start**:
```csharp
var orchestrator = new DiscoveryOrchestrator(llmService);
var package = await orchestrator.ExecutePhase0(initiation);
```

**Full Guide**: See `IMPLEMENTATION-GUIDE.md` → Pattern 3

---

## The Discovery Process (High Level)

```
1. INITIATE
   ↓
2. INTERVIEW STAKEHOLDERS
   - Use Five Whys
   - Apply Jobs-to-be-Done
   - Document findings
   ↓
3. SYNTHESIZE PROBLEM STATEMENT
   - Combine all interviews
   - Identify root causes
   - Quantify impact
   ↓
4. VALIDATE WITH STAKEHOLDERS
   - Get approval
   - Resolve conflicts
   - Finalize statement
   ↓
5. ASSESS FEASIBILITY
   - Research precedents
   - Identify risks
   - Validate constraints
   ↓
6. MAKE RECOMMENDATION
   - GO / CONDITIONAL / POC / NO-GO
   - Confidence level
   - Next steps
   ↓
7. VALIDATE COMPLETION
   - Run checklist
   - Get approvals
   - Package artifacts
   ↓
8. HANDOFF TO PHASE 1
   (Specification & Design)
```

---

## File Organization

### Recommended Directory Structure

```
your-project/
├── .discovery/                      # Reusable assets
│   ├── primitives/
│   │   ├── agents/                  # Agent instructions
│   │   ├── templates/               # Artifact templates
│   │   ├── workflows/               # Process definitions
│   │   └── checklists/              # Quality gates
│   ├── memory/                      # Persistent context
│   │   ├── organization.context.md
│   │   └── technical-stack.context.md
│   └── config/                      # Configuration
│
├── discovery-sessions/              # Active sessions
│   ├── 001-project-name/
│   │   ├── interviews/              # Stakeholder interviews
│   │   ├── working/                 # Drafts & iterations
│   │   ├── artifacts/               # Final deliverables
│   │   └── validation/              # Quality checks
│   └── 002-another-project/
│
└── specs/                           # Phase 1 handoff
    └── project-name/
        └── phase-0/                 # Artifacts from Phase 0
```

**See**: `DIRECTORY-STRUCTURE.md` for detailed explanation

---

## Core Concepts

### Three-Layer Framework

**Layer 1: Markdown Prompt Engineering**
- Structured prompts guide AI reasoning
- Headers, lists, and links organize information
- Reduces ambiguity, improves consistency

**Layer 2: Agentic Primitives**
- Reusable building blocks (`.instructions.md`, `.template.md`)
- Encapsulate roles, rules, and workflows
- Document successes and failures

**Layer 3: Context Engineering**
- Strategic context management
- Prevents context overload and collapse
- Session splitting, memory files, selective loading

### Key Artifacts

**Problem Statement**: What problem are we solving and why?
- Root cause analysis (Five Whys)
- Quantified business impact
- Measurable success criteria
- Validated constraints

**Feasibility Report**: Can this problem be solved?
- Precedent research
- Risk assessment
- Capability gap analysis
- Clear recommendation (GO/CONDITIONAL/POC/NO-GO)

**Interview Transcripts**: Raw stakeholder input
- Structured questioning
- Active listening and validation
- Explicit and implicit requirements

---

## Success Criteria

### Phase 0 is Complete When:

**Critical Criteria** (All required):
- [ ] Problem statement is clear and specific
- [ ] Root causes identified (not just symptoms)
- [ ] Business impact is quantified
- [ ] Min 3 stakeholder groups interviewed
- [ ] All stakeholders approve problem definition
- [ ] Feasibility recommendation is clear
- [ ] All constraints are validated

**Important Criteria** (80%+ required):
- [ ] Five Whys applied to reach root causes
- [ ] Similar implementations researched
- [ ] Risks identified with mitigations
- [ ] Capability gaps assessed
- [ ] Documentation is complete and traceable
- [ ] No contradictions between artifacts

**See**: `phase-0-completion.checklist.md` for full validation

---

## Expected Outcomes

### Artifacts Produced

From Phase 0, you will have:

1. **Problem Statement** (final, approved)
   - Clear, specific, unambiguous
   - Traces back to stakeholder interviews
   - Quantified business impact
   - Measurable success criteria

2. **Interview Transcripts** (3+ stakeholders)
   - Executive/leadership perspective
   - Technical/implementation perspective
   - User/customer perspective
   - Documented verbatim with analysis

3. **Feasibility Report**
   - Clear recommendation with confidence level
   - Evidence from precedent research
   - Risk register with mitigations
   - Capability gap analysis
   - Resource estimates (if GO)

4. **Supporting Documents**
   - Success criteria matrix
   - Constraints document
   - Risk register
   - Stakeholder approval record
   - Completion checklist

### Ready for Phase 1

With these artifacts, Phase 1 (Specification & Design) can begin without needing to revisit discovery. The specification team has:
- Complete understanding of the problem
- Validated constraints and success criteria
- Awareness of risks and capabilities
- Stakeholder alignment and buy-in

---

## Typical Timeline

**Simple Project**: 1-2 weeks
- 3-5 stakeholder interviews
- Straightforward problem space
- Clear feasibility

**Medium Project**: 2-4 weeks
- 5-8 stakeholder interviews
- Multiple stakeholder groups
- Some complexity or uncertainty

**Complex Project**: 4-8 weeks
- 8+ stakeholder interviews
- Cross-functional dependencies
- High complexity or novel problem
- May require proof-of-concept

**Effort Distribution**:
- Interviews: 40%
- Synthesis: 20%
- Feasibility Analysis: 30%
- Validation: 10%

---

## Best Practices

### Do's ✅

- **Use Five Whys** to reach root causes (not just symptoms)
- **Separate interview sessions** for different stakeholders
- **Apply delta updates** to prevent context collapse
- **Validate with stakeholders** before proceeding
- **Document sources** for all claims and findings
- **Run the checklist** before declaring completion

### Don'ts ❌

- **Don't jump to solutions** during discovery
- **Don't skip stakeholder validation** loops
- **Don't rewrite from scratch** (use incremental updates)
- **Don't assume consensus** without explicit confirmation
- **Don't proceed with gaps** in critical criteria
- **Don't rush feasibility** analysis

---

## Troubleshooting

### Common Issues & Solutions

**"Agent keeps proposing solutions"**
→ Reload instructions. Emphasize: "You are in discovery mode. Understand the problem, don't solve it."

**"Stakeholders disagree on problem"**
→ This is normal! Document the disagreement. Reconvene stakeholders. May need executive tie-breaker.

**"Can't find similar implementations"**
→ Broaden search terms. Look at adjacent domains. Search for failure stories.

**"Taking too long"**
→ Focus on minimum viable discovery: 3 interviews, core problem statement, basic feasibility.

**"Too much context for agent"**
→ Use session splitting. Load only relevant memory files. Focus on one task at a time.

**See**: `IMPLEMENTATION-GUIDE.md` → Troubleshooting for more

---

## Integration with Full SDLC

Phase 0 is the first phase of the complete AI-Native Software Development Lifecycle:

```
Phase 0: Discovery & Ideation ← YOU ARE HERE
    ↓
Phase 1: Specification & Design
    ↓
Phase 2: Planning & Setup
    ↓
Phase 3: Development
    ↓
Phase 4: Testing & QA
    ↓
Phase 5: Deployment
    ↓
Phase 6: Operations & Monitoring
    ↓
Phase 7: Analysis & Optimization
    ↓
Phase 8: Evolution & Iteration
```

**Key Handoff**: Phase 0 artifacts become inputs to Phase 1

---

## Resources & Learning

### Start Here

1. **Read**: `phase-0-architecture.html` (open in browser)
   - Core philosophy and principles
   - Three-layer framework
   - Agent architecture
   - Context engineering strategies

2. **Review**: `IMPLEMENTATION-GUIDE.md`
   - Detailed step-by-step instructions
   - All three implementation patterns
   - Best practices and troubleshooting

3. **Reference**: `DIRECTORY-STRUCTURE.md`
   - File organization rationale
   - Usage patterns for each structure
   - Migration path from simple to advanced

### Detailed Process

- **Workflow**: `discovery-workflow.prompt.md`
  - Complete orchestration of Phase 0
  - Step-by-step with decision points
  - Context engineering notes
  - Troubleshooting common issues

### Agent Behavior

- **Discovery**: `discovery-facilitator.instructions.md`
  - Interview protocols (Five Whys, JTBD)
  - Active listening techniques
  - Documentation standards
  - Validation checkpoints

- **Feasibility**: `feasibility-analyzer.instructions.md`
  - Research protocol
  - Risk assessment framework
  - Constraint validation
  - Recommendation framework

### Quality Gates

- **Checklist**: `phase-0-completion.checklist.md`
  - Critical criteria (all required)
  - Important criteria (80%+ required)
  - Documentation quality checks
  - Phase 1 readiness validation

---

## Support & Contribution

### Questions?

1. Check `IMPLEMENTATION-GUIDE.md` → Troubleshooting
2. Review the relevant agent instructions file
3. Consult `discovery-workflow.prompt.md` for process details

### Feedback & Improvements

This is a living framework. As you use it:
- Document what works well
- Note what could be improved
- Add lessons learned to `.discovery/memory/lessons-learned.memory.md`
- Evolve your agent instructions based on experience

### Customization

Feel free to adapt:
- Agent instructions for your domain
- Templates for your organization's needs
- Workflows for your team's process
- Checklists for your quality standards

The framework is flexible—make it yours!

---

## Version Information

**Framework Version**: 1.0  
**Last Updated**: 2025-01-16  
**Compatibility**: Tool-agnostic (works with any AI chat interface)

**Based on**:
- GitHub Spec-Kit methodology
- Agentic Primitives framework
- Context Engineering best practices
- Spec-Driven Development principles

---

## Quick Reference Card

### Most Important Files

1. **START HERE**: `phase-0-architecture.html` (education)
2. **HOW TO USE**: `IMPLEMENTATION-GUIDE.md` (instructions)
3. **FULL PROCESS**: `discovery-workflow.prompt.md` (orchestration)
4. **AGENT 1**: `discovery-facilitator.instructions.md` (interviews)
5. **AGENT 2**: `feasibility-analyzer.instructions.md` (viability)
6. **QUALITY CHECK**: `phase-0-completion.checklist.md` (validation)

### Essential Workflow

```bash
1. Load discovery-facilitator.instructions.md
2. Interview 3+ stakeholder groups
3. Synthesize problem statement (use template)
4. Validate with stakeholders
5. Load feasibility-analyzer.instructions.md
6. Conduct feasibility analysis (use template)
7. Run completion checklist
8. Package artifacts for Phase 1
```

### Key Templates

- `problem-statement.template.md` - Final problem doc
- `interview-transcript.template.md` - Interview format
- `feasibility-report.template.md` - Feasibility assessment

---

## Remember

**The goal of Phase 0 is to ensure Phase 1 proceeds without needing to revisit discovery.**

If you find yourself going back to "clarify the problem" during specification or development, Phase 0 wasn't complete.

**Invest the time now to save weeks later.**

---

**Ready to begin?** Open `IMPLEMENTATION-GUIDE.md` and choose your implementation pattern.

**Want to learn more?** Open `phase-0-architecture.html` in your browser.

**Have questions?** Review `discovery-workflow.prompt.md` for detailed process guidance.
