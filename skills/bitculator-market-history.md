---
name: bitculator-market-history
description: Pull OHLCV candle history, point-in-time historical prices, and whole-market history series.
api: Bitculator Data API
operations: [candleHistory, historicalPrice, marketcapHistory, globalMarketcapVolumeHistory]
generated: '2026-09-03'
method: generated
source: openapi/bitculator-data-api-openapi.json + https://bitculator.com/en/documentation/api/v1
---

# Read market history

1. **Candles.** `GET /api/v1/coins/{slug}/history` (`candleHistory`) returns OHLC + volume
   candles. Retention depends on interval: minutely ~8 days, half-hourly ~3 months, hourly
   ~6 months, daily = full history. Most recent candles in the window come back oldest-first.
   Premium indicator/history windows are plan-gated — a window above your plan returns 403
   `plan_required` with `details.required_plan` naming the tier.
2. **Point-in-time price.** `GET /api/v1/historical-price?slug=bitcoin&date=2021-04-14`
   (`historicalPrice`) — dates from 2009-01-01, not in the future; up to a 3-day fallback when
   the exact day has no data.
3. **Per-coin market cap series.** `GET /api/v1/coins/{slug}/marketcap-history`
   (`marketcapHistory`).
4. **Whole-market series.** `GET /api/v1/global/history/{metric}`
   (`globalMarketcapVolumeHistory`) with `{metric}` = `marketcap` or `volume`; granularity
   follows the period (24h half-hourly, 7d hourly, 30d/all daily).
5. All series values are decimal strings — use a decimal type, never float.
