# Rhythm

Type: Metric Domain

Description:
Metrics that describe the temporal regularity and timing of the gait cycle. Rhythm metrics capture how consistently and quickly steps are taken.

Clinical significance:
Rhythm disruption is commonly observed in neurological populations. Reduced cadence and irregular stride timing are early indicators of motor control impairment in Parkinson's disease, MS, and other conditions.

Metrics in this domain:
- [[Stride Time]]
- [[Cadence]]

---

## Referenced In

```dataviewjs
const path = dv.current().file.path;
const papers = dv.pages('"01_Papers"')
    .where(p => p.file.outlinks.some(l => l.path === path))
    .sort(p => p.year, 'desc');
const insights = dv.pages('"02_Insights"')
    .where(p => p.file.outlinks.some(l => l.path === path));

papers.length > 0
    ? dv.table(["Paper", "Year", "Status"], papers.map(p => [p.file.link, p.year, p.status]))
    : dv.paragraph("_No papers indexed yet._");

if (insights.length > 0) {
    dv.header(4, "Insights");
    dv.list(insights.map(p => p.file.link));
}
```
