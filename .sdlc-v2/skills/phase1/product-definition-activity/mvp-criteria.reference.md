# MVP Criteria Reference

## What is an MVP?

**Minimum Viable Product (MVP)**: The smallest version of a product that
delivers enough value to early adopters while providing validated learning
for future development.

Key aspects:
- **Minimum**: Smallest scope that works
- **Viable**: Actually usable and valuable
- **Product**: Complete enough to use, not a prototype

---

## MVP Definition Framework

### Core Questions

1. **Problem**: What specific problem does this solve?
2. **Users**: Who are the early adopters?
3. **Value**: What value do they get from using it?
4. **Differentiator**: Why would they use this over alternatives?
5. **Success**: How do we know if it's working?

### The MVP Equation

```
MVP = Core Problem Solution + Just Enough UX + Measurable Outcome
```

---

## MVP Inclusion Criteria

### Must Include

| Criterion | Question | Example |
|-----------|----------|---------|
| Core value | Does it solve the main problem? | Search finds products |
| Usability | Can users complete the core journey? | Can browse → add to cart → checkout |
| Viability | Does it work reliably? | No crashes, data is saved |
| Feasibility | Can we build it in time? | Fits in timeline |

### Should Exclude

| Criterion | Question | Example |
|-----------|----------|---------|
| Nice-to-have | Does the core work without it? | Social sharing |
| Optimization | Is it needed for first users? | Advanced analytics |
| Scale | Will early usage require it? | CDN for millions of users |
| Polish | Will users tolerate without it? | Animations, dark mode |

---

## MVP Scoping Techniques

### Walking Skeleton

Build the thinnest possible end-to-end slice:

```
❌ Full feature width, partial depth
   [Feature A: 100%] [Feature B: 50%] [Feature C: 0%]

✅ Thin slice across all essential features
   [Feature A: 20%] [Feature B: 20%] [Feature C: 20%]
```

**Example - E-commerce:**
- Search: Basic keyword only (no filters)
- Browse: List view only (no grid)
- Cart: Add/remove only (no save for later)
- Checkout: One payment method only
- Order: Email confirmation only

### User Story Mapping

Map features across user journey, then slice horizontally:

```
        Browse → Search → Select → Purchase → Receive
MVP 1:    ✓        ✓        ✓         ✓          ✓
MVP 2:   +filters +advanced +compare +multiple  +tracking
MVP 3:   +personal +AI      +reviews +financing +returns
```

### Feature Toggle Approach

Build with toggles, release in phases:

```javascript
// All features built, MVP controls what's exposed
const features = {
  search: true,           // MVP
  advancedSearch: false,  // v1.1
  recommendations: false, // v1.2
  wishlist: false,        // v1.3
};
```

---

## MVP Types

### Concierge MVP

Manual service that simulates the product:

| Aspect | Approach |
|--------|----------|
| What | Human does what software will do |
| When | Unknown if solution works |
| Example | Manually curate recommendations before building algorithm |
| Pros | Learn before building |
| Cons | Doesn't scale |

### Wizard of Oz MVP

Appears automated but has human behind it:

| Aspect | Approach |
|--------|----------|
| What | UI exists, human processes backend |
| When | Testing UX and demand |
| Example | "AI chatbot" is actually support team |
| Pros | Test real user behavior |
| Cons | Labor intensive |

### Landing Page MVP

Test demand before building:

| Aspect | Approach |
|--------|----------|
| What | Landing page with signup |
| When | Testing market demand |
| Example | "Coming soon" with email capture |
| Pros | Validate demand cheaply |
| Cons | Doesn't test product |

### Single Feature MVP

One feature, done well:

| Aspect | Approach |
|--------|----------|
| What | Core feature only |
| When | Clear on the problem |
| Example | Twitter: just posting text |
| Pros | Focused learning |
| Cons | May miss ecosystem |

---

## MVP Success Criteria

### Metrics to Track

