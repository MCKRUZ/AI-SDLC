# Interview 9: Tom Bradley - Support Team Lead

**Date**: 2025-11-05  
**Duration**: 85 minutes  
**Role**: Support Team Lead  
**Years at Company**: 6 years  
**Reports to**: Sarah Kim (IT Director)  
**Team Size**: 10 people (6 Level 1, 3 Level 2, 1 lead)  
**Status**: ✅ COMPLETE

---

## Pre-Interview Context

Tom Bradley has been with Precision Manufacturing for 6 years, starting as a Level 1 help desk technician and working his way up to Support Team Lead. He manages the 10-person help desk team (Level 1 & 2 support) and coordinates after-hours on-call rotation. Known for being protective of his team but also deeply committed to keeping operations running. He's visibly tired during the interview - mentions he was on call last night and got paged three times.

---

## Interview Transcript

**Interviewer**: Tom, thanks for making time. I know you were on call last night. How are you holding up?

**Tom**: [Laughs tiredly] I'm fine. It's just... normal at this point. We got paged at 11 PM, 2 AM, and 5 AM. The 2 AM one was a MES issue - operator couldn't log in. Turned out to be a password expiration issue, but it took 45 minutes to resolve because I had to VPN in, coordinate with the operator on the phone, and then verify everything was working. By the time I got back to sleep, it was almost 3 AM, and then we got paged again at 5.

**Interviewer**: That sounds brutal. Is that a typical night?

**Tom**: [Nods] Yeah, unfortunately. We average 3-4 pages per night, sometimes more. And it's not just me - we have a rotation of 5 people who cover nights and weekends. So you're on call roughly one week out of every five, and during that week, you basically don't sleep well. You're always half-awake, waiting for the phone to ring.

**Interviewer**: What's the impact on your team?

**Tom**: [Sighs] It's wearing everyone down. We've had three people leave the support team in the past 18 months. Two went to other companies, one transferred internally to the application development team because, as he put it, "at least they don't get paged at 2 AM." 

And the people we have left... they're tired. Morale is not great. We're all committed to keeping production running - we know how important that is - but there's only so long you can sustain this pace before people burn out or leave.

**Interviewer**: Sarah mentioned you have 10 people on the support team. Can you break that down?

**Tom**: Sure. We have:
- 6 Level 1 technicians - they handle the basic stuff: password resets, account unlocks, email issues, printer problems, basic application questions
- 3 Level 2 technicians - they handle more complex issues: application errors, database connectivity, MES troubleshooting, network issues
- And me - I'm the team lead, so I handle escalations, coordinate with other IT teams, manage the on-call rotation, and still take tickets when we're swamped

**Interviewer**: What's your current ticket volume look like?

**Tom**: On an average day, we get about 80-100 new tickets. We close maybe 70-80 of them same day, so we're always running a backlog of 300-350 open tickets. Some of those are quick fixes that we just haven't gotten to yet, but a lot of them are complex issues that require coordination with vendors, other IT teams, or waiting for maintenance windows.

**Interviewer**: How do you prioritize?

**Tom**: We have a triage system:
- **Priority 1 (Critical)**: Production down, MES issues, anything that's costing the company money RIGHT NOW. We drop everything for P1s. Target response: immediate.
- **Priority 2 (High)**: Production impacted but not stopped, quality system issues, security issues. Target response: 1 hour.
- **Priority 3 (Medium)**: Individual user impacted, application errors that don't stop work. Target response: 4 hours.
- **Priority 4 (Low)**: Enhancement requests, "nice to have" fixes, cosmetic issues. Target response: best effort.

The problem is, we get maybe 10-15 P1 or P2 tickets a day, and those consume most of our time. The P3 and P4 tickets just... pile up.

**Interviewer**: What percentage of your tickets are related to MES?

**Tom**: [Thinks] Maybe 30-35%? MES is the most problematic system we support. It's old, it's finicky, and when it breaks, production stops. So MES tickets automatically get elevated to P1 or P2, even if it's just one operator having an issue, because we can't risk it spreading to other operators or affecting production.

**Interviewer**: Can you give me some examples of common MES issues?

**Tom**: Oh, man. Where do I start?

- **Login issues**: Operators get locked out, passwords expire, authentication fails. This happens several times a day across all three shifts.
- **System freezes**: MES just... stops responding. Operator is in the middle of logging a job, and the system freezes. They have to close it, log back in, and hope their data saved.
- **Barcode scanner issues**: Scanners stop working, or they scan but MES doesn't recognize the barcode. Could be hardware, could be software, hard to diagnose remotely.
- **Slow performance**: System takes 10-15 seconds to load screens, which doesn't sound like much, but when you're doing this 50 times a shift, it adds up and operators get frustrated.
- **Data sync issues**: MES doesn't sync properly with the ERP, so production data is missing or incorrect. This usually requires manual reconciliation.
- **Print failures**: Job tickets or labels don't print, or they print incorrectly. Operators can't proceed without proper documentation.

**Interviewer**: How do you typically handle these issues?

**Tom**: It depends on the issue and the time of day.

During business hours (7 AM to 6 PM), we have the full team available, so we can send someone to the floor if needed. Level 2 techs know MES pretty well, so they can usually walk an operator through troubleshooting or, if necessary, go to the floor and fix it hands-on.

