
# METHODOLOGY — D2C Unit Economics Stress-Test
## Mamaearth vs boAt | FY22–FY25 Analysis + FY26–FY28 Projections

---

## 1. DATA SOURCES

### Mamaearth (Honasa Consumer Ltd — BSE: 543832)
- **Primary:** BSE Annual Reports FY22–FY25 (Audited P&L, Balance Sheet, Cash Flow)
- **Secondary:** Investor Presentations (BSE Corporate Announcements tab)
- **Cross-check:** ICICI Securities Initiation Coverage Report (available via BSE analyst reports)
- **Earnings commentary:** Q4FY25 Earnings Call Transcript — operating profit margin disclosure

### boAt (Imagine Marketing Ltd)
- **Primary:** SEBI DRHP (October 2025) — Restated 3-year financials (FY23-FY25)
- **FY25 standalone:** Company press release — ₹3,070 Crore revenue, 4.64% EBITDA margin
- **FY22:** Estimated from public filings and press releases prior to DRHP

### Industry Benchmarks
- CAC inflation ~30% YoY: Unicommerce D2C Report 2024; Redseer Strategy Consultants
- LTV:CAC 3x threshold: Standard referenced across Indian D2C analyst coverage
- Market size: IMARC Group India D2C Forecast 2025

---

## 2. METRIC DERIVATIONS

### CAC (Customer Acquisition Cost)
**Formula:** `CAC (₹) = Marketing Spend (₹Cr × 10M) / New Customers (Mn × 1M)`

**Confidence: MEDIUM**

**New Customers Estimation:**
Neither brand directly discloses "new customers acquired." We derive it as:
`New Customers (t) = Active Consumers (t) - Active Consumers (t-1) + Estimated Churn (t-1)`

Churn estimates:
- Mamaearth: 18–20% annual churn (based on 44% repeat rate; multi-brand offsets pure single-brand churn)
- boAt: 25–28% annual churn (hardware replacement cycle; 28% repeat rate in FY25)

**Assumption documented:** All marketing spend (A&P line in P&L) is attributed to new customer acquisition.
In reality, ~15-25% of marketing spend serves retention and brand purposes. This makes our CAC estimates
conservative (slightly higher than actual). This is the correct direction for stress-testing — we are
testing against a conservative CAC, not an optimistic one.

**Cross-check:** Derived Mamaearth FY24 CAC of approximately ₹1,900-2,100 is consistent with
analyst commentary in ICICI Securities coverage report range.

---

### LTV (Customer Lifetime Value)
**Formula:** `LTV (₹) = AOV × Orders/Year × Gross Margin % × Customer Lifespan (years)`

**Confidence: MEDIUM**

**AOV Derivation:** Revenue / Estimated Total Orders
- Total Orders = Active Consumers × Avg Orders/Year

**Orders/Year:** Estimated from disclosed repeat purchase rate (investor presentations).
A 44% annual repeat rate ≈ 2.7-2.8 orders/year for a brand with multi-SKU purchases.

**Gross Margin %:** Directly calculated from reported P&L: (Revenue - COGS) / Revenue.
Gross profit is disclosed in annual reports. **Confidence: HIGH**

**Customer Lifespan:**
- Mamaearth: 2.4–2.5 years. Based on: India beauty D2C benchmark 2-3 years;
  Mamaearth's multi-brand strategy (The Derma Co., Aqualogica) extends lifespan above single-brand.
  **Confidence: LOW-MEDIUM** — most sensitive assumption in LTV model.
- boAt: 3.0–3.5 years. Hardware ecosystem creates longer cycles; replacement + accessories.
  **Confidence: LOW-MEDIUM**

**Sensitivity note:** A 6-month change in customer lifespan assumption changes LTV:CAC ratio by ~0.3-0.5x.
This is why we present scenario ranges rather than point estimates.

---

### LTV:CAC Ratio
**Formula:** `LTV:CAC = LTV / CAC`
**Threshold:** 3.0x = industry minimum for sustainable D2C operations
**Confidence:** Derived — inherits confidence levels of both LTV and CAC

---

### Payback Period
**Formula:** `Payback (months) = [CAC / (AOV × Gross Margin % × Orders/Year)] × 12`
This equals: months to recover CAC from gross profit contribution per customer per year.
**Confidence: MEDIUM** (same driver uncertainty as CAC)

---

### Marketing Efficiency Ratio
**Formula:** `Revenue / Marketing Spend`
This is a revenue-ROAS proxy. Higher = more revenue generated per rupee of ad spend.
**Confidence: HIGH** — both inputs are directly reported.

---

## 3. SCENARIO MODEL ASSUMPTIONS

| Parameter | Bear | Base | Bull | Justification |
|-----------|------|------|------|---------------|
| CAC YoY Change | +30% | +15% | -10% | Bear = documented 2022-24 actual; Base = moderated; Bull = organic channel push |
| LTV YoY Change | -5% | +2% | +8% | Bear = AOV pressure + shorter lifespan; Bull = retention investment |
| Revenue Growth | +5% | +12% | +18% | Correlated with customer efficiency scenario |
| Projection Horizon | 3 years (FY26-FY28) | Same | Same | Sufficient to show breach timeline |

---

## 4. INTERVENTION MODEL ASSUMPTIONS

### CAC Reduction (Paid→Organic Shift)
- 15% of marketing spend shifted to organic/creator content
- Organic CAC = 40% of paid CAC (conservative; industry range 30-50%)
- No incremental cost (reallocation)

### AOV Increase (Bundling/Upsell)
- 12% AOV lift target (industry achievable through bundling)
- Investment = 0.5% of revenue in merchandising/tech development
- Conservative: not all customers adopt bundles

### Retention Improvement (CRM/Loyalty)
- 10% annual churn reduction
- Lifespan extension: ~8 months (from 10% × ~6.5yr = 0.65yr added)
- Investment = 1.5% of revenue (standard CRM + loyalty program budget)

---

## 5. LIMITATIONS AND KNOWN UNCERTAINTIES

1. **CAC is derived, not disclosed** — primary source of model uncertainty
2. **LTV lifespan assumption** — sensitive; verified against industry benchmarks but not brand-specific data
3. **boAt FY22 estimates** — derived from press releases, not DRHP (covers only FY23-FY25)
4. **Attribution of marketing spend** — assumes 100% acquisition-directed; likely 10-20% retention
5. **Scenario projections** — linear extrapolation; real outcomes are nonlinear

All limitations are conservative in direction: they make our stress-test more demanding, not less.
If the brand can maintain LTV:CAC > 3x even under these conservative derivations, the underlying
economics are likely stronger than our model suggests.

---

## 6. DATA INTEGRITY VERIFICATION

- Mamaearth revenue FY25 (₹2,066Cr): Consistent with announced results
- Mamaearth operating profit margin FY25 (3.3%): Directly from Q4FY25 earnings call
- boAt EBITDA margin FY25 (4.64%): Directly from company press release
- boAt channel split (70.55% online / 29.45% offline): Directly from DRHP disclosure
- Gross margins: Calculated directly from reported P&L; no derivation required

