# HealthConnect Clinic — Reducing Missed Appointments with Data & AI

**AnalystLab Africa Experience Lab — Data Analytics Track**

A shared cross-track project: HealthConnect Clinic, a fictional healthcare provider, is losing significant appointment capacity to no-shows and wants to use data, machine learning, and Generative AI to improve attendance and the patient support experience. This repo covers the Data Analytics track's contribution.

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## My Role (Data Analytics Track)

Understand the appointment dataset, assess its quality, calculate KPIs, run exploratory analysis on no-show drivers, validate findings statistically, stress-test them, and translate results into evidence-based business recommendations — feeding relevant findings to the Data Science and Project Management tracks along the way.

## Progress

### Week 4 — Problem Understanding

**Headline finding:** Booking lead time is the strongest behavioral signal in the dataset. Same-week bookings attend far more reliably than bookings made a month or more in advance — a pattern stronger than reminders, demographics, or distance to the clinic.

- 5,000 appointments, no-show rate 48.5% (initial, pre-Cancelled-exclusion figure), data confirmed clean.
- 6 business questions defined, each linked to a proposed KPI.

Full detail: `reports/Initial Analysis Document.docx`, `reports/Week4 Project Summary.docx`.

### Week 5 — Analysis & Initial Implementation

Calculated all 5 proposed KPIs against the real dataset, ran exploratory analysis across booking lead time, prior no-show history, reminders, appointment type/day, distance, and waiting time, and produced 6 supporting charts.

- **Overall no-show rate: 51.2%** (2,423 of 4,737 appointments with a definitive outcome; Cancelled appointments excluded from this rate).
- **Booking lead time** is the strongest driver: 26.6% (0–3 days) rising to 63.9% (30+ days).
- **Prior no-show count** is the second-strongest driver: 46.3% (no history) rising to 70.3% (3+ prior no-shows).
- Reminders help only modestly (~5-point improvement); appointment type, day, and time are weak drivers (3–5-point spreads).
- Cross-track collaboration point identified with the Data Science track.

Full detail: `reports/Week5 Project Summary.docx` (see also the Week 5 analysis referenced in Week 6 outputs below).

### Week 6 — Integration, Advanced Development & Validation

Deepened and formally validated the two strongest Week 5 drivers rather than repeating the Week 5 EDA:

- **Statistically validated** booking lead time (χ² = 340.42, p < 0.001) and prior no-show history (χ² = 72.36, p < 0.001) as genuine, non-chance drivers.
- **New analysis:** tested whether the two drivers interact. Finding — they combine **additively, not synergistically** (likelihood-ratio test on the interaction term: p = 0.50). No special "combined-risk" protocol is needed; applying both interventions independently captures the full risk.
- **Refined KPI:** reminder effectiveness now broken out by risk segment — near-zero benefit for low-risk patients (0.4pt) vs. a real effect for every at-risk segment (4.9–6.5pt), sharpening where reminder resources should go.
- **Cross-track integration completed with Project Management:** Week 5 findings were provided to PM and logged as a completed integration point (`Completed – PM Integration`) informing PM's Week 7 testing/refinement priorities.

Full detail: `reports/Week6_Advanced_Analytics_Report.docx`, `reports/Week6_Project_Summary.docx`.

### Week 7 — Testing & Refinement (current)

Independently re-derived the entire Week 5/6 analytical pipeline from the raw dataset — rather than trusting prior outputs — and pushed the two validated drivers into a combined, actionable form.

- **Full reproduction:** all 8 previously reported KPIs and both chi-square statistics reproduced exactly from the raw CSV. No calculation errors found anywhere in the pipeline.
- **New analysis — combined risk matrix:** merged booking lead time and prior no-show history into a single 2×2 risk view. The highest-risk segment (long lead time + has prior no-shows) covers **1,529 appointments (1,035 unique patients) at a 63.6% no-show rate** — 2.3x the lowest-risk segment (715 appointments, 28.0%). Confirms the Week 6 additive-interaction finding at a practical, targetable level.
- **Segment stability testing:** the lead-time effect holds across gender and every age group, but is measurably weaker at the youngest (18–24) and oldest (65+) bands than for working-age patients (25–64) — a genuine refinement, not just a re-confirmation.
- **Sensitivity testing:** the headline no-show rate and lead-time pattern are robust to how Cancelled appointments are treated (rates shift 2–5 points under an alternative treatment, but the underlying shape is unchanged).
- **A claim tested and rejected:** an earlier draft (produced with an external tool) asserted reminders were disproportionately assigned to lower-risk patients. Tested directly against the data and found **false** — reminder-send rates are nearly identical (71.6–74.3%) across all four risk segments. Documented transparently as a failed test rather than dropped silently.
- **Cross-track contribution:** shared the combined risk matrix and the rejected reminder-bias claim with the Project Management track, giving Week 8 planning a concrete, sized target segment instead of an abstract statistical pattern.

Full detail: `reports/01_HealthConnect_Analytics_Testing_Report.docx`, `reports/02_Week7_Project_Summary.docx`.

## Repository Structure

```
├── reports/
│   ├── Initial Analysis Document.docx              # Week 4/5: dataset overview, data quality, KPIs, EDA, insights
│   ├── Week4 Project Summary.docx                  # Week 4 concise summary
│   ├── Week5 Project Summary.docx                  # Week 5 concise summary
│   ├── Week6_Advanced_Analytics_Report.docx        # Week 6: validated findings, interaction analysis, refined KPIs
│   ├── Week6_Project_Summary.docx                  # Week 6 concise summary
│   ├── 01_HealthConnect_Analytics_Testing_Report.docx # Week 7: independent re-validation, combined risk matrix, sensitivity testing
│   └── 02_Week7_Project_Summary.docx                  # Week 7 concise summary
├── data/
│   ├── HealthConnect_Appointment_Data.csv             # Original dataset (unmodified, per project rules)
│   └── HealthConnect_Data_Dictionary.pdf              # Variable definitions
└── README.md
```

*Note: static charts (Python/pandas/matplotlib) were used throughout this project rather than an interactive BI dashboard.*

## Project Stages

Problem Understanding (Week 4) → Analysis & Initial Implementation (Week 5) → Integration & Validation (Week 6) → **Testing & Refinement (Week 7, current)** → Final Presentation (Week 8)

## Tools & Skills Applied

Python (pandas, scipy, scikit-learn) · Statistical Hypothesis Testing (chi-square, likelihood-ratio test) · Logistic Regression · Segment & Sensitivity Analysis · Data Quality Assessment · KPI Design & Validation · Cross-Track Collaboration · Healthcare Data Analysis

## Author

**Oluwatosin Olusanya**
Data Analytics Intern, AnalystLab Africa
Senior Finance Officer (13+ years) transitioning into Financial Data Analysis
http://www.linkedin.com/in/oluwatosin-olusanya-aa97a739a · https://x.com/sunday_tosin

## Acknowledgment

Completed as part of the [AnalystLab Africa](https://www.analystlabafrica.com) Experience Lab Internship Programme.
