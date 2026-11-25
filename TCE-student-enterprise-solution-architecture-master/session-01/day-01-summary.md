# Day 1 — One-Page Recap

## Use this page

Try to explain each idea aloud before reading the answer below it. If you can explain the new-employee story and the four architecture views in your own words, you are ready for Session 2.

Use this to refresh your memory before Session 2. It only covers what matters most — for the full explanation, go back to [README.md](README.md).

## The one question we started with

What technology does a large company need before even one employee can perform their job? Answer: a lot more than you'd guess — and none of it is optional.

## The new employee story, compressed

```mermaid
flowchart LR
    A[HR creates employee record] --> B[Manager requests laptop]
    B --> C[Laptop set up & secured]
    C --> D[Employee gets identity & email]
    D --> E[Access granted to job apps]
    E --> F[IT supports & patches laptop]
    F --> G[Access changes with role]
    G --> H[Access removed, laptop returned]
```

One "simple" laptop request touches people, business processes, applications, data, hardware, networks, security, vendors, policies, support teams, costs, compliance, and architecture decisions — all at once.

## From one employee to a whole company

Multiply that story by thousands of employees, and you get everything a large company has to run at the same time: devices, servers, networks, applications, databases, cloud services, identities and permissions, cybersecurity, licenses, vendor contracts, data centers, a help desk, monitoring, backups, disaster recovery, compliance, budgets, and old and new systems running side by side. None of it works if these pieces are disconnected from each other.

## Why this course exists

A program that runs correctly on your laptop can still fail inside a real company — not because the logic is wrong, but because it can't handle real users, real failures, real security needs, or real cost limits. Programming teaches you to build the pieces. Enterprise system design teaches you how those pieces fit into a company that has to keep running.

## Business as Usual (BAU)

> The organization can keep doing its normal daily work, reliably, every day.

BAU doesn't happen automatically — it depends on systems being reliable, available, secure, supported, monitored, backed up, and governed, all at the same time.

## Enterprise architecture, in one sentence

> Understanding how a company's business processes, applications, data, and technology fit together, so decisions are coordinated instead of every team building something disconnected.

| View | Question it answers |
|---|---|
| Business | What work needs to get done? |
| Application | What software supports that work? |
| Data | What information does the company use? |
| Technology | What does it all run on? |

**Governance**, in one line: agreed rules and decision processes so technology is purchased, built, secured, operated, and retired responsibly.

## Carry this into Session 2

The skill from today: noticing the system behind something that looks simple. Session 2 uses that skill on a real Campus Bank business problem — identifying stakeholders and turning their needs into clear requirements.

---

## Where to go next

[← Course home](../README.md) · [Course map](../COURSE_MAP.md) · [Session 2 →](../session-02/README.md)
