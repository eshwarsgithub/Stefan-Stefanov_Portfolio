# SSP/2026 — Stefan Stefanov Portfolio Terminal
## Complete Build & Change Log

> **Competition:** Young Investor 2026 · Finance Club, Sofia High School of Mathematics (SMG)  
> **Team:** Mariela Bedrova and Team · MAY 2026  
> **Repo:** `eshwarsgithub/Stefan-Stefanov_Portfolio`  
> **Stack:** Single-file HTML/CSS/JS · Chart.js 4.4.0 · Served via `npx serve`

---

## Commit History

| Hash | Date | Description |
|---|---|---|
| `3a67858` | Apr 29 | Initial project scaffold |
| `0891c54` | Apr 29 | Bloomberg Terminal full build |
| `f8b523a` | Apr 29 | 20 premium features upgrade |
| `ab2a959` | Apr 29 | Correlation heatmap, backtest, drift, mobile |
| `2c734b2` | Apr 29 | Footer credit fix |
| `b675bd1` | May 31 | **Ivan Petrov → Stefan Stefanov rebrand + €700k** |
| `be98b5b` | May 31 | README.md |
| `34593db` | May 31 | `vercel.json` deployment config |
| `f74a378` | Jun 1  | **Macroeconomic analysis + allocation rationale** |
| `6ed9cc7` | Jun 1  | CHANGELOG.md |
| `62a0778` | Jun 1  | **§03.4 Sector & sub-asset allocation charts** |

---

## Phase 1 — Initial Build (Apr 29 · commits `0891c54` → `2c734b2`)

### `0891c54` — Bloomberg Terminal Portfolio Dashboard

The entire single-page terminal was built from scratch as a Bloomberg Terminal × Linear × Arc aesthetic:

**Visual Design System**
- Pitch-black canvas: `--bg: #070809`, `--bg-1: #0b0d10`, `--bg-2: #101317`
- Electric mint accent: `--acc: #5eead4`
- Typography: JetBrains Mono (numerics/code), Instrument Serif (headings), Geist (body)
- Hairline grid overlay via `body::before` CSS pseudo-element
- Ambient glow: `body::after` with radial gradients
- All 7 sections fade-in on scroll (`.fade` → `.vis` via IntersectionObserver)

**Layout Structure**
- Sticky topbar (42px): logo mark `SS`, `SSP/2026` label, live Sofia clock, `Ctrl+K` hint
- Scroll progress bar: 2px mint gradient line pinned at top
- Fixed side nav: §01–§07 dot indicators with active section highlighting
- 7 `<section class="s">` blocks with consistent `.s-head` / `.container` pattern

**§01 Executive Summary**
- 6 KPI cells: Total Mandate · Target Return · Risk Profile · Horizon · Instruments · Blended TER
- §01.1 Thesis panel: serif headline + rationale paragraph
- §01.2 Performance chart: 12-month portfolio vs 60/40 benchmark (Chart.js line, hypothetical)

**§02 Client Profile & IPS**
- Client dossier card: name, age, background, capital, income, family, interests, tax
- IPS core rules list: 6 behavioral rules (drawdown limit, TER cap, drift trigger, rebalance rule, single-stock ban, currency rule)
- IPS compliance scorecard: 5 live PASS/MONITOR/BREACH indicators wired to §03 sliders
- 3 investment goals: retirement (2052–2056), lifestyle fund, legacy/values

**§03 Asset Allocation**
- Interactive doughnut chart (Chart.js): 4 asset class rings with live legend EUR values
- 4 draggable weight sliders: Equities / Fixed Income / Real Assets / Cash
- Sliders update doughnut, compliance scorecard, and KPI block in real time
- Drift visualizer: current vs. target bars with amber (±3%) / red (±5%) IPS breach indicators
- 20-year projection chart: bull/base/bear fan from €700k
- Geographic exposure grid: 6 regions (North America 45%, Europe 32%, EM 18%, Asia-Pacific 4%, Other 1%)
- Glide path chart: stacked area 2026→2056 (55% → 40% equity target)
- Efficient frontier scatter: Stefan's mandate plotted on MPT curve
- §03.9 Bulgaria/Eurozone context panel: lev-to-euro conversion, ECB framework, tax advantages

