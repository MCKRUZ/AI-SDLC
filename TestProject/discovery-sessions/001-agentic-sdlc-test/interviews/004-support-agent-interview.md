# Interview Transcript: Support Agent - Alex Thompson

**Project Name**: Customer Support Portal Redesign  
**Interview Number**: 004  
**Date**: 2025-01-17  
**Start Time**: 2:30 PM  
**End Time**: 3:15 PM  
**Duration**: 45 minutes

---

## Participants

**Interviewer**: Discovery Facilitator (AI Agent)  
**Stakeholder**: Alex Thompson  
**Role/Title**: Senior Support Agent  
**Department**: Customer Success / Support  
**Relationship to Problem**: Frontline user of support portal, handles 6-8 tickets daily

---

## Interview Context

### Purpose of This Interview
Alex is a frontline agent who uses the portal 8 hours/day. This interview validates (or challenges) perspectives from CEO, CTO, and Support Lead with real user experience. Critical for understanding if proposed solutions actually match workflows.

### Prior Context
From previous interviews:
- CEO: Churn crisis, board pressure, Q3 deadline
- CTO: Proposes GPT-4 + Azure Search + caching
- Support Lead: Wants AI suggestions, unified view, better search

**VALIDATION NEEDED**: Does Alex's day-to-day reality match these perspectives?

---

## Opening Context

**Initial statement from Alex**:

> "I've been doing support for 3 years - 1 year at my previous company, 2 years here at TechFlow. I love helping customers, that's why I do this job. But the tools here are by far the worst I've used. At my last company, we had Zendesk with a proper knowledge base integration. Here, it feels like we're working with duct tape and paperclips.
>
> Every ticket takes way longer than it should. I spend more time fighting the portal than actually helping customers. And the frustrating part is, I *know* the answer to most questions - I've answered them hundreds of times. But I can't quickly find the article or previous response to send. So I retype everything. It's like, why even have documentation if I can't use it effectively?"

---

## Question: Walk me through your typical day

**Response**:

