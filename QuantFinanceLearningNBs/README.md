# 03 · Quant Finance Learning Notebooks

## Overview

A structured, self-study reference covering **40+ quantitative finance concepts** — each with formal mathematical derivations, Python implementations, and visualisations. Originally built to prepare for Quantitative Risk Analyst roles, the collection now also spans the **quant-developer / robo-advisor** track (portfolio construction, rebalancing, tax, convex optimization, systems).

## What's new

Seven interview-focused notebooks (`04`–`10`) have been added alongside the original three learning modules (`01`–`03`). The originals are academic "Module" walkthroughs; the new set is a ground-up, production-oriented track written for quant-developer interviews (Scalable Capital robo-advisor context).

| # | Notebook | Status |
|---|----------|--------|
| 01 | `quant_finance_01_market_fundamentals.ipynb` | Original |
| 02 | `quant_finance_02_risk_measures_mpt.ipynb` | Original |
| 03 | `quant_finance_03_strategies_backtesting.ipynb` | Original |
| 04 | `quant_finance_04_portfolio_management_fundamentals.ipynb` | **New** |
| 05 | `quant_finance_05_rebalancing_deep_dive.ipynb` | **New** |
| 06 | `quant_finance_06_risk_models.ipynb` | **New** |
| 07 | `quant_finance_07_tax_optimization.ipynb` | **New** |
| 08 | `quant_finance_08_convex_optimization.ipynb` | **New** |
| 09 | `quant_finance_09_system_design_interview.ipynb` | **New** |
| 10 | `quant_finance_10_python_techstack_cheatsheet.ipynb` | **New** |