**§04 Holdings**
- 13-instrument table: #, instrument name, ticker, asset class pill, weight %, EUR value, TER, live 24h% + sparkline, rationale note
- Filter buttons: ALL / EQ / FI / RA / CA
- Search box: real-time name/ticker filtering
- Factor exposure radar chart (Chart.js): Value / Growth / Quality / Momentum / Low Vol / ESG (6 axes)
- ESG scorecard: E: 72 AA · S: 68 A · G: 76 AA with animated bars
- Correlation heatmap: 13×13 color-coded matrix with hover tooltips (added `ab2a959`)

**§05 Risk & Behavioral**
- 4 crisis stress tests: GFC 2008 (−34%), COVID 2020 (−28%), Rate Shock 2022 (−14%), Geopolitical 2026 (−18%)
- Monte Carlo simulation: 300 paths, P10/P50/P90 fan chart (Chart.js scatter)
- Rolling drawdown chart: Jan 2020–Apr 2026 with −22% IPS limit line (added `ab2a959`)
- Historical backtest chart: portfolio vs benchmark Jan 2020–Apr 2026 (added `ab2a959`)
- 5 behavioral bias flip-cards: Loss Aversion · Recency Bias · Overconfidence · Home Bias · Mental Accounting
- Behavioral finance quiz: 5 interactive questions testing IPS knowledge and bias recognition

**§06 Implementation**
- Entry strategy: DCA over 6 months (Jan–Jun 2026) · 3 tranches · specific allocations
- Benchmark tracking panel
- Milestones timeline: 6-month DCA → 1yr review → 5yr rebalance → 2034 bond maturity → 2052–2056 retirement
- Tax efficiency panel: Bulgaria 10% flat tax vs. EU average; UCITS domicile advantage (Ireland/Luxembourg)

**§07 Conclusion**
- 3-pillar synthesis paragraph: disciplined diversification · behavioral awareness · long-term thinking
- Benjamin Graham quote
- References list: 9 sources (IMF, ECB, MSCI, BlackRock, Bulgarian National Bank, Kahneman, Vanguard, Graham, Thaler)

**JavaScript Modules (single `<script>` block, ~44,000 chars)**
- Boot sequence IIFE: 12-line CLI animation, 1.8s dissolve to main content
- Live NAV ticker: 10 instruments, animated sparkline, clamped ±0.5% random walk around €700,000
- Live clock: Sofia timezone, updates every second
- Chart.js chart builders: perfChart, allocChart, projChart, mcChart, btChart, ddChart, frontierChart, radarChart, glideChart, heatmapChart
- Scenario calculator: input capital + horizon → compute bull/base/bear terminal values
- IPS compliance watcher: observes slider values, updates scorecard PASS/MONITOR/BREACH
- IntersectionObserver: `.fade` scroll reveals
- Command palette: `Ctrl+K` opens search overlay, keyboard nav (↑↓ Enter Esc)
- Side nav: scroll spy with active section tracking
- Keyboard shortcuts: `G+1`–`G+7` section jumps, `?` help overlay, `P` print

### `f8b523a` — 20 Premium Features Upgrade

Added on top of the base build:

1. Terminal boot sequence with CLI animation (1.8s dissolve)
2. Scroll progress bar (mint gradient, pinned top)
3. Fixed side nav with active section tracking
4. Command palette (`Cmd+K`) with search + keyboard nav
5. Animated KPI counters on scroll-reveal
6. Performance chart §01: 12-month portfolio vs 60/40 benchmark
7. IPS compliance scorecard §02: live PASS/MONITOR/BREACH
8. Geographic exposure grid §03: 6-region look-through
9. Asset glide path chart §03: stacked area 2026→2056
10. Efficient frontier scatter §03: mandate on MPT curve
11. Factor exposure radar §04: 6-axis spider chart
12. ESG score breakdown §04: E/S/G bars with MSCI methodology
13. Holdings sparklines + live 24h% per row
14. Monte Carlo simulation §05: 300 paths, P10/P50/P90
15. Crisis stress test cards §05: 4 scenarios clickable
16. Behavioral finance quiz §05: 5 bias questions
17. Rolling drawdown chart §05: vs −22% IPS limit
18. Tax efficiency panel §06: Bulgaria 10% vs EU
19. Print/PDF export: `@media print` stylesheet + ⎙ PRINT button
20. Micro-interactions: ripple effects, live EUR/USD, keyboard shortcuts

