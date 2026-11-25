# Team 10 — Security, Fraud, Bots, and Enterprise Resilience

## Picture the moment

Attack traffic and genuine buyers arrive together. Blocking everything protects the system but ruins the launch; allowing everything rewards bots and fraud. Your design must make that trade-off visible and controllable.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Protect the launch from abuse and cyber failure without blocking genuine customers or becoming a central bottleneck.

## Stakeholders

customers, security operations, fraud, identity, payments, legal, SRE, all other teams.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

DDoS/WAF, bot defense, identity risk, fraud decisioning, secrets, policy, SIEM, incident orchestration, recovery testing.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

request/device/account/payment/order risk, rule/model version, decision reason, alert, evidence, audit.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

bot and fraud scoring combined with rules, human review, appeal, and safe fallback.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

attack absorption; low false-positive rate; fraud loss limit; MTTD/MTTR; tested RTO/RPO.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

credential stuffing; compromised service account; DDoS; fraud model unavailable; regional outage.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Model attack traffic at multiples of 2M requests/second, risk-decision latency, log volume, review queue, replication, and recovery/replay time.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Least privilege, separation of duties, key rotation, tamper-resistant evidence, tokenization, data minimization, and explainable denials.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Hard review question

> How does each critical team operate if your fraud, identity, or security telemetry service is unavailable?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
