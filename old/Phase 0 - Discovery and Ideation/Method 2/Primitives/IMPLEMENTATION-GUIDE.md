# Phase 0 Implementation Guide

## Getting Started

This guide shows you how to use the Phase 0 Discovery & Ideation files to conduct a complete, structured discovery process that produces specification-ready artifacts.

---

## What You Have

### Core Files

**Agent Instructions** (How AI agents should behave):
- `discovery-facilitator.instructions.md` - Interview and problem exploration agent
- `feasibility-analyzer.instructions.md` - Technical viability assessment agent

**Templates** (Structure for artifacts):
- `problem-statement.template.md` - Final problem documentation
- `interview-transcript.template.md` - Interview documentation
- `feasibility-report.template.md` - Feasibility assessment
- `phase-0-completion.checklist.md` - Quality gate validation

**Workflows** (Process orchestration):
- `discovery-workflow.prompt.md` - Complete Phase 0 process
- `DIRECTORY-STRUCTURE.md` - File organization guide

---

## Quick Start (3 Implementation Patterns)

Choose the pattern that matches your team's needs:

### Pattern 1: Conversational (No Code)
**Best for**: Small teams, first-time users, simple projects  
**Tools needed**: AI chat interface + text editor  
**Time investment**: Low setup, manual execution

### Pattern 2: Template-Based (Semi-Automated)
**Best for**: Repeatable processes, medium teams  
**Tools needed**: Claude Code, Gemini CLI, or similar + templates  
**Time investment**: Medium setup, semi-automated execution

### Pattern 3: Programmatic (Fully Automated)
**Best for**: Enterprise scale, complex projects, analytics  
**Tools needed**: Custom C# application + LLM API  
**Time investment**: High setup, automated execution with checkpoints

---

## Pattern 1: Conversational Implementation

### Step 1: Set Up Your Directory

Create the directory structure manually or use this script:

```bash
#!/bin/bash
# save as: init-discovery.sh

PROJECT_NAME=$1

if [ -z "$PROJECT_NAME" ]; then
    echo "Usage: ./init-discovery.sh project-name"
    exit 1
fi

# Create directory structure
mkdir -p .discovery/primitives/{agents,templates,workflows,checklists}
mkdir -p .discovery/memory
mkdir -p discovery-sessions/${PROJECT_NAME}/{interviews,working,artifacts,validation}

echo "Created discovery structure for: $PROJECT_NAME"
echo "Next steps:"
echo "1. Copy agent instructions to .discovery/primitives/agents/"
echo "2. Copy templates to .discovery/primitives/templates/"
echo "3. Start your first interview!"
```

### Step 2: Place the Files

```
your-project/
├── .discovery/
│   ├── primitives/
│   │   ├── agents/
│   │   │   ├── discovery-facilitator.instructions.md
│   │   │   └── feasibility-analyzer.instructions.md
│   │   ├── templates/
│   │   │   ├── problem-statement.template.md
│   │   │   ├── interview-transcript.template.md
│   │   │   └── feasibility-report.template.md
│   │   ├── workflows/
│   │   │   └── discovery-workflow.prompt.md
│   │   └── checklists/
│   │       └── phase-0-completion.checklist.md
│   └── memory/
│       └── organization.context.md
└── discovery-sessions/
    └── 001-my-project/
        ├── interviews/
        ├── working/
        ├── artifacts/
        └── validation/
```

### Step 3: Create Organizational Context

Create `.discovery/memory/organization.context.md`:

```markdown
# Organizational Context

**Organization**: [Your company name]
**Industry**: [Your industry]
**Size**: [Team size]
**Tech Stack**: [Primary technologies]

**Key Characteristics**:
- [Characteristic 1]
- [Characteristic 2]

**Past Projects**:
- [Project 1]: [Outcome]
- [Project 2]: [Outcome]

**Current Priorities**:
1. [Priority 1]
2. [Priority 2]
```

### Step 4: Start Your First Interview

#### 4.1 Open Your AI Chat Interface
Use Claude, ChatGPT, or your preferred AI assistant.

#### 4.2 Load the Discovery Facilitator
Start a new conversation and provide this context:

