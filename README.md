
# D2C Unit Economics Stress-Test: Mamaearth vs boAt

> *A purely analytical, public-data project that reverse-engineers CAC, LTV, and unit economics for two listed Indian D2C brands — then stress-tests their sustainability under three forward scenarios.*

---

## Problem Statement

India's D2C market is at an inflection point. After years of growth-at-any-cost, the post-2022 funding slowdown has forced a reckoning with unit economics. CAC has inflated ~30% YoY across Indian D2C brands. The critical question is: **at current CAC inflation, when does LTV:CAC cross below the 3x sustainability threshold — and what intervention has the highest ROI to prevent it?**

This project answers that question for two publicly filed Indian D2C brands:
- **Mamaearth (Honasa Consumer Ltd)** — BSE-listed, operating profit margin halved from 7.1% (FY24) to 3.3% (FY25)
- **boAt (Imagine Marketing Ltd)** — SEBI DRHP filed, turned profitable in FY25 at 4.64% EBITDA after two loss years

---

## Methodology

All data sourced from public SEBI/BSE filings:
- Mamaearth: BSE Annual Reports FY22–FY25, Investor Presentations, Q4FY25 Earnings Call
- boAt: SEBI DRHP (October 2025), FY25 press release

**Key derived metrics:**
- `CAC = Marketing Spend / Estimated New Customers`
- `LTV = AOV × Orders/Year × Gross Margin % × Customer Lifespan`
- `Payback Period = CAC / (AOV × GM% × Orders/Year) × 12 months`

Full derivation logic, assumptions, and confidence levels: [`docs/methodology.md`](docs/methodology.md)

---

## Key Findings

### Mamaearth
- Operating profit margin: **7.1% (FY24) → 3.3% (FY25)** — 380bps deterioration despite ₹146Cr revenue growth
- Marketing spend as % of revenue: **29.1% → 29.9%** — approaching the 30% D2C beauty danger threshold
- LTV:CAC: Currently above 3x threshold, but declining trajectory signals structural pressure
- **Bear case projection:** LTV:CAC breaches 3x by FY27 if CAC inflation continues at 30% YoY

### boAt
- FY25 EBITDA turnaround to **4.64%** driven by marketing cost discipline (spend reduced 7.4% YoY)
- Channel shift: online declining from 78% to 70.55% of revenue — margin implications for IPO narrative
- Wearables growing to **37% of revenue** — the higher-margin path forward
- **IPO risk:** 4.64% EBITDA margin leaves minimal buffer for post-listing cost increases

### Intervention ROI Rankings (per brand)
| Brand | Highest ROI Intervention | LTV:CAC Improvement |
|-------|-------------------------|---------------------|
| Mamaearth | Retention (CRM/Loyalty) | See scenario model |
| boAt | CAC Reduction (Organic Shift) | See scenario model |

---

## Scenario Model Results

| Scenario | Mamaearth FY28 | boAt FY28 | Status |
|----------|---------------|-----------|--------|
| Bear (CAC +30% YoY) | Near/below 3x | Near 3x | ⚠️ Critical |
| Base (CAC +15% YoY) | Above 3x | Above 3x | ✅ Manageable |
| Bull (CAC -10% YoY) | Healthy 5x+ | Healthy 5x+ | ✅ Strong |

---

## Project Structure

```
d2c-unit-economics-stresstesting/
├── data/
│   ├── raw/                    # Source data files (from SEBI/BSE filings)
│   └── clean/
│       └── master_metrics.csv  # Single source of truth — all metrics, both brands
├── notebooks/
│   ├── 00_environment_setup.ipynb
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_scenario_model.ipynb
│   └── 04_dashboard.ipynb
├── outputs/
│   ├── charts/                 # Individual chart exports (HTML + PNG)
│   ├── dashboard/              # Full interactive dashboard
│   ├── cfo_memo.md             # CFO memo output
│   ├── scenario_results.csv    # Scenario projection data
│   └── intervention_results.csv
└── docs/
    ├── methodology.md          # Full derivation logic + assumptions
    ├── benchmarks.md           # Benchmark thresholds with sources
    └── data_sources.md         # All source URLs + access dates
```

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/OmDadhe/d2c-unit-economics-stresstesting
cd d2c-unit-economics-stresstesting

# 2. Install dependencies
pip install pandas numpy plotly openpyxl matplotlib seaborn kaleido

# 3. Run notebooks in order (Google Colab recommended)
# 00_environment_setup.ipynb → creates raw data files
# 01_data_cleaning.ipynb    → derives all metrics
# 02_eda.ipynb               → exploratory charts
# 03_scenario_model.ipynb    → scenario + intervention model
# 04_dashboard.ipynb         → interactive dashboard + CFO memo
```

**Or run everything at once:**
```python
# In Colab: Run each notebook top-to-bottom in order 00 → 04
```

---

## Tools & Stack

| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data cleaning, metric derivation |
| Plotly | Interactive visualizations, dashboard |
| openpyxl | Excel file handling |
| SEBI/BSE Public Data | All financial inputs |

---

## Data Sources

All data is publicly available:
- [BSE India — Honasa Consumer](https://www.bseindia.com/stockinfo/AnnRepNew.html?scripcd=543832)
- [SEBI — Imagine Marketing DRHP](https://www.sebi.gov.in/filings/public-issues.html)
- Full source log: [`docs/data_sources.md`](docs/data_sources.md)

---

## Author

**Om Dadhe** — Data / Product Analyst  
🔗 [LinkedIn](https://linkedin.com/in/contactom) | 💻 [GitHub](https://github.com/OmDadhe) | 🌐 [Portfolio](https://om-dadhe-portfolio.vercel.app)

---

*This project uses only public SEBI/BSE-filed data. All derived metrics are documented with sources, assumptions, and confidence levels in [`docs/methodology.md`](docs/methodology.md).*
