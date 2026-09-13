# HealthConnect Clinic – Appointment Attendance & No-Show Analytics

## Project Overview

This project is part of the **AnalystLab Africa Experience Lab Internship Programme – Data Analytics Track**. It uses the HealthConnect Clinic appointment dataset to investigate patient attendance, no-shows, cancellations, and operational factors associated with missed appointments.

The project progresses from data preparation and exploratory analysis in Week 5 to **advanced analytics, validation, segmentation, and decision support in Week 6**.

**Project objective:** Improve patient appointment attendance and healthcare support using data and AI.

## Business Problem

HealthConnect Clinic is experiencing a significant number of missed appointments. This creates unused appointment capacity and makes it harder for the clinic to plan and allocate resources effectively.

The analysis focuses on questions such as:

- What proportion of appointments result in no-shows, cancellations, or attendance?
- Which appointment characteristics are associated with higher no-show rates?
- Does booking an appointment further in advance relate to no-show behaviour?
- Does previous no-show history indicate higher future risk?
- How do reminders and reminder channels relate to attendance?
- Which findings have the greatest operational impact?

## Dataset

The HealthConnect dataset contains **5,000 appointment records** and includes:

- Appointment ID
- Patient ID
- Gender
- Age and Age Group
- Appointment Type
- Booking Date and Appointment Time
- Booking Lead Days
- Previous Appointments
- Previous No-Shows
- Reminder Sent
- Reminder Channel
- Distance to Clinic (km)
- Waiting Time (minutes)
- Appointment Outcome

Appointment outcomes include **Attended, No-Show, and Cancelled**.

## Week 5 – Exploratory Analysis

Week 5 established the baseline analysis through data preparation, EDA, KPI calculations, and Power BI visualizations.

Core validated outcome KPIs used in Week 6:

| KPI | Result |
|---|---:|
| Total Appointments | 5,000 |
| No-Show Appointments | 2,423 |
| No-Show Rate | 48.46% |
| Attendance Rate | 46.28% |
| Cancellation Rate | 5.26% |
| Non-Attendance Rate | 53.72% |

## Week 6 – Advanced Analytics & Decision Support

Week 6 moved beyond descriptive counts and focused on **rate-based comparisons, deeper segmentation, KPI validation, and evidence-based recommendations**.

### Key Findings

#### 1. Booking Lead Time

No-show rates increased substantially as booking lead time increased:

- 0–9 days: **29%**
- 10–19 days: **37%**
- 20–29 days: **44%**
- 30–39 days: **51%**
- 40–49 days: **62%**
- 50–59 days: **68%**
- 60+ days: **68%**

Longer booking lead times therefore represent one of the strongest observed risk patterns.

#### 2. Previous No-Show History

Observed no-show rates increased with previous no-show history:

- 0 previous no-shows: **44%**
- 1: **53%**
- 2: **59%**
- 3: **68%**
- 4: **67%**
- 5: **100%**

The 100% result for five previous no-shows should be interpreted cautiously until the segment size is confirmed.

#### 3. Reminder Status

- No reminder: **51%** no-show rate
- Reminder sent: **47%** no-show rate

The Week 5 count-based interpretation was revised after comparing rates. The results show an association, not proof that reminders directly cause lower no-show rates.

#### 4. Reminder Channel

Observed no-show rates were:

- None: **51%**
- WhatsApp: **50%**
- Email: **48%**
- SMS: **46%**

SMS had the lowest observed no-show rate among the analysed channels and should be investigated further rather than treated as proven causal evidence.

#### 5. Age and Gender

The Week 6 analysis demonstrated why rates are more useful than raw counts for comparing groups. Patients aged 65+ had the highest no-show count in Week 5, but an observed no-show rate of approximately **45%** in Week 6, so they were not the highest-risk age group.

Gender rates were approximately:

- Male: **49%**
- Female: **48%**
- Prefer not to say: **44%**

The male rate was slightly higher, but the difference between male and female patients was small compared with the stronger patterns observed for booking lead time and previous no-show history.

## Combined Risk Segmentation

A Power BI matrix was used to investigate the relationship between **Previous No-Shows** and **Booking Lead Time**.

The analysis showed that no-show rates generally increased with longer booking lead times, including among patients with no previous no-shows. Higher-risk combinations were also observed among patients with previous no-show history and longer lead times.

