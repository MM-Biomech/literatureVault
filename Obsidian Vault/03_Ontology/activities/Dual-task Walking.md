# Dual-task Walking

Type: Activity

Description:
Walking while simultaneously performing a secondary cognitive or motor task. Used to assess gait under ecologically valid conditions and to quantify the cognitive-motor interference effect.

Common secondary tasks:
- Carrying a full cup of water (manual)
- Counting backwards (cognitive)
- Verbal fluency tasks (cognitive)
- [[Stroop Word Test]] (cognitive)

Common populations studied:
- [[Healthy Adults]]
- [[Parkinsons Disease]]
- [[Multiple Sclerosis]]

Common metrics:
- [[Dual Task Effect]]
- [[Stride Velocity]]
- [[Stride Length]]
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
