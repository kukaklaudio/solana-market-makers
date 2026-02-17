# Solana Market Makers — Address Directory

A curated list of known **market maker wallet addresses on Solana**, sourced from [Nansen](https://nansen.ai) proprietary labels, on-chain analysis, and public reports.

## 📊 Data

### [`market_makers.csv`](./market_makers.csv)

| Column | Description |
|---|---|
| `address` | Solana wallet address |
| `entity` | Parent company/entity name |
| `sub_label` | Specific Nansen label or sub-entity |
| `is_market_maker` | `true` if Nansen explicitly tags as "Market Maker" |
| `source` | Data source (nansen, lookonchain, arkham, etc.) |

### [`entities.json`](./entities.json)

Aggregated entity-level data showing token holdings and activity across major Solana tokens (JUP, BONK, WIF, PYTH, W, ORCA, RAY, JTO, RNDR, PENGU).

### [`exchanges.csv`](./exchanges.csv)

Top exchange wallets on Solana (Binance, Coinbase, Kraken, etc.) — useful for filtering exchange flow vs market maker flow.

## 🏦 Entities Covered

| Entity | Addresses | Nansen MM Tag | Notes |
|---|---|---|---|
| **Wintermute** | 3 | ✅ Yes | Primary + Secondary MM wallets, plus OTC wallet |
| **Jump Trading / Jump Capital** | 5 | ❌ No (tagged as "Fund") | Multiple wallets across trading + capital arms |
| **DWF Labs** | 1 | ❌ Not labeled | Detected via who-bought-sold activity |
| **Cumberland DRW** | Entity-level only | — | $232K across BONK, WIF, PYTH, RNDR, PENGU |
| **Galaxy Digital** | Entity-level only | — | $2M+ mostly in RNDR |

## 📈 Entity Holdings (Aggregate, via Nansen TGM)

From `aggregate_by_entity` scan across 10 major Solana tokens:

| Entity | Total USD | Top Tokens |
|---|---|---|
| Wintermute Market Making | $2,753,375 | JUP, W, BONK, PENGU, WIF |
| Galaxy Digital | $2,032,448 | RNDR ($1.9M), PYTH |
| Jump Trading Market Making | $1,676,375 | PYTH ($1.5M), JUP |
| Wintermute (OTC) | $603,484 | JUP, WIF, ORCA, BONK |
| Cumberland DRW | $231,802 | PENGU, WIF, PYTH |
| Jump Trading | $98,487 | W, RAY |

## ⚠️ Limitations

- **Nansen's "Market Maker" label** is rare — only Wintermute's MM wallets have it explicitly. Jump, Cumberland, GSR etc. are tagged as "Fund" or entity names.
- **GSR, Keyrock, Auros, Flowdesk, B2C2** were not found in the token holder scans — they may operate via different mechanisms (OTC, perps) or use unlabeled addresses.
- Addresses change over time. Market makers regularly rotate wallets.
- Entity-level data (`aggregate_by_entity`) does not expose individual addresses.

## 🔧 Methodology

1. **Nansen TGM Holders** (`/api/v1/tgm/holders`) — scanned 10 tokens with `aggregate_by_entity: true` to identify MM entities
2. **Nansen Who Bought/Sold** (`/api/v1/tgm/who-bought-sold`) — 7-day window across 10 tokens to find individual addresses
3. **Nansen Address Labels** (`/api/beta/profiler/address/labels`) — verified addresses and confirmed "Market Maker" tags
4. **Nansen Smart Money DEX Trades** (`/api/v1/smart-money/dex-trades`) — checked recent trades
5. **Public sources** (Lookonchain, Arkham, social media) — cross-referenced known addresses

## 🔑 Nansen API Notes

- Base URL: `https://api.nansen.ai/api/v1/` (v1 endpoints), `https://api.nansen.ai/api/beta/` (beta endpoints)
- Auth: `?apikey=YOUR_KEY` as query parameter
- The `aggregate_by_entity` parameter on TGM holders is the most efficient way to find MM entities
- The `address/labels` beta endpoint is the only way to confirm the "Market Maker" label
- Credits are consumed per request — plan queries carefully

## 📅 Last Updated

2026-02-17

## 📜 License

MIT — Data sourced from Nansen API (paid subscription required). Use responsibly.
