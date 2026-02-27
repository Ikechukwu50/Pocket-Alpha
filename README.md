# 📈 PocketAlpha: AI-Driven Global Equity Engine

PocketAlpha is a sophisticated market intelligence pipeline built on **n8n**. It bridges the gap between the Wall Street (US) and NGX (Nigeria) markets by synthesizing real-time price data with global geopolitical news.

## 🚀 How it Works
1. **Data Harvest:** Pulls live stock data for US and Nigerian equities via the Finnhub API.
2. **Global News Context:** Fetches the latest market-moving headlines using NewsAPI.
3. **AI Synthesis:** Uses **Google Gemini (LLM)** to correlate news sentiment with stock volatility.
4. **Decisive Reporting:** Delivers a high-conviction "Aggressive Trader" brief directly to Telegram.

## 🛠️ Tech Stack
* **Orchestration:** n8n
* **AI Logic:** Google Gemini
* **Data Sources:** Finnhub API, NewsAPI
* **Delivery:** Telegram Bot API

## 📊 Key Features
* **Cross-Market Analysis:** Simultaneous monitoring of USD and NGN equities.
* **Automated Logic:** Calculates percentage changes and volatility metrics automatically.
* **Professional Formatting:** Clean, emoji-rich reports delivered to your pocket every morning.

## 🔧 Setup
1. Import the `PocketAlpha_Workflow.json` into your n8n instance.
2. Add your API credentials for Google Gemini, Finnhub, and NewsAPI.
3. Set your Telegram Chat ID and Bot Token.
4. Activate the 'Schedule Trigger' to receive automated daily updates.

graph LR
    %% Trigger Layer
    Start([Schedule Trigger]) -->|Every Morning| News[NewsAPI]
    
    %% Data Acquisition Layer
    News -->|Headlines| Price[Finnhub API]
    Price -->|US & NG Stock Data| Agg[Data Aggregator]
    
    %% AI Intelligence Layer
    Agg -->|Structured JSON| Gemini{Google Gemini AI}
    Gemini -->|Prompt Logic| Logic[Aggressive Trader Persona]
    
    %% Delivery Layer
    Logic -->|Formatted Markdown| Telegram((Telegram Bot))
    
    %% Styling
    style Gemini fill:#4285F4,stroke:#333,stroke-width:2px,color:#fff
    style Telegram fill:#0088cc,stroke:#333,stroke-width:2px,color:#fff
    style Start fill:#34A853,stroke:#333,stroke-width:2px,color:#fff
    
