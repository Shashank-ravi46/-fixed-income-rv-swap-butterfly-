Fixed Income Relative Value Framework
### SOFR Swap Curve Bootstrapping · Swap Spread Dynamics · 2s5s10s Butterfly Strategy
### USD · EUR · GBP Cross-Currency Basis Analysis

**Author:** Shashank Ravindrakumar | MSc Economics & Finance, King's College London  
**Tools:** Python · Google Colab · FRED API · ECB API · Bank of England API · Excel  
**Difficulty:** Institutional  

---

## What This Project Does

Replicates the core analytical toolkit used by rates desks at Goldman Sachs,
Deutsche Bank, and macro hedge funds (Brevan Howard, BlueCrest).

| Module | What It Builds |
|--------|---------------|
| **Swap Curve Bootstrapping** | Strips SOFR par swap rates → discount factors → zero-coupon rates using iterative analytical bootstrapping |
| **Swap Spread Analysis** | Computes USD 2y/5y/10y swap spreads vs. Treasuries — proxy for bank credit/funding risk premium |
| **2s5s10s Butterfly** | Constructs DV01-neutral curve curvature trade; z-score mean-reversion signal (entry ±1.5σ) |
| **Carry & Roll-Down** | Decomposes P&L into carry income and roll-down by tenor |
| **Backtest Engine** | 10-year backtest with Sharpe, max drawdown, Calmar, hit rate, P&L attribution |
| **XCCY Basis** | EUR/USD and GBP/USD rate differentials using ECB and BoE APIs — captures dollar funding stress regimes |

---

## Key Results

- Bootstrapped zero-coupon SOFR swap curve across **2,700+ daily observations** (2014–2026)
- 2s5s10s butterfly z-score strategy: backtested P&L decomposed into **carry + mark-to-market**
- XCCY basis analysis identifies **GFC 2008 echoes, ECB QE (2016), COVID (2020), Fed hike cycle (2022–23)**

---

## Data Sources

| Source | Data | Access |
|--------|------|--------|
| [FRED](https://fred.stlouisfed.org) | Treasury yields (DGS2/5/10), SOFR, swap rates | Free API key |
| [ECB Data Portal](https://data-api.ecb.europa.eu) | EUR AAA yield curve | No key needed |
| [Bank of England](https://www.bankofengland.co.uk/statistics) | GBP gilt yield curve, SONIA | No key needed |

---

## Project Structure
fixed-income-rv-swap-butterfly/
├── fixed_income_rv_main.ipynb    ← Full Colab notebook (15 cells)
├── outputs/
│   ├── fixed_income_rv_report.xlsx
│   └── charts/
│       ├── swap_spreads.html
│       ├── butterfly_signals.html
│       ├── carry_rolldown.html
│       ├── backtest_pnl.html
│       └── xccy_differentials.html
└── README.md

---

## Methodology Note

Swap spreads post-2016 use a proxy spread over Treasuries, clearly
documented as an approximation due to FRED DSWP series discontinuation.
True XCCY basis requires FX forward rates (Bloomberg/Refinitiv);
rate differentials used here capture dominant regime signals.
Limitations are explicitly modelled, not papered over.

---

## Academic Reference

Duarte, J., Longstaff, F., Yu, F. (2007). *Risk and Return in Fixed-Income
Arbitrage: Nickels in Front of a Steamroller?* Review of Financial Studies.

---

## Skills Demonstrated

`Swap curve bootstrapping` `Fixed income RV` `DV01-neutral positioning`
`Carry/roll-down` `Z-score mean reversion` `XCCY basis` `FRED API`
`ECB API` `BoE API` `pandas` `numpy` `scipy` `plotly` `openpyxl`

