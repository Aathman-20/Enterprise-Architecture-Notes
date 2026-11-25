# Session 2: Business Problems, Stakeholders, and Requirements

## Your path through this session

You now know why enterprise systems matter. Next, learn to turn a vague complaint into a problem, a stakeholder need, and a testable requirement.

**Start with:** the opening story.  
**Work on:** the activity using your own team project.  
**Keep:** the artifact named in “What you’ll produce”; you will use it in the next session.

# Part 1 — Understand

## Purpose

In Session 1, you learned that a company's technology is made of many connected pieces, and that things only work when those pieces are designed on purpose. Today we go one level deeper: before anyone designs anything, someone has to figure out *what problem is actually being solved, for whom, and why.* Skip this step, and you can build a system that works perfectly and still solves the wrong problem.

## A familiar example

Imagine a student says, "The college portal is bad." That is a complaint, but it is not yet a usable problem statement. Do pages fail to load during registration? Are marks published late? Can students not tell whether a fee payment succeeded? Each version affects different people and leads to different requirements. Architecture begins by replacing the vague complaint with the specific problem.

## What you'll be able to do after this session

- Take a vague complaint ("customers are unhappy") and turn it into a clear, specific business problem.
- Identify the stakeholders affected by a problem, and explain what each one actually needs.
- Tell the difference between what someone *says* they want and what they actually *need*.
- Write a requirement clearly enough that two different people would build the same thing from it.

## Key ideas

**Stakeholder**
Anyone affected by a decision, or who has a say in it. Not just "the customer" — think about the people who support the system, the people who pay for it, and the people who have to follow rules because of it. In a college, that's students, but it's also faculty, the finance office, and the IT helpdesk.

**Business problem**
A specific, describable gap between what's happening now and what should be happening — not a technology choice. "Customers wait three days to see if their transfer went through" is a business problem. "We should use a faster database" is not — that's a possible answer, arrived at too early.

**Requirement**
A clear statement of what a system must do, written specifically enough that it can't be interpreted two different ways. "The app should be fast" is not a requirement — how fast, for whom, doing what? "A customer must be able to see their transfer status within 5 seconds of opening the app" is a requirement.

Requirements actually come in two flavors, and it's worth knowing both names. A **functional requirement** describes *what* the system does — "a customer can see their transfer status." A **non-functional requirement** describes *how well* it does it — the "within 5 seconds" part. Non-functional requirements are just as real and just as buildable as functional ones; you'll meet more of them later in the course, like how secure something needs to be (Session 5) or how reliable it needs to be (Session 5).

**Stated want vs. real need**
What a stakeholder asks for isn't always what actually solves their problem. A branch manager might ask for "a bigger report" when what they actually need is "the same report, but able to catch errors before customers notice them." Part of this skill is asking enough questions to find the real need underneath the request.

**Understanding check:** before moving on, try explaining "stated want vs. real need" back in your own words, using an example from your own life — not the branch-manager one. If you can't think of one yet, that's a good sign to ask a question now rather than later.

## Campus Bank: the problem we'll work through

Here's the business problem Campus Bank is facing, and it's the one we'll use for the rest of the course:

> Campus Bank customers currently wait up to three days to find out whether a money transfer they sent actually went through. Support staff spend hours each week manually checking logs to answer "where is my money" calls. The bank doesn't know how many customers this affects, or what it's costing in support time and customer trust.

Notice what this problem statement does *not* do: it doesn't mention a database, an API, or a technology of any kind. It says what's wrong, for whom, and what it's costing. That's on purpose — the moment you jump to "we need a faster backend," you've skipped past understanding the actual people affected.

**Campus Bank's stakeholders for this problem**, and what each one actually needs:

| Stakeholder | What they need |
|---|---|
| Retail customer | To know their transfer status quickly, without calling anyone |
| Support staff | A way to answer "where's my money" without manually digging through logs |
| Compliance officer | Every transfer traceable, with a clear record of what happened and when |
| Bank's engineering team | A solution that doesn't destabilize the transfer system that already works |
| CFO | A solution that doesn't require expensive new infrastructure just to show a status |

**Understanding check:** which team might "own" the decision of how fast the status has to update — the customer, support, or engineering? There isn't one clean answer; that's worth discussing out loud.

## Part 1 checkpoint

Before the break: you should now be able to tell a real business problem apart from a technology decision disguised as one, and name at least five real stakeholders for Campus Bank's transfer-status problem. If that's not solid yet, that's worth more discussion time now — Part 2 builds directly on it.

---

## Ten-minute break

---

# Part 2 — Apply

## Activity: Turn a complaint into a requirement

Working with your team, take Campus Bank's problem statement above and:

1. List every stakeholder you can think of, beyond the five already named.
2. For each stakeholder, write one sentence describing what they actually need — not what a system should do, what *they* need.
3. Pick the single most important stakeholder need, and write it as one clear requirement — specific enough that two different people building it would build the same thing.
4. Do the same for your own team's project domain: write a one-paragraph business problem statement (no technology names allowed in it), and list at least four real stakeholders.

**Understanding check, once you've drafted a requirement:** could a stranger who never heard this discussion build the right thing from your sentence alone? If you're not sure, that's the thing to fix before moving on.

## What you'll produce

A one-page stakeholder list and a first draft of your project's business problem statement — no diagrams yet, just clear, specific writing. You'll use this again, unchanged in substance, in every session from here on.

## Connecting to your final project

This is where your final project actually starts. Everything you build for the rest of the semester — the process diagrams, the application design, the data design, the technology choices — has to trace back to the problem statement and stakeholder list you write today. If a later decision doesn't help one of these stakeholders, that's worth questioning.

## What this is called, professionally

What you just did — turning a vague complaint into named stakeholders and a specific requirement — has a name: **requirements engineering.** It's a real, named discipline, not something this course invented. There's also a formal framework called **TOGAF** that organizes this kind of work (and everything else this course covers) into a repeatable cycle architects walk again and again. You'll hear TOGAF mentioned again later in the course — for now, just know that you already did the real thing it describes, before knowing its name. That order is deliberate: the name means more once you've felt the need for it.

## Recap

A business problem is a specific gap, described without naming a technology. Stakeholders are everyone affected by it, not just the obvious ones. A requirement has to be specific enough that it can't be misread. Getting this step wrong means everything you build afterward is aimed at the wrong target, no matter how well you build it.

## Looking ahead to Session 3

Now that we know *who* Campus Bank's transfer-status problem affects and *what* they need, Session 3 asks: what does the actual process look like today, step by step, and what application design would fix it? We turn today's requirement into a real process diagram and a real design decision.

---

## Where to go next

[← Session 1](../session-01/README.md) · [Course map](../COURSE_MAP.md) · [Session 3 →](../session-03/README.md)
