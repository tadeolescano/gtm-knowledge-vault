# GTM Knowledge Vault

An Obsidian vault template for building go-to-market AI agents on top of evidence instead of on top of a model's generic training data.

Patterns I built and ran in production at an AI startup, rewritten as a reusable template with fictional examples.

---

## The problem

Ask any large language model how to write cold email, structure a sales process or price a product, and you get competent, average advice drawn from the same public corpus everyone else is using. Run that advice through an agent at volume and you do not get a better GTM motion. You get the market average, multiplied.

Most "AI SDR" and "GTM agent" builds skip three things:

1. **Your own data.** What actually happened in your CRM, your sequencer and your sales calls outranks any external best practice, and no model has it.
2. **Provenance.** "Measured in the CRM", "someone said it on a call" and "we reasoned it" are three different kinds of truth. An agent that blends them will state a guess with the same confidence as a fact.
3. **Permission to say "I don't know".** Without explicit gaps, an agent fills every hole with something plausible.

This vault is the layer that fixes those three things before anyone writes an agent.

## How it works

### 1. The build order

```
sources  ->  vault  ->  skills  ->  workflows  ->  agents
```

| Step | Deliverable | Exit criterion |
|---|---|---|
| Sources | A credibility-filtered list of operators and publications per GTM domain | Every source passes the filter in [`99-meta/source-credibility-filter.md`](99-meta/source-credibility-filter.md) |
| Vault | P0 evidence plus L1/L2/L3 market knowledge, tagged and linked | An agent can answer a GTM question and cite where the answer came from |
| Skills | Single-purpose, tuned units (account research, copy drafting, campaign QA...) | Output is good on real inputs, not demo inputs |
| Workflows | A play run end to end by hand, with the skills, human in the loop | It completes cleanly several times in a row |
| Agents | A role, a set of tuned skills, an objective and a proven workflow | It does the workflow without supervision and declines when the vault has a gap |

Nothing is automated until the workflow behind it works by hand. A skill that is right 70% of the time breaks an agent chain silently.

### 2. The evidence ladder

| Level | Holds | Read it when |
|---|---|---|
| **P0** | First-party evidence from your systems of record and your recorded calls | **Always first.** Where it contradicts a market conclusion, P0 wins |
| **L1** | Conclusions, one or two lines each, with stable IDs (`C-SAL-04`) | "What do we know?" |
| **L2** | Topics: the reasoning, numbers and quotes behind each conclusion | "How do we know it?" |
| **L3** | Source notes: one per video, article or episode, with excerpts | "Who said it, and exactly what?" |

Agents traverse top-down and never skip a level: P0, then L1, then L2 only if L1 is not enough, then L3 only to verify a quote.

### 3. Two tag systems, on purpose

**Provenance tags (P0 only)** describe *where a fact came from*:

| Tag | Meaning | Can an agent quote it as a finding? |
|---|---|---|
| `verified` | Pulled from a system of record on a stated date | Yes, with the date |
| `reported` | A person said it on a recorded call. True that it was said, not that it is true | Only as "X said..." |
| `inferred` | Our reasoning over verified facts | Never as a finding |

**Confidence tags (L1/L2)** describe *how much independent agreement exists*:

| Tag | Meaning |
|---|---|
| `high` | Three or more unconnected operators reached it, or there are verifiable numbers |
| `medium` | One credible operator with evidence, no independent confirmation |
| `hypothesis` | Asserted without evidence, or the person asserting it sells the solution. Testable |

### 4. Gap sections

Every L2 topic ends with a `## Gaps` section. The vault router lists known gaps, and the agent instructions say: if a query lands on a gap, say so, do not improvise. This is the single most important behaviour the vault encodes.

### 5. The precedence rule and the conflict register

When your own evidence contradicts a market conclusion, P0 wins. No averaging, no "both can be true". Every overturned or qualified conclusion is logged in `P0-evidence/P0-conflicts-with-L1.md`, and agents check that register before using any L1 conclusion.

## Structure

```
gtm-knowledge-vault/
├── AGENTS.md                  # operating instructions for any LLM working in the vault
├── 00-INDEX.md                # router: every query starts here
├── 00-BRIEF.md                # why the vault exists, what it is not, how you will know it worked
├── P0-evidence/               # first-party evidence (your CRM, sequencer, calls)
├── L1-conclusions/            # one file per GTM area, conclusions with stable IDs
├── L2-topics/                 # reasoning per topic, always ends with Gaps
├── L3-sources/                # one note per source; _raw/ holds untouched captures
├── 40-opportunities/          # scored, prioritized plays with a metric and a kill condition
├── 50-skills/                 # skill specs: one job, inputs, outputs, tuning log
├── 60-workflows/              # manual run logs of plays before they are automated
├── 70-agents/                 # agent role catalog and agent profiles
├── 99-meta/                   # build order, tag taxonomy, source filter, changelog
└── templates/                 # Obsidian templates for every note type
```

The example notes describe **Acme Analytics**, a fictional B2B SaaS company. Every company, person and number in them is invented to show the format.

## How to use it

1. **Clone and open as a vault.** `git clone` the repo and open the folder in [Obsidian](https://obsidian.md). Enable the core Templates plugin and point it at `templates/`. The Dataview community plugin is optional; the dashboard queries in `99-meta` use it.
2. **Delete the Acme examples** once you have read them, or keep them in a branch as reference.
3. **Write the brief first.** Fill `00-BRIEF.md`: what the agents are for, and what would prove the vault worked. If you cannot write this, you are not ready to build agents.
4. **Build P0 before L1.** Pull your own outbound, pipeline and call data into `P0-evidence/` using `templates/P0-evidence-note.md`. Tag every claim `verified`, `reported` or `inferred`. This is the highest-value hour in the whole project; do not delegate it.
5. **Build the source list.** Use `99-meta/source-credibility-filter.md`. Fewer, better sources beat a long list.
6. **Harvest into `L3-sources/_raw/`, then distill.** Collection and judgment are separate passes. Raw captures are never edited.
7. **Write L2 topics and L1 conclusions.** Deduplicate (five people describing one play is one note with five sources). Flag contradictions instead of blending them.
8. **Reconcile against P0.** Log every overturned or qualified conclusion in the conflict register.
9. **Score opportunities.** Each one gets a measurable hypothesis, a metric and a kill condition.
10. **Only then** write skill specs, run workflows by hand, and promote proven workflows to agents.
11. **Point your agent at `AGENTS.md`.** Works with any coding or chat assistant that can read a folder of Markdown.

## What this is not

- **Not a content library.** Nobody is meant to read it end to end. It is a retrieval structure for agents and for people making decisions.
- **Not a substitute for talking to customers.** Market sources are strangers theorising. Customer interviews belong in P0, and their absence is usually the biggest gap.
- **Not finished knowledge.** Expect your own evidence to overturn some market conclusions. That is the vault working, not failing.
- **Not a decision engine.** It makes decisions cheaper to take and easier to defend. It does not take them.
- **Not an agent framework.** No orchestration code here. The vault is what agents read; how you run them is up to you.

## Security and data boundaries

- Never commit API keys. Use a local `.env` and keep it in `.gitignore` from the first commit.
- Keep customer personal data out of the vault. Aggregate numbers and anonymised patterns, yes. Contact lists, no.
- If your P0 contains anything confidential, keep the vault private and publish only the template.

## License

MIT. See [LICENSE](LICENSE).

---

Built by Tadeo Lescano, GTM Engineer. [LinkedIn](https://www.linkedin.com/in/tadeo-lescano/) · [GitHub](https://github.com/tadeolescano)
