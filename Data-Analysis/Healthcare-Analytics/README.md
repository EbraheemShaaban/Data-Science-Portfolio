# Healthcare Appointment No-Show Analysis


## Overview

This project analyzes appointment-level records from public clinics in Vitória, Brazil, to explore patterns associated with missed medical appointments (`NoShow`). It combines data-quality checks, feature engineering, rate-based exploratory data analysis, a confounding-aware comparison of SMS reminders, a chi-square association test, reusable CSV exports, and baseline classification models.

The goal is to demonstrate a reproducible analytics workflow—not to make clinical decisions or claim causal explanations.

## Business questions

- What is the no-show rate in the cleaned analysis dataset?
- How does the rate vary by waiting time, weekday, age group, and recorded patient/appointment characteristics?
- Does the observed SMS/no-show relationship change when appointments are compared within waiting-time groups?
- Is there a statistical association between SMS status and appointment outcome?
- How do Logistic Regression and Random Forest compare on held-out data?

## Dataset

The source is the public medical appointments dataset commonly distributed as `KaggleV2-May-2016.csv` or `Data.csv`, with fields such as patient and appointment identifiers, booking and appointment dates, age, neighbourhood, health-condition flags, SMS reminder status, and the `No-show` outcome. 



## What is included

1. **Data quality audit** — missing values, exact duplicate rows, duplicate appointment IDs, invalid ages, invalid dates, and unexpected target values.
2. **Data cleaning** — standardizes column names and dates; excludes records with invalid age/date/target values; retains an audit of cleaning decisions.
3. **Feature engineering** — `WaitDays`, appointment weekday, booking weekday, month, age group, and waiting-time group.
4. **Rate-based EDA** — calculates appointment counts and no-show rates by relevant groups, rather than relying only on raw counts.
5. **Waiting-time and SMS analysis** — compares SMS/no-SMS rates overall and within waiting-time bands to highlight potential confounding.
6. **Statistical testing** — chi-square test and Cramér's V for the association between SMS status and outcome.
7. **Baseline machine learning** — compares Logistic Regression and Random Forest using a held-out test set, class-aware metrics, and a confusion matrix. Patient-grouped splitting is used when patient IDs are available.


## Outputs

The notebook writes CSV files to `outputs/`, including:

- `healthcare_kpis.csv`
- `data_quality_cleaning_log.csv`
- `cleaned_appointment_data.csv`
- `no_show_by_weekday.csv`
- `no_show_by_wait_group.csv`
- `no_show_by_sms.csv`
- `no_show_by_wait_and_sms.csv`
- `no_show_by_neighbourhood.csv`
- `numeric_correlation_matrix.csv`
- `model_comparison_metrics.csv`








