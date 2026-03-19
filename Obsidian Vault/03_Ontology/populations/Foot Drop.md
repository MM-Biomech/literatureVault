# Foot Drop

Type: Clinical Condition
<!-- Housed in populations/ because it functions as a study group label in the literature -->

Description:
Failure to dorsiflex the foot during swing phase, which may cause [[Toe Drag]], [[Foot Slap]], or [[Forefoot Strikes]]. Not a population per se, but commonly used as a study group label.

Common causes:
- [[Multiple Sclerosis]]
- [[Peripheral neuropathy]]

Clinical scales:

Commonly studied activities:
- [[Straight-line walking]]

Relevant gait metrics:
- [[Stride Velocity]]
- [[Swing Percent]]

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
