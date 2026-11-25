# Team 03 — Inventory Reservation and Order Integrity

## Picture the moment

Only one unit of the most popular configuration remains. Customers in two regions press Buy almost together. Both deserve a fast answer, but the business can confirm the unit only once.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Guarantee that confirmed orders correspond to real units while serving online, retail, and partner channels.

## Stakeholders

customers, order operations, inventory planners, stores, finance, fulfillment.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

available-to-promise ledger, holds, expiry, payment coordination, confirmation, cancellation, reconciliation.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

SKU, configuration, location, on-hand, safety stock, held, committed, in-transit, version.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

conversion probability for holds only if it cannot create unfair cancellation.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

zero confirmed oversells; reservation p99 under 500 ms; reconciliation under 15 minutes.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

concurrent last-unit requests; expired hold with late payment; duplicate events; regional split brain.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Estimate reservation TPS from 8M attempts, hot-key concentration, write amplification, expiry workload, ledger storage, and replay time.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Restrict order/customer linkage; immutable audit trail for inventory adjustments and overrides.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Hard review question

> Choose and defend consistency boundaries. What occurs when payment succeeds one second after a hold expires?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
