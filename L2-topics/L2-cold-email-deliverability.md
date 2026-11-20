---
level: L2
type: topic
area: SAL
conclusions: ["C-SAL-01", "C-SAL-02"]
sources: ["[[L3-example-operator-deliverability-talk]]"]
updated: 2026-01-15
example: "FICTIONAL sources. Mechanics are real-world general practice."
---

# L2 · Cold email deliverability

## Summary

Authentication (SPF, DKIM, DMARC) is necessary and not sufficient. Most deliverability failures at scale are architectural: many lookalike domains sending cold, all linking to one destination, through a shared tracking domain, sometimes with attachments. Filters see that pattern as one cluster and penalise all of it.

## Mechanics

1. Verify the destination domain every email links to, not only the sending domains. If it is listed, every message is filtered.
2. Use a custom tracking domain per sending domain (or per domain family), or turn click tracking off.
3. No attachments in cold email. Offer the asset on reply.
4. Measure placement with seed tests before and after any fix. Opens are not a placement metric.
5. Fix placement before changing copy or targeting.

## Where sources agree

| Claim | Sources | Confidence |
|---|---|---|
| Placement must be measured, not assumed | 4 | `high` |
| Shared tracking domains hurt reputation | 3 | `high` |

## Where sources disagree

| Position A | Position B | Cheapest test |
|---|---|---|
| Many cheap domains, low volume each | Fewer, aged, on-brand domains | Seed test both families for two weeks |

## Applies to us?

[[P0-outbound-performance]] has no placement test on record. Until one exists, every copy conclusion is provisional.

## Gaps

- No source gives placement benchmarks by mailbox provider for our segment.
- No source quantifies the reply-rate effect of removing tracking.
