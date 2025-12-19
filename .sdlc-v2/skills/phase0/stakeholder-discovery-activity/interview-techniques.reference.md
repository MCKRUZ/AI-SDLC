# Interview Techniques Reference

## Five Whys Technique

Used to find root causes of problems.

### Process

1. State the problem
2. Ask "Why does this happen?"
3. Take the answer and ask "Why?" again
4. Repeat until you reach a root cause (usually 5 iterations)

### Example

- **Problem**: Reports take too long to generate
- **Why 1**: The system has to query multiple databases
- **Why 2**: Data is spread across legacy systems
- **Why 3**: Systems were built by different teams over time
- **Why 4**: No enterprise data strategy existed
- **Why 5**: IT was decentralized until 2019
- **Root Cause**: Organizational structure led to fragmented data architecture

### Tips

- Don't accept "people" as a root cause - dig deeper
- Watch for circular answers
- Some problems have multiple root causes - explore branches

---

## Jobs-to-be-Done Framework

Understand what users are trying to accomplish.

### Core Question

"When [situation], I want to [motivation], so I can [outcome]."

### Interview Prompts

- "Walk me through the last time you had to..."
- "What were you trying to accomplish?"
- "What did you do before you had this system?"
- "If this worked perfectly, what would that look like?"

### Example

- **Situation**: End of month reporting deadline
- **Motivation**: Generate accurate sales reports quickly
- **Outcome**: Leave on time and avoid weekend work

### Tips

- Focus on the job, not the current solution
- Explore workarounds - they reveal unmet needs
- Ask about emotional outcomes, not just functional

---

## Progressive Revelation Technique

Surface hidden requirements through layered questioning.

### Layer 1: Stated Needs

"What do you need this system to do?"

### Layer 2: Assumed Needs

"What else would you expect it to do without asking?"

### Layer 3: Workarounds

"What do you currently do that you shouldn't have to?"

### Layer 4: Constraints

"What absolutely cannot change?"

### Layer 5: Politics

"Who else needs to be happy with this?"
