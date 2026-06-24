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

### Methodology

Before performing bootstrap simulations, it is useful to first understand simple trade reshuffling.

Imagine all 67 historical trades are placed in a hat.

### Trade Reshuffling (Without Replacement)

- Pick a trade from the hat
- Write it down
- Leave it out of the hat
- Continue until all 67 trades have been selected

This changes only the order of trades while preserving the exact historical distribution of winners and losers.

### Trade Reshuffling Example

The original trade sequence was randomly reordered without replacement. This preserved the exact trade distribution while demonstrating how trade sequencing alone can affect the equity curve.

[INSERT RESHUFFLED TRADE SEQUENCE]

[INSERT RESHUFFLED EQUITY CURVE]

### Bootstrap Sampling (With Replacement)

Bootstrap sampling extends this idea by returning each selected trade back into the hat before the next draw.

- Pick a trade from the hat
- Write it down
- Put it back into the hat
- Repeat until 67 trades have been selected

Because each trade is returned to the hat after selection, some trades may appear multiple times while others may not appear at all. This creates entirely new but statistically similar trade sequences while preserving the underlying characteristics of the strategy.

A total of 1,000 bootstrap simulations were generated to estimate the distribution of potential future outcomes.

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

The strategy remained profitable across a wide range of simulated trade sequences, suggesting that historical performance was not solely dependent on trade order. Bootstrap results indicated that the strategy's edge persisted across many alternative paths generated from the same underlying trade distribution.
