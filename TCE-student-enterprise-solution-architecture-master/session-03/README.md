# Session 3: Business Processes and Application Design

## Your path through this session

Bring the requirement you wrote in Session 2. You will turn it into a business process and decide how applications should support it.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

# Part 1 — Understand

## Purpose

Last session, you turned a vague complaint into a clear requirement: customers need to see their transfer status quickly, without calling support. Today we ask the next question: what actually has to happen, step by step, for that to work — and what software design would deliver it? This is the session where "the business wants X" turns into "here's the software structure that provides X."

## A familiar example

When you order food, the app does not simply "deliver food." It accepts the order, confirms payment, sends it to the restaurant, assigns a delivery partner, tracks progress, and handles failure. One customer action crosses a process and several applications. Campus Bank's transfer-status problem works the same way: first understand the steps and handoffs, then decide how software should support them.

## What you'll be able to do after this session

- Draw a simple process diagram showing the steps, decisions, and people involved in getting something done.
- Explain what an application actually is, and how several applications work together to support one business process.
- Explain the difference between building one connected application versus several smaller, independent ones — and why that choice isn't about which one is "more advanced."
- Choose and justify an application design for your own project, based on a real trade-off, not a guess.

## Key ideas

**Business process**
The actual sequence of steps, decisions, and handoffs that get something done — who does what, in what order, with what decision points along the way. A transfer isn't just "money moves" — it's "check the request is valid, check the balance, move the money, record what happened, tell the customer."

**Business capability**
Something a business can *do*, independent of which software currently does it — "Process a Transfer," "Verify a Customer's Identity," "Answer a Support Question." A capability is the *what*; a process (above) is the *how*, step by step. Naming capabilities is useful because they usually outlive any one process or application — Campus Bank could completely redesign *how* it verifies a customer's identity without changing the fact that "Verify a Customer's Identity" is still a capability it needs.

**Process diagram**
A simple picture of a business process: boxes for steps, diamonds for decisions, arrows showing the order things happen in. You don't need special software for this — pen and paper works, and so does a free tool like draw.io.

**Application**
A piece of software built to handle a specific job. A bank might have one application for managing accounts, a separate one for handling transfers, and another for authentication — each responsible for its own piece of the process.

**Monolith**
One application that contains everything — all the pieces built and deployed together as a single unit. Simpler to build and manage early on, but everything is tied together, so a change in one part can risk the whole thing.

**Microservices**
Many small, independent applications, each responsible for one capability, deployed and updated separately. More flexible as a company grows, but it costs more to run and coordinate — more moving parts, more places something can go wrong.

**Application design decision**
Choosing how to structure your software — one connected application, several independent ones, or something in between — based on real trade-offs like team size, how often things change, and how much operational complexity you can actually support. There's no universally "correct" answer; there's only the right answer for a given situation.

**Integration**
However you structure your applications, the moment you have more than one, they need to talk to each other — reliably, and in a way both sides agree on. That's called integration. It's a real cost of splitting something into separate pieces: the new "check my status" feature, if built separately, has to integrate with the core transfer system to actually get a real answer.

**Understanding check:** in your own words, what could go wrong if a company picked microservices for a brand-new, one-person project? Try answering before reading further in this session.

## Campus Bank: from process to design

Campus Bank's real transfer process, step by step, looks like this:

```
Customer requests transfer → check the request hasn't already been submitted (avoid double-charging)
  → check the account has enough balance → move the money → record what happened, with a traceable ID
  → return the result to the customer
```

Right now, this entire process runs inside **one application** — a single, connected piece of software that handles accounts, transfers, and login together. That's a monolith, and for Campus Bank's current size, it works fine: one team can understand the whole thing, and changes are simpler to test and release.

But remember last session's requirement — customers need to see transfer status quickly. If Campus Bank adds a brand-new "check my status" feature, does it belong inside that same connected application, or would it work better as its own small, independent piece? There's a real trade-off either way: adding it to the existing application is simpler right now, but ties its future changes to everything else in that application. Building it separately keeps it isolated, but now the bank has two things to run, monitor, and keep talking to each other correctly.

That's not a hypothetical question — it's the actual kind of decision an architect makes, and there's no "obviously correct" answer. The right choice depends on how big the team is, how often this piece will change, and how much operational complexity the bank is ready to take on.

**Understanding check:** who would be affected if Campus Bank chose wrong here — not just the engineering team, think back to Session 2's stakeholder list.

## Part 1 checkpoint

Before the break, you should be able to describe Campus Bank's transfer process as a sequence of steps and decisions, and explain — in plain words — the real trade-off between building the new feature inside the existing application versus as its own piece. If that's still fuzzy, that's worth more discussion now.

---

## Ten-minute break

---

# Part 2 — Apply

## Activity: Diagram the process, then decide

1. Draw a simple process diagram for Campus Bank's transfer flow, using the steps above — boxes, decision diamonds, arrows.
2. In your team, decide: should the new "check my transfer status" feature live inside the existing application, or as its own separate piece? Write three bullet points defending your choice — and be honest about what it costs, not just what it gains.
3. For your own project: draw a process diagram for the one core process your problem statement is about, and make the same monolith-vs-separate-pieces decision, with justification.

**Understanding check:** once your team has picked a design, could you defend it to someone who picked the opposite? Try actually saying it out loud to a teammate before writing it down.

## What you'll produce

A process diagram for Campus Bank's transfer flow, and an application design decision — with justification — for both Campus Bank's new feature and your own project.

## Connecting to your final project

This session produces two of your project's required artifacts: a process diagram for your core business process, and an application design decision you can defend. Every later session assumes this design exists — Session 4's data design and Session 5's technology choices both build on what you decide here.

## Naming what we drew

The diagram you just drew — boxes for steps, a diamond for the decision, arrows for order — has a formal name: **BPMN** (Business Process Model and Notation). Companies use tools like Bizagi or draw.io to build these formally, with a standard set of shapes everyone in the industry recognizes. The thinking is exactly what you just did by hand; the notation just makes it readable to someone who wasn't in the room.

## Recap

A business process is the real sequence of steps and decisions behind a business need. An application is software built to handle a piece of that process. Whether to build one connected application or several independent ones is a real trade-off, not a matter of which sounds more modern — and defending that trade-off, honestly, is the actual skill.

## Looking ahead to Session 4

Session 3 decided how the software is structured. Session 4 asks: what information does this process depend on, where does it actually live, and who is responsible for making sure it's correct?

---

## Where to go next

[← Session 2](../session-02/README.md) · [Course map](../COURSE_MAP.md) · [Session 4 →](../session-04/README.md)