### `ab2a959` — Additional Charts + Mobile

- Correlation heatmap §04: 13×13 matrix, hover tooltips
- Historical backtest chart §05: Jan 2020–Apr 2026 with COVID + rate shock visible
- Rebalancing drift visualizer §03: live current vs target bars
- Keyboard help overlay: `?` opens full shortcut cheatsheet
- Full mobile responsive: breakpoints at 768px / 480px, stacked grid, hidden side nav

### `2c734b2` — Footer Fix

- Updated footer credit from `[previous text]` to `PREPARED · MARIELA BEDROVA AND TEAM`
- Date set to `MAY 2026`

---

## Phase 2 — Stefan Stefanov Rebrand + Data Correction (May 31 · commit `b675bd1`)

Complete data overhaul to match the competition PRD client specification.

### Identity & Branding

| Before | After |
|---|---|
| `Ivan Petrov` | `Stefan Stefanov` |
| `IP` monogram | `SS` monogram |
| `IPP/2026` | `SSP/2026` |
| `IPP-26-001` | `SSP-26-001` |
| `Ivan Petrov Portfolio Terminal` | `Stefan Stefanov Portfolio Terminal` |

### Capital Recalculation (€500,000 → €700,000)

| Asset Class | Weight | Old EUR | New EUR |
|---|---|---|---|
| Equities | 55% | €275,000 | €385,000 |
| Fixed Income | 35% | €175,000 | €245,000 |
| Real Assets | 7% | €35,000 | €49,000 |
| Cash | 3% | €15,000 | €21,000 |
| **Total** | **100%** | **€500,000** | **€700,000** |

All 13 individual holding EUR values recalculated at new base.  
JS constants updated: `let nav=700000`, `const TOTAL=700000`, `START=700000`, scenario calculator default `value="700000"`.  
Nav clamp fixed: `Math.max(696500, Math.min(703500, nav+d))`.

### Client Profile Updates (§02 Dossier Card)

| Field | Before | After |
|---|---|---|
| Age | 48 | **37** |
| Background | Generic professional | **Sold EV charging station maintenance company (Germany) — exited Dec 2025** |
| Capital | €500,000 | **€700,000 deposited Jan 1, 2026** |
| Income | Employed | **Post-exit; investment returns as primary income** |
| Family | Married | **Unmarried · no children · no family formation planned** |
| Interests | Generic | **Cooking · skiing · music · annual Alps resort trip** |
| Tax | EU average | **Bulgarian flat 10%** |

### Investment Horizon & Retirement Dates

| Element | Before | After |
|---|---|---|
| Horizon | 12–20 years | **20–28 years** |
| Retirement window | 2038–2041 | **2052–2056** |
| Glide path end | 2041 | **2056** |

### Bugs Fixed During Rebrand

**1. UTF-8 BOM blank page**  
PowerShell `.NET WriteAllText` with `[System.Text.Encoding]::UTF8` adds a BOM prefix (`﻿`) to the file. Browser HTML parser rejects BOM → blank white page. Fixed by using `new System.Text.UTF8Encoding($false)` (explicit no-BOM) for all subsequent file writes.

**2. JS syntax error (apostrophe in template literal)**  
`'Perfect — Stefan's IPS is internalized!'` — the unescaped `'` in `Stefan's` terminated the single-quoted string inside a JS template literal, crashing the entire script block. Boot screen stayed permanently black (the `#boot` overlay at `z-index:9999` never received `.out` class). Fixed to `'Perfect — Stefan\'s IPS is internalized!'`. Detected via `node --check` on the extracted `<script>` block.

**3. UPPERCASE boot line missed by string replacement**  
`INIT IVAN PETROV PORTFOLIO TERMINAL` — PowerShell `.Replace()` is case-sensitive; mixed-case replacement didn't catch the all-caps boot line. Fixed with targeted Edit tool on the exact string.

