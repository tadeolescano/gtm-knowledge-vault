---
type: catalog
updated: 2026-01-15
---

# Skill catalog

Skills are reusable units that do one thing well. Build them only after the decision session has agreed which plays to run. Spec each one with [[templates/skill-spec]].

| Skill | Does | Reads | Status |
|---|---|---|---|
| `source-harvest` | Enumerate a source, filter by relevance and recency, write raw captures with frontmatter | `99-meta/source-credibility-filter` | spec |
| `account-research` | Research one account: signals, stack, hiring, funding, org shape | P0 ICP notes | spec |
| `contact-signal-scan` | Recent public activity and engagement for named contacts | none | spec |
| `email-copy` | Draft a sequence from the proven copy library plus distilled practice | P0 outbound, L2 sequence design | spec |
| `sequence-builder` | Multi-touch cadence with branching and exit conditions | `email-copy` output | spec |
| `icp-scoring` | Score an account against the tier model | ABM scoring config | spec |
| `campaign-qa` | Pre-send checks: placement status, personalisation integrity, list hygiene, compliance | L2 deliverability | spec |
| `attribution-reconcile` | Reconcile call notes, chat and CRM so source attribution is correct | CRM | spec |
| `performance-readout` | Weekly readout from sequencer, LinkedIn tool, CRM and web analytics | P0 | spec |

Rule: a skill that works 70% of the time breaks an agent chain silently. Tune on real inputs and log every fix.
