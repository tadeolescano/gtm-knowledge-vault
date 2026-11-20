---
level: P0
type: evidence
area: outbound
systems: ["CRM", "sequencer"]
pulled: 2026-01-12
refresh: weekly
example: "FICTIONAL. Acme Analytics is invented; all figures are illustrative."
---

# P0 · Outbound performance (Acme Analytics, fictional)

## Headline facts

| Claim | Provenance | Source | As of |
|---|---|---|---|
| Signal-led lists (competitor followers, new-leader hires) booked roughly twice as many meetings per 1,000 sends as broad firmographic lists | `verified` | Sequencer campaign export joined to CRM meetings | 2026-01-12 |
| Doubling send volume year over year lowered the reply rate | `verified` | Sequencer, yearly totals | 2026-01-12 |
| "Our reply rate is about 1%" | `reported` | Said by the sales lead on an internal call | 2025-12-03 |
| The measured reply rate is less than half the figure circulating internally | `inferred` | Comparison of the two rows above | 2026-01-12 |
| Acme has a hit-rate problem, not a volume problem | `inferred` | Rows 1, 2 | 2026-01-12 |

## By audience lane (illustrative)

| Lane | Bookings per 1k sends | Index vs broad |
|---|---|---|
| Competitor / follower signal | 0.6 | 2.0x |
| Leadership-hire signal | 0.45 | 1.5x |
| Broad firmographic | 0.3 | 1.0x |

## Confounds

- One rep ran every booked call. Rep effect cannot be separated from message effect.
- Lane labels come from campaign names, not from a clean experiment.

## Gaps

- No conversion data from meeting to closed-won by lane yet.
- No inbox-placement test on record. Deliverability is unverified.
