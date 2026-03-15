# 03 · Quant Finance Learning Notebooks

## Overview

A structured reference covering **20+ quantitative finance concepts** — each with formal mathematical derivations, Python implementations, and visualisations. Built as a self-study resource for myself in order to prepare for Quantitative Risk Analyst roles.

## Modules

### Module 1 — Market Fundamentals
`01_market_fundamentals.ipynb`

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
`02_risk_measures_mpt.ipynb`

| Concept | Key Formula / Method |
|---------|---------------------|
| Sharpe Ratio | $(μ_p - r_f) / σ_p$ — limits and critique |
| Sortino Ratio | Downside deviation only — better for skewed strategies |
| Information Ratio | $α / TE$ — Fundamental Law: $IR ≈ IC \cdot \sqrt{BR}$ |
| CAPM & SML | $E[r_i] = r_f + β(r_m - r_f)$ — Security Market Line |
| Coherent Risk Measures | Artzner axioms — why VaR fails subadditivity |
| Estimation Error Problem | Markowitz amplifies forecast errors — visualised |
| Black-Litterman | Prior + views → posterior expected returns |

### Module 3 — Strategies, Backtesting & Instruments
`03_strategies_backtesting.ipynb`

| Concept | Key Formula / Method |
|---------|---------------------|
| Mean Reversion | Ornstein-Uhlenbeck process, half-life = ln(2)/κ |
| Momentum | MA crossover (Golden Cross), buy/hold comparison |
| Pairs Trading | Engle-Granger cointegration, ADF test, z-score signals |
| Survivorship Bias | Quantified: +X% p.a. phantom alpha from dead stocks |
| Look-Ahead Bias | Rolling vs. full-sample normalisation comparison |
| Walk-Forward Analysis | IS vs. OOS Sharpe ratio per window |
| Transaction Costs | Break-even turnover = Gross Alpha / TC |
| Bond Pricing & Duration | $P = Σ CF/(1+y)^t$, Macaulay & Modified Duration |
| Yield Curve | Normal, flat, inverted — recession signal |
| Corporate Actions | Dividend & split adjustment — phantom return elimination |

## References

- de Prado, M.L. (2018). *Advances in Financial Machine Learning*. Wiley.
- Grinold, R. & Kahn, R. (1999). *Active Portfolio Management*. McGraw-Hill.
- Fama, E. & French, K. (1993). *Common Risk Factors*. Journal of Financial Economics.
- Carhart, M. (1997). *On Persistence in Mutual Fund Performance*. Journal of Finance.
- Fabozzi, F.J. (2007). *Fixed Income Analysis*. CFA Institute.
- Jegadeesh, N. & Titman, S. (1993). *Returns to Buying Winners*. Journal of Finance.
- Engle, R. & Granger, C. (1987). *Co-Integration and Error Correction*. Econometrica.
- Hull, J.C. (2018). *Options, Futures, and Other Derivatives*. Pearson.
