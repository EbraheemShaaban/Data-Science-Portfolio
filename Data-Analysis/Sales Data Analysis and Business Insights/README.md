# Sales Data Analysis and Business Insights Using Python

## Overview

This project explores 2019 monthly sales records to identify revenue patterns, product performance, geographic trends, purchase timing, and products frequently purchased together. The notebook follows a reproducible workflow: load the source files, validate and clean records, engineer analytical features, calculate KPIs, visualize patterns, and export summary tables.

> **Dataset note:** The source CSV files are not included in this repository. Add the 12 original monthly files to a `dataset/` directory before running the notebook.

## Business Questions

- Which month generated the highest revenue?
- Which city contributed the most revenue?
- At what hours and on which weekdays were the most order-line records observed?
- Which product pairs appeared together in the same order most often?
- Which products led by units sold, and which led by revenue?
- What data-quality issues should be reviewed before making decisions?

## Features

- **Data consolidation:** combines files matching `Sales_*_2019.csv`, without accidentally reading generated output files.
- **Data quality checks:** detects repeated header rows, reports invalid records and non-positive quantities/negative prices, and reports exact duplicate business rows for review.
- **Feature engineering:** derives revenue, month, city/state, hour, weekday, and date.
- **Business KPIs:** calculates total revenue, unique orders, units sold, and average order value.
- **Exploratory data analysis:** visualizes monthly revenue, city revenue, hourly activity, weekday revenue, and product performance.
- **Market basket analysis:** counts product pairs at the order level and calculates support, directional confidence, and lift.
- **Reusable outputs:** exports cleaned records and analysis tables as CSV files.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Project Structure

```text
Sales_Analysis_Enhanced/
├── Sales_Analysis_Enhanced.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── dataset/                 # Add the 12 original monthly CSV files here
└── outputs/                 # Created when the notebook runs
```

## Getting Started

### 1. Set up Python

Python 3.10 or later is recommended.

```bash
python -m venv .venv
```

Activate the environment:

**Windows**
```bash
.venv\Scripts\activate
```

**macOS/Linux**
```bash
source .venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Add the data

Create a `dataset/` directory beside the notebook and place the original monthly files inside it. Expected names look like:

```text
dataset/
├── Sales_January_2019.csv
├── Sales_February_2019.csv
└── ... remaining monthly files ...
```

The notebook expects these columns:

`Order ID`, `Product`, `Quantity Ordered`, `Price Each`, `Order Date`, `Purchase Address`

### 4. Run the notebook

```bash
jupyter notebook Sales_Analysis_Enhanced.ipynb
```

Run the cells from top to bottom. The notebook stops with a clear error if the dataset directory, matching CSV files, or required columns are missing.

## Generated Outputs

The notebook creates an `outputs/` directory with:

- `cleaned_sales_data.csv`
- `sales_kpis.csv`
- `monthly_sales_summary.csv`
- `city_sales_summary.csv`
- `hourly_sales_summary.csv`
- `weekday_sales_summary.csv`
- `product_performance.csv`
- `market_basket_pairs.csv` (when at least one order contains two or more distinct products)

These files are generated when you run the notebook; no performance figures are hard-coded in this README.

## Methodology Notes

- Invalid required values are excluded from the analysis after being counted and reported.
- Exact duplicate business rows are reported but not automatically removed, because duplicate-looking line items may require source-system review.
- Products are deduplicated within each order for pair analysis to reduce inflated pair counts.
- **Support** is the proportion of orders containing both products.
- **Confidence A → B** is the proportion of orders containing product A that also contain product B.
- **Lift** compares the observed pair frequency with the frequency expected if the two products were independent. A lift above 1 indicates a positive association in this dataset, not causation.
- Hourly counts describe recorded order-line rows; they should not automatically be interpreted as unique orders or proof of the best time to advertise.
- Since the data covers 2019 only, it supports comparisons among months in that year, not year-over-year seasonality claims.

## Limitations and Next Steps

- Findings depend on the quality, coverage, and definitions in the supplied dataset.
- Address parsing assumes a conventional US-style address format; malformed or nonstandard addresses may have an unknown city/state.
- Purchase timing is descriptive. Advertising recommendations should ideally be validated with controlled experiments.
- The data does not include advertising spend, margin, customer identifiers, or campaign outcomes, so return on ad spend and customer-level analysis are out of scope.
- For further development, results can be presented in an interactive Power BI dashboard and validated against business definitions.

## Attribution

This work is an enhanced educational adaptation of the sales-analysis project by [Sinjoy Saha](https://github.com/sinjoysaha/sales-analysis). Preserve appropriate attribution and review the original repository's license and the dataset's terms before redistributing or publishing a derivative. The enhancements in this version include data-quality reporting, KPI exports, weekday analysis, product revenue/volume summaries, and order-level market-basket metrics.

## CV Description

**Sales Data Analysis and Business Insights | Python, Pandas, NumPy, Matplotlib**

- Cleaned and consolidated 12 monthly sales files, engineered analytical features, and calculated core sales KPIs.
- Used EDA and visualizations to compare revenue by month/city, product performance, and purchase timing.
- Implemented order-level product-pair analysis using support, confidence, and lift, and exported results for reporting.
