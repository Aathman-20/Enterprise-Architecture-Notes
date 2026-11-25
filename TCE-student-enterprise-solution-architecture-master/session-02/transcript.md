# Session 2 Transcript — Business Problems, Stakeholders, and Requirements

## How to use this transcript

Use this as a replay of the class conversation. Keep your own project beside you and translate each Campus Bank example into your domain.

## Human opening

Before we use any architecture terms, imagine a student says, “The college portal is bad.” That is a complaint, but it is not yet a usable problem statement. Does it fail during registration? Are marks late? Can students not tell whether a fee payment succeeded? Each answer affects different people and creates different requirements.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Welcome back. Last week we ended with one idea I want you to be able to repeat in your sleep: enterprise system design is about noticing the system behind something that looks simple. Today, we use that instinct on something concrete — a real Campus Bank problem — and turn it into something an engineer could actually start building from.

[PAUSE FOR RESPONSES]

Quick check before we start — in the chat, tell me one thing you noticed *behind the scenes* this week, now that you're looking for it. Doesn't have to be dramatic. A login screen, a delivery tracking page, anything.

[SCREEN: Campus Bank problem statement]

Here's the problem we're going to live with for the rest of the semester:

Campus Bank customers wait up to three days to find out if a transfer actually went through. Support staff spend hours a week manually digging through logs to answer "where's my money" calls. Nobody at the bank even knows how many customers this affects.

Notice what I did *not* say. I didn't say "we need a faster database." I didn't say "let's add a status API." Not yet. The moment you jump to a technology, you've skipped past actually understanding who's affected and why it matters to them. That's the mistake I want you to avoid for the rest of your career, not just this semester.

## Stakeholders

[SCREEN: camera or a simple table]

So who actually cares about this problem? Not just "the customer" — that's the easy, lazy answer. Let's go slower.

The retail customer, obviously — they want to know their money's status without calling anyone. Support staff — they're the ones stuck manually digging through logs every single day this problem exists; this is costing *them* real time, not just annoying the customer. The compliance officer — they need every transfer traceable, provably, after the fact. The engineering team — whatever we build here can't destabilize the transfer system that already works correctly; that's a real constraint, not a suggestion. And the CFO — whatever we build, it can't require some huge new infrastructure investment just to show a status message.

Here's the skill I want you to practice: for each of those, what do they actually *need* — not what would a lazy first guess say they need. A branch manager might ask you for "a bigger, more detailed report." Nine times out of ten what they actually need is a report that catches errors *before* a customer notices them — the "bigger" part was never really the point. You have to ask enough questions to find that out; you can't just take the first sentence someone says to you and start building.

## Turning this into a requirement

[SCREEN: camera]

Now — a requirement. Here's a bad one: "the app should be fast." Fast for whom, doing what, how fast? That sentence can't be built from — two different engineers would build two different things from it.

Here's a good one: "a customer must be able to see their transfer status within five seconds of opening the app." Now two different people, working independently, would build roughly the same thing. That specificity is the entire point of a requirement.

[PAUSE FOR RESPONSES]

Try this with me right now — someone put in the chat a requirement for the compliance officer's need, "every transfer traceable." Make it specific... okay, I'm seeing some good attempts. Something like "every transfer must have a permanent, timestamped record showing what happened and when" — that's specific enough to build from. "Transfers should be traceable" on its own isn't.

## Activity

[SCREEN: activity instructions]

For the rest of this session and your homework: list every Campus Bank stakeholder you can think of beyond the five I named, write what each one actually needs, and turn the single most important one into a clear requirement. Then do the exact same three steps for your own team's project — a one-paragraph problem statement, no technology names allowed in it, and at least four real stakeholders.

This becomes the foundation for literally everything else this semester. Get this part honest and specific now, and every later session gets easier. Rush it, and you'll spend the rest of the term designing the wrong thing very carefully.

## Closing

[SCREEN: camera]

Next week, we take this requirement and ask: what does the actual process look like, step by step, and what software structure would deliver it? See you then.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 1](../session-01/README.md) · [Course map](../COURSE_MAP.md) · [Session 3 →](../session-03/README.md)
