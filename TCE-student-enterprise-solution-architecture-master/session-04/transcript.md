# Session 4 Transcript — Data Architecture and Governance

## How to use this transcript

Read this with your Session 3 diagram nearby. Add data to that same flow instead of starting a separate diagram.

## Human opening

Suppose your address is stored separately in admissions, the library, transport, and the placement office. You correct it in one place, but the other three still show the old address. Nothing is technically down, yet the college no longer knows which value to trust. That is the kind of problem data architecture solves.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Here's a claim I want you to sit with for a second: a bank can rebuild its transfer application three separate times over ten years, and through all three rebuilds, what actually counts as "a transaction" barely changes. Applications get rewritten constantly. Data usually doesn't. That gap is what today is about — reasoning about information itself, separately from whatever piece of software happens to be using it this year.

## What Campus Bank's feature depends on

[SCREEN: simple list — Customer, Account, Transaction]

Go back to the transfer-status feature from the last two sessions. What real-world things does it actually depend on? A Customer, who owns accounts. An Account, with a current balance. And a Transaction record for every transfer — including a unique ID, so the same transfer can never accidentally get counted twice.

[PAUSE FOR RESPONSES]

Here's the actual question I want you to sit with, and answer in the chat: where does "status" live *right now*, today, before we build anything new? Is it a real, readable field in the Transaction record — or is it buried inside a technical log that only an engineer could make sense of?

... Right, and if it's the second one, that's a real, specific finding. It means the data we need to answer the customer's question doesn't exist yet in a usable form — even though the transfer itself works perfectly correctly behind the scenes. That's a data problem, not an application problem, and they're not the same kind of fix.

## Who owns it, and how fast does it need to update

[SCREEN: camera]

Ownership means: if two different systems ever show a different balance for the same account, which one is actually correct? Somebody has to be the source of truth — not just "everyone who happens to read it."

And then there's the batch-versus-real-time question. Does status need to update the instant it changes, or is "updated within a minute" genuinely good enough? That answer should come straight from the requirement you wrote in Session 2 — not from whichever option happens to sound more advanced on a resume.

## AI readiness, honestly

One more idea, quickly, because you'll hear this phrase constantly once you're working: "AI readiness." It does not mean owning an AI tool. It means having data that's clean, well-owned, and governed *before* anyone adds a model on top of it. A company with messy, contradictory data isn't ready for AI just because it bought one — it needs to fix its data first. Being able to say that plainly, instead of nodding along with a sales pitch, is a real, valuable skill.

## Activity

[SCREEN: activity instructions]

List the data entities behind Campus Bank's transfer-status feature, with two or three attributes each. Decide who owns each one. Decide batch or real-time, and defend it with cost and correctness — not vibes. Then do the same three steps for your own project.

## Closing

[SCREEN: camera]

You now know what the software does and what information it depends on. Next week: where does all of this actually run, and how does a company keep it secure and alive every single day without watching it by hand? See you then.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 3](../session-03/README.md) · [Course map](../COURSE_MAP.md) · [Session 5 →](../session-05/README.md)
