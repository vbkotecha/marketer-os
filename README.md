# AgentServices — Marketing Intelligence API

AI-powered marketing tools for media buying teams. Part of the AgentServices platform.

## What It Does

Five AI-powered endpoints that give marketing teams real-time intelligence:

1. **Brand Sentiment Analysis** — Analyze sentiment across Twitter, Reddit, TikTok
2. **Industry Trend Detection** — Catch rising trends with velocity scores before competitors
3. **Competitive Intelligence** — Reverse-engineer competitor strategy (keywords, channels, budgets)
4. **Content Gap Analysis** — Find SEO opportunities competitors rank for but you don't
5. **AI Ad Copy Generator** — Platform-specific ad copy for Google, Meta, TikTok, Taboola

## Why This Matters

Media buying teams spend hours manually researching competitors, analyzing sentiment, 
and writing ad variations. This API automates all of it with AI — turning days of 
research into seconds of API calls.

Built for the **It's Today Media $5K Build Challenge**.

## Live Demo

- **API Base:** https://marketer-os-production.up.railway.app
- **Interactive Docs:** https://marketer-os-production.up.railway.app/docs
- **MCP Manifest:** https://marketer-os-production.up.railway.app/mcp
- **GitHub:** https://github.com/vbkotecha/marketer-os

## Quick Start

```bash
# Brand sentiment
curl -X POST https://marketer-os-production.up.railway.app/v1/marketing/sentiment \
  -H "Content-Type: application/json" \
  -d '{"brand": "Tesla", "platforms": ["twitter", "reddit"]}'

# Ad copy generation
curl -X POST https://marketer-os-production.up.railway.app/v1/marketing/ad-copy \
  -H "Content-Type: application/json" \
  -d '{"product": "Your Product", "platform": "google", "count": 5}'

# Trend detection
curl -X POST https://marketer-os-production.up.railway.app/v1/marketing/trends \
  -H "Content-Type: application/json" \
  -d '{"industry": "fintech", "limit": 5}'
```

## Architecture

- **Backend:** FastAPI + Python 3.11
- **AI Engine:** OpenAI GPT-4o-mini
- **Deployment:** Railway (auto-deploy from GitHub)
- **MCP Compatible:** Streamable HTTP transport for AI tool integration

## What's Next

- Real platform data integration (Twitter API, Meta Marketing API)
- A/B testing score predictions
- Landing page generation from ad copy
- Automated campaign optimization recommendations
- x402 micropayment integration for per-request pricing

## Part of AgentServices

This marketing intelligence module is part of the larger **AgentServices** platform — 
a unified API for AI agents that includes:

- Crypto market data and DeFi yields
- DEX swap quotes across 6 chains
- Prediction market data
- IP geolocation and web metadata
- Dispute resolution (AgentCourt engine)
- **Marketing Intelligence** (this repo)

Main API: https://api.aiservices.to | GitHub: https://github.com/vbkotecha/aiservices-api

## License

MIT
