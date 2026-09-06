# BP plc: Commodity Risk Modelling & Equity Valuation

Independent equity-research style project combining **commodity-risk analysis in Python** with a **bottom-up operating forecast and FCFF DCF valuation of BP plc**.

## Project Overview

This project examines how BP's operating performance and equity value are affected by commodity prices, production assumptions and capital allocation.

It combines two linked pieces of analysis:

1. **Python commodity-risk analysis** using weekly BP, Brent, FTSE 100 and GBP/USD data.
2. **Excel operating model and DCF** translating business drivers into segment earnings, unlevered free cash flow and implied equity value.

## Valuation Framework

**Operating drivers → Segment earnings → Adjusted EBIT → NOPAT → UFCF → DCF → Enterprise Value → Equity Value → Implied Value per Share**

The model includes:

- 2023A–2025A historical financial analysis
- 2026E–2030E operating forecasts
- Oil and gas production assumptions
- Segment-level earnings forecasts
- DD&A, capex, tax and working-capital schedules
- Unlevered free cash flow build
- WACC and terminal-value analysis
- Enterprise-to-equity bridge
- DCF sensitivity analysis
- Model checks and source support

## Commodity-Risk Analysis

The Python analysis tests BP's sensitivity to Brent crude while controlling for broader market and FX movements.

It includes:

- Baseline OLS regression
- HAC-robust inference
- Brent price-regime analysis
- Expanding-window validation
- 2024–2026 holdout testing
- Alternative interaction specifications
- Non-linear challenger modelling

The final specification retains a **price-regime OLS framework**, reflecting evidence that BP's Brent sensitivity varies across different oil-price environments.

## Tools

- **Excel** — financial modelling, operating forecasts, DCF and sensitivities
- **Python** — pandas, statsmodels, scikit-learn
- **Jupyter Notebook** — analysis and model validation

## Repository Structure

```text
BP-Commodity-Risk-and-Equity-Valuation/
├── README.md
├── BP_Financial_Model.xlsx
├── BP_Commodity_Analysis.ipynb
├── project-summary.pdf
└── images/
