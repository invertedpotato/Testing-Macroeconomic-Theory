# Empirical Examination of Macroeconomic Theories

This Jupyter notebook empirically examines some macroeconomic theories using real-world U.S. data from 1980-2024. This analysis is meant to see how well these theories hold up in practice, by not only examining whether there is a statistically significant relationship between any two variables, but also how well one variable can explain the variation in the other variable(by computing the R-squared value).
## Overview

This project empirically tests the following macroeconomic theories:

| # | Theory | Hypothesis |
|---|--------|------------|
| 1 | **IS Curve** | Higher interest rates → Lower investment (negative relationship) |
| 2 | **Labor Market Theory** | Higher production → Higher employment (positive relationship) |
| 3 | **LM Curve / Money Demand** | Income ↑ → Money Demand ↑; Interest Rate ↑ → Money Demand ↓ |
| 4 | **Phillips Curve** | Lower unemployment → Higher inflation (negative relationship) |
| 5 | **Quantity Theory of Money** | Higher money supply growth → Higher inflation (positive relationship) |

## Data Sources

All data is fetched directly from the Federal Reserve Economic Data (FRED) API using `pandas_datareader`. Key datasets include:

| FRED Code | Description |
|-----------|-------------|
| **M2SL** | M2 Money Supply (broad money) |
| **CPIAUCSL** | Consumer Price Index (inflation measure) |
| **INDPRO** | Industrial Production Index |
| **PAYEMS** | Total Nonfarm Payroll Employment |
| **UNRATE** | Civilian Unemployment Rate |
| **TB3MS** | 3-Month Treasury Bill Rate |
| **GDP** | Gross Domestic Product (for velocity calculation) |

## Key Findings

| Theory | Expected Relationship | Result | Statistical Significance | R² |
|--------|---------------------|--------|-------------------------|-----|
| IS Curve | Interest Rate ↓ → Investment ↑ | ✓ Supported | p < 0.001 | 0.51 |
| Labor Market | Production ↑ → Employment ↑ | ✓ Supported | p < 0.001 | 0.55 |
| Money Demand (Income) | Income ↑ → Money Demand ↑ | ✓ Supported | p < 0.001 | — |
| Money Demand (Interest) | Interest Rate ↑ → Money Demand ↓ | ✗ Not supported | p = 0.202 | — |
| Phillips Curve | Unemployment ↓ → Inflation ↑ | ✗ Not supported | p = 0.599 | ≈ 0 |
| Quantity Theory (Pre-2008) | M2 Growth ↑ → Inflation ↑ | ✓ Supported | p = 0.006 | 0.023 |
| Quantity Theory (Post-2008) | M2 Growth ↑ → Inflation ↑ | ✗ Not supported | p = 0.035 (negative slope) | 0.023 |


## Requirements

- Python 3.8+
- pandas
- numpy
- statsmodels
- matplotlib
- fredapi (for FRED API access)

## Author

Ashvin Budhiraja | ashvinbudhiraja9@gmail.com | 
