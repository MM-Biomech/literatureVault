# CIDP

Type: Population

Description:
Chronic inflammatory demyelinating polyneuropathy. A peripheral nerve disorder causing progressive motor and sensory deficits. Gait is commonly affected due to distal weakness and sensory loss.

Clinical scales:
- [[I-RODS]]
- [[INCAT]]

Commonly studied activities:
- [[Straight-line walking]]

Relevant gait metrics:
- [[Stride Velocity]]
- [[Stride Time]]

Notes:


---

## Referenced In

```dataviewjs
const path = dv.current().file.path;
const currentTitle = dv.current().file.name;

const papers = dv.pages('"01_Papers"')
    .where(p => p.file.outlinks.some(l => l.path === path))
    .sort(p => p.year, 'desc');
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
