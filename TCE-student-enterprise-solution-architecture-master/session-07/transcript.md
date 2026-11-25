# Session 7 Transcript — Final Design Review and Presentation

## How to use this transcript

Use this as presentation rehearsal, not as a script to memorize. Your explanation should sound like you and respond to the room.

## Human opening

If a new teammate cannot understand your design without asking you to explain every box, the architecture is not yet communicating well. Today's review tests more than the diagram. It tests whether the problem, decisions, trade-offs, risks, and evidence form one story another person can follow.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Here's the idea I want to open with: an architecture nobody can explain and defend, out loud, in ten minutes, isn't actually finished — it just hasn't been tested against a skeptical audience yet. Today, you find out where yours stands, safely, among classmates, instead of for the first time in a real interview.

## The whole arc, in one glance

[SCREEN: Session 1's problem statement next to today's finished design]

Let's go back to where we started. Session 1: Campus Bank customers waited three days to see a transfer status, and support staff were stuck manually checking logs. That was it — no technology, just a problem and the people it affected.

Six sessions later, that same problem has named stakeholders and a clear requirement, a real process diagram and an application design decision, a data design with clear ownership, a technology and security design, and a written record explaining why it was built the way it was. That's the entire arc this course walked: understand the business, identify requirements, understand what exists, design the solution, weigh the trade-offs, govern and operate it, improve it over time. None of that required a new framework every week. It required asking the same honest questions, in order, at increasing depth.

## What makes a review actually useful

[SCREEN: camera]

An architecture review is a conversation where someone who didn't build the system tries to find its weak points on purpose — so they're found now, not later, in production. When you're in the audience for someone else's presentation today, your job isn't to be nice. It's to ask one real question that pokes at an actual weak point. "Good job" helps nobody. "Your data design doesn't say who owns the Account entity if the core system and the new feature ever disagree" — that helps.

[PAUSE FOR RESPONSES]

Before presentations start — thirty-second pair check. Trade your problem statement with the person next to you on your team. Can they say it back to you in one sentence? If not, fix the sentence before you present, not after.

## Presenting

[SCREEN: presentation order]

Each team gets about eight to ten minutes: the business problem and who it affects, the process and application design, the data design, the technology and security design, and one Architecture Decision Record, defended live. Then at least one real question from the room.

## Closing

[SCREEN: camera]

You now have a real answer to "tell me about something you designed" — not a class assignment, but a full, defensible story: a real business problem, the people it affected, the decisions you made, the trade-offs you accepted, and why. That's what this course actually produced. Congratulations, and thank you for eight in the morning, every Saturday, all semester.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 6](../session-06/README.md) · [Course map](../COURSE_MAP.md) · [Apple Event challenge →](../use-cases/apple-event-enterprise-challenge/README.md)