```
I want you to help me conduct a discovery interview. Please read and follow 
the instructions in this document:

[Paste the entire contents of discovery-facilitator.instructions.md]

Additionally, here is context about our organization:

[Paste contents of organization.context.md]

We are beginning discovery for a new project: [PROJECT NAME]

The stakeholder I'm interviewing today is: [NAME, ROLE]

The purpose of this interview is to understand: [PURPOSE]

Please begin by suggesting opening questions based on the Five Whys and 
Jobs-to-be-Done frameworks.
```

#### 4.3 Conduct the Interview
The agent will guide you through structured questioning. After each stakeholder response, share it with the agent, and the agent will:
- Paraphrase for validation
- Suggest follow-up questions
- Identify gaps or ambiguities
- Apply Five Whys technique

#### 4.4 Document the Interview
After the interview, ask the agent:

```
Please generate a complete interview transcript using the template structure 
from interview-transcript.template.md. Include:
- All questions asked and responses received
- Key insights extracted
- Implicit requirements identified
- Open questions for follow-up
```

Copy the agent's output and save it to:
`discovery-sessions/001-my-project/interviews/001-[role]-interview.md`

### Step 5: Repeat for All Stakeholders

Interview at least 3 different stakeholder groups:
- Executive/Leadership
- Technical/Implementation team
- End Users/Customers

For each interview:
1. Start new conversation with Discovery Facilitator
2. Load organization context + previous interview summaries
3. Conduct interview
4. Generate and save transcript

### Step 6: Synthesize Problem Statement

#### 6.1 Load All Context for Synthesis
Start a new conversation:

```
I want you to synthesize findings from multiple stakeholder interviews into 
a problem statement. 

Please read and follow the instructions in:
[Paste discovery-facilitator.instructions.md]

Pay special attention to the "Problem Statement Synthesis" section.

Here are the interview transcripts:

Interview 1 (CEO):
[Paste or summarize]

Interview 2 (CTO):
[Paste or summarize]

Interview 3 (Support Lead):
[Paste or summarize]

Please synthesize these findings into a problem statement using the template:
[Paste problem-statement.template.md]

Use the delta update approach - show how your understanding evolved across 
interviews.
```

#### 6.2 Iterative Refinement
Save the agent's output to:
`discovery-sessions/001-my-project/working/problem-statement-v1.md`

As you conduct more interviews or gain clarity:
- Update with delta changes
- Create v2, v3, etc.
- Track what changed and why

### Step 7: Validate with Stakeholders

#### 7.1 Prepare Review Package
Send the problem statement to each stakeholder:

```
Subject: Please Review: Problem Statement for [Project]

[Stakeholder Name],

Based on our conversation and input from other stakeholders, we've 
synthesized the attached problem statement.

Please review and confirm:
1. Does this accurately represent the problem?
2. Is the business impact correctly stated?
3. Are the success criteria appropriate?

Please respond with:
- [ ] Approved as-is
- [ ] Approved with comments (listed below)
- [ ] Needs revision (major issues listed below)
```

#### 7.2 Address Feedback
- If all approve: Move to final version
- If conflicts: Use agent to help resolve contradictions
- Update problem statement based on feedback

Save final as:
`discovery-sessions/001-my-project/artifacts/problem-statement.final.md`

### Step 8: Conduct Feasibility Analysis

#### 8.1 Load Feasibility Analyzer
Start a new conversation:

```
I want you to assess the feasibility of solving this problem.

Please read and follow the instructions in:
[Paste feasibility-analyzer.instructions.md]

Here is the validated problem statement:
[Paste problem-statement.final.md]

Here is our organizational context:
[Paste organization.context.md]

Please conduct a comprehensive feasibility analysis including:
1. Precedent research (find similar implementations)
2. Risk assessment
3. Capability gap analysis
4. Constraint validation
5. Clear recommendation (GO/CONDITIONAL/POC/NO-GO)

Use web search to research similar implementations.
```

#### 8.2 Iterative Analysis
The agent will conduct research and analysis. Guide it through:
- Reviewing case studies
- Identifying risks
- Assessing capabilities
- Validating constraints

Save working notes to:
`discovery-sessions/001-my-project/working/research-notes.md`

#### 8.3 Generate Feasibility Report
Ask the agent to complete the feasibility report:

```
Based on your analysis, please generate a complete feasibility report using:
[Paste feasibility-report.template.md]

Include:
- Clear recommendation with confidence level
- Evidence from your research
- Risk register
- Capability gap analysis
- Next steps
```

