# Session 6 Transcript — Bringing It Together and Making Decisions

## How to use this transcript

Use this to rehearse your architecture decision aloud. If the reason or trade-off sounds unclear when spoken, rewrite the ADR.

## Human opening

Imagine a team chose a shared spreadsheet instead of building a new application. Six months later someone asks, “Why didn't we build the app?” A useful decision record preserves the deadline, team size, alternatives, benefits, and limitations. Without the reasoning, an old decision can look careless even when it was sensible.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Over five sessions, you've made real decisions — who's affected, what the process looks like, how the software's structured, where the data lives, what it all runs on. Today's job is to connect all four into one picture, and to practice something architects do constantly and almost never get taught explicitly: writing down *why* a decision was made, so the reasoning outlives the decision itself.

## One system, four angles

[SCREEN: camera]

Business, application, data, technology — these aren't four separate projects. They're four angles on the exact same system. And here's a subtle but real problem: if your business layer calls something "Funds Transfer" and your application layer calls that same thing something completely different, that's not a small inconsistency. It means two people looking at your architecture from two different angles can't even tell they're looking at the same feature. Consistency of naming across all four views is part of what makes the whole thing actually usable by someone other than you.

## Writing an ADR

[SCREEN: the sample ADR]

Let's write one together, live, for a decision you already made — Session 3's choice about whether the status feature lives inside the existing application or as its own piece.

Decision: build it as its own small application, separate from the core transfer system.
Why: keeps changes to this new, less-proven feature from risking the transfer system that already works reliably.
What else we considered: building it inside the existing application — simpler right now, but ties its future to a system the bank can't afford to destabilize.
What it costs: one more piece of software to deploy, monitor, and keep talking correctly to the core system.

[PAUSE FOR RESPONSES]

Notice what that record does — it doesn't just state the decision, it keeps the reasoning, including the option we turned down and what we gave up by not choosing it. A year from now, when someone asks "why isn't this just part of the main app," this record answers them without anyone needing to remember the original conversation. That's the entire point of writing it down. In the chat — tell me, briefly, one decision from your own project this would apply to.

## Activity

[SCREEN: activity instructions]

On one page, connect your project's core feature across all four views — one line each, using the same names consistently. Then pick the single decision from your project with the most real trade-off behind it, and write it as an ADR in the same four-part format. Trade it with another team — can they follow your reasoning without you explaining it out loud? If not, that's the part to rewrite.

## Closing

[SCREEN: camera]

Everything is built now. Next week, you present it, defend it under real questions, and learn to describe what you built the way you'd describe it in an actual interview. See you then.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 5](../session-05/README.md) · [Course map](../COURSE_MAP.md) · [Session 7 →](../session-07/README.md)
