# Interview 8: Manufacturing Supervisor - Maria Rodriguez

**Project**: Contoso Manufacturing Azure Modernization Initiative  
**Phase**: Phase 0 - Discovery & Ideation  
**Interview Number**: 008  
**Date**: November 5, 2025  
**Time**: 2:30 PM  
**Location**: Conference Room B (adjacent to production floor)  
**Duration**: 72 minutes

---

## Interviewee Profile

**Name**: Maria Rodriguez  
**Title**: Manufacturing Supervisor, Second Shift  
**Department**: Operations  
**Reports To**: Robert Turner (VP Operations)  
**Tenure**: 18 years with Contoso Manufacturing  
**Background**:
- Started as machine operator (2007)
- Promoted to team lead (2012)
- Manufacturing Supervisor (2016-present)
- Union member for 15 years, management for 3 years
- Manages 60 operators across 3 production lines (second shift)
- Lived through SAP implementation disaster (2018)

---

## Interview Context

This is the eighth stakeholder interview in Phase 0 discovery. Previous interviews covered executive perspective (Michael, Jennifer), technical leadership (Sarah, Kevin, Patricia), operational leadership (Robert), and union leadership (Jimmy). This interview provides critical ground-truth validation from the floor level - understanding how systems actually work in daily production, what operators need, and what makes implementations succeed or fail.

Maria is particularly valuable because she bridges union and management perspectives, having been a union member for 15 years before moving into supervision 3 years ago. She has direct experience with the 2018 SAP failure and manages the operators who will be most impacted by system changes.

---

## Part 1: Opening & Current State

**Discovery Facilitator**: Maria, thanks so much for taking time during your shift. I know second shift is your busy time, so I really appreciate it.

**Maria Rodriguez**: No problem. Robert said this was important. Plus, I've been hearing rumors about "cloud migration" and "modernization" - figured I should find out what's actually going on before my operators start asking me questions I can't answer.

**DF**: That's exactly why you're so important to talk to. I've talked to Michael, Sarah, Jennifer, Robert, Kevin, Jimmy Garcia, and Dr. Rodriguez. But I realized I haven't talked to anyone who actually *uses* these systems every single day on the production floor.

**Maria**: *[Nods]* Yeah, there's usually a big gap between what IT thinks happens on the floor and what actually happens. No offense to Sarah - she's good people - but she's not here at 2 AM when MES goes down and we've got a hot order for Detroit Dynamics due at 6 AM.

**DF**: That's exactly the reality I need to understand. Before we dive in, I want to be clear: this is discovery, not sales. I'm not here to convince you of anything. I'm here to understand reality - what works, what doesn't, what you need, what concerns you have.

**Maria**: *[Leans back, crosses arms - but not defensively, more settling in]* Okay. That's refreshing. Usually when corporate starts talking about "modernization," it means they're about to make my life harder and expect me to smile about it.

**DF**: *[Laughs]* Fair. Let me start with the basics. You've been here 18 years - started as an operator, right? Walk me through your day-to-day. What systems do you and your team interact with?

**Maria**: Every day? MES is the big one - ShopFloor Pro. Every operator uses it multiple times per shift. That's our work orders, our materials tracking, our quality checks, our production counts. If MES goes down, we basically stop. We *can* run on paper for a bit, but it's slower, error-prone, and we have to double-enter everything later.

**DF**: How often does MES go down?

**Maria**: *[Pauses, thinking]* Unplanned outages? Maybe once every two months on average. Usually gets fixed within an hour. But here's the thing - when it goes down during second shift, we're running with skeleton IT support. Sarah's team is mostly day shift. Kevin's got one infrastructure guy on call, but if it's an application issue, we're stuck until morning unless it's critical enough to wake someone up.

**DF**: What happens when you can't wake someone up?

**Maria**: We work around it. Paper logs, manual tracking, slower pace. My operators are good - they know how to keep things moving. But it creates stress, increases error rates, and we spend the next shift catching up on data entry. Plus, if Quality comes looking for traceability and we're on paper, that's a whole thing with Dr. Rodriguez's team.

**DF**: Besides MES, what else?

**Maria**: ERP for inventory - checking what materials we have, what's on order. Less frequent, but critical when we need it. Then there's the quality system - QMS - for logging inspections, defects, corrective actions. My team leads use that more than operators.

**Maria**: Oh, and email, obviously. Shift handoff notes, production reports, safety alerts. The usual.

**DF**: What about the PLC systems - the machine controls?

**Maria**: *[Waves hand]* That's mostly Lisa's world. Manufacturing IT. Operators don't touch that directly - they interact with the HMI screens on the machines. Those screens talk to the PLCs, PLCs talk to MES. When that chain breaks - like the PLC integration goes down - we lose real-time production data. Machines still run, but we're blind on counts, cycle times, downtime tracking.

**DF**: How often does that happen?

**Maria**: *[Grimaces]* More than it should. Maybe once a month something gets wonky. Usually it's a network hiccup or the integration service crashes. Lisa's team fixes it, but it can be down for hours. During that time, we're manually entering production counts into MES.

---

## Part 2: MES System Deep Dive

**DF**: Let's dig into MES specifically, since that seems to be the most critical system for your team. How long does it take to train a new operator on MES?

**Maria**: *[Thinks carefully]* Depends on the person. Someone with computer skills, maybe has used systems at another job? Two weeks to basic competency - they can enter a work order, log materials, complete quality checks. But to be really *good* at it - knowing all the shortcuts, troubleshooting when something looks wrong, understanding the workflow - that's three to six months.

**DF**: What about someone who's not computer-savvy?

**Maria**: *[Sighs]* That's tougher. I've got operators in their 50s who've been here 20 years. They know their machines inside and out - they can hear when something's off before the sensors catch it. But MES? Some of them still hunt-and-peck on the keyboard. For them, basic competency might take a month or more, and they'll never be fast at it.

**DF**: How do you handle that?

**Maria**: Pairing. I put a newer operator who's tech-savvy with an experienced operator who knows the process. They cover each other's gaps. It works, but it's not ideal - slows both of them down a bit.

**DF**: If MES changed significantly - new interface, different workflows - how would that impact your team?

**Maria**: *[Leans forward, serious]* That's what worries me when I hear "cloud migration." If you completely redesign MES, you're essentially starting over with training. Even my experienced operators - the ones who've used ShopFloor Pro for 10 years - they'd be back to square one.

**Maria**: And it's not just training time. It's the errors during the learning curve. Wrong work orders pulled, materials misapplied, quality checks skipped by accident. That costs us in rework, scrap, and customer complaints.

**DF**: What's your estimate - if MES interface changed significantly, how much would productivity drop during the transition?

**Maria**: *[Doesn't hesitate]* 30 percent, easy. Maybe more. For probably two to three months until people get comfortable. And that's assuming the new system is well-designed and we have good training. If it's poorly designed or training is inadequate? Could be six months of pain.

**DF**: That's... significant.

**Maria**: *[Nods firmly]* That's why I'm nervous when I hear about this stuff. I've lived through system changes before.

---

## Part 3: SAP Experience - What Really Happened

**DF**: Speaking of which - let's talk about SAP. You were here in 2018, right? What actually happened from your perspective on the floor?

**Maria**: *[Exhales sharply]* SAP. Yeah. That was a nightmare. You want the real story or the sanitized version?

**DF**: Real story, please.

**Maria**: Okay. So, corporate decided we needed a "modern ERP system." SAP was supposed to integrate everything - inventory, production, quality, financials. They promised it would make our lives easier. *[Laughs bitterly]*

**DF**: What actually happened?

**Maria**: Training was a joke. They gave us a two-hour overview session - PowerPoint slides, mostly. Click here, click there, here's how you enter a work order. No hands-on practice, no real scenarios, no troubleshooting. Just "here's the happy path, good luck."

**Maria**: Then go-live day comes. First shift starts using it. Within an hour, we knew we were in trouble. The system was slow - screens took 10-15 seconds to load. The workflow made no sense - took 12 clicks to do what used to take 3. And half the time, it just... hung. Spinning wheel of death.

**DF**: What did you do?

**Maria**: First day, we tried to make it work. Operators were frustrated, production slowed way down, but we pushed through. Day two, same thing. By day three, people were talking about calling the union - this was before I was in management, I was still a team lead and union member myself.

**DF**: How long did this go on?

**Maria**: Three weeks of chaos. Production dropped by 50 percent - we couldn't keep up with orders. Quality suffered because people were rushing to make up lost time. Operators were staying late, coming in early, working through breaks just to hit their numbers. Morale was in the toilet.

**Maria**: Finally, Robert - he was plant manager then - called an emergency meeting with the CEO and said we had to roll back or we'd lose the Detroit Dynamics contract. They rolled back to the old system. Took another week to get fully back to normal because we'd accumulated a backlog of data entry.

**DF**: What was the impact on your team personally?

**Maria**: *[Quiet for a moment]* We lost three people. Two operators quit - found jobs elsewhere because they didn't trust management anymore. One team lead transferred to day shift because the stress was too much. Those were good people, experienced people. Hard to replace.

**Maria**: And the rest of us? We're still gun-shy. When someone from corporate says "we're implementing a new system," people start updating their resumes. That's the SAP legacy.

**DF**: What should they have done differently?

**Maria**: *[Counts on fingers]*

**Maria**: One - actually train us. Not a two-hour slideshow. Weeks of hands-on practice with realistic scenarios. Time to make mistakes in a safe environment.

**Maria**: Two - pilot it. Don't do big-bang cutover. Try it on one production line, work out the kinks, then expand.

**Maria**: Three - listen to the floor. We told them on day one the system was too slow and the workflow was broken. They said "give it time, you'll adjust." We didn't adjust. The system was bad.

**Maria**: Four - have a rollback plan. They didn't. They committed to SAP and refused to admit it wasn't working until we were in crisis mode.

**Maria**: Five - support. When things broke at 2 AM, there was no one to call. We were on our own.

**DF**: Did anyone from the SAP implementation team ever actually work a shift on the floor to see how the system performed in real conditions?

**Maria**: *[Laughs]* No. They came down for a "go-live celebration" during day shift when the managers were around. Took some photos, shook some hands, left. Never saw them again after that.

---

## Part 4: Operator Capabilities & Training Reality

**DF**: Let me ask about your team's capabilities. You've got 60 operators on second shift. What's the range of technical comfort level?

**Maria**: *[Thinks]* I'd say... maybe a third are comfortable with technology. They have smartphones, use apps, pick up new software quickly. Another third are okay - they can learn, but it takes time and patience. The last third? They struggle. Not because they're not smart - some of my best operators are in this group - but because they didn't grow up with computers and it doesn't come naturally.

**DF**: What's the age breakdown?

**Maria**: Second shift skews older because of seniority. We've got operators in their 20s and 30s, but most are 40s, 50s, even a few in their 60s. The older folks have 15, 20, 25 years on the floor. They're incredibly valuable - they know the machines, the processes, the tricks. But ask them to learn a whole new computer system? That's tough.

**DF**: Jimmy mentioned in his interview that the union is concerned about older workers being left behind if systems change. Is that a real concern?

**Maria**: Absolutely. Look, I love Jimmy, but sometimes he makes it sound more dramatic than it is. Most people can learn if you give them real support. But here's the thing - if you bring in a completely new system and give them inadequate training, then yeah, you're setting them up to fail. And when they fail, what happens? Management says "they can't do the job anymore" and brings in younger workers. That's what people are afraid of.

**DF**: Is that fear justified based on past behavior?

**Maria**: *[Pauses, choosing words carefully]* I'm management now, so I have to be careful here. But yeah, I've seen it. Not a mass layoff, but a slow shift. Older workers get reassigned to "simpler" tasks, opportunities go to younger workers, and eventually the older folks get frustrated and take early retirement. It's not malicious, but it happens.

**DF**: What would "real training" look like for a major system change like moving MES to the cloud?

**Maria**: *[Becomes animated]* Okay, so if I was designing it:

**Maria**: Phase One - Before anything changes, bring in trainers who actually understand manufacturing. Not IT people reading from a script. People who've worked on production floors. Give us two weeks of classroom training - real hands-on in a training environment, not production. Let people make mistakes without consequences.

**Maria**: Phase Two - Pilot with volunteers. Pick one production line, pick operators who are tech-savvy and willing, run both systems in parallel for three months. Let them find all the problems. Fix the problems. Document the workarounds.

**Maria**: Phase Three - Expand gradually. One line at a time. Each new line gets two weeks of training plus two weeks of hand-holding with the pilot team helping out. Don't move to the next line until the current line is comfortable.

**Maria**: Phase Four - Ongoing support. Not just day shift. 24/7 hotline with people who know MES and manufacturing, not just IT generalists. For at least six months after full rollout.

**DF**: What would that cost in terms of time and resources?

**Maria**: *[Shrugs]* A lot. But less than losing three weeks of production like we did with SAP. And definitely less than losing the Detroit Dynamics contract.

**DF**: Robert mentioned in his interview that he wants Michael to work a shift on the floor. Do you think that would help?

**Maria**: *[Smiles]* Robert told you about that? Yeah, I think it would make a huge difference. Not a tour - an actual shift. Let Michael enter work orders in MES during a production crunch. Let him see what happens when the system hiccups and we've got a hot order due. Let him deal with a quality issue at 11 PM when there's no QA manager around and he has to make a judgment call.

**Maria**: If he does that, he'll understand why we're so protective of stability. And honestly, if he's willing to do that, it tells us he actually cares about getting it right. That builds trust.

---

## Part 5: Union Sentiment & Change Management

**DF**: Speaking of trust - you were union for 15 years before becoming management three years ago. What's the sentiment on the floor about this modernization initiative?

**Maria**: *[Sighs]* Mixed, leaning skeptical. The younger operators - late 20s, early 30s - they're actually kind of interested. They've heard "cloud" means better interfaces, mobile access, modern tools. They're willing to give it a shot if it's done right.

**Maria**: The middle group - 40s - they're cautious. They've seen initiatives come and go. They'll believe it when they see it. But they're not against it if we're involved and it actually makes their jobs easier.

**Maria**: The older operators - 50s and 60s - they're worried. Not just about learning new systems, but about what it means for their jobs. They remember SAP. They remember promises that didn't pan out. And they hear "cloud" and "modernization" and think "they're getting ready to replace us."

**DF**: Is that a realistic fear?

**Maria**: *[Pauses]* Depends on how it's done. If management comes in and says "we're moving to the cloud, here's two hours of training, figure it out," then yeah, some people won't make it and they'll feel pushed out. If management says "we're partnering with you on this, we'll train you for real, we're committed to helping you succeed," then no, people can adapt.

**DF**: What about the "no layoffs" promise? Do people believe it?

**Maria**: *[Laughs softly]* Not really. They've heard "no layoffs" before. What happens is "no layoffs... but we're not filling positions when people retire. And we're reorganizing, so your role is going away but there's this other role you can apply for if you want." Technically not a layoff, but effectively the same thing.

**DF**: So how do you build trust?

**Maria**: Actions, not words. If you want people to believe "no layoffs," show them the retraining plan upfront. Budget for it. Start training people before the system changes, not after. Celebrate people who successfully transition. Make it clear that learning the new system is part of the job, not a test to weed people out.

**Maria**: And involve the union early. Not "here's what we're doing, deal with it." More like "here's what we're thinking, what concerns do you have, how can we address them together?"

**DF**: Have you talked to Jimmy about this?

**Maria**: Not officially - I'm management, he's union, there's a line. But I know Jimmy from my union days. He's reasonable. He's not trying to block progress. He just wants to make sure his people are treated fairly. If you engage him early, partner with him, he'll work with you. If you ignore him until you're ready to implement, he'll fight you.

**DF**: If this is done badly - inadequate training, rushed timeline, people struggling - what happens?

**Maria**: Best case? Passive resistance. People slow down, find reasons why the new system doesn't work, quietly sabotage by working exactly to spec but not using their judgment. Productivity drops, quality suffers.

**Maria**: Worst case? Jimmy files grievances, calls for a work-to-rule, maybe even a strike authorization vote. I don't think he wants that - strikes hurt everyone - but if people feel backed into a corner, they'll vote yes.

**DF**: What would prevent that worst case?

**Maria**: Communication. Respect. Partnership. Treat us like adults who have valuable input, not like obstacles to be managed.

---

## Part 6: System Requirements & What Actually Matters

**DF**: Let's talk about what you actually need from these systems. If you could wave a magic wand and fix three things about the current setup, what would they be?

**Maria**: *[Doesn't hesitate]*

**Maria**: One - reliability. I don't want MES going down during production. I don't want "the server crashed" or "the network is flaky." I need 99.9% uptime, and when it does go down, I need someone who can fix it fast, any time of day or night.

**Maria**: Two - speed. Right now, MES is... okay. It's not fast, but it's tolerable. If we move to the cloud and add latency, and suddenly every screen takes three seconds to load instead of one? That adds up. Operators are hitting that system hundreds of times per shift. Three seconds times 300 transactions times 60 operators? That's hours of lost productivity.

**Maria**: Three - simplicity. I want workflows that make sense. Minimum clicks to do common tasks. Clear error messages when something goes wrong, not "Error 0x8004792E - Contact your administrator." I want my operators spending time making parts, not fighting the software.

**DF**: What about new capabilities? Are there things you wish you could do that you can't do now?

**Maria**: *[Thinks]* Mobile would be nice. Right now, operators have to walk to the MES terminal. If they could use a tablet or something to enter data at the machine, that would save time.

**Maria**: Better dashboards would help. Right now, I have to pull reports to see how the shift is tracking - production counts, downtime, quality issues. If I had a real-time dashboard I could glance at, that would help me stay ahead of problems.

**Maria**: And honestly? Integration. Right now, MES doesn't talk to maintenance very well. When a machine goes down, I have to manually notify maintenance, they open a ticket in their system, there's this whole back-and-forth. If that was automated - machine goes down, maintenance automatically notified, ticket automatically created, I can see status in real-time - that would be huge.

**DF**: Those sound reasonable. What about things you absolutely don't want to change?

**Maria**: *[Firm]* Don't mess with the core workflow unless you have a really good reason. My operators know the sequence: pull work order, check materials, start job, log progress, quality check, complete. That workflow is muscle memory. If you rearrange it just to make it "modern," you're creating problems for no reason.

**Maria**: And don't take away functionality we depend on. Sometimes IT sees a feature that's "rarely used" in the data and thinks "let's remove that to simplify." But that "rarely used" feature might be critical when we need it. Like emergency work orders, or rework tracking, or manual quality overrides for engineering. We don't use them often, but when we do, we REALLY need them.

**DF**: What would success look like for you? If this modernization project goes well, what would be different in six months, a year?

**Maria**: *[Leans back, thinking]*

**Maria**: In six months? We've piloted the new MES on one line. The operators on that line are comfortable with it, maybe even prefer it. We've identified and fixed the major issues. My other operators are cautiously optimistic because they've seen it work.

**Maria**: In a year? Most lines have transitioned. Operators are trained and confident. The system is stable - maybe even more stable than before. We're starting to see the benefits - better dashboards, mobile access, faster workflows. And morale is good because people feel like they were part of the process, not victims of it.

**Maria**: That would be success.

**DF**: And what would failure look like?

**Maria**: *[Grimaces]* We go live too fast, training is inadequate, the system has problems we didn't catch in testing. Production drops, operators are frustrated, quality suffers. Management pressures us to "make it work," but we don't have the tools or support to do that. People start calling out sick, morale tanks, maybe a few key people quit.

**Maria**: Six months later, we've either rolled back and wasted a bunch of money, or we're still limping along with a system that nobody likes and productivity that never fully recovered.

**Maria**: That's what I'm afraid of. Not because I'm against change - I'm not. But because I've seen it go wrong, and I don't want to go through that again.

---

## Part 7: Downtime Tolerance & Production Reality

**DF**: Let me ask about downtime. Michael says "zero impact to manufacturing operations." Robert says "parallel running during migration, cutover during maintenance windows." What's the actual tolerance?

**Maria**: *[Laughs]* Michael's not wrong, exactly. We can't have planned downtime during production hours. If MES is down for four hours during second shift, that's $2.4 million in lost production. So from that perspective, yeah, zero tolerance.

**Maria**: But Robert's right too. You can't just flip a switch. You need parallel running to validate the new system works before you cut over. And cutover needs to happen during a maintenance window - Sunday morning when we're not running, or Christmas week when we're on reduced schedule.

**DF**: How many Sunday morning windows do you have per year?

**Maria**: 52 Sundays. But not all of them are available. Some Sundays we're running overtime for hot orders. And we share those windows with mechanical maintenance and electrical maintenance. IT gets maybe one Sunday a month, four hours max. So call it 12 windows per year, 48 hours total.

**DF**: Is that enough for a major migration?

**Maria**: *[Shakes head]* Not even close. If you're migrating multiple systems, you're talking hundreds of hours of cutover work. Even if each individual cutover only takes four hours, you've got sequential dependencies - can't migrate the warehouse system until the ERP is done, can't migrate MES until the warehouse is done. That's years of Sunday mornings.

**DF**: So what's the answer?

**Maria**: Parallel running. Like Robert said. Run both systems at once, sync data between them, validate they match. Do that for three to six months depending on criticality. Then the actual cutover is lower risk because you know the new system works.

**Maria**: But parallel running is expensive. Double infrastructure, double data entry in some cases, constant monitoring to make sure they stay in sync. And it's a pain for operators - they might have to enter data in both systems until cutover.

**DF**: Would operators accept that temporary pain?

**Maria**: *[Nods]* If it means the final system works and we don't have another SAP disaster? Yeah. People will grumble, but they'll do it. Especially if you're honest about it - "this is going to be annoying for a few months, but it's the safe way to do this."

**DF**: What systems absolutely cannot fail without stopping production?

**Maria**: MES is number one. If MES goes down for more than an hour, we're in trouble. We can limp along on paper for a bit, but not long.

**Maria**: ERP is second. We need inventory data. If we can't see what materials we have, we can't run production efficiently.

**Maria**: After that, it's less critical but still important. QMS for quality tracking. Email for communication. The machine PLCs obviously, but that's Lisa's domain.

**DF**: If we had to prioritize - which system should be migrated last because it's highest risk?

**Maria**: *[Doesn't hesitate]* MES. Absolutely MES. That's the heart of production. You migrate everything else first, prove you can do it successfully, build trust. Then tackle MES with all the lessons learned.

---

## Part 8: Safety & Compliance

**DF**: One more thing I want to touch on - safety. Are there safety implications if systems fail or if operators are confused by new interfaces?

**Maria**: *[Becomes very serious]* Yes. Absolutely yes. This is something people don't think about enough.

**Maria**: Example: Operator is running a CNC machine. The MES work order tells them which fixture to use, which program to run, what speeds and feeds. If the operator pulls the wrong work order from a confusing interface, or misreads an unclear screen, they could set up the machine incorrectly. Best case, you get scrap. Worst case, the part comes loose, the cutter breaks, and debris goes flying. That's a safety incident.

**Maria**: Another example: Quality checks. Some of our parts have critical dimensions - if they're out of spec, the part could fail in the customer's application. That's an airplane component or a medical device. The QMS tells operators which dimensions to check and what the tolerances are. If an operator skips a check because they're confused by a new interface, or if they log the check incorrectly, that's a quality failure that could harm someone downstream.

**DF**: Have you seen that happen?

**Maria**: Not serious injuries, thankfully. But during the SAP mess, we had a couple close calls. One operator set up a job wrong because the SAP work order was confusing - part came loose during machining. Another operator missed a quality check because they clicked the wrong button in the new interface. We caught it before it shipped, but it was close.

**DF**: What does that mean for system changes?

**Maria**: It means you can't rush. It means training has to be thorough. It means the interface has to be clear - no ambiguity, no confusing layouts, good error prevention. And it means you need to involve operators in testing - not just "does this button work?" but "can you find this information quickly when you're under pressure at 3 AM?"

**DF**: Does Dr. Rodriguez know about these safety considerations?

**Maria**: Patricia? Yeah, she gets it. She's been pushing for better system validation for years. But sometimes there's tension between Quality's requirements and IT's timelines. Patricia wants extensive testing and documentation. IT wants to move fast. Guess who usually wins?

**DF**: What should happen?

**Maria**: Patricia should have veto power on any system that affects safety or quality. If she says "this isn't ready," that needs to be the final word. And Robert should back her up on that - he's ultimately responsible for plant safety.

---

## Part 9: Bottom Line & Final Thoughts

**DF**: Maria, we're coming up on an hour and 15. Let me ask you a few final questions. Bottom line: Is this Azure modernization initiative a good idea, from your perspective?

**Maria**: *[Long pause]*

**Maria**: I think it's necessary. Our systems are aging. We need to do something. And cloud has advantages - better disaster recovery, easier to scale, potentially better tools.

**Maria**: But it has to be done right. Not like SAP. That's my bottom line.

**DF**: What does "done right" mean?

**Maria**: It means taking the time to do it properly. Not cutting corners. Not rushing because Michael promised the board a timeline.

**Maria**: It means real training - months, not hours. Hands-on, practical, with support.

**Maria**: It means piloting before full rollout. Proving it works on one line before rolling it out to all of them.

**Maria**: It means listening to the people who use the systems. Not just nodding and ignoring us, but actually incorporating our feedback.

**Maria**: It means having adequate support. 24/7, people who know manufacturing, not just generic IT support.

**Maria**: And it means being honest about the timeline and costs. If this is going to take three years and cost $8 million, say that. Don't promise 18 months and $3 million and then act surprised when it takes longer and costs more.

**DF**: If Michael asked you for one piece of advice, what would it be?

**Maria**: *[Looks directly at interviewer]*

**Maria**: Come work a shift on my floor. Not a tour, not a walk-through. An actual eight-hour shift. Enter work orders in MES during a production crunch. Deal with a system hiccup at 2 AM. Talk to my operators - the ones who've been here 20 years and know these machines inside out but struggle with computers.

**Maria**: Do that, and you'll understand what we need. You'll understand why we're cautious. And you'll build trust with the people who are going to make or break this initiative.

**Maria**: Robert told you the same thing, didn't he?

**DF**: He did.

**Maria**: *[Smiles]* That's because Robert knows. He's been here. He understands. Michael's a smart guy, I'm sure. But smart doesn't matter if you don't understand the reality on the ground.

**DF**: What if Michael doesn't take that advice? What if he tries to push this through without that floor-level understanding?

**Maria**: *[Sighs]* Then we're probably looking at SAP 2.0. Maybe it doesn't fail as badly - maybe Sarah's team prevents the worst of it. But it'll be messy, expensive, and painful. And people will remember.

**Maria**: Look, I want this to succeed. I really do. But I'm also realistic. I've seen how these things go. The odds of success go way up if leadership actually understands what they're asking for and partners with us. The odds go way down if they treat us like widgets to be managed.

**DF**: Last question. If you could send one message to Michael, Jennifer, and the board, what would it be?

**Maria**: *[Thinks carefully]*

**Maria**: We're not the enemy. We're not resisting change because we're stubborn or lazy or afraid. We're cautious because we've been burned before. We're protective because these systems are critical to our jobs and to the company's success.

**Maria**: If you partner with us - really partner, not just pretend to involve us - we'll make this work. My operators are smart, capable, adaptable people. Give them real training, real support, and real respect, and they'll deliver.

**Maria**: But if you treat this like a technical project instead of a people project, it will fail. The technology might work fine, but the people won't adopt it, and you'll have spent millions for nothing.

**Maria**: That's what I'd tell them.

**DF**: Maria, this has been incredibly valuable. Thank you for your honesty and your time. Is there anything else you think I should know?

**Maria**: *[Stands up, picks up her radio]*

**Maria**: Just one thing. Whatever you decide, decide soon. The rumors are already flying. Operators are worried about their jobs, wondering if the company is going to sell, if we're automating them out of work. The longer this drags on without clear communication, the more anxious people get.

**Maria**: So if you're going forward, tell us. Tell us the plan, the timeline, what we can expect. If you're not going forward, tell us that too. The worst thing is uncertainty.

**DF**: I'll make sure that feedback gets to the team. Thanks again, Maria.

**Maria**: No problem. Good luck. You're going to need it.

*[Maria leaves. Through the window, you can see her stopping to talk to an operator on the floor, checking something on a screen, then moving on to the next station. Back to work.]*

---

## Post-Interview Analysis

### Interviewer Observations

**Demeanor**: Professional, direct, pragmatic. Maria is protective of her team but not defensive. She's clearly lived through enough "corporate initiatives" to be skeptical, but she's open to change if done properly.

**Confidence Level**: Very high on operational topics (MES, training, floor dynamics). Maria speaks from 18 years of experience and has clear, specific examples.

**Body Language**: Relaxed but alert. Engaged throughout. Became more animated when discussing training programs (passion point) and more serious when discussing safety (responsibility).

**Suspected But Unspoken**: Maria is caught between her union roots and management responsibility. She's careful not to criticize management too directly, but her sympathies clearly lie with the operators. She's also worried about her own job security if this initiative fails.

---

## Key Themes Identified

### 1. SAP Trauma is Real and Lasting
The 2018 SAP implementation failure created deep organizational scars that still affect how employees view any "modernization" initiative. Three weeks of 50% production loss, inadequate training (2-hour overview), and ultimate rollback. Three employees lost (2 quit, 1 transferred). This trauma shapes current skepticism and resistance.

**Impact on Current Initiative**: Any system change will trigger fear and resistance based on SAP experience. Must be explicitly acknowledged and addressed.

### 2. Training Must Be Substantial, Not Token
Maria's detailed four-phase training program:
- Phase 1: 2 weeks classroom (hands-on, manufacturing-focused trainers)
- Phase 2: 3-month pilot with volunteers
- Phase 3: Gradual rollout, line-by-line with 2 weeks training + 2 weeks hand-holding
- Phase 4: 24/7 support for 6 months post-rollout

**Impact on Budget**: Real training costs $50K per person per Maria's estimate. With 180 operators, that's $9M just for training.

### 3. MES is Critical and High-Risk
- 180 operators use MES multiple times per shift
- 10+ years of muscle memory with current system
- Interface changes could cause 30% productivity drop for 2-3 months (potentially 6 months if poorly executed)
- MES downtime during production = $240K per day lost

**Impact on Timeline**: MES should be migrated LAST after proving success on other systems.

### 4. Operator Capability Range
- 1/3 tech-comfortable (pick up new systems quickly)
- 1/3 okay (can learn with time and patience)
- 1/3 struggle (older workers, not computer-native, need substantial support)

**Impact on Training**: One-size-fits-all training won't work. Need differentiated approach based on capability.

### 5. Floor-Level Partnership is Essential
Both Robert and Maria emphasize: Michael must work an actual 8-hour shift on the floor to build trust and understand reality. This is about credibility and demonstrating genuine commitment to understanding their world.

**Impact on Leadership**: Michael's credibility with floor workers depends on this action.

### 6. Parallel Running is Necessary but Expensive
- 3-6 months parallel operation for critical systems (especially MES)
- Doubles infrastructure costs
- Requires double data entry in some cases
- Annoying for operators but acceptable if communicated honestly

**Impact on Budget**: Adds $1-2M in parallel running costs (Kevin's estimate confirmed by operational perspective).

### 7. Sunday Maintenance Windows are Limited
- 52 Sundays per year
- Shared with mechanical/electrical maintenance
- IT gets ~12 windows per year (one per month)
- 4 hours max per window
- Total: 48 hours per year for ALL IT changes

**Impact on Timeline**: Sequential migration of multiple systems over years, not months.

### 8. Safety and Quality Implications
Operator confusion with new interfaces can lead to:
- Incorrect machine setups (safety hazard)
- Missed quality checks (customer safety hazard)
- During SAP, had "close calls" with safety incidents

**Impact on Governance**: Patricia (Quality Manager) should have veto power on systems affecting safety/quality.

### 9. Union Sentiment is Mixed but Manageable
- Younger operators (20s-30s): Interested, willing to try
- Middle operators (40s): Cautious, "show me it works"
- Older operators (50s-60s): Worried about job security and ability to learn

**Impact on Change Management**: Early union engagement (Jimmy), visible retraining investment, "no layoffs" backed by actions not just words.

### 10. Communication and Transparency are Critical
Uncertainty is damaging. Rumors are already flying. Workers need clear, honest information about plans, timeline, and what to expect. Worst thing is prolonged ambiguity.

**Impact on Project Kickoff**: Communication plan must be part of Phase 0 → Phase 1 transition.

---

## Critical Insights

### What Maria Confirms
- ✅ Robert's requirement for Michael to work a floor shift
- ✅ Jimmy's concerns about inadequate training and job security fears
- ✅ Sarah's assessment that timeline is "years not quarters"
- ✅ Kevin's parallel running requirements (3-6 months for critical systems)
- ✅ Patricia's validation and testing needs
- ✅ Jennifer's concern about realistic cost and timeline expectations

### What Maria Adds (New Information)
- ⚠️ **NEW**: Specific SAP failure details (3 weeks chaos, 50% production drop, 3 people lost, rollback)
- ⚠️ **NEW**: 30% productivity drop estimate during MES transition for 2-3 months
- ⚠️ **NEW**: Safety incidents risk during system changes (close calls during SAP)
- ⚠️ **NEW**: Only 12 Sunday windows per year, 48 hours total (shared with mechanical/electrical)
- ⚠️ **NEW**: Operator capability breakdown (1/3 comfortable, 1/3 okay, 1/3 struggle)
- ⚠️ **NEW**: Floor sentiment range by age group (younger interested, middle cautious, older worried)
- ⚠️ **NEW**: Detailed four-phase training program design
- ⚠️ **NEW**: MES goes down ~once every 2 months, usually fixed within an hour
- ⚠️ **NEW**: PLC integration fails ~once per month, can be down for hours
- ⚠️ **NEW**: New operator MES training: 2 weeks basic, 3-6 months to proficiency
- ⚠️ **NEW**: Non-tech-savvy operator MES training: 1+ months basic, never fast
- ⚠️ **NEW**: Operators use MES hundreds of times per shift (latency matters)
- ⚠️ **NEW**: "Rarely used" critical features (emergency work orders, rework tracking, manual quality overrides)
- ⚠️ **NEW**: Mobile MES access would be valuable (reduce walks to terminals)
- ⚠️ **NEW**: Real-time supervisor dashboards needed (currently pull reports)
- ⚠️ **NEW**: MES-maintenance integration gap (manual notifications, separate systems)

### What Maria Challenges
- ❌ Any timeline that doesn't include months of training
- ❌ Any approach that doesn't pilot on one line first
- ❌ Any cutover approach that isn't parallel running for MES
- ❌ Any "no layoffs" promise without visible retraining investment
- ❌ Any plan that treats this as "technical project" vs "people project"
- ❌ Any timeline based on 48 hours/year of Sunday windows being sufficient
- ❌ IT removing "rarely used" features without understanding criticality

---

## Requirements Generated

### Explicit Requirements
1. **Michael Floor Shift**: 8-hour shift working alongside operators before finalizing plans (Robert and Maria both require)
2. **MES Migration Last**: Migrate other systems first, prove success, then tackle MES with lessons learned
3. **Pilot Program**: One production line, volunteer operators, 3 months parallel running minimum
4. **Training Program**: 4-phase approach (2 weeks classroom + 3 months pilot + gradual rollout + 6 months 24/7 support)
5. **24/7 Manufacturing Support**: People who know MES and manufacturing, not just IT generalists
6. **Parallel Running for MES**: 3-6 months minimum
7. **Operator UAT Involvement**: Operators test system in realistic scenarios before deployment
8. **Patricia Veto Power**: Quality Manager must approve systems affecting safety/quality
9. **Communication Plan**: Clear, regular updates to floor workers about plans and timeline
10. **Preserve Core Workflow**: Don't change MES workflow sequence without compelling reason

### Implicit Requirements
1. **Mobile MES Access**: Tablets at machines to reduce terminal walks (productivity improvement)
2. **Real-Time Supervisor Dashboards**: Visibility into shift performance without pulling reports
3. **MES-Maintenance Integration**: Automated work order creation when machines fail
4. **Critical Feature Retention**: Keep emergency work orders, rework tracking, manual quality overrides
5. **Clear Error Messages**: No cryptic error codes, provide actionable guidance
6. **Minimal Clicks for Common Tasks**: Optimize for operator efficiency
7. **Training Environment**: Non-production system for practice without consequences
8. **Trainer Quality**: Manufacturing-experienced trainers, not IT reading scripts
9. **Differentiated Training**: Adjust approach based on operator tech comfort level
10. **Rollback Capability**: Ability to return to old system if new system fails

### Non-Functional Requirements
1. **MES Uptime**: 99.9% availability during production hours
2. **MES Performance**: Screen load times <1 second (vs. current ~1 second, not 3+ seconds)
3. **MES Downtime Recovery**: <1 hour for critical issues, 24/7 support availability
4. **Training Duration**: Minimum 2 weeks classroom + 2 weeks hands-on per line
5. **Support Response Time**: <15 minutes for production-down issues, 24/7
6. **Pilot Duration**: 3 months minimum for MES, may need 6 months
7. **Gradual Rollout**: One line at a time, don't proceed until current line comfortable

---

## Risks Identified

### New Risks

**RISK-034: SAP Trauma Organizational PTSD** (CRITICAL)
- **Category**: Organizational/Change Management
- **Probability**: 5 (Certain - already exists)
- **Impact**: 4 (Major - affects morale, resistance, attrition)
- **Severity**: 20/25 (CRITICAL)
- **Description**: 2018 SAP failure created lasting trauma. Any "modernization" initiative triggers fear and resistance. Three weeks of chaos, 50% production drop, inadequate training, ultimate rollback. Lost 3 employees (2 quit, 1 transferred). Workers are "gun-shy" and start updating resumes when corporate mentions system changes.
- **Impact**: Passive resistance, slower adoption, higher attrition risk, morale damage
- **Mitigation**: 
  - Explicitly acknowledge SAP failure and what will be different this time
  - Show evidence of learning (pilot approach, real training, parallel running)
  - Build trust through actions (Michael floor shift, early engagement)
  - Communication: "Not like SAP" requires demonstrable proof
- **Owner**: Michael Chen + Change Management

**RISK-035: Safety Incidents During Transition** (HIGH)
- **Category**: Safety/Regulatory
- **Probability**: 3 (Medium - 50%)
- **Impact**: 5 (Critical - worker injury, regulatory issues, customer safety)
- **Severity**: 15/25 (HIGH)
- **Description**: Operator confusion with new interfaces can lead to incorrect machine setups (safety hazard), missed quality checks (customer safety hazard). During SAP, had "close calls" with incorrect job setups and missed quality checks. Parts for aerospace and medical devices require perfect quality checks.
- **Impact**: Worker injury, customer safety incidents, regulatory violations, liability, reputation damage
- **Mitigation**:
  - Involve operators in testing and interface design
  - Thorough training with safety scenario practice
  - Clear, unambiguous interfaces with error prevention
  - Patricia (Quality) has veto power on systems affecting safety/quality
  - Robert backs up Patricia on safety veto
  - Enhanced supervision during transition period
- **Owner**: Patricia Rodriguez + Robert Turner + Sarah Mitchell

**RISK-036: Sunday Window Capacity Constraint** (MEDIUM-HIGH)
- **Category**: Timeline/Operational
- **Probability**: 5 (Certain - only 48 hours/year available)
- **Impact**: 3 (Moderate - extends timeline significantly)
- **Severity**: 15/25 (HIGH)
- **Description**: Only 12 Sunday maintenance windows per year (4 hours each = 48 hours total). Shared with mechanical and electrical maintenance. Even simple cutovers take 4 hours. Sequential dependencies (ERP → warehouse → MES) mean migrating multiple systems over years, not months. Cannot do parallel work on systems with dependencies.
- **Impact**: Timeline extends from 18 months to 3-5 years just based on cutover window availability
- **Mitigation**:
  - Parallel running reduces cutover complexity (most work done in advance)
  - Christmas shutdown week for tactical upgrades
  - Coordinate with mechanical/electrical maintenance for shared windows
  - Accept multi-year timeline as reality
- **Owner**: Sarah Mitchell + Robert Turner + Kevin Martinez

**RISK-037: Training Budget Inadequacy** (HIGH)
- **Category**: Financial
- **Probability**: 4 (High - not budgeted)
- **Impact**: 4 (Major - training failure leads to adoption failure)
- **Severity**: 16/25 (HIGH)
- **Description**: Real training costs ~$50K per operator (Maria's estimate). With 180 operators, that's $9M just for MES training alone. Jennifer's budget model may not include this level of training investment. Inadequate training budget leads to token training (like SAP's 2-hour overview), which leads to adoption failure.
- **Impact**: Adoption failure, productivity drops, quality issues, potential project failure
- **Mitigation**:
  - Update budget model with realistic training costs
  - Four-phase training approach (classroom + pilot + rollout + support)
  - Manufacturing-experienced trainers (not IT reading scripts)
  - Differentiated training based on operator capability
  - 24/7 support for 6 months post-rollout
- **Owner**: Jennifer Walsh + Michael Chen + HR

### Risk Elevation Updates

**RISK-033: MES Floor Adoption Resistance** (Increase to CRITICAL)
- **Previous Severity**: HIGH (20/25)
- **New Severity**: 20/25 (CRITICAL - confirmed by floor supervisor)
- **Update**: Maria confirms 30% productivity drop for 2-3 months is realistic, potentially 6 months if poorly executed. With 180 operators, muscle memory of 10+ years, and SAP trauma, resistance is significant. Risk is not theoretical - it's grounded in past experience and current capability assessment.

---

## Contradictions Flagged

### Maria vs. Michael on Timeline (IMPLICIT)
- **Michael**: 18-month transformation
- **Maria**: "Months of training" + "3-month pilot" + "gradual rollout one line at a time" + "6 months support" = Multi-year timeline minimum
- **Analysis**: Maria's success scenario (6 months for pilot, 1 year for most lines) implies 18-24 months for MES alone, after other systems have been migrated successfully
- **Resolution Needed**: Michael must accept multi-year timeline

### Maria vs. IT on "Rarely Used Features" (IMPLICIT)
- **Typical IT Thinking**: Remove rarely-used features to simplify interface
- **Maria**: Those features are critical when needed (emergency work orders, rework tracking, manual quality overrides). Usage data shows frequency, not criticality.
- **Analysis**: Feature decisions must consider criticality, not just usage frequency
- **Resolution Needed**: Include floor users in feature prioritization decisions

### Maria vs. Management on "No Layoffs" Promise (IMPLICIT)
- **Management Promise**: "No layoffs"
- **Floor Reality**: Workers don't believe it based on past experience. "No layoffs" has meant "no backfill, reorganization, role changes" which feels like layoffs.
- **Analysis**: Trust gap between promise and belief
- **Resolution Needed**: Demonstrate commitment through visible retraining investment BEFORE system changes

---

## Open Questions Generated

### For Michael
- ❓ **Will Michael commit to working an 8-hour shift on the floor?** (Robert and Maria both require this for credibility)
- ❓ **Will Michael explicitly acknowledge SAP failure and explain what will be different?** (Address organizational trauma directly)
- ❓ **Is Michael willing to accept multi-year timeline for proper training and rollout?** (Maria's success scenario is 18-24 months for MES alone)
- ❓ **Will Michael partner with floor workers or treat them as obstacles to manage?** (Maria's "people project vs technical project" distinction)

### For HR/Training
- ❓ **What is realistic training budget per operator?** (Maria estimates $50K, need HR validation)
- ❓ **Who will design and deliver training program?** (Need manufacturing-experienced trainers, not IT generalists)
- ❓ **What is differentiated training approach for different capability levels?** (1/3 comfortable, 1/3 okay, 1/3 struggle)
- ❓ **How will company demonstrate "no layoffs" commitment visibly?** (Actions to build trust before system changes)

### For Project Team
- ❓ **What is pilot program structure?** (Which line, which operators, duration, success criteria)
- ❓ **What is gradual rollout plan?** (Timeline for each line, lessons learned process between lines)
- ❓ **What is 24/7 support model?** (Who, coverage, expertise level, escalation)
- ❓ **How will operators be involved in UAT and testing?** (Not just functional testing, but usability under pressure)

### For Operations
- ❓ **What is communication plan to floor workers?** (Address rumors, reduce uncertainty)
- ❓ **How will floor workers be involved in ongoing decisions?** (Partnership vs top-down)
- ❓ **What is Christmas shutdown timeline for tactical upgrades?** (Opportunity for lower-risk changes)

### For Quality (Patricia)
- ❓ **Does Patricia have explicit veto power on systems affecting safety/quality?** (Maria says she should, but is it formalized?)
- ❓ **What is validation approach for safety-critical systems?** (MES work orders, quality checks)

---

## Stakeholder Alignment Assessment

### Aligned With
- ✅ **Robert Turner**: Floor immersion requirement, parallel running, partnership approach, MES criticality
- ✅ **Jimmy Garcia**: Real training, early engagement, respect for workers, no-layoffs backed by actions
- ✅ **Sarah Mitchell**: Timeline reality (years not quarters), system complexity, training needs
- ✅ **Kevin Martinez**: Parallel running requirements (3-6 months for critical systems)
- ✅ **Patricia Rodriguez**: Validation importance, testing thoroughness, safety/quality veto power
- ✅ **Jennifer Walsh**: Realistic cost and timeline expectations, learning from past failures

### Potentially Misaligned With
- ⚠️ **Michael Chen**: Timeline expectations (if still thinking 18 months vs 3-5 years)
- ⚠️ **Michael Chen**: Understanding of floor reality (if hasn't worked a shift)
- ⚠️ **Michael Chen**: Training investment magnitude ($9M just for operator training)
- ⚠️ **Board**: May not understand timeline required for proper execution
- ⚠️ **IT Team**: May want to move faster than floor can absorb changes

### Critical Dependencies
- Maria's success depends on: Michael floor immersion, real training budget, pilot approach, gradual rollout
- Maria's support enables: Operator buy-in, smooth adoption, productivity maintenance, quality maintenance
- Maria's resistance creates: Passive resistance from operators, adoption failure, potential project failure

---

## Bottom Line Assessment

**Maria's Verdict**: "Necessary, but must be done right. Not like SAP."

### Success Criteria (Maria's Definition)
- **6 months**: Pilot successful on one line, operators comfortable, maybe prefer new system, issues identified and fixed
- **12 months**: Most lines transitioned, operators trained and confident, system stable, seeing benefits (dashboards, mobile, faster workflows), morale good because people feel like partners

### Failure Scenario (Maria's Fear)
- **Go-live**: Rushed timeline, inadequate training, system has problems
- **Early weeks**: Production drops, operators frustrated, quality suffers, management pressures "make it work"
- **Months later**: Either rolled back (wasted money) or limping along with broken system (never recovered productivity)
- **Long-term**: Key people quit, SAP trauma reinforced, organizational resistance to future changes

### Critical Success Factor
**Floor-level partnership and trust-building**, demonstrated by Michael working an actual 8-hour shift on the floor. This single action would:
- Build credibility with 180 operators
- Demonstrate genuine commitment to understanding their world
- Provide Michael with reality check on system usage under pressure
- Create foundation for partnership vs adversarial relationship

### Maria's One-Sentence Summary
"My operators are smart, capable, adaptable people - give them real training, real support, and real respect, and they'll deliver. But if you treat this like a technical project instead of a people project, it will fail."

---

## Implications for Discovery

### What This Interview Confirms
1. **Timeline misalignment is universal**: Michael's 18 months vs everyone else's 3-5 years
2. **Training investment is massive**: $9M for operators alone, not in current budget
3. **SAP trauma is pervasive**: Affects all levels (operators, supervisors, managers)
4. **Floor-level partnership is essential**: Without it, passive resistance kills adoption
5. **MES is highest risk system**: Should be last, requires most care
6. **Parallel running is necessary**: Not optional for critical systems
7. **Sunday windows are severe constraint**: Only 48 hours/year = multi-year timeline

### What This Interview Adds
1. **Ground truth on operator capabilities**: 1/3, 1/3, 1/3 breakdown with age considerations
2. **Detailed training program design**: Four-phase approach with specific durations
3. **Safety incident risk**: Close calls during SAP, could happen again
4. **Specific SAP failure details**: 3 weeks, 50% production drop, 3 people lost
5. **Floor sentiment by age group**: Younger interested, middle cautious, older worried
6. **System reliability requirements**: 99.9% uptime, <1 second load times, <1 hour recovery
7. **Communication urgency**: Rumors flying, uncertainty damaging, need clarity soon

### What This Interview Enables
1. **Training program design**: Maria provided detailed blueprint
2. **Pilot program structure**: One line, volunteers, 3 months minimum
3. **Change management approach**: Partner with floor, don't impose on floor
4. **System requirements refinement**: Mobile access, dashboards, integration needs
5. **Timeline validation**: Sunday windows alone prove multi-year timeline
6. **Budget validation**: Training costs must be 10x higher than initially thought
7. **Success criteria definition**: Maria's 6-month and 12-month milestones

### What Still Needs Discovery
1. **Support Lead perspective**: Customer-facing impact, downtime tolerance from customer angle
2. **Sales Director perspective**: Customer requirements, competitive pressure, revenue risk
3. **HR Director perspective**: Training capacity, change management resources, organizational readiness
4. **Lisa Chen (Manufacturing IT)**: PLC integration details, shop floor constraints

---

## Recommendations for Next Steps

### Immediate Actions (Within 7 Days)
1. **Michael-Maria Meeting**: Michael should meet with Maria and commit to floor shift within 30 days
2. **Training Budget Update**: Jennifer needs to update financial model with $9M training investment
3. **Communication to Floor**: Address rumors, clarify that discovery is happening, decisions not yet made
4. **SAP Acknowledgment**: Begin drafting communication that explicitly addresses SAP failure and what's different

### Short-Term Actions (Within 30 Days)
1. **Michael Floor Shift**: 8-hour shift on second shift with Maria's team
2. **Pilot Program Planning**: Define structure (which line, which operators, duration, success criteria)
3. **Training Program Design**: Work with Maria and HR to detail four-phase approach
4. **Timeline Revalidation**: Update board presentation with realistic multi-year timeline

### Medium-Term Actions (Within 90 Days)
1. **Complete Remaining Interviews**: Support Lead, Sales Director, HR Director
2. **Synthesis Session**: Integrate all 11 interviews into comprehensive problem statement
3. **Feasibility Report**: Update with ground-truth from floor-level perspective
4. **Go/No-Go Decision**: Based on complete discovery including floor reality

---

**End of Interview 8 Analysis**

**Interviews Completed**: 8 of 11 (73%)  
**Remaining Interviews**: Support Lead, Sales Director, HR Director  
**Estimated Discovery Completion**: After Interview 11 + Synthesis

---

*Transcript prepared by Discovery Facilitator*  
*Phase 0 - Discovery & Ideation*  
*Contoso Manufacturing Azure Modernization Initiative*