Save to:
`discovery-sessions/001-my-project/artifacts/feasibility-report.md`

### Step 9: Validate Completion

#### 9.1 Run the Checklist
Start a new conversation:

```
I want you to validate that our Phase 0 discovery is complete.

Please review our artifacts against this checklist:
[Paste phase-0-completion.checklist.md]

Our artifacts:
- Problem Statement: [Paste or link]
- Interview Transcripts: [Summarize - we have X interviews]
- Feasibility Report: [Paste or link]

Go through each criterion and mark it as met or not met. Identify any gaps.
```

#### 9.2 Address Gaps
If checklist reveals gaps:
- Create action items
- Assign owners
- Complete missing work
- Re-run checklist

Save completed checklist to:
`discovery-sessions/001-my-project/validation/completion-checklist.md`

### Step 10: Package for Phase 1

Once approved:

```bash
# Copy artifacts to specs directory
mkdir -p specs/my-project/phase-0/
cp discovery-sessions/001-my-project/artifacts/* specs/my-project/phase-0/

echo "Phase 0 complete! Ready for Phase 1 (Specification)."
```

---

## Pattern 2: Template-Based Implementation

### Overview
Uses slash commands (like spec-kit) to automate common tasks while maintaining human oversight.

### Setup

#### 1. Install Prerequisites
- Claude Code, Gemini CLI, or similar agentic CLI tool
- uv (Python package manager)
- Git

#### 2. Create Slash Commands

Create `.discovery/commands.md`:

```markdown
# Discovery Commands

## /discovery.init <project-name>
Initialize a new discovery session with templates and structure.

**Implementation**:
1. Create directory structure
2. Copy templates to working directory
3. Create session.meta.md
4. Load organizational context

## /discovery.interview role=<role> [framework=<framework>]
Conduct a structured interview with a stakeholder.

**Parameters**:
- role: Stakeholder's role (e.g., "CEO", "Developer")
- framework: Optional - "five-whys" or "jtbd" (default: both)

**Implementation**:
1. Load discovery-facilitator.instructions.md
2. Load organizational context
3. Guide interview using specified framework
4. Generate transcript using template
5. Save to interviews/NNN-role-interview.md
6. Update working notes

## /discovery.synthesize
Synthesize all interviews into a problem statement.

**Implementation**:
1. Load all interview transcripts
2. Load problem-statement.template.md
3. Apply synthesis using delta update approach
4. Generate problem-statement-v[N].md
5. Increment version number

## /discovery.validate
Validate problem statement with stakeholders.

**Implementation**:
1. Load current problem statement
2. Generate review request emails
3. Track responses
4. Identify contradictions
5. Update status

## /discovery.feasibility
Conduct feasibility analysis.

**Implementation**:
1. Load feasibility-analyzer.instructions.md
2. Load final problem statement
3. Conduct research, risk assessment, capability analysis
4. Generate feasibility-report.md

## /discovery.check
Run completion checklist.

**Implementation**:
1. Load phase-0-completion.checklist.md
2. Review all artifacts
3. Mark criteria as met/not met
4. Generate gap report
5. Create action items
```

#### 3. Configure Your CLI Tool
Add commands to your CLI configuration. For Claude Code:

```bash
# In your project's .claude/ directory
# Add these as custom commands
```

### Usage

```bash
# Initialize new project
/discovery.init "customer-portal-redesign"

# Conduct interviews
/discovery.interview role="CEO" framework="five-whys"
/discovery.interview role="CTO" framework="jtbd"
/discovery.interview role="Support Lead"

# Synthesize findings
/discovery.synthesize

# Run feasibility analysis
/discovery.feasibility

# Validate completion
/discovery.check
```

---

## Pattern 3: Programmatic Implementation

### Overview
Full C# application with automated workflows, validation, and analytics.

### Architecture

