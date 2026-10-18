# Scenario Analysis of a Delta-Hedged Option on the Squared Spread

Code for the MF 731 homework `09_scenario_analysis_pub`: one long European option paying
(S1_T − S2_T)², delta-hedged with the two stocks, revalued over a five-day horizon under all
3,888 combinations of log-return, volatility and correlation shocks on the assignment's grid.

The notebook prices the option in closed form, checks the price and deltas, computes the full
loss in every scenario, and reports the worst-case scenario risk measure max ℓ and the weighted
scenario risk measure max wℓ with the scenarios that attain them.

| File | Contents |
|---|---|
| `scenario_homework.ipynb` | the notebook |
| `scenario_loss_by_vol_corr.png` | largest loss for each volatility and correlation shock |
| `scenario_loss_by_returns.png` | loss over the log-return grid at the worst-case parameters |

## Running it

```bash
pip install -r requirements.txt
```

Open the notebook in VS Code, select a Python kernel and **Run All**. No data are needed;
every input is a parameter. The last cell prints `ALL CHECKS PASSED`.
