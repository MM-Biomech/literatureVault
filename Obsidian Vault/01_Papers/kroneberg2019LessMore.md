---
type: paper
citekey: kroneberg2019LessMore
title: Less Is More – Estimation of the Number of Strides Required to Assess Gait Variability in Spatially Confined Settings
year: 2019
status: processed
---
## Study Context
%% begin study-context %%
Population:
- [[Healthy Older Adults]]
- [[Parkinson's Disease]]
- [[Cerebellar Ataxia]]
- [[Essential Tremor]]

Sample Size:
 - 31 people with movement disorders
 - 172 Older adults (78 F, 70+-6.2 years)

Activity:
- [[Straight-line walking]] (10 metres and 20 metres)

Protocol:
- Movement disorder: 10 m corridor × 5 laps (50 m total, 4 turns of 180°), comfortable pace, no turn instructions
- Older Adults: 20 m corridor, back and forth for 1 min, comfortable pace, no turn instructions, pylons marking segment ends

Devices:
- [[IMU]] (Mobility Lab, APDM — 6 sensors: wrists, shanks, sternum, lower back)

Statistics:
- [[ICC]] (two-way random single measure)
- [[Pearson Correlation]]

Metrics Studied:
- [[Stride Length]]
- [[Stride Time]]
- [[Coefficient of Variation]]

Purpose / Hypothesis:

- (p. 3) explore how the magnitude of gait variability can be reliably captured in the clinical setting using a commercially available sensor-based gait analysis system.
- (p. 3) explored effects of the common practice to collect strides over several walking segments separated by 180◦ turns using an automated turn detection.

Participant Demographics:

- (p. 3) included data from a large cohort of elderly healthy (HE) subjects and data from subjects with different movement disorders (MD) known to be associated with increased gait variability, namely cerebellar ataxia (ATX), essential tremor (ET) and Parkinson's disease (PD).
- (p. 3) MD dataset) comprised 31 subjects with movement disorders associated with increased gait variability 12 Parkinson's disease (PD, age 60 ± 9), 7 cerebellar ataxia (ATX, age 58 ± 7), 12 essential tremor (ET, age 67 ± 10)
- (p. 3) HE dataset) consisted of 172 healthy elderly individuals (78 females, average age 70.1 years ± 6.2)

Methods Details:

- (p. 3) Mobility Lab R©, APDM, Portland, OR, United States) consisting of six bodyworn inertial sensors, symmetrically attached to wrists, shanks and medially placed over sternum and lower back.
- (p. 3) 10-m distance ( = segment) five times back and forth at their preferred speed without specific instructions for turning.
- (p. 3) 50 m of walking and four turns of 180◦
- (p. 3) HE study, participants walked a 20-m distance (=segment) back and forth for 1 min, also at preferred speed and without specific instructions for turning but with respective segment ends marked with pylons.
- (p. 3) At least 40 gait cycles were obtained per participant
- (p. 3) first approach, we used the algorithms for turn excision provided by the manufacturer (Mobility Lab software V1.0.0.201503302135) to export raw data. Software output settings were preset to exclude turns from analysis.
  - Note: Used proprietary turn detection and timestamped gait events
- (p. 3) stride length and stride time (=gait cycle time) and their CoVs (SD/mean)∗100 were used for further analysis
  - Note: 
- (p. 4) "generous" turn segmentation would attenuate any confounding effect of turns on stride length/time CoVs.
  - Note: They used the detected turns and excluded one extra stride on each side to see the effect. This reduced their 40 strides to 32
- (p. 5) to explore the dependency of CoVs from the number of strides recorded, we calculated individual CoVs for (a) each of the five/three (MD/HE) segments of straight 10/20 m walking between turns and (b) cumulative for each of 3–40 strides when using manufacturer's turn excision and 3–32 when applying the alternative turn segmentation.
  - Note: Iteratively increased the number of strides from 3 to 40/32
