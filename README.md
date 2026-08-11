# Stack Overflow 2019 Developer Survey Analysis

A pandas-based exploratory analysis of the [Stack Overflow 2019 Annual Developer Survey](https://survey.stackoverflow.co/2019), looking at developer salaries, demographics, and roles across ~89,000 respondents worldwide.

## What this project does

- Loads and cleans the raw survey data (handling missing values and a salary-cap data artifact)
- Analyzes average developer salary by country
- Filters and compares respondents by role (e.g., developers vs. non-developers)
- Visualizes salary distribution and top-paying countries

## Key findings

- **Salary rises steadily with experience, but plateaus and gets noisier after ~20 years.** Average salary climbs from ~\$57,500 for those under 1 year of professional coding experience to ~\$163,600 at 20 years — but beyond that, averages swing unpredictably (e.g. dropping to \$118k at 29 years), likely due to shrinking sample sizes at the high end.

- **Doctoral degree holders report the highest median salary (\$80,371)**, notably higher than Bachelor's (\$58,634) or Master's (\$57,372) holders — a surprising gap given Master's degrees are often assumed to out-earn Bachelor's on average.

- **"Full-stack developer" is the single most common role**, with 8,433 respondents identifying as such — more than double the next most common single role ("Developer, back-end" at 4,913).

- **Andorra and Australia rank among the highest-paying countries for developers** (~\$161k and ~\$169k average respectively after cleaning), though small-sample countries like Andorra should be treated with caution given low respondent counts.

- **A salary-cap data artifact required cleaning before any of the above was reliable.** Several respondents' salaries were capped at exactly \$2,000,000 USD due to a likely "Weekly" vs "Yearly" pay-frequency mix-up during survey completion; these rows were filtered out (`ConvertedComp < 2,000,000`) before computing any averages.

## Tools used

- Python, pandas, matplotlib
- Jupyter Notebook

## Data source

Stack Overflow Developer Survey 2019, publicly available under the [Open Database License (ODbL)](https://opendatacommons.org/licenses/odbl/1-0/).

## How to run

1. Clone this repo
2. Install dependencies: `pip install pandas matplotlib jupyter`
3. Download the [2019 survey CSV](https://survey.stackoverflow.co/?_ga=2.133514379.488281014.1786185283-1880181986.1785681186) and place it in a `Data/` folder
4. Open `Pandas_Project.ipynb` in Jupyter and run all cells

## Notes

This project was built while learning pandas and data analysis fundamentals. Feedback and suggestions welcome.
