# How Bad Can Things Get? Extreme-Value VaR for an S&P 500 Position

Code for the MF 731 homework `10_extreme_practice`: one-day Value at Risk of a $1,000,000
position in the S&P 500 index, with linearized losses L = −V X, for confidence levels
0.99 ≤ α ≤ 0.9999.

The notebook uses N + 1 = 2556 daily closes from 11/01/2011 (N = 2555 log returns) and
estimates α ↦ VaR_α four ways: the empirical distribution; a normal model with EWMA mean and
variance (λ = θ = 0.97, 100-day initialisation, forecast made on 11/01/2021); a GEV
distribution fitted to block maxima (n = 73, m = 35 and n = 35, m = 73) with
`scipy.stats.genextreme`; and a generalised Pareto distribution fitted to the losses above the
empirical 95% VaR with `scipy.stats.genpareto`. It compares the estimates at α = 0.9999 and
checks how precisely the tail index ξ is estimated.

| File | Contents |
|---|---|
| `evt_practice_homework.ipynb` | the notebook |
| `sp500_prices.csv` | cached daily ^GSPC closes (Yahoo Finance `Close`), 11/01/2011–01/31/2022 |
| `evt_var_curves.png` | α ↦ VaR_α for the five estimates, 0.99 ≤ α ≤ 0.9999 |
| `evt_tail_fit.png` | fitted loss tails against the largest observed losses (log scale) |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. The prices are read
from `sp500_prices.csv`; Yahoo Finance is contacted only if that file is missing. The last
cell prints `ALL CHECKS PASSED`.
