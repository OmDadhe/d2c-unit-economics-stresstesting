# D2C Unit Economics Stress-Test: Mamaearth vs boAt

> Reverse-engineered CAC, LTV, and unit economics for two listed Indian D2C brands using public SEBI/BSE filings — stress-tested sustainability under three forward scenarios and quantified intervention ROI in ₹ crore.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![Plotly](https://img.shields.io/badge/Plotly-Interactive-purple)](https://plotly.com)
[![Data](https://img.shields.io/badge/Data-Public%20SEBI%2FBSE-green)](https://sebi.gov.in)
[![Approach](https://img.shields.io/badge/Approach-No%20Kaggle%2C%20No%20ML-orange)]()

---

## The Problem

India's D2C market hit an inflection point post-2022. CAC inflated ~30% YoY while the funding slowdown forced a shift from growth-at-any-cost to profitability. The question this project answers:

**At current CAC inflation, when does LTV:CAC cross below the 3x sustainability threshold — and what intervention has the highest ROI to prevent it?**

Two brands. Two different stress-test narratives. Both publicly filed.

| Brand | Narrative | Data Source |
|-------|-----------|-------------|
| **Mamaearth** (Honasa Consumer — BSE: 543832) | Operating profit margin 7.1% → 3.3% in one year. Derived LTV:CAC well below the 3x threshold. | BSE Annual Reports FY22–FY25 |
| **boAt** (Imagine Marketing) | Turned profitable at 4.64% EBITDA after two loss years. IPO pending. Derived LTV:CAC healthy at 4.65x — but fragile under CAC inflation. | SEBI DRHP (Oct 2025) |

---

## A Note on Methodology

Neither brand directly discloses CAC or LTV. This project derives them from public filings using documented assumptions. Every derived metric is clearly labelled, with its formula, data source, assumption, and confidence level in [`docs/methodology.md`](docs/methodology.md).

**Directly disclosed (from filings):** Revenue, Gross Profit, Marketing Spend, Active Consumer base, Repeat Purchase Rate, EBITDA margin, Channel Mix.

**Derived with documented assumptions:** CAC, AOV, Orders per customer, Customer Lifespan, LTV, LTV:CAC, Payback Period.

The LTV:CAC finding for Mamaearth (below 3x threshold) holds under sensitivity testing across all reasonable new customer assumptions — see [`docs/methodology.md`](docs/methodology.md) for the full sensitivity table.

---

## Key Findings

### Mamaearth — Unit Economics Under Structural Stress

| Metric | FY24 | FY25 | Source |
|--------|------|------|--------|
| Operating Profit Margin | 7.1% | 3.3% | Q4FY25 earnings call (direct disclosure) |
| Marketing Spend | ₹559 Cr | ₹618 Cr | BSE Annual Report (direct disclosure) |
| Active Consumers | 9.3 Mn | 10.8 Mn | Investor presentation (direct disclosure) |
| Gross Margin | 71.5% | 71.1% | Calculated from P&L |
| **Derived CAC** | ~₹2,200 | **₹2,943** | Marketing Spend ÷ Estimated New Customers |
| **Derived LTV** | ~₹3,100 | **₹2,677** | AOV × Orders/Yr × GM% × Lifespan |
| **Derived LTV:CAC** | ~1.41x | **~0.91x** | Derived — see methodology note |

Mamaearth's derived LTV:CAC is well below the 3x industry threshold and declining. The structural driver is a low AOV (₹581) against a high CAC (₹2,943) — the gap cannot be closed by acquisition efficiency alone. **Sensitivity check: even assuming 5 million new customer acquisitions (highly optimistic vs. the ~1.5 Mn active base delta), LTV:CAC remains at 2.17x — still below threshold.**

### boAt — Healthy Today, Vulnerable Forward

| Metric | FY24 | FY25 | Source |
|--------|------|------|--------|
| EBITDA Margin | -0.4% | 4.64% | Press release (direct disclosure) |
| Marketing Spend | ₹465 Cr | ₹431 Cr | DRHP restated P&L (direct disclosure) |
| Online/Offline Split | 72% / 28% | 70.55% / 29.45% | DRHP (direct disclosure) |
| Gross Margin | 31.4% | 31.5% | Calculated from DRHP P&L |
| **Derived CAC** | ~₹1,190 | **₹937** | Marketing Spend ÷ Estimated New Customers |
| **Derived LTV** | ~₹3,800 | **₹4,360** | AOV × Orders/Yr × GM% × Lifespan |
| **Derived LTV:CAC** | ~3.2x | **~4.65x** | Derived — see methodology note |

FY25 turnaround driven by marketing cost discipline. LTV:CAC healthy, but bear case projects breach to 2.49x by FY27.

---

## Scenario Model

Bear case = documented 2022–2024 actual CAC inflation rate (Unicommerce D2C Report 2024).

| Scenario | Assumption | Mamaearth FY28 | boAt FY28 | Assessment |
|----------|-----------|----------------|-----------|------------|
| 🔴 Bear | CAC +30% YoY, LTV -5% | 0.35x | 1.82x | Both breach |
| 🟡 Base | CAC +15% YoY, LTV +2% | 0.63x | 3.41x | Mamaearth critical; boAt manageable |
| 🟢 Bull | CAC -10% YoY, LTV +8% | 1.68x | 7.20x | Mamaearth recovering; boAt strong |

The base case is not safe for Mamaearth. Even moderated CAC inflation keeps derived LTV:CAC well below 3x through FY28 — confirming a structural AOV/LTV problem, not a marketing efficiency problem.

---

## Intervention ROI

### Mamaearth

| Intervention | Investment | LTV:CAC Impact | Revenue Impact | ROI |
|-------------|-----------|---------------|----------------|-----|
| AOV Increase (Bundling) | ₹3 Cr | +0.11x | ₹248 Cr | **80x** |
| CAC Reduction (Organic Shift) | ₹0 (reallocation) | +0.09x | ₹103 Cr | — |
| Retention (CRM/Loyalty) | ₹31 Cr | +0.25x | ₹33 Cr | 1.1x |

No single intervention moves Mamaearth above 3x. The structural fix is AOV expansion.

### boAt

| Intervention | Investment | LTV:CAC Impact | Revenue Impact | ROI |
|-------------|-----------|---------------|----------------|-----|
| AOV Increase (Premium Wearables) | ₹15 Cr | +0.56x | ₹368 Cr | **24x** |
| CAC Reduction (Organic Shift) | ₹0 (reallocation) | +0.46x | ₹154 Cr | — |
| Retention (CRM/Loyalty) | ₹46 Cr | +0.86x | ₹182 Cr | 3.9x |

---

## Project Structure

```
d2c-unit-economics-stresstesting/
├── data/
│   ├── raw/                         # Source data (BSE Annual Reports + SEBI DRHP)
│   └── clean/
│       └── master_metrics.csv       # Single source of truth — all metrics, both brands
├── notebooks/
│   ├── 00_environment_setup.ipynb   # Setup + raw data creation
│   ├── 01_data_cleaning.ipynb       # Metric derivation (CAC, LTV, payback period)
│   ├── 02_eda.ipynb                 # 8 charts — revenue, margins, marketing, LTV:CAC
│   ├── 03_scenario_model.ipynb      # Bear/Base/Bull scenarios + intervention ROI model
│   ├── 04_dashboard.ipynb           # 9-panel Plotly dashboard + CFO memo generation
│   └── 05_documentation.ipynb       # Repo finalization
├── outputs/
│   ├── charts/                      # 8 individual charts (HTML + PNG)
│   ├── dashboard/d2c_dashboard.html # Standalone interactive dashboard
│   ├── cfo_memo_final.md            # CFO memo with scenario table + intervention rankings
│   ├── scenario_results.csv         # FY26–FY28 projections
│   └── intervention_results.csv     # Intervention ROI data
└── docs/
    ├── methodology.md               # Formula derivations, assumptions, confidence levels, sensitivity
    ├── benchmarks.md                # All thresholds with sources
    └── data_sources.md              # Source URLs + access dates
```

---

## How to Run

```bash
pip install pandas numpy plotly openpyxl kaleido
```

Run notebooks in order in Google Colab (00 → 05). See [`COLAB_INSTRUCTIONS.md`](COLAB_INSTRUCTIONS.md) for step-by-step guide.

---

## Stack

| Tool | Use |
|------|-----|
| Python, Pandas, NumPy | Data cleaning, metric derivation |
| Plotly | 8 individual charts + 9-panel interactive dashboard |
| BSE Annual Reports | Mamaearth P&L, investor presentations, Q4FY25 earnings call |
| SEBI DRHP (Oct 2025) | boAt restated financials, channel mix, product breakdown |

---

## Author

**Om Dadhe** — Data / Product Analyst  
[linkedin.com/in/contactom](https://linkedin.com/in/contactom) · [github.com/OmDadhe](https://github.com/OmDadhe) · [om-dadhe-portfolio.vercel.app](https://om-dadhe-portfolio.vercel.app)
