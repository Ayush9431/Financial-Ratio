# Company Financial Ratio Screener

A Python-based screener that pulls real financial statement data for 10 companies across four sectors and compares them using four core financial ratios — built to practice combining finance fundamentals with data analysis.

## What this project does

- Pulls live balance sheet and income statement data via the `yfinance` API
- Calculates four key financial ratios for each company:
  - **Return on Equity (ROE)** — profitability relative to shareholder equity
  - **Current Ratio** — short-term liquidity
  - **Debt-to-Equity** — financial leverage and risk
  - **Net Profit Margin** — how much revenue converts to profit
- Compares companies across four sectors: **Technology, Banking, UK Consumer, and Energy**
- Visualizes each ratio with bar charts
- Flags cases where a ratio isn't meaningfully comparable (e.g. banks and the Current Ratio) rather than forcing a number that would be misleading

## Companies covered

| Sector | Companies |
|---|---|
| Technology | Apple, Microsoft, Meta, Tesla |
| Banking | JPMorgan, HSBC, Barclays |
| UK Consumer | Unilever, Tesco |
| Energy | Shell |

## Key findings

- **Technology** shows the strongest overall profitability, with Microsoft posting the highest Net Profit Margin in the dataset (~40.3%) and Apple showing an exceptionally high ROE (~151.9%) — though the latter is partly a function of a low equity base from years of share buybacks, not purely operational efficiency.
- **Banks** post strong Net Profit Margins (~25-31%) but carry by far the highest leverage (Barclays' Debt-to-Equity ~2.83) — a reflection of how banking balance sheets are structured, not a red flag on its own. Current Ratio was excluded for banks, since the conventional current-assets/current-liabilities framework doesn't map onto how banks report.
- **UK Consumer** companies show the weakest liquidity of the non-bank group (Tesco's Current Ratio ~0.59), with Unilever and Tesco diverging sharply on profitability (~18.7% vs ~2.4% Net Profit Margin).
- **Shell** combines comparatively low leverage (~0.43 Debt-to-Equity) with more modest profitability (~6.7% Net Profit Margin), reflecting the capital-intensive, cyclical nature of the energy sector.
- **The overarching lesson:** ratios can't be judged in isolation or without sector context — a Debt-to-Equity ratio that's normal for a bank would be a warning sign for a tech company, and vice versa for liquidity expectations.

Full sector-by-sector analysis and a summary comparison table are included in the notebook.

## Tools used

- Python, pandas, matplotlib
- `yfinance` for live financial statement data
- Jupyter Notebook

## How to run

1. Clone this repo
2. Install dependencies: `pip install yfinance pandas matplotlib jupyter`
3. Open `Analysis_Financial_Ratio.ipynb` in Jupyter and run all cells

Note: since this pulls live data from Yahoo Finance, exact figures will differ slightly from the values quoted above depending on when it's run (most recent reporting period at time of execution).

## Notes

This project was built while learning to combine Python/pandas with core finance concepts - data cleaning decisions (like excluding banks from the Current Ratio) were made deliberately to keep comparisons meaningful rather than mechanically applying every ratio to every company.
