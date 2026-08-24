# Market Regime & Correlation Analysis

A beginner-friendly Jupyter notebook that downloads real index data with
[`yfinance`](https://pypi.org/project/yfinance/), classifies each trading day into a simple
market regime, and analyzes how three major indices move together over time.

**Indices:** NIFTY 50 (`^NSEI`), S&P 500 (`^GSPC`), NASDAQ (`^IXIC`)

## Market Regimes

Each trading day is classified into one of three regimes using a simple rule based on a
50-day moving average and 21-day rolling (annualized) volatility:

- **Bull Market** — price above its 50-day moving average and volatility is not elevated
- **High Volatility / Stress Market** — rolling volatility is in the top 25% of that
  index's own history
- **Normal Market** — everything else

## What's inside

The notebook (`Market_Regime_Correlation_Analysis.ipynb`) walks through 11 sections:

1. Introduction
2. Data collection
3. Daily returns
4. Market regime classification
5. Correlation matrix
6. Rolling correlation (30-day: NIFTY 50 vs S&P 500, NIFTY 50 vs NASDAQ)
7. Rolling volatility
8. Distribution of returns
9. Positive vs negative days
10. Drawdowns
11. Summary

All the code is written to be simple and readable, with a comment or markdown
explanation above every step.

## Getting started

### 1. Install the required packages

```bash
pip install -r requirements.txt
```

### 2. Launch Jupyter

```bash
jupyter notebook
```

Then open `Market_Regime_Correlation_Analysis.ipynb` and run all cells (`Cell > Run All`).

> **Note:** This notebook needs an active internet connection, since it downloads
> live data from Yahoo Finance each time you run it. Results will look different
> every time you re-run it, since the market keeps moving.

## Project structure

```
market-regime-correlation-analysis/
├── Market_Regime_Correlation_Analysis.ipynb   # the main notebook
├── build_notebook.py                          # script that generates the notebook
├── requirements.txt                           # Python dependencies
├── data/                                      # (optional) folder for saved CSV exports
├── README.md
└── .gitignore
```

## Customizing it

Want to explore a different regime rule or more indices? Open Section 2 ("Data
collection") to add tickers, or Section 4 ("Market regime classification") to adjust
the moving-average window, volatility window, or stress-quantile threshold.
