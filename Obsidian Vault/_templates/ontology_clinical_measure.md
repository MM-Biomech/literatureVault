<%* await tp.file.move("03_Ontology/Clinical Measure/" + tp.file.title) %>
# <% tp.file.title %>

Type: Clinical Measure

Purpose:

Administration:
<!-- clinician-administered / self-report / performance-based -->

Score range:

Interpretation:
- Higher scores indicate:
- Lower scores indicate:

Equation:
<!-- Delete if not applicable -->
$$

$$

MDC:
MCID:
<!-- Delete fields above if not reported or not applicable -->

Relevant populations:
- [[]]

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
