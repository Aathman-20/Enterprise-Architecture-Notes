# Team 01 — Global Livestream Platform

## Picture the moment

At 9:59 a.m., millions of screens show the countdown. A few seconds later, one CDN begins failing in Southeast Asia while the venue feed is still healthy. Viewers do not care which company caused the problem; they see one broken event.

Begin with the outcome. Agree on what must remain true for the customer and the business before choosing technology.

[← Challenge overview](README.md)

## Mission

Deliver a high-quality worldwide event stream without making the venue or a single cloud/CDN region a global point of failure.

## Stakeholders

viewers, event production, media operations, accessibility users, network/CDN partners.

## Outcomes and boundaries

Write four measurable outcomes: one for the customer, one for operations, one for money, and one for risk. Then show where your responsibility begins and ends. Name the decisions your team owns, the decisions it receives from other teams, and the decisions it must never make.

## Capabilities your design must cover

multi-bitrate encoding, origin shielding, multi-CDN routing, captions, replay, QoE telemetry.

For each capability, explain its job, owner, trusted data, and behavior when a dependency is slow or unavailable. A box without those answers is only a label, not a design.

## Data that matters

viewer session, playback start, bitrate, buffer time, device class, country, CDN, error.

Identify the business key and source of truth for each important record. Then cover timestamps, classification, retention, quality, lineage, correction, and—where scale requires it—partitioning. Clearly distinguish authoritative state from a cache, read model, or analytical copy.

## Analytics or ML question

regional demand prediction and early anomaly detection for rebuffering.

First decide whether rules or ordinary analytics are enough. If ML adds real value, define the prediction, data available at decision time, offline test, production KPI, bias or leakage risk, deployment and monitoring, human control, rollback, and a simple fallback.

## Starting quality targets

startup under 2 seconds at p95; rebuffer ratio under 0.5%; playback success 99.95%.

Add p50, p95, and p99 latency where relevant. Define availability from the user’s perspective. Include RTO, RPO, data freshness, durability, error budget, and recovery validation.

## Failure scenarios to design

venue uplink loss; CDN degradation; telemetry surge larger than video control plane.

For each, show detection, blast radius, degraded mode, containment, owner, recovery, reconciliation, and customer communication. Include one compound failure where two things go wrong together.

## Required capacity work

Calculate 20M viewers at 6 Mbps average, CDN egress per minute, telemetry EPS, storage for all renditions, and origin traffic with and without shielding.

Show formulas, units, peak-to-average ratio, headroom, and the first expected bottleneck. Explain how long the system can buffer and how fast it can recover or replay after an outage.

## Security and governance

Protect viewing history and precise location; separate aggregate operations telemetry from identifiable account data.

Draw trust boundaries and list at least five threats. Include authentication, authorization, encryption, secrets, audit, privacy, data residency, abuse control, and deletion/retention.

## Required cross-team contracts

Define at least three inbound and three outbound APIs/events. Coordinate names and ownership using the [shared interface catalog](SHARED-INTERFACE-CATALOG.md). For each contract cover versioning, idempotency, ordering, retry, timeout, dead-letter/replay, security, and SLO.

## Architecture decisions

Write at least two ADRs. Compare three realistic options. Include disadvantages and the evidence that would reverse your choice.

## Hard review question

> Can the event continue if both primary contribution feeds fail after the venue has already produced 15 minutes of content?

## Before you submit

Read the design aloud as one story. Follow one customer action from beginning to end, then repeat the journey with a failure injected. Check that the diagrams, numbers, contracts, security controls, and recovery steps agree. If a teammate cannot explain why a component exists, simplify or justify it.

Use the [submission template](SUBMISSION_TEMPLATE.md) and expect a random [challenge card](CHALLENGE-CARDS.md) during review.

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
