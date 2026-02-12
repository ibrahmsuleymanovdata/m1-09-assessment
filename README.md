# Assessment | Air Quality Trends

## Overview

You are supporting a public health and urban planning team that needs a reliable analysis of daily air quality and weather conditions across multiple European cities. Your job is to clean imperfect data, analyze trends, and communicate findings with clear visuals and concise interpretations.

## Learning Goals

By the end of this mini-project, you should be able to:

- Load and inspect a real-world dataset with pandas
- Clean invalid and missing values responsibly
- Apply indexing, filtering, grouping, and reshaping
- Compute rolling statistics and event-based metrics
- Create clear visualizations and explain results

## Assessment Files

Use the files included in this repository:

- Dataset: `m1-09-assessment.csv`
- Starter notebook: `m1-09-assessment.ipynb`

## Tasks

### Part A: Core Data Handling

1. Load the CSV with date parsing and set `date` as a datetime index.
2. Inspect structure with `info()`, `describe()`, and missing-value counts.
3. Coerce invalid `pm25` strings to `NaN`.
4. Choose and apply a missing-value strategy for `pm25` and justify it.

### Part B: Required Analysis

5. Identify the city with the highest percentage of invalid/missing `pm25`.
6. Compute a 7-day rolling average of `pm25` per city and explain why this helps interpretation.
7. Define a percentile-based high-pollution threshold and count events per city.
8. Compare volatility between two cities using a metric you define and justify.
9. Create a month-by-city pivot table of average `pm25`.

### Part C: Aggregations

10. Compute average `pm25` by city.
11. Compute monthly average `pm25` per city.
12. Identify the hottest day (`max avg_temp_c`) per city.

### Part D: Visualization

13. Line plot of monthly `pm25` trends for at least two cities.
14. Bar chart of overall average `pm25` by city.
15. One additional plot of your choice.

### Part E: Interpretation Questions

Answer briefly (no code):

1. Which city has the most persistent high `pm25`, and why?
2. How does missing/invalid data affect confidence in results?
3. Does temperature appear related to `pm25` in your analysis?
4. What is one limitation of daily averages for policy decisions?
5. What additional dataset would improve this analysis, and why?

## Hints

- Use `pd.read_csv(..., parse_dates=["date"])` and `set_index("date")`.
- Use `pd.to_numeric(..., errors="coerce")` for invalid strings.
- `groupby(["city", pd.Grouper(freq="M")])` is useful for monthly aggregation.
- `pivot_table` works well for month-by-city summaries.
- Apply rolling windows after sorting by date.

## Common Pitfalls

- Not setting a datetime index before rolling/resampling.
- Using the wrong denominator when computing missing-data percentages.
- Mixing pre-cleaning and post-cleaning values in the same metric.

## Submission

### What to submit

- Completed `m1-09-assessment.ipynb`

### Git workflow

1. Fork this repo to your GitHub account.
2. Clone your fork locally.
3. Complete the notebook.
4. Commit and push your work:

```bash
git add .
git commit -m "Solve m1-09 assessment"
git push -u origin HEAD
```

5. Open a Pull Request from your fork to your own default branch.
6. Submit the **Pull Request URL** in the Student Portal field for this assessment.
