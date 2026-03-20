# Parkinson's Disease

Type: Population

Description:
A progressive neurodegenerative disorder characterized by dopaminergic cell loss in the substantia nigra. Motor symptoms include tremor, rigidity, bradykinesia, and postural instability. Gait is commonly impaired with reduced stride length, velocity, and cadence, along with increased variability and freezing of gait in later stages.

Clinical scales:
- [[HY]]
- [[UPDRS]]

Commonly studied activities:
- [[Straight-line walking]]
- [[Turning]]
- [[Dual-task Walking]]
- [[Stairs Up]]
- [[Stairs Down]]

Relevant gait metrics:
- [[Stride Velocity]]
- [[Stride Time]]
- [[Stride Length]]
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

const refData = dv.pages('"04_Reference_Data"')
    .where(p => p.file.outlinks.some(l => l.path === path));

papers.length > 0
    ? dv.table(["Paper", "Year", "Status"], papers.map(p => [p.file.link, p.year, p.status]))
    : dv.paragraph("_No papers indexed yet._");

if (insights.length > 0) {
    dv.header(4, "Insights");
    dv.list(insights.map(p => p.file.link));
}

if (refData.length > 0) {
    dv.header(4, "Reference Data");
    dv.list(refData.map(p => p.file.link));
}
```
