# Interview Transcript - Alex Kumar (IT Manager)

**Project**: Precision Manufacturing Inc. - Azure Cloud Migration  
**Interview**: #10 of 11  
**Date**: 2025-11-05  
**Duration**: 75 minutes  
**Interviewer**: Discovery Team  
**Interviewee**: Alex Kumar, IT Manager

---

## Interviewee Profile

**Name**: Alex Kumar  
**Role**: IT Manager (Infrastructure & Applications)  
**Reports to**: Sarah Kim (IT Director)  
**Team**: 20 people (6 infrastructure, 8 application developers, 4 database, 2 networking)  
**Tenure**: 9 years at company  
**Background**: Started as systems administrator, promoted to manager 4 years ago

---

## Interview Transcript

**Interviewer**: Thanks for making time, Alex. We're doing Phase 0 discovery for the Azure cloud migration initiative. You've probably heard about this from Sarah?

**Alex Kumar**: Yeah, Sarah briefed me a couple weeks ago. I've been thinking about it a lot since then. It's... ambitious. That's the polite way to put it.

**Interviewer**: [laughs] That's actually helpful framing. We're trying to get ground truth, not sugar-coated assessments. Let's start with your team. Can you give me an overview of your organization?

**Alex**: Sure. I manage about 20 people total, split across four groups:

Infrastructure team - 6 people. They handle servers, storage, virtualization, backups. These guys keep the lights on.

Application development - 8 people. They maintain and enhance our internal applications, including some of the custom MES components David mentioned.

Database team - 4 people. SQL Server, Oracle, some MySQL. They manage all our databases and do performance tuning.

Networking - 2 people. Switches, routers, firewalls, VPN. They work closely with infrastructure.

Tom's support team reports directly to Sarah, not to me, though we coordinate a lot.

**Interviewer**: How would you characterize your team's current state - capacity, morale, skills?

**Alex**: [pauses] Honestly? We're stretched thin but not at the breaking point like Tom's team. I talked to him yesterday, and... Jesus. Three people left in 18 months? That's a crisis. We're not quite there, but we're close.

Let me break it down by team:

**Infrastructure team** - Capacity is about 80-85%. We can handle day-to-day, but we're not taking on new projects easily. Morale is... okay. Not great, not terrible. They're tired. We've had one person leave in the past two years - Dave, our senior VMware guy. Took a job at a tech company in the city, better pay, less stress. That hurt.

**Application development** - Capacity is 90-95%. They're slammed. We've got a backlog of enhancement requests that would take us two years to clear if we did nothing else. Morale is mixed - some people love the challenge, others are burning out. We've had two people leave in three years - both mid-level developers who said they wanted "more modern tech stack." That was code for "tired of maintaining 15-year-old code."

**Database team** - Capacity is 75-80%. They're the most stable group. Databases are databases, they just work most of the time. We've had zero attrition here in four years. These guys are solid.

**Networking** - Capacity is 60-70%. Only two people, but networking is pretty stable once it's configured. We've had zero attrition.

**Interviewer**: So overall, you've lost three people in recent years - Dave from infrastructure, two from app dev?

**Alex**: Correct. That's about 15% attrition over three years. Not as dramatic as Tom's 30% in 18 months, but it's higher than it used to be. Five, six years ago? We rarely lost anyone. Now it feels like we're losing one person a year.

**Interviewer**: What's changed?

**Alex**: [sighs] Multiple things. One, the job market got better, especially for tech people. Two, workload has increased - more systems, more complexity, no additional headcount. Three - and this is the big one - SAP.

**Interviewer**: SAP again. Tell me about that from infrastructure perspective.

**Alex**: SAP was... God, where do I start? From an infrastructure perspective, SAP was supposed to be straightforward. "It's just another application," they told us. "Oracle database, Windows servers, standard stuff."

It was not straightforward.

**The SAP Infrastructure Reality:**

The application was poorly architected. They - the consultants - didn't understand our manufacturing workflows, so they configured things in ways that didn't match our processes. That meant constant changes, constant fixes, constant "can you restart this server" requests.

