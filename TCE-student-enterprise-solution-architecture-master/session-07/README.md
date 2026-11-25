# Session 7: Final Design Review and Presentation

## Your path through this session

This is the final review. Tell one connected story: problem, people, process, applications, data, technology, decisions, risks, and outcomes.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

## Purpose

An architecture nobody can explain and defend, out loud, in ten minutes, isn't finished — it just hasn't been tested against a skeptical audience yet. This session is where you find that out safely, among classmates, instead of for the first time in a real interview.

## A familiar example

If a new teammate cannot understand your design without asking you to explain every box, the architecture is not yet communicating well. A final review tests more than the diagram: it tests whether the problem, decisions, trade-offs, risks, and evidence form one story that another person can follow.

## What you'll be able to do after this session

- Present a complete architecture clearly to people seeing it for the first time.
- Answer hard, honest questions about your design without getting defensive.
- Review someone else's architecture and give feedback that's genuinely useful, not just polite.
- Describe what you built, in one or two sentences, the way you'd describe it to an interviewer.

## Key ideas

**Architecture review**
A structured conversation where someone who didn't build the system tries to find its weak points on purpose — so those weak points are found now, in a classroom, instead of later, in production.

**Portfolio readiness**
Whether a stranger — a recruiter, an interviewer, a new teammate — can look at your work and understand what you built and why, in under two minutes, without you standing next to them explaining it.

**Understanding check, before you present:** can you say your entire project's problem and design in two or three sentences, without notes? If not, that's worth fixing before your slot, not during it.

## Campus Bank: the whole arc, in one glance

Go back to the Campus Bank problem introduced in Session 2: customers waited up to three days to see a transfer status, and support staff were stuck manually checking logs. That was the entire starting point — no technology, just a problem and the people it affected.

Six sessions later, that same problem has: named stakeholders and a clear requirement (Session 2), a real process diagram and an application design decision (Session 3), a data design with clear ownership (Session 4), a technology and security design (Session 5), and a written decision record explaining why it was built the way it was (Session 6). That's the entire arc this course walks: **understand the business → identify requirements → understand the existing environment → design the solution → evaluate trade-offs → govern and operate it → improve it over time.** Nothing about that arc required a new framework each week — it required asking the same honest questions, in order, at increasing depth.

## Activity: Present and defend

Each team presents their project's architecture in about 8–10 minutes, covering: the business problem and who it affects, the process and application design, the data design, the technology and security design, and one Architecture Decision Record, defended live. After each presentation, the audience asks at least one real question — not a compliment, a question that pokes at a real weak point.

Then, trade written feedback with one other team: one specific strength, and one specific place their design could be pushed further. Useful feedback names something concrete — not "good job," but "your data design doesn't say who owns the Account entity if the core system and the new feature ever disagree."

**Understanding check, while watching another team present:** could you explain their design's hardest trade-off back to them in one sentence? If not, that's the question worth asking them.

**Understanding check, after your own presentation:** what's one question you got that you didn't have a great answer for? That's worth thinking through even after the class ends — it's the realistic version of what an interviewer will ask.

## What you'll produce

Your final architecture document and diagrams, delivered as a live presentation, plus one written piece of feedback for another team, and one you receive.

## Connecting to your final project

This session *is* the final project's delivery. Everything from Sessions 2 through 6 comes together here, as a single, defensible story — not seven disconnected artifacts, but one problem followed all the way through to a working design.

## Recap

A finished architecture is one you can explain and defend out loud, under real questions, to someone who didn't build it. Getting feedback that actually challenges your design, and giving it honestly to someone else, is as much a part of this discipline as the design work itself.

## What comes next

You now have a real answer to "tell me about something you designed" — not a class assignment, but a full, defensible story: a real-feeling business problem, the people it affected, the decisions you made, the trade-offs you accepted, and why. That's the actual outcome of this course — not a transcript, not a grade, but a piece of work you can stand behind.

---

## Where to go next

[← Session 6](../session-06/README.md) · [Course map](../COURSE_MAP.md) · [Apple Event challenge →](../use-cases/apple-event-enterprise-challenge/README.md)
