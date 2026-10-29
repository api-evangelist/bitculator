# Bitculator

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Modern cryptocurrency REST API providing programmatic read access to crypto market data including coins, prices, markets, exchanges, wallets, global market data, sentiment, indicators, liquidations, conversions, calculators, editorial content, alarms, and webhooks. Version 1.0.0 with 70+ endpoints across 15 groups.

**Areas:** Cryptocurrency · crypto-market-data · Blockchain · Finance · Fintech · Web3 · Trading · Exchange Data · Wallets · Sentiment · Indicators

## Bitculator on APIs.io

Everything profiled for Bitculator is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/bitculator/](https://apis.io/providers/bitculator/)** — or go straight to one of the APIs or properties below.

### APIs (15)

- [Bitculator Alarms API](https://apis.io/apis/bitculator/bitculator-alarms-api/) — Price-alarm CRUD — the same alarms the web app manages. Alarms consume the key owner's alarm inventory balance, are TARGET-type on coins only, and an…
- [Bitculator Calculators API](https://apis.io/apis/bitculator/bitculator-calculators-api/) — Server-side financial calculators mirroring the web tools: DCA, profit/loss and loan (which read cached market data), plus stateless compound-interest and…
- [Bitculator Coins API](https://apis.io/apis/bitculator/bitculator-coins-api/) — Ranked coin and token market data: paginated listings, single-coin detail, movers (gainers/losers), recently-added, trending, and per-coin time series.…
- [Bitculator Conversion API](https://apis.io/apis/bitculator/bitculator-conversion-api/) — Convert between any two active assets (crypto AND fiat), and list the currencies usable as conversion legs. Values are decimal strings. Fiat FX rates…
- [Bitculator Editorial API](https://apis.io/apis/bitculator/bitculator-editorial-api/) — Editorial articles — published (ACTIVE) only. `locale` picks the content language with per-field English fallback (the payload reports which `locale`…
- [Bitculator Exchanges API](https://apis.io/apis/bitculator/bitculator-exchanges-api/) — Exchange rankings, detail, trust scores, time series and per-exchange market/coin listings. Volumes are USD. There is no CEX/DEX column — `type` is derived…
- [Bitculator Global Market API](https://apis.io/apis/bitculator/bitculator-global-market-api/) — Market-wide aggregates — total marketcap and volume, asset/exchange/pair/market counts, BTC/ETH dominance with a rank-based top-3, the market Fear & Greed…
- [Bitculator Indicators API](https://apis.io/apis/bitculator/bitculator-indicators-api/) — Per-coin technical indicators. Each indicator is its own dedicated endpoint — momentum oscillators (RSI, Stoch-RSI, CCI, MFI, Williams %R), trend and price…
- [Bitculator Liquidations API](https://apis.io/apis/bitculator/bitculator-liquidations-api/) — Derivatives liquidations. Source coverage is currently OKX swap markets only (stated in every `meta.note`). The RAW feed (the `/liquidations` list and the…
- [Bitculator Markets API](https://apis.io/apis/bitculator/bitculator-markets-api/) — Tickers (per-exchange markets) and pairs (venue-aggregated markets), plus a coin's markets and raw per-exchange trading symbols. All of it is snapshot data…
- [Bitculator Meta API](https://apis.io/apis/bitculator/bitculator-meta-api/) — API meta and introspection: an authenticated ping to verify a key and the middleware stack, current-key usage/quota, and the machine-readable OpenAPI spec.
- [Bitculator Prices API](https://apis.io/apis/bitculator/bitculator-prices-api/) — The lightweight price hot path — current price, marketcap, 24h volume and recent changes for a requested set of coins. `/prices` requires a selector (ids,…
- [Bitculator Sentiment API](https://apis.io/apis/bitculator/bitculator-sentiment-api/) — Market and per-coin sentiment indices. Fear & Greed and Bull/Bear are 15-minute-refresh SNAPSHOTS — only the current reading exists, there is no time series…
- [Bitculator Wallets API](https://apis.io/apis/bitculator/bitculator-wallets-api/) — Crypto wallet reviews — review `score`, supported-asset count, pros/cons counts, price model and release date, plus a grouped tag taxonomy on detail/compare…
- [Bitculator Webhooks API](https://apis.io/apis/bitculator/bitculator-webhooks-api/) — Bitculator POSTs each event as JSON with an HMAC signature header: X-Bitculator-Signature: t=<unix-ts>,v1=<hex hmac_sha256("<ts>.<raw-body>", secret)>…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Bitculator Webhooks](https://apis.io/asyncapis/bitculator/bitculator-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Bitculator MCP Server](https://apis.io/servers/bitculator/bitculator-mcp-server/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Bitculator Data Api Overlay](https://apis.io/overlays/bitculator/bitculator-data-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Bitculator Authentication](https://apis.io/security/bitculator/bitculator-authentication/)
- [Bitculator Domain Security](https://apis.io/security/bitculator/bitculator-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Bitculator Plans Pricing](https://apis.io/plans/bitculator/bitculator-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Bitculator Rate Limits](https://apis.io/rate-limits/bitculator/bitculator-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.bitculator.com/)
- [Pricing](https://bitculator.com/en/crypto-api)
- [Sign up](https://bitculator.com/en/register)
- [Support](https://bitculator.com/en/contact)
- [Terms of service](https://bitculator.com/en/terms-of-service)
- [Privacy policy](https://bitculator.com/en/privacy-policy)
- [GitHub](https://github.com/Bitculator)

## API Evangelist rating

**Kin Score 51.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 53.3 |
| Contract governance | 4.5 |
| Operational transparency | 42.1 |
| Developer ergonomics | 47.0 |
| Access clarity | 76.3 |

**Agent readiness 36.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 22.3** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/bitculator/](https://apis.io/providers/bitculator/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Bitculator: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/bitculator/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
