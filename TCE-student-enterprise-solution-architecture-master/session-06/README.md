# Session 6: Bringing It Together and Making Decisions

## Your path through this session

Nothing new is being designed in isolation today. Your job is to connect the four views and write down why your hardest decision makes sense.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

# Part 1 — Understand

## Purpose

Over five sessions, you've made real decisions: who the stakeholders are, what the process looks like, how the software is structured, where the data lives, and what technology runs it. Today's job is to connect all four into one consistent picture, and to practice something architects do constantly and rarely get taught explicitly: writing down *why* a decision was made, so the reasoning outlives the decision itself.

## A familiar example

A team may choose a simple shared spreadsheet instead of building a new application. Six months later, someone may ask, "Why didn't we build the app?" A useful decision record preserves the original context: the deadline, team size, alternatives, benefits, and accepted limitations. Without that reasoning, an old decision can look careless even when it was sensible at the time.

## What you'll be able to do after this session

- Show how a single business need connects across all four views — business, application, data, and technology — in one consistent picture.
- Write a short, clear record of one architecture decision: what was decided, why, what else was considered, and what it costs.
- Explain why keeping the reasoning behind a decision matters as much as the decision itself.
- Spot a trade-off in your own project and defend the side you chose, honestly.

## Key ideas

**Connecting the four views**
Business, application, data, and technology aren't four separate documents — they're four angles on the same system, and they should use consistent names for the same things. If your business layer calls something "Funds Transfer" and your application layer calls the same thing something completely different, that mismatch is a real problem, not a small one — it means two people looking at your architecture from different angles can't tell they're looking at the same feature.

**Architecture Decision Record (ADR)**
A short, written record of one decision: what was decided, why, what other options were considered, and what the decision costs. An ADR survives a system being rewritten — it's a record of *why*, kept separately from *what*, so the next person doesn't have to guess or repeat the same debate from scratch.

**Trade-off**
Every real architecture decision gives something up to gain something else. There is no option that's simply "better" with no cost — if it sounds like there is, you likely haven't found the cost yet.

**Understanding check:** in your own words, why does an ADR need to include the option that *wasn't* chosen, not just the one that was?

## Campus Bank: one decision, written down properly

Across the last four sessions, Campus Bank's transfer-status feature has picked up decisions at every layer: a business requirement (customers need fast, self-serve status), a process (check request → validate → respond), an application decision (built as its own small piece, separate from the core transfer application), a data decision (status stored as a real, queryable field, updated close to real-time), and a technology decision (run on infrastructure that can add capacity automatically, monitored closely because it's customer-facing).

Here's what an Architecture Decision Record for the application-design piece of that looks like:

> **Decision:** Build "check my transfer status" as its own small application, separate from Campus Bank's core transfer system.
> **Why:** Keeps changes to this new, less-proven feature from risking the transfer system that already works reliably. Lets the team release updates to status-checking independently and more often.
> **What else we considered:** Adding it directly inside the existing transfer application — simpler to build right now, but ties its future changes to a system the bank can't afford to destabilize.
> **What it costs:** One more piece of software to deploy, monitor, and keep talking correctly to the core system. More operational work than the simpler option.

Notice what this record does: it doesn't just state the decision, it keeps the *reasoning* — including the option that was turned down, and what was given up to choose this one. A year from now, when someone asks "why isn't this just part of the main app," this record answers them without anyone needing to remember the original conversation.

**Understanding check:** if your business-layer and application-layer descriptions of the same feature used two different names, what real problem could that cause later?

## Part 1 checkpoint

Before the break, you should be able to explain why the four views need to agree with each other on naming, and why an ADR needs a real alternative, not a strawman. Stay here longer if that's still fuzzy.

---

## Ten-minute break

---

# Part 2 — Apply

## Activity: Draw the connection, write the record

1. On one page, show how your project's core feature connects across all four views — one line each for business, application, data, and technology, using consistent names for the same thing across all four.
2. Pick the single decision from your project that had the most real trade-off behind it — the one where the "obviously better"-sounding choice wasn't actually free. Write it as an ADR, in the same four-part format shown above.
3. Trade your ADR with another team. Can they understand your reasoning without asking you to explain it out loud? If not, rewrite the unclear part.

**Understanding check:** without looking at your notes, can you say your ADR's "what else we considered" out loud in one sentence? If you have to go check, the ADR probably needs to be clearer.

## What you'll produce

A one-page view connecting business, application, data, and technology for your project's core feature, and at least one written Architecture Decision Record.

## Connecting to your final project

This session's output — the connected view and the ADR — are both required parts of your final architecture document, and the connected view is what you'll actually present in Session 7, since it's the fastest way to show a stranger your whole design in one glance.

## Naming the professional tool

There's a formal visual notation called **ArchiMate**, built specifically to draw all four views — business, application, data, technology — in one consistent modelling tool. Professional architects use a free tool called **Archi** to build ArchiMate models. What you did today by hand is the same thinking; ArchiMate just gives it a standard visual language other architects recognize instantly. It's genuinely useful if you continue in this field, and it's entirely optional for this course — your connected one-pager and written ADR are what's required, however you draw them.

## Recap

The four views you've been building all semester are one system seen from four angles, not four separate projects — and they should agree with each other on names and boundaries. An Architecture Decision Record keeps a decision's reasoning alive after the decision itself is old news. Every real decision costs something; naming that cost honestly is the actual skill.

## Looking ahead to Session 7

Everything is built. Session 7 is where you present it, defend it under real questions, and learn to describe what you built the way you would in an actual interview.

---

## Where to go next

[← Session 5](../session-05/README.md) · [Course map](../COURSE_MAP.md) · [Session 7 →](../session-07/README.md)
