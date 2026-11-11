# Business Requirements Document (BRD)

## 1. Project Overview

The objective of this project is to develop a Single Page Application (SPA) that monitors, calculates, and displays market sentiment in real time or near-real time (similar to the TickerTape Market Mood Index). The application will leverage **`yfinance`** as the primary data source to extract market indicators, sentiment drivers, and historical price trends, presenting them through a clean, modern interactive dashboard.

---

## 2. Core Objectives & Business Goals

* **Market Sentiment Visualization:** Provide retail investors and traders with an intuitive gauge (Fear/Greed index spectrum) indicating current market sentiment.
* **Data-Driven Insights:** Aggregate standard metrics from `yfinance` (such as volatility, market momentum, breadth, and safe-haven demand) into a unified mood score ranging from 0 to 100.
* **Low Latency & High Responsiveness:** Ensure the SPA loads fast, updates dynamically without full-page reloads, and offers responsive UI components across desktop and mobile views.

---

## 3. Scope of Work

### In-Scope

* **Backend / Data Pipeline:**
* Integration with `yfinance` python API / node wrapper to fetch index quotes (e.g., ^NSEI, ^BSESN, ^VIX, ^GSPC, S&P 500, or India VIX depending on target market).
* Sentiment engine script to normalize raw financial metrics into a composite score (0–100).
* RESTful API endpoints or WebSocket connection serving current index values, zone status, historical sentiment charts, and underlying component breakdown.


* **Frontend SPA:**
* **Interactive Sentiment Dial / Gauge:** Visual indicator displaying the current market score and zone (Extreme Fear, Fear, Greed, Extreme Greed).
* **Historical Trend Line Chart:** Interacting with timeline filters (1D, 1W, 1M, 1Y, ALL) showing index trajectory over time.
* **Indicator Breakdown Component:** Visual card grid detailing individual metric contributions (e.g., Volatility, Market Momentum, Stock Price Breadth, Net FII/DII or Volume metrics).
* **Dark/Light Theme Toggle** and clean, modern aesthetic.



### Out-of-Scope (Phase 1)

* Live trading integration or broker order execution.
* Real-time tick-level streaming (data updates on structured intervals based on `yfinance` polling rate limits).

---

## 4. Market Mood Index (MMI) Logic & Methodology

The aggregated Index Score ($0 \text{ to } 100$) will be calculated based on a weighted average of key indicators pulled via `yfinance`:

$$\text{MMI Score} = \sum_{i=1}^{n} (w_i \times S_i)$$

| Indicator Metric | `yfinance` Ticker Source | Description / Weightage |
| --- | --- | --- |
| **Market Volatility (VIX)** | `^INDIAVIX` / `^VIX` | Measures market uncertainty. High volatility pushes score toward Extreme Fear. |
| **Market Momentum** | Main Index (e.g., `^NSEI`, `^GSPC`) | Moving Average Convergence Divergence (20-day vs 50-day EMA). |
| **Price Breadth / Strength** | Sector ETF / Index Advance-Decline proxies | Ratio of stocks hitting 52-week highs vs 52-week lows. |
| **Safe Haven Demand** | Gold (`GOLDBEES.NS` / `GC=F`) vs Equities | Demand shift toward gold indicates risk-off / fear sentiment. |

### Sentiment Zones Definition

* **0 - 30:** Extreme Fear *(Potential buying opportunity / Oversold)*
* **31 - 50:** Fear *(Cautious market stance)*
* **51 - 70:** Greed *(Bullish sentiment / Momentum)*
* **71 - 100:** Extreme Greed *(Market potentially overbought / Profit booking territory)*

---

## 5. UI/UX & Functional Requirements

### 5.1 Gauge & Zone Header

* **Radial/Semi-circle Gauge:** Displays the dynamic score needle pointing to current zone color bands (Red, Amber, Light Green, Dark Green).
* **Current Zone Card:** Displays text status (e.g., *"Greed - 64.5"*) alongside time of last update.

### 5.2 Component Breakdown Grid

* Grid of individual indicator cards displaying:
* Indicator Name & Icon
* Status Badge (e.g., High Volatility / Neutral Momentum)
* Contribution weightage and percentage change.



### 5.3 Historical Sentiment Charting

* Interactive line graph showing MMI historical movement overlayed against main benchmark index values.
* Filter controls: `1D`, `1W`, `1M`, `6M`, `1Y`, `MAX`.

---

## 6. Technical Architecture & Tech Stack

```
   [ yfinance API ]
          │
          ▼
┌───────────────────┐
│ Backend Engine    │  (Python FastAPI / Node.js Express)
│ - Data Fetcher    │  Calculates composite score & caches results
│ - Score Normalizer│
└─────────┬─────────┘
          │ REST API / WebSockets
          ▼
┌───────────────────┐
│ Frontend SPA      │  (React / Vue.js + Tailwind CSS)
│ - Dashboard UI    │  Displays Radial Gauge, Breakdown Cards,
│ - Charting engine │  and Historical Line Chart (Recharts / Chart.js)
└───────────────────┘

```

* **Frontend:** React.js / Vite, Tailwind CSS, Recharts / Chart.js, Lucide-react icons.
* **Backend:** Python (FastAPI / Flask) or Node.js with `yfinance` / `pytz` / `pandas`.
* **Caching Layer:** Redis or local in-memory cache to reduce redundant `yfinance` calls and avoid rate-limiting.

---

## 7. Non-Functional Requirements

* **Performance:** SPA initial load time $< 1.5\text{ seconds}$; API response time $< 300\text{ms}$ (cached).
* **Reliability:** Graceful error handling in case `yfinance` experiences rate limits or structure changes; display fallback/stale data warning banner if updates fail.
* **Responsiveness:** Fully adaptive UI supporting Mobile ($320\text{px}+$ screen widths), Tablet, and Desktop.


## 8. UI stitch UI design
*  https://stitch.google.com/projects/6222566160645123747?pli=1

