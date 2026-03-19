# Symmetry Ratio (SR)

Type: Metric

Definition:
The ratio of a spatiotemporal parameter between the right and left limb. Easier to interpret clinically than [[Symmetry Index]].

Equation:
$$
SR = \frac{X_R}{X_L}
$$

Domain: [[Asymmetry]]

Unit: dimensionless

Interpretation:
- 1.0 = perfect symmetry
- Values above 1.0 indicate right limb dominance; below 1.0 indicate left limb dominance
- e.g. SR = 2.0 means right-side value is twice the left

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
