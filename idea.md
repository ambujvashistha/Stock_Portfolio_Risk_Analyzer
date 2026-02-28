# 📊 Stock Portfolio Risk Analyzer

## 🚀 Project Overview

Retail investors increasingly manage diversified stock portfolios. However, understanding portfolio risk requires more than observing daily gains and losses.

Professional risk metrics such as Value at Risk (VaR), Sharpe Ratio, beta, and correlation matrices provide deeper insight into portfolio exposure. Most retail investors lack accessible tools that calculate these metrics interactively.

This project aims to build a **desktop-based Stock Portfolio Risk Analyzer** using:

- Python
- Streamlit
- NumPy
- Pandas
- Plotly
- yfinance

The objective is to bring professional-grade risk analytics to an accessible and interactive desktop application.

---

# 🎯 Problem Statement

There is no integrated, lightweight desktop tool that:

- Accepts portfolio holdings
- Processes historical price data
- Computes key financial risk metrics
- Runs Monte Carlo simulations
- Performs scenario analysis
- Visualizes risk exposure interactively

Without proper risk analysis:
- Investors underestimate volatility
- Diversification weaknesses go unnoticed
- Risk-adjusted performance remains unclear
- Decisions are made based on intuition rather than analytics

---

# 🏗️ System Architecture

## 1️⃣ Data Layer
- Fetch historical stock data using `yfinance`
- Compute daily log returns
- Handle missing data and alignment

## 2️⃣ Analytics Engine
Built using:
- NumPy (matrix operations)
- Pandas (data manipulation)

Handles:
- Statistical computation
- Risk metrics
- Simulation engine
- Optimization algorithms

## 3️⃣ Visualization Layer
Built using:
- Streamlit (UI)
- Plotly (interactive charts)

---

# 📈 Core Features

## 1️⃣ Portfolio Input
- Add multiple tickers
- Assign weights or quantities
- Adjustable:
  - Confidence level (95% / 99%)
  - Risk-free rate
  - Time horizon
  - Simulation count

---

# 📊 Risk Metrics Implementation

## 🔹 Value at Risk (VaR)

### Historical VaR
- Sort historical portfolio returns
- Extract percentile based on confidence level

### Parametric VaR (Gaussian)
\[
VaR = \mu - Z \cdot \sigma
\]

### Monte Carlo VaR
- Simulate thousands of return paths
- Use covariance matrix
- Cholesky decomposition

---

## 🔹 Conditional Value at Risk (CVaR)
\[
CVaR = E[Loss \mid Loss > VaR]
\]

Measures expected loss beyond VaR threshold.

---

## 🔹 Sharpe Ratio
\[
Sharpe = \frac{R_p - R_f}{\sigma_p}
\]

Risk-adjusted performance metric.

---

## 🔹 Sortino Ratio
\[
Sortino = \frac{R_p - R_f}{\sigma_d}
\]

Uses downside deviation instead of total volatility.

---

## 🔹 Beta
\[
\beta = \frac{Cov(R_p, R_m)}{Var(R_m)}
\]

Measures sensitivity to market index (e.g., S&P 500).

---

## 🔹 Correlation Matrix
- Pairwise asset correlation
- Identifies diversification weakness
- Displayed as heatmap

---

## 🔹 Maximum Drawdown

\[
Max\ Drawdown = \frac{Peak - Trough}{Peak}
\]

Measures largest portfolio decline from peak.

---

## 🔹 Risk Contribution per Asset

Calculates each asset’s contribution to total portfolio volatility:

\[
RC_i = w_i \cdot \frac{\partial \sigma_p}{\partial w_i}
\]

Helps identify dominant risk contributors.

---

# 🧠 Monte Carlo Simulation Engine

Simulates future portfolio returns:

\[
R = \mu \Delta t + \sigma \sqrt{\Delta t} Z
\]

- Generate correlated random variables
- Use Cholesky decomposition
- Run 10,000+ simulations
- Output:
  - Distribution of future portfolio values
  - Probability of loss
  - Tail risk

---

# 📉 Scenario Analysis

Supports stress testing:

- “What if Asset X drops 20%?”
- Volatility shock
- Correlation shock
- Market crash simulation

Recalculates:
- VaR
- CVaR
- Sharpe
- Portfolio value distribution

---

# 📊 Visualization Dashboard

Interactive visualizations using Plotly:

- Portfolio return distribution histogram
- Monte Carlo simulation paths
- Correlation heatmap
- Efficient frontier graph
- Drawdown chart
- Risk contribution bar chart
- Cumulative growth chart

---

# 🏦 Advanced Features

## 🔹 Efficient Frontier

Generate optimal portfolios by minimizing variance for given expected returns.

Outputs:
- Minimum variance portfolio
- Maximum Sharpe portfolio
- Risk-return curve

---

## 🔹 Portfolio Optimization (Markowitz)

Objective:

Minimize:
\[
w^T \Sigma w
\]

Subject to:
- Sum of weights = 1
- Target return constraint
- Optional no-short-selling constraint

---

# ⚙️ Technical Challenges

- Covariance matrix stability
- Ensuring positive semi-definite matrix
- Handling missing financial data
- Efficient Monte Carlo vectorization
- Numerical stability in optimization
- Avoiding overfitting to historical data

---

# 📅 Development Roadmap

## Phase 1 – Core Risk Metrics
- Data fetching
- Return calculation
- VaR
- Sharpe
- Beta

## Phase 2 – Visualization
- Correlation heatmap
- Risk dashboard
- Distribution plots

## Phase 3 – Monte Carlo & CVaR
- Simulation engine
- Scenario testing
- Tail risk analysis

## Phase 4 – Optimization
- Efficient frontier
- Markowitz portfolio optimization
- Risk contribution analysis

---

# 🎓 Learning Outcomes

- Financial risk modeling
- Matrix algebra in finance
- Monte Carlo simulation
- Quantitative portfolio theory
- Numerical optimization
- Statistical stability handling

---

# 💡 End Goal

To build a professional-grade, interactive Stock Portfolio Risk Analyzer that:

- Makes advanced financial analytics accessible
- Helps retail investors understand risk exposure
- Supports data-driven investment decisions
- Demonstrates strong quantitative + engineering capability

---

# 🚀 Future Scope

- Add CVaR optimization
- Add Black-Litterman model
- Add Student-t distribution for fat tails
- Add factor modeling (Fama-French)
- Add multi-currency support
- Deploy as SaaS platform

---

# 🏁 Conclusion

This project bridges quantitative finance and software engineering, creating a powerful analytics tool that brings institutional-level risk modeling to everyday investors.