# MF 731 — Corporate Risk Management

Code accompanying the written homework submissions. Each notebook is
self-contained and runs top to bottom.

## Contents

| File | Assignment | What it does |
|---|---|---|
| `volatility_homework_1.ipynb` | SPY volatility | MA(100) and EWMA(0.94) volatility, GARCH(1,1) fitted by maximum likelihood, 100 simulated forecast paths |
| `loss_homework.ipynb` | Loss distribution | Full, linearized and second-order loss operators for a delta-hedged short put; loss distribution by Monte Carlo, N = 100,000 |
| `SPY_data.csv` | — | Cached SPY closing prices, so the volatility notebook reproduces offline |
| `*.png` | — | Figures produced by the notebooks |

## Running them

```bash
pip install -r requirements.txt
```

Then open either notebook in VS Code, select a Python kernel, and **Run All**.

The volatility notebook reads `SPY_data.csv` if it is present and only contacts
Yahoo Finance when that file is missing. The loss notebook needs no data at all —
every input is a parameter.

Both notebooks end with a self-check cell that verifies their internal
consistency and prints `ALL CHECKS PASSED`. Both fix a random seed, so re-running
reproduces the same figures and numbers exactly.

## Requirements

Python 3.9 or newer, plus the packages in `requirements.txt`.
