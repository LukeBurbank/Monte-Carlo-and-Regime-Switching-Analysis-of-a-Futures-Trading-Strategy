# Monte-Carlo-and-Regime-Switching-Analysis-of-a-Futures-Trading-Strategy
Bootstrap and regime-switching Monte Carlo simulations used to evaluate the robustness, risk, and drawdown characteristics of a discretionary NQ futures trading strategy.
## Project Overview

This project analyzes the robustness of a discretionary futures trading strategy using two Monte Carlo frameworks:

1. Bootstrap Monte Carlo Simulation
2. Regime-Switching Monte Carlo Simulation

The objective was to determine whether the strategy's historical performance remained statistically robust when trade order and market conditions were randomized across thousands of simulated paths.

## Dataset

- 67 historical trades
- Performance measured in R-Multiples
- Trades classified into two market regimes:
  - Ideal
  - Not Ideal
## Monte Carlo #1: Bootstrap Simulation

### Objective

The first simulation tested whether the strategy's profitability was dependent on the exact sequence of historical trades.

Trades were randomly resampled with replacement 1,000 times to generate alternative equity curves and drawdown outcomes.

### Example Bootstrap Resample

[INSERT PICTURE HERE]

### Example Bootstrap Equity Curve

[INSERT PICTURE HERE]

### Bootstrap Monte Carlo Results

- Average Drawdown: -5.35R
- Median Drawdown: -5.00R
- Worst Drawdown: -18.48R
- 5th Percentile Drawdown: -9.32R

### Bootstrap Drawdown Distribution

[INSERT PICTURE HERE]

### Bootstrap Monte Carlo Paths

[INSERT PICTURE HERE]

### Conclusion

The strategy remained profitable across a wide range of simulated trade sequences, suggesting that performance was not solely dependent on the historical ordering of trades.
