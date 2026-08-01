<div align="center">
  <a href="TechnicalReport.pdf">
    <img src="banner.png" alt="ProjectBanner" width="100%">
  </a>
  <p><em>Click the banner to view the full analysis report</em></p>
</div>

<div align="center">

<br />

<h1><b>📐📈 QUANTITATIVE DeFi RESEARCH ⚙️</b></h1>

## Microstructure, Arbitrage & Risk Engineering

<h3>
<i>Synthesizing continuous-time finance, stochastic calculus, and decentralized market microstructure.</i>
</h3>

*A capstone-grade quantitative research project on Decentralized Finance markets — AMM mechanics, statistical arbitrage, stochastic risk, and derivatives pricing, unified under one rigorous mathematical lens.*

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![Modules](https://img.shields.io/badge/Modules-4-blueviolet?style=for-the-badge)

<div align="center">

<p>
  <a href="./01_AMM_Microstructure"><img src="https://img.shields.io/badge/I_|_AMM_Microstructure-0052FF?style=for-the-badge&logo=ethereum&logoColor=white" /></a>
  <a href="./02_Statistical_Arbitrage"><img src="https://img.shields.io/badge/II_|_Statistical_Arbitrage-F7931A?style=for-the-badge&logo=bitcoin&logoColor=white" /></a>
  <a href="./03_Monte_Carlo_Risk"><img src="https://img.shields.io/badge/III_|_Monte_Carlo_VaR-4CAF50?style=for-the-badge&logo=python&logoColor=white" /></a>
  <a href="./04_Options_Pricing"><img src="https://img.shields.io/badge/IV_|_Options_Pricing-8A2BE2?style=for-the-badge&logo=google-scholar&logoColor=white" /></a>
</p>

</div>

<p>
<b>
📊 Constant Product AMMs &nbsp; • &nbsp;
⚡ HFT Cointegration &nbsp; • &nbsp;
🎲 GBM Stress Testing &nbsp; • &nbsp;
📉 Black-Scholes Greeks
</b>
</p>

---

</div>

<hr />

## 📖 Overview

This repository contains a comprehensive quantitative analysis of the Decentralized Finance (DeFi) ecosystem. By synthesizing concepts from **Automated Market Makers (AMMs)**, **stochastic calculus**, and **statistical arbitrage**, this mega-project quantifies the unique risks and opportunities present in crypto-asset markets.

The central thesis: **DeFi markets, while structurally novel, strictly obey the fundamental laws of financial mathematics.**

> Arbitrage is not guaranteed by correlation. Risk is quantifiable via stochastic simulation. Yield — whether from AMM fees or option premiums — is simply compensation for assuming convexity risk.

Four self-contained research modules build this case from the ground up, moving from market microstructure → statistical trading → probabilistic risk → derivatives pricing.

---

## 🧭 Table of Contents

- [Microstructure, Arbitrage \& Risk Engineering](#microstructure-arbitrage--risk-engineering)
- [📖 Overview](#-overview)
- [🧭 Table of Contents](#-table-of-contents)
- [🏗️ Repository Architecture \& Modules](#️-repository-architecture--modules)
- [📊 Executive Findings](#-executive-findings)
- [Module I — AMM Microstructure \& Impermanent Loss](#module-i--amm-microstructure--impermanent-loss)
  - [1.1 The Mathematics of Slippage](#11-the-mathematics-of-slippage)
  - [1.2 Quantifying Impermanent Loss (IL)](#12-quantifying-impermanent-loss-il)
- [Module II — High-Frequency Statistical Arbitrage](#module-ii--high-frequency-statistical-arbitrage)
  - [2.1 Cointegration Analysis](#21-cointegration-analysis)
  - [2.2 Strategy Performance](#22-strategy-performance)
- [Module III — Stochastic Risk Modeling (Monte Carlo)](#module-iii--stochastic-risk-modeling-monte-carlo)
  - [3.1 Methodology](#31-methodology)
  - [3.2 Risk Metrics](#32-risk-metrics)
- [Module IV — Derivatives Pricing (DeFi Options)](#module-iv--derivatives-pricing-defi-options)
  - [4.1 Black-Scholes Valuation](#41-black-scholes-valuation)
  - [4.2 The Greeks (Risk Sensitivities)](#42-the-greeks-risk-sensitivities)
- [🧩 Conclusion \& Future Work](#-conclusion--future-work)
- [🛠️ Tech Stack](#️-tech-stack)
- [🚀 Getting Started](#-getting-started)
- [Citation](#citation)
- [📜 License](#-license)
- [⭐ Support](#-support)

---

## 🏗️ Repository Architecture & Modules

This project is divided into four distinct modules, each targeting a specific domain of quantitative finance:

| Module | Directory | Focus | Core Technique |
|---|---|---|---|
| **I** | [`/01_AMM_Microstructure`](./01_AMM_Microstructure) | Mathematical modeling of Uniswap V2 liquidity pools | Constant-product bonding curve, slippage & impermanent loss |
| **II** | [`/02_Statistical_Arbitrage`](./02_Statistical_Arbitrage) | High-frequency statistical arbitrage (pairs trading) | Cointegration, ADF testing, rolling z-score mean reversion |
| **III** | [`/03_Monte_Carlo_Risk`](./03_Monte_Carlo_Risk) | Protocol solvency stress testing | Geometric Brownian Motion, Monte Carlo VaR |
| **IV** | [`/04_Options_Pricing`](./04_Options_Pricing) | Black-Scholes pricing engine for DeFi Option Vaults (DOVs) | Black-Scholes, Greeks (Delta, Gamma) |

---

## 📊 Executive Findings

| # | Module | Key Metric | Finding |
|---|---|---|---|
| 1 | AMM Microstructure | Max drawdown **-11.2%** | Liquidity provision behaves as a **short-convexity strategy** — LPs mimic a short straddle payoff and underperform HODL in trending markets. |
| 2 | Statistical Arbitrage | Correlation **0.98** vs. ADF **p = 0.477** | High correlation ≠ cointegration. The BTC/ETH spread is **non-stationary**, and a naive mean-reversion strategy lost **-\$398.88**. |
| 3 | Monte Carlo Risk | **5.87%** liquidation probability | A 30-day, 10,000-path GBM simulation puts ~1-in-17 odds on ETH falling below the **\$2,290** liquidation threshold; 95% VaR = **\$2,255.85**. |
| 4 | Options Pricing | Theoretical price **\$133.35** | At σ = 60% annualized, an OTM ETH call (Spot \$2,500 / Strike \$2,600 / 30D) prices with **Delta 0.4530**; Gamma peaks at the strike, marking maximum hedging risk. |

---

## Module I — AMM Microstructure & Impermanent Loss

**Objective:** Reverse-engineer the Uniswap V2 constant-product invariant

$$x \cdot y = k$$

and quantify the true economic cost of providing liquidity.

### 1.1 The Mathematics of Slippage
The "bonding curve" was modeled to measure execution price impact as a function of trade size relative to pool depth. A slippage heatmap shows an **exponential** blow-up in price impact as trades grow relative to reserves — a \$100k trade against a \$50k pool produces catastrophic slippage (**>400%**), underscoring why deep liquidity is non-negotiable for efficient markets.

### 1.2 Quantifying Impermanent Loss (IL)
Using historical ETH data (2024–2025), the notebook backtests a Liquidity Provider (LP) position against a simple HODL benchmark.

| Metric | Result |
|---|---|
| Strategy comparison | LP consistently **underperforms** HODL in trending markets |
| Max divergence (drawdown) | **-11.2%** during peak volatility |

**Takeaway:** Impermanent loss isn't a bug — it's the AMM's way of pricing the optionality it implicitly sells to arbitrageurs.

---

## Module II — High-Frequency Statistical Arbitrage

**Objective:** Test a mean-reversion (pairs trading) strategy on BTC/ETH using 1-minute interval data.

### 2.1 Cointegration Analysis
The pair shows an extreme Pearson correlation of **0.98** — a number that looks like a green light for pairs trading. The **Augmented Dickey-Fuller (ADF)** test tells a different story:

| Test | Value | Interpretation |
|---|---|---|
| ADF p-value | **0.477** | Cannot reject the null of a unit root |
| Spread behavior | **Non-stationary** (random walk) | No stable equilibrium to revert to |

A rolling z-score of the spread confirms persistent drift away from zero rather than oscillation around a mean.

### 2.2 Strategy Performance
Because the spread lacks stationarity, the mean-reversion algorithm effectively "fought the trend" and produced a net loss of **-\$398.88**.

> This negative result is deliberately included as a proof-of-concept: **correlation is not cointegration**, and skipping stationarity testing (ADF) before deploying capital is a direct path to systematic losses.

---

## Module III — Stochastic Risk Modeling (Monte Carlo)

**Objective:** Estimate Value-at-Risk (VaR) for a DeFi lending protocol holding ETH as collateral.

### 3.1 Methodology
A **Geometric Brownian Motion (GBM)** model was calibrated from realized market data:

- Daily drift: **μ ≈ 0**
- Daily volatility: **σ ≈ 3.8%**
- Simulation: **10,000 paths** over a **30-day horizon**

### 3.2 Risk Metrics

| Metric | Value | Meaning |
|---|---|---|
| **95% VaR** | \$2,255.85 | 95% confidence ETH stays above this level over the horizon |
| **Liquidation probability** | **5.87%** | ~1-in-17 chance ETH breaches the \$2,290 liquidation threshold within 30 days |

**Takeaway:** Static loan-to-value (LTV) ratios are insufficient in a market with fat-tailed, path-dependent risk — protocols need dynamic collateralization informed by simulations like this one.

---

## Module IV — Derivatives Pricing (DeFi Options)

**Objective:** Price an ETH call option for an automated DeFi Option Vault (DOV) strategy.

### 4.1 Black-Scholes Valuation
Using the volatility derived in Module III (annualized σ = **60%**), an out-of-the-money call was priced:

| Parameter | Value |
|---|---|
| Spot price | \$2,500 |
| Strike price | \$2,600 |
| Expiry | 30 days |
| **Theoretical price** | **\$133.35** |

### 4.2 The Greeks (Risk Sensitivities)

- **Delta (Δ) = 0.4530** — a \$1 move in ETH shifts the option's value by \$0.45; a delta-neutral vault would need to hold 0.45 ETH per option sold.
- **Gamma (Γ)** — peaks exactly at the strike price, marking the zone of maximum hedging risk, where Delta itself is most sensitive to price moves and rebalancing must be most frequent.

---

## 🧩 Conclusion & Future Work

This capstone project demonstrates that DeFi markets, while structurally innovative, remain governed by the same laws that price every other financial market:

1. **Arbitrage** is not guaranteed by correlation alone — stationarity matters.
2. **Risk** is quantifiable via stochastic simulation, not intuition.
3. **Yield** — from AMM fees or option premiums — is simply compensation for assuming convexity risk.

**Future work** will integrate these four modules into a live **"Vault Strategy"** that dynamically hedges AMM impermanent loss using the options priced in Module IV — closing the loop between liquidity provision and derivatives-based risk management.

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Language** | Python 3.10+ |
| **Data & Numerics** | `pandas` (time-series), `numpy` (vectorized math) |
| **Statistics & Econometrics** | `scipy` (optimization), `statsmodels` (cointegration / ADF testing) |
| **Market Data** | `yfinance` |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/sanaurrehmanarain/Quantitative-DeFi-Research.git
cd Quantitative-DeFi-Research

# Install dependencies
pip install pandas numpy scipy statsmodels yfinance

# Explore a module
cd 01_AMM_Microstructure
```

Each module directory is self-contained with its own notebooks/scripts and outputs — start with **Module I** for the AMM foundations, or jump straight to the module most relevant to your interest.

---

## Citation

If you use this project in academic research, publications, educational materials, or derivative works, please cite it and provide appropriate credit to the original author.

This repository includes a `CITATION.cff` file, so GitHub provides a **"Cite this repository"** button in the repository sidebar. You can use it to obtain citations in BibTeX, APA, and other supported formats.

**Suggested citation:**

> Arain, S. U. R. (2026). *Quantitative-DeFi-Research* (Version 1.0) [Software]. https://github.com/sanaurrehmanarain/Quantitative-DeFi-Research

| | |
|---|---|
| **Author** | Sana Ur Rehman Arain |
| **Profession** | Data Scientist |
| **GitHub** | [@sanaurrehmanarain](https://github.com/sanaurrehmanarain) |
| **Contact** | sana.arain.work@gmail.com |

If you build upon this work, attribution is appreciated and helps others discover the original project.

> **Note:** The MIT License requires that the original copyright notice be retained in copies of the Software.

---

## 📜 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## ⭐ Support

If you found this project helpful, consider giving the repository a **⭐ Star** on GitHub — it helps others discover the project and motivates future improvements.
