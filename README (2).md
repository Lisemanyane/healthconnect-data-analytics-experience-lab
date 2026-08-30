# HealthConnect Clinic Experience Lab — Data Analytics Track

**AnalystLab Africa — Experience Lab Internship Programme**
**Project:** Improving Patient Appointment Attendance and Healthcare Support Using Data and AI

## Project Overview

HealthConnect Clinic (fictional) is experiencing missed patient appointments, unclear drivers of
no-show behaviour, inefficient use of appointment slots, and repetitive patient enquiries. This
repository documents the Data Analytics track's contribution to answering the central project
question:

> How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the
> patient support experience?

## Week 4 — Problem Understanding (Current)

**Status:** ✅ Complete

Week 4 focused on understanding the appointment dataset, assessing its quality, and defining the
business questions and KPIs that will guide analysis in later weeks.

### What's in this submission

| File | Description |
|---|---|
| `HealthConnect_Week4_DataAnalytics.docx` | Initial Analysis Document — dataset overview, data quality findings, business questions, proposed KPIs, analysis approach, assumptions/limitations/risks, and Week 4 summary |
| `HealthConnect_Data_Quality_Assessment.xlsx` | Full data quality assessment workbook — raw data, live-formula checks (completeness, duplicates, categorical consistency, outliers, logical consistency), and a findings summary |
| `HealthConnect_Appointment_Data_CLEANED.xlsx` | Cleaned dataset, with a Cleaning Log sheet documenting every change made and why |

### Key findings from Week 4

- Dataset: 5,000 appointment records, 18 substantive fields
- No duplicate appointment IDs; all cross-field logic checks (booking lead time, weekday
  consistency, reminder logic) passed with zero mismatches
- Missing data limited to three fields: `reminder_channel` (1,366 blanks — explained by
  `reminder_sent = No`), `distance_to_clinic_km` (90 blanks), `waiting_time_minutes` (60 blanks)
- Two unlabeled columns found in the source file (one blank, one with a single stray value) —
  excluded from analysis pending clarification
- Appointment outcomes are reasonably balanced: No-Show 48.5% · Attended 46.3% · Cancelled 5.3%

### Proposed KPIs (identified, not yet calculated — per Week 4 scope)

1. Overall No-Show Rate (%)
2. No-Show Rate by Demographic Segment (age band / gender / area)
3. No-Show Rate by Booking Lead-Time Bucket
4. Reminder Effectiveness (no-show rate: reminder sent vs not)
5. No-Show Rate by Distance Band

Full justification and links to business questions are in the Initial Analysis Document.

## Tools Used

- Microsoft Excel — data cleaning and data quality assessment (formula-based, auditable)
- Microsoft Word — Initial Analysis Document
- Python (pandas) — planned for Week 5 exploratory analysis and KPI calculation

## Next Steps (Week 5)

- Calculate the five proposed KPIs against the cleaned dataset
- Begin bivariate analysis to answer the business questions defined in Week 4
- Resolve the two unlabeled source columns and confirm handling of missing distance/waiting-time
  values with the data owner / Data Dictionary

## Author

[Your Full Name] — Data Analytics Track Intern, AnalystLab Africa Experience Lab

---
*Part of the AnalystLab Africa Experience Lab — HealthConnect Clinic Project*
