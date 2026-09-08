# Transportation Operations & Performance Analytics

## Project Overview

This project analyzes 2025 U.S. airline operations data to identify performance bottlenecks, major delay drivers, high-risk periods, routes, and differences in airline performance.

The goal is to use data analysis to identify operational patterns and provide practical recommendations for improving on-time performance.

## Business Questions

1. When is the operation most vulnerable to arrival delays?
2. Which delay causes should be prioritized for operational improvement?
3. Which routes have the highest arrival delay rates?
4. Which airlines perform above or below the overall delay benchmark?

## Dataset

**Source:** U.S. Department of Transportation, Bureau of Transportation Statistics (BTS)

**Dataset:** Reporting Carrier On-Time Performance Data

**Period:** January–December 2025

The dataset contains airline flight operations information including scheduled and actual departure and arrival times, delays, cancellations, diversions, airports, routes, and major delay causes.

## Tools & Technologies

- Python
- Pandas
- Matplotlib
- DuckDB
- SQL
- Parquet
- Jupyter Notebook
- Git/GitHub

## Analysis Workflow

### 1. Data Quality & Preparation

The raw 2025 airline operations data was cleaned and prepared using Python and pandas. Missing values were investigated, cancelled and diverted flights were excluded from the main operational analysis, and additional features such as departure hour and route were created.

The final cleaned dataset was saved in CSV and Parquet formats.

### 2. Exploratory Analysis

The cleaned dataset was explored to identify patterns in arrival delays across time, airlines, routes, airports, and delay causes.

Monthly, airline, route, departure-hour, and weekday delay rates were compared. A minimum flight-count threshold was used for group-level comparisons where small samples could distort the results.

### 3. Business Analysis

The exploratory results were translated into four business questions focused on identifying high-risk periods, major delay drivers, high-risk routes, and differences in airline performance.

The analysis was used to develop operational interpretations and recommendations.

### 4. SQL Analysis

DuckDB was used to query the cleaned Parquet dataset directly with SQL.

SQL analysis was used to evaluate airline and route delay rates, monthly delay patterns, delayed flight counts, departure-hour performance, delay-cause impact, and airline-origin airport combinations. Group-level comparisons used a minimum flight-count threshold where appropriate to reduce the effect of small samples.

## Key Findings

- **July had the highest 15+ minute arrival delay rate**, at 6.58 percentage points above the annual average. June and December were also above the annual benchmark.
- **Late Aircraft Delay was the largest contributor to total delay minutes**, accounting for approximately 37% of total delay time. Carrier Delay was the second-largest contributor at approximately 31%.
- **ROA-SFB had the highest 15+ minute arrival delay rate among routes with at least 100 flights**, at approximately 67%. Several of the highest-delay routes involved SFB.
- **F9 had the highest arrival delay rate relative to the overall airline benchmark**, at 5.60 percentage points above the average. OH, B6, and AA were also above the benchmark, while HA was 5.03 percentage points below it.

## Recommendations

1. **Prioritize Late Aircraft Delay**

   Investigate late aircraft turnaround and scheduling factors because this delay category had the largest overall impact on total delay minutes.

2. **Increase Monitoring During High-Risk Periods**

   July and other periods with above-average delay rates should receive additional operational monitoring.

3. **Review High-Risk Routes**

   Routes with consistently high delay rates, particularly those involving SFB, should receive further operational investigation.

4. **Investigate Airlines Above the Benchmark**

   Airlines with higher-than-average delay rates should be reviewed to identify operational factors contributing to their performance differences.

## Repository Structure

```text
transportation-operations-analytics/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 01_data_quality.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   └── 03_business_analysis.ipynb
├── sql/
│   └── 04_sql_analysis.ipynb
├── requirements.txt
└── README.md

```

## Data Availability

The original and processed datasets are not included in this repository because of their large file size.

The analysis was performed using the 2025 Reporting Carrier On-Time Performance dataset from the U.S. Department of Transportation, Bureau of Transportation Statistics.

## How to Run

1. Clone the repository.
2. Install the required packages with `pip install -r requirements.txt`.
3. Run the notebooks in order:
   - `01_data_quality.ipynb`
   - `02_exploratory_analysis.ipynb`
   - `03_business_analysis.ipynb`
   - `04_sql_analysis.ipynb`

Because the datasets are not included in the repository due to their file size, the required data files must be available in the expected Data/ directory structure before running the notebooks.