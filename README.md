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

### Trade Reshuffling Example

The original 67 trades were randomly reordered without replacement. This preserved the exact trade distribution while demonstrating how trade sequencing alone can alter the equity curve.

[INSERT RESHUFFLED TRADE SEQUENCE]

[INSERT RESHUFFLED EQUITY CURVE]

### Bootstrap Simulation
To illustrate the process, imagine 67 historical trades placed in a hat.

**Trade Reshuffling (without replacement):**
- Pick a trade from the hat
- Write it down
- Leave it out of the hat
- Continue until all 67 trades have been used once

This preserves the exact trade distribution while changing only the sequence of trades.

**Bootstrap Sampling (with replacement):**
- Pick a trade from the hat
- Write it down
- Put it back into the hat
- Repeat 67 times

This allows some trades to appear multiple times while others may not appear at all, creating entirely new simulated trade sequences.

Bootstrap sampling was then performed by randomly selecting trades with replacement. This allowed trades to appear multiple times or not appear at all within a simulated path.

1,000 bootstrap simulations were generated to estimate the distribution of future outcomes.

### Monte Carlo Equity Curve Distribution

[INSERT MONTE CARLO PATHS]

### Drawdown Distribution

[INSERT DRAWDOWN HISTOGRAM]

### Drawdown Statistics

- Average Drawdown: -5.35R
- Median Drawdown: -5.00R
- Worst Drawdown: -18.48R
- 5th Percentile Drawdown: -9.32R

### Conclusion

The strategy remained profitable across a wide range of simulated trade sequences, suggesting that performance was not solely dependent on the historical ordering of trades.
