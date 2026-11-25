# Session 5: Technology, Cloud, Security, and Operations

## Your path through this session

Your application and data design now need a safe place to run. This session adds infrastructure, cloud choices, security, monitoring, and recovery.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

# Part 1 — Understand

## Purpose

Everything so far has been decisions on paper — what the problem is, how the process works, what the data looks like. Today, those decisions meet reality: actual servers, actual security rules, actual bills, and actual failures at inconvenient times. This is where architecture stops being diagrams and starts being something a company has to operate every single day.

## A familiar example

An exam-registration portal may work perfectly with ten test users and still fail when two thousand students open it at 9:00 AM. That is the gap between software that works and a service an organization can depend on. Technology architecture asks where it runs, how it handles a sudden load, how failures are detected, how data is protected, and what the reliability costs.

## What you'll be able to do after this session

- Explain the difference between owning your own hardware and renting capacity from a cloud provider, and when each makes sense.
- Read a simple deployment diagram and explain, in plain words, what happens from "code is written" to "a customer's request gets handled."
- Explain what it means to design security into a system from the start, instead of adding it as an afterthought.
- Explain why "we tested it and it should work" is a different, weaker claim than "we've actually run it in production."
- Reason about what drives a system's running cost.

## Key ideas

**On-premise vs. cloud**
On-premise means the company owns and runs its own physical servers. Cloud means renting computing capacity from a provider like AWS or Azure, paying for what you use, and letting the provider handle the physical hardware. Neither is automatically better — on-premise can be cheaper at very large, steady scale; cloud is usually faster to start with and easier to scale up or down.

**Deployment**
The actual path code takes from a developer's laptop to something a real customer can use — built, tested, packaged, and placed onto servers that can handle real traffic.

**Security by design**
Making security part of the architecture from the beginning — deciding who can access what, and limiting each part of the system to only what it actually needs — instead of bolting security on after something is already built.

**Monitoring vs. observability**
Monitoring tells you *whether* something is working ("is the server up?"). Observability goes further — it lets you understand *why* something is behaving a certain way when it isn't obviously broken. A company needs both: monitoring catches the obvious failures, observability helps you actually fix the confusing ones.

**Validated vs. deployed**
Passing every automated test and check is real, valuable evidence that something is likely to work. It is not the same claim as "this has actually run successfully with real traffic." A responsible architect says out loud which of the two is true — that honesty is itself part of the job, and mixing them up is one of the most common ways teams get surprised in production.

**Cost-aware design**
Understanding what actually drives a system's bill — how much computing time it uses, how much data it stores, how much data it moves — well enough to predict roughly what a design change will cost before you build it, not after the invoice arrives.

**Understanding check:** in your own words, why is "we tested it and it passed" a weaker claim than "we've run it in production"? Can you think of a time something worked in testing but not in real use?

## Campus Bank: designed, tested, never proven live

Campus Bank has a complete, carefully built deployment design: how the application gets packaged, how it would run on managed infrastructure that can automatically add more capacity under load, and a monitoring setup that would alert someone the moment something looks wrong. Every part of it has been checked and validated by automated tools.

Here's the honest part: **none of it has ever been run against real, live traffic.** It's a real, well-designed plan that has only ever been tested, never proven under the pressure of real customers on a real day. This is a genuinely common situation in the industry, and it's worth sitting with rather than glossing over — a team can do everything right on paper and still not know, for certain, how the system behaves at 9 AM on a Monday until it actually happens.

This matters directly for the "check my transfer status" feature from Sessions 3 and 4: if it needs to be fast and always available, the technology decisions here — how much capacity is reserved for it, how it recovers if a server fails, who gets alerted if it slows down — are what actually deliver on that promise, or fail to.

**Understanding check:** what would you tell a customer if they asked "how do you know this won't fail on me"? Is "we tested it thoroughly" a complete answer?

## Part 1 checkpoint

Before the break, you should be able to explain, in plain words, why "validated" and "deployed" are different claims, and name one real reason a company might choose on-premise over cloud. Stay here longer if that's still fuzzy.

---

## Ten-minute break

---

# Part 2 — Apply

## Activity: Design for a failure

1. For Campus Bank's transfer-status feature: what technology setup would you choose — on-premise, cloud, or a mix — and why, given that a bank needs both reliability and a defensible cost?
2. Name one specific way this feature could fail (a server goes down, traffic spikes suddenly, a security key leaks) and describe, in a few sentences, what the system should do when that happens.
3. List two or three things that would drive this feature's running cost, and roughly how you'd expect each one to scale as more customers use it.
4. Repeat all three steps for your own project.

**Understanding check:** for the failure you named, would your team actually notice it happening, or only find out when a customer complains? That difference is what "monitoring" is for.

## What you'll produce

A short technology/deployment decision (on-premise, cloud, or hybrid, with justification), one failure scenario and how the system responds to it, and a short cost-driver note — for Campus Bank and for your own project.

## Connecting to your final project

This is the technology architecture section of your final project, and it has to be consistent with what you decided in Sessions 3 and 4 — a real-time feature needs different technology choices than a batch one, and a security-sensitive one needs different choices than a low-risk one.

## Naming the tools

The decisions you just made — cloud or on-premise, how the system responds to failure — get implemented in the real world using specific tools: **Docker** packages an application so it runs the same way everywhere. **Kubernetes** keeps many copies of an application running reliably, restarting them if they fail. **Terraform** lets a team define their infrastructure in code instead of clicking through a console by hand. **AWS** and **Azure** are two of the major cloud platforms that provide the actual servers underneath all of it. You don't need to operate any of these yet — you need to recognize what problem each one solves when you hear its name.

## Recap

Technology decisions turn everything from earlier sessions into something a company actually has to run, secure, and pay for. On-premise versus cloud is a real trade-off, not a "cloud is always better" default. Security should be designed in from the start. And "we validated it" is a real but limited claim — it's not the same as "we've proven it works live."

## Looking ahead to Session 6

You now have decisions across business, application, data, and technology. Session 6 connects all four into one consistent picture, and teaches you to write down *why* you made a decision — so the reasoning survives even after the system itself changes.

---

## Where to go next

[← Session 4](../session-04/README.md) · [Course map](../COURSE_MAP.md) · [Session 6 →](../session-06/README.md)
