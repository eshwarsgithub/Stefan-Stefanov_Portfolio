# SSP/2026 — Stefan Stefanov Portfolio Terminal

> **Young Investor 2026** · Finance Club at Sofia High School of Mathematics (SMG)
> Prepared by **Mariela Bedrova and Team** · MAY 2026

---

## Overview

An interactive, browser-based investment portfolio terminal built for the **Young Investor 2026** competition. The terminal presents a complete €700,000 investment mandate for the hypothetical client **Stefan Stefanov** — a 37-year-old Bulgarian entrepreneur who sold his EV charging station maintenance company in Germany (Dec 2025) and deposited €700,000 into a Bulgarian bank account on January 1, 2026.

The project consists of two deliverables:
- **`index.html`** — Interactive portfolio terminal (visual presentation, charts, analytics)
- **`Stefan_Stefanov_Investment_Report.md`** — Full written investment report (Word document source, 3,400 words)

---

## Client Profile

| Field | Detail |
|---|---|
| **Name** | Stefan Stefanov |
| **Age** | 37 · Sofia, Bulgaria |
| **Background** | Sold EV charging station maintenance company (Germany) — exited Dec 2025 |
| **Capital** | €700,000 (post-exit, after German taxes) |
| **Status** | Unmarried · no children · no family formation planned |
| **Interests** | Cooking · skiing · music · annual 10-day Alps resort trip (~€10,000/yr) |
| **Personality** | Practical · analytical · disciplined · patient · detail-oriented |

---

## Portfolio at a Glance

| Metric | Value |
|---|---|
| **Total Mandate** | €700,000 |
| **Target Return** | 6.0–6.5% p.a. (ECB inflation 2% + real 4%) |
| **Investment Horizon** | 20–28 years (retirement 2052–2056) |
| **Risk Profile** | Moderate — max drawdown −22%, volatility 9–11% |
| **Blended TER** | 0.22% p.a. |
| **Instruments** | 13 UCITS ETFs & listed bonds |
| **Sharpe Ratio** | ~0.60 |

### Asset Allocation

| Class | Weight | EUR Value | Rationale |
|---|---|---|---|
| Equities | 55% | €385,000 | 37yo · 26yr horizon · ECB cutting cycle supports entry |
| Fixed Income | 35% | €245,000 | Behavioral anchor · 5 sub-buckets across credit quality |
| Real Assets | 7% | €49,000 | Inflation hedge · infrastructure + REIT |
| Cash | 3% | €21,000 | Lifestyle reserve (Alps trip) · behavioral firewall |

### Equity Sector Exposure (look-through, 55% sleeve)

| Sector | Weight | EUR Value |
|---|---|---|
| Technology | 28% | €107,800 |
| Financials | 17% | €65,450 |
| Healthcare | 12% | €46,200 |
| Industrials | 11% | €42,350 |
| Consumer Discretionary | 10% | €38,500 |
| Consumer Staples | 7% | €26,950 |
| Communication Services | 7% | €26,950 |
| Energy | 4% | €15,400 |
| Materials | 3% | €11,550 |
| Other / Utilities | 1% | €3,850 |

---

## 13 Holdings

| # | Instrument | Ticker | Class | Weight | EUR Value |
|---|---|---|---|---|---|
| 01 | iShares MSCI World UCITS ETF | IWDA | Equity | 25% | €175,000 |
| 02 | iShares Core EURO STOXX 50 ETF | EXW1 | Equity | 10% | €70,000 |
| 03 | iShares MSCI Emerging Markets ETF | EIMI | Equity | 8% | €56,000 |
| 04 | iShares MSCI World ESG Screened ETF | SAWD | Equity | 7% | €49,000 |
| 05 | Xtrackers MSCI World Info Tech ETF | XDWT | Equity | 5% | €35,000 |
| 06 | iShares € Govt Bond 7–10yr ETF | IEGY | Fixed Income | 12% | €84,000 |
| 07 | iShares € Corporate Bond ETF | IEBC | Fixed Income | 10% | €70,000 |
| 08 | iShares € High Yield Corp Bond ETF | IHYG | Fixed Income | 5% | €35,000 |
| 09 | Bulgaria Republic Eurobond 3.125% 2034 | BULGAR | Fixed Income | 4% | €28,000 |
| 10 | Amundi Euro Short Duration Bond ETF | CSH2 | Fixed Income | 4% | €28,000 |
| 11 | iShares Global Infrastructure ETF | INFR | Real Assets | 4% | €28,000 |
| 12 | iShares Dev. Markets Property Yield ETF | IWDP | Real Assets | 3% | €21,000 |
| 13 | EUR Money Market Fund | MMF | Cash | 3% | €21,000 |

---

## Terminal Features

### Macroeconomic Analysis
- **§01.3 — 2026 Macro Environment** — IMF GDP forecasts, ECB rate path (4.0% → 2.5%), Eurozone CPI (2.2%), Bulgaria Eurozone accession, geopolitical context, energy transition tailwind
- **§01.4 — Macro → Portfolio Bridge** — 8 macro themes mapped to specific instruments

