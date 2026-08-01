<div align="center">
  <a href="report.pdf">
    <img src="../banner1.png" alt="ProjectBanner" width="100%">
  </a>
  <p><em>Click the banner to view the full analysis report</em></p>
</div>

# Module 4: Derivatives Pricing (DeFi Options)

*This project is **Module 4** of the broader [`Quantitative-DeFi-Research`](../README.md) mega-project.*

## 📖 Overview
As institutional capital enters DeFi, the demand for hedging instruments has surged. "DeFi Option Vaults" (DOVs) automate the selling of covered calls to generate yield. This module implements a Black-Scholes-Merton pricing engine to value ETH options and calculate risk sensitivities ("The Greeks") to manage hedging risk for automated vault strategies.

## 🧮 Mathematical Framework
The fair price of a European Call Option $C(S,t)$ is governed by the Black-Scholes model:
$$C = S_0 N(d_1) - K e^{-rT} N(d_2)$$
To manage portfolio risk, the engine calculates critical partial derivatives (The Greeks):
*   **Delta ($\Delta$):** $\Delta = \frac{\partial C}{\partial S}$ (Sensitivity to spot price changes).
*   **Gamma ($\Gamma$):** $\Gamma = \frac{\partial^2 C}{\partial S^2}$ (Rate of change of Delta / Convexity).

## 📊 Results and Analysis
Using the derived volatility from Module 3 ($\sigma = 60\%$), a Risk-Free Rate of $5\%$, and a 30-day maturity ($T=30/365$), we priced an Out-of-the-Money (OTM) ETH Call Option (Spot: $2,500, Strike: $2,600).
*   **Fair Valuation:** The theoretical price of the call option is $133.35.
*   **Risk Sensitivities:** Delta was calculated at 0.4530, indicating that for every $1.00 increase in ETH, the option value increases by $0.45. To remain Delta Neutral, a vault must short 0.453 ETH against this position.
*   **Hedging Danger:** Gamma peaks exactly at the Strike Price ($2,600), marking the "danger zone" where Delta changes most rapidly, requiring constant algorithmic rebalancing.

## 📋 Project Tasks
*   **Pricing Engine:** Implement the Black-Scholes formula for Call/Put pricing.
*   **Risk Sensitivities:** Calculate and mathematically derive the Option Greeks (Delta, Gamma, Theta).
*   **Simulation:** Simulate the PnL of a "Covered Call" strategy vs. simply holding ETH.
*   **Visualization:** Plot sensitivity analysis showcasing option convexity and Delta stability.

*Conclusion: This foundational model enables automated market making for options, Impermanent Loss hedging, and principal-protected yield generation across the DeFi ecosystem.*
