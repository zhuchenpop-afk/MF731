# Ten-Day VaR of a Delta-Hedged Short Put

Code for the MF 731 homework `05_var_10day_hw_pub`: 95% ten-day Value at Risk of 100
short European puts (κ = 170, T = 0.292) delta-hedged in a Black–Scholes market.

The notebook compares two estimates — the one-day VaR from 40,000 simulated returns
scaled by √10, and a 40,000-path simulation of the ten-day self-financing strategy with
the hedge reset every day — and explains the gap with a delta-gamma (χ²) approximation.

| File | Contents |
|---|---|
| `var_10day_homework.ipynb` | the notebook |
| `var_10day_distributions.png` | √10 × one-day loss vs. the simulated ten-day loss |
| `var_10day_horizon_ratio.png` | how far the square-root-of-time rule overshoots, by horizon |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. No data are needed;
every input is a parameter. Seeds are fixed, so every number reproduces exactly. The last
cell prints `ALL CHECKS PASSED`.
