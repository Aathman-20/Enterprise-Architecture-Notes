# Team 08 — Retail Store Demand and Workforce

## Picture the moment

A store opens with a line outside and dozens of pickup reservations. Then its WAN link fails. Associates still need to serve customers without selling pickup inventory to a walk-in buyer.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Prepare 520 stores with the right stock, trained staff, appointments, pickup lanes, and offline resilience.

## Stakeholders

customers, store associates, managers, workforce planners, loss prevention, accessibility users.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

store forecast, replenishment, transfers, appointments, pickup reservation, POS, workforce scheduling, edge/offline sync.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

footfall, reservation, pickup, POS transaction, staff skill/shift, store stock, queue time.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

hourly footfall/demand prediction and schedule recommendations with manager override.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

wait under 15 minutes; reservation ready rate; stock accuracy; labor utilization; offline continuity.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

WAN outage at 40 stores; walk-in surge; pickup inventory missing; duplicate offline/online sale.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Calculate customers/hour, service time, required concurrent associates, POS throughput, offline storage, and reconciliation workload.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Minimize video/footfall identification; fair scheduling; protect employee/customer data; audit overrides.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Hard review question

> During WAN loss, which transactions continue, what local truth is trusted, and how do you reconcile without double-selling after reconnection?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
