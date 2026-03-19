# Symmetry Index (SI)

Type: Metric

Definition:
A percentage measure of asymmetry between left and right limb performance on a given spatiotemporal parameter.

Equation:
$$
SI = \frac{|X_L - X_R|}{0.5 \times (X_L + X_R)} \times 100\%
$$

Domain: [[Asymmetry]]

Unit: % (unitless percentage)

Interpretation:
- 0% = perfect symmetry
- Higher values indicate greater asymmetry between limbs
- Note: SI has known reliability limitations in healthy adults. See [[Symmetry Ratio]] for a more reliable alternative.

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
