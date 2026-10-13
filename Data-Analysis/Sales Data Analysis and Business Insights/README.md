# Sales Data Analysis and Business Insights

## Overview

This project explores 2019 monthly sales records to identify revenue patterns, product performance, geographic trends, purchase timing, and products frequently purchased together. The notebook follows a reproducible workflow: load the source files, validate and clean records, engineer analytical features, calculate KPIs, visualize patterns, and export summary tables.


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

##  Outputs

The notebook creates an `outputs/` directory with:

- `cleaned_sales_data.csv`
- `sales_kpis.csv`
- `monthly_sales_summary.csv`
- `city_sales_summary.csv`
- `hourly_sales_summary.csv`
- `weekday_sales_summary.csv`
- `product_performance.csv`
- `market_basket_pairs.csv` (when at least one order contains two or more distinct products)

