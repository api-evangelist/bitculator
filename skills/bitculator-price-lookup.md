---
name: bitculator-price-lookup
description: Resolve a coin to its canonical slug and read live or per-coin prices with correct decimal handling.
api: Bitculator Data API
operations: [listCoins, getPrices, getACoinPrice, getCoinDetail]
generated: '2026-09-03'
method: generated
source: openapi/bitculator-data-api-openapi.json + https://bitculator.com/en/documentation/api/v1
---

# Look up live crypto prices

All calls need `Authorization: Bearer <key>` — keys are minted in the developer console
(free plan, no card), are prefixed `bc_`, and must stay server-side.

1. **Resolve the slug.** Coins are addressed by canonical slug (e.g. `bitcoin`), not symbol.
   If you only have a name/symbol, list with `GET /api/v1/coins` (`listCoins`) and match —
   ambiguous symbols resolve to the highest-ranked coin. Respect the plan `per_page` cap
   (Free 100, Starter/Pro 250); exceeding it returns 422 `validation`, it does not clamp.
2. **Batch price reads.** `GET /api/v1/prices?slugs=bitcoin,ethereum` (`getPrices`) returns up to
   100 coins in one call — one request of quota total, the cheapest way to answer price questions.
   Add `convert=EUR` for fiat conversion.
3. **Single coin.** `GET /api/v1/prices/{slug}` (`getACoinPrice`) for one price, or
   `GET /api/v1/coins/{slug}` (`getCoinDetail`) for the full profile (supplies, rank, ATH/ATL,
   FDV, links, contracts).
4. **Parse prices as decimal strings.** Prices, rates, market caps and supplies are STRINGS
   (`"price": "63520.780763913"`) to preserve precision — never coerce to float for arithmetic;
   use a decimal type. Counts and percentage changes are JSON numbers.
5. **Watch quota headers.** Every response carries `X-Quota-Limit` / `X-Quota-Used` /
   `X-Quota-Reset`. On a `rate_limited` error, back off until the `X-Quota-Reset` instant.
   Unknown slug returns 404 with `{"error":{"code":"not_found"}}` — match on `error.code`.
