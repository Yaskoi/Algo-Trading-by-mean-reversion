# 📊 Mean-Reversion & Statistical Arbitrage Strategies in Python

## Overview

This project investigates the implementation of various **mean-reversion trading strategies** using the ARK Innovation ETF (**ARKK**) and pairs of US-listed equities. The goal is to evaluate the performance and robustness of classical systematic trading techniques and compare them to a simple Buy & Hold approach.

We focus on three strategies:

1. **Simple Moving Average (SMA) Crossover**
2. **Z-score-based Reversion**
3. **Statistical Arbitrage with Cointegrated Pairs**

---

## 📁 Files

- `ARKK.xlsx`: Historical daily prices of ARKK.
- `vma.xlsx`: Historical daily prices of Visa (V) and Mastercard (MA).
- `main.ipynb`: Main Jupyter notebook with all analyses and visualizations.
- `ysk_quantlib`: Custom Python library with helper functions (ADF, PP, Jarque-Bera, cointegration tests, etc.).

---

## 🔧 Tech Stack

- **Language:** Python 3.10+
- **Main Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `yfinance`, `ysk_quantlib`
- **Environment:** Jupyter Notebook / VS Code

---

## 📘 Notebook Content

### I. Exploratory Analysis of ARKK (2015–2024)

- Normalization and visualization of prices
- Daily and annualized return computation
- Volatility analysis
- Normality (Jarque-Bera) and stationarity tests (ADF, PP)

### II. Mean-Reversion Strategies

#### 1. SMA Strategy
- Buy when price is above the moving average
- Sell when price falls below it

#### 2. Z-score Strategy
- Compute rolling z-score of price
- Enter long/short positions when z-score exceeds defined thresholds
- Evaluate cumulative returns and Sharpe ratio

#### 3. Statistical Arbitrage
- Test cointegration (Engle-Granger) between V & MA
- Model the spread, calculate Bollinger bands
- Long/short signals based on z-score of the spread
- Backtest and compute strategy Sharpe ratio

### III. Automated Pair Selection
- Loop over ~20 S&P500 stocks
- Apply cointegration test to each pair
- Retain statistically significant pairs (p-value < 0.05)

---

## 📈 Strategy Comparison

| Strategy      | Cumulative Return | Sharpe Ratio | Notes                        |
|---------------|-------------------|--------------|------------------------------|
| SMA Crossover | Low               | Moderate     | Sensitive to lookback window |
| Z-score       | High              | Lower        | Beats Buy & Hold             |
| Stat Arb      | Variable          | Highest      | Needs pair selection tuning  |

---


## 🚀 Future Improvements

- Out-of-sample validation
- Apply strategy to crypto pairs or sector indices
- Integrate **chaos-based regime filters** (Lyapunov exponents)
- Refine signal generation using ML or HMM models
---

