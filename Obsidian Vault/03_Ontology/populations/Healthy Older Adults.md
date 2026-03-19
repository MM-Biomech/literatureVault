# Healthy Older Adults

Type: Population

Description:
Neurologically and orthopaedically intact adults typically aged 65 and older. Distinguished from [[Healthy Adults]] because age-related gait changes (reduced speed, increased double support time, greater variability) produce meaningfully different normative values. Used as age-matched controls when studying older neurological populations such as early-stage Parkinson's disease.

Clinical scales:

Commonly studied activities:
- [[Straight-line walking]]
- [[Turning]]
- [[Dual-task Walking]]

Relevant gait metrics:
- [[Stride Velocity]]
- [[Stride Time]]
- [[Cadence]]

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
