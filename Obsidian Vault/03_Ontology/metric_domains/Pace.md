# Pace

Type: Metric Domain

Description:
Metrics that describe the speed and spatial characteristics of walking. Pace metrics are the most commonly reported outcomes in clinical gait studies.

Clinical significance:
Walking speed is one of the strongest predictors of health outcomes in older adults and neurological populations. Pace metrics are sensitive to disease severity and treatment response.

Metrics in this domain:
- [[Stride Velocity]]
- [[Stride Length]]

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
