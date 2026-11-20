# Tag taxonomy

## Provenance (P0)

| Tag | Definition | Quotable as finding |
|---|---|---|
| `verified` | Pulled from a system of record, with date and filters | Yes |
| `reported` | Said by a person on a recorded call | Only as attributed speech |
| `inferred` | Our reasoning over verified facts | No |

## Confidence (L1, L2)

| Tag | Definition |
|---|---|
| `high` | Three or more unconnected operators, or verifiable numbers |
| `medium` | One credible operator with evidence |
| `hypothesis` | No evidence, or the speaker sells the solution |

## Source verdict (L3)

| Tag | Definition |
|---|---|
| `signal` | Operator describing their own operation, little or no selling |
| `partial` | Usable mechanics wrapped in a pitch, or claims without evidence |
| `discard` | Kept only in the discard log with a reason |

## Lifecycle

| Tag | Use |
|---|---|
| `needs-revalidation` | Tactic or source older than 12 months |
| `overturned` | L1 conclusion contradicted by P0 |
| `qualified` | L1 conclusion holds only partly for us |

## Conclusion IDs

`C-MKT-NN` marketing · `C-SAL-NN` sales and outbound · `C-PMM-NN` product marketing · `C-AUT-NN` automation. IDs are never reused.
