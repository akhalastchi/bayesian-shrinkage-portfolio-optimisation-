# Bayesian Shrinkage Portfolio Optimisation

## Overview

This project investigates whether Bayesian hierarchical shrinkage of expected returns can improve portfolio stability and performance relative to classical mean-variance optimisation.

Three portfolio construction approaches are compared:

1. Classical Mean-Variance Optimisation
2. Ledoit-Wolf Covariance Shrinkage
3. Bayesian Hierarchical Mean Shrinkage + Ledoit-Wolf Covariance Shrinkage

## Methodology

### Data

- ETFs: SPY, QQQ, GLD, EEM, EFA, IWM, TLT
- Daily adjusted prices from Yahoo Finance
- 3-year estimation window

### Bayesian Model

A hierarchical Bayesian model is used to estimate expected returns:

- Global expected return parameter
- Asset-level expected returns
- Non-centred parameterisation
- PyMC NUTS sampler

### Results

| Portfolio | Return | Volatility | Sharpe |
|------------|---------:|---------:|---------:|
| Classical | 22.40% | 13.09% | 1.56 |
| Ledoit-Wolf | 22.74% | 13.28% | 1.56 |
| Bayesian + Ledoit-Wolf | 16.27% | 10.81% | 1.31 |

Key findings:

- Bayesian shrinkage successfully reduced extreme return estimates.
- Posterior diagnostics showed good convergence.
- Bayesian estimates were more conservative.
- Shrinkage did not improve in-sample Sharpe ratio for this ETF universe.
