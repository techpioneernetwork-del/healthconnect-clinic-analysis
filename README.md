# HealthConnect Clinic — Reducing Missed Appointments with Data & AI
**AnalystLab Africa Experience Lab — Data Analytics Track**

A shared cross-track project: HealthConnect Clinic, a fictional healthcare provider, is losing significant appointment capacity to no-shows and wants to use data, machine learning, and Generative AI to improve attendance and the patient support experience. This repo covers the Data Analytics track's contribution.

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## My Role (Data Analytics Track)

Understand the appointment dataset, calculate and validate KPIs, identify what actually drives no-shows, and stress-test those findings — output that directly informs the Data Science track's predictive modeling and the Project Management track's Week 8 planning.

## Headline Findings (validated through Week 7)

| Metric | Result |
|---|---|
| Overall No-Show Rate | 51.2% (2,423 of 4,737 appointments) |
| No-Show Rate: 0-3 day booking | 26.6% |
| No-Show Rate: 30+ day booking | 63.9% |
| No-Show Rate: no prior no-shows | 46.3% |
| No-Show Rate: 3+ prior no-shows | 70.3% |
| Highest-risk combined segment | 1,529 appointments (1,035 patients), 63.6% no-show |
| Lowest-risk combined segment | 715 appointments, 28.0% no-show |
| Chi-square: booking lead time | χ² = 340.42, p < 0.001 |
| Chi-square: prior no-show history | χ² = 72.36, p < 0.001 |

**The strongest, now-validated finding:** booking lead time is the dominant driver of no-shows — patients who book close to their appointment date attend far more reliably than those booking a month or more out. This has been confirmed statistically significant (not chance), stable across gender and every age group (though weaker at the youngest and oldest bands), and robust to how cancelled appointments are treated. Combined with a patient's own no-show history, it identifies a clear, appropriately sized highest-risk group of 1,529 appointments that management can act on directly.

## Project Timeline

| Week | Stage | Status |
|---|---|---|
| Week 4 | Problem Understanding — data quality assessment, 6 business questions, 5 proposed KPIs | ✅ Complete |
| Week 5 | Analysis & Solution Design — all 5 KPIs calculated, EDA, visualisations, business insights, cross-track collaboration with Data Science | ✅ Complete |
| Week 6 | Advanced Development — statistical validation (chi-square tests), interaction-effect testing, risk-segmented reminder analysis, PM integration | ✅ Complete |
| Week 7 | Testing & Validation — independent re-derivation of every KPI/statistic, combined risk-segment matrix, segment stability testing, sensitivity testing | ✅ Complete |
| Week 8 | Final Integration & Presentation | Upcoming |

## Repository Structure

```
├── reports/
│   ├── 01_Initial_Analysis_Document.docx                     # Week 4: data quality, business questions, proposed KPIs
│   ├── 02_Week4_Project_Summary.docx                         # Week 4 summary
│   ├── 01_Initial_HealthConnect_Analytics_Report.docx         # Week 5: calculated KPIs, EDA, insights, recommendations
│   ├── 02_Week5_Project_Summary.docx                         # Week 5 summary
│   ├── 04_Week6_Advanced_Analytics_Report.docx                # Week 6: chi-square validation, interaction-effect test
│   ├── 05_Week6_Project_Summary.docx                          # Week 6 summary
│   ├── 01_HealthConnect_Analytics_Testing_Report.docx         # Week 7: independent re-validation, combined risk matrix, sensitivity testing
│   └── 02_Week7_Project_Summary.docx                          # Week 7 summary
├── dashboard/
│   ├── hc_leadtime.png              # No-show rate by booking lead time
│   ├── hc_prevnoshow.png            # No-show rate by prior no-show count
│   ├── hc_monthly.png               # Monthly no-show trend
│   ├── hc_reminders.png             # Reminder effectiveness by channel
│   ├── hc_type_day.png              # No-show rate by appointment type & day
│   ├── hc_w7_riskmatrix.png         # Week 7: combined risk matrix (lead time × prior history)
│   └── hc_w7_agegroup_leadtime.png  # Week 7: lead-time effect by age group
├── data/
│   ├── HealthConnect_Appointment_Data.csv   # Original dataset (unmodified, per project rules)
│   └── HealthConnect_Data_Dictionary.pdf    # Variable definitions
└── README.md
```

*Note: static charts (Python/pandas/matplotlib) were used throughout this project rather than an interactive BI dashboard — this is reflected consistently across all weekly deliverables.*

## Cross-Track Collaboration

- **Week 5–6:** Shared validated KPIs and the confirmed lead-time/history drivers with the **Data Science track** to prioritise their feature selection for the no-show prediction model.
- **Week 7:** Shared the combined risk-segment matrix (1,529-appointment highest-risk group) and the confirmed absence of reminder-assignment bias with the **Project Management track**, to support Week 8 readiness planning with a concrete, sized target segment.

## Testing & Validation Highlights (Week 7)

Every KPI and statistical result from Weeks 5–6 was independently re-derived from the raw dataset and reproduced exactly — no calculation errors found. Testing also went further: a claim (from an early draft, later confirmed to have come from an external tool) that reminders were disproportionately assigned to lower-risk patients was tested directly against the data and found **false** — documented transparently in the Testing & Validation Record rather than dropped silently, alongside 5 other tests that passed.

## Project Stages

Problem Understanding (Week 4) → Analysis & Solution Design (Week 5) → Advanced Development (Week 6) → Testing & Validation (Week 7) → Final Integration & Presentation (Week 8)

## Tools & Skills Applied

Python (pandas, matplotlib, scipy) · Data Quality Assessment · Exploratory Data Analysis · KPI Design & Calculation · Statistical Hypothesis Testing (chi-square) · Interaction & Segment Analysis · Sensitivity/Robustness Testing · Cross-Track Collaboration

## Author

**Oluwatosin Olusanya**
Data Analytics Intern, AnalystLab Africa
Senior Finance Officer (13+ years) transitioning into Financial Data Analysis
https://www.linkedin.com/in/oluwatosin-olusanya-aa97a739a · https://x.com/sunday_tosin

## Acknowledgment

Completed as part of the [AnalystLab Africa](https://www.analystlabafrica.com) Experience Lab Internship Programme.