After hours (6 PM to 7 AM) and weekends, it's whoever's on call. And that person is remote - they're at home, not on-site. So they have to:
1. Get paged
2. VPN in
3. Call the operator or supervisor to understand the issue
4. Try to troubleshoot remotely
5. If they can't fix it remotely, they either have to drive in (30-45 minutes for most of us) or escalate to someone else

**Interviewer**: How often do on-call people have to drive in?

**Tom**: Maybe once or twice a week? It's not super common, but it happens. Usually it's for something that absolutely can't wait until morning - like if MES is completely down for a whole line, or if there's a security issue that needs immediate hands-on attention.

**Interviewer**: What's the average resolution time for MES issues?

**Tom**: [Grimaces] That's... not great.

- **Simple issues** (password reset, restart): 15-30 minutes
- **Moderate issues** (scanner not working, print failure): 1-2 hours
- **Complex issues** (data sync problems, system freeze): 2-4 hours, sometimes longer
- **Critical outages** (MES down for a line): 2-6 hours, depending on root cause

And here's the thing - that's just resolution time. If it's after hours and the on-call person needs to drive in, add another 30-60 minutes for travel.

**Interviewer**: How do operators react when they're waiting for support?

**Tom**: [Laughs bitterly] Not well. And I don't blame them.

Imagine you're on the floor at 2 AM, you're tired, you've got a line running, and suddenly MES freezes. You can't log jobs, you can't scan parts, production is stopped. You call the help desk, you get the on-call person, and they say "I'm troubleshooting, give me 30 minutes."

But 30 minutes on the floor feels like an eternity. The supervisor is breathing down your neck, the line is down, you're losing production. And if the on-call person can't fix it remotely and has to drive in? Now you're looking at an hour, maybe more.

Operators get frustrated. They call back. They escalate to their supervisor. The supervisor calls Robert (COO), Robert calls Sarah, Sarah calls whoever's on call and asks for a status update. It becomes this whole thing.

**Interviewer**: Does your team have manufacturing floor experience?

**Tom**: [Shakes head] Not really. Most of us came from traditional IT backgrounds - help desk, desktop support, systems administration. We've learned about manufacturing on the job, but we're not operators. We don't have that deep understanding of how the floor works, what the job pressures are, what the terminology means.

There's one guy - Steve, one of our Level 2 techs - who worked in manufacturing before getting into IT. He's invaluable for MES issues because he understands operator workflows and can speak their language. But he's just one person, and he's on the on-call rotation like everyone else, so he's not always available.

**Interviewer**: How would you characterize the relationship between support and the floor workers?

**Tom**: [Pauses] It's... complicated.

On one hand, operators know we're trying to help. They know we're not the ones who designed MES or made it slow and frustrating. When we fix their issues, they're grateful.

On the other hand, there's definitely some friction. Operators see us as "IT people" who don't really understand their world. They think we don't appreciate how urgent their issues are, or how much pressure they're under to keep production running.

And honestly? They're not wrong. Most of us haven't worked a shift on the floor. We don't know what it's like to have a line go down at 3 AM and know that every minute costs the company money. We're doing our best, but there's definitely a gap.

**Interviewer**: Sarah mentioned that Michael wants to modernize and move to Azure. Have you heard about this?

**Tom**: [Groans] Yeah, I've heard. And I'm... let's just say I have concerns.

**Interviewer**: What concerns?

**Tom**: Where do I start?

**First concern: Capacity**. We're already drowning in tickets with the current systems. If we're migrating systems to the cloud, that's going to generate a TON of new support requests. Users will have questions, things will break, there will be training issues, compatibility problems, you name it. 

And during the migration, we'll be supporting BOTH the old systems AND the new systems. So instead of 80-100 tickets a day, we might be looking at 150-200. How are we supposed to handle that with the same 10 people?

**Second concern: Skills**. My team knows the current systems - we've been supporting them for years. But cloud? Azure? That's new. We'd need training, and training takes time. And while we're learning, we're still expected to keep up with the ticket queue.

**Third concern: After-hours support during migration**. If we're doing cutovers on Sunday mornings or during off-hours, who's going to be there to support it? The on-call person? That's not realistic. Cutovers are high-risk activities that need multiple people standing by. But if we pull people for that, who's covering the regular on-call rotation?

**Fourth concern: MES specifically**. If we're migrating MES to the cloud, that's... [shakes head] ...that's terrifying. MES is already our most problematic system. If we move it to the cloud and something goes wrong - latency issues, connectivity problems, compatibility issues - we could shut down production for hours or days. And my team will be the ones getting yelled at.

**Interviewer**: What would you need to support a cloud migration successfully?

**Tom**: [Thinks] A lot.

**1. More people**. We'd need at least 4-6 more support staff, maybe more, just to handle the increased ticket volume during migration. And those people would need to be trained on both old and new systems.

**2. Training for current team**. Everyone on my team would need substantial training on Azure, cloud troubleshooting, new application interfaces, everything. That's probably 3-6 months of training, which is hard to do while keeping up with BAU work.

**3. Floor-level support during MES transition**. If we're migrating MES, we can't do it with the standard help desk model. We'd need people ON THE FLOOR, all three shifts, for at least 3-6 months. Not sitting at a desk waiting for tickets - actually embedded with operators, walking the floor, seeing issues in real-time.

