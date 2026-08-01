# Module II: High-Frequency Statistical Arbitrage

## Project Title
High-Frequency Statistical Arbitrage in Crypto Markets (Pairs Trading)

## Status
**✅ Completed** — all tasks below finished.

## Objective
To develop an algorithmic trading strategy that exploits temporary price divergences between highly correlated crypto assets (BTC/ETH) using 1-minute interval data and cointegration statistics.

---

## Tasks

### 1. High-Frequency Data Acquisition
- [x] Fetch 1-minute interval data for BTC-USD and ETH-USD (last 7 days).
- [x] Align timestamps strictly to ensure synchronous data for correlation analysis.

### 2. Statistical Modeling (The "Quant" Engine)
- [x] Perform Engle-Granger Cointegration Test to prove the pair is statistically coupled.
- [x] Calculate the Spread: `Spread = Price_A - (Hedge_Ratio * Price_B)`.
- [x] Normalize the Spread into a Z-Score (standard deviations from the mean).

### 3. Strategy Logic (Mean Reversion)
- [x] Entry Signal: When Z-Score > 2.0 (Short the Spread) or Z-Score < -2.0 (Long the Spread).
- [x] Exit Signal: When Z-Score returns to 0 (Mean Reversion).
- [x] Transaction Costs: Incorporate realistic exchange fees (e.g., 0.1%).

### 4. Performance Analytics
- [x] Calculate Cumulative Returns, Sharpe Ratio, and Maximum Drawdown.
- [x] Visualize the "Spread" dynamics and trade entry/exit points.

### 5. Reporting
- [x] Technical report covering Stationarity, Cointegration vectors, and PnL attribution.
