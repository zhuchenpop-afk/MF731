# Stress Testing a Market-Cap-Weighted MSFT/AAPL Portfolio

Code for the MF 731 homework `09_stress_testing_pub`: a $1,000,000 portfolio of Microsoft and
Apple held in proportion to their market capitalisations on 09/01/2016, stressed with a
−5σ shock to Apple's next daily log return and a −5 conditional-σ shock to Microsoft's.

The notebook estimates the EWMA mean vector and covariance matrix (λ = θ = 0.97) from the
daily log returns 09/01/2011–09/01/2016, computes the one-day normal VaR, the ten-day VaR by
the square-root-of-time rule and the regulatory capital 3 × ten-day VaR, applies the shock,
updates the EWMA estimates and simulates days 2–10 on 50,000 paths with the shares held
fixed. It reports the average shocked ten-day loss, the shocked ten-day VaR, and how often
the shocked losses exceed the pre-shock ten-day VaR and the regulatory capital, and compares
them with no shock and with the lecture's version of the shock.

| File | Contents |
|---|---|
| `stress_test_homework.ipynb` | the notebook |
| `stock_prices.csv` | cached daily prices (Yahoo Finance `Close` and `Adj Close`), 09/01/2011–09/01/2016 |
| `stress_loss_distribution.png` | ten-day losses with and without the shock, against the pre-shock VaR and capital |
| `stress_paths.png` | cumulative loss and EWMA correlation day by day, with and without the shock |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. The prices are read
from `stock_prices.csv`; Yahoo Finance is contacted only if that file is missing. The
Monte-Carlo seed is fixed, so every number reproduces exactly. The last cell prints
`ALL CHECKS PASSED`.
