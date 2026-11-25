# Session 1 Transcript — Enterprise System Design: How a Company Keeps Its Business Running

## How to use this transcript

Read this after the main lesson if you want to hear the explanation again in a more conversational voice. Pause at the questions and answer them before reading on.

## Human opening

Before we start, think about your college login. One username may open email, the learning portal, exam registration, library services, and Wi-Fi. It feels like one simple login, but behind it are identity records, applications, networks, security rules, support teams, and data that must agree. Today we are going to reveal that same hidden system at company scale.

**Scheduled Zoom slot:** Friday, August 21, 2026, starting 9:30 PM CT (Saturday, August 22, starting 8:00 AM IST). Planned slot: 90 minutes.
**Format:** Live Zoom delivery script, written to be spoken naturally — not read like a textbook.

**This is a guide, not a countdown.** The times mentioned below are typical ranges, not deadlines. This is a student-paced, understanding-driven class — if a discussion is genuinely helping students understand, let it run. If Part 2 doesn't finish in this slot, that's a normal outcome: pick it up at the start of Session 2, the same way a learning module can reasonably take more than one live meeting. Do not cut a student's question short to protect a timestamp.

Bracketed cues like `[SCREEN: ...]` mark when to switch what's visible. Bracketed `[PAUSE: ...]` marks a structured interaction point — actually stop talking, watch the chat or unmute someone, and let it run as long as it's useful, not just the minimum listed. Each interaction point includes the exact question to ask, likely answers so you're not caught flat-footed, a natural response, and a transition line into the next topic.

## The shape of the class

| | Covers | Typical range |
|---|---|---|
| **Part 1** | Why this course exists, one new employee's laptop, what BAU means | Often 40–55 min |
| **Ten-minute break** | A real stopping point | ~10 min |
| **Part 2** | Zooming out to a whole company, three failure stories, a first look at the four views | Often 35–55 min |

If you're well past the "typical range" for Part 1 and the discussion is still valuable, that's fine — just be aware Part 2 may need to become next class's opening instead of squeezing into what's left of tonight.

---

# Part 1 — Understand, through one story

[SCREEN: camera, full frame]

Hi, everyone. Welcome to Enterprise System Design. I know some of you are joining at eight in the morning, so — thank you for being here, and thank you for having coffee, or tea, or whatever gets you through an 8 AM Saturday class.

Before I say anything else, I want to tell you what this course is *not*. It's not a course about memorizing framework names. It's not a course where I hand you a diagram with forty boxes on it and ask you to reproduce it on an exam. If that's what you were expecting, good news — that's not what's happening tonight, and it's not what's happening for the rest of the semester either.

Here's the one question I want stuck in your head by the time we're done today:

**What technology does a large company need before even one employee can perform their job?**

Hold onto that. We're going to answer it slowly, with a story, and by the time we're done, I think you'll be surprised by how big the answer actually is.

### Interaction 1 — icebreaker

**Ask:** "Before we start the story — quick question in the chat. What technology did you use just to get into this Zoom class tonight? Not the fancy stuff — I mean everything. Think about it for a second."

[PAUSE: let it run 2–3 minutes, longer if people keep adding to it]

**Likely answers:** "My laptop." "Wi-Fi." "Zoom app." "My college email to get the link." "My phone as a hotspot." A few students usually go further on their own — "my ID to log into the student portal that had the link."

**Your response:** "Good — and notice, most of you stopped at 'laptop' or 'Zoom.' Nobody said 'and someone had to create my student account, and someone had to make sure Zoom was allowed on the college network, and someone had to send that link to the right email address.' That's not a criticism — it's actually the whole point of tonight. All of that happened, and none of us noticed it happening. That's what we're going to go looking for."

**Transition:** "But before the story — let me tell you why this course exists at all, because I think it's a fair question."

## Why this course is in your curriculum

You've spent time learning to write programs, and you're good at it — that's a real, separate skill, not a lesser one. A program you write for an assignment has to be correct. A company's technology has to be correct *and* available to thousands of people at once *and* secure *and* affordable *and* still working the same way five years from now, after several different teams have touched it. Nobody teaches you that second part by writing more code — you learn it by looking at how a real company actually operates.

Here's what a lone working program usually doesn't handle once it enters a real company: it can't support the number of users a real company has. It's too slow once real traffic hits it. It goes down during a failure nobody designed for. It leaks something it shouldn't. It doesn't talk to systems the company already has. Nobody can tell what it's doing once it's running — there's no way to monitor it. It can't be safely updated without breaking something. It quietly creates a second copy of data that disagrees with the first. It costs more than the value it creates. It breaks a rule nobody thought to check. When it fails at 2 AM, the support team has no idea what to do. It solves a technical puzzle, but not the actual business problem.

