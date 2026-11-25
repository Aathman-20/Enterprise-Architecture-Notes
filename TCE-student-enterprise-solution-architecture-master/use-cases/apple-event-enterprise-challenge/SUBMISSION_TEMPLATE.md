# Student Submission Template

Use this template to build an argument, not to fill boxes. Every section should help a reviewer understand the business outcome, the evidence behind the design, and how the system behaves when reality differs from the plan.

## A practical way to use this template

Do not fill this page from top to bottom in one pass. Start with the executive summary, sketch the flow, and write down unknowns. Add numbers, contracts, security, and failures only after the team agrees on the basic story. Return to the executive summary last and rewrite it.

Copy this file into your team workspace. Replace prompts with your own reasoning.

## 1. Executive summary

Explain the problem, affected users, business outcome, recommendation, largest risk, and requested decision in no more than 250 words.

## 2. Scope

### In scope

- 

### Out of scope

- 

### Facts, assumptions, and unknowns

| Type | Statement | How it will be validated |
| --- | --- | --- |
| Fact |  |  |
| Assumption |  |  |
| Unknown |  |  |

## 3. Stakeholders and measurable outcomes

| Stakeholder | Need | Risk if unmet | KPI and target |
| --- | --- | --- | --- |
|  |  |  |  |

## 4. Architecture views

Provide:

1. Context diagram showing users, external parties, and your system boundary.
2. Logical diagram showing responsibilities and major data movement.
3. One sequence for the critical path.
4. Deployment/failure-domain diagram.

A box must have a responsibility, owner, data handled, and scaling/failure behavior.

## 5. Capacity model

Show formulas and units.

| Workload | Average | Peak | Burst duration | Payload | Daily volume | Design headroom |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
|  |  |  |  |  |  |  |

Calculate network throughput, requests or events per second, storage per day, database write/read load, and recovery replay time. State whether compression, replication, retention, and indexing are included.

## 6. Data and integration

### System-of-record table

| Data domain | Authoritative owner | Store | Consistency | Retention | Classification |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

### Three contracts

For each API/event include name, producer, consumer, schema fields, identifier, event time, version, ordering key, authentication, authorization, retry, idempotency, error/dead-letter handling, and SLO.

## 7. Quality attributes

| Attribute | Target | Measurement | Design response |
| --- | --- | --- | --- |
| Availability |  |  |  |
| Latency |  |  |  |
| Durability |  |  |  |
| Data freshness |  |  |  |
| RTO/RPO |  |  |  |

Explain consistency choices using a real business example.

## 8. Security and privacy

Identify trust boundaries, threats, least-privilege roles, secrets, encryption, abuse prevention, regional restrictions, audit evidence, retention/deletion, and incident response.

## 9. Analytics and ML

State the decision improved by ML, label/target, features available at decision time, offline metric, online KPI, bias or leakage risk, deployment, drift detection, retraining, human approval, rollback, and non-ML fallback.

If ML is not justified, explain why rules or conventional software are better.

## 10. Failure analysis

| Failure | Customer impact | Detection | Immediate action | Recovery | Prevention |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

Include dependency timeout, regional outage, corrupted or delayed data, duplicate operation, and overload behavior.

## 11. Decisions

Write two short ADRs:

- Context and constraints
- Options considered
- Decision and why
- Consequences
- Evidence that would reverse the decision

## 12. Cost and operations

Identify the five largest cost drivers. Explain scaling guardrails, cost anomaly detection, ownership, dashboard, alerts, runbook, on-call escalation, maintenance, patching, recovery test, and audit review.

## 13. Cross-team agreement

List three inbound and three outbound contracts. Resolve ownership conflicts with other teams. Name the behavior when a dependency is unavailable.

## 14. Final defense

Prepare a 3-minute executive explanation and 7-minute technical walkthrough. Every member must answer at least one challenge question.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
