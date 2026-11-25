# Team 06 — Supply, Supplier, and Manufacturing Planning

## Picture the moment

Demand doubles after the reveal, but a camera component has a ten-week lead time and one supplier is already at capacity. A forecast is not yet a build plan; your job is to find a plan the factories can actually execute.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Convert approved demand into a feasible production plan across components, suppliers, factories, quality constraints, lead times, and cost.

## Stakeholders

supply planners, procurement, suppliers, factories, quality, finance, sustainability.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

BOM explosion, supplier commitments, capacity/yield model, scenario solver, approval workflow, ERP/MES integration.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

forecast version, BOM, component lot, lead time, capacity, yield, work order, quality result, shipment.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

supplier-delay and yield prediction; optimization for service, cost, lead time, carbon, and risk.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

plan feasibility 100%; frozen-window stability; reduced shortage/expedite cost; traceability by lot.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

critical supplier loses 40%; quality hold; forecast doubles; ERP unavailable during plan publication.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Calculate required components from forecast and BOM, usable output from yield, bottleneck capacity, safety stock, lead-time gap, and recovery scenarios.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Supplier confidentiality, segregation of duties, signed approvals, immutable change history, and factory network boundaries.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Required shared case

Work with Teams 05 and 07 on the [six-day order-to-delivery case](CROSS-TEAM-CASE-ORDER-TO-DELIVERY.md). Be explicit that launch-week phones were largely produced and positioned before orders opened. Use first-day demand to decide later production waves, component commitments, overtime, and expedite options. Do not claim that increasing factory output on Saturday automatically creates stock for Friday.

## Hard review question

> Which decisions are automated, which require human approval, and how do you stop nervous planning from changing the factory every 15 minutes?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
