---
name: scraping
description: Web scraping with Firecrawl and Bright Data. JavaScript rendering, anti-bot bypass, structured data extraction. Use for market research, competitor analysis, documentation. Don't use for authenticated/private content.
disable-model-invocation: true
model: sonnet
effort: medium
allowed-tools: Read, Write, Bash, WebFetch
---

# Web Scraping

## Tool Selection
- Firecrawl: general scraping, JS rendering (primary tool)
- Bright Data MCP: when site blocks normal scraping (anti-bot bypass)
- Direct WebFetch: simple pages without protection

## Best Practices
- Respect robots.txt
- Rate limit requests (1-2 sec between)
- Cache results locally
- Structure output as JSON/CSV

## Legal Notes
- Public data only
- Check ToS of target site
- Don't scrape personal data without consent