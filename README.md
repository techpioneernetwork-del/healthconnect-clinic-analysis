# HealthConnect Clinic — Reducing Missed Appointments with Data & AI

**AnalystLab Africa Experience Lab — Data Analytics Track — Final Submission (Week 8)**

A shared cross-track project: HealthConnect Clinic, a fictional healthcare provider, was losing significant appointment capacity to no-shows and wanted to use data, machine learning, and Generative AI to improve attendance and the patient support experience. This repo covers the Data Analytics track's contribution, from initial problem understanding through to a validated, portfolio-ready decision-support package.

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## My Role (Data Analytics Track)

Quantify the no-show problem, identify its statistically validated drivers, and turn those findings into a decision-support package that Data Science and Project Management could build on directly.

## Headline Result

**51.2%** of scheduled appointments ended in a no-show (2,423 of 4,737 definitive-outcome appointments) — confirmed and independently re-validated across an 8-week analysis. Two factors drive this overwhelmingly:

| Driver | Effect | Statistical test |
|---|---|---|
| Booking lead time | 26.6% no-show (0–3 days) → 63.9% (30+ days) | χ²=340.42, p<0.001 |
| Prior no-show history | 46.3% (0 priors) → 70.3% (3+ priors) | χ²=72.36, p<0.001 |

Combined, these two factors isolate a **1,529-appointment (1,035-patient) highest-risk segment at 63.6% no-show**, versus 28.0% in the lowest-risk segment (715 appointments) — directly targetable with confirmation calls or double-booking policies.

## Project Journey

| Week | Stage | Output |
|---|---|---|
| 4 | Problem Understanding | Dataset quality assessment, 6 business questions, initial KPI proposals |
| 5 | Analysis & Initial Implementation | 5 KPIs calculated, 6 charts, 5 business insights, 4 recommendations |
| 6 | Integration & Validation | Cross-track integration with Project Management; lead-time and prior-no-show drivers statistically validated (chi-square) |
| 7 | Testing & Refinement | Independent re-derivation of every KPI and test (exact match); sensitivity/robustness testing; a claim of reminder-assignment bias tested and found false |
| 8 | Final Integration & Presentation | Final decision-support package, presentation deck, and cross-track contribution to Data Science and Project Management |

See [`ANALYTICAL_PROCESS.md`](./ANALYTICAL_PROCESS.md) for the full methodology write-up.

## Business Insights & Recommendations

- Roughly 1 in 2 scheduled appointments is missed — a structural operational problem, not a seasonal one.
- Route the 1,529-appointment highest-risk segment to manual confirmation calls or double-booking policies rather than treating all patients identically.
- Introduce a shorter default booking window, or a mandatory re-confirmation step, for appointments booked more than 14 days out.
- Design a distinct outreach approach for patients under 25 and over 65 — the lead-time effect is measurably weaker for them.
- Maintain reminders (prioritizing SMS) as a low-cost baseline, but not a standalone fix — their effect is real but modest, and smallest where risk is already low.
- Adopt this risk-segmentation approach as a standing quarterly review, given the no-show rate has remained structurally stable (not seasonal).

## Limitations

- Descriptive/associational analysis — identifies strong, validated, segment-stable patterns but does not by itself prove that intervening on lead time will cause a proportional drop in no-shows.
- Small missing-data exclusions in `distance_to_clinic_km` (1.8%) and `waiting_time_minutes` (1.2%), handled row-wise.
- The "Cancelled" outcome was excluded from headline no-show calculations; this was explicitly sensitivity-tested (Week 7) and does not materially change conclusions.
- No interactive BI dashboard was built; all visual outputs are static, reproducible charts generated from the validated dataset.
- Age-band segment findings are directionally clear but based on moderate sample sizes once split by lead-time band.

## Cross-Track Contribution

- **→ Data Science:** booking lead time and prior no-show history confirmed as the two strongest, independent predictors, with the combined risk-segment flag offered as a candidate engineered feature.
- **→ Project Management:** the sized 1,529-appointment / 1,035-patient highest-risk segment incorporated into Week 7–8 resourcing and confirmation-call planning.

## Repository Structure

```
├── reports/
│   ├── 01_Initial_Analysis_Document.docx              # Week 4: dataset overview, data quality, business questions, KPIs
│   ├── 02_Week4_Project_Summary.docx                  # Week 4: concise weekly summary
│   ├── 03_HealthConnect_Final_Analytics_Package.docx  # Week 8: final KPIs, validated findings, visualizations,
│   │                                                   #         insights, recommendations, limitations, cross-track contribution, executive summary
│   ├── 04_Week7-8_Transition_Brief.docx               # Week 8: testing → final integration readiness brief
│   └── presentation/                                  # Week 8: analytics section of the final presentation (exported slides)
├── data/
│   ├── HealthConnect_Appointment_Data.csv             # Original dataset (unmodified, per project rules)
│   └── HealthConnect_Data_Dictionary.pdf              # Variable definitions
├── ANALYTICAL_PROCESS.md                              # Full week-by-week methodology write-up
└── README.md
```

## Tools & Skills Applied

Python (pandas) · Statistical Hypothesis Testing (chi-square) · Data Quality Assessment · KPI Design · Risk Segmentation · Healthcare Data Analysis · Cross-Track Collaboration

## Author

**Oluwatosin Olusanya**
Data Analytics Intern, AnalystLab Africa
Senior Finance Officer (13+ years) transitioning into Financial Data Analysis
[LinkedIn](http://www.linkedin.com/in/oluwatosin-olusanya-aa97a739a) · [X](https://x.com/sunday_tosin)

## Acknowledgment

Completed as part of the [AnalystLab Africa](https://www.analystlabafrica.com) Experience Lab Internship Programme.

#AnalystLabAfrica
