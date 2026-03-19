# Healthy Adults

Type: Population

Description:
Neurologically and orthopaedically intact adults without known gait-affecting conditions. Used as normative controls in clinical gait studies.

Clinical scales:

Commonly studied activities:
- [[Straight-line walking]]
- [[Turning]]
- [[Dual-task Walking]]
- [[Stairs Up]]
- [[Stairs Down]]

Relevant gait metrics:
- [[Stride Velocity]]
- [[Stride Time]]
- [[Turn Duration]]

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
