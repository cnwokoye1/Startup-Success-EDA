# Startup Success Analysis (EDA Project)

This project explores factors associated with startup success using a real-world dataset
spanning 20+ years of startup activity. The analysis applies end-to-end
exploratory data analysis (EDA) techniques to prepare the dataset for future modeling tasks.

---

## Objectives

- Investigate relationships between funding history, location, milestones, and startup outcomes.
- Identify correlations and distribution patterns across numerical features.
- Examine categorical trends such as geographic and industry-based success rates.
- Demonstrate a multi-tool analytics workflow using Python and SQL.

---

## Dataset

The dataset includes the following features:
- Geographic information (state, city, latitude, longitude)
- Founding and funding timelines
- Funding totals and funding rounds
- Business milestones and relationships
- Industry classifications
- A binary outcome label reflecting startup success or closure

---

## Tools & Technologies

- **Python:** `pandas`, `numpy`
- **Visualization:** `matplotlib`, `seaborn`
- **Feature Encoding:** `scikit-learn`
- **SQL:** Query-based aggregation and feature engineering (documented in notebook)

---

## Key Steps Performed

### Data Preprocessing
- Removed unnecessary and duplicated columns
- Identified and handled missing values
- Selected and verified numeric feature sets
- Encoded binary classification labels

### EDA & Visualization
- Generated distributions and skew metrics for all numerical features
- Detected outliers via box plots
- Examined correlations using heatmaps
- Analyzed relationships between geography, milestones, and startup success

### SQL Simulation
- Developed SQL queries to aggregate:
  - Success rates by industry
  - Average funding per round
  - Geographic startup performance summaries
- Demonstrated how SQL-generated features would be merged into pandas workflows.

### Modeling Readiness
Outlined a complete pipeline including:
- SQL-driven feature engineering
- Class balancing
- Feature normalization
- Baseline classifier training

---

## Sample SQL Queries

```sql
SELECT category_code,
       COUNT(*) AS startups,
       SUM(labels) AS successful,
       ROUND(100.0 * SUM(labels) / COUNT(*),2) AS success_rate
FROM startups
GROUP BY category_code;