**4. Clear escalation paths**. Right now, if we can't fix something, we escalate to Sarah's infrastructure team or the application developers. But during migration, escalation paths will be more complex because we're dealing with contractors, consultants, cloud vendors, etc. We need very clear escalation procedures.

**5. Better documentation**. Our documentation for current systems is... okay. But for new systems, we need excellent documentation - troubleshooting guides, FAQs, known issues, workarounds. And that documentation needs to be created BEFORE we migrate, not after.

**6. Realistic timelines**. If Michael thinks we can migrate everything in 18 months, he's out of his mind. Support alone would need 12-18 months just to prepare - hiring, training, building documentation, creating new processes. You can't compress that without sacrificing quality.

**Interviewer**: Sarah estimated needing 10-15 contractors for the overall project. Would support need contractors too?

**Tom**: Absolutely. We'd need contractors for two reasons:

**First**, to backfill our regular support work while the core team focuses on migration support. So maybe 2-3 contractors to handle Level 1/Level 2 tickets during business hours.

**Second**, to provide specialized migration support. These would be people with cloud experience, Azure expertise, maybe even people who've done manufacturing cloud migrations before. We'd need at least 4-6 of these people to cover all three shifts during critical migration periods.

So yeah, we're talking about 6-9 contractors just for support, on top of the 10-15 Sarah mentioned for other parts of IT.

**Interviewer**: What would that cost?

**Tom**: [Shrugs] I'm not great with budgets, but... a good IT support contractor costs maybe $75-100/hour? So:

- Backfill contractors: 2-3 people × $75/hour × 40 hours/week × 52 weeks = roughly $300-450K/year
- Migration support contractors: 4-6 people × $100/hour × 40 hours/week × ~18 months = roughly $1.2-1.8M over 18 months

So we're talking $1.5-2.5M just for support contractors over the migration period.

And that's probably conservative. If we need 24/7 coverage during critical periods, add another 30-50% for off-hours premiums.

**Interviewer**: Have you been involved in any discussions about this migration?

**Tom**: [Laughs] No. I've heard about it third-hand from Sarah, but nobody's asked for my input. Which is... frustrating. I'm the one who's going to have to support this thing, and I haven't been consulted.

**Interviewer**: What would you want to tell Michael if you had his ear?

**Tom**: [Pauses, then speaks carefully]

I'd tell him that support isn't an afterthought. It's not something you figure out after you've migrated. It's a critical success factor that needs to be planned from day one.

I'd tell him that the help desk model works okay for business-as-usual, but it completely breaks down during major changes. You can't expect operators at 2 AM to wait an hour for remote support when production is down.

I'd tell him that my team is already burned out. We're running on fumes. If you pile a migration on top of our current workload without adding capacity, people will quit. And then you'll be in an even worse position because you'll lose institutional knowledge and experience at the worst possible time.

And I'd tell him... [pauses] ...I'd tell him that the floor workers are the key to success. They're the ones who will make or break adoption. And right now, they don't trust IT. Not after SAP. If you want them to trust you, you need to show them that you're serious about supporting them - not just with words, but with actions. Real support, real training, real respect.

**Interviewer**: You mentioned SAP. What do you remember about that?

**Tom**: [Grimaces] Oh, I remember it vividly. I was a Level 1 tech at the time, so I wasn't as involved as the Level 2 folks, but it was chaos.

We got absolutely BURIED in tickets. I'm talking 200-300 tickets a day during the first week. Every single operator was calling with issues - couldn't log in, couldn't find their work orders, system was slow, system was crashing, you name it.

And we couldn't help them because we had barely been trained ourselves. We got maybe 8 hours of SAP training before go-live, which was nowhere near enough. So operators would call and say "I can't find the button to log my production," and we'd be like "Umm... let me put you on hold and figure that out."

It was embarrassing. We felt useless. And operators were furious - rightfully so.

The on-call rotation was a nightmare. Whoever was on call during SAP was getting paged 10-15 times a night. People were getting maybe 2-3 hours of sleep. One guy had a breakdown and called in sick for a week because he just couldn't handle it anymore.

And then after three weeks, they rolled it back. Three weeks of hell, and it was all for nothing.

**Interviewer**: What did you learn from SAP?

**Tom**: [Thinks] A few things.

**First**: Adequate training is non-negotiable. For users AND for support staff. You can't expect people to support systems they don't understand.

**Second**: Pilot programs are essential. If we had piloted SAP on one line, we would have discovered all these issues before inflicting them on the entire facility. But we did a big bang approach, and it was a disaster.

**Third**: Floor-level support matters. During SAP, we tried to support everything remotely from the help desk. But operators needed someone right there, right now, to answer questions and help them navigate the new system. Remote support just doesn't cut it for floor systems during transitions.

**Fourth**: Communication is critical. During SAP, operators felt like the system was imposed on them without warning or input. They were resentful before it even started. Better communication and involvement could have helped.

**Fifth**: Have a rollback plan. It took us three weeks to admit SAP wasn't working and roll back. If we'd had a clear rollback plan and decision criteria, we could have cut our losses earlier.

**Interviewer**: If Michael wants to migrate MES to the cloud, what would your advice be?

**Tom**: [Leans forward] Do NOT repeat SAP. Here's what you need:

**1. Pilot program**. Pick one line. Migrate that line to the new MES. Run it in parallel with the old system for at least 3-6 months. Learn what breaks, fix it, document it. Only when the pilot is successful do you expand to other lines.