### New Files Created

**`.gitignore`**
```
node_modules/
*.png
*.jpg
*.jpeg
*.docx
```

**`README.md`** — 104-line project overview including:
- Client profile table (Stefan Stefanov, all attributes)
- Portfolio metrics table (€700k, 6.0–6.5% target, 20–28yr horizon, 0.22% TER, Sharpe ~0.60)
- All 18 UI/UX features listed
- Section map §01–§07
- `npm install && npm run dev` quickstart
- Competition details and submission info

---

## Phase 3 — Vercel Deployment Setup (May 31 · commit `34593db`)

**`vercel.json`** created:
```json
{
  "version": 2,
  "builds": [{ "src": "index.html", "use": "@vercel/static" }],
  "routes": [{ "src": "/(.*)", "dest": "/index.html" }]
}
```

**Deployment issue diagnosed and resolved:**  
Vercel GitHub App lacked access to the `Mbariela25` account (403 on repo fetch). Solution: pushed to `eshwarsgithub/Stefan-Stefanov_Portfolio` (user's own account) — Vercel deployment now connects to this repo.

**Git multi-remote setup:**
- `origin` → `Mbariela25/Ivan-Petrov-Portfolio`
- `eshwar` → `eshwarsgithub/Stefan-Stefanov_Portfolio` (primary deployment target)

---

## Phase 4 — Investment Strategy: Macroeconomic Analysis + Rationale (Jun 1 · commit `f74a378`)

Added the actual investment strategy substance required by the PRD's 5 evaluation criteria (macroeconomic analysis #3, investment goal understanding #1, financial calculation rationale #4).

### New CSS Classes Added (to `<style>` block)

```css
.stat-box        — metric card (bg-2 background, rounded, padded)
.stat-label      — 10px uppercase label in ink-3
.stat-val        — 22px mono accent-colored figure
.stat-sub        — 11px description in ink-3
.bridge-tbl      — macro→portfolio mapping table
.bridge-tbl th   — 10px uppercase column headers
.bridge-tbl td   — 9px padded cells, hover highlight
```

### §01.1 Thesis — Expanded (lines ~908–930)

Previous: 2 paragraphs describing what the portfolio is.  
Updated: 4 paragraphs that argue for the portfolio:

- **Para 1** (unchanged): Business exit narrative — EV charging, Germany, structured counterpart to liquidity
- **Para 2** (new): ECB dovish pivot context — 4.0% → 2.5% rate cut justifies bond duration extension; disinflation (2.2% CPI) supports equities; Bulgaria Eurozone accession eliminates FX risk
- **Para 3** (new): Deployment timing rationale — WHY January 2026 is the right entry point
- **Para 4** (new): Personality-portfolio match — practical/analytical/disciplined Stefan → low-cost, passive, IPS-governed structure; behavioral bias architecture

### §01.3 — "2026 Macro Environment" (new panel)

4 stat boxes:
- **Global GDP Growth:** 3.1% · IMF 2026 · US 2.2% · Eurozone 0.9% · EM 4.1%
- **ECB Deposit Rate:** 2.50% · cutting cycle 4.0% → 2.5% confirmed
- **Eurozone CPI:** 2.2% · down from 10.6% peak (2022)
- **Bulgaria 2026:** EUR Zone · lev–euro conversion · ECB framework access

2 narrative paragraphs:
- Geopolitical environment: Russia-Ukraine → energy transition acceleration; US-China decoupling → EM diversification; Middle East → oil tail risk; NATO defence spending uplift
- Energy transition tailwind: €1T+ global clean energy investment (IEA 2025); EU Green Deal + IRA spillovers; Stefan's EV charging expertise as portfolio conviction edge

### §01.4 — "Macro → Portfolio Bridge" (new panel)

Table mapping 8 macro themes directly to portfolio instruments:

| Macro Theme | Portfolio Response |
|---|---|
| ECB rate cuts → falling EUR yields | IEGY duration extension · IEBC spread compression |
| Disinflation + real earnings growth | Equities 55% · IWDA core at 25% |
| Energy transition acceleration | INFR revenue uplift · ESG tilt via SAWD |
| Bulgaria → Eurozone accession 2026 | All EUR-denominated · BULGAR strategic hold |
| US tech leadership + AI cycle | XDWT capped at 5% — conviction with overconfidence guard |
| EM growth recovery (Asia/India) | EIMI 8% · supply-chain diversification |
| Residual inflation + housing pressure | INFR + IWDP (7% real assets total) |
| Geopolitical uncertainty | IHYG capped at 5% · MMF 3% behavioral anchor |

### §03.0 — "Allocation Rationale" (new panel, before doughnut chart)

4-column grid explaining the WHY behind each allocation bucket:

**55% Equities:**  
37yo with 20–28yr horizon; equity risk premium is the only lever that hits 6.0–6.5% target; ECB pivot + disinflation = equity-supportive 2026 entry; −22% IPS drawdown limit consistent with 55% equity historical max drawdown.

**35% Fixed Income:**  
Kahneman & Tversky (1979): losses feel 2× more painful — bond floor prevents panic selling; 4 sub-buckets (sovereign IEGY 12%, IG credit IEBC 10%, capped HY IHYG 5%, rate buffer CSH2 4%); BULGAR 4% anchored by ECB membership post-accession.

**7% Real Assets:**  
CPI 2.2% hides structural inflation pressures (energy transition, housing, defence); INFR = inflation-linked regulated utility revenues; Stefan's EV background makes INFR a conviction hold; IWDP adds property linkage without illiquidity penalty.

**3% Cash (MMF):**  
Pre-committed behavioral architecture (Dr. Ivanchev framework); covers 12+ months of Alps trip + lifestyle costs; prevents forced equity selling at market lows; zero-reason selling is the #1 individual investor wealth destroyer.

### §04 Holdings — Updated Rationale Notes (7 of 13)

| Ticker | Old Rationale | Updated Rationale |
|---|---|---|
| IWDA | Core diversification — antidote to business concentration | Core equity (25%) — ECB rate cut + disinflation tailwind · antidote to single-business concentration |
| EXW1 | Eurozone tilt; aligned with post-accession narrative | Eurozone tilt — ECB cutting cycle + Bulgaria post-accession EUR convergence trade |
| EIMI | AI/tech tailwinds — aligned with global technology growth trends | EM recovery — Asia/India supply-chain diversification · US-China decoupling beneficiary |
| SAWD | Honors ESG values — near-zero tracking-error vs. parent index | ESG screen — energy transition alignment · near-zero tracking error vs. MSCI World parent |
| XDWT | Tech conviction — capped vs. overconfidence bias | AI/tech cycle conviction — US tech leadership 2026 · hard-capped at 5% vs. overconfidence bias |
| BULGAR | Patriotic conviction · matures aligned with horizon | Bulgaria Eurozone accession 2026 — sovereign spread removal · 3.125% coupon · matures 2034 |
| INFR | Inflation-linked revenues — aligned with Stefan's infrastructure business background | Energy transition infrastructure — Stefan's EV industry insight · inflation-linked utility revenues |

### §07 Conclusion — Added Macro Synthesis Paragraph

New paragraph added before Graham quote:

> "The 2026 macro environment validated the deployment timing: the ECB's dovish pivot created a rare window to extend fixed-income duration and capture bond price appreciation as yields fall; confirmed Eurozone disinflation removed the 2022–2023 valuation headwind from equities; and Bulgaria's Eurozone accession eliminated residual currency risk for the entire portfolio. Stefan's EV charging background — built during Europe's first infrastructure investment supercycle — positions him to recognise the second one as it unfolds."

---

## Current State of `index.html`

| Metric | Value |
|---|---|
| Total lines | ~2,740 |
| `<style>` block | ~715 lines |
| `<script>` block | ~44,200 chars |
| Chart.js charts | 10 (perf, alloc, proj, MC, backtest, drawdown, frontier, radar, glide, heatmap) |
| Sections | §01–§07 |
| Subsection panels | 20+ labeled with `§XX.Y` index tags |
| New panels added (Jun 1) | 3 (§01.3, §01.4, §03.0) |

---

## Competition PRD Checklist

| PRD Criterion | Status | Where |
|---|---|---|
| Understanding of Stefan's investment goals, desires, interests, required return | ✅ | §02 Dossier + Goals + IPS rules; §01.1 Thesis |
| Organization and clarity | ✅ | 7-section structure, labeled panels, side nav, command palette |
| Macroeconomic analysis | ✅ | §01.3 Macro Environment (IMF/ECB/IEA data) + §01.4 Macro→Portfolio Bridge |
| Financial calculations, diversification, risk management | ✅ | §03 (allocation with rationale), §04 (13 holdings), §05 (Monte Carlo, stress tests, drawdown) |
| Realistic investment approach | ✅ | UCITS ETFs + listed bonds only, 0.22% TER, passive index-based, DCA entry strategy, tax-efficient domicile |

---

## Phase 5 — Sector & Sub-Asset Allocation Charts (Jun 1 · commit `62a0778`)

The PRD requires the portfolio allocation to be "visually presented" showing **asset allocation, sector allocation, and respective weights**. The existing §03.1 doughnut only covered the top-level 4-class split. This phase adds the missing sector and fixed-income breakdown charts.

### §03.4 — New Panel: "SECTOR & SUB-ASSET ALLOCATION"

Two side-by-side doughnut charts inserted before the §03.5 20-year projection panel.

**Left chart — `sectorChart` (Equity Sector Breakdown)**

Blended look-through across all 5 equity ETFs (IWDA 25%, EXW1 10%, EIMI 8%, SAWD 7%, XDWT 5%) against the 55% equity sleeve (€385,000):

| Sector | % of Equities | EUR Value |
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

Technology weight elevated to 28% because XDWT (5% of portfolio) is 100% technology, boosting the blended sector tilt above the MSCI World baseline of ~24%.

**Right chart — `fiChart` (Fixed Income Sub-Allocation)**

Breakdown of the 35% fixed income sleeve (€245,000) by instrument bucket:

| Bucket | Instrument | % of FI | EUR Value |
|---|---|---|---|
| Government Bonds | IEGY | 34% | €84,000 |
| IG Corporate | IEBC | 29% | €70,000 |
| High Yield | IHYG | 14% | €35,000 |
| Bulgaria Sovereign | BULGAR | 11% | €28,000 |
| Short Duration | CSH2 | 11% | €28,000 |

**Implementation details**
- Both charts use `type:'doughnut'` with `cutout:'62%'`
- Each wrapped in `try/catch` to match existing chart error handling pattern
- HTML legends use a 4-column CSS grid: color swatch · name · weight % · EUR value
- Hover tooltips show label + percentage (Chart.js callback)
- Charts initialized immediately after the `ring` doughnut chart in the JS block

**PRD requirement now fully met:**

| Requirement | Before | After |
|---|---|---|
| Asset allocation (pie chart) | ✅ §03.1 doughnut | ✅ |
| Sector allocation (pie chart) | ❌ missing | ✅ §03.4 equity sector doughnut |
| Sub-asset allocation | ❌ missing | ✅ §03.4 fixed income breakdown doughnut |
| Portfolio weights visible | ✅ §03.1 legend | ✅ both new charts include % + EUR legends |

---

## Repository Structure

```
Ivan-Petrov-Portfolio/
├── index.html              ← Main application (sole file served)
├── README.md               ← Project overview + competition info
├── CHANGELOG.md            ← This file
├── vercel.json             ← Static deployment config
├── .gitignore              ← Excludes node_modules, images, docx
├── package.json            ← npx serve dev script
├── package-lock.json       ← Lockfile
├── PRD.md                  ← Competition brief (reference only)
├── chart.py                ← Python chart generation script (legacy)
├── generate_html.py        ← Python HTML generator (legacy)
├── Ivan_Petrov_Portfolio_Report.md   ← Original report (legacy)
└── Young_Investor_2026_Translation.docx  ← Competition spec (gitignored)
```

---

*Last updated: June 1, 2026 · SSP-26-001 · commit `62a0778`*