> "I start at 9 AM. First thing: check Zendesk queue. Usually 25-30 tickets assigned to me. I prioritize:
> - Angry customers first (CAPS LOCK, multiple exclamation points)
> - Enterprise customers second (they're paying more)
> - Everyone else third
>
> For each ticket:
> 1. Read the question in Zendesk (that's fine)
> 2. Open support portal, search for customer (15-20 seconds, portal is SLOW)
> 3. Wait for customer profile to load (another 10-15 seconds)
> 4. Check what plan they're on - this determines what features they have
> 5. Oh wait, plan info isn't complete in support portal, have to open Salesforce
> 6. Open Salesforce, search same customer again (20 seconds)
> 7. Now I know their plan. Close Salesforce.
> 8. Go back to support portal, look at their past tickets to see if they've asked before
> 9. Search our knowledge base for relevant article
> 10. Search returns garbage - like, I'll search 'API rate limits' and get articles about 'Getting Started' and 'Pricing Plans'. Totally irrelevant.
> 11. Give up on search, click through Categories manually
> 12. Find article (maybe), read it to make sure it's current
> 13. Copy article link
> 14. Go back to Zendesk, paste link, write custom message explaining context
> 15. Hit send
>
> Total time: 15-20 minutes for a simple question that should take 2-3 minutes.
>
> I do this 6-8 times per day. By 3 PM I'm mentally exhausted from all the clicking and context switching. Not from helping customers - from fighting the tools."

---

## Question: What would make your job easier?

**Response**:

> "Three things:
>
> **#1: Smart suggestions when ticket arrives**
> Like, when a ticket comes in saying 'How do I export data?', the system should automatically show me:
> - 3 relevant help articles
> - A draft response based on similar past tickets
> - Who else on the team has answered this before (so I can ask them if needed)
> 
> Let me review it, maybe tweak it, then send. That would cut my time from 20 minutes to 5 minutes.
>
> **#2: Everything about customer in one place**
> I shouldn't have to open 3 different systems to see: their plan, their usage, their past tickets. One screen. All info. That's it.
>
> **#3: Search that actually works**
> Our current search is useless. Literally useless. I've stopped using it. I need search that understands what I'm asking for, not just matches keywords. Like Google for our docs.
>
> Bonus thing: Mobile access that doesn't suck. Sometimes I work from home, use my tablet, and the portal is completely unusable. I have to fire up my laptop just to check on tickets."

---

## Question: Jennifer mentioned AI-suggested responses. Would that actually help?

**Response**:

> "YES. Oh my god, yes. I mean, I'd need to review it before sending - I don't trust AI to talk to customers without me checking. But having a draft to start from would be incredible.
>
> You know what I do now? I keep a Notepad file on my computer with like 20 common responses I've typed out. When I get a common question, I copy from my Notepad, paste into Zendesk, customize the customer name and specific details, then send.
>
> But these templates get out of date. Features change, new solutions exist, and I forget to update my Notepad. So sometimes I send outdated info by accident. If the AI was pulling from current documentation and past good responses, it would be better than my manual Notepad system.
>
> Just please, please let me review before it sends. I've seen chatbots go wrong, and I don't want to be the person who let AI send something stupid to a customer."

---

## Question: Anything Jennifer or Mike wouldn't know about your workflow?

**Response**:

> "Maybe this: I've developed my own workarounds that Jennifer doesn't know about.
>
> - I keep that Notepad file of common responses
> - I have browser bookmarks to frequently-used help articles (because search doesn't work)
> - I screenshot complex setup instructions so I can send them quickly without re-typing
> - I use Slack to message other agents: 'Hey, how did you handle X?' instead of searching past tickets
>
> Everyone on the team has their own system. Maria has a different Notepad file. David has his own bookmark structure. We're all reinventing the wheel because the tools don't help us.
>
> Also, this might sound small, but: keyboard shortcuts. Power users like me want to fly through tickets. But the support portal requires so much mouse clicking. At my previous job, I could do 80% of my work with keyboard only. Here, I'm clicking, clicking, clicking all day. My wrist hurts.
>
> Oh, and one more thing: The portal doesn't warn me if another agent is working on the same ticket. Twice last week I spent 15 minutes researching an answer, went to send it, and saw someone else had already responded. Total wasted time. We need real-time indicators of who's working on what."

---

## Key Findings from Agent Perspective

### Validates Previous Interviews
- Ticket times ARE 15-20 minutes (Jennifer estimated 20-30, Alex says 15-20) ✓
- Context switching between systems is painful ✓
- Search doesn't work ✓
- AI suggestions would help (with review) ✓
- Manual re-typing of common responses wastes time ✓

### New Insights Not Mentioned Before
- **Everyone has personal workarounds**: Notepad files, bookmarks, screenshots, Slack
- **Workarounds get out of date**: Personal templates have stale info
- **Keyboard shortcuts matter**: Power users want efficiency
- **Real-time collision detection needed**: Agents duplicating work unknowingly
- **Mobile access is poor**: Tablet/phone experience unusable
- **Physical pain**: Wrist hurts from excessive clicking

### Agent-Specific Requirements
1. AI suggestions must allow review before sending (same as Jennifer)
2. Unified customer view (validates Jennifer's #2 priority)
3. Working search (validates Jennifer and CTO)
4. Keyboard shortcuts for power users
5. Real-time indicators of agent activity
6. Mobile-responsive design
7. Saved response templates (with current data)

---

## Quantified Impact from Agent Level

- **Tickets handled per day**: 6-8 - Source: Alex's workflow
- **Time per simple ticket**: 15-20 minutes - Source: Walkthrough
- **Target time with improvements**: 5 minutes - Source: Alex estimate
- **Time savings potential**: 10-15 minutes per ticket
- **Daily time saved**: 60-120 minutes per agent (assuming 6-8 tickets)
- **Across 8 agents**: 8-16 hours saved per day collectively
- **Context switches per ticket**: 3-4 systems - Source: Workflow description
- **Search abandonment**: 100% (Alex stopped using search entirely) - Source: Stated behavior

---

## Critical Quotes

> "I spend more time fighting the portal than actually helping customers."  
> — Alex Thompson

> "Like, why even have documentation if I can't use it effectively?"  
> — Alex Thompson

> "Our current search is useless. Literally useless. I've stopped using it."  
> — Alex Thompson

> "We're all reinventing the wheel because the tools don't help us."  
> — Alex Thompson, on personal workarounds

> "Just please, please let me review before it sends. I've seen chatbots go wrong."  
> — Alex Thompson, on AI suggestions

---

## Reconciliation with Management View

### Where Alex Agrees with Jennifer
- AI suggestions would help ✓
- Unified customer view critical ✓
- Search is broken ✓
- Time estimates similar ✓

### Where Alex Adds Detail
- Keyboard shortcuts (Jennifer didn't emphasize this)
- Real-time collision detection (Jennifer mentioned in passing, Alex experiences pain)
- Personal workarounds epidemic (Jennifer didn't know extent)
- Mobile access (mentioned by Jennifer as "nice to have," Alex says it's urgent for WFH)

### No Contradictions
Alex's perspective aligns with and reinforces Jennifer's views

---

## Final Synthesis Note

**All four stakeholders (CEO, CTO, Support Lead, Agent) agree**:
1. Current portal inadequate for scale
2. AI suggestions + better search are critical
3. Response times must improve
4. Churn is business-critical problem
5. Support team burning out

**One gap remains**: Unified customer view is top priority for Support (Jennifer #2, Alex #2) but not explicitly in CTO's Phase 1 plan. This MUST be reconciled before finalizing problem statement.

---

**Interview complete. Ready to synthesize all findings into comprehensive problem statement.**