**2. Floor-level support**. During the pilot and for at least 6 months after full rollout, you need dedicated support staff ON THE FLOOR, all three shifts. Not help desk people taking tickets - actual people walking the floor, seeing issues in real-time, helping operators immediately.

**3. Real training**. Not 2 hours. Not even 2 days. Operators need weeks of training - classroom training, hands-on practice, simulated scenarios. And support staff need even more training because we're the ones who have to troubleshoot.

**4. Parallel running**. Keep the old MES running while the new one is being adopted. Operators need a fallback if the new system isn't working. This probably means months of parallel running, not weeks.

**5. Rollback criteria**. Define upfront what "success" looks like and what triggers a rollback. Productivity drop >X%? Quality issues? Safety incidents? Whatever it is, document it and get leadership buy-in BEFORE you start.

**6. Adequate staffing**. You cannot do this with current support levels. You need more people - either contractors or new hires - to handle the increased support load.

**7. Realistic timeline**. This isn't a 6-month project. It's an 18-24 month project just for MES. Plan accordingly.

**Interviewer**: What's your biggest fear if this migration happens?

**Tom**: [Pauses] That it becomes SAP 2.0.

That we rush into it without adequate planning or support. That we overwhelm the floor workers with too much change too fast. That my team gets buried in tickets and burns out. That people quit - both operators and support staff - because they can't handle the stress.

And worst of all, that we repeat SAP's mistakes and damage the company's relationship with floor workers even further. They already don't trust IT. If we screw this up, that trust will be gone forever.

**Interviewer**: If everything goes right - proper planning, adequate resources, realistic timeline - would you support this?

**Tom**: [Nods slowly] Yeah, I would. I mean, the current systems are old and problematic. MES especially is a pain to support. If we could get to a modern, cloud-based system that's faster, more reliable, and easier to use... that would be great. For operators, for IT, for the company.

But "if everything goes right" is doing a lot of heavy lifting in that sentence. Based on what I've seen so far - Michael's 18-month timeline, the lack of consultation with support, the apparent lack of understanding about what it takes to support floor workers during major changes - I'm not optimistic that everything WILL go right.

I hope I'm wrong. But my team and I are bracing for another disaster.

**Interviewer**: What's the one thing that would make you more optimistic?

**Tom**: [Thinks] If Michael would spend time with my team. Not just a 30-minute meeting where he presents a PowerPoint. But actually sit with us, take tickets with us, answer calls with us, understand what our day-to-day is like.

And even better - if he'd work a shift on the floor. Not as an observer, but actually doing the job. Log into MES as an operator, scan parts, log jobs, deal with the system freezing or being slow. Experience what operators experience every single day.

If he did that, he'd understand why operators are cautious about change. He'd understand why my team is skeptical. He'd understand why you can't just flip a switch and migrate everything in 18 months.

And maybe - MAYBE - he'd adjust his plans accordingly.

**Interviewer**: Maria Rodriguez mentioned that Michael should do an 8-hour shift on her floor. Would that help from your perspective too?

**Tom**: [Lights up] Absolutely! Maria's second shift is a great idea because that's when support challenges are worst. We have fewer people available after 3 PM, and if something breaks on second shift, the on-call response is slower.

If Michael worked second shift, he'd experience:
- What it's like when MES freezes at 11 PM and production stops
- What it's like to call the help desk and wait 30 minutes for help
- What it's like when the on-call person can't fix it remotely and has to drive in
- What it's like when the system is slow and every screen takes 15 seconds to load

He'd see firsthand why operators are frustrated with current systems AND why they're scared of change. And he'd understand why support is so critical during transitions.

**Interviewer**: Any other concerns we haven't covered?

**Tom**: [Thinks] Yeah, a few smaller things:

**Metrics**: How will we measure success? Right now, we track ticket volume, resolution time, customer satisfaction. During migration, those metrics will all go to hell because everything will be new and broken. We need different metrics or adjusted expectations.

**Knowledge base**: Our current knowledge base is okay for current systems. But for new systems, we'll need to build it from scratch. That takes time and effort - someone needs to write articles, create FAQs, document known issues. Who's doing that? When?

**Vendor support**: If we're moving to Azure and new cloud-based applications, we'll be dealing with different vendors. What's their support model? Can we escalate to them 24/7? What are their SLAs? We need to understand vendor support BEFORE we migrate, not after.

**Security incidents**: David's security team is already stretched thin. During migration, security incidents will likely increase - misconfigured access, data exposure, phishing attempts targeting users confused by new systems. Who's handling those incidents? What's the escalation path?

**Change fatigue**: This isn't just about one migration. If we're moving 8+ systems to the cloud over 18-36 months, that's constant change for operators and support staff. People get tired of change. How do we manage change fatigue?

**Interviewer**: Those are all great points. Any final thoughts?

**Tom**: [Sighs] Look, I'm not trying to be negative. I genuinely want this company to succeed. I want better systems for operators, I want better systems for my team to support, I want the company to be more competitive.

But I've been in IT long enough to know that good intentions aren't enough. You need planning, resources, realistic timelines, and - most importantly - you need to listen to the people who do the work every day.

Right now, I don't feel heard. My team doesn't feel heard. The floor workers don't feel heard. We're all just... bracing for impact.

If Michael and the leadership team genuinely engage with us - not just to check a box, but to really understand our concerns and incorporate our feedback - this could be successful.

