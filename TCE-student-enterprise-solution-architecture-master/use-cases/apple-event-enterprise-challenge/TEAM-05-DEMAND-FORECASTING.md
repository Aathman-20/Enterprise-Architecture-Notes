# Team 05 — ML Demand Sensing and Forecasting

## Picture the moment

Views and carts suggest enormous demand for one color. Later you discover that bots produced much of the activity. A factory plan based on the raw signal would create months of unwanted inventory.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Turn uncertain pre-launch interest and early orders into calibrated demand ranges by product, configuration, region, channel, and time.

## Stakeholders

demand planners, finance, manufacturing, allocation, stores, product leadership.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

historical baseline, streaming features, feature store, model training, inference, registry, monitoring, planner approval.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

sales history, price, calendar, availability, views, searches, carts, orders, sentiment, bot score.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

hierarchical probabilistic forecasting plus demand sensing; separate unconstrained demand from sales limited by stock.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

forecast bias within agreed band; confidence coverage; freshness under 15 minutes; reduced stockouts/excess.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

cold-start product; bot-inflated interest; stockout hides demand; delayed features; drift after reveal.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Estimate feature/event volume, dimensional series count, training window, inference frequency, compute window, and forecast publication size.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Do not use protected traits for allocation; document proxy risks, model version, approval, and override reason.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Required shared case

Work with Teams 06 and 07 on the [six-day order-to-delivery case](CROSS-TEAM-CASE-ORDER-TO-DELIVERY.md). Your forecast must separate a fast launch-day demand update from a production recommendation. Publish a range and confidence—not one unexplained number—and show how bot traffic, stockouts, and stale events change the result.

## Hard review question

> How do you learn true demand when customers cannot order an out-of-stock configuration?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
