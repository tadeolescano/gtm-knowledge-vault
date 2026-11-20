# Build order

```
sources -> vault -> skills -> workflows -> agents
```

| Phase | Do | Deliverable | Review |
|---|---|---|---|
| 0 | Infrastructure: private repo, secrets in `.env`, a deploy target that holds no customer data | Access confirmed | Owner |
| 1 | Source list per GTM domain, filtered for credibility | `99-meta/source-master-list` | Owner reviews before harvesting; bad sources poison everything downstream |
| 2 | Harvest raw captures | `L3-sources/_raw/` + ingestion log | Spot check |
| 3 | Write P0, then distill L3 into L2/L1, then reconcile | P0 notes, L1, L2, conflict register | Decision makers |
| 4 | Score opportunities | `40-opportunities/prioritized-list` | Decision session; do not leave without a metric per play |
| 5 | Build skills for the agreed plays | `50-skills/` specs + tuning logs | Output quality on real inputs |
| 6 | Run workflows by hand | `60-workflows/` run logs | Three clean runs |
| 7 | Agents | `70-agents/` profiles | Objective met, gaps declined |
| 8 | Continuous intelligence loop | Proposals queue | Human approves every vault change |

## Things that are easy to forget

- **Baseline first.** Record reply rate, meeting rate, cost per meeting and stage conversion before changing anything. Without it you cannot prove the new engine beats the old one.
- **Recency weighting.** Outbound and paid tactics decay in months.
- **Mine your own history before importing anyone else's.** Emails that already booked meetings are proprietary evidence.
- **Contradictions are surfaced, not blended.**
- **Deliverability caps everything.** Volume is bounded by domain and mailbox health.
- **Sales capacity is the real ceiling.** Booking more meetings than the team can run well makes the numbers worse.
- **Definition of done per phase.** Review the deliverable, not the progress narrative.
