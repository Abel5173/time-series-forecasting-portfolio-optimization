# Time Series Forecasting and Portfolio Optimization

Implementation for the GMF Investments challenge (Tenx Platform).

## Overview

This repository contains code and notebooks for downloading market data (TSLA, BND, SPY), preprocessing, exploratory data analysis (EDA), time series forecasting, future projections, portfolio optimization, and simple backtesting. The working date range in the notebooks is 2015-07-01 to 2025-07-31.

## Structure

- `data/` – Historical CSVs saved by the notebooks.
- `notebooks/` – Jupyter notebooks for Tasks 1–5.
  - `task1_data_preprocessing.ipynb` – Data fetching, cleaning, and EDA.
  - `task2_forecasting_models.ipynb` – Baseline ARIMA/LSTM for TSLA.
  - `task3_future_forecast.ipynb` – 12‑month TSLA forecast.
  - `task4_portfolio_optimization.ipynb` – Efficient Frontier and portfolio weights.
  - `task5_backtesting.ipynb` – Backtest vs benchmark.
- `reports/` – Plots and figures (forecast, Efficient Frontier, backtest).
- `requirements.txt` – Project dependencies.

## Setup

```bash
# (Recommended) Create a virtual environment
python3 -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

## Requirements

- Python 3.12+
- Libraries (see `requirements.txt`):
  - yfinance, pandas, numpy, matplotlib, seaborn
  - statsmodels, scikit-learn, pmdarima
  - tensorflow/keras (for LSTM), PyPortfolioOpt
  - jupyter

## How to Run

1. Install dependencies: `pip install -r requirements.txt`.
2. Open and run the notebooks in `notebooks/` in order.
3. Data downloaded by the notebooks is saved under `data/` (paths are set relative to the `notebooks/` folder).

## Notes

- yfinance’s `download` now defaults to `auto_adjust=True`; adjusted prices are accessible via the `Close` column.
- When downloading multiple tickers, yfinance returns a multi-index column DataFrame; the notebooks handle flattening/selection internally.
