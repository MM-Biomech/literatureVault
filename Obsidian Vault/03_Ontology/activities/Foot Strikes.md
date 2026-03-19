# Foot Strikes

Type: Activity
<!-- Sub-event of walking; used as an ontology node for gait event detection references -->

Description:
The moment the foot first makes contact with the floor during the gait cycle. Can occur as a [[Heel Strike]], [[Midfoot Strike]], or [[Forefoot Strike]] depending on footwear, speed, and neurological status.

Common populations studied:
- [[Healthy Adults]]
- [[Foot Drop]]

Common metrics:
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