But if they steamroll ahead with the 18-month timeline and inadequate resources? It'll be SAP 2.0. And I don't know if this company can survive another SAP.

**Interviewer**: Tom, thank you for your candor. This has been incredibly valuable.

**Tom**: [Stands up] No problem. Just... do something with this information, okay? We're all counting on someone to make the right decisions.

---

## Key Takeaways from Interview 9

### Support Team Reality

**Team Composition**:
- 6 Level 1 technicians (basic support)
- 3 Level 2 technicians (complex issues)
- 1 Team Lead (Tom)
- **Total**: 10 people supporting 300+ users across 24/7 operations

**Current Workload**:
- 80-100 tickets/day (average)
- 300-350 open tickets (backlog)
- 70-80 tickets closed/day
- 10-15 P1/P2 (critical/high) tickets/day consume most time

**On-Call Reality**:
- 5-person rotation (1 week on call every 5 weeks)
- 3-4 pages per night (typical)
- 30-45 minute response time if driving in required
- 1-2 drive-ins per week
- Brutal toll on team morale and sleep

**Attrition**:
- 3 people left in past 18 months (2 to other companies, 1 internal transfer)
- Primary reason: Burnout from on-call rotation
- Quote: "At least they don't get paged at 2 AM"

### MES Support Challenges

**Ticket Volume**:
- 30-35% of all tickets are MES-related
- MES automatically elevated to P1/P2 priority
- Production impact makes every MES issue urgent

**Common MES Issues**:
- Login/authentication failures (several times/day)
- System freezes (mid-job, data loss risk)
- Barcode scanner failures (hardware vs software unclear)
- Slow performance (10-15 seconds per screen)
- Data sync issues with ERP (manual reconciliation)
- Print failures (job tickets, labels)

**Resolution Times**:
- Simple issues (password reset): 15-30 minutes
- Moderate issues (scanner, print): 1-2 hours
- Complex issues (data sync, freeze): 2-4 hours
- Critical outages (line down): 2-6 hours
- Add 30-60 minutes if after-hours drive-in required

**Support Model Limitation**:
- Business hours (7 AM - 6 PM): Full team, floor presence possible
- After hours (6 PM - 7 AM): Remote only, VPN troubleshooting, phone coordination
- Operators frustrated by 30-60 minute wait times when production is down
- Help desk model breaks down for floor systems during critical issues

### Manufacturing Floor Gap

**Team Background**:
- Most team members from traditional IT backgrounds
- Limited understanding of manufacturing workflows
- Don't speak operator language or understand floor pressures
- Only **1 person (Steve, Level 2)** has manufacturing background
- Steve is invaluable but just one person in rotation

**Relationship with Floor**:
- "Complicated" - operators know support is trying to help
- But see support as "IT people who don't understand"
- Trust gap between support and operators
- Support acknowledges: "They're not wrong"

### Migration Concerns

**Capacity Crisis**:
- Current: 80-100 tickets/day
- During migration: Projected 150-200 tickets/day
- Supporting BOTH old and new systems simultaneously
- Same 10 people cannot handle this load

**Skills Gap**:
- Team knows current systems well
- Zero Azure/cloud experience
- Need 3-6 months training for cloud skills
- Training while maintaining BAU work is unrealistic

**After-Hours Support During Cutovers**:
- Cutovers on Sundays need multiple people standing by
- Who covers regular on-call rotation during cutovers?
- High-risk activities can't rely on single on-call person

**MES Migration Terror**:
- MES already most problematic system
- Cloud introduces latency, connectivity, compatibility risks
- Could shut down production for hours or days
- Support team will bear the brunt of operator frustration

### What Support Needs

**1. More People**:
- Need 4-6 additional support staff minimum
- Trained on both old and new systems
- Backfill for BAU work while core team focuses on migration

**2. Training**:
- 3-6 months Azure/cloud training for entire team
- Cannot happen while maintaining BAU workload
- Support staff need MORE training than users (troubleshooting depth)

**3. Floor-Level Support for MES**:
- Cannot use help desk model for MES transition
- Need people ON THE FLOOR, all three shifts
- 3-6 months minimum during pilot
- 6+ months after full rollout
- Embedded with operators, not waiting for tickets

**4. Clear Escalation Paths**:
- More complex with contractors, consultants, cloud vendors
- Need documented procedures before migration
- Who handles what? What are SLAs?

**5. Better Documentation**:
- Current documentation is "okay"
- New systems need excellent documentation
- Troubleshooting guides, FAQs, known issues, workarounds
- Must be created BEFORE migration, not after

**6. Realistic Timeline**:
- Support needs 12-18 months just to prepare
- Hiring, training, documentation, process creation
- Cannot compress without sacrificing quality

### Support Contractor Costs

**Two Types Needed**:
1. **Backfill contractors**: Handle BAU tickets while team focuses on migration
   - 2-3 people needed
   - $75/hour × 40 hours/week × 52 weeks
   - **Cost**: ~$300-450K/year

2. **Migration support contractors**: Specialized cloud/Azure expertise
   - 4-6 people needed for all three shifts
   - $100/hour × 40 hours/week × 18 months
   - **Cost**: ~$1.2-1.8M over 18 months

**Total Support Contractor Budget**: $1.5-2.5M (conservative)
- Add 30-50% more if 24/7 coverage needed during critical periods
- **Reality**: Probably $2-3M for adequate support contractor coverage

