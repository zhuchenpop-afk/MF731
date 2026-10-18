# MF 731 — Corporate Risk Management

Code accompanying the written homework submissions. Each notebook is
self-contained and runs top to bottom.

## Contents

| File | Assignment | What it does |
|---|---|---|
| `volatility_homework_1.ipynb` | SPY volatility | MA(100) and EWMA(0.94) volatility, GARCH(1,1) fitted by maximum likelihood, 100 simulated forecast paths |
| `loss_homework.ipynb` | Loss distribution | Full, linearized and second-order loss operators for a delta-hedged short put; loss distribution by Monte Carlo, N = 100,000 |
| `var_est_homework/` | Portfolio VaR | One-day 95% VaR of a cap-weighted MSFT/AAPL/GOOGL portfolio: empirical vs. normal with EWMA mean and covariance, under the full, linearized and quadratic loss operators |
| `var_10day_homework/` | Ten-day VaR | Delta-hedged short put: square-root-of-time rule vs. a daily-rebalanced ten-day simulation (40,000 paths), with a delta-gamma explanation of the gap |
| `var_backtest_homework/` | VaR backtesting | S&P 500, 2016–2026: rolling empirical vs. EWMA-normal one-day VaR, exceedance counts and their 95% confidence interval |
| `scenario_homework/` | Scenario analysis | Delta-hedged option on the squared spread of two stocks: worst-case and weighted scenario risk measures over 3,888 return/volatility/correlation scenarios |
| `SPY_data.csv` | — | Cached SPY closing prices, so the volatility notebook reproduces offline |
| `*.png` | — | Figures produced by the notebooks |

## Running them

```bash
pip install -r requirements.txt
```

Then open any notebook in VS Code, select a Python kernel, and **Run All**. Each
homework folder also has its own `requirements.txt` and `README.md`.

The notebooks that use market data read a cached CSV (`SPY_data.csv`, and the
`*_prices.csv` file inside the portfolio-VaR and backtest folders) and only contact
Yahoo Finance when that file is missing. The loss, ten-day VaR and scenario notebooks need
no data at all — every input is a parameter.

Every notebook ends with a self-check cell that verifies its internal
consistency and prints `ALL CHECKS PASSED`. Random seeds are fixed, so re-running
reproduces the same figures and numbers exactly.

## Requirements

Python 3.9 or newer, plus the packages in `requirements.txt`.
