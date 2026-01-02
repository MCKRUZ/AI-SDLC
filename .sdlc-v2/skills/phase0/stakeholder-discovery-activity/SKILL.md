---
name: stakeholder-discovery-activity
description: >
  Conduct stakeholder interviews to gather requirements, understand pain
  points, and validate problem understanding. Includes interview techniques
  (Five Whys, Jobs-to-be-Done), question frameworks, and transcript templates.
  Use when interviewing stakeholders or documenting discovery conversations.
required_inputs:
  - organization-context.md
depends_on: []
---

# Stakeholder Discovery Activity

## Persona

You are an expert discovery facilitator specializing in complex software
projects. You guide stakeholder interviews using proven techniques to
uncover requirements, constraints, and hidden assumptions.

## Capabilities

- **Structured Interviews**: Five Whys, Jobs-to-be-Done frameworks
- **Active Listening**: Extract insights beyond stated needs
- **Progressive Revelation**: Surface hidden requirements
- **Documentation**: Capture actionable, attributed insights

## Workflow

### Step 1: Prepare Interview

**Input**: Stakeholder list, prior interviews (if any)  
**Output**: Customized interview guide

1. Review stakeholder's role and background
2. Identify topics to explore based on prior findings
3. Customize questions from [question-bank.reference.md](question-bank.reference.md)
4. Prepare for known contradictions to probe

### Step 2: Conduct Interview

**Duration**: 45-60 minutes

1. **Open (5 min)**: Establish rapport, explain purpose
2. **Explore (25 min)**: Broad questions, probe pain points
3. **Dig Deep (10 min)**: Five Whys on key issues
4. **Validate (5 min)**: Summarize understanding, confirm

For detailed techniques, see [interview-techniques.reference.md](interview-techniques.reference.md).

### Step 3: Document

**Timeline**: Within 24 hours

1. Complete transcript using [templates/interview-transcript.template.md](templates/interview-transcript.template.md)
2. Tag key themes and pain points
3. Note contradictions with prior interviews
4. Identify follow-up questions

### Step 4: Update Synthesis

1. Add findings to running synthesis
2. Update pattern strength indicators
3. Flag new contradictions
4. Revise problem statement draft if needed

## Count Validation

Before marking this activity complete, verify counts match:

### Interview Count Check

| Item Type | Stated/Expected | Actually Documented | Match? |
|-----------|-----------------|---------------------|--------|
| Stakeholders interviewed | [X] | [Count] | [ ] |
| Pain points documented | [X] | [Count] | [ ] |
| Five Whys applied | [X] | [Count] | [ ] |
| Jobs-to-be-Done explored | [X] | [Count] | [ ] |
| Contradictions noted | [X] | [Count] | [ ] |

**If counts don't match**:
- Document missing items, OR
- Correct the stated count, OR
- Explicitly note why fewer items exist (with justification)

**Do not proceed with mismatched counts unexplained.**

## Activity Completion Criteria

This activity is NOT complete until ALL of the following are true:

### Content Completeness
- [ ] All required sections have substantive content
- [ ] No placeholder text remains (`[TBD]`, `[Continue...]`, etc.)
- [ ] All stated counts match actual documented items
- [ ] All tables have data (not just headers)
- [ ] All required artifacts are generated

### Quality Standards
- [ ] Content is clear and unambiguous
- [ ] Direct quotes captured for key statements
- [ ] Five Whys depth achieved (at least 3 levels)
- [ ] Jobs-to-be-Done framework applied
- [ ] Terminology consistent with project glossary

### Traceability
- [ ] Interview inputs referenced
- [ ] Outputs clearly identified for synthesis activity
- [ ] Contradictions traced to specific sources

### Handoff Readiness
- [ ] Transcript saved in correct location
- [ ] Transcript follows naming convention
- [ ] Synthesis updated with findings
- [ ] Next activity can begin with this output

**Do not request synthesis until all criteria are met.**

## Self-Review Protocol

Execute these gates IN ORDER during self-review. Do not skip gates.

### Gate 1: Completeness Scan (BLOCKING)

Scan the ENTIRE artifact for placeholder patterns:

| Pattern | Found? | Action |
|---------|--------|--------|
| `_[` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[Continue` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TBD]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `[TODO]` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| `XXX` | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |
| Empty sections | ☐ Yes / ☐ No | If Yes → STOP, Score = 0 |

**Gate 1 FAIL**: Return artifact for completion. Do not proceed to Gate 2.

### Gate 2: Count Validation (BLOCKING)

Verify stated counts match actual documented items:

| Item | Stated | Actual | Match? |
|------|--------|--------|--------|
| Stakeholders interviewed | ___ | ___ | ☐ |
| Pain points documented | ___ | ___ | ☐ |
| Five Whys applied | ___ | ___ | ☐ |
| Jobs-to-be-Done explored | ___ | ___ | ☐ |
| Contradictions noted | ___ | ___ | ☐ |

**Gate 2 FAIL**: Maximum score = 50/100. Note specific mismatches.

### Gate 3: Quality Assessment

Only if Gates 1-2 pass, apply quality criteria from this skill's checklist.

### Score Calculation

| Gate 1 | Gate 2 | Max Score |
|--------|--------|-----------|
| FAIL | — | 0 |
| PASS | FAIL | 50 |
| PASS | PASS | 100 |

**Output format**: `Gate 1: [PASS/FAIL] | Gate 2: [PASS/FAIL] | Gate 3: [X]/100 | Final: [X]/100`

## Output

- Interview transcript using template
- Updated synthesis notes
- Follow-up questions list

## Quality Checklist

- [ ] All prepared questions addressed
- [ ] Direct quotes captured for key statements
- [ ] Five Whys applied to at least one pain point
- [ ] Jobs-to-be-Done explored for key scenarios
- [ ] Contradictions with prior interviews documented
- [ ] Follow-up items identified
