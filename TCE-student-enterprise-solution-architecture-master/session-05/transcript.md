# Session 5 Transcript — Technology, Cloud, Security, and Operations

## How to use this transcript

Use this to test whether your design can survive real operation. For every choice, ask what fails, who notices, and what happens next.

## Human opening

An exam-registration portal may work perfectly with ten test users and still fail when two thousand students open it at 9 AM. That is the difference between software that works and a service an organization can depend on. Today we design for that second standard.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Everything up to now has been decisions on paper. Today, those decisions meet reality — actual servers, actual security rules, actual bills, and actual failures at inconvenient times. This is the session where architecture stops being diagrams and starts being something a company has to operate, every day, including the days nobody's watching closely.

## On-premise vs. cloud

[SCREEN: camera]

On-premise means the company owns its own physical hardware. Cloud means renting capacity from a provider — AWS, Azure — and paying for what you actually use. Neither one is automatically the right answer. On-premise can be cheaper at very large, very steady scale. Cloud is usually faster to start with, and easier to scale up or down as things change.

[PAUSE FOR RESPONSES]

Quick question in the chat — for Campus Bank's transfer-status feature specifically, would you lean cloud or on-premise? No wrong answer yet, I just want to see your instinct before I say anything more.

## Designed, tested, never proven live

[SCREEN: camera]

Here's the part of this session I actually think matters most. Campus Bank has a complete, carefully built plan for how this all runs — packaging, automatic scaling under load, monitoring that would alert someone the moment something looks wrong. Every part of it has been checked and validated by automated tools.

And it has never once run against real, live traffic.

I want you to really sit with that, because it's an extremely common, real situation — not a failure, not something to be embarrassed about. A team can do everything right on paper, pass every check, and still not know for certain how the system behaves at nine in the morning on a Monday until it actually happens. The honest, professional move is saying that gap out loud — "we've validated this, we haven't proven it live" — instead of quietly letting people assume those are the same claim. That distinction is one most junior engineers never learn to make, and I want you to leave this course already knowing it.

## Security and cost, briefly

Security by design means deciding, from the start, who can access what, and giving each part of the system only what it actually needs — not bolting security on at the end. And cost-aware design means understanding what actually drives your bill — computing time, storage, data moved — well enough to guess what a design change costs *before* you build it, not after the invoice shows up.

## Activity

[SCREEN: activity instructions]

For Campus Bank's transfer-status feature: pick on-premise, cloud, or a mix, and justify it. Name one specific way this feature could fail, and describe what the system should do when it does. List two or three things that would drive its running cost. Then repeat all three for your own project.

## Closing

[SCREEN: camera]

You now have decisions across business, application, data, and technology. Next week, we connect all four into one picture, and I teach you how to write down *why* you made a decision, so the reasoning survives even after the decision itself is old news. See you then.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 4](../session-04/README.md) · [Course map](../COURSE_MAP.md) · [Session 6 →](../session-06/README.md)
