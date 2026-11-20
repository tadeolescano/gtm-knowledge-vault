---
level: 0
type: router
purpose: "Single entry point. Every query starts here."
updated: 2026-01-15
---

# INDEX · Vault entry point

> Example content describes **Acme Analytics**, a fictional company. Replace it with your own.

## Levels

| Level | Holds | When to use it |
|---|---|---|
| **P0** | Our own evidence: our numbers, our customers, our calls | **Read first, always** |
| **L1** | Conclusions, one or two lines each | "What do we know?" |
| **L2** | Reasoning behind each conclusion | "How do we know it?" |
| **L3** | Source notes with excerpts | "Who said it, exactly?" |

## Routing by area

| If the query is about | Go to |
|---|---|
| Why this vault exists | [[00-BRIEF]] |
| Whether an L1 conclusion still holds for us | **[[P0-conflicts-with-L1]]** |
| Our outbound performance, deliverability, campaigns | **[[P0-outbound-performance]]** |
| Our won and lost deals, segments, loss reasons | **[[P0-customers-and-deals]]** |
| Outbound, cold email, lists, sales process | [[L1-sales]] |
| Positioning, content, paid, demand creation | [[L1-marketing]] |
| Building agents and GTM automation | [[L2-ai-gtm-automation]] |
| What to build next | [[40-opportunities/prioritized-list]] |
| Which agent does what | [[70-agents/agent-role-catalog]] |

## Confidence and provenance

- L1/L2 confidence: `high` · `medium` · `hypothesis`
- P0 provenance: `verified` · `reported` · `inferred`
- Full definitions: [[99-meta/tag-taxonomy]]

## Known gaps

The agent says "I don't know" when a query lands here.

| Gap | Status |
|---|---|
| Why customers actually bought | No closed-won interviews in P0 yet |
| Pricing and packaging | One source, older than 12 months |
| Referral as a measurable channel | Mechanisms covered, no conversion data |
| Self-serve / PLG | No sources |