**NOT IN ANYONE'S BUDGET**

### SAP 2018 - Support Perspective

**What Happened**:
- 200-300 tickets/day (vs. normal 80-100)
- Support team buried, couldn't keep up
- Team had only 8 hours SAP training (inadequate)
- Operators calling: "I can't find the button..."
- Support response: "Umm... let me figure that out"
- Embarrassing and demoralizing

**On-Call Nightmare**:
- 10-15 pages per night (vs. normal 3-4)
- 2-3 hours sleep maximum
- One person had breakdown, called in sick for a week
- Brutal toll on team mental health

**Three Weeks Then Rollback**:
- All that suffering for nothing
- Trust destroyed with operators
- Support team traumatized

### Lessons Learned from SAP

1. **Adequate training non-negotiable** - for users AND support
2. **Pilot programs essential** - would have discovered issues early
3. **Floor-level support matters** - remote support insufficient for transitions
4. **Communication critical** - operators felt imposed upon, resented before it started
5. **Have rollback plan** - took 3 weeks to admit failure, should have been faster

### Advice for MES Migration

**Tom's 7 Requirements**:
1. **Pilot program** - one line, 3-6 months parallel running
2. **Floor-level support** - ON THE FLOOR, all shifts, 6+ months
3. **Real training** - weeks, not hours, for operators and support
4. **Parallel running** - keep old MES as fallback
5. **Rollback criteria** - define success/failure upfront
6. **Adequate staffing** - cannot do with current support levels
7. **Realistic timeline** - 18-24 months for MES alone

### Tom's Biggest Fear

**SAP 2.0**:
- Rush without adequate planning/support
- Overwhelm floor workers with too much change too fast
- Support team buried and burned out
- People quit (operators and support)
- Further damage to IT/floor relationship
- "I don't know if this company can survive another SAP"

### What Would Make Tom Optimistic

