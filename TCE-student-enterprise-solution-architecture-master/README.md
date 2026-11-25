# Enterprise System Design

**This is the student course repository** for Enterprise System Design at Thiagarajar College of Engineering — everything here is written for you, the student, to read and use directly. (If you're the instructor looking for delivery timing, run sheets, or answer keys, those live in a separate, private planning repository, not here.)

Every company depends on technology. A bank needs systems to manage accounts and transactions. An airline needs systems to manage reservations, aircraft, employees, and passengers. A hospital needs systems to support patients, doctors, medicines, and billing. A college needs systems to register students, run classes, and process fees. All of these systems have to keep working, securely and correctly, every single day.

This course teaches you how systems like that are understood, designed, connected, governed, and improved.

## Start here: the course in one view

If this is your first visit, open the **[Course Map](COURSE_MAP.md)**. It shows the one question each session answers, the artifact you keep, and how that work moves into the next session.

Read the sessions in order. When you finish Session 7, use the Apple Event challenge to test the same thinking across ten connected teams.

When you receive a new case and do not know how to begin, use the **[Solutions Architect Use-Case Playbook](SOLUTIONS_ARCHITECT_USE_CASE_PLAYBOOK.md)**. It walks from the first clarifying question through requirements, capacity, logical design, AWS mapping, security, resilience, cost, delivery, and presentation.

## Who this is for

You're an undergraduate IT student. You already know how to code. You haven't necessarily worked inside a large company yet, and that's completely fine — this course doesn't assume you have. What it does assume is that you're curious about the gap between "a program that runs on my laptop" and "a system a real company can depend on."

## Why this course exists

Writing one working program is a real skill, and you already have it. But a company isn't one program. It's thousands of people, hundreds of applications, huge amounts of data, and infrastructure that all has to work together, all the time, without falling over. A program that works perfectly on your own laptop can still fail completely once it enters that world — not because your code is wrong, but because a company needs things your laptop never had to worry about: enough capacity for thousands of users, safety when something fails, protection for sensitive information, a way to fit in with systems that already exist, someone who can monitor and support it, and a cost that makes sense.

**Enterprise System Design is the discipline of connecting business needs to technology decisions**, so that what gets built actually survives contact with a real, running company.

## What you will learn

By the end of this course, you'll be able to:

- Explain why a company needs more than working software — it needs working *systems*.
- Take a real business problem, find out who it actually affects, and turn that into clear requirements.
- Understand how business processes, applications, data, and technology connect and depend on each other.
- Reason about real trade-offs — cost versus speed, simplicity versus flexibility, on-premise versus cloud — instead of picking a technology because it sounds impressive.
- Think about how a system stays secure, reliable, and supportable once it's live — not just how it's built.
- Present and defend a complete architecture for a real-feeling business problem.

## The learning rhythm

Every session follows the same human learning flow:

1. **Recognize it** through an everyday situation you already understand.
2. **Name the problem** without jumping immediately to a technology.
3. **Learn the concept** in plain language.
4. **See it applied** to the continuing Campus Bank case.
5. **Try it** with your team on a project domain you choose.
6. **Keep one artifact** that becomes part of your final architecture.
7. **Connect it forward** to the next session.

You are not expected to memorize a framework or copy Campus Bank's answer. You are expected to explain why your own decision fits your own problem.

## How the sessions connect

The course follows one path, and every session hands the next one something real to build on — not a clean slate each week:

```
Understand the business → identify requirements → understand what already exists
  → design the solution → evaluate trade-offs → govern and operate it → improve it over time
```

| # | Session | What it adds |
|---|---|---|
| 1 | [Enterprise System Design: How a Company Keeps Its Business Running](session-01/README.md) | Why enterprise systems exist at all, using one new employee's laptop as the way in |
| 2 | [Business Problems, Stakeholders, and Requirements](session-02/README.md) | Who actually cares about a business problem, and how their needs become written requirements |
| 3 | [Business Processes and Application Design](session-03/README.md) | How a business process becomes a real application design, and the trade-offs in how software is structured |
| 4 | [Data Architecture and Governance](session-04/README.md) | What information a company depends on, who owns it, and how it's kept trustworthy |
| 5 | [Technology, Cloud, Security, and Operations](session-05/README.md) | Where systems actually run, how they're kept secure, and how a company keeps them alive day to day |
| 6 | [Bringing It Together and Making Decisions](session-06/README.md) | Connecting business, application, data, and technology into one consistent picture, and writing down *why* a decision was made |
| 7 | [Final Design Review and Presentation](session-07/README.md) | Presenting and defending a complete architecture, the way you'd defend it to a real stakeholder — or an interviewer |

Each session opens with a real-feeling business problem, not a technology. You'll never be taught "here's what a database is" in the abstract — you'll be taught "Campus Bank's customers can't see their transfer status for three days; here's the data decision that responds to that, and here's what it costs."

## What you will build: Campus Bank

Every session uses the same continuing example: **Campus Bank**, a fictional digital bank. You'll follow it from a single business problem all the way to a complete, defended architecture. Using one example across the whole course means you spend your time getting better at *design*, not re-learning a new business every week — which is exactly what a real architect's job looks like: one system, many decisions, over time.

Alongside Campus Bank, you'll build your own architecture for a project of your team's choosing, applying each session's ideas to a domain you pick — a bank, a hospital, a retail company, a campus system, or another business you find interesting.

## How to use this repository

Each `session-0N/` folder holds that session's materials. Use the `README.md` as the main lesson. Use `transcript.md` only when you want to replay the spoken explanation in text. Activities and summaries are for practice and review. Work through the sessions in order; each one reuses a decision made earlier.

You don't need to memorize anything from this repository. You need to be able to explain the ideas in your own words, and to have tried the activity yourself before the next class.

## Where to begin

Start with **[Session 1](session-01/README.md)**. Fifteen minutes in, you'll already be thinking about a company's technology differently than you were before you opened it.

## Final course outcome

By the last session, you and your team will have taken a real-feeling business problem all the way through: who it affects, what it requires, how the software is structured, where the data lives, how it stays secure and reliable, and why you made the decisions you made. You'll present that architecture and defend it — the same conversation you'd have with a stakeholder at a real company, or with an interviewer asking "walk me through something you designed."


## Real-world team architecture challenge

After learning the session concepts, apply them under realistic scale and failure pressure in the **[Apple Event Enterprise Launch Challenge](use-cases/apple-event-enterprise-challenge/README.md)**.

Ten teams design different parts of one connected enterprise—from global livestream and launch-time checkout through data, ML forecasting, stores, manufacturing, fulfillment, customer support, fraud, and resilience. This is not a service-name exercise: teams must calculate capacity, agree on data ownership and interfaces, handle injected failures, document tradeoffs, and defend the complete architecture.