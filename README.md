# 📊 Pocket Alpha — Automated Daily Market Intelligence

> Every morning, you wake up to AI-analyzed market signals covering US and Nigerian stocks. No charts to read. No manual research. Just actionable intelligence — delivered straight to your Telegram.

Pocket Alpha is a fully autonomous market briefing system that pulls live financial news and stock data, runs it through Google Gemini AI with an aggressive trader persona, and delivers a formatted intelligence report to Telegram — every single morning on a schedule.

---

## The Problem

Retail traders and investors spend hours every morning doing the same thing: checking news, scanning stock prices, trying to figure out what matters and what doesn't. Most of that time is noise. By the time they've processed everything, the best opportunities have already moved.

## The Solution

A 5-layer automated pipeline that does all of that research autonomously, filters it through an AI with the mindset of an aggressive trader, and puts a clean, formatted briefing in your Telegram before you've finished your morning coffee.

---

## How It Works

```
⏰ Schedule Trigger (Every Morning)
          ↓
📰 NewsAPI — Financial Headlines
          ↓
📈 Finnhub API — Live US & Nigerian Stock Data
          ↓
🔗 Data Aggregator — Structured JSON Package
          ↓
🤖 Google Gemini AI — Aggressive Trader Persona Analysis
          ↓
📲 Telegram Bot — Formatted Markdown Briefing Delivered
```

### Layer by Layer

**1. Schedule Trigger**
n8n fires automatically every morning. No manual intervention needed — ever.

**2. NewsAPI — Headlines Layer**
Pulls the most relevant financial and market headlines from global sources. Filters for market-moving news only.

**3. Finnhub API — Price Data Layer**
Fetches live stock data for both US markets and the Nigerian Stock Exchange (NGX). This dual-market coverage is what makes Pocket Alpha unique — it serves both global and local Nigerian investors.

**4. Data Aggregator**
Combines headlines and price data into a clean, structured JSON payload optimized for LLM consumption. No noise. No redundancy.

**5. Google Gemini AI — The Brain**
This is where the intelligence happens. Gemini receives the structured data and is prompted with an **Aggressive Trader Persona** — analyzing the data not as a neutral observer but as someone actively looking for entry points, momentum signals, and risk flags.

**6. Telegram Bot — Delivery**
The AI analysis is formatted as clean markdown and pushed to a Telegram bot. Users receive a professional-grade briefing directly in their chat.

---

## Sample Output

```
📊 POCKET ALPHA — Morning Briefing
📅 Thursday, 24 October 2025 | 07:00 WAT

━━━━━━━━━━━━━━━━━━━━━━━━━━━

🇺🇸 US MARKET SNAPSHOT

NVDA  $487.20  ▲ +2.4%
AAPL  $229.87  ▼ -0.8%
TSLA  $248.50  ▲ +1.1%

📰 KEY HEADLINES:
• Fed signals pause on rate hikes — risk-on sentiment building
• NVDA GPU demand surge confirmed in supply chain data

🎯 GEMINI SIGNAL:
Tech momentum is real today. NVDA breaking above resistance with volume confirmation. AAPL weakness is noise — earnings catalyst in 3 days. Watch TSLA for continuation above $250.

Risk appetite: HIGH. Aggressive positioning warranted on dips.

━━━━━━━━━━━━━━━━━━━━━━━━━━━

🇳🇬 NIGERIAN MARKET (NGX)

DANGCEM  ₦452.00  ▲ +1.3%
GTCO     ₦48.75   ▼ -0.5%
MTNN     ₦198.00  ▲ +2.1%

🎯 GEMINI SIGNAL:
MTNN showing strong momentum on subscriber growth narrative. 
Banking sector soft — GTCO weakness may deepen ahead of MPC meeting.

━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚡ Powered by Pocket Alpha
```

---

## Tech Stack

| Component | Technology |
|---|---|
| Orchestration | n8n |
| News Data | NewsAPI |
| Stock Data | Finnhub API |
| AI Analysis | Google Gemini AI |
| Delivery | Telegram Bot API |
| Data Format | Structured JSON → Markdown |

---

## What Makes It Different

**Dual Market Coverage** — Most market tools cover US markets only. Pocket Alpha covers both US and Nigerian (NGX) stocks, making it genuinely useful for Nigerian investors managing mixed portfolios.

**Aggressive Trader Persona** — The AI isn't prompted to be balanced or neutral. It's prompted to think like a trader actively looking for opportunities — giving you the kind of direct, opinionated analysis you'd get from a seasoned trader, not a cautious analyst.

**Fully Autonomous** — Once set up, it runs every morning without any human input. No clicking, no triggering, no manual steps.

**Zero Ongoing Cost** — Built on free-tier APIs and n8n. After setup, the daily briefing costs effectively nothing to run.

---

## Getting Started

### Prerequisites
- n8n instance (cloud or self-hosted)
- NewsAPI key — [newsapi.org](https://newsapi.org) (free tier available)
- Finnhub API key — [finnhub.io](https://finnhub.io) (free tier available)
- Google Gemini API key — [ai.google.dev](https://ai.google.dev) (free tier available)
- Telegram Bot token — create via [@BotFather](https://t.me/BotFather) on Telegram

### Installation

```bash
git clone https://github.com/Ikechukwu50/pocket-alpha
cd pocket-alpha
```

### Setup

1. Import `workflow.json` into your n8n instance
2. Add your API credentials in n8n's credential manager:

```
NEWSAPI_KEY=your_newsapi_key
FINNHUB_API_KEY=your_finnhub_key
GEMINI_API_KEY=your_gemini_key
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_CHAT_ID=your_chat_id
```

3. Set your preferred delivery time in the Schedule Trigger node
4. Activate the workflow

### Customization

**Change the stocks monitored:**
Edit the Finnhub node to add or remove ticker symbols for US stocks and NGX symbols for Nigerian stocks.

**Adjust the AI persona:**
Edit the Gemini prompt node to change the trader persona — make it more conservative, more aggressive, or focused on a specific strategy (e.g., swing trading, value investing).

**Change delivery time:**
Adjust the Schedule Trigger to fire at whatever time suits your morning routine.

**Add more markets:**
Extend the Finnhub node to pull data from other exchanges — UK (LSE), Kenya (NSE), Ghana (GSE).

---

## Roadmap

- [ ] WhatsApp delivery option alongside Telegram
- [ ] Weekly portfolio performance summary
- [ ] Sector rotation signals
- [ ] Customizable watchlist per user
- [ ] Web dashboard for signal history
- [ ] Multi-user support (serve multiple Telegram subscribers)

---

## ⚠️ Disclaimer

Pocket Alpha is an informational tool, not financial advice. The AI analysis represents one analytical perspective and should not be the sole basis for any investment decision. Always do your own research and consult a qualified financial advisor before making investment decisions.

---

## License

MIT License — open source and free to use, modify, and deploy.

---

## Built By

**Ikechukwu C. Miller** — AI & Automation Engineer

📧 ikechukwucmiller@gmail.com
💼 [LinkedIn](https://www.linkedin.com/in/ikechukwu-miller-b272bb263)
🐙 [GitHub](https://github.com/Ikechukwu50)

> Want a custom market intelligence system built for your trading desk, investment platform, or financial community? Let's talk.
