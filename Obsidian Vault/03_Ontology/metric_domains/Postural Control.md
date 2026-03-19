# Postural Control

Type: Metric Domain

Description:
Metrics that reflect the ability to maintain balance and dynamic stability during walking. Postural control metrics capture the weight-bearing and stabilization phases of the gait cycle.

Clinical significance:
Postural control impairment is a major fall risk factor across neurological populations. Metrics in this domain are sensitive to dual-task conditions and disease progression.

Metrics in this domain:
- [[Double Support Time]]

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
