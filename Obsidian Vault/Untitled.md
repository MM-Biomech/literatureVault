
---
type: project
status: active
---

# project_note

## Research Question

## Populations
- [[]]

## Key Metrics
- [[]]

## Key Methods
- [[]]

---

## Relevant Insights

```dataview
TABLE population, metric, domain, property, citekey
FROM "02_Insights"
WHERE population = ""
SORT metric ASC
```

<!-- Edit the WHERE clause above to match your target population(s). -->
<!-- For multiple populations: WHERE population = "Parkinsons Disease" OR population = "Healthy Older Adults" -->

---

## Relevant Papers

```dataview
TABLE year, status
FROM "01_Papers"
WHERE contains(file.outlinks, this.file.link)
SORT year DESC
```

<!-- Link this project note from any relevant paper note's Notes section to make it appear here. -->

---

## Reference Data

| Metric | Population | Value | Source |
|--------|------------|-------|--------|
| [[]]   | [[]]       |       | [[]]   |

---

## Open Questions
- 

## Notes

