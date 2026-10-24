# Placement Data Analysis: Descriptive Stats, Outliers & Seaborn Charts

A Jupyter/Colab notebook that explores a campus placement dataset with **Pandas** and **Seaborn**. It builds descriptive statistics and outlier detection from scratch, then visualizes the data with univariate, bivariate and categorical plots.

## Dataset

`Placement.csv`: 215 students, 15 columns.

| Column | Type | Description |
|--------|------|-------------|
| sl_no | Quantitative | Serial number (ID) |
| gender | Qualitative | M / F |
| ssc_p, hsc_p, degree_p | Quantitative | Secondary, higher secondary and degree percentages |
| ssc_b, hsc_b | Qualitative | Board of education (Central / Others) |
| hsc_s | Qualitative | Higher secondary stream (Commerce / Science / Arts) |
| degree_t | Qualitative | Degree type (Comm&Mgmt / Sci&Tech) |
| workex | Qualitative | Work experience (Yes / No) |
| etest_p | Quantitative | Employability test percentage |
| specialisation | Qualitative | MBA specialisation (Mkt&HR / Mkt&Fin) |
| mba_p | Quantitative | MBA percentage |
| status | Qualitative | Placed / Not Placed |
| salary | Quantitative | Salary offered (67 missing values) |

## What the Notebook Does

1. **Load and inspect:** `read_csv`, `columns`, `isnull().sum()`, `info()`, `shape`
2. **Classify columns:** a reusable `QuanQual(dataset)` function splits columns into quantitative and qualitative by dtype
3. **Descriptive statistics table:** built manually with mean, median, mode, min, quartiles, max, IQR, and lower and upper outlier limits
4. **Outlier handling:** detects values outside the IQR limits (using 1.6 × IQR) and caps them at the limit
5. **Seaborn visualizations:**

| Type | Plots |
|------|-------|
| Univariate | `distplot` (histogram + KDE) of `ssc_p` |
| Bivariate | `jointplot` (scatter and KDE) of `ssc_p` vs `salary`, `pairplot` colored by gender |
| Categorical | `stripplot`, `swarmplot` |
| Distribution | `violinplot`, `boxplot` |
| Comparison | `barplot`, `countplot`, `pointplot` |
| Overview | Horizontal `boxplot` of all numeric columns |

## Key Observations

- Salary has the largest outliers: the maximum is 940,000 against a median of 265,000.
- The salary mean (288,655) sits above the median (265,000), which indicates right skew.
- Capping salary at the upper outlier limit (396,000) lowers the mean to about 278,236 while the median stays at 265,000.
- Salary is missing for 67 students, so averages only cover students with a recorded salary.
- Both boards have more male than female students in the count plots.



## Project Structure

```
.
├── QuanQual_seaborn_chart.ipynb   # Main notebook
├── Placement.csv                  # Dataset
└── README.md
```

## Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Google Colab