- (p. 5) two-way random single measure model was applied to compute intraclass coefficient (ICC) with segments regarded as "repeated measurements." Thus ICCs reflect to which degree  individuals maintain their results stable over the 3–5 segments of continuous walking segmented by turns. ICCs less than 0.4 were interpreted as poor, 0.4–0.8 as fair to good and more than 0.8 as excellent.
- (p. 5) Pearson's correlation coefficients were calculated for individual cumulative means/CoVs over gait cycles 3–40 (32) with the individual mean/CoV at stride 40 (32).
%% end study-context %%

---

## Results
%% begin results %%
- CoV-SL = coefficient of variation stride length
- CoV-ST = coefficient of variation stride time
- (p. 6) CoV-SL and CoV-ST were highest in the subgroup of ataxic subjects. Subgroup differences were not statistically evaluated
- (p. 6) stride length and stride time were highly consistent across the 3–5 segments (ICC > 0.90) in all groups
- (p. 6) after omission of one more stride before and after the manufacturer's turn excision, this generally decreased CoV group means while respective ICCs only partially improved and range of CoV over segments only partially decreased
- (p. 7) Pearson's correlation coefficients of cumulative means/CoVs from stride 3 through to stride 40 versus the individual mean/CoV at stride 40 were plotted against strides. We used R > 0.8
- (p. 7) stride length and stride time, very strong correlations (R > 0.9) were reached after only 3 gait cycles in all groups
- (p. 7) CoV stride length, R > 0.8 was reached at the 10th stride in ATX and PD group, but only after 20th stride in ET and 16th stride in HE.
- (p. 7) CoV stride time criterion was reached at 8th stride for ATX, 18th and 19th stride for ET and PD and 20th stride  in HE.
- (p. 7) correlation criterion indicated a number of < 10 strides as sufficient in the disease groups studied except for 16 strides for CoV stride length in ET. Estimates increased for HE (25 strides for CoV stride length and 17 for CoV stride time) possibly due to smaller total number of strides considered.
%% end results %%

---

## Key Insights Extracted
%% begin key-insights %%
- [[Proprietary turn excision algorithms can fail and artificially inflate gait variability CoV]]
- [[Walking turns elevate CoV of spatiotemporal parameters when not excluded from gait analysis]]
- [[Gait variability CoV stabilizes within 15 strides in movement disorder groups]]
- [[Turn detection algorithms may fail to identify wide-radius turns with low horizontal acceleration]]

- (p. 8) (1) algorithmic excision of turns can fail and result in misleadingly high values for gait variability and this seems to occur independent of gait dysfunction
- (p. 8) (2) we observed indeed an effect of turns on spatiotemporal stride characteristics calculated of straight walking segments inbetween turns, which resulted in increased CoV and wider confidence margins with increasing number of steps
- (p. 8) (3) despite low repeatability according to ICC, only marginal absolute changes in parameters of gait variability occur at group level between the 10th and 40th stride, indicating that the assessment of gait variability can be reliably performed using short distance walks that include less than 15 strides.
- (p. 8) there may be a limitation of such algorithms to detect turns with broader diameter and subsequently lower horizontal accelerations.
%% end key-insights %%

---

## Reference Data Extracted
%% begin reference-data %%
- [[]]
%% end reference-data %%

---

## Follow-up Citations
%% begin follow-up %%
- (p. 2) a value of 2.6% [2.3–3.1] has been proposed as a reliable upper limit for CoV stride time in physiological gait (Konig et al., 2016b).
  - Find: König 2016b — normative CoV stride time threshold in healthy gait
- (p. 3) recording more than 50 gait cycles considering only steady-state walking is commonly recommended (Konig et al., 2014a) for a reliable description of gait variability.
  - Find: König 2014a — minimum stride count recommendation for gait variability
%% end follow-up %%

---

## Notes
%% begin notes %%

%% end notes %%

%% Import Date: 2026-03-24T13:02:42.440-04:00 %%