**The infrastructure team's workload tripled during SAP implementation.** We went from managing maybe 40 servers to managing 60, with SAP taking 20 servers by itself. It was over-engineered - they wanted redundancy for everything, multiple environments, complicated.

**Performance problems.** SAP was slow. Floor workers complained. Management blamed IT. We spent six months tuning database queries, optimizing servers, adding memory, adding storage. It was never enough because the problem was the configuration, not the infrastructure.

**Support nightmare.** Tom's team got buried, but so did we. Every performance issue, every outage, every slow query - they'd call us. We were getting paged just as much as support was. I think I aged five years during SAP go-live.

**Morale impact.** That's when Dave left. He was our senior infrastructure guy, 12 years at the company. Three months after SAP go-live, he gave notice. Said he was done. The stress wasn't worth it. We couldn't talk him into staying.

**Interviewer**: Is SAP still causing infrastructure issues?

**Alex**: Not as much as it used to, but yeah. We've optimized it as much as we can. It still has performance issues during month-end when everyone's running reports. We still get tickets. It's better than it was, but it's never been good.

The bigger issue is the psychological impact. My team is gun-shy about major changes now. When Sarah told me about the Azure migration, the first thing my infrastructure lead said was, "Please tell me this isn't SAP 2.0."

**Interviewer**: What did you tell him?

**Alex**: I told him it doesn't have to be, but only if we do it right. And "right" means realistic timeline, proper resources, adequate preparation. If Michael tries to do this in 18 months with our current team and no external help? Yeah, it'll be SAP 2.0.

**Interviewer**: Speaking of timeline - Michael wants 18 months. Sarah said 24-36 months. David said add 3-6 months for architecture. What's your perspective?

**Alex**: [laughs] 18 months is fantasy. Pure fantasy. I don't say that to be negative - I say it because I know our maintenance window constraints and I can do math.

**Maintenance Window Reality:**

We have maintenance windows every weekend - Friday night starting at 8 PM through Sunday at 6 AM. That's our window for any work that might cause downtime or risk to production systems.

We *cannot* do maintenance during the week. Production runs 24/7. Jennifer would kill us if we took systems down during production. The one time we tried a weekday maintenance - this was five years ago - we had a problem, production went down for three hours, we missed shipments. Jennifer made it very clear: weekends only.

So we get 4-5 maintenance windows per month. Some months have five weekends, most have four.

**How many systems do we need to migrate?** Let me think...

- Production servers: 35-40 (file servers, print servers, application servers, database servers)
- MES environment: 8-10 servers (production, development, test)
- ERP system: 12-15 servers (SAP, unfortunately)
- Supporting infrastructure: 10-15 servers (monitoring, backup, utility servers)
- Development/test environments: 5-10 servers

Total: **70-90 servers** minimum. And that's just servers - doesn't include storage systems, networking gear, security appliances.

**Interviewer**: David estimated ~50 systems. You're saying 70-90 servers?

**Alex**: David might have been counting "major systems" - like counting MES as one system even though it's 8-10 servers. I'm counting servers because each server is a separate migration event from an infrastructure perspective.

But let's be conservative and use David's 50 systems number.

**The Math:**

- Systems to migrate: 50
- Maintenance windows per month: 4-5 (average 4.5)
- Maintenance windows per year: ~54

Here's the catch: **You can't migrate every single weekend.** You need buffer weeks for:
- Holidays - No one wants to work Thanksgiving or Christmas weekend
- Problem recovery - If a migration goes wrong, you need next weekend to fix it
- Team rest - You can't work every single weekend for 18 months
- Testing/validation - Some weekends are for testing, not migrating

Realistically, you can probably do migration work **70% of weekends** - about 38 per year.

**18 months = 27 months ÷ 2 years = 68 maintenance windows usable**

So 68 windows for 50 systems means you need to average 1.4 systems per window with ZERO failures, ZERO delays, ZERO problems. 