```csharp
// Core interfaces
public interface IDiscoveryAgent
{
    Task<Interview> ConductInterview(Stakeholder stakeholder);
    Task<ProblemStatement> SynthesizeFindings(List<Interview> interviews);
}

public interface IFeasibilityAgent
{
    Task<FeasibilityReport> AnalyzeFeasibility(ProblemStatement problem);
    Task<List<Risk>> IdentifyRisks(ProblemStatement problem);
}

// Orchestrator
public class DiscoveryOrchestrator
{
    private readonly IDiscoveryAgent _discoveryAgent;
    private readonly IFeasibilityAgent _feasibilityAgent;
    private readonly ILLMService _llm;
    
    public async Task<DiscoveryPackage> ExecutePhase0(
        ProjectInitiation initiation)
    {
        // 1. Conduct interviews
        var interviews = await ConductAllInterviews(
            initiation.Stakeholders
        );
        
        // 2. Synthesize problem statement
        var problemStatement = await _discoveryAgent
            .SynthesizeFindings(interviews);
            
        // 3. Validate with stakeholders
        await ValidateWithStakeholders(problemStatement);
        
        // 4. Conduct feasibility analysis
        var feasibility = await _feasibilityAgent
            .AnalyzeFeasibility(problemStatement);
            
        // 5. Validate completion
        var validation = await ValidateCompleteness(
            interviews,
            problemStatement,
            feasibility
        );
        
        return new DiscoveryPackage
        {
            ProblemStatement = problemStatement,
            Interviews = interviews,
            FeasibilityReport = feasibility,
            ValidationResults = validation
        };
    }
}
```

See `DIRECTORY-STRUCTURE.md` "Pattern 3: Programmatic" section for full implementation guidance.

---

## Best Practices

### Context Engineering

**Do**:
- Use separate chat sessions for different interviews
- Load only relevant memory files
- Use delta updates for iterative refinement
- Document sources and reasoning

**Don't**:
- Mix multiple stakeholder perspectives in one session
- Rewrite documents from scratch
- Skip validation loops
- Assume consensus without checking

### Quality Gates

Never skip:
1. **Five Whys**: Must reach root causes
2. **Stakeholder Validation**: Must have explicit approval
3. **Completion Checklist**: Must pass all critical criteria
4. **Phase Handoff**: Must prepare artifacts for Phase 1

### Time Investment

**Typical Timeline**:
- Simple project: 1-2 weeks
- Medium project: 2-4 weeks
- Complex project: 4-8 weeks

**Effort Distribution**:
- Interviews: 40%
- Synthesis: 20%
- Feasibility Analysis: 30%
- Validation: 10%

### When to Stop

Phase 0 is complete when:
- All critical stakeholders have been interviewed
- Root causes (not symptoms) are identified
- Business impact is quantified
- Feasibility recommendation is clear
- All stakeholders approve problem definition
- Completion checklist passes

---

## Troubleshooting

### "Agent keeps proposing solutions"
**Fix**: Reload instructions emphasizing "no solutions, only problem understanding." Use system message: "You are in discovery mode. Your role is to understand the problem, not solve it."

### "Stakeholders disagree on problem"
**Fix**: This is normal! Document the disagreement explicitly. Reconvene stakeholders to discuss. May need executive decision.

### "Can't find similar implementations"
**Fix**: Broaden search terms. Look at adjacent problem spaces. Search for failure stories (postmortems). Check academic research.

### "Taking too long"
**Fix**: Focus on minimum viable discovery:
- 3 stakeholder interviews minimum
- Core problem statement
- Basic feasibility assessment
- Can always refine later

### "Too much context for agent"
**Fix**: Use session splitting. Don't load all interviews at once. Focus agent on one task at a time.

---

## Next Steps

Once Phase 0 is complete:

1. **Review completion checklist** - Ensure all quality gates passed
2. **Obtain stakeholder approvals** - Get final sign-off
3. **Package artifacts** - Copy to specs/ directory
4. **Hand off to Phase 1** - Specification & Design begins
5. **Remain available** - Phase 1 team may have questions

---

## Support & Resources

**Documentation**:
- `DIRECTORY-STRUCTURE.md` - File organization
- `discovery-workflow.prompt.md` - Detailed process guide
- Agent instruction files - Specific agent behaviors

**Templates**:
- All `.template.md` files in primitives/templates/

**Checklists**:
- `phase-0-completion.checklist.md` - Quality validation

**Need Help?**
- Review agent instructions for specific guidance
- Check troubleshooting section above
- Refer to discovery-workflow.prompt.md for detailed steps

---

**Remember**: Time invested in Phase 0 pays dividends throughout the project. A well-understood problem leads to better specifications, better implementations, and fewer costly reworks.
