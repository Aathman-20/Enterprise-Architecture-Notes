# Shared Interface Catalog

This catalog is the agreement between teams. Before inventing a new API or event, check whether another team already owns the business fact. Agree on meaning and ownership first; schema comes next.

## This is a team conversation

An interface is not finished because one team wrote an event name. The producer and consumer must agree on what the event means, when it is final, how duplicates behave, and who repairs bad data. Sit with the other team and settle those questions together.

This catalog is a starting point, not a complete design. Teams must agree on ownership, schemas, versioning, reliability, and privacy before drawing final diagrams.

| Business object/event | Candidate owner | Likely consumers | Key correctness concern |
| --- | --- | --- | --- |
| ProductPublished | Product/catalog | Store, analytics, support | Effective time and market eligibility |
| PriceActivated | Pricing | Checkout, stores, analytics | Currency, tax, market, exact activation time |
| ViewerEngaged | Livestream | Analytics, forecast | Sampling, privacy, late arrival |
| CartUpdated | Commerce | Analytics, forecast, fraud | Session identity and duplicates |
| PaymentAuthorized | Payment | Order/inventory | Timeout after successful authorization |
| InventoryHeld | Inventory | Commerce, allocation | Expiry, fencing/version, oversell |
| OrderConfirmed | Order | Fulfillment, forecast, support | Exactly-once business effect |
| DemandForecastPublished | Forecast | Planning, allocation, stores | Version, horizon, confidence range |
| DemandPlanChanged | Forecast | Manufacturing, allocation, command center | Prior version, reason, freshness, and approval status |
| SupplyResponsePublished | Manufacturing | Forecast, allocation, finance | Earliest available date, quantity, constraint, cost, and plan version |
| ProductionPlanApproved | Manufacturing | Supplier, allocation, analytics | Human approval and frozen horizon |
| UnitProduced | Factory | Inventory, quality, allocation | Serial/lot traceability |
| InventoryPositionChanged | Inventory | Store, commerce, allocation | Location and available-to-promise truth |
| DeliveryPromiseCreated | Fulfillment | Commerce, support | Inputs, promise version, expiry, and customer-visible date |
| DeliveryPromiseChanged | Fulfillment | Commerce, support, analytics | Previous date, new date, reason, approval, and customer notification |
| ShipmentStatusChanged | Logistics | Support, analytics | Carrier duplication and out-of-order scans |
| CustomerIssueDetected | Support | Product, operations, security | Approved source and privacy |
| RiskDecisionMade | Security/fraud | Checkout, support | Explanation, appeal, model/rule version |

## Minimum event envelope

Every event proposal must contain:

- event_id: globally unique identifier
- event_type and schema_version
- occurred_at and ingested_at
- producer and data_owner
- business_entity_id
- correlation_id and causation_id
- region and data_classification
- payload
- trace context
- replay flag when applicable

## Questions teams must resolve together

1. Is an event a statement of fact or a command asking another team to act?
2. Can it be changed, or must a correction be a new event?
3. What ordering is required and for which business key?
4. How long can a consumer be unavailable?
5. Who handles schema evolution?
6. Can the payload contain customer data?
7. How are deletion and retention obligations propagated?
8. How does a consumer rebuild state after loss?
9. Which actions require synchronous confirmation?
10. How is end-to-end traceability demonstrated?

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
