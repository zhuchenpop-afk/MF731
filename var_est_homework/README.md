# VaR of a Market-Cap-Weighted Stock Portfolio

Code for the MF 731 homework `05_var_est_hw1_pub`: one-day 95% Value at Risk of a
$1,000,000 portfolio of Microsoft, Apple and Google held in proportion to their market
capitalisations on 05/22/2026.

The notebook estimates the VaR two ways — from the empirical distribution of the 500
daily log returns 05/24/2024–05/22/2026, and from a normal model with EWMA mean vector
and covariance matrix (λ = θ = 0.97) — each under the full, linearized and quadratic
loss operators, and then decomposes the difference between the two methods.

| File | Contents |
|---|---|
| `var_est_homework.ipynb` | the notebook |
| `stock_prices.csv` | cached daily closes (Yahoo Finance, `Close`, not adjusted), 05/23/2024–05/22/2026 |
| `var_est_loss_distributions.png` | historical vs. normal-EWMA loss distributions |
| `var_est_ewma_var_path.png` | normal-EWMA VaR through time vs. the two-year empirical VaR |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. The prices are read
from `stock_prices.csv`; Yahoo Finance is contacted only if that file is missing. The
Monte-Carlo seed is fixed, so every number reproduces exactly. The last cell prints
`ALL CHECKS PASSED`.
