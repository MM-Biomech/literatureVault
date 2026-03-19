# Multiple Sclerosis

Type: Population

Description:
A chronic autoimmune demyelinating disease of the central nervous system. Gait impairment is one of the most common and disabling symptoms, including reduced walking speed, increased variability, and asymmetry. Severity varies widely across individuals and disease subtypes.

Clinical scales:
- [[EDSS]]
- [[MSWS12]]
- [[T25FW]]
- [[9HPT]]
- [[SDMT]]

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
const currentTitle = dv.current().file.name;
const insights = dv.pages('"02_Insights"')
    .where(p =>
        p.file.outlinks.some(l => l.path === path) ||
        [p.population, p.activity, p.metric, p.method, p.domain, p.property]
            .flat()
            .some(v => String(v ?? '').toLowerCase() === currentTitle.toLowerCase())
    );

papers.length > 0
    ? dv.table(["Paper", "Year", "Status"], papers.map(p => [p.file.link, p.year, p.status]))
    : dv.paragraph("_No papers indexed yet._");

if (insights.length > 0) {
    dv.header(4, "Insights");
    dv.list(insights.map(p => p.file.link));
}
```
