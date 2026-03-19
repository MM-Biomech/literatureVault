# Variability

Type: Metric Domain

Description:
Metrics that describe the degree of step-to-step or stride-to-stride fluctuation in gait parameters. High variability reflects reduced automaticity of walking and greater cognitive-motor demand.

Clinical significance:
Gait variability is a sensitive marker of fall risk and neurological decline. It is often elevated before changes in mean pace become detectable, making it useful for early detection of impairment.

Metrics in this domain:
- [[Stride Time Variability]]
- [[Stride Length Variability]]

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
