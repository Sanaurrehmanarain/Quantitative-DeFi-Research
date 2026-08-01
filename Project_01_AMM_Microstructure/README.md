<div align="center">
  <a href="report.pdf">
    <img src="../banner1.png" alt="ProjectBanner" width="100%">
  </a>
  <p><em>Click the banner to view the full analysis report</em></p>
</div>

# Module 1: Automated Market Maker (AMM) Mathematics

*This project is **Module 1** of the broader [`Quantitative-DeFi-Research`](../README.md) mega-project.*

## 📖 Overview
This module investigates the mathematical properties of Automated Market Makers (AMMs), specifically the Constant Product Market Maker (CPMM) model utilized by protocols like Uniswap V2[cite: 3]. By simulating a liquidity pool using historical ETH-USD market data, this study quantifies the divergence between Liquidity Provision (LP) returns and a "Buy and Hold" strategy[cite: 3]. 

## 🧮 Mathematical Framework
The simulation reverse-engineers the core invariant function:
$$R_x \cdot R_y = k$$
Where $R_x$ and $R_y$ are the reserves of the respective assets (e.g., ETH and USDC)[cite: 3]. 

When a trader swaps an amount $\Delta x$ for an output $\Delta y$, the execution amount is determined by:
$$\Delta y = \frac{R_y \cdot \Delta x}{R_x + \Delta x}$$

The value of an LP position relative to a HODL strategy defines **Impermanent Loss (IL)**:
$$\frac{V_{LP}}{V_{HODL}} = \frac{2 \sqrt{P_t / P_0}}{1 + P_t / P_0}$$
This equation proves that for any price change where $P_t \neq P_0$, the LP value is strictly less than or equal to the HODL value[cite: 3].

## 📊 Results and Analysis
1.  **Impermanent Loss:** Demonstrated a -11.2% divergence from the HODL strategy during peak volatility periods[cite: 5]. The LP strategy consistently underperformed during strong market trends[cite: 3].
2.  **Slippage Mechanics:** Microstructure analysis reveals a convex relationship between trade size and price slippage[cite: 3]. A $100k trade in a $50k pool resulted in >400% slippage, illustrating that trade sizes exceeding 1% of pool liquidity result in exponential slippage costs (>2%)[cite: 2, 5].

## 📋 Project Tasks
*   **Data Acquisition:** Fetch historical ETH-USD data and calculate realized volatility[cite: 4].
*   **Mathematical Modeling:** Implement the $x \cdot y = k$ formula, swap functions, and price impact equations[cite: 4].
*   **Simulation:** Run a "Hold vs. Provide Liquidity" backtest to calculate IL[cite: 4].
*   **Visualization:** Plot the Bonding Curve, LP vs HODL portfolio values, and a Slippage Heatmap[cite: 4].

*Bridging the Gap: While AMMs (Module 1) solve the problem of constant liquidity availability, they transfer price risk to LPs. Module 2 explores how High-Frequency Traders exploit temporary price divergences across these markets.*