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

The first simulation tested whether the strategy's profitability was dependent on the historical ordering of trades.

### Methodology

Before performing bootstrap simulations, it is useful to first understand simple trade reshuffling.

Imagine all 67 historical trades are written on slips of paper and placed into a hat.

### Trade Reshuffling (Without Replacement)

- Pick a trade from the hat
- Write it down
- Leave it out of the hat
- Continue until all 67 trades have been selected

This changes only the order of trades while preserving the exact historical distribution of winners and losers.

### Trade Reshuffling Example

The original trade sequence was randomly reordered without replacement. This preserved the exact trade distribution while demonstrating how trade sequencing alone can affect the equity curve.

Trade reshuffling provides a useful foundation because it isolates the impact of trade sequencing while keeping the underlying performance distribution unchanged. However, it is limited to the exact set of historical trades.

To generate entirely new but statistically similar trade histories, the analysis uses bootstrap sampling with replacement. This approach allows individual trades to appear multiple times or not at all, creating thousands of alternative paths while preserving the overall characteristics of the strategy.

### Bootstrap Sampling (With Replacement)

Bootstrap sampling extends this idea by returning each selected trade back into the hat before the next draw.

- Pick a trade from the hat
- Write it down
- Put it back into the hat
- Repeat until 67 trades have been selected

Because each trade is returned to the hat after selection, some trades may appear multiple times while others may not appear at all. This creates entirely new but statistically similar trade sequences while preserving the underlying characteristics of the strategy.

A total of 1,000 bootstrap simulations were generated to estimate the distribution of potential future outcomes.

### Bootstrap Monte Carlo Equity Curve Distribution

![Monte Carlo Equity Curve Distribution](images/bootstrap_equity_distribution.png)
### Drawdown Distribution

![Drawdown Distribution](images/bootstrap_drawdown_distribution.png)

### Drawdown Statistics

- Average Drawdown: -5.35R
- Median Drawdown: -5.00R
- Worst Drawdown: -18.48R
- 5th Percentile Drawdown: -9.32R

### Key Findings

- The median bootstrap path remained profitable across 1,000 simulations.
- The original equity curve finished near the center of the simulated distribution.
- Most simulated paths experienced maximum drawdowns between approximately 3R and 7R.
- Randomizing trade outcomes did not eliminate the strategy's positive expectancy.
- Performance appeared robust to trade sequencing, suggesting profitability was not dependent on a specific historical order of trades.

### Conclusion

The strategy remained profitable across a wide range of simulated trade sequences, suggesting that historical performance was not solely dependent on trade order. Bootstrap results indicated that the strategy's edge persisted across many alternative paths generated from the same underlying trade distribution.
