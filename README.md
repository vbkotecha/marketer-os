# MarketerOS — MCP-Powered Marketing Intelligence for AI Agents

> The first marketing intelligence layer built specifically for AI agents. Agents query real-time marketing data — sentiment, trends, competitive analysis, content gaps — and pay per query with USDC micropayments via x402.

## The Problem

Media buying teams spend 40%+ of their time on research: analyzing competitors, monitoring trends, testing creative variations, identifying audience sentiment shifts. This work is repetitive, data-heavy, and perfectly suited for AI automation.

But AI agents can't access marketing intelligence today. There's no API layer designed for agents. Existing marketing SaaS tools (SEMrush, Sprout, SimilarWeb) are:
- Built for humans with dashboards, not for agent consumption
- Expensive ($100-500/month subscriptions)
- Not MCP-compatible
- Not pay-per-use

MarketerOS fixes this. It's an MCP server that gives AI agents programmatic access to marketing intelligence — sentiment analysis, trend detection, competitive monitoring, content gap analysis — with pay-per-query pricing via x402 USDC micropayments.

## What It Does

### 1. Sentiment Analysis (`/v1/marketing/sentiment`)
Analyze brand/product sentiment across platforms. Input a brand name, get real-time sentiment score with breakdown by platform, trend direction, and key themes driving positive/negative sentiment.

### 2. Trend Detection (`/v1/marketing/trends`)
Identify trending topics and hashtags in any niche. Agents can query "what's trending in [industry]" and get ranked results with velocity metrics.

### 3. Competitive Intelligence (`/v1/marketing/competitors`)
Monitor competitor ad strategies, creative patterns, and positioning shifts. Input a competitor URL, get their likely ad strategy, target keywords, and creative themes.

### 4. Content Gap Analysis (`/v1/marketing/content-gaps`)
Identify topics your competitors rank for that you don't. Input your domain + competitor domains, get actionable content recommendations.

### 5. Ad Copy Generation (`/v1/marketing/ad-copy`)
Generate optimized ad copy variations for Google, Meta, TikTok with platform-specific formatting, character limits, and best practices baked in.

## Architecture

```
AI Agent → MCP Protocol → MarketerOS Server → Marketing Intelligence APIs
                              ↓
                     x402 Payment Layer (USDC on Base)
```

- **Runtime:** Python FastAPI
- **Protocol:** MCP (Model Context Protocol) + REST
- **Payments:** x402 micropayments ($0.01-0.05/query)
- **Data Sources:** Web scraping, public APIs, AI analysis
- **Deployment:** Railway (live URL provided)

## MCP Integration

MarketerOS exposes an MCP endpoint that any AI agent can connect to:

```python
# Connect via MCP
from mcp import Client

client = Client("https://marketer-os.up.railway.app/mcp")
result = await client.call("marketing_sentiment", {"brand": "Stripe"})
```

## Quick Start

```bash
# Install
pip install marketer-os

# Run
marketer-os --port 8000

# Query
curl https://marketer-os.up.railway.app/v1/marketing/sentiment?brand=Stripe
```

## Why This Matters

The agent economy is emerging. AI agents are becoming autonomous actors that need to buy services. Marketing intelligence is a $50B+ market currently locked behind expensive human-facing SaaS subscriptions. MarketerOS unlocks this market for agents — pay-per-query, no subscriptions, programmatic access.

## Tech Stack

- **Backend:** Python, FastAPI, Uvicorn
- **AI:** OpenAI GPT for analysis and generation
- **Protocol:** MCP (Model Context Protocol)
- **Payments:** x402 (USDC on Base L2)
- **Deployment:** Railway
- **Monitoring:** Built-in health checks and metrics

## Roadmap

- [x] Sentiment analysis endpoint
- [x] Trend detection endpoint
- [x] Competitive intelligence endpoint
- [x] Content gap analysis endpoint
- [x] Ad copy generation endpoint
- [x] MCP server endpoint
- [ ] Google Ads API integration
- [ ] Meta Marketing API integration
- [ ] TikTok Ads API integration
- [ ] Real-time dashboard
- [ ] Agent marketplace listing

## License

MIT — Built for the It's Today Media Build Challenge

## Author

Vivek Kotecha — Building the x402 agent economy at [AIServices.to](https://aiservices.to)