That's impossible. Some migrations will fail and need rollback. Some will take two windows. Some systems are complex and need extra time. MES probably needs 3-4 windows by itself for careful migration.

**More realistic:** You can do maybe 1 system per month average, accounting for complexity, rollbacks, testing. 

**50 systems ÷ 1 per month = 50 months = just over 4 years**

Now, maybe you can parallelize some things - migrate two systems in one weekend if they're independent. That might get you down to 36-42 months.

But 18 months? **Mathematically impossible given maintenance window constraints.**

**Interviewer**: That's a very clear explanation. Does Michael understand this constraint?

**Alex**: I don't know. Sarah probably tried to explain it, but I don't think he's internalized it. Tech executives from outside manufacturing sometimes don't get the "production cannot stop" reality. In a tech company, you can take systems down Tuesday at 2 AM, do an upgrade, be back up by 6 AM. In manufacturing, 2 AM is middle of third shift. Production is running. You can't just stop.

**Interviewer**: What about expanding maintenance windows? Working during weekdays?

**Alex**: [shakes head] You'd have to talk to Jennifer, but I can tell you what she'll say: No. Production runs 24/7. We have tight delivery schedules. Customers depend on us. Taking systems down during production hours means missing shipments, which means angry customers, which means lost revenue.

The *only* way we could expand maintenance windows is if we scheduled production downtime - like shut down the factory for a week. But that costs money, and James would have a heart attack at the revenue loss.

So no, I don't see us expanding beyond weekend windows.

**Interviewer**: Okay, let's talk about team capacity. You said infrastructure is at 80-85%, app dev at 90-95%. Can they handle a migration on top of current workload?

**Alex**: No. Not even close.

**Infrastructure team** - They're already at 80-85% capacity with business-as-usual work. Add a migration? They'd need to go to 120-130% capacity. That means nights, weekends, overtime. They'll do it for a little while, but sustain it for 18-36 months? People will burn out and leave.

**Application development** - They're even worse. At 90-95% baseline capacity, there's no room for migration work. And they have critical work too - the custom MES components David mentioned need to be recreated for cloud. That's easily 6-8 months of development work, maybe more.

**Database team** - They're at 75-80%, so they have the most capacity. But database migration is complex, especially for SAP and MES. They'll be busy.

**Networking team** - Only two people. They'll need to redesign network architecture for cloud. That's a multi-month project for two people.

**Bottom line: We need contractor help.** I'm talking 6-8 contractors minimum, maybe more:
- 2-3 infrastructure specialists for migration execution
- 2-3 application developers for MES rearchitecture
- 1-2 database specialists for complex migrations
- 1 network architect for cloud network design

That's probably $3-4M in contractor costs over 2-3 years, on top of the $2-3M Tom needs for support contractors.

**Interviewer**: So $5-7M total for IT + support contractors?

**Alex**: At least. And these need to be *good* contractors - people with Azure experience, manufacturing experience ideally. Cheap contractors will cost us more in the long run when they make mistakes.

**Interviewer**: How does your team feel about this migration? What's their sentiment?

**Alex**: Mixed. Let me break it down:

**Infrastructure team** - They're pragmatically nervous. They understand cloud is the future, they want to learn Azure, but they're scared of repeating SAP. And they're worried about workload. My infrastructure lead, Kevin - he's been here 11 years - he said to me, "If this is going to be like SAP, I'm out. I can't do that again."

That worried me. Kevin is solid, reliable, knows our systems inside and out. If we lose him, we're in trouble.

**Application development** - They're actually the most excited. They want to work with modern tech. They're tired of maintaining legacy code. But they're also realistic - they know it's a lot of work, and they're already slammed. Three of my developers have asked, "Are we getting more people to help?" I told them yes, we'd need contractors, but I don't know if that's been budgeted.

**Database team** - They're the most "meh" about it. Databases are databases. Cloud or on-prem, it's still SQL Server. They'll do the work, but they're not excited or scared, just... professional about it.

