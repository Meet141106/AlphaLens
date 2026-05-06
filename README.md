# 🔮 AlphaLens — Premium Stock Intelligence Dashboard

> **See Beyond the Market**

AlphaLens is a financial intelligence terminal built with Python. It pulls live market data, runs technical analysis, and now digs deeper — surfacing hidden patterns and cross-variable relationships that standard dashboards miss. Dark-themed, fast, and built for people who actually want to understand what's happening with a stock.

---

## What It Does

| Feature | Description |
|---|---|
| 📊 **Technical Analysis** | 50/200-day Moving Averages, breakout detection against 20-day resistance, volatility scoring |
| 📰 **News Intelligence** | Live company news from Finnhub with keyword sentiment scoring |
| 🧠 **AI Summary** | Data-driven market summaries based on cumulative returns, momentum, and volatility |
| 📂 **CSV Dataset Upload** | Upload any stock CSV — AlphaLens auto-detects columns and runs the full analysis pipeline on it |
| 🔍 **Deep Insights Engine** | Eight statistical engines that find patterns hidden across multiple variables — not surface metrics |
| 📄 **PDF Export** | ReportLab-generated dark-themed reports with tables, metrics, and AI summaries |
| 📈 **Premium Charting** | Glow-effect price lines, filled area chart, MA overlays, current price marker |
| ⚡ **Live Market Strip** | Real-time ticker for BTC, ETH, AAPL, MSFT, AMZN, TSLA, GOOGL |
| 🗂️ **Multi-Page Navigation** | Dashboard · Insights · Watchlist · News · How It Works · About |
| 🔄 **Non-blocking UI** | All data fetching runs on background threads — the UI never freezes |

---

## Deep Insights Engine

This is the most substantial feature. After you analyze a ticker (live or from CSV), AlphaLens runs 8 independent statistical engines on the price data and presents the findings as insight cards on the **Insights tab**.

The idea isn't to show you what happened — it's to show you *why*, *when*, and *for how long*. Think of it like detective work on price data.

### The 8 Engines

**📅 Day-of-Week Effect**
Groups returns by weekday and checks whether certain days consistently outperform others. A 0.2% daily edge on Thursdays versus Mondays is the kind of thing you'd never notice scrolling a chart.

**📆 Monthly Seasonality**
Averages returns per calendar month across all available years. Catches patterns like "December is reliably strong" or "September is where this stock consistently bleeds."

**📦 Volume → Price Signal**
On days where volume is in the top 10%, what does the next session do? If high-volume days are followed by price rises 67% of the time versus 53% normally, that's institutional accumulation — not noise.

**🌊 Volatility Regime**
Computes where today's intraday range (High - Low) sits relative to the full history as a histogram. A reading at the 15th percentile means unusually low volatility — which often precedes a breakout.

**📈 Overnight Gap Analysis**
Measures how often the stock opens above/below the previous close, and whether those gaps tend to continue intraday or reverse. Tells you if this is a momentum stock or a mean-reverting one.

**🔁 Streak & Reversal**
Tracks consecutive up/down days and computes the reversal probability after streaks of 3, 4, or 5 days. If 71% of 4-day win streaks end in a red day, that's a real edge.

**📉 Drawdown Profile**
Maps every peak-to-trough decline of 5%+ across the dataset. Shows max drawdown, current distance from all-time high, and how many significant dips the stock has had.

**🚨 Anomaly Detection**
Flags trading days where returns exceed 3 standard deviations from the mean — the statistical outliers. Labels them, finds the biggest single-day move, and tells you whether extreme moves skew bullish or bearish.

Each engine fires only when there's enough data to be statistically meaningful (60–365 rows depending on the engine). Cards show a severity label (Bullish / Bearish / Neutral / Informational) and an embedded chart wherever relevant — bar charts, histograms, scatter plots, pie charts.

---

## CSV Upload

AlphaLens works with any stock CSV — Kaggle datasets, Yahoo Finance exports, broker downloads, whatever.

**Column detection is automatic.** It looks for common naming patterns:

| Your column name | Detected as |
|---|---|
| `date`, `Date`, `datetime` | Date index |
| `open`, `Open`, `open_price` | Open |
| `high`, `High` | High |
| `low`, `Low` | Low |
| `close`, `Close`, `adj close`, `adjusted close` | Close |
| `volume`, `vol`, `Volume` | Volume |

If both `Close` and `Adj Close` are present, it keeps `Close` and drops the duplicate silently.

The minimum requirement is a `Close` column and at least 5 rows. Everything else is optional but enables more engines.

After upload, the full analysis pipeline runs — chart, moving averages, breakout detection, PDF export — exactly the same as with live data.

---

## Insights Toast Notification

When analysis finishes (whether from API or CSV), a notification slides in from the bottom-right corner. It shows the ticker name, how many patterns were detected, and a single button to jump to the Insights tab.

It stays on screen for 2 minutes and slides out smoothly. You can dismiss it early with the ✕ button.

---

## Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/Meet141106/AlphaLens.git
cd AlphaLens
```

### 2. Create a virtual environment
```bash
python3 -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set your Finnhub API key (optional)
Get a free key at [finnhub.io](https://finnhub.io)

```bash
export FINNHUB_API_KEY="your_api_key_here"   # Windows: set FINNHUB_API_KEY=...
```

> The app runs fine without this. News and sentiment sections are disabled gracefully if the key isn't set. The Insights engine, charting, and PDF export all work without it.

### 5. Run
```bash
python3 main.py
```

---

## Project Structure

```
AlphaLens/
├── main.py              # Everything — GUI, data engines, views, PDF generator
├── requirements.txt     # Python dependencies
├── .gitignore
└── README.md
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| GUI | [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter) |
| Market Data | [yfinance](https://github.com/ranaroussi/yfinance) |
| News & Sentiment | [Finnhub API](https://finnhub.io) |
| Data Processing | [pandas](https://pandas.pydata.org), [NumPy](https://numpy.org) |
| Charting | [Matplotlib](https://matplotlib.org) |
| PDF Reports | [ReportLab](https://www.reportlab.com) |
| Language | Python 3.10+ |

---

## PDF Export

Click **Export PDF** after analyzing any ticker to get a dark-themed report with:
- Market summary table (price, trend, risk, sentiment — color coded)
- Key metrics grid (volume, market cap, MAs, volatility)
- AI executive summary paragraph
- AlphaLens branding and footer

Works for both live API data and uploaded CSV datasets.

---

## Disclaimer

AlphaLens is for educational and informational purposes only. Nothing here is financial advice. Do your own research before making any investment decisions.

---

## Author

- **Meet** — [GitHub](https://github.com/Meet141106)
- **Innovator (vc)** — [GitHub](https://github.com/innovator-sh)

---

*Built for clarity. Designed for precision.*
