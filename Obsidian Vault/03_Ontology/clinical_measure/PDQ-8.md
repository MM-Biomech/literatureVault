
# PDQ-8

Type: Clinical Measure

Purpose:
To assess the quality of life of people with Parkinson's disease across 8 domains: mobility, activities of daily of living, emotional well-being, stigma, social support, cognition, communication, and bodily discomfort.
This is the shorter version of the [[PDQ-39]]

Administration:
self-report

Score range:
0 - 32

Interpretation:
- Higher scores indicate: poor health outcomes
- Lower scores indicate: better health outcomes

Equation:
Due to having Parkinson’s disease, how often during the last month have you…

1. Had difficulty getting around in public?
2. Had difficulty dressing yourself?
3. Felt depressed?
4. Had problems with your close personal relationships?
5. Had problems with your concentration, e.g. when reading or watching TV?
6. Felt unable to communicate with people properly?
7. Had painful muscle cramps or spasms?
8. Felt embarrassed in public due to having Parkinson’s disease?
  
Each question is scored between 0 and 4 as follows:

- Never = 0
- Occasionally = 1
- Sometimes = 2
- Often = 3
- Always or cannot do at all = 4
$$
Sum(Responses)
$$

MDC:
MCID:
<!-- Delete fields above if not reported or not applicable -->

Relevant populations:
- [[Parkinson's Disease]]

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
