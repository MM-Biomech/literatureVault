
# Clinical Global Impressions scale (CGI)

Type: Clinical Measure

Purpose:
Measurement of clinical change used across many diseases. Assesses the patient's functioning prior to and after initiating medication in trials.
Comes in different variants Severity of illness: (CGI-S); Global Improvement (CGI-I); Efficacy index (CGI-E).

Administration:
clinician-administered

Score range:
"Considering your total clinical experience with this particular population, how ill is the patient at this time?" 
1. Normal, not at all ill
2. Borderline mentally ill
3. Mildly ill
4. Moderately ill
5. Markedly ill
6. Severely ill
7. Among the most extremely ill patients

Interpretation:
- Higher scores indicate: More ill than typical
- Lower scores indicate: Less ill than typical


Relevant populations:
- [[Parkinson's Disease]] used in TOH study
- Not disease dependent

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
