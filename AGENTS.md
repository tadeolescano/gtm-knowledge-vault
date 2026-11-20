# AGENTS.md · How an AI assistant works in this vault

Read this file in full before answering any question or editing any note.

## Retrieval procedure

0. Open [[00-INDEX]]. It routes every query.
1. Check [[P0-conflicts-with-L1]] before using any L1 conclusion. Our own evidence overturns some market conclusions and qualifies others.
2. If the query touches **our** numbers, customers, pricing, list, copy or calls, the answer is in `P0-evidence/` and nowhere else. If P0 has no answer, say so. Do not substitute a market conclusion.
3. Otherwise read the relevant L1 file. If the conclusion is sufficient, answer and cite its ID (for example `C-SAL-04`).
4. If not sufficient, follow the conclusion's `Go deeper` link to L2.
5. If L2 is not sufficient, follow its `Source` link to L3. Check the L3 note before quoting anything verbatim.
6. Always cite the conclusion ID or P0 note, and the provenance or confidence tag.

## Hard rules

- **Never present a `hypothesis` as a finding.** Say "one operator claims..." or "untested".
- **Never quote an `inferred` P0 fact as a finding.** It is our reasoning, label it as such.
- **`reported` means someone said it.** Write "the prospect said..." not "the prospect has...".
- **Precedence:** where P0 contradicts L1, P0 wins. No averaging.
- **Gaps are answers.** If a query lands on a `## Gaps` section or a gap listed in [[00-INDEX]], reply "the vault does not know" and name the cheapest way to find out.
- **Never pick a winner in a contradiction between sources.** Present both positions and the test that would settle it.
- **Do not edit `L3-sources/_raw/`.** Raw captures are immutable.

## Writing rules

- New notes start from a file in `templates/`. Keep the frontmatter complete.
- One idea per L1 conclusion. Stable IDs: `C-<AREA>-<NN>` where AREA is `MKT`, `SAL`, `PMM` or `AUT`. Never reuse a retired ID.
- Every L2 topic ends with `## Gaps`.
- Every P0 claim carries `verified`, `reported` or `inferred`, plus a date and the system it came from.
- Log every structural change in [[99-meta/changelog]].

## Source filter (apply to any new material)

1. **Follow the money.** If the central thesis is what the speaker sells, keep the mechanics, discard the thesis.
2. **Check the promised evidence.** Claims of data with no data shown are a tell.
3. **Count independent arrivals.** Two people from one company are one source.
4. **Recency.** Tactics older than 12 months are marked `needs-revalidation`.

## When asked to build something

Respect the build order in [[99-meta/build-order]]. If asked to automate a workflow that has no successful manual run logged in `60-workflows/`, say so and propose the manual run first.
