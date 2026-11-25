# Session 3 Transcript — Business Processes and Application Design

## How to use this transcript

Follow the spoken example, then stop and draw your own process before continuing. The value is in making the decision yourself.

## Human opening

Think about ordering food through an app. The app does not simply “deliver food.” It accepts the order, confirms payment, sends it to the restaurant, assigns a delivery partner, tracks progress, and handles failure. One customer action crosses a process and several applications. Campus Bank's transfer-status problem works the same way.

**Format:** Live Zoom delivery script, written to be spoken naturally.

---

[SCREEN: camera]

Last week, we turned a vague complaint into a specific requirement: Campus Bank customers need to see their transfer status within five seconds, without calling anyone. Today, we ask the question that comes right after that: what actually has to happen, step by step, for that to work — and what software structure would deliver it?

## The process, step by step

[SCREEN: the process steps, or draw them live]

Here's Campus Bank's real transfer process. A customer requests a transfer. The system checks that this exact request hasn't already been submitted — that matters, because without it, a customer double-clicking "send" could accidentally send money twice. Then it checks the account actually has enough balance. Then it moves the money. Then it records what happened, with a traceable ID attached. And finally, it returns the result to the customer.

[PAUSE FOR RESPONSES]

Before I go further — in the chat, guess: which one of those five steps do you think is the one most likely to be missing in a poorly designed system? ... A lot of you are saying the duplicate-request check, and you're right to guess that — it's the one that's easy to forget and expensive to get wrong.

## One application, or several?

[SCREEN: camera]

Right now, this whole process lives inside one connected application — accounts, transfers, login, all built and released together. That's called a monolith, and for Campus Bank's current size, that's a completely reasonable choice — one team can hold the whole thing in their head, and testing a change is simpler when everything's in one place.

But here's the real question this session is about: if we build that new "check my status" feature from last week's requirement, should it live inside that same connected application, or as its own small, separate piece?

Building it inside the existing application is simpler right now — one less thing to deploy. But it ties the future of this new, less-proven feature to a system the bank genuinely cannot afford to destabilize. Building it separately keeps it isolated — but now there are two things to run, monitor, and keep talking to each other correctly.

I want to be really clear about something: there is no "obviously correct" answer here. Anyone who tells you microservices are always the modern, better choice hasn't actually paid the operational cost of running them. The right answer depends on team size, how often this piece will change, and how much complexity you're actually ready to operate. That honest trade-off — that's the actual skill this session teaches.

## Activity

[SCREEN: activity instructions]

Draw a simple process diagram for Campus Bank's transfer flow — boxes for steps, a diamond for the duplicate-check decision, arrows for order. Then, as a team, decide: inside the existing application, or separate? Write three bullet points defending your choice, and be honest about what it costs you, not just what it gains you. Then repeat both steps for your own project's core process.

## Closing

[SCREEN: camera]

Today we decided how the software is structured. Next week, we ask what information this process actually depends on, where it lives, and who's responsible for it being correct. See you then.

[SCREEN: fade to camera, end]

---

## Where to go next

[← Session 2](../session-02/README.md) · [Course map](../COURSE_MAP.md) · [Session 4 →](../session-04/README.md)
