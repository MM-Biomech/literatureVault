# Asymmetry

Type: Metric Domain

Description:
Metrics that quantify the difference in gait parameters between left and right limbs. Asymmetry reflects underlying neuromuscular imbalance or compensatory strategies.

Clinical significance:
Asymmetry is commonly elevated in unilateral or asymmetric neurological conditions (e.g. hemiplegia, early-stage PD). It can predict fall risk and may be a sensitive early marker of motor deterioration.

Metrics in this domain:
- [[Stride Time Asymmetry]]
- [[Symmetry Index]]
- [[Symmetry Ratio]]

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
