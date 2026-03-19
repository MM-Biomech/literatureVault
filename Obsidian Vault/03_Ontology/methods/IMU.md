
# IMU

Type: Measurement Method

Description:
A wearable device that contains at least two of: Accelerometer, Gyroscope, and Magnetometer. Can be used on its own as a single sensor or with multiple other IMUs placed on other locations on the body.
Sometimes calibrated to a biomechanical model to calculate joint angles.

Key specifications:
- Sampling rate:
- Sensor type:

Common uses:
- [[Gait Event Detection]]
- [[Segment Orientation]]
- [[Activity Recognition]]

Compared to:
- [[Motion Capture]]

Limitations:
- 

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
