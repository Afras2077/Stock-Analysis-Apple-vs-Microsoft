# Stock Analysis: Apple vs Microsoft

A Jupyter notebook that pulls live stock data for Apple (AAPL) and Microsoft (MSFT) and runs a comparative analysis of price trends, daily returns, volatility, and risk-adjusted performance.

## What it does

1. **Pulls live data** from Yahoo Finance via `yfinance` — current price, market cap, P/E ratio, dividend yield, and 6 months of historical closing prices for both tickers.
2. **Visualizes prices** — a bar chart of current prices and a line chart of 6-month closing price trends.
3. **Computes daily returns** and compares them statistically:
   - Two-sample t-test (Welch's) to test whether AAPL and MSFT have significantly different mean daily returns
   - Histograms of each stock's return distribution
   - Volatility (standard deviation of returns) for each stock
   - Correlation between the two return series
4. **Runs a regression** (OLS) to test whether MSFT's returns predict AAPL's returns, with a scatter plot and fitted line.
5. **Risk-adjusted performance** — annualized Sharpe ratio for each stock.
6. **Cumulative returns** — growth of $1 invested in each stock over the period.
7. **Rolling volatility** — 20-day rolling standard deviation, showing how risk shifted over time rather than a single static number.

## Key findings

- No statistically significant difference in mean daily returns between AAPL and MSFT over the 6-month window (p > 0.05).
- MSFT showed higher volatility than AAPL — the riskier stock in this window, though higher risk doesn't necessarily mean higher reward.
- The relationship between AAPL and MSFT returns is positive but weak — MSFT's returns are not a reliable predictor of AAPL's daily performance (low R², p > 0.05).

## Requirements

yfinance
pandas
matplotlib
scipy
statsmodels

## Install with:

```bash
pip install yfinance pandas matplotlib scipy statsmodels
```

## Running it

Open `stock_analysis.ipynb` in Jupyter and run all cells top to bottom:

```bash
jupyter notebook stock_analysis.ipynb
```

Data is pulled live from Yahoo Finance, so prices and stats will reflect whatever the current 6-month window looks like at the time you run it — exact numbers in the markdown commentary cells may drift from what's printed if re-run later.
