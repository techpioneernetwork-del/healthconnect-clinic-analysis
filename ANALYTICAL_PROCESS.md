# Analytical Process — HealthConnect No-Show Analysis

**Data Analytics Track · AnalystLab Africa HealthConnect Experience Lab**
Oluwatosin Olusanya, Data Analyst

This document walks through the analytical process from initial exploration (Week 5) to the final validated decision-support package (Week 8).

## 1. Problem Framing (Week 4)

HealthConnect Clinic needed to understand and reduce missed appointments, make better use of appointment slots, and improve administrative support. The Data Analytics track's role was to quantify the scale of the no-show problem and identify its drivers using the approved dataset (`HealthConnect_Appointment_Data.csv`) and data dictionary.

## 2. Initial Analysis (Week 5)

- Calculated the overall no-show rate and 4 supporting KPIs.
- Produced 6 exploratory charts covering appointment outcomes, lead time, prior no-show history, reminder effectiveness, and time trends.
- Derived 5 initial business insights and 4 recommendations from the raw patterns observed.

**Method:** descriptive statistics and rate comparisons across candidate driver variables (booking lead time, prior no-show count, appointment type, day of week, reminder channel).

## 3. Integration & Validation (Week 6)

- Statistically validated the two strongest candidate drivers using **chi-square tests of independence**:
  - Booking lead time vs. no-show outcome: χ²=340.42, p<0.001
  - Prior no-show count vs. no-show outcome: χ²=72.36, p<0.001
- Shared these validated findings with the Project Management track, which logged the integration and used it to shape Week 7 testing priorities.
- Refined the reminder-effectiveness analysis by risk segment rather than treating it as a single flat effect.

## 4. Testing & Refinement (Week 7)

- **Independent re-derivation**: recalculated all 5 core KPIs and both chi-square tests directly from the raw dataset. Every figure reproduced exactly — confirming zero calculation errors in the pipeline.
- **Interaction testing**: tested whether lead time and prior no-show history interact (synergistic) or combine independently (additive). Result: additive, not synergistic (p=0.50) — each factor can be addressed as a separate lever.
- **Sensitivity testing**: re-ran headline calculations under an alternative treatment of "Cancelled" appointments. Rates shifted 2–5 points, but the underlying pattern held.
- **Segment-stability testing**: confirmed the lead-time effect holds across gender and all age groups, though it is measurably weaker for patients under 25 and over 65.
- **Hypothesis testing on an external claim**: a claim from an earlier AI-assisted draft — that reminders were sent disproportionately to lower-risk patients — was tested directly and found false (send rates 71.6–74.3% across all risk segments, essentially flat). This was documented as a failed test rather than dropped.

## 5. Final Integration & Decision Support (Week 8)

- Combined the two validated drivers into a single **risk-segmentation matrix**, isolating a highest-risk group of 1,529 appointments (1,035 patients) at 63.6% no-show, versus 28.0% in the lowest-risk group (715 appointments).
- Translated validated findings into **actionable recommendations** (targeted confirmation calls, a shorter default booking window, differentiated outreach for under-25/over-65 patients, SMS-prioritized reminders, a standing quarterly review).
- Finalized the executive summary, dashboard/report, and presentation slide deck.
- Documented cross-track handoffs to Data Science (validated features + risk-segment flag) and Project Management (sized target segment for staffing).

## Key Methodological Decisions

| Decision | Rationale |
|---|---|
| Chi-square test of independence for categorical drivers | Both lead time and prior no-show count are naturally bucketed; chi-square tests whether the no-show rate differs across buckets more than chance would predict |
| Excluded "Cancelled" from headline no-show rate | Cancellations are a distinct outcome from silent no-shows; sensitivity-tested this choice in Week 7 and found it did not materially change conclusions |
| Row-wise exclusion for missing `distance_to_clinic_km` (1.8%) and `waiting_time_minutes` (1.2%) | Missingness was small and unrelated to the core KPIs; excluding affected rows only from calculations using those specific fields avoided biasing the headline metrics |
| Additive (not multiplicative) combination of the two risk factors | Confirmed via interaction test (p=0.50) rather than assumed |

## Limitations

- **Associational, not causal**: the analysis identifies strong, statistically validated, segment-stable patterns, but does not by itself prove that intervening on lead time will reduce no-shows by a proportional amount.
- **Missing data**: small amounts of missing data in `distance_to_clinic_km` and `waiting_time_minutes` were excluded row-wise from calculations using those specific fields.
- **"Cancelled" outcome treatment**: excluded from headline no-show rate calculations; this choice was sensitivity-tested and found not to materially change conclusions, but remains worth revisiting if HealthConnect's operational definition of "non-attendance" differs.
- **No interactive BI dashboard**: all visual outputs are static, reproducible charts generated directly from the validated dataset.
- **Age-band sample sizes**: moderate once split by lead-time band; direction of the finding is clear, but exact magnitudes should be treated as indicative.

## Reproducibility

All KPIs and statistical tests in this project were independently re-derived from the raw dataset during Week 7 testing and matched exactly, confirming the analytical pipeline is reproducible end-to-end.
