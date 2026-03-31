
# Unified Parkinson's Disease Rating Scale (UPDRS)

Type: Clinical Measure

Purpose:
Considered the gold standard in rating the disease severity (signs and symptoms) and monitoring the response to medications in people with Parkinson's disease. The test comprises of six segments: 1) Mentation, Behavior, and Mood, 2) ADL, 3) Motor sections, 4)  Complications of Therapy (in the past week) 5) Modified [[HY]], and 6) Schwab and England ADL scale. The first four segments are made up of 42 items grouped into four subscales. The UPDRS was developed in 1987 as a gold standard by neurologists for monitoring the response to medications used to decrease the signs and symptoms of Parkinson's.

Administration:
clinician-administered

Score range:
Parts 1 to 3 are scored on a 0-4 rating scale.
Part 4 is scored with yes and no ratings.
Then the administrator rates the patient on  the H and Y Scale and the Schwab and England Activities of Daily Living Scale.

Interpretation:
- Higher scores indicate: increase in disability
- Lower scores indicate: decrease in disability

Equation:
<!-- Delete if not applicable -->
$$

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
