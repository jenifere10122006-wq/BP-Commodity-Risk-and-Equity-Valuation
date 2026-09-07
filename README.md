# BP plc: Commodity Risk Modelling & Equity Valuation

## Overview

This project combines quantitative commodity-risk analysis with a segment-level discounted cash flow valuation of BP plc.

The analysis investigates how BP's equity returns respond to Brent crude-oil movements, whether that exposure changes across different market environments, and how those findings should inform forward-looking valuation scenarios.

The project consists of two linked components:

1. A Python-based commodity exposure analysis using weekly BP, Brent, FTSE 100 and GBP/USD data.
2. A segment-level FCFF DCF translating commodity and operating assumptions into BP's implied equity value.

## Commodity Risk Analysis

I analysed 659 weekly observations and estimated BP's Brent sensitivity using multivariate OLS while controlling for FTSE 100 and GBP/USD returns.

The baseline model estimated a Brent beta of approximately 0.27 and an FTSE beta of 1.13. Brent and FTSE remained statistically significant under HAC robust inference, while GBP/USD did not.

Rolling regressions showed that BP's Brent exposure was not stable through time. The 52-week Brent beta averaged approximately 0.27 but ranged from 0.02 to 0.61.

I then tested whether this variation was associated with:

- positive versus negative Brent moves;
- prevailing Brent price regimes;
- extreme oil-price movements;
- recent Brent volatility;
- stressed equity markets;
- nonlinear Brent effects; and
- lagged returns and momentum.

The strongest conditional relationship was the prevailing Brent price regime. BP's estimated Brent beta was approximately 0.17 in low-price environments and approximately 0.35 in medium- and high-price environments.

Alternative regime definitions produced a similar pattern, while directional asymmetry, extreme moves, volatility and nonlinear specifications provided substantially weaker evidence.

## Model Validation

To reduce overfitting risk, all new model development after the initial analysis used pre-2024 data only.

Competing specifications were compared using expanding-window walk-forward validation over 2019–2023, while 2024–2026 was reserved as a final untouched holdout period.

The final holdout contained 138 observations.

| Model | Holdout R² | MAE | RMSE |
|---|---:|---:|---:|
| Baseline OLS | 0.321 | 2.62% | 3.25% |
| Price-Regime OLS | 0.378 | 2.50% | 3.11% |
| Regime + Stress OLS | 0.362 | 2.55% | 3.15% |

The simpler price-regime specification achieved the strongest final holdout performance and was therefore retained.

## Valuation Implications

The statistical results do not imply a direct cash-flow elasticity to Brent. Instead, they show that BP's equity exposure to oil has historically varied materially across commodity-price environments.

I therefore use the analysis to motivate distinct Bear, Base and Bull commodity scenarios rather than relying on one deterministic Brent assumption.

Forward-looking Brent assumptions are translated through BP's production, realised pricing, segment earnings and free cash flow in the DCF.

## DCF Valuation

The DCF forecasts BP from 2023A–2030E at segment level and converts operating earnings into unlevered free cash flow.

The model includes:

- Oil Production & Operations;
- Gas & Low Carbon Energy;
- Customers & Products;
- corporate and other costs;
- operating taxes;
- D&A;
- capital expenditure;
- working capital;
- JV/associate cash distributions;
- calculated WACC;
- terminal value;
- enterprise-to-equity bridge; and
- operating and WACC/terminal-growth sensitivity analysis.

### Base Case

- Operating enterprise value: **$224.0bn**
- Implied ordinary equity value: **$158.4bn**
- Implied share value: **739p**
- Reference market price: **540p**
- Implied upside: **37.0%**
- WACC: **7.06%**
- Perpetual growth: **1.5%**

### Operating Scenarios

- Bear: **515p/share**
- Base: **739p/share**
- Bull: **951p/share**

## Key Conclusion

BP has meaningful exposure to both Brent crude and broader equity-market movements, but its Brent sensitivity is not constant.

The strongest historical evidence indicates that BP's commodity exposure is regime-dependent, with materially greater Brent sensitivity in medium- and high-price environments than in low-price environments.

Additional model complexity did not consistently improve out-of-sample performance. The relatively simple price-regime model produced the strongest final holdout results.

The valuation therefore focuses on how different forward-looking commodity environments affect BP's operating performance, cash generation and intrinsic equity value rather than attempting to forecast one precise future oil price.

## Tools

- **Excel** — financial modelling, operating forecasts, DCF and sensitivities
- **Python** — pandas, statsmodels, scikit-learn
- **Jupyter Notebook** — analysis and model validation
