# Confidence Intervals for VaR: Unknown Volatility and Unknown Mean

Code for the MF 731 homework `13_CI_pub`: one-day 97% Value at Risk of a $1,000,000 position
in Apple over 10/31/2018–11/01/2018, with the full loss L = −V(e^X − 1) and normal log returns
X ~ N(μ, σ²) whose true parameters are unknown.

From the daily log returns 11/01/2016–10/31/2018 the notebook estimates the VaR from the
empirical distribution and from the normal formula with the sample mean and variance, then
quantifies parameter uncertainty: (a) a 98% confidence interval with μ known, from
(n − 1)S²/σ² ~ χ²(n − 1), and (b) the lecture's simulation for unknown μ and σ
(M = 125,000 trials), reporting the average simulated VaR and its 1% / 99% quantiles.

| File | Contents |
|---|---|
| `var_ci_homework.ipynb` | the notebook |
| `aapl_prices.csv` | cached daily AAPL closes (Yahoo Finance `Close` and `Adj Close`), 11/01/2016–10/31/2018 |
| `var_ci_simulation.png` | distribution of the simulated VaRs with both confidence intervals |
| `var_ci_sigma.png` | VaR as a function of σ, with the 98% interval for σ |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. The prices are read
from `aapl_prices.csv`; Yahoo Finance is contacted only if that file is missing. The
simulation seed is fixed, so every number reproduces exactly. The last cell prints
`ALL CHECKS PASSED`.