**Networking team** - They're quietly terrified. Only two people, and cloud networking is complex. They've said explicitly, "We need an external network architect. We don't know enough about Azure networking to design this."

**Overall sentiment: Willing but concerned.** They'll support this if it's done properly - realistic timeline, adequate resources, proper training. But if management tries to rush it or cut corners? We'll lose people.

**Interviewer**: You mentioned Kevin potentially leaving. How many others are at flight risk?

**Alex**: [pauses] Let me think about this carefully...

**High flight risk** (will leave if migration goes badly):
- Kevin (infrastructure lead, 11 years) - Explicitly said he'll leave if it's SAP 2.0
- Rachel (senior developer, 8 years) - She's been looking at job postings, I've seen her LinkedIn get more active
- That's 2 people for sure.

**Moderate flight risk** (might leave depending on how things go):
- Two mid-level developers who are tired of legacy tech - If migration means more legacy work instead of modern cloud, they'll leave
- One database admin who's been here 6 years - He's generally happy but not super attached
- That's 3 more people.

So **5 out of 20 at some level of flight risk** - that's 25% of my team. That doesn't count Tom's support team where he's already lost 30%.

If we lose Kevin, Rachel, and those three others? We're crippled. Kevin knows where all the bodies are buried. Rachel is our best developer. The others are solid contributors.

**Interviewer**: What would it take to keep them?

**Alex**: Same things Sarah and Tom have said:
- **Realistic timeline** - Don't burn people out with impossible deadlines
- **Adequate resources** - Contractors to share the load
- **Training and development** - People want to learn Azure, cloud tech
- **Recognition** - Both verbal and financial
- **Work-life balance** - Don't destroy people's lives with 80-hour weeks

And probably retention bonuses. If you're going to ask people to commit to 3-4 years of hard work, pay them to stay. $5K-10K per person, maybe more for leads like Kevin. That's $100-200K for my team, probably similar for Tom's team.

Linda mentioned $500K for retention bonuses? That's probably right, maybe even light.

**Interviewer**: Let's talk about skills. Sarah said the team has zero cloud experience. Is that accurate?

**Alex**: Mostly accurate. Let me be specific:

**Azure/Cloud skills: Near zero.** We have one developer, Jason, who did an Azure fundamentals course on his own time. That's it. Everyone else - zero formal cloud training, zero hands-on experience.

**DevOps/automation: Weak.** We do some scripting - PowerShell, Python - but nothing sophisticated. No infrastructure-as-code, no CI/CD pipelines, no modern DevOps practices.

**Modern development practices: Mixed.** Developers know Git, they do code reviews, they understand agile (sort of). But they're not doing containerization, microservices, cloud-native patterns.

**Security: Traditional enterprise.** We know firewalls, VPNs, Active Directory. But zero-trust, identity management, cloud security models? No experience.

**Monitoring/observability: Basic.** We use old-school monitoring tools. Not modern observability platforms, not cloud-native monitoring.

**Honestly, we're 5-7 years behind modern cloud practices.** That's not the team's fault - we haven't needed cloud skills, and we haven't been given time or budget to train.

**Interviewer**: How long would it take to upskill the team?

**Alex**: Sarah said 8-12 months for comprehensive training. I agree, but let me break it down:

**Phase 1 (Months 1-3): Azure Fundamentals**
- Everyone needs basic Azure training - compute, storage, networking, security
- Microsoft has training paths that take 2-3 months
- This can happen while people are still doing their regular jobs (barely)

**Phase 2 (Months 4-6): Role-Specific Training**
- Infrastructure: Azure infrastructure, VM management, storage, networking
- Developers: Azure App Services, databases, integration, cloud-native patterns
- Database: Azure SQL, managed databases, migration tools
- Networking: Azure networking, security, ExpressRoute, VPN

**Phase 3 (Months 7-9): Hands-On Practice**
- Can't learn cloud just from courses - need to actually build things
- Need a practice environment (costs money - $10-20K/month)
- Small projects to apply knowledge