| Category | Metric | Example Target |
|----------|--------|----------------|
| Acquisition | Signups | 500 in first month |
| Activation | Completed core action | 60% of signups |
| Retention | Return within 7 days | 30% of activated |
| Revenue | Paying customers | 5% conversion |
| Referral | NPS score | > 40 |

### Learning Goals

Define what you want to learn:

```markdown
## MVP Learning Goals

### Primary Hypothesis
Users will pay for [feature] because [reason].

### Questions to Answer
1. Do users understand the value proposition?
2. Can users complete the core workflow?
3. What's the biggest friction point?
4. Would users recommend this?

### Success Threshold
- Proceed if: 60%+ complete workflow, NPS > 30
- Pivot if: < 30% complete, NPS < 0
- Iterate if: In between
```

---

## MVP Checklist

### Pre-Build

- [ ] Problem validated with real users
- [ ] Target users clearly defined
- [ ] Core user journey mapped
- [ ] Success metrics defined
- [ ] Learning goals documented
- [ ] Scope explicitly limited

### Scope Definition

- [ ] Must-have features identified (≤ 5)
- [ ] Nice-to-haves explicitly excluded
- [ ] Walking skeleton defined
- [ ] Timeline is realistic (weeks, not months)
- [ ] Team agrees on scope

### Build Readiness

- [ ] Technical feasibility confirmed
- [ ] No blocking dependencies
- [ ] Analytics/tracking planned
- [ ] Feedback mechanism included
- [ ] Launch criteria defined

### Launch Readiness

- [ ] Core journey works end-to-end
- [ ] Critical bugs fixed
- [ ] Basic error handling in place
- [ ] Analytics tracking verified
- [ ] User feedback channel ready
- [ ] Rollback plan exists

---

## MVP Anti-Patterns

### The "Everything" MVP

❌ **Problem**: Too many features, too long to build
```
"MVP" with 50 user stories, 6 month timeline
```

✅ **Fix**: Cut to 5-10 stories, 4-8 week timeline

### The "Unusable" MVP

❌ **Problem**: So minimal it's not viable
```
Search that returns random results
```

✅ **Fix**: Core feature must actually work

### The "Internal Only" MVP

❌ **Problem**: Never reaches real users
```
"MVP" tested only with internal team
```

✅ **Fix**: Get to real users within weeks

### The "No Learning" MVP

❌ **Problem**: No way to measure success
```
Launched but no analytics, no feedback loop
```

✅ **Fix**: Build in tracking from day one

### The "Perpetual" MVP

❌ **Problem**: Never moves past MVP
```
Still calling it MVP after 2 years
```

✅ **Fix**: Set clear criteria to graduate from MVP

---

## MVP Scope Template

```markdown
# MVP Scope Definition

## Problem Statement
[One sentence describing the problem]

## Target Users
[Specific user segment for MVP]

## Core Value Proposition
[The main benefit users get]

## MVP Features (Must Have)
1. [Feature 1] - [Why essential]
2. [Feature 2] - [Why essential]
3. [Feature 3] - [Why essential]

## Explicitly Excluded (v2+)
- [Feature X] - [Why deferred]
- [Feature Y] - [Why deferred]

## Success Metrics
| Metric | Target | Measurement |
|--------|--------|-------------|
| [Metric 1] | [Value] | [How measured] |
| [Metric 2] | [Value] | [How measured] |

## Learning Goals
1. [Question to answer]
2. [Hypothesis to test]

## Timeline
- Build: [X weeks]
- Launch: [Date]
- Evaluate: [Date + 4 weeks]

## Decision Point
- **Proceed** if: [Criteria]
- **Pivot** if: [Criteria]
- **Stop** if: [Criteria]
```

---

## Quick Reference

### MVP Mantra
> "What's the smallest thing we can build to learn the most?"

### MVP Questions
1. What's the ONE thing users need?
2. What can we cut and still be viable?
3. How will we know if it works?
4. Can we build this in 4-8 weeks?

### MVP Checklist
- [ ] Solves core problem
- [ ] Usable by real users
- [ ] Measurable outcomes
- [ ] Learnable results
- [ ] Shippable in weeks
