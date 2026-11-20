---
level: P0
type: readme
---

# P0 · First-party evidence

P0 is what happened in **your** systems: CRM, sequencer, LinkedIn tool, call recorder, billing. It is the only layer that knows your market, your list and your message.

## The precedence rule

Where P0 contradicts an L1 conclusion, **P0 wins**. Log it in [[P0-conflicts-with-L1]].

## Provenance tags

| Tag | Use when | Write it as |
|---|---|---|
| `verified` | Pulled from a system of record, on a stated date, with stated filters | "`verified` 2026-01-12, CRM deals report, Q4 cohort: ..." |
| `reported` | A person said it on a recorded call | "`reported` the prospect's VP said..." |
| `inferred` | Our reasoning over verified facts | "`inferred` this suggests..." |

## What belongs here

- Outbound volume, replies, meetings, by segment, geo, campaign and copy angle
- Pipeline by stage and source, win/loss with reasons
- Call findings: objections, stall patterns, what prospects said they care about
- Contradictions in how the team describes the product, pricing or proof

## What does not

- Contact lists or any personal data
- Raw call transcripts with names (summarise and anonymise)
- Credentials, ever

## Maintenance

P0 goes stale continuously. Schedule a refresh (weekly works) that re-queries the systems and writes only what changed to [[99-meta/changelog]]. The refresh never edits analysis; a human does.