For example, patients with **0 previous no-shows** had an observed no-show rate increasing from approximately **24% for appointments booked 0–9 days in advance to 65% for appointments booked 60+ days in advance**.

This supports using both variables as candidate inputs for future risk segmentation and predictive modelling.

## KPI Validation

The core Week 5 KPIs were rechecked against the underlying 5,000 appointment records.

The no-show rate was independently calculated as:

```text
2,423 no-show appointments ÷ 5,000 total appointments × 100 = 48.46%
```

The outcome categories also reconcile:

```text
48.46% No-Show + 46.28% Attended + 5.26% Cancelled = 100%
```

The core KPIs were therefore retained for Week 6 decision support.

## Business Recommendations

1. **Prioritize long-lead appointments** for enhanced confirmation, particularly appointments booked 50+ days in advance.
2. **Identify previous no-show history** as a risk indicator and provide additional follow-up without penalizing patients.
3. **Continue and monitor reminder interventions**, evaluating performance using rates rather than raw counts.
4. **Investigate reminder channel performance**, with SMS identified as the lowest observed no-show-rate channel in this dataset.
5. **Develop a risk-based appointment strategy** using variables such as Previous No-Shows, Booking Lead Days, Reminder Sent, Reminder Channel, Age Group, Gender, and Appointment Type.
6. Avoid treating observed relationships as causal until further statistical or experimental testing is completed.

## Cross-Track Collaboration

During Week 6, the Data Analytics work was compared with an independent analysis from a fellow **Data Analytics student**.

The comparison showed directional agreement around reminder effectiveness, reminder channels, and the small difference between male and female no-show rates. A discrepancy in overall KPIs was also identified: the collaborating analysis reported a 51% no-show rate, while this analysis validated **48.46%** from 2,423 no-shows out of 5,000 records.

The discrepancy is documented as an item requiring reconciliation rather than being ignored.

## Data Quality & Limitations

- **90** records have missing Distance to Clinic values.
- **60** records have missing Waiting Time values.
- Missing values were not replaced with zero because zero represents a valid measurement.
- Some segmented groups may contain relatively few appointments, making extreme rates less reliable.
- The dataset is observational; associations do not establish causation.
- Historical behaviour may not represent future patient behaviour.
- Reminder performance may be affected by other patient or appointment characteristics.
- Raw counts can be misleading when segment sizes differ; Week 6 therefore prioritised rates.

## Week 7 Analytical Testing Requirements

The next stage will test whether the Week 6 findings are robust enough to support operational decisions and predictive modelling.

Planned testing includes:

- Validate high-risk segments and segment sizes.
- Test whether the booking lead-time relationship remains statistically meaningful.
- Assess the predictive value of previous no-show history.
- Evaluate reminder effectiveness while controlling for relevant factors.
- Compare reminder channels more rigorously.
- Test combined risk factors and interactions.
- Validate data quality, missingness, outliers, and KPI reliability.
- Provide validated analytical findings to support predictive modelling.
- Determine which relationships are strong enough for operational intervention.

## Tools & Technologies

- **Microsoft Power BI** – dashboard development and interactive analysis
- **Power Query** – data preparation and transformation
- **DAX** – KPI and analytical measure development
- **Microsoft Excel** – data inspection and supporting analysis
- **GitHub** – portfolio documentation and version control

## Project Structure

```text
healthconnect-analytics/
│
├── README.md
├── HealthConnect_Week6_Advanced_Analytics_Report.docx
├── HealthConnect_Week6_Advanced_Analytics_Report.pdf
├── HealthConnect_Dashboard.pbix
├── data/
├── screenshots/
└── documentation/
```

## Skills Demonstrated

- Data cleaning and preparation
- Exploratory data analysis
- Data quality validation
- KPI development and validation
- Power BI dashboard development
- Power Query
- DAX
- Rate-based segmentation
- Advanced analytical investigation
- Business insight generation
- Evidence-based recommendations
- Analytical risk and limitation assessment
- Cross-track collaboration
- Data storytelling and decision support

## Conclusion

The HealthConnect analytics project progressed from descriptive EDA in Week 5 to deeper validation and decision support in Week 6. The strongest observed patterns were associated with **booking lead time and previous no-show history**, while reminder status and channel also showed meaningful differences requiring further testing.

The Week 6 analysis provides HealthConnect with a stronger evidence base for targeted appointment-management strategies and establishes candidate variables and analytical requirements for future predictive modelling and Week 7 testing.