### Allocation
- **§03.0 — Allocation Rationale** — explicit WHY for each of 55/35/7/3 (macro + behavioral finance)
- **§03.1 — Interactive Doughnut Chart** — asset allocation with live sliders
- **§03.4 — Sector & Sub-Asset Charts** — equity sector breakdown (10 sectors) + fixed income buckets (5 sub-types)
- **§03.3 — Drift Visualiser** — real-time ±5% IPS threshold monitoring
- **§03.5 — 20-Year Projection** — bull/base/bear scenarios from €700k
- **§03.6 — Geographic Exposure** — 6-region look-through analysis
- **§03.7 — Glide Path** — 55% → 40% equity into retirement (2026–2056)
- **§03.8 — Efficient Frontier** — Stefan's mandate plotted on MPT curve

### Risk & Behavioral
- **Monte Carlo simulation** — 300 paths, P10/P50/P90 percentiles
- **Correlation heatmap** — 13×13 matrix
- **Crisis stress tests** — GFC 2008, COVID 2020, Rate Shock 2022, Geopolitical 2026
- **Rolling drawdown chart** vs −22% IPS limit
- **Backtest chart** (Jan 2020–Apr 2026 vs benchmark)
- **Behavioral quiz** — 5 questions on IPS rules & biases
- **Bias flip-cards** — Loss Aversion, Recency, Overconfidence, Home Bias, Mental Accounting

### UI / UX
- **Boot sequence** terminal animation on load
- **Live NAV** with animated sparkline
- **IPS compliance scorecard** — live PASS/MONITOR/BREACH wired to sliders
- **Factor radar** (Value, Growth, Quality, Momentum, Low Vol, ESG)
- **ESG scorecard** (E: 72 AA · S: 68 A · G: 76 AA)
- **Scenario calculator** — input capital & horizon, compute outcomes
- **Command palette** (`Ctrl+K`) and full keyboard shortcuts (`G+1`–`G+7`, `?`)
- **Print / PDF export** ready

---

## Sections

| # | Section | Panels |
|---|---|---|
| §01 | Executive Summary | KPIs · Thesis (macro-expanded) · Performance chart · §01.3 Macro Environment · §01.4 Macro→Bridge |
| §02 | Client Profile & IPS | Dossier · 6 IPS rules · Compliance scorecard · 3 investment goals |
| §03 | Asset Allocation | §03.0 Rationale · Doughnut · Sliders · Drift · **§03.4 Sector charts** · Projection · Geography · Glide path · Frontier · Bulgaria context |
| §04 | Holdings | 13-instrument table · Factor radar · ESG · Correlation heatmap |
| §05 | Risk & Behavioral | Stress tests · Monte Carlo · Drawdown · Backtest · Bias cards · Quiz |
| §06 | Implementation | DCA entry strategy · Benchmark · Milestones timeline · Tax efficiency |
| §07 | Conclusion | 3-pillar synthesis · Macro synthesis · Graham quote · 10 references |

---

## Project Files

| File | Purpose |
|---|---|
| `index.html` | Interactive portfolio terminal (sole served file) |
| `Stefan_Stefanov_Investment_Report.md` | Full written report — Word document source (3,400 words) |
| `CHANGELOG.md` | Complete build & change log across all phases |
| `README.md` | This file |
| `vercel.json` | Static deployment config for Vercel |
| `package.json` | Dev server script (`npm run dev`) |
| `PRD.md` | Competition brief (reference) |
| `.gitignore` | Excludes node_modules, images, docx |

---

## Running Locally

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

---

## PRD Compliance

| Evaluation Criterion | Status | Evidence |
|---|---|---|
| Understanding of Stefan's goals, interests, required return | ✅ | §02 dossier · required return derived (2% inflation + 4% real) · Alps trip budgeted |
| Organisation and clarity | ✅ | 7 sections · 20+ labeled panels · side nav · command palette |
| Macroeconomic analysis | ✅ | §01.3 (IMF/ECB/IEA data) · §01.4 (macro→instrument mapping) |
| Financial calculations, diversification, risk management | ✅ | §03 allocation · §04 13 holdings · §05 Monte Carlo + stress tests |
| Realistic investment approach | ✅ | UCITS-only · 0.22% TER · passive index-based · DCA entry · tax-efficient |
| Pie chart — asset allocation | ✅ | §03.1 interactive doughnut |
| Pie chart — sector allocation | ✅ | §03.4 equity sector doughnut (10 sectors) |
| Pie chart — portfolio weights | ✅ | All charts include % and EUR value legends |

---

## Competition

- **Event:** Young Investor 2026 — Finance Club, Sofia High School of Mathematics
- **Mentor:** Dr. Boyan Ivanchev (founder of behavioral finance & neuroeconomics in Bulgaria)
- **Submission:** [mlad.investitor@outlook.com](mailto:mlad.investitor@outlook.com)
- **Team size:** 1–5 participants · Grades 9–12
