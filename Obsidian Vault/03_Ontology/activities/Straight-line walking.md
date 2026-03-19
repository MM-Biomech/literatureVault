# Straight-line Walking

Type: Activity

Description:
Walking in a straight path at a self-selected comfortable pace. The most common gait assessment protocol. Typically performed over a defined distance (e.g. 10 m) or time (e.g. 2 min).

Common populations studied:
- [[Healthy Adults]]
- [[Multiple Sclerosis]]
- [[Parkinsons Disease]]
- [[CIDP]]

Common metrics:
- [[Stride Velocity]]
- [[Stride Time]]
- [[Stride Length]]
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