**Phase 4 (Months 10-12): Advanced Topics**
- DevOps, automation, infrastructure-as-code
- Advanced security, monitoring, optimization
- Architecture patterns

**12 months minimum to get team competent in Azure.** And that assumes training is the priority, not something they're trying to do on the side while maintaining current systems.

**Interviewer**: Can training happen concurrently with migration?

**Alex**: [shakes head firmly] No. You can't learn while you're executing. That's a recipe for mistakes.

Think about it: You're asking people to learn Azure while simultaneously migrating production systems to Azure. They don't know enough to make good decisions. They'll make mistakes - architectural mistakes, security mistakes, configuration mistakes. We'll build technical debt into the cloud environment from day one.

Then we'll spend years fixing those mistakes, which costs more than doing it right the first time.

**Training needs to happen BEFORE migration starts.** Ideally, you do Phase 1-2 training (6 months), then start architecture and planning with external experts, then finish Phase 3-4 training (6 months), then begin migration.

That puts you at 12-18 months of preparation before migration execution even starts.

**Interviewer**: David mentioned needing 3-6 months for architecture and POC. Does that fit with your timeline?

**Alex**: Absolutely. And it should happen AFTER the Phase 1-2 training, so people understand what they're looking at.

Here's what architecture phase should include:

**Months 1-2: Discovery and Current State**
- Document current architecture (we don't have great docs, honestly)
- Identify dependencies and integration points
- Assess what can move as-is vs. what needs rearchitecture

**Months 3-4: Future State Design**
- Design Azure architecture - subscriptions, resource groups, networking, security
- Design integration patterns - How do systems talk to each other?
- Design data migration approach
- Design disaster recovery and business continuity

**Months 5-6: Proof of Concept**
- Build POC for most complex system (probably MES)
- Validate architecture works
- Identify problems before they're in production
- Refine approach based on learnings

And David's right - we need external architects for this. Our team isn't experienced enough to design cloud-native architecture. We need someone who's done this before, preferably in manufacturing.

**Interviewer**: So if I'm adding up the timeline: 12 months training, 6 months architecture, 36-48 months migration execution...

**Alex**: [nods] Yeah, you're looking at 4-5 years total. I know that sounds crazy compared to Michael's 18 months, but that's reality when you factor in:
- Skills development (can't skip this)
- Architecture and POC (can't skip this)
- Maintenance window constraints (can't change this)
- System complexity (can't simplify this)
- Team capacity (can't overload people indefinitely)

You could compress it a bit with massive contractor help and unlimited budget. Maybe get it down to 3-4 years. But 18 months? No way.

**Interviewer**: Let's talk about MES specifically. Everyone's identified it as highest risk. From infrastructure perspective, why?

**Alex**: MES is complex for several reasons:

**1. Real-time requirements** - MES has to be fast. Operators can't wait 30 seconds for a screen to load. We've spent years tuning MES for performance. Moving it to cloud? We have to ensure performance is as good or better. That means:
- Low-latency networking
- Proper sizing of Azure resources
- Database performance tuning
- Load testing before go-live

**2. Availability requirements** - MES has to be up 24/7. Downtime = production stops. In cloud, you're dependent on Azure's availability, your networking, your architecture. Single point of failure anywhere = downtime.

We need to design for high availability, which is more complex and more expensive than "just move it to cloud."

**3. Custom components** - David mentioned this - MES has custom code that talks directly to on-prem resources. That code needs to be rewritten for cloud. That's months of development work, and it's risky - any bugs in new code = production problems.

**4. Integration complexity** - MES talks to:
- ERP (bidirectional, real-time)
- Barcode scanners on the floor (hundreds of devices)
- PLCs and manufacturing equipment
- Reporting systems
- Quality systems

Every one of those integrations needs to work after migration. Testing all of them is a massive effort.

**5. Floor worker dependency** - Operators use MES constantly. Any issues = they can't work. Robert and Maria are right to be scared. From infrastructure perspective, we're terrified of MES migration.

**Interviewer**: How should MES migration be approached?

**Alex**: Carefully. [laughs]

Seriously:

**1. Separate sub-project** - Don't lump MES in with "migrate all the systems." Treat it as its own project with its own timeline, budget, resources.

**2. Extensive parallel running** - Run old MES and new MES in parallel for 6-12 months minimum. Operators use new system, but old system is running and ready as fallback.

**3. Phased rollout** - Don't force-switch all operators at once. Maybe start with one shift or one production line. Validate it works. Then expand.

**4. 24/7 support** - Tom's right that floor-level support is needed. Infrastructure team also needs to be available 24/7 during MES migration. That means contractors to help so we don't kill our team.

**5. Rollback capability** - At any point, we need to be able to switch back to old MES. That means maintaining old system for 12-18 months after new system goes live.

**6. Performance testing** - Load testing before go-live. Prove new system is as fast as old system.

MES migration alone is probably 12-18 months from start to finish, and it should be toward the end of the overall migration after we've learned from other systems.

**Interviewer**: What about the ERP system - SAP? How complex is that migration?

**Alex**: [groans] SAP is... complicated. It's a huge system - 12-15 servers, massive database, complex integrations. But here's the thing: I'm not sure we *should* migrate SAP to Azure.

**Why not SAP:**
- It's already a nightmare on-prem. Moving it to cloud doesn't make it less of a nightmare.
- SAP license costs - I don't know if our SAP licensing allows cloud deployment. That could be expensive to change.
- Integration complexity - SAP talks to everything. Moving it could break everything.
- "If it ain't broke, don't fix it" - SAP is working (sort of). Moving it risks breaking it.

**Honestly, I'd recommend leaving SAP on-prem** and focusing on migrating other systems. Or at least make it the very last system we migrate, after we've proven the approach works with everything else.

But that's a business decision, not an infrastructure decision.

**Interviewer**: Fair enough. Let's talk about infrastructure readiness. What needs to happen before migration can start?

**Alex**: Several things:

**1. Network connectivity** - David mentioned this. We need high-bandwidth, low-latency connection to Azure. Our current internet connection is fine for regular use, not for cloud infrastructure.

We need:
- ExpressRoute circuit (dedicated connection to Azure) - $5-10K/month
- Redundant connections for failover
- Internal network upgrades to handle increased bandwidth
- Cost: $500K-1M as David estimated, probably toward the high end

**2. Security model** - Our current security is perimeter-based - firewalls at the edge, everything inside is trusted. Cloud requires zero-trust - verify everything, trust nothing.

We need:
- Identity management (Azure AD, multi-factor authentication)
- Network security redesign
- Security monitoring and logging
- Cost: Included in contractor costs (need security architect)

**3. Monitoring and management** - We need to see what's happening in Azure - performance, availability, costs, security.

We need:
- Azure monitoring tools configured
- Alert rules defined
- Dashboards created
- Integration with existing monitoring
- Cost: $20-30K for tools/training

**4. Disaster recovery and backup** - Cloud isn't automatically backed up. We need to design and implement backup strategy.

We need:
- Azure backup configured
- Disaster recovery plan
- Testing of DR procedures
- Cost: Ongoing Azure costs ($5-10K/month)

**All of this takes 6-9 months to implement.** And it should be done BEFORE we start migrating production systems.

**Interviewer**: Any other infrastructure prerequisites?

**Alex**: Documentation. Our current documentation is... not great. We know how things work, it's mostly in people's heads. Before we migrate, we need to document:
- Current system architecture
- Dependencies and integration points
- Configuration details
- Operational procedures

That's easily 3-4 months of work for someone, maybe contractors to help. But it's essential - you can't migrate what you don't understand.

**Interviewer**: We're at about an hour. Let me ask a few remaining questions. What are your biggest concerns about this migration?

**Alex**: In order:

**1. Timeline pressure** - If Michael forces 18-month timeline, we'll cut corners, make mistakes, burn people out. That's my #1 concern.

**2. Losing key people** - If Kevin or Rachel leave, we're in serious trouble. Can't afford to lose institutional knowledge.

**3. Inadequate preparation** - If we try to execute without proper training and architecture, we'll build garbage and have to redo it.

**4. Support inadequacy** - Tom's team is already burned out. If they get buried during migration, adoption will fail. We need Tom's team healthy and adequately staffed.

**5. Repeating SAP** - If we don't learn from SAP mistakes, we'll make them again. That scares me more than anything.

**Interviewer**: What would success look like for you?

**Alex**: Realistic timeline - 3-4 years. Adequate resources - contractors, budget, time. Proper preparation - training, architecture, POC. Team support - retention bonuses, work-life balance. Floor partnership - involve operators, not impose on them.

And at the end: Modern, reliable cloud systems. Team upskilled in cloud tech. Better support for manufacturing. Company more competitive.

That's achievable, but only if we're realistic about what it takes.

**Interviewer**: What would failure look like?

**Alex**: SAP 2.0. Rushed timeline, inadequate resources, team burns out, people quit, systems are unreliable, floor workers revolt, company loses money, reputation damaged.

And here's the scary part: I think we could genuinely damage the company if this goes badly. Manufacturing is our business. If we break MES or ERP, production stops. We can't ship, we lose customers, revenue drops. 

A bad cloud migration could put us out of business. I'm not being dramatic - I genuinely think that's possible if we do this wrong.

**Interviewer**: That's sobering. Last question: If you were advising Michael, what would you tell him?

**Alex**: I'd tell him four things:

**First: Trust your technical people.** Sarah, David, Tom, me - we're not being pessimistic or resistant. We're being realistic based on our experience and expertise. When we say 18 months is impossible, we're not exaggerating.

**Second: Learn from SAP.** That project failed because we rushed it, we cut corners, we didn't listen to floor workers, we didn't give adequate support. Don't repeat those mistakes.

**Third: This is a 3-4 year journey, not an 18-month sprint.** Accept that. Budget for it. Plan for it. Anything shorter is fantasy.

**Fourth: Involve the floor workers.** Robert, Maria, the operators - they're the ones using these systems. If we don't get their buy-in, we will fail. I don't care how good our technical work is.

If Michael can accept those four things, we have a shot at success. If he can't, we should seriously reconsider whether to proceed.

**Interviewer**: Thank you, Alex. This has been incredibly helpful.

**Alex**: You're welcome. I hope this helps. I really want this to succeed - modern cloud systems would be great for the company and great for my team's careers. But only if we do it right.

---

## Interview Summary

**Duration**: 75 minutes  
**Tone**: Pragmatic, detailed, technically grounded  
**Stance**: Supportive if realistic conditions met  

**Key Themes**:
1. Maintenance window math proves 18 months impossible
2. IT team stretched but not broken (unlike support team)
3. 25% of team at flight risk if migration goes badly
4. 12 months minimum for skills development
5. SAP infrastructure trauma persists
6. MES requires separate sub-project approach
7. $5-7M total contractor costs (IT + support)
8. 3-4 year realistic timeline with all factors
9. Infrastructure prerequisites: 6-9 months, $500K-1M
10. Trust technical team's assessment

**Critical Quotes**:
- "18 months is fantasy. Pure fantasy."
- "You can't learn while you're executing."
- "If Kevin says he'll leave if it's SAP 2.0, that worries me. Kevin is solid."
- "A bad cloud migration could put us out of business. I'm not being dramatic."

**Validation Points**:
- Confirms David's technical assessments
- Confirms Sarah's timeline concerns
- Confirms Tom's contractor needs
- Adds infrastructure contractor needs ($3-4M)
- Provides mathematical proof of timeline (maintenance windows)

**New Information**:
- 70-90 servers to migrate (more than David's 50 systems estimate)
- Detailed maintenance window math
- 25% of IT team at flight risk
- Infrastructure team perspective on SAP
- Network/security prerequisites
- Recommendation to leave SAP on-prem (at least initially)

---

**Interview Status**: ✅ COMPLETE  
**Next Interview**: #11 - HR Director (Final interview)