# Source credibility filter

A source qualifies only if it meets **at least three** of these:

1. Demonstrable operator track record: built or ran the programs they describe.
2. Engaged audience, not just follower count.
3. Publishes specifics: numbers, screenshots, real sequences, real campaign structures.
4. Recent output: active in the last six months.
5. Referenced by other credible operators.

**Hard exclusions:** pure info-product funnels, listicles, anything with no measurable claim.

## Domains to cover separately

- B2B outbound: deliverability, sequencing, copy, offer design
- Signal- and intent-based prospecting
- AI-automated GTM: enrichment waterfalls, agents, AI-assisted SDR work
- Paid acquisition for B2B
- LinkedIn organic and social selling
- Content and demand creation for technical buyers
- Conversion: landing pages, demo booking, product-led activation
- Unconventional plays: gifting, events, community, partner-led

## Discovery prompt (adapt)

```text
Context: [your company, category, buyer roles, regions].
Task: identify the most credible current practitioners and publications in each
of these domains: [list]. For each: name, platform, why credible (operator
evidence), what specifically they are expert in, last publication date.
Apply this filter: [paste the filter]. Exclude anything that fails and say why.
Output a markdown table grouped by domain. 8 to 15 qualified sources per domain.
```

Then run a second pass: "Who is missing from this list that a top operator in this space would name?"
