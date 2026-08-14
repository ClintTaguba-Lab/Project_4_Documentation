# Data Dictionary

## Overview

This data dictionary documents the key variables used in the
**Financial Inclusion in the Philippines** analysis.

The project uses the Philippines subset of the **Global Findex 2025**
microdata. It includes both original source variables and derived
variables created during data preparation.

---

## Source Variables

| Field | Data Type | Description | Example Value |
|---|---|---|---|
| `wpid_random` | Identifier | Unique respondent identifier | `123456789` |
| `wgt` | Float | Survey weight used for weighted estimates | `0.674757` |
| `account` | Binary | Indicates whether the respondent has a financial account | `1` |
| `dig_account` | Binary | Indicates whether the respondent has a digitally enabled account | `1` |
| `anydigpayment` | Binary | Indicates whether the respondent made or received a digital payment | `1` |
| `saved` | Binary | Indicates whether the respondent saved money | `1` |
| `borrowed` | Binary | Indicates whether the respondent borrowed money | `1` |
| `internet_use` | Binary | Indicates whether the respondent uses the internet | `1` |
| `female` | Categorical | Source gender variable | `1` |
| `age` | Numeric | Respondent age | `32` |
| `educ` | Categorical | Source education category | `2` |
| `inc_q` | Ordinal | Respondent income quintile | `3` |
| `emp_in` | Categorical | Workforce participation status | `1` |
| `urbanicity` | Categorical | Urban/rural residence classification | `2` |

---

## Derived Variables

These variables were created during data preparation to make the
analysis easier to interpret.

| Field | Data Type | Description | Example Value |
|---|---|---|---|
| `Gender` | Categorical | Readable gender classification | `Female` |
| `Education` | Categorical | Readable education level | `Secondary` |
| `Income_Quintile` | Ordinal | Readable income quintile | `Q3 - Middle` |
| `Employment` | Categorical | Readable workforce status | `In Workforce` |
| `Residence` | Categorical | Readable residence classification | `Urban` |
| `Age_Group` | Categorical | Respondent age band | `25-34` |
| `Account_Status` | Categorical | Readable account ownership status | `Account Owner` |
| `Digital_Account_Status` | Categorical | Readable digital account status | `Digital Account` |
| `Digital_Payment_Status` | Categorical | Readable digital payment status | `Digital Payment User` |
| `Internet_Status` | Categorical | Readable internet usage status | `Internet User` |
| `Saving_Status` | Categorical | Readable saving status | `Saved` |
| `Borrowing_Status` | Categorical | Readable borrowing status | `Borrowed` |
| `Financial_Behavior` | Derived Segment | Combined saving and borrowing behavior | `Saver & Borrower` |
| `Financial_Engagement` | Derived Segment | Financial engagement classification | `Digitally Active` |

---

## Financial Engagement Segments

| Segment | Definition |
|---|---|
| `Financially Excluded` | Respondent does not own a financial account |
| `Basic Access` | Respondent owns an account but does not use digital payments |
| `Digitally Active` | Respondent owns an account and uses digital payments |

> **Note:** Financial engagement segments were created specifically for
> this project and are not official Global Findex classifications.

---

## Financial Behavior Segments

| Segment | Definition |
|---|---|
| `Saver & Borrower` | Respondent reported both saving and borrowing |
| `Saver Only` | Respondent reported saving but not borrowing |
| `Borrower Only` | Respondent reported borrowing but not saving |
| `Neither` | Respondent reported neither saving nor borrowing |

---

## Notes

- Survey weights (`wgt`) were used for population-level descriptive estimates.
- Raw categorical variables were converted into readable labels during data preparation.
- Derived variables were created specifically for this analysis.
- Variable interpretations follow the Global Findex 2025 data documentation.
