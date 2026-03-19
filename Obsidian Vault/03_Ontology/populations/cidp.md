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
