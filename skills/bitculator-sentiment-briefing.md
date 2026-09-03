---
name: bitculator-sentiment-briefing
description: Build a whole-market sentiment briefing — Fear & Greed, Bull/Bear, altseason, indicator tally, and liquidations.
api: Bitculator Data API
operations: [globalMarketSnapshot, fearGreedIndex, bullBearIndex, altseasonIndex, marketIndicatorTally, todaysLiquidationSummary, indicatorSnapshot]
generated: '2026-09-03'
method: generated
source: openapi/bitculator-data-api-openapi.json + https://bitculator.com/en/documentation/api/v1
---

# Market sentiment briefing

1. **Anchor with the snapshot.** `GET /api/v1/global` (`globalMarketSnapshot`) — total market
   cap, 24h volume, BTC/ETH dominance, coin/exchange counts.
2. **Sentiment indices.** `GET /api/v1/sentiment/fear-greed` (`fearGreedIndex`, add
   `?coin=<slug>` for a per-coin reading with 7d/30d sub-scores),
   `GET /api/v1/sentiment/bull-bear` (`bullBearIndex`), and
   `GET /api/v1/sentiment/altseason` (`altseasonIndex`).
3. **Technical breadth.** `GET /api/v1/sentiment/indicators` (`marketIndicatorTally`) tallies
   bullish vs bearish technical indicators market-wide; per-coin, `GET
   /api/v1/coins/{slug}/indicators` (`indicatorSnapshot`) returns all 13 indicator families in
   one call. Premium indicator windows are plan-gated (403 `plan_required`).
4. **Liquidations.** `GET /api/v1/liquidations/summary` (`todaysLiquidationSummary`) — today's
   totals with the long/short split; data can be null right after the daily rollover, so handle
   null rather than treating it as zero.
5. Each step is one request against the monthly quota; the whole briefing costs ~6 requests.
   Analytics values are JSON numbers, prices decimal strings.
