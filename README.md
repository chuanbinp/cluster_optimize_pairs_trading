## Unsupervised Pair Discovery and Statistical Validation for Pairs Trading

### Overview

This project develops a data-driven framework for pairs trading by combining unsupervised learning with classical statistical arbitrage validation before backtesting mean reversion strategies. Pairs trading involves identifying two historically correlated stocks — such as Coca-Cola [finance:The Coca-Cola Company] and Pepsi [finance:PepsiCo, Inc.], or Apple [finance:Apple Inc.] and Microsoft [finance:Microsoft Corporation] — and exploiting temporary divergences in their price relationship. It is a market-neutral strategy, meaning it seeks to profit regardless of market direction. When the prices of two correlated stocks diverge beyond a certain threshold, the strategy takes a long position in the undervalued stock and a short position in the overvalued stock, assuming the spread will eventually revert to the mean.

To get started, we need to identify and select appropriate stock pairs with high historical correlation. We will explore the use of unsupervised learning for this task. Each equity is represented as a numerical vector capturing its price dynamics. Similar equities are identified via clustering or nearest-neighbour search, and candidate pairs are then filtered through traditional cointegration and mean-reversion checks.

We aim to build a mean reversion trading strategy with the pairs that passes through the validation checks. Finally, the strategy is backtested with realistic trading assumptions to assess profitability and robustness. We will also evaluate the strategy performance based on metrics like Sharpe ratio, skewness, maximum drawdown, etc.

### Objectives

- Generate vector representations of equities using statistical time-series and valuation metrics
- Identify candidate trading pairs using unsupervised learning (clustering / similarity search)
- Validate pairs using correlation, cointegration, and spread stationarity tests
- Backtest and evaluate performance using metrics such as Sharpe ratio, drawdown, and hit rate

### Methodology

- **Data Collection:** Obtain daily adjusted prices for a broad equity universe (e.g., S&P 500 [finance:S&P 500]) from Yahoo Finance
- **Feature Construction:** Compute time-series vectors (returns, volatility, autocorrelation, PCA components)
- **Unsupervised Pair Discovery:** Apply KMeans, hierarchical clustering, or nearest-neighbour search to find similar equities
- **Statistical Validation:** For each candidate pair, test for cointegration (Engle–Granger), spread stationarity (ADF), and mean-reversion (half-life, Hurst exponent)
- **Signal Design:** Define entry/exit rules based on z-score thresholds of the spread or a Kalman-filtered residual
- **Backtesting:** Simulate trades with transaction costs and portfolio constraints; compute performance metrics

### Tools and Libraries

- Programming Language: Python
- Libraries: pandas, NumPy, statsmodels, scikit-learn, yfinance, backtrader, matplotlib

### Expected Outcome

A reproducible pairs trading pipeline that automatically discovers and tests tradeable equity pairs, combining machine learning–based similarity detection with rigorous statistical validation. The project aims to demonstrate that unsupervised learning can enhance traditional pairs selection and improve the efficiency of statistical arbitrage research.