To avoid redundancy, the new notebooks **cross-reference** the originals rather than re-deriving shared theory (see [Overlap & cross-references](#overlap--cross-references)).

## Original modules

### Module 1 — Market Fundamentals
`quant_finance_01_market_fundamentals.ipynb`

| Concept | Key Formula / Method |
|---------|---------------------|
| Simple vs. Log Returns | $r^{log} = \ln(P_t/P_{t-1})$ — time-additive |
| Volatility & Fat Tails | Rolling vol, Jarque-Bera test, QQ-plot |
| Correlation & Instability | Rolling Pearson/Spearman, correlation breakdown |
| Drawdown & Calmar Ratio | MDD, underwater period, Calmar = CAGR / \|MDD\| |
| Leverage & Margin Calls | $r_{lev} = L \cdot r - (L-1) r_f$, firesale spirals |
| Weighted Portfolio Returns | Rebalancing bonus demonstration |
| Beta & Alpha | OLS regression, rolling beta, Jensen's alpha |
| Fama-French / Carhart | 4-factor model, factor attribution chart |

### Module 2 — Risk Measures & Portfolio Theory
`quant_finance_02_risk_measures_mpt.ipynb`

| Concept | Key Formula / Method |
|---------|---------------------|
| Sharpe Ratio | $(μ_p - r_f) / σ_p$ — limits and critique |
| Sortino Ratio | Downside deviation only — better for skewed strategies |
| Information Ratio | $α / TE$ — Fundamental Law: $IR ≈ IC \cdot \sqrt{BR}$ |
| CAPM & SML | $E[r_i] = r_f + β(r_m - r_f)$ — Security Market Line |
| VaR / CVaR / Coherent Risk | Artzner axioms — why VaR fails subadditivity |
| Estimation Error Problem | Markowitz amplifies forecast errors — visualised |
| Black-Litterman | Prior + views → posterior expected returns |

### Module 3 — Strategies, Backtesting & Instruments
`quant_finance_03_strategies_backtesting.ipynb`

| Concept | Key Formula / Method |
|---------|---------------------|
| Mean Reversion | Ornstein-Uhlenbeck process, half-life = ln(2)/κ |
| Momentum | MA crossover (Golden Cross), buy/hold comparison |
| Pairs Trading | Engle-Granger cointegration, ADF test, z-score signals |
| Survivorship Bias | Quantified: phantom alpha from dead stocks |
| Look-Ahead Bias | Rolling vs. full-sample normalisation comparison |
| Walk-Forward Analysis | IS vs. OOS Sharpe ratio per window |
| Transaction Costs | Break-even turnover = Gross Alpha / TC |
| Bond Pricing & Duration | $P = Σ CF/(1+y)^t$, Macaulay & Modified Duration |
| Yield Curve | Normal, flat, inverted — recession signal |
| Corporate Actions | Dividend & split adjustment |

## New notebooks (quant-developer track)

### 04 — Portfolio Management Fundamentals
`quant_finance_04_portfolio_management_fundamentals.ipynb`
Efficient frontier & Mean-Variance Optimization, CAPM applied to equilibrium returns, Black-Litterman, Ledoit-Wolf covariance shrinkage, VaR/CVaR, and risk-parity budgeting. *Fundamentals (returns, covariance, CAPM theory) are cross-referenced to Modules 01–02.*

### 05 — Rebalancing Deep Dive
`quant_finance_05_rebalancing_deep_dive.ipynb`
Rebalancing triggers (calendar, threshold bands, cash-flow), transaction-cost taxonomy, the rebalancing problem as a convex program, tax-aware rebalancing, and scaling to production (parallelism, order netting).

### 06 — Risk Models
`quant_finance_06_risk_models.ipynb`
Systematic vs. idiosyncratic risk, EWMA & GARCH(1,1) dynamic volatility, the covariance matrix and curse of dimensionality, Ledoit-Wolf shrinkage, PCA/macro factor models, tail risk, and stress testing / risk attribution. *Formal VaR/CVaR coherence theory is cross-referenced to Module 02.*

### 07 — Tax Optimization
`quant_finance_07_tax_optimization.ipynb`
Tax-deferral compounding, German capital-gains reference (KESt, Freistellungsauftrag, Verlustverrechnung, Vorabpauschale, Teilfreistellung), tax-lot accounting as an LP, tax-loss harvesting quantified, and the pan-European landscape.

### 08 — Convex Optimization
`quant_finance_08_convex_optimization.ipynb`
Convex sets & functions, problem taxonomy (LP/QP/QCQP/SOCP/SDP), KKT conditions and complementary slackness, the closed-form MVO solution, and cvxpy in production (DCP rules, parameters, warm-starting, solver choice).

### 09 — System Design & Interview Mastery
`quant_finance_09_system_design_interview.ipynb`
End-to-end robo-advisor architecture, the rebalancing pipeline step by step, database design patterns, how to whiteboard system architecture, and model answers to common interview questions.

### 10 — Python & Tech-Stack Cheat Sheet
`quant_finance_10_python_techstack_cheatsheet.ipynb`
Python patterns (dataclasses, typing, vectorisation), NumPy & pandas for time series, production cvxpy, testing financial code, SQL for portfolio databases, and Docker / CI-CD / AWS / Terraform essentials.

## Overlap & cross-references

The new notebooks intentionally reuse — rather than duplicate — theory established in the originals. Where topics overlap, the newer notebook now points back to the canonical derivation:

| Shared topic | Canonical source | Referenced from |
|--------------|------------------|-----------------|
| Returns, variance, covariance, correlation | Module 01 | 04 (Parts 1–2) |
| Volatility & GARCH | Module 01 | 06 (Part 2 extends with EWMA + GARCH(1,1)) |
| CAPM & Security Market Line | Module 02 | 04 (Part 4, applied) |
| VaR / CVaR & coherence axioms | Module 02 | 06 (Part 6, production framing) |
| MPT & covariance estimation error | Module 02 | 04 & 06 |
| Transaction costs & slippage | Module 03 | 05 (Part 3) |

Within the new set, Ledoit-Wolf shrinkage / factor models appear in both 04 and 06 (different depth), and tax-aware rebalancing appears in both 05 and 07 (mechanics vs. tax-law detail).

## References

- de Prado, M.L. (2018). *Advances in Financial Machine Learning*. Wiley.
- Grinold, R. & Kahn, R. (1999). *Active Portfolio Management*. McGraw-Hill.
- Fama, E. & French, K. (1993). *Common Risk Factors*. Journal of Financial Economics.
- Carhart, M. (1997). *On Persistence in Mutual Fund Performance*. Journal of Finance.
- Fabozzi, F.J. (2007). *Fixed Income Analysis*. CFA Institute.
- Jegadeesh, N. & Titman, S. (1993). *Returns to Buying Winners*. Journal of Finance.
- Engle, R. & Granger, C. (1987). *Co-Integration and Error Correction*. Econometrica.
- Ledoit, O. & Wolf, M. (2004). *A Well-Conditioned Estimator for Large-Dimensional Covariance Matrices*. Journal of Multivariate Analysis.
- Rockafellar, R.T. & Uryasev, S. (2000). *Optimization of Conditional Value-at-Risk*. Journal of Risk.
- Boyd, S. & Vandenberghe, L. (2004). *Convex Optimization*. Cambridge University Press.
- Hull, J.C. (2018). *Options, Futures, and Other Derivatives*. Pearson.