**Michael Floor Immersion**:
- Not just 30-minute PowerPoint meeting
- Sit with support team, take tickets, answer calls
- **Better: Work 8-hour shift on floor** (Maria's second shift)
- Experience what operators experience daily
- Understand why operators are cautious
- Understand why support is skeptical
- **Then** adjust plans accordingly

**Why Second Shift Specifically**:
- Support challenges are worst after 3 PM
- Fewer people available
- On-call response slower
- Would experience:
  - MES freezing at 11 PM, production stopped
  - Calling help desk, waiting 30 minutes
  - On-call person can't fix remotely, has to drive in
  - System slowness (15 seconds per screen)

### Additional Concerns

**Metrics During Migration**:
- Current metrics (ticket volume, resolution time, satisfaction) will tank
- Everything new and broken
- Need different metrics or adjusted expectations

**Knowledge Base**:
- Current knowledge base okay for current systems
- Need to build from scratch for new systems
- Who's writing articles, FAQs, troubleshooting guides?
- When?

**Vendor Support**:
- New vendors for Azure and cloud apps
- What's their support model? 24/7 escalation? SLAs?
- Need to understand BEFORE migration

**Security Incidents**:
- Will increase during migration
- Misconfigured access, data exposure, phishing
- David's team already stretched
- Who handles? What's escalation path?

**Change Fatigue**:
- 8+ systems over 18-36 months = constant change
- People get tired of change
- How to manage fatigue?

### Tom's Final Message

**Wants Success**:
- Better systems for operators
- Better systems for support to support
- Company competitiveness

**But Needs to Be Heard**:
- "I don't feel heard"
- "My team doesn't feel heard"
- "Floor workers don't feel heard"
- "We're all just... bracing for impact"

**If Engaged Properly**:
- Could be successful
- But requires genuine engagement, not checkbox exercise

**If Steamrolled**:
- SAP 2.0
- Company might not survive another SAP

---

## Red Flags from Interview 9

1. **Support team at breaking point**: 3 people left in 18 months, morale low, burnout pervasive
2. **Ticket volume will double**: 80-100 → 150-200 tickets/day during migration
3. **Zero consultation with support**: Tom hasn't been asked for input despite being critical stakeholder
4. **Help desk model breaks for floor systems**: Remote support insufficient during MES transition
5. **Only 1 person with manufacturing background**: Steve is single point of failure
6. **On-call rotation is brutal**: 3-4 pages/night, wearing team down
7. **MES is 30-35% of tickets**: Already most problematic system, cloud migration adds risk
8. **Support contractor costs not budgeted**: $1.5-2.5M (probably $2-3M) for adequate support coverage
9. **SAP caused support team breakdown**: 200-300 tickets/day, 10-15 pages/night, one person called in sick for week
10. **Fear of SAP 2.0 is pervasive**: "I don't know if this company can survive another SAP"

---

## Green Flags from Interview 9

1. **Tom is thoughtful and experienced**: 6 years at company, worked way up, knows the systems
2. **Support team is committed**: Despite burnout, still dedicated to keeping production running
3. **Steve (manufacturing background) exists**: Invaluable for MES issues, understands operators
4. **Tom has clear vision for success**: 7 specific requirements for MES migration
5. **Willing to support if done properly**: Not anti-change, wants better systems
6. **Learned lessons from SAP**: Specific insights on what went wrong and how to avoid repeat
7. **Supports Michael floor shift**: Echoes Maria and Robert, sees value in immersion
8. **Realistic about challenges**: Not sugar-coating, but also not just complaining

---

## Critical Quotes

**On Team Burnout**:
> "We're running on fumes. If you pile a migration on top of our current workload without adding capacity, people will quit. And then you'll be in an even worse position because you'll lose institutional knowledge and experience at the worst possible time."

**On Help Desk Model Failure**:
> "The help desk model works okay for business-as-usual, but it completely breaks down during major changes. You can't expect operators at 2 AM to wait an hour for remote support when production is down."

**On Floor Workers**:
> "The floor workers are the key to success. They're the ones who will make or break adoption. And right now, they don't trust IT. Not after SAP."

**On Michael Floor Shift**:
> "If he'd work a shift on the floor... he'd understand why operators are cautious about change. He'd understand why my team is skeptical. He'd understand why you can't just flip a switch and migrate everything in 18 months."

**On SAP Trauma**:
> "The on-call rotation was a nightmare. Whoever was on call during SAP was getting paged 10-15 times a night. People were getting maybe 2-3 hours of sleep. One guy had a breakdown and called in sick for a week because he just couldn't handle it anymore."

**On Being Heard**:
> "Right now, I don't feel heard. My team doesn't feel heard. The floor workers don't feel heard. We're all just... bracing for impact."

**On SAP 2.0 Fear**:
> "If they steamroll ahead with the 18-month timeline and inadequate resources? It'll be SAP 2.0. And I don't know if this company can survive another SAP."

---

## Follow-Up Questions Generated

### For Michael (URGENT):
- Will you spend time with Tom's support team to understand their daily reality?
- Will you commit to 8-hour floor shift on Maria's second shift to experience support challenges?
- Are you willing to accept that support needs $2-3M for contractors alone?
- How will you address support team burnout before adding migration workload?

### For Sarah (URGENT):
- What's the plan for supporting BOTH old and new systems during 12-36 month migration?
- How will support team get 3-6 months Azure/cloud training while maintaining BAU?
- What's the floor-level support model for MES transition (not help desk)?
- How to backfill support team while they focus on migration?

### For Jennifer:
- Does budget include $2-3M for support contractors?
- What's the funding strategy for support contractor costs over 18-36 months?
- Can support contractor costs be spread across multiple years?

### For IT Manager (Interview 10):
- Tom mentioned 3 people left support team in 18 months - what's the broader IT attrition picture?
- How does support team burnout compare to other IT teams?
- What's the retention risk if migration starts without addressing burnout?

### For HR Director (Interview 11):
- What's the realistic cost to hire 4-6 new support staff?
- How long to recruit support people with manufacturing floor experience?
- What's the retention strategy to prevent more support attrition during migration?
- How to address support team burnout and morale?

### For Project Team:
- What's the floor-level support staffing model for MES transition?
- How many support contractors needed for all three shifts?
- What's the support documentation strategy (knowledge base, FAQs, troubleshooting)?
- What are the escalation paths during migration (contractors, vendors, consultants)?
- How to measure support success during migration (metrics will tank)?

---

## Impact on Feasibility Assessment

### Operational Feasibility Impact

**Support Capacity Constraints**:
- Team already underwater (80-100 tickets/day, 300-350 backlog)
- Will double during migration (150-200 tickets/day)
- Support BOTH old and new systems for 12-36 months
- Cannot be done with current 10-person team

**After-Hours Support Inadequacy**:
- Help desk model breaks for floor systems
- Remote support insufficient for MES transition
- Need floor-level support (all shifts, 6+ months)
- Current on-call rotation already brutal (3-4 pages/night)

**Burnout and Attrition**:
- 3 people left in 18 months (30% attrition rate)
- Team morale low, running on fumes
- Adding migration workload without capacity will cause more attrition
- Loss of institutional knowledge at critical time

**Recommendation**: **Reduce Operational Feasibility by 5 points** (50 → 45)
- Support capacity crisis worse than understood
- Floor-level support model not designed yet
- Burnout will cause attrition during migration

### Financial Feasibility Impact

**Support Contractor Costs**:
- Backfill contractors: $300-450K/year
- Migration support contractors: $1.2-1.8M over 18 months
- Total: $1.5-2.5M (conservative)
- Reality with 24/7 coverage: **$2-3M**

**NOT IN CURRENT BUDGET**

**Updated Total Cost Estimate**:
- Previous: $16.5-23.5M
- Add support contractors: $2-3M
- **New Total**: $18.5-26.5M

**Recommendation**: **Reduce Financial Feasibility by 3 points** (40 → 37)
- Another $2-3M hidden cost discovered
- Support contractor budget not in anyone's plan
- Total cost now $18.5-26.5M vs. $3M allocated

### Timeline Feasibility Impact

**Support Preparation Time**:
- Need 12-18 months just to prepare support
- Hiring 4-6 new staff (3-6 months)
- Training entire team on Azure/cloud (3-6 months)
- Building documentation and procedures (6-12 months)
- Cannot be compressed without sacrificing quality

**Floor-Level Support Duration**:
- MES pilot: 3-6 months floor support needed
- MES rollout: 6+ months floor support needed
- Total: 9-12 months of intensive floor-level support for MES alone

**Recommendation**: **Maintain Timeline Feasibility at 25/100** (already critical)
- Support preparation adds to timeline but doesn't change fundamental constraints
- Sunday window math still dominates timeline

### Overall Feasibility

**Previous Overall**: 38/100  
**After Interview 9**: **36/100** (-2 points)

**Breakdown**:
- Timeline: 25/100 (unchanged - critical)
- Financial: 37/100 (down 3 - new $2-3M cost)
- Technical: 45/100 (unchanged)
- Operational: 45/100 (down 5 - support crisis)
- Organizational: 35/100 (unchanged)

**Assessment**: Still **CONDITIONAL GO**, but conditions now include:
- Support capacity plan with contractors ($2-3M)
- Floor-level support model designed
- Support team burnout addressed BEFORE migration starts
- Support team training strategy (3-6 months)

---

## New Risks Identified

**RISK-038**: Support Team Attrition During Migration (Score: 20/25 - CRITICAL)
- 30% attrition rate in 18 months (3 of 10 left)
- Team already burned out, morale low
- Adding migration workload will cause more attrition
- Loss of institutional knowledge at critical time
- Mitigation: Address burnout first, hire contractors, reduce on-call burden

**RISK-039**: Support Capacity Inadequacy (Score: 22/25 - CRITICAL)
- Ticket volume will double (80-100 → 150-200/day)
- Same 10 people cannot handle this load
- Supporting both old and new systems simultaneously
- Mitigation: Hire 4-6 new staff, bring in 6-9 contractors, realistic timeline

**RISK-040**: Help Desk Model Failure for Floor Systems (Score: 18/25 - HIGH)
- Remote support insufficient for MES transition
- Operators can't wait 30-60 minutes when production down
- Current model breaks during major changes
- Mitigation: Floor-level support model (all shifts, 6+ months), embedded with operators

**RISK-041**: Support Contractor Budget Inadequacy (Score: 16/25 - HIGH)
- Need $2-3M for support contractors alone
- Not in current budget ($3M total, now $18.5-26.5M needed)
- Backfill + migration support contractors required
- Mitigation: Budget approval, spread costs over multiple years

**RISK-042**: Support Skills Gap for Cloud (Score: 15/25 - HIGH)
- Team knows current systems, zero Azure/cloud experience
- Need 3-6 months training for entire team
- Cannot train while maintaining BAU workload
- Mitigation: Contractors with cloud expertise, training time allocated, phased approach

**RISK-043**: Knowledge Base and Documentation Gap (Score: 14/25 - MODERATE)
- Current documentation okay for current systems
- Need excellent documentation for new systems
- Troubleshooting guides, FAQs, known issues, workarounds
- Must be created BEFORE migration, not after
- Mitigation: Dedicated resource for documentation, 6-12 months timeline

**RISK-044**: Vendor Support Model Unknown (Score: 13/25 - MODERATE)
- New vendors for Azure and cloud applications
- Support model, 24/7 escalation, SLAs unknown
- Need to understand BEFORE migration
- Mitigation: Vendor due diligence, SLA negotiation, escalation procedures defined

---

## New Themes Identified

**THEME 16: Support as Critical Success Factor (Not Afterthought)**
- Support isn't something to figure out after migration
- Needs to be planned from day one
- Floor-level support essential for MES transition
- Help desk model breaks down during major changes

**THEME 17: Manufacturing Floor Experience Gap in IT**
- Most IT staff from traditional IT backgrounds
- Don't understand manufacturing workflows or floor pressures
- Only 1 person (Steve) has manufacturing background
- Gap creates friction with operators

**THEME 18: On-Call Brutality and Burnout**
- 3-4 pages per night, every night
- 1 week on call every 5 weeks
- 30% attrition in 18 months
- People getting 2-3 hours sleep during on-call weeks
- SAP was 10-15 pages/night (one person had breakdown)

---

## New Contradictions Identified

**CONTRADICTION 17**: Support Model Assumption
- **Michael's Assumption** (implied): Current help desk can support migration
- **Tom's Reality**: Help desk model completely breaks down during major changes
- **Gap**: Need floor-level support model for MES (all shifts, 6+ months)
- **Impact**: HIGH - Wrong support model = adoption failure
- **Severity**: 🟠 HIGH

**CONTRADICTION 18**: Support Contractor Costs
- **Current Budget**: No support contractors budgeted (likely)
- **Tom's Estimate**: $2-3M for adequate support contractor coverage
- **Gap**: $2-3M hidden cost not in budget
- **Impact**: HIGH - Another budget gap discovered
- **Severity**: 🟠 HIGH

---

## Status After Interview 9

**Interviews Complete**: 9 of 11 (82%)  
**Interviews Remaining**: 2 (IT Manager, HR Director)  

**Updated Feasibility**: 36/100 (down from 38/100)

**Total Risks**: 44 (up from 37)
- Critical (20-25): 10 risks (up from 8)
- High (15-19): 14 risks (up from 12)
- Moderate (10-14): 14 risks (up from 17)
- Low (1-9): 6 risks

**Total Contradictions**: 18 (up from 16)

**Total Themes**: 18 (up from 15)

**Critical Actions** (all remain urgent):
1. Michael-Maria floor shift (within 7 days)
2. Budget reality update ($18.5-26.5M including support)
3. Support capacity plan (contractors, hiring, floor-level model)
4. Address support team burnout BEFORE migration starts

---

**Interview 9 Complete**: 2025-11-05  
**Next Interview**: IT Manager (Interview 10)  
**Status**: Ready for Interview 10 or artifact updates
