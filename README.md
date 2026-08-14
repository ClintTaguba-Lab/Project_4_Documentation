# Financial Inclusion in the Philippines

> *Analyzing financial access, digital payment adoption and financial
> behavior among Filipino adults using Global Findex 2025 survey data.*

------------------------------------------------------------------------

## Key Results at a Glance

| Finding                                       |                   Result |
|-----------------------------------------------|-------------------------:|
| Largest account ownership gap                 | **48.53 pp — Education** |
| Digital payment adoption among account owners |               **80.37%** |
| Digital activation gap                        |               **19.63%** |
| Largest digital adoption gap                  |       **44.29 pp — Age** |
| Saving gap by financial engagement            |             **40.35 pp** |

------------------------------------------------------------------------

## ⚙️ Project Type Flags

- Exploratory Data Analysis (EDA)
- Python Analysis
- Data Cleaning / Wrangling
- Statistical Analysis
- Data Visualization
- End to End Analysis

------------------------------------------------------------------------

## Table of Contents

1.  [Project Overview](#1-project-overview)
2.  [Objectives](#2-objectives)
3.  [Project Scope & Tools](#3-project-scope--tools)
4.  [Repository Structure](#4-repository-structure)
5.  [Data Workflow](#5-data-workflow)
6.  [Data Model & Schema](#6-data-model--schema)
7.  [Analysis & Metrics](#7-analysis--metrics)
8.  [Key Insights](#8-key-insights)
9.  [Recommendations](#9-recommendations)
10. [Assumptions & Limitations](#10-assumptions--limitations)
11. [Future Enhancements](#11-future-enhancements)
12. [Deliverables](#12-deliverables)
13. [Author](#13-author)

------------------------------------------------------------------------

## 1. Project Overview

**Context:** Financial inclusion extends beyond whether individuals own
a financial account. People may have formal financial access but remain
digitally inactive, while financially excluded individuals may still
participate in financial behaviors such as saving or borrowing.

This project analyzes the Philippines subset of the Global Findex 2025
dataset to examine financial inclusion across three connected
dimensions:

**Financial Access → Digital Activation → Financial Behavior**

**Problem Statement:** Which groups in the Philippines remain
financially excluded and what characteristics are associated with the
transition from financial access to active digital financial usage?

**Approach:** The project uses survey-weighted descriptive analysis,
demographic segmentation, behavioral segmentation, interactive
visualization, Chi-square tests, and Cramér’s V association measures.

Three research questions guide the analysis:

1.  Which demographic groups show the largest gaps in financial account
    ownership?
2.  Among account owners, which groups show the largest differences in
    digital payment adoption?
3.  How do saving and borrowing behaviors differ across financial
    engagement levels?

**Outcome:** The analysis found that:

- Education and income show the largest disparities in financial account
  ownership.

- 80.37% of account owners use digital payments, leaving a 19.63%
  digital activation gap.

- Age and internet usage are the strongest observed differentiators of
  digital payment adoption among account owners.

- ## Financial engagement differentiates saving behavior more strongly than borrowing behavior.

## 2. Objectives

- **Primary Objective:** Identify demographic and behavioral
  characteristics associated with financial exclusion and digital
  financial adoption among Filipino adults.
- **Secondary Objective 1:** Quantify financial account ownership using
  survey-weighted estimates.
- **Secondary Objective 2:** Identify demographic groups with the
  largest account ownership gaps.
- **Secondary Objective 3:** Determine whether account ownership
  translates into digital payment activity.
- **Secondary Objective 4:** Identify characteristics associated with
  digital adoption among account owners.
- **Secondary Objective 5:** Compare saving and borrowing behavior
  across financial engagement levels.
- **Secondary Objective 6:** Statistically validate major descriptive
  findings.
- **Secondary Objective 7:** Translate analytical evidence into
  practical financial inclusion recommendations.

> 💡 *Every analysis decision in this project traces back to one of
> these objectives.*

------------------------------------------------------------------------

## 3. Project Scope & Tools

### Scope

| Dimension                  | Details                                                                                                                                             |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| **In Scope**               | Philippine respondents from Global Findex 2025; financial access, digital payment usage, saving, borrowing, internet usage, and demographic factors |
| **Out of Scope**           | Causal inference, transaction level analysis, credit quality, monetary transaction values, longitudinal trends                                      |
| **Survey Year**            | 2025                                                                                                                                                |
| **Source Dataset**         | Global Findex 2025 microdata                                                                                                                        |
| **Granularity**            | One row per survey respondent                                                                                                                       |
| **Primary Analysis Level** | Respondent level weighted analysis                                                                                                                  |

### Tools & Technologies

| Category                | Tool(s) Used                 |
|-------------------------|------------------------------|
| Data Source             | Global Findex 2025 Microdata |
| Data Access             | Google BigQuery              |
| Data Processing         | Python                       |
| Analysis                | Pandas, NumPy                |
| Statistical Testing     | SciPy                        |
| Visualization           | Plotly                       |
| Development Environment | Google Colab                 |
| Version Control         | Git / GitHub                 |
| Documentation           | Markdown                     |

------------------------------------------------------------------------

## 4. Repository Structure

``` text
financial-inclusion-philippines/
│
├── README.md
├── notebooks/
│   └── Financial_Inclusion_Philippines_Portfolio.ipynb
├── visuals/
│   ├── financial_inclusion_snapshot.png
│   ├── account_ownership_gap.png
│   ├── digital_adoption_gap.png
│   └── financial_behavior.png
├── data/
│   └── README.md
└── docs/
    └── data_dictionary.md
```

------------------------------------------------------------------------

## 5. Data Workflow

    Global Findex 2025
          ↓
    Filter Philippines
          ↓
    Validate Respondents
          ↓
    Select Analysis Variables
          ↓
    Check Missing Values & Categories
          ↓
    Apply Survey Weights
          ↓
    Feature Engineering
          ↓
    Weighted Descriptive Analysis
          ↓
    Segmentation & Gap Analysis
          ↓
    Statistical Validation
          ↓
    Visualization
          ↓
    Insights & Recommendations

1.  **Source:** \[Global Findex 2025 microdata containing approximately
    144,090 respondents and 199 variables.\]
2.  **Filtering:** The dataset was filtered to respondents whose economy
    was recorded as the Philippines.

The final Philippine sample contains:

- 1,000 respondents
- 1,000 unique respondent IDs
- 0 duplicate respondent IDs Only variables relevant to the research
  questions were retained for analysis.

3.  **Cleaning:** Data quality and category checks were performed before
    analysis.

The cleaning process included:

- checking respondent IDs for duplicates
- reviewing missing values in key analytical variables
- checking for missing survey weights
- validating raw category values against the data definitions
- reviewing demographic and financial indicator coding
- checking survey weight values before weighted calculations
- confirming that key binary indicators were consistently coded

These checks helped ensure that the analytical sample and variables were
suitable for the subsequent weighted analysis.

4.  **Transformation:** Raw survey variables were transformed into
    readable categories and analytical segments to support
    interpretation.

Derived fields included:

- Gender - readable gender categories
- Education - Primary or Less, Secondary, and Tertiary
- Income Quintile - Q1 Poorest through Q5 Richest
- Employment - In Workforce and Out of Workforce
- Residence - Urban and Rural
- Age Group - grouped respondent age bands
- Account Status - Account Owner or No Account
- Digital Payment Status - Digital Payment User or Non-Digital Payment
  User
- Digital Account Status - Digital Account or No Digital Account
- Internet Status - Internet User or Non Internet User
- Financial Behavior - Saver & Borrower, Saver Only, Borrower Only, or
  Neither
- Financial Engagement - Financially Excluded, Basic Access, or
  Digitally Active

Reusable functions were also created to calculate survey-weighted
percentages across demographic and behavioral groups.

5.  **Analysis:** The project combines descriptive, visual, and
    statistical analysis.

Methods used include:

- Survey weighted analysis to estimate population level percentages
- Demographic segmentation to compare financial outcomes across
  population groups
- Gap analysis to measure percentage point differences between the
  highest and lowest groups
- Behavioral segmentation to examine saving and borrowing patterns
- Cross tabulation to validate relationships between financial access
  and digital payment indicators
- Chi-square tests of independence to test categorical associations
- Cramér’s V to compare association strength
- Plotly visualizations to communicate major patterns and disparities

6.  **Output:** The analysis produces:

- weighted KPI summaries
- demographic comparison tables
- percentage point gap analyses
- financial behavior segments
- interactive Plotly visualizations
- statistical validation tables
- key findings and evidence summaries
- prioritized recommendations
- assumptions and limitations
- a documented Google Colab notebook containing the complete analytical
  workflow.

------------------------------------------------------------------------

## 6. Data Model & Schema

### Dataset / Table: `Global Findex 2025`

## Analysis Dataset

| Field                    | Type        | Description                                               | Example Value          |
|--------------------------|-------------|-----------------------------------------------------------|------------------------|
| `wpid_random`            | Identifier  | Unique respondent identifier                              | `123456789`            |
| `wgt`                    | Numeric     | Survey weight used for population level estimates         | `0.674757`             |
| `account`                | Binary      | Whether the respondent has a financial account            | `1`                    |
| `dig_account`            | Binary      | Whether the respondent has a digitally enabled account    | `1`                    |
| `anydigpayment`          | Binary      | Whether the respondent made or received a digital payment | `1`                    |
| `saved`                  | Binary      | Whether the respondent saved money                        | `1`                    |
| `borrowed`               | Binary      | Whether the respondent borrowed money                     | `1`                    |
| `internet_use`           | Binary      | Whether the respondent used the internet                  | `1`                    |
| `female`                 | Categorical | Raw gender variable                                       | `1`                    |
| `age`                    | Numeric     | Respondent age                                            | `32`                   |
| `educ`                   | Categorical | Raw education level code                                  | `2`                    |
| `inc_q`                  | Ordinal     | Income quintile from 1 (poorest) to 5 (richest)           | `3`                    |
| `emp_in`                 | Categorical | Raw workforce status variable                             | `1`                    |
| `urbanicity`             | Categorical | Raw residence classification                              | `2`                    |
| `Gender`                 | Derived     | Readable gender category                                  | `Female`               |
| `Education`              | Derived     | Readable education category                               | `Secondary`            |
| `Income_Quintile`        | Derived     | Readable income quintile category                         | `Q3 - Middle`          |
| `Employment`             | Derived     | Readable workforce status category                        | `In Workforce`         |
| `Residence`              | Derived     | Readable residence category                               | `Urban`                |
| `Age_Group`              | Derived     | Respondent age band                                       | `25-34`                |
| `Account_Status`         | Derived     | Readable financial account status                         | `Account Owner`        |
| `Digital_Account_Status` | Derived     | Readable digital account status                           | `Digital Account`      |
| `Digital_Payment_Status` | Derived     | Readable digital payment status                           | `Digital Payment User` |
| `Internet_Status`        | Derived     | Readable internet use status                              | `Internet User`        |
| `Saving_Status`          | Derived     | Readable saving behavior status                           | `Saved`                |
| `Borrowing_Status`       | Derived     | Readable borrowing behavior status                        | `Borrowed`             |
| `Financial_Behavior`     | Derived     | Combined saving and borrowing behavior                    | `Saver & Borrower`     |
| `Financial_Engagement`   | Derived     | Analytical financial engagement segment                   | `Digitally Active`     |

### Financial Engagement Definition

| Segment                  | Definition                                        | Example                            |
|--------------------------|---------------------------------------------------|------------------------------------|
| **Financially Excluded** | Does not own a financial account                  | `account = 0`                      |
| **Basic Access**         | Owns an account but does not use digital payments | `account = 1`, `anydigpayment = 0` |
| **Digitally Active**     | Owns an account and uses digital payments         | `account = 1`, `anydigpayment = 1` |

> **Note:** These financial engagement segments were created
> specifically for this analysis and are not official Global Findex
> classifications.

------------------------------------------------------------------------

## 7. Analysis & Metrics

**Analytical Approach & Framework**

The analysis follows three connected stages:

**Financial Access → Digital Activation → Financial Behavior**

### **Research Question 1 - Financial Access**

**Which demographic groups show the largest gaps in financial account
ownership?**

**Key Metric**

**Weighted Account Ownership Rate**

Weighted share of respondents within each demographic group who own a
financial account.

### Largest Observed Gaps

| Factor    | Lowest Group    | Lowest Rate | Highest Group | Highest Rate |          Gap |
|-----------|-----------------|------------:|---------------|-------------:|-------------:|
| Education | Primary or Less |      33.62% | Tertiary      |       82.15% | **48.53 pp** |
| Income    | Q1 – Poorest    |      33.05% | Q5 – Richest  |       64.47% | **31.42 pp** |
| Age       | 55–64           |      34.02% | 25–34         |       55.89% | **21.87 pp** |

### Statistical Validation

| Factor     | Cramér’s V | p-value |
|------------|-----------:|--------:|
| Education  |  **0.249** | \<0.001 |
| Income     |  **0.203** | \<0.001 |
| Employment |      0.151 | \<0.001 |
| Age        |      0.109 |   0.035 |
| Residence  |      0.056 |   0.075 |
| Gender     |      0.055 |   0.080 |

Education and income were the strongest observed demographic
associations with financial account ownership.

|                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \### **Research Question 2 - Digital Activation**                                                                                                                                                                                                                                                                                                          |
| Among account owners, which groups show the largest differences in digital payment adoption?                                                                                                                                                                                                                                                               |
| **Digital Activation Rate**                                                                                                                                                                                                                                                                                                                                |
| Among financial account owners:                                                                                                                                                                                                                                                                                                                            |
| \* 80.37% use digital payments. \* 19.63% remain digitally inactive.                                                                                                                                                                                                                                                                                       |
| \### Largest Observed Digital Adoption Gaps                                                                                                                                                                                                                                                                                                                |
| \| Factor \| Lowest Group \| Lowest Rate \| Highest Group \| Highest Rate \| Gap \| \|—\|—\|—:\|—\|—:\|—:\| \| Age \| 55–64 \| 50.04% \| 15–24 \| 94.33% \| **44.29 pp** \| \| Internet \| Non-Internet User \| 48.29% \| Internet User \| 87.52% \| **39.23 pp** \| \| Income \| Q1 – Poorest \| 53.17% \| Q2 – Lower Middle \| 86.42% \| **33.25 pp** \| |
| \### Statistical Validation                                                                                                                                                                                                                                                                                                                                |
| \| Factor \| Cramér’s V \| p-value \| \|—\|—:\|—:\| \| Age \| **0.370** \| \<0.001 \| \| Internet Usage \| **0.354** \| \<0.001 \| \| Residence \| 0.268 \| \<0.001 \| \| Income \| 0.246 \| \<0.001 \| \| Education \| 0.245 \| \<0.001 \| \| Gender \| 0.020 \| 0.651 \| \| Employment \| 0.014 \| 0.755 \|                                              |
| Age and internet usage were the strongest observed associations with digital payment adoption among account owners.                                                                                                                                                                                                                                        |

### **Research Question 3 - Financial Behavior**

How do saving and borrowing behaviors differ across financial engagement
levels?

### Financial Behavior Segments

| Behavior         | Weighted Share |
|------------------|---------------:|
| Saver & Borrower |     **40.49%** |
| Borrower Only    |     **31.48%** |
| Neither          |         14.88% |
| Saver Only       |         13.14% |

### Behavior by Financial Engagement

| Financial Engagement | Saving Rate | Borrowing Rate |
|----------------------|------------:|---------------:|
| Financially Excluded |      36.75% |         65.66% |
| Basic Access         |      42.95% |         66.50% |
| Digitally Active     |  **77.10%** |     **81.11%** |

Observed Gaps \* Saving gap: 40.35 percentage points \* Borrowing gap:
15.45 percentage points

### Statistical Validation

| Behavior  | Cramér’s V | p-value |
|-----------|-----------:|--------:|
| Saving    |  **0.313** | \<0.001 |
| Borrowing |  **0.145** | \<0.001 |

Financial engagement showed a substantially stronger association with
saving behavior than borrowing behavior.

------------------------------------------------------------------------

### Methods Used

| Method                              | Purpose                                                                       | Applied To                                                               |
|-------------------------------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| **Survey Weighted Analysis**        | Estimate percentages while accounting for respondent survey weights           | Account ownership, digital payment adoption, saving, and borrowing rates |
| **Descriptive Analysis**            | Summarize financial and demographic characteristics of respondents            | Overall financial inclusion indicators                                   |
| **Demographic Segmentation**        | Compare financial outcomes across population groups                           | Age, gender, education, income, employment, and residence                |
| **Behavioral Segmentation**         | Group respondents according to saving, borrowing and financial engagement     | Financial Behavior and Financial Engagement segments                     |
| **Percentage-Point Gap Analysis**   | Measure the difference between the highest and lowest performing groups       | Account ownership and digital payment adoption                           |
| **Cross Tabulation**                | Examine relationships between categorical financial indicators                | Account ownership, digital usage, saving, and borrowing                  |
| **Chi-Square Test of Independence** | Test whether categorical variables show statistically detectable associations | RQ1, RQ2, and RQ3                                                        |
| **Cramér’s V**                      | Measure and compare the strength of categorical associations                  | Demographic and behavioral factors                                       |
| **Data Visualization**              | Communicate patterns, gaps, and comparisons visually                          | KPI summaries and research question findings                             |
| **Evidence Synthesis**              | Combine descriptive and statistical evidence into actionable findings         | Final insights and recommendations                                       |

------------------------------------------------------------------------

## 8. Key Insights

**Insight 1: Education and income define the largest financial access
gaps**  
Account ownership varied substantially across socioeconomic groups, with
a **48.53 percentage point gap by education** and a **31.42
percentage point gap by income**. Statistical testing also identified
education and income as the strongest demographic associations with
account ownership, suggesting that financial access remains particularly
uneven across education and income levels.

**Insight 2: Account ownership does not guarantee digital
participation**  
Although **80.37% of account owners use digital payments**, **19.63%
remain digitally inactive**. This suggests that gaining access to a
financial account is only one stage of financial inclusion and that
digital activation should be considered separately from account
acquisition.

**Insight 3: Age and internet usage are key differentiators of digital
adoption**  
Among account owners, digital payment adoption showed a **44.29
percentage point gap across age groups** and a **39.23 percentage-point
gap between internet and non-internet users**. These were also the
strongest statistical associations with digital payment adoption,
suggesting that digital inclusion efforts may need to address
age-related and connectivity-related barriers.

**Insight 4: Financial engagement differentiates saving more strongly
than borrowing**  
Saving showed a **40.35 percentage point gap across financial engagement
levels**, compared with only **15.45 percentage points for borrowing**.
Borrowing remained relatively common even among financially excluded
respondents, suggesting that financial exclusion does not necessarily
mean financial inactivity and that inclusion should be evaluated across
multiple financial behaviors.

------------------------------------------------------------------------

## 9. Recommendations

| Priority   | Recommendation                                                                                                                                                 | Based On                                                                                      | Suggested Owner                         |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------|
| **High**   | Prioritize simplified and assisted financial access initiatives for lower education and lower-income groups                                                    | **Insight 1:** Education and income show the largest financial access gaps                    | Financial Inclusion / Retail Banking    |
| **High**   | Track digital activation separately from account acquisition and provide post opening support for digitally inactive account owners                            | **Insight 2:** 19.63% of account owners remain digitally inactive                             | Digital Banking / Customer Engagement   |
| **High**   | Strengthen assisted digital onboarding and digital literacy support for older and non internet users                                                           | **Insight 3:** Age and internet usage are key differentiators of digital adoption             | Digital Banking / Branch Operations     |
| **Medium** | Develop accessible saving initiatives for financially excluded and basic access groups                                                                         | **Insight 4:** Saving differs more strongly across financial engagement levels than borrowing | Deposits / Product Strategy             |
| **Low**    | Explore broader financial inclusion measures that combine account ownership, digital activity, saving, and borrowing rather than relying on a single indicator | **Insight 4:** Financial exclusion does not necessarily mean financial inactivity             | Financial Inclusion / Consumer Research |

------------------------------------------------------------------------

# 10. Assumptions & Limitations

### Assumptions

- **Survey weights represent the target population:** The provided
  survey weight (`wgt`) was treated as the appropriate weighting
  variable for calculating population-level descriptive percentages.

- **Source variable definitions are valid:** Variables such as account
  ownership, digital-payment usage, saving, borrowing, education,
  employment, and internet usage were interpreted according to the
  definitions and coding provided in the Global Findex dataset.

- **Binary indicators represent reported participation:** Variables such
  as `account`, `anydigpayment`, `saved`, and `borrowed` were treated as
  indicators of whether a respondent reported the corresponding
  financial behavior.

- **Financial engagement was simplified into three analytical
  segments:** Respondents were classified as **Financially Excluded**,
  **Basic Access**, or **Digitally Active** to support the analysis.
  These categories were created specifically for this project and are
  not official Global Findex classifications.

- **Demographic categories were grouped for analytical clarity:**
  Variables such as age, education, income, employment and residence
  were converted into readable categories or grouped bands to make
  comparisons easier to interpret.

- **Statistical significance was evaluated at the 5% level:** A p-value
  below **0.05** was used as the threshold for identifying statistically
  detectable associations in the sample.

### Limitations

- **The analysis is based on a cross-sectional survey:** The data
  captures respondents at a particular point in time. Therefore, the
  findings identify patterns and associations but cannot establish
  causal relationships.

- **The Philippine sample contains 1,000 respondents:** While survey
  weights were used for descriptive estimates, some subgroup results may
  be based on relatively small numbers of respondents and should be
  interpreted cautiously.

- **Financial behaviors are self-reported:** Responses related to
  saving, borrowing, account ownership, and digital payment usage may be
  affected by recall error, misunderstanding, or response bias.

- **Behavioral indicators provide limited detail:** Variables such as
  `saved`, `borrowed`, and `anydigpayment` indicate whether an activity
  occurred but do not capture its frequency, monetary value, duration,
  intensity, or financial outcome.

- **The statistical tests do not implement a full complex-survey
  design:** Chi-square tests and Cramér’s V were used as supplementary
  sample level association measures. A more rigorous inferential
  analysis would account for the complete survey design where the
  necessary design variables are available.

- **Potential confounding factors were not controlled simultaneously:**
  The analysis evaluates demographic and behavioral relationships
  primarily through segmentation and categorical association tests.
  Multivariable modeling could determine whether associations remain
  after controlling for other characteristics.

- **Country comparisons and time trends are outside the project scope:**
  The analysis focuses only on the Philippines and does not determine
  whether the observed patterns are unique relative to other countries
  or have changed over time.

- **Association should not be interpreted as causation:** For example,
  higher digital payment adoption among internet users does not
  demonstrate that internet usage directly causes digital payment
  adoption. Other demographic, socioeconomic or behavioral factors may
  contribute to the observed relationship.

------------------------------------------------------------------------

## 11. Future Enhancements

- [ ] Apply survey design aware statistical inference if full survey
  design variables become available.
- [ ] Build multivariable models for account ownership and digital
  payment adoption.
- [ ] Compare the Philippines with selected ASEAN economies.

------------------------------------------------------------------------

## 12. Deliverables

| Deliverable        | Description                                                                      | Location                                                    |
|--------------------|----------------------------------------------------------------------------------|-------------------------------------------------------------|
| Analysis Notebook  | Complete Python analysis, transformations, statistical tests and visualizations  | `notebooks/Financial_Inclusion_Philippines_Portfolio.ipynb` |
| GitHub README      | Executive case study and key findings                                            | `README.md`                                                 |
| Visualizations     | Portfolio-ready charts                                                           | `visuals/`                                                  |
| Data Documentation | Dataset source and field definitions                                             | `data/README.md` / `docs/data_dictionary.md`                |

------------------------------------------------------------------------

## 13. Author

**Clinton Taguba**

Data Analyst \| Aspiring Data Scientist & Data Engineer

- 🔗 https://www.linkedin.com/in/clintontaguba/
- 💼 https://clinttaguba-lab.github.io/
- 📧 tagubaclinton@gmail.com

------------------------------------------------------------------------

*Last updated: August 2026*
