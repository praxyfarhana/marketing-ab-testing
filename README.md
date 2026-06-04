# Marketing A/B Testing Analysis

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-CC0%20Public%20Domain-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Table of Contents
- [Background](#background)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Installation & Setup](#installation--setup)
- [Analysis Workflow](#analysis-workflow)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Conclusions](#conclusions)
- [Author](#author)

---

## Background

Marketing companies invest heavily in advertising campaigns 
to attract and convert potential customers. However, the 
market is complex and several campaign strategies can work 
simultaneously, making it difficult to determine which 
approach delivers the maximum impact.

To navigate this complexity, companies rely on data-driven 
decision making through **A/B testing** — a randomized 
experimentation process where two or more versions of a 
variable such as a web page, banner, or page element are 
shown to different segments of people at the same time 
to identify which version drives the most engagement 
and business metrics.

---

##  Problem Statement

This project seeks to answer two critical business questions:

- **Would the campaign be successful?**
- **If the campaign was successful, how much of that 
  success could be attributed to the ads?**

To answer these questions, an A/B test was conducted where:
- The **majority of users** were exposed to advertisements 
  (experimental group)
- A **smaller portion of users** saw a Public Service 
  Announcement or nothing at all (control group)

---

## Dataset

- **Source:** [Marketing A/B Testing — Kaggle](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing)
- **Author:** Favio Vázquez
- **License:** CC0 Public Domain
- **Size:** 588,101 rows × 6 columns

### Data Dictionary

| Column | Type | Description |
|---|---|---|
| `user id` | Integer | Unique identifier for each user |
| `test group` | String | `ad` = saw advertisement, `psa` = saw PSA |
| `converted` | Boolean | `True` = made a purchase, `False` = did not |
| `total ads` | Integer | Total number of ads seen by user |
| `most ads day` | String | Day user saw the most ads |
| `most ads hour` | Integer | Hour user saw the most ads |

---

## Project Structure
ab_testing_project/
│
├── notebooks/
│   └── marketing_ab_testing.ipynb   # Main analysis notebook
│
├── README.md                         # Project documentation

---

##  Technologies Used

| Tool | Version | Purpose |
|---|---|---|
| Python | 3.12 | Programming language |
| Jupyter Notebook | 7.5.6 | Development environment |
| pandas | 2.x | Data manipulation |
| numpy | 2.x | Numerical computing |
| matplotlib | 3.x | Data visualization |
| seaborn | 0.x | Statistical visualization |
| scipy | 1.x | Chi-square hypothesis testing |
| kagglehub | 0.3.4 | Kaggle API integration |

---

##  Installation & Setup

### Prerequisites
- Python 3.12+
- Jupyter Notebook
- Kaggle Account & API Token

### Step 1 — Clone the Repository
```bash
git clone https://github.com/yourusername/marketing-ab-testing.git
cd marketing-ab-testing
```

### Step 2 — Install Required Libraries
```bash
pip install kagglehub==0.3.4 pandas numpy matplotlib seaborn scipy notebook
```

### Step 3 — Set Up Kaggle API Token
- Go to **Kaggle → Settings → API Tokens**
- Click **Generate New Token**
- Copy the token and add it to the notebook

### Step 4 — Launch Jupyter Notebook
```bash
jupyter notebook
```

### Step 5 — Open the Notebook
Navigate to `notebooks/marketing_ab_testing.ipynb` 
and run all cells.

---

##  Analysis Workflow
1. Environment Setup & API Configuration
        ↓
2. Import Libraries
        ↓
3. Load Dataset via Kaggle API
        ↓
4. Data Exploration
   ├── Shape & Structure
   ├── Data Types
   ├── Missing Values
   ├── Duplicates
   └── Summary Statistics
        ↓
5. Data Cleaning
   ├── Verify column integrity
   └── Remove outliers (IQR method)
        ↓
6. Visualizations
   ├── Distribution of Test Groups
   ├── Conversion Rate by Test Group
   ├── Total Ads Distribution
   ├── Conversions by Day of Week
   └── Conversions by Hour of Day
        ↓
7. Hypothesis Testing
   ├── Build Contingency Table
   ├── Run Chi-Square Test
   ├── Interpret Results
   └── Observed vs Expected Analysis
        ↓
8. Conclusions & Business Recommendations

---

## Key Findings

### Dataset After Cleaning
| Metric | Value |
|---|---|
| Total Users | 536,044 |
| Ad Group | 514,716 (96.02%) |
| PSA Group | 21,328 (3.98%) |
| Outliers Removed | 52,057 (8.85%) |
| Data Retained | 91.15% |

### Conversion Rates
| Group | Conversions | Rate |
|---|---|---|
| Ad Group | 6,889 | 1.34% |
| PSA Group | 226 | 1.06% |
| **Difference** | **+57** | **+0.28%** |

### Chi-Square Test Results
| Metric | Value |
|---|---|
| Chi-Square Statistic | 11.9396 |
| P-Value | 0.0005 |
| Degrees of Freedom | 1 |
| Significance Level | 0.05 |
| **Result** | **Reject Null Hypothesis ✅** |

### Best Days for Conversions
| Day | Conversions | Rank |
|---|---|---|
| Monday | 1,368 | 🥇 1st |
| Tuesday | 1,104 | 🥈 2nd |
| Sunday | 1,023 | 🥉 3rd |
| Saturday | 798 | Lowest |

### Peak Hours for Conversions
| Hour | Time | Conversions |
|---|---|---|
| 14 | 2:00 PM | 609 |
| 15 | 3:00 PM | 609 |
| 16 | 4:00 PM | 571 |

---

##  Business Recommendations

| Recommendation | Action | Reason |
|---|---|---|
| Continue running ads | Scale the campaign | Statistically proven to work |
| Focus on Mondays | Increase Monday ad spend | Highest conversion day (1,368) |
| Schedule ads 12PM - 4PM | Peak conversion window | 609 conversions at 2PM-3PM |
| Reduce Saturday spend | Lower Saturday budget | Lowest conversion day (798) |
| Avoid overnight ads | Pause ads 3AM - 7AM | Very low conversions overnight |

---

##  Conclusions

The chi-square test returned a **p-value of 0.0005** — 
far below the significance level of 0.05. We therefore 
**reject the null hypothesis** and conclude that:

> **Ads have a statistically significant impact on 
> customer conversions. The campaign is successful 
> and the observed difference is not due to random chance.**

The company can confidently invest in and scale this 
advertising campaign. Strategic scheduling of ads on 
**Mondays between 12PM and 4PM** is recommended to 
maximize conversion rates and return on investment.

---

##  Author

**Farhana Praxy**
- Kaggle: [@farhanapraxy](https://www.kaggle.com/farhanapraxy)

---

## Acknowledgements

- Dataset provided by [Favio Vázquez](https://www.kaggle.com/faviovaz) on Kaggle
- Inspired by the WorldQuant University 
  Applied Data Science Lab A/B Testing project

