# D2C Unit Economics Stress-Test: Mamaearth vs boAt

> Reverse-engineered CAC, LTV, and unit economics for two listed Indian D2C brands using public SEBI/BSE filings — then stress-tested their sustainability under three forward scenarios and quantified intervention ROI in ₹ crore.

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
| **Mamaearth** (Honasa Consumer — BSE: 543832) | Operating profit margin 7.1% → 3.3% in one year. LTV:CAC already below the 3x threshold at **0.91x**. | BSE Annual Reports FY22–FY25 |
| **boAt** (Imagine Marketing) | Turned profitable at 4.64% EBITDA after two loss years. IPO pending. LTV:CAC healthy at **4.65x** — but fragile under CAC inflation. | SEBI DRHP (Oct 2025) |

---

## Key Findings

### Mamaearth — Already in the Danger Zone

| Metric | FY24 | FY25 | Signal |
|--------|------|------|--------|
| Operating Profit Margin | 7.1% | 3.3% | ⚠️ -380bps YoY |
| CAC (derived) | ~₹2,200 | ₹2,943 | ⚠️ +34% YoY |
| LTV (derived) | ~₹3,100 | ₹2,677 | ⚠️ Declining |
| **LTV:CAC** | ~1.41x | **0.91x** | 🔴 Below 3x threshold |
| Marketing % of Revenue | 29.1% | 29.9% | ⚠️ Near 30% danger limit |

**Mamaearth has already crossed the unit economics threshold — not approaching it.** At 0.91x, the business recovers only ₹0.91 in lifetime gross profit per ₹1 of acquisition spend. Bear case projection: 0.49x by FY27. Even the bull case (CAC -10% YoY) only recovers to 1.68x — confirming this is a structural AOV/LTV problem, not a marketing efficiency problem.

### boAt — Healthy Today, Vulnerable Forward

| Metric | FY24 | FY25 | Signal |
|--------|------|------|--------|
| EBITDA Margin | -0.4% | 4.64% | ✅ Turnaround |
| Marketing Spend | ₹465 Cr | ₹431 Cr | ✅ -7.4% cost discipline |
| **LTV:CAC** | ~3.2x | **4.65x** | ✅ Healthy |
| Wearables Revenue Mix | 35% | 37% | ✅ Higher-margin growth path |

FY25 turnaround was driven by marketing cost discipline, not revenue recovery. LTV:CAC at 4.65x gives runway, but bear case projects breach to 2.49x by FY27. At 4.64% EBITDA pre-IPO, post-listing cost inflation erases profitability within one quarter.

---

## Scenario Model

Bear case = documented 2022–2024 actual CAC inflation rate (Unicommerce D2C Report 2024).

| Scenario | Assumption | Mamaearth FY28 | boAt FY28 | Assessment |
|----------|-----------|----------------|-----------|------------|
| 🔴 Bear | CAC +30% YoY, LTV -5% | 0.35x | 1.82x | Both brands breach |
| 🟡 Base | CAC +15% YoY, LTV +2% | 0.63x | 3.41x | Mamaearth critical; boAt manageable |
| 🟢 Bull | CAC -10% YoY, LTV +8% | 1.68x | 7.20x | Mamaearth recovering; boAt strong |

The base case is not safe for Mamaearth. Even moderated CAC inflation keeps LTV:CAC well below 3x through FY28.

---

## Intervention ROI

### Mamaearth

| Intervention | Investment | LTV:CAC Impact | Revenue Impact | ROI |
|-------------|-----------|---------------|----------------|-----|
| AOV Increase (Bundling) | ₹3 Cr | 0.91x → 1.02x | ₹248 Cr | **80x** |
| CAC Reduction (Organic Shift) | ₹0 (reallocation) | 0.91x → 1.00x | ₹103 Cr | — |
| Retention (CRM/Loyalty) | ₹31 Cr | 0.91x → 1.16x | ₹33 Cr | 1.1x |

No single intervention moves Mamaearth above 3x. The structural fix is AOV expansion — 12% AOV lift at ₹3 Cr investment delivers ₹248 Cr revenue impact (80x ROI).

### boAt

| Intervention | Investment | LTV:CAC Impact | Revenue Impact | ROI |
|-------------|-----------|---------------|----------------|-----|
| AOV Increase (Premium Wearables) | ₹15 Cr | 4.65x → 5.21x | ₹368 Cr | **24x** |
| CAC Reduction (Organic Shift) | ₹0 (reallocation) | 4.65x → 5.12x | ₹154 Cr | — |
| Retention (CRM/Loyalty) | ₹46 Cr | 4.65x → 5.52x | ₹182 Cr | 3.9x |

---

## Methodology

All data from public SEBI/BSE filings. No proprietary data, no Kaggle datasets.

| Metric | Formula | Confidence |
|--------|---------|------------|
| **CAC** | Marketing Spend ÷ Estimated New Customers | Medium — new customers derived from YoY active base delta + churn |
| **LTV** | AOV × Orders/Year × Gross Margin% × Customer Lifespan | Medium — lifespan from industry benchmarks |
| **LTV:CAC** | LTV ÷ CAC | Derived |
| **Payback Period** | CAC ÷ (AOV × GM% × Orders/Year) × 12 | Medium |

**FY25 derived unit economics:**

| | Mamaearth | boAt |
|--|-----------|------|
| CAC | ₹2,943 | ₹937 |
| LTV | ₹2,677 | ₹4,360 |
| **LTV:CAC** | **0.91x** | **4.65x** |
| AOV | ₹581 | ₹2,326 |
| Gross Margin | 71.1% | 31.5% |

Full derivation logic, assumptions, and confidence levels: [`docs/methodology.md`](docs/methodology.md)

---

## Project Structure

```
d2c-unit-economics-stresstesting/
├── data/
│   ├── raw/                         # Source data (BSE Annual Reports + SEBI DRHP)
│   └── clean/
│       └── master_metrics.csv       # Single source of truth — all metrics, both brands, FY22–FY25
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
│   ├── scenario_results.csv         # FY26–FY28 projections across all scenarios
│   └── intervention_results.csv     # Intervention ROI data
└── docs/
    ├── methodology.md               # Formula derivations, assumptions, confidence levels
    ├── benchmarks.md                # All thresholds with sources
    └── data_sources.md              # Source URLs + access dates
```

---

## How to Run

```bash
pip install pandas numpy plotly openpyxl kaleido
```

Run notebooks in order in Google Colab (00 → 05). See [`COLAB_INSTRUCTIONS.md`](COLAB_INSTRUCTIONS.md) for the full step-by-step guide.

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
