---
level: P0
type: evidence
area: "{{outbound | pipeline | customers | calls | positioning}}"
systems: ["{{CRM}}", "{{sequencer}}"]
pulled: {{date}}
refresh: "{{weekly | monthly | manual}}"
owner: "{{name}}"
---

# P0 · {{title}}

> Precedence: where this note contradicts an L1 conclusion, this note wins. Log the conflict in [[P0-conflicts-with-L1]].

## Headline facts

| Claim | Provenance | Source system | As of |
|---|---|---|---|
| {{claim}} | `verified` | {{system / report name}} | {{date}} |
| {{claim}} | `reported` | {{call, speaker role}} | {{date}} |
| {{claim}} | `inferred` | reasoning over the rows above | {{date}} |

## Detail

{{Tables, cuts by segment, method notes. State filters and date ranges explicitly.}}

## Confounds

{{What could make these numbers misleading: single rep, small sample, attribution gaps, manual exports.}}

## Gaps

{{What this note cannot answer and what it would take to answer it.}}
