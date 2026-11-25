# Session 4: Data Architecture and Governance

## Your path through this session

Bring your process and application view from Session 3. Now decide what data the process depends on, who owns it, and how people can trust it.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

# Part 1 — Understand

## Purpose

Applications get rewritten. Data usually doesn't — a bank might rebuild its transfer application three times over ten years, and through all three rebuilds, "what counts as a transaction" barely changes. Today's session is about reasoning about information itself, separately from whatever software happens to be using it right now.

## A familiar example

Suppose your address is stored separately in admissions, the library, transport, and the placement office. You correct it in one place, but the other three still show the old address. Nothing is technically "down," yet the organization no longer knows which value to trust. Data architecture is how we decide where important data belongs, who owns it, how it moves, and which copy is authoritative.

## What you'll be able to do after this session

- Identify the real-world "things" a system needs to track, and describe what information matters about each one.
- Explain who owns a piece of data — meaning, who is responsible for it being correct — not just who can see it.
- Explain the difference between processing data in scheduled batches versus handling it the moment it happens.
- Explain, honestly, what it means for a system's data to be trustworthy enough to build new features — including AI features — on top of it.

## Key ideas

**Data entity**
One real-world "thing" a system needs to track — a Customer, an Account, a Transaction. Each entity has attributes: a Customer has a name and an email; a Transaction has an amount and a timestamp.

**Data ownership**
Which team or system is the *source of truth* for a piece of data — not just who happens to read it. If both the transfer application and the reporting dashboard show an account balance, only one of them should be trusted as correct if they ever disagree. That's ownership.

**Data governance**
The rules for who can access data, who can change it, and how you could prove — after the fact — that those rules were followed. Governance is what keeps "everyone can edit anything" from turning into "nobody can trust anything."

**Batch processing**
Handling data in scheduled chunks — once an hour, once a night — instead of the instant it happens. Good enough, and often cheaper, when a small delay doesn't hurt anyone. A nightly report of yesterday's transactions is a reasonable use of batch processing.

**Real-time processing**
Handling each piece of data the moment it happens. Needed when a delay actually causes harm — like fraud detection, where minutes matter.

**AI readiness**
Having clean, well-owned, well-governed data *before* adding any kind of AI or automated model — not the model itself. A company with messy, contradictory data isn't ready for AI just because it bought an AI tool; it needs to fix its data first. Claiming "AI readiness" without this is a common and honest mistake to be able to spot.

**Understanding check:** explain, in your own words, why "AI readiness" is about data, not about owning an AI tool. What would you say to a manager who disagreed?

## Campus Bank: what the transfer feature depends on

Campus Bank's transfer process from Session 3 depends on real information: the Customer who owns each account, the Account itself and its current balance, and the Transaction record of every transfer, including a unique ID so the same transfer can never accidentally be processed twice.

For the new "check my transfer status" feature, ask: where does "status" actually live right now? Is it a real field in the Transaction record, or is it something only visible buried inside a technical log that a customer — or even a support agent — can't easily read? If it's the second one, that's a real, specific finding: the data needed to answer the customer's question doesn't currently exist in a usable form, even though the transfer itself works correctly.

This also raises the batch-versus-real-time question directly: does a customer need to see their transfer status the instant it changes, or is "updated within a minute" good enough? That answer changes what you'd actually build — and it should come from the requirement you wrote in Session 2, not from whichever option sounds more advanced.

**Understanding check:** which team would notice first if the "status" field were wrong — and does that tell you who should own it?

## Part 1 checkpoint

Before the break, you should be able to name Campus Bank's key data entities and explain, in plain words, why "who owns this data" is a different question from "who can see this data." If that's still fuzzy, stay here a bit longer.

---

## Ten-minute break

---

# Part 2 — Apply

## Activity: Trace the data behind your process

1. List the data entities involved in Campus Bank's transfer-status feature (at minimum: Customer, Account, Transaction). For each, list two or three attributes that matter.
2. Decide: who owns each entity — meaning, which part of the system is the source of truth if two places ever disagree?
3. Decide: should transfer-status updates be batch or real-time? Justify it using cost and correctness, not "real-time sounds better."
4. Do the same three steps for your own project's core process.

**Understanding check:** for each entity on your list, can you say who owns it in one sentence, without saying "the system" or "the database"? If you can't, that's worth resolving now.

## What you'll produce

A short data entity list with attributes and ownership, and a batch-versus-real-time decision with justification, for both Campus Bank and your own project.

## Connecting to your final project

The data design you produce today becomes a required part of your final architecture document. It also constrains Session 5 — the technology choices you make next session have to actually support the data decisions (batch or real-time, how much data, how sensitive it is) you make today.

## Seeing governance as a real process (optional, time permitting)

If there's time left in class, your instructor may show one real example of a company writing down a data decision as a permanent, checkable record instead of just talking about it once and forgetting it. That's what "governance" looks like in practice — not a rulebook nobody reads, but a habit of writing decisions down.

## SQL vs. NoSQL, briefly (optional)

You'll hear these two names a lot once you start working with real systems, so here's the short version.

**SQL** databases commonly organize strongly related data into tables — rows and columns, with clear relationships between them, and strong guarantees that a change either fully happens or doesn't happen at all. **NoSQL** is a broad category of databases built for other kinds of data structures and access patterns — not one single alternative, but a whole family of different approaches.

Neither one is automatically better. The right choice depends on how related the data is, how it's typically accessed, how strict the consistency needs to be, how much scale is involved, and what the team can realistically operate.

**For Campus Bank:** accounts, balances, and financial transactions usually benefit from relational structure and strong transactional consistency — the same reasoning behind the "SQL, not NoSQL" answer you may have already guessed earlier in the course. But that doesn't mean every part of a bank uses the same kind of database. Things like system logs, temporary login sessions, or high-volume activity events sometimes fit a different kind of database better, when their access patterns actually justify it. A real bank's technology is rarely just one database type used everywhere — different data gets different treatment, on purpose.

**Optional design question, if you want to think it through:** for Campus Bank's transfer-status feature specifically, which part of it — if any — might reasonably use a different kind of database than the core account/transaction data? There isn't a single required answer; the point is practicing the same "what does this specific data actually need" reasoning, not memorizing a rule.

## Recap

Data outlives the applications built on top of it, so it deserves its own design thinking, separate from any one piece of software. Every entity needs a clear owner. Batch versus real-time is a real trade-off between cost and correctness. And being "AI-ready" means having trustworthy data first — not owning an AI tool.

## Looking ahead to Session 5

You now know what the software does (Session 3) and what information it depends on (today). Session 5 asks: where does all of this actually run, and how does the company keep it secure and available, every day, without someone watching it constantly by hand?

---

## Where to go next

[← Session 3](../session-03/README.md) · [Course map](../COURSE_MAP.md) · [Session 5 →](../session-05/README.md)
