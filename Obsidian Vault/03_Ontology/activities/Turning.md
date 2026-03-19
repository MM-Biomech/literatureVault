# Turning

Type: Activity

Description:
A 180° change in walking direction. Turning is a high-demand motor task requiring coordination of stepping, trunk rotation, and balance. Impaired in many neurological conditions.

Common populations studied:
- [[Healthy Adults]]
- [[Multiple Sclerosis]]
- [[Parkinsons Disease]]

Common metrics:
- [[Turn Duration]]
- [[Turn Velocity]]
- [[Turn Angle]]

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
