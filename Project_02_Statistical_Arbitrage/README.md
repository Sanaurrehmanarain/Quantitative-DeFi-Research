<div align="center">
  <a href="report.pdf">
    <img src="../banner1.png" alt="ProjectBanner" width="100%">
  </a>
  <p><em>Click the banner to view the full analysis report</em></p>
</div>

# Module 2: High-Frequency Statistical Arbitrage (Crypto Pairs Trading)

*This project is **Module 2** of the broader [`Quantitative-DeFi-Research`](../README.md) mega-project.*

## 📖 Overview
Building on the market microstructure analyzed in Module 1, this project evaluates the viability of a Pairs Trading (Statistical Arbitrage) strategy applied to Bitcoin (BTC) and Ethereum (ETH) using high-frequency (1-minute) market data. The objective was to exploit temporary pricing inefficiencies between these two highly correlated assets using the Engle-Granger Two-Step Method.

## 🧮 Mathematical Framework
The strategy relies on finding a stable Hedge Ratio ($\beta$) using Ordinary Least Squares (OLS) regression:
$$P_{ETH} = \beta \cdot P_{BTC} + \epsilon$$
Resulting in $\beta = 0.0423$.

The **Spread** is normalized into a rolling Z-Score to generate mean-reversion signals:
$$Z_t = \frac{S_t - \mu_{60}}{\sigma_{60}}$$
*   **Short Signal:** $Z_t > 2.0$ (Sell ETH, Buy BTC).
*   **Long Signal:** $Z_t < -2.0$ (Buy ETH, Sell BTC).

## 📊 Results and Analysis
*   **Correlation vs. Cointegration:** The assets demonstrated a near-perfect correlation coefficient of 0.98. However, the Augmented Dickey-Fuller (ADF) test yielded a p-value of 0.477, failing to reject the null hypothesis of non-stationarity.
*   **Performance:** Because the spread followed a random walk rather than mean-reverting, the algorithmic strategy "fought the trend," resulting in an out-of-sample net loss of -$398.88.
*   **Risk Takeaway:** A robust quantitative trading engine must include a Regime Filter; if $P_{ADF} > 0.05$, the system should halt trading as the fundamental assumption of mean reversion is violated.

## 📋 Project Tasks
*   **Data Handling:** Align 1-minute interval timestamps strictly to ensure synchronous data.
*   **Statistical Modeling:** Perform Engle-Granger Cointegration tests and normalize the spread into a Z-Score.
*   **Strategy Logic:** Build entry ($|Z| > 2.0$) and exit ($Z = 0$) parameters with 0.1% transaction costs.
*   **Analytics:** Calculate cumulative returns and visualize spread dynamics.

*Bridging the Gap: Just as statistical assumptions can fail during structural regime shifts (Module 2), decentralized protocols face catastrophic failures if asset prices crash. Module 3 models this tail risk using stochastic Monte Carlo simulations.*
