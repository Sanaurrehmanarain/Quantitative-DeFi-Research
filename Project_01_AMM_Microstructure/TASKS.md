# Module I: AMM Microstructure & Impermanent Loss

## Project Title
Mathematical Modeling and Microstructure Analysis of Automated Market Makers (AMMs)

## Status
**✅ Completed** — all tasks below finished.

## Objective
To reverse-engineer and simulate a Constant Product Market Maker (CPMM) using real-world market data, quantifying the risks of Liquidity Provision (Impermanent Loss) and the impact of trade size on price execution (Slippage).

---

## Tasks

### 1. Data Acquisition & Pre-processing
- [x] Fetch historical minute-level/hourly data for a crypto asset (e.g., ETH-USD) using Yahoo Finance / FRED APIs.
- [x] Calculate realized volatility and returns to characterize the market environment.

### 2. Mathematical Modeling (CPMM)
- [x] Implement the Constant Product Formula: `x * y = k`.
- [x] Derive and code the Swap Function to calculate exact token outputs for a given input.
- [x] Derive and code the Price Impact (Slippage) formulas based on pool depth.

### 3. Simulation & Liquidity Analysis
- [x] Simulate a liquidity pool initialized with a fixed ratio based on real market prices.
- [x] Run a "Hold vs. Provide Liquidity" backtest to calculate Impermanent Loss (IL).
- [x] Quantify the correlation between Market Volatility and Impermanent Loss.

### 4. Microstructure Visualization
- [x] Plot the Bonding Curve (Hyperbola).
- [x] Visualize the divergence between "HODL Strategy" portfolio value and "LP Strategy" value.
- [x] Create a Slippage Heatmap showing cost vs. trade size relative to pool depth.

### 5. Reporting
- [x] Compile findings into a professional technical report with APA 7 citations.
- [x] Discuss implications for DeFi market efficiency and risk management.
