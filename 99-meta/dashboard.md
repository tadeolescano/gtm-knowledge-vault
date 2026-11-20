# Dashboard

Requires the Dataview community plugin.

## Conclusions by confidence

```dataview
TABLE confidence, file.folder
FROM "L1-conclusions"
```

## P0 notes by freshness

```dataview
TABLE pulled, refresh
FROM "P0-evidence"
WHERE type = "evidence"
SORT pulled ASC
```

## L3 sources by verdict

```dataview
TABLE verdict, published, domain
FROM "L3-sources"
WHERE type = "source"
SORT published DESC
```

## Opportunities

```dataview
TABLE status, fit, effort, confidence
FROM "40-opportunities"
WHERE type = "opportunity"
```
