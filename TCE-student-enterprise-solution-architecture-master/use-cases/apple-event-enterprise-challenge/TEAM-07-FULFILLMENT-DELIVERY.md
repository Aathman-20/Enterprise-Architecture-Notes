# Team 07 — Allocation, Fulfillment, and Delivery Promise

## Picture the moment

A customer is promised Friday delivery. The nearest warehouse is overloaded and the carrier cutoff is approaching. Your system must decide whether another location can keep the promise without creating an expensive split shipment.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Allocate scarce inventory fairly and produce a delivery promise that remains believable through warehouse, carrier, customs, and weather changes.

## Stakeholders

customers, allocation planners, warehouses, carriers, customs, stores, support.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

allocation rules, order routing, warehouse orchestration, carrier selection, promise engine, tracking, exception management.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

inventory position, order priority, node capacity, cutoff, route, carrier SLA, scan, customs status.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

ETA/delay prediction and constrained allocation optimization with policy guardrails.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

promise accuracy above 95%; on-time rate; minimized split shipments and cost; fair regional service.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

warehouse overload; carrier API outage; out-of-order scans; customs delay; inventory mismatch.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Calculate units/hour per warehouse, queue growth, pick-pack capacity, carrier cutoff volume, network transit, and backlog-clear time.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Limit carrier/customer data, encrypt labels, audit prioritization, and explain allocation exceptions.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Required shared case

Work with Teams 05 and 06 on the [six-day order-to-delivery case](CROSS-TEAM-CASE-ORDER-TO-DELIVERY.md). Decide when to keep September 18, when to offer another configuration or pickup location, and when to show a later date. Your promise must consider physical inventory, existing reservations, warehouse throughput, store capacity, carrier cutoffs, and transit time.

## Hard review question

> What is fair allocation: first-come-first-served, market quota, customer priority, or business value—and who approves that policy?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
