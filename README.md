# HealthConnect Clinic — Reducing Missed Appointments with Data & AI
**AnalystLab Africa Experience Lab — Data Analytics Track**

A shared cross-track project: HealthConnect Clinic, a fictional healthcare provider, is losing significant appointment capacity to no-shows and wants to use data, machine learning, and Generative AI to improve attendance and the patient support experience. This repo covers the Data Analytics track's contribution.

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## My Role (Data Analytics Track)

Understand the appointment dataset, calculate KPIs, and identify what actually drives no-shows — findings that directly inform the Data Science track's predictive modeling work.

## Headline Findings (Week 5)

| KPI | Result |
|---|---|
| Overall No-Show Rate | 51.2% (2,423 of 4,737 appointments) |
| No-Show Rate: 0-3 day booking | 26.6% |
| No-Show Rate: 30+ day booking | 63.9% |
| No-Show Rate: no prior no-shows | 46.3% |
| No-Show Rate: 3+ prior no-shows | 70.3% |
| Reminder effect | 54.6% → 49.9% (modest, ~5pt) |

**The strongest finding:** booking lead time is by far the dominant driver of no-shows — patients who book close to their appointment date attend far more reliably than those booking a month or more out. This holds independently within every appointment type (verified via a robustness check), ruling out appointment type as a confounding factor. A patient's own no-show history is the second-strongest predictor. Reminders help, but only modestly compared to these two.

## Project Timeline

| Week | Stage | Status |
|---|---|---|
| Week 4 | Problem Understanding — data quality assessment, 6 business questions, 5 proposed KPIs | ✅ Complete |
| Week 5 | Analysis & Solution Design — all 5 KPIs calculated, EDA, visualisations, business insights, cross-track collaboration with Data Science | ✅ Complete |
| Week 6 | Development (planned) | Upcoming |

## Repository Structure

```
├── reports/
│   ├── 01_Initial_Analysis_Document.docx            # Week 4: data quality, business questions, proposed KPIs
│   ├── 02_Week4_Project_Summary.docx                # Week 4 summary
│   ├── 01_Initial_HealthConnect_Analytics_Report.docx  # Week 5: calculated KPIs, EDA, insights, recommendations
│   └── 02_Week5_Project_Summary.docx                # Week 5 summary
├── dashboard/
│   ├── hc_leadtime.png       # No-show rate by booking lead time
│   ├── hc_prevnoshow.png     # No-show rate by prior no-show count
│   ├── hc_monthly.png        # Monthly no-show trend
│   ├── hc_reminders.png      # Reminder effectiveness by channel
│   └── hc_type_day.png       # No-show rate by appointment type & day
├── data/
│   ├── HealthConnect_Appointment_Data.csv   # Original dataset (unmodified, per project rules)
│   └── HealthConnect_Data_Dictionary.pdf    # Variable definitions
└── README.md
```

## Cross-Track Collaboration

Shared the confirmed finding that booking lead time and prior no-show count are the two strongest, independent predictors of no-shows with the **Data Science track**, to help prioritise their feature selection for the no-show prediction model ahead of their own analysis.

## Project Stages

Problem Understanding (Week 4) → Analysis & Solution Design (Week 5) → Development → Testing & Refinement → Final Presentation

## Tools & Skills Applied

Python (pandas, matplotlib) · Data Quality Assessment · Exploratory Data Analysis · KPI Design & Calculation · Confound/Robustness Testing · Business Insight Generation · Cross-Track Collaboration

## Author

**Oluwatosin Olusanya**
Data Analytics Intern, AnalystLab Africa
Senior Finance Officer (13+ years) transitioning into Financial Data Analysis
[LinkedIn](https://www.linkedin.com/in/oluwatosin-olusanya-aa97a739a) · [X / Twitter](https://x.com/sunday_tosin)

## Acknowledgment

Completed as part of the [AnalystLab Africa](https://www.analystlabafrica.com) Experience Lab Internship Programme.
