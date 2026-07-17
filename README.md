# Quant-Portfolio

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-013243?logo=numpy)
![SciPy](https://img.shields.io/badge/SciPy-1.10%2B-8CAAE6?logo=scipy)
  
Quantitative portfolio, covering Monte Carlo simulation, portfolio optimization, and a comprehensive quant finance reference spanning **10 notebooks and 40+ concepts** — from Basel III market risk and factor models to rebalancing, tax optimization, convex optimization, and robo-advisor system design.

Built as a self-study and portfolio project in preparation for **Quantitative Development** and **AI/ML in Finance** roles.

---

## Contents

| Folder | Topic | Key Methods |
|--------|-------|-------------|
| [`MonteCarloVAR`](./MonteCarloVAR/) | Market Risk – VaR & CVaR | Monte Carlo, Cholesky, Kupiec Backtest |
| [`PortfolioOptimization`](./PortfolioOptimization/) | Portfolio Construction | Markowitz, Risk Parity, Efficient Frontier |
| [`QuantFinanceLearningNBs`](./QuantFinanceLearningNBs/) | Quant Finance Reference | 10 notebooks, 40+ concepts, theory + code |

---

## Project Highlights

### 01 · Monte Carlo Value at Risk & Expected Shortfall
- **10,000-scenario Monte Carlo engine** with correlated asset returns via Cholesky decomposition
- **VaR** at 95% and 99% confidence levels (1-day holding period)
- **Expected Shortfall / CVaR** at 97.5% — the Basel III / FRTB regulatory standard
- **Component VaR** for risk attribution by asset
- **Kupiec Proportion-of-Failures backtest** with χ² test statistic
- Multi-day scaling via the square-root-of-time rule (Basel capital horizons)

### 02 · Portfolio Optimization — Efficient Frontier & Risk Parity
- **Efficient Frontier** traced via 200-point constrained optimization (SLSQP, long-only)
- **Minimum Variance Portfolio**, **Maximum Sharpe Ratio (Tangency) Portfolio**
- **Risk Parity** — equal risk contribution allocation (Bridgewater All Weather approach)
- **Capital Market Line** and Tobin separation theorem
- Static backtest with cumulative return, drawdown, Sharpe, and Calmar ratio comparison
- Risk contribution decomposition across all strategies

### 03 · Quant Finance Learning Notebooks
**Ten** structured reference notebooks — the original three learning modules (`01`–`03`) plus **seven new quant-developer / robo-advisor notebooks** (`04`–`10`).

Original learning modules:
- **Module 1 — Market Fundamentals:** Returns, volatility, correlation, drawdown, leverage, beta/alpha, Fama-French
- **Module 2 — Risk Measures & MPT:** Sharpe, Sortino, Information Ratio, CAPM, VaR/CVaR theory, MPT & Black-Litterman
- **Module 3 — Strategies & Backtesting:** Mean reversion, momentum, pairs trading (cointegration), backtesting biases, transaction costs, fixed income, corporate actions

New quant-developer track:
- **04 — Portfolio Management Fundamentals:** MVO & efficient frontier, applied CAPM, Black-Litterman, Ledoit-Wolf shrinkage, risk parity
- **05 — Rebalancing Deep Dive:** Calendar / threshold / cash-flow triggers, transaction-cost taxonomy, rebalancing as convex optimization, production scaling
- **06 — Risk Models:** EWMA & GARCH(1,1), covariance estimation, PCA / macro factor models, tail risk, stress testing
- **07 — Tax Optimization:** German capital-gains reference, tax-lot accounting as an LP, tax-loss harvesting, pan-European landscape
- **08 — Convex Optimization:** Convexity, LP/QP/SOCP/SDP taxonomy, KKT conditions, cvxpy in production
- **09 — System Design & Interview Mastery:** End-to-end robo-advisor architecture, rebalancing pipeline, database design, whiteboarding
- **10 — Python & Tech-Stack Cheat Sheet:** Python/NumPy/pandas patterns, production cvxpy, testing, SQL, Docker / CI-CD / AWS / Terraform

To avoid redundancy, the new notebooks cross-reference the originals rather than re-deriving shared theory (returns, CAPM, VaR/CVaR coherence). Each notebook includes formal mathematical derivations, Python implementations, visualizations, and academic references.

---

## Regulatory & Theoretical Context

| Standard | Relevance in this Repository |
|----------|------------------------------|
| **Basel III / FRTB** | ES at 97.5% as primary risk metric; Kupiec backtesting |
| **Basel II** | VaR at 99%, 10-day horizon via √T rule |
| **Markowitz (1952)** | Mean-variance optimization; Efficient Frontier |
| **Fama-French (1993, 2015)** | 3- and 5-factor models; risk attribution |
| **Carhart (1997)** | 4-factor model including momentum |
| **Engle-Granger (1987)** | Cointegration test for pairs trading |
| **Black-Litterman (1992)** | Robust portfolio optimization |

---

## Getting Started

### Requirements

```bash
git clone https://github.com/FlorianEbner96/Quant-Portfolio.git
cd Quant-Portfolio
pip install -r requirements.txt
```

### Run a notebook

```bash
jupyter notebook MonteCarloVAR/var_monte_carlo.ipynb
```

All notebooks use **synthetic market data** generated from realistic parameters — no external data sources required. To use real market data, replace the data generation section with `yfinance`:

```python
import yfinance as yf
data = yf.download(['SAP.DE', 'ALV.DE', 'SIE.DE'], start='2019-01-01', end='2024-01-01')
returns = data['Adj Close'].pct_change().dropna()
```

---

## Repository Structure

```
Quant-Risk-Portfolio/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── MonteCarloVAR/
│   ├── var_monte_carlo.ipynb
│   └── README.md
│
├── PortfolioOptimization/
│   ├── portfolio_optimization.ipynb
│   └── README.md
│
└── QuantFinanceLearningNBs/
    ├── quant_finance_01_market_fundamentals.ipynb
    ├── quant_finance_02_risk_measures_mpt.ipynb
    ├── quant_finance_03_strategies_backtesting.ipynb
    ├── quant_finance_04_portfolio_management_fundamentals.ipynb
    ├── quant_finance_05_rebalancing_deep_dive.ipynb
    ├── quant_finance_06_risk_models.ipynb
    ├── quant_finance_07_tax_optimization.ipynb
    ├── quant_finance_08_convex_optimization.ipynb
    ├── quant_finance_09_system_design_interview.ipynb
    ├── quant_finance_10_python_techstack_cheatsheet.ipynb
    └── README.md
```

---

## References

- Markowitz, H. (1952). *Portfolio Selection*. Journal of Finance, 7(1), 77–91.
- Sharpe, W.F. (1964). *Capital Asset Prices: A Theory of Market Equilibrium*. Journal of Finance, 19(3).
- Fama, E. & French, K. (1993). *Common Risk Factors in the Returns on Stocks and Bonds*. Journal of Financial Economics, 33(1).
- Carhart, M. (1997). *On Persistence in Mutual Fund Performance*. Journal of Finance, 52(1).
- Engle, R. & Granger, C. (1987). *Co-Integration and Error Correction*. Econometrica, 55(2).
- Artzner, P. et al. (1999). *Coherent Measures of Risk*. Mathematical Finance, 9(3).
- Black, F. & Litterman, R. (1992). *Global Portfolio Optimization*. Financial Analysts Journal.
- Basel Committee on Banking Supervision (2019). *Minimum Capital Requirements for Market Risk (FRTB)*.
- Hull, J.C. (2018). *Options, Futures, and Other Derivatives* (10th ed.). Pearson.
- de Prado, M.L. (2018). *Advances in Financial Machine Learning*. Wiley.
- Grinold, R. & Kahn, R. (1999). *Active Portfolio Management*. McGraw-Hill.

---

## Author

**Florian Ebner**  
M.Sc. Bioinformatics · Johann Wolfgang Goethe-Universität Frankfurt  
[LinkedIn](https://www.linkedin.com/in/florian-ebner-b6a19a214) · florianebner96@googlemail.com

---

## License

This project is licensed under the MIT License — see [LICENSE](./LICENSE) for details.