Programming courses teach you to build the pieces. **This course teaches you how those pieces fit into a company that already exists, already has rules, and already can't afford to stop running.** That gap — that's this whole course.

[SCREEN: simple slide — the arrow: Understand the business → requirements → existing environment → design → trade-offs → govern & operate → improve]

Quickly, before the story — here's the shape of the whole semester. We're going to follow one continuing example, a fictional bank called Campus Bank, through this path: understand the business, figure out what's needed, look at what already exists, design a solution, weigh the trade-offs, keep it running safely, and improve it over time.

Today, we only do the first piece of that — understanding why a business needs this kind of thinking at all. No code today. No complicated diagrams today. Just one story.

## The story

[SCREEN: back to camera, or a blank whiteboard]

Let's say a large company — a bank, an airline, a hospital, doesn't matter yet — just hired someone. Let's call her Priya. First day. Before she can do anything at all on a computer, a whole chain of things has to happen — and I want you to guess it with me before I just tell you.

### Interaction 2 — predict the steps

**Ask:** "Here's the question. Priya got the job offer, she accepted, and Monday is her first day. Before she can open her laptop and actually start working — what has to happen first? Just call out anything you think of, in the chat or out loud. Don't worry about the order."

[PAUSE: let it run 3–5 minutes — this is worth real time, don't rush it]

**Likely answers:** "She needs a laptop." "Someone has to give her a login." "HR has to add her to the system." "IT has to set up her email." Fewer students usually mention: background checks, who actually *pays* for the laptop, or what happens to her access when she eventually leaves.

**Your response:** "That's a strong list already — laptop, login, email, HR. Here's what I want you to notice: you got maybe four or five things. The real number is closer to twelve, and every one of them involves a different team, not just IT. Let's walk through it properly, in order, and count together."

**Transition:** "Here's the full chain."

[SCREEN: the twelve steps, or just a simple list slide — build it one line at a time if you're doing this live on a blank slide]

One — HR creates her employee record. The company now officially knows she exists as an employee, not just a name on an offer letter.

Two — her manager requests a laptop for her.

Three — procurement buys or assigns one. Someone owns that budget — this is the finance side of the story, and it's real money, tracked against a real budget line.

Four — IT records that laptop as a company asset. It gets tagged, tracked, owned — the company tracks laptops the way it tracks money.

Five — the laptop gets set up: operating system, approved software.

Six — security gets applied. Encryption, antivirus, rules about what she can and can't install. A separate security team, usually, from the team that set up the laptop.

Seven — she gets a digital identity. A username. A company email. This is often its own team too — identity and access management, sometimes called IAM — and it's a bigger deal than it sounds, because this identity is what every other system will trust to know it's really her.

Eight — she's given access to the specific apps her job needs. Not everything the company owns — just her slice of it. Someone in her department has to actually request this, app by app.

Nine — the network has to actually let her laptop connect to the right things — office Wi-Fi, VPN if she works remotely sometimes, and *not* connect to things she has no reason to reach.

Ten — that laptop and those apps get watched over. If something breaks, a support or help-desk team is responsible — a completely different team from the one that built any of this.

Eleven — software gets patched over time, usually without her noticing at all.

Twelve — if she changes roles next year, her access changes with her.

And thirteen — if she ever leaves, her access gets shut off and the laptop gets collected. And there's often a vendor involved too, somewhere in this chain — the company that made the laptop, the company that hosts the email service — external businesses the company depends on but doesn't own.

### Interaction 3 — naming the teams

**Ask:** "Now — quick show of hands, or type it in chat. Besides 'IT,' how many *different* teams did you just hear me name in that list?"

[PAUSE: let it run 2–4 minutes]

**Likely answers:** Students usually catch HR, security, and support fairly fast. Fewer immediately name finance/procurement, identity management, networking, or vendor management as *separate* teams — they tend to lump those all into "IT."

**Your response:** "Let's count them out loud: HR. The manager. Procurement, which is really finance. IT asset tracking. Security. Identity management. The team that grants app access — usually inside whatever department she's joining. Networking. Support. And vendor management, for the outside companies involved. That's nine or ten different groups of people, for one employee's laptop. None of them can skip their part, and none of them can do their part without trusting that the others already did theirs."

**Transition:** "Read that list again in your head. Reliably. Correctly. Mostly invisible to Priya herself."

Nobody stood at a whiteboard and wrote "let's do architecture" to make this work. But everything on that list *is* architecture — decisions made ahead of time, so this works the same way for the next new hire, and the one after that.

And here's why it has to be decided ahead of time, not figured out fresh every time someone new joins: imagine if HR, procurement, IT, and security each had their own private process, with no agreement between them. One new hire might get a laptop before her background check clears. Another might wait two extra weeks because nobody knew whose job it was to request her app access. A third might leave the company and keep working access for a month because nobody's process included "tell security when someone's gone." None of those are hypothetical — they're the actual, ordinary failures that happen at real companies when this coordination isn't designed on purpose.

[SCREEN: camera]

If your class still has questions or examples to share here, let that conversation run — this is exactly the kind of moment worth real time, not something to hurry past.

## What "Business as Usual" means

All twelve of those steps, working together, every day, for every employee — that has a name: **Business as Usual**, or BAU.

**Business as Usual means the organization can keep doing its normal daily work, reliably, every day.**

BAU is never automatic. It's the result of a lot of systems and a lot of teams, working together, continuously — not a one-time event like Priya's first day, but something that has to keep holding true every day after that too.

## Part 1 checkpoint

[SCREEN: camera]

Here's the idea I want you to leave Part 1 with:

**A laptop is not useful merely because the company purchased it. It becomes useful only when people, processes, applications, data, infrastructure, security, and support work together.**

That's Part 1. If your room needs more time here, take it — Part 2 builds directly on this, so it's worth genuinely reaching this understanding before moving on.

---

## Ten-minute break

Actually take it. Stretch, get water, let people step away from the screen. Don't rush back in at nine minutes because you're "ahead of schedule" — there is no schedule to be ahead of.

---

# Part 2 — Apply, by zooming out

[SCREEN: camera]

Welcome back. Quick recap before we continue: before the break, we followed one new employee's laptop and found nine or ten different teams quietly depending on each other to make it work. We landed on one idea — a laptop alone is never enough; it takes people, process, data, infrastructure, security, and support, all working together. That's Business as Usual for one employee. Now let's see what it looks like for an entire company.

## From one laptop to a whole company

[SCREEN: a slide or list — thousands of everything]

Now stop imagining one employee. Imagine fifty thousand of them.

That means, at any given moment: thousands of laptops and phones, being tracked, secured, repaired, retired. Servers and storage running actual company software. Networks connecting offices and data centers. Hundreds of business applications. Databases full of customer and employee data. Cloud services rented from providers like AWS or Azure, sitting right next to systems the company still runs itself. A system tracking who has access to what. Cybersecurity tools watching, all day, every day. Software licenses to track and renew. Vendor contracts. Data centers. A help desk fielding thousands of "my laptop won't turn on" tickets a day. Monitoring systems that alert someone the second something's wrong. Backups. A disaster recovery plan for when things go very wrong. Legal and compliance requirements. A technology budget somebody has to defend. And — old systems, sometimes decades old, running right alongside brand-new ones.

Here's the part I really want to land: **none of this works if it's separate.** The laptop's useless without the network. The network's useless without security. Security's useless if nobody's watching for alerts. Monitoring's useless if there's no one on call to respond. A backup is useless if nobody ever actually tested restoring it.

### Interaction 4 — the stakes of BAU

**Ask:** "Here's a real question, and I want an honest guess, not a textbook answer. If employees at a company suddenly cannot access *one* important system — just one — what actually happens to the business that day?"

[PAUSE: let it run 3–4 minutes]

**Likely answers:** "They can't do their job." "Customers get angry." "The company loses money." Some students get more specific — "support calls pile up," "other systems that depend on it might also break," "people just sit around waiting."

**Your response:** "All true, and here's the part that surprises people: it doesn't matter if the *rest* of the company's software is perfect. One missing piece is enough to stop real work, for real people, that day. That's the thing BAU protects against — and it's also exactly what breaks in the three stories I'm about to tell you."

**Transition:** "Let's look at three real-feeling scenes where exactly that happened."

## Why companies fail without this — three quick scenes

[SCREEN: camera, or three short slides, one per scenario]

I want to be honest with you, not dramatic — this isn't a scare tactic, it's just what actually happens when this kind of thinking is missing. Three quick scenes.

**One.** A customer transfers money from Account A to Account B. It leaves A. It never arrives in B. Follow who that touches — the customer, angry and worried. Support, who has to trace it across systems. Finance, trying to find where the money actually sits. Audit, who has to explain how it happened. And the bank's reputation, the moment that customer tells a friend. One missing safeguard, felt by five different groups.

**Two.** An airline's check-in system goes down for two hours. Sounds like "one system had a problem." Follow the chain — passengers can't check in, gate staff can't board on time, baggage falls behind, call centers get flooded, flights leave late, which then delays the *next* flights those same aircraft were supposed to fly. One failure, rippling through an entire day.

**Three.** A new employee gets her laptop on day one — but can't log into email, can't reach the one application her job actually needs. She has the hardware. She doesn't have access. Owning the laptop isn't the same as being able to do the job. Nothing crashed. Nothing made the news. The company's just quietly paying someone who can't do anything yet — the exact same idea as our Part 1 checkpoint, just at company scale.

Notice something about all three of these: none of them are stories about broken code. The transfer logic worked. The check-in system, when it was up, worked fine. Priya's laptop itself worked perfectly. What failed, every single time, was the coordination between pieces that each worked correctly on their own.

### Interaction 5 — is the laptop enough

**Ask:** "Back to scenario three, and I want you to actually answer this one: is handing someone a laptop enough to make them productive on day one? Why or why not?"

[PAUSE: let it run 3–5 minutes]

**Likely answers:** "No — they still need accounts and access." "No, because the apps aren't set up yet." A few will connect it back to the twelve-step list from earlier: "it's basically step eight that's missing — access to the apps her job needs." Occasionally someone says "yes, if IT does their job fast enough" — which is a fair answer, and worth acknowledging: it *can* be enough, if every one of those nine or ten teams did their part correctly and on time. That's the whole point.

**Your response:** "Exactly right, both directions. The laptop is necessary but not sufficient — and whether it's *actually* enough depends entirely on whether all those other teams we counted earlier did their job, in the right order, before day one. None of these three stories are exotic. They're ordinary — and they happen exactly when pieces that needed to work together, didn't."

**Transition:** "So if none of this is automatic, what actually organizes all of it? That's the last real idea for tonight."

## A first look at enterprise architecture

[SCREEN: the four-box diagram — Business, Application, Data, Technology]

Now that you've actually seen the problem — a company needing dozens of moving parts to work together, reliably, every day — here's the definition that addresses it, and I promise it's simpler than it sounds:

**Enterprise architecture is the practice of understanding how a company's business processes, applications, data, and technology fit together — so the company can make coordinated decisions instead of every team building something disconnected.**

Four simple questions, and we're going to use these four, over and over, for the rest of the course. **Business** — what work needs to get done? Think of Priya's onboarding itself: "hire and equip a new employee" is a business need, full stop, before any software gets involved. **Application** — what software supports that work? That's the specific HR system, the IT asset tracker, the identity system — each one a piece of software built to handle one part of the job. **Data** — what information does the company use? Priya's employee record, her access permissions, the laptop's asset tag — information that has to stay correct even as the applications around it change. **Technology** — what does it all run on? The servers, the network, the cloud services underneath every one of those applications.

### Interaction 6 — placing customer information

**Ask:** "Quick test, and there's a slightly tricky answer here. Think about a customer's name, account balance, and transaction history at a bank. Which of the four views — business, application, data, or technology — would that information belong to?"

[PAUSE: let it run 3–5 minutes]

**Likely answers:** Most students say "data" immediately, and that's correct. A good number also reasonably say "application," because that's *where* they'd see it, on a screen. Occasionally someone says "business," reasoning that customer info is part of the business relationship.

**Your response:** "Data is the right main answer — that's exactly the distinction this course keeps coming back to. The *application* is the screen that shows it to you. The *data* is the actual information itself, and it usually outlives any one application — a bank can rebuild its entire mobile app three times over ten years, and 'what counts as a customer's balance' barely changes underneath it. That's why we treat data as its own view, not just part of whatever app happens to display it."

**Transition:** "One more idea, and then we're close to done for tonight."

And one more sentence, because you'll hear this word a lot: **Governance means having agreed rules and decision processes, so technology is purchased, built, secured, operated, and retired responsibly** — instead of every team deciding on its own.

You'll hear names like TOGAF and ArchiMate later in this course. Tonight, forget the names entirely. They're just organized ways of asking those same four questions, again, on bigger systems. You already asked those four questions tonight — about Priya's laptop — without needing a framework to do it.

## Closing

[SCREEN: camera]

Here's what I want you to leave with tonight:

**Enterprise system design is not about drawing complicated boxes. It's about understanding how a business actually works, and designing technology that lets that business run securely, reliably, and efficiently.**

You took one laptop request tonight and found a small enterprise system hiding inside it — people, process, data, hardware, and rules, all depending on each other. That's the skill. Noticing the system behind something that looks simple.

Next time, in Session 2, we take a real business problem for Campus Bank, figure out who actually cares about solving it, and turn that into clear, written requirements. Everything from tonight becomes the toolkit you use to do that.

[SCREEN: activity worksheet]

Now — your homework, and I want to be clear this is homework, not something we're doing live tonight. Open the activity file, "What Must Happen Before a New Employee Can Start Work?" Pick any large company you can picture — a bank, an airline, a hospital, your own college, anywhere — and walk through it yourself, the same way we just walked through Priya's story together. Bring what you find to Session 2.

Thanks for being here at eight in the morning. See you next Saturday.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Course home](../README.md) · [Course map](../COURSE_MAP.md) · [Session 2 →](../session-02/README.md)
