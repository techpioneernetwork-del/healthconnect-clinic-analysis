# HealthConnect Clinic — Reducing Missed Appointments with Data & AI
**AnalystLab Africa Experience Lab — Data Analytics Track**

A shared cross-track project: HealthConnect Clinic, a fictional healthcare provider, is losing significant appointment capacity to no-shows and wants to use data, machine learning, and Generative AI to improve attendance and the patient support experience. This repo covers the Data Analytics track's contribution.

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## My Role (Data Analytics Track)

Understand the appointment dataset, assess its quality, define the business questions worth investigating, and propose KPIs that will guide deeper analysis in later weeks — laying groundwork the Data Science track builds a predictive model on top of.

## Week 4 — Problem Understanding (current)

**Headline finding:** Booking lead time is the strongest behavioral signal in the dataset. Same-week bookings attend far more reliably than bookings made a month or more in advance — a pattern stronger than reminders, demographics, or distance to the clinic.

| Metric | Value |
|---|---|
| Total appointments | 5,000 |
| No-Show rate | 48.5% |
| Attended rate | 46.3% |
| Cancelled rate | 5.3% |
| Data quality | Clean — no duplicates, no illogical values, missingness fully explained |

**6 business questions defined**, each linked to a proposed KPI:
1. What is the overall no-show rate, and how does it vary over time? → *Overall No-Show Rate*
2. Does booking lead time affect attendance? → *No-Show Rate by Booking Lead Time*
3. Does a patient's prior no-show history predict future no-shows? → *Repeat No-Show Rate*
4. Does sending a reminder (and which channel) reduce no-shows? → *Reminder Effectiveness Rate*
5. Which appointment types, days, or times see the most no-shows? → *Slot Utilisation Loss*
6. Does distance to the clinic influence attendance?

Full detail in `reports/01_Initial_Analysis_Document.docx`.

## Repository Structure

```
├── reports/
│   ├── 01_Initial_Analysis_Document.docx    # Dataset overview, data quality, business questions, KPIs
│   └── 02_Week4_Project_Summary.docx        # Concise weekly summary
├── data/
│   ├── HealthConnect_Appointment_Data.csv   # Original dataset (unmodified, per project rules)
│   └── HealthConnect_Data_Dictionary.pdf    # Variable definitions
└── README.md
```

## Project Stages

Problem Understanding (Week 4) → Analysis & Solution Design → Development → Testing & Refinement → Final Presentation

## Tools & Skills Applied

Python (pandas) · Data Quality Assessment · Business Question Definition · KPI Design · Healthcare Data Analysis

## Author

**Oluwatosin Olusanya**
Data Analytics Intern, AnalystLab Africa
Senior Finance Officer (13+ years) transitioning into Financial Data Analysis
[LinkedIn](https://www.linkedin.com/in/PLACEHOLDER) · [X / Twitter](https://x.com/PLACEHOLDER)

## Acknowledgment

Completed as part of the [AnalystLab Africa](https://www.analystlabafrica.com) Experience Lab Internship Programme.
