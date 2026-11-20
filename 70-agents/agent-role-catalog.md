---
type: catalog
updated: 2026-01-15
---

# Agent role catalog

Agents come last: a role, a set of tuned skills, one objective and a workflow already proven by hand. Profiles use [[templates/agent-profile]].

| Role | Job | Core skills | Priority | Gate to build |
|---|---|---|---|---|
| **Outreach** | Research accounts, prioritise by signal, draft outbound for human review | `account-research`, `contact-signal-scan`, `email-copy`, `icp-scoring` | P1 | Signal lane workflow clean x3 |
| **Housekeeping** | Reconcile call notes and CRM into one source of truth; flag stage and property violations | `attribution-reconcile` | P1 | CRM gate rules live |
| **Demand generation** | Market and competitor monitoring, creative briefs, paid campaign proposals | `source-harvest`, `performance-readout` | P1 | Readout skill stable |
| **SEO / GEO** | Track search and AI-answer visibility, propose content and page changes | `source-harvest` | P2 | Content workflow clean x3 |
| **Product marketing** | Brief the growth team on product changes and update messaging notes | none yet | P2 | Product update process defined |
| **CRO** | Analyse site behaviour, propose A/B tests with a hypothesis and a metric | `performance-readout` | P3 | Analytics baseline in P0 |

## Common rules for every agent

- Reads [[AGENTS]] and starts from [[00-INDEX]].
- Drafts, does not send, until a human has approved the workflow for autonomous runs.
- Declines on vault gaps and contested figures.
- Logs cost per run.
- The end state is an objective ("N qualified meetings per month at target cost") that an orchestrator decomposes into skills. That only works once everything below it is solid.
