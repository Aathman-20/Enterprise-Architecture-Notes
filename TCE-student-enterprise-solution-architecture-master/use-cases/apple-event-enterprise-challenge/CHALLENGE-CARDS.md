# Challenge Cards

A challenge card tests whether the architecture can adapt without losing its core guarantees. State what changes, what remains protected, and which earlier decision you would revisit. You do not need to redesign the whole system.

## When a card appears

Pause for one minute. Do not add five new products or redraw the whole architecture. Point to the part of your existing design that should absorb the problem. If you cannot point to one, you have found a missing responsibility.

Your instructor may reveal cards during the design review. Do not redesign everything. Explain detection, containment, degraded operation, recovery, reconciliation, and customer communication.

## Card A — The 20x surprise

A celebrity mention causes one region to exceed forecast traffic by 20x for 12 minutes. Autoscaling needs five minutes to add capacity.

## Card B — Payment ambiguity

The payment provider times out for 3% of requests. Half of those payments actually succeeded. Customers press Buy again.

## Card C — Hot inventory

One color/storage combination receives 55% of orders but contains only 12% of inventory. Two regions believe the same 25,000 units are available.

## Card D — Poison event

A new producer sends a valid schema with a logically impossible negative quantity. The event is copied into analytics and planning.

## Card E — Regional data restriction

A regulator says customer-level behavioral data cannot leave the country. Global executives still need launch metrics.

## Card F — Forecast manipulation

Bot traffic makes product interest appear four times higher than genuine demand. The production optimizer recommends an expensive factory change.

## Card G — Factory disruption

A supplier producing one critical component loses 40% of capacity for three weeks. Existing finished-goods inventory covers only nine days.

## Card H — Logistics outage

A carrier API is unavailable for six hours after accepting shipments. Customers see no tracking movement.

## Card I — Store WAN failure

Forty stores lose WAN access on launch morning. Customers with valid pickup reservations are waiting outside.

## Card J — GenAI misinformation

The support assistant confidently invents a warranty promise that is not present in approved policy.

## Card K — Credential compromise

A service account with broad access is used from an unfamiliar geography. It has access to customer, order, and inventory data.

## Card L — Observability failure

Technical dashboards are green, but conversion in one major market has fallen to zero because the wrong price is displayed.

## Response format

For the selected card, answer:

1. What first signal detects it?
2. What automated action is safe?
3. Who owns the incident?
4. What continues and what is disabled?
5. What data must be reconciled?
6. What is communicated to customers and leaders?
7. What design change reduces recurrence?
8. Which SLO, KPI, or risk limit was violated?

---

[← Challenge home](README.md) · [Submission template](SUBMISSION_TEMPLATE.md) · [Course map](../../COURSE_MAP.md)
