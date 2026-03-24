---
type: insight
population: Healthy Older Adults
activity: Straight-line Walking
metric: Coefficient of Variation
domain: Variability
property: Detection
method: IMU
citekey: kroneberg2019LessMore
contested: false
---

IMU-based turn detection algorithms may fail to identify wide-radius turns that produce low horizontal acceleration, leading to undetected turn contamination in gait variability data.

Evidence:
[[kroneberg2019LessMore]] noted this as a potential limitation of their Mobility Lab turn excision approach. Wide turns — common in large clinical corridors or free-living settings — generate smaller angular velocity and horizontal acceleration signals than tight 180° turns, which may fall below the detection threshold of angular velocity-based algorithms. This is a methodologically important consideration for our lab's work in non-laboratory environments.

Reference Data:
- [[]]
