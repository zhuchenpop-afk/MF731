# Backtesting One-Day VaR on the S&P 500

Code for the MF 731 homework `05_var_backtest_hw_pub`: a constant $1 position in the
S&P 500 index, 05/23/2016–05/22/2026.

Every day from 05/29/2020 the notebook forecasts the next day's 95% VaR (full loss
operator) from the empirical distribution of the last 1,010 log returns and from a normal
model with EWMA mean and variance (λ = θ = 0.97), counts the exceedances over the
1,504 evaluation days, and tests each count against its 95% confidence interval.

| File | Contents |
|---|---|
| `var_backtest_homework.ipynb` | the notebook |
| `sp500_prices.csv` | cached daily closes of `^GSPC` (Yahoo Finance), 05/23/2016–05/22/2026 |
| `backtest_var_paths.png` | VaR forecasts, realised losses and exceedances for both methods |
| `backtest_cumulative_exceedances.png` | running exceedance counts against the expected count |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. The prices are read
from `sp500_prices.csv`; Yahoo Finance is contacted only if that file is missing. The last
cell prints `ALL CHECKS PASSED`.
