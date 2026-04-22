# 🔮 AlphaLens — Premium Stock Intelligence Dashboard

> **See Beyond the Market**

AlphaLens is a professional-grade financial intelligence terminal built with Python. It transforms raw market data into clear, actionable insights through advanced technical analysis, real-time news sentiment, and AI-driven summaries — all inside a stunning dark-themed desktop GUI.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📊 **Smart Technical Analysis** | 50/200-day Moving Averages, Breakout detection (20-day resistance), Volatility |
| 📰 **News Intelligence** | Real-time company news via Finnhub API with keyword-based sentiment scoring |
| 🧠 **AI Insight Engine** | Dynamic, rule-based market summaries combining trend + sentiment signals |
| 📄 **Professional PDF Export** | ReportLab-powered dark-themed reports with tables, metrics & AI insights |
| 📈 **Premium Charting** | Glow-effect price lines, filled area, current price marker, clean date labels |
| ⚡ **Live Market Strip** | Real-time ticker for BTC, ETH, AAPL, MSFT, AMZN, TSLA, GOOGL |
| 🗂️ **Multi-Page Navigation** | Dashboard · Watchlist · News · How It Works · About |
| 🔄 **Non-blocking UI** | All API/data calls run in background threads — zero freezing |

---

## 🚀 Getting Started

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

### 4. Set your Finnhub API key
Get a free key at [finnhub.io](https://finnhub.io)

```bash
export FINNHUB_API_KEY="your_api_key_here"   # Windows: set FINNHUB_API_KEY=...
```

> Without the key, the app still works — news/sentiment sections will be disabled gracefully.

### 5. Run the app
```bash
python3 main.py
```

---

## 🗂️ Project Structure

```
AlphaLens/
├── main.py              # Full application — GUI, engine, views
├── requirements.txt     # Python dependencies
├── .gitignore
└── README.md
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| GUI | [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter) |
| Market Data | [yfinance](https://github.com/ranaroussi/yfinance) |
| News & Sentiment | [Finnhub API](https://finnhub.io) |
| Charting | [Matplotlib](https://matplotlib.org) |
| PDF Reports | [ReportLab](https://www.reportlab.com) |
| Language | Python 3.10+ |

---

## 📄 PDF Report Export

Click **Export PDF** after analyzing any ticker to generate a dark-themed professional report including:
- Market Summary table (price, trend, risk, sentiment with color coding)
- Key Metrics grid (volume, market cap, MAs, volatility)
- AI Executive Insights paragraph
- AlphaLens branding & footer

---

## ⚠️ Disclaimer

AlphaLens is built for **educational and informational purposes only**. It does not constitute financial advice. Always conduct your own research before making investment decisions.

---

## 👤 Author

**Meet** — [GitHub](https://github.com/Meet141106)

---

*Built for clarity. Designed for precision.*
