# Solana Market Makers & Funds — Address Directory

Curated list of **market maker and fund wallet addresses on Solana**, sourced from [Nansen](https://nansen.ai) API (35 tokens scanned), public on-chain reports, and Lookonchain data.

## 📊 Files

| File | Description |
|---|---|
| [`market_makers.csv`](./market_makers.csv) | Individual MM wallet addresses (11 addresses, 4 entities) |
| [`funds.csv`](./funds.csv) | VC/Fund wallet addresses (19 addresses, 10 entities) |
| [`exchanges.csv`](./exchanges.csv) | Top exchange wallets on Solana (10 addresses) |
| [`entities.json`](./entities.json) | Aggregated entity holdings across 35 Solana tokens |

## 🏦 Market Makers

### Individual Addresses Found

| Entity | Addresses | Confirmed MM Tag | Total Holdings |
|---|---|---|---|
| **Wintermute** | 3 | ✅ (2 of 3) | $11.1M across 20+ tokens |
| **Jump Trading / Jump Capital** | 5 | ❌ (tagged as Fund) | $2.95M |
| **DWF Labs** | 2 | ❌ | Detected via activity |

### Entity-Level Only (no individual addresses)

| Entity | Total USD | Top Tokens |
|---|---|---|
| **Galaxy Digital** | $131.9M | jitoSOL ($128M), RNDR ($1.9M) |
| **Cumberland DRW** | $322K | PENGU, TRUMP, WIF, BONK |
| **Alameda Research** | $9.1K | INF |
| **Flowdesk** | $29 | GRASS, TRUMP |

## 💰 Funds / VCs

| Entity | Addresses | Total Holdings |
|---|---|---|
| **Sigil Fund** | 3 | $1.28M (mSOL, jitoSOL, HONEY) |
| **a16z** | entity-level | $847K (PNUT) |
| **Jump Capital** | 5 | $595K (DRIFT) + $743K (USDC/JUP) |
| **Borderless Capital** | 2 | $563K (jitoSOL, RENDER) |
| **Hypersphere Ventures** | 1 | $224K (USDC) |
| **Framework Ventures** | 1 | $28K |
| **Defiance Capital** | 1 | $17K |
| **Infinity Ventures Crypto** | entity-level | $15K (ZEUS) |
| **LVT Capital** | 3 | $31K |
| **Master Ventures** | entity-level | $10K |
| **Moonrock Capital** | 1 | $5K |
| **Axia8 Ventures** | entity-level | $3K |
| **Kenetic Capital** | 1 | $2K |

## 🔧 Methodology

**35 Solana tokens scanned** via Nansen TGM Holders API:

USDC, JUP, BONK, WIF, PYTH, W, ORCA, RAY, JTO, RNDR, PENGU, mSOL, jitoSOL, DRIFT, TENSOR, INF, POPCAT, MEW, BOME, WEN, MOBILE, HONEY, GRASS, IO, RENDER, FARTCOIN, AI16Z, TRUMP, STEP, MNDE, SAMO, KMNO, PRCL, ZEUS, PNUT

**Endpoints used:**
1. `POST /api/v1/tgm/holders` with `aggregate_by_entity: true` — entity discovery
2. `POST /api/v1/tgm/who-bought-sold` — individual address extraction
3. `POST /api/beta/profiler/address/labels` — label verification
4. `POST /api/v1/smart-money/dex-trades` — trade activity
5. `POST /api/v1/smart-money/holdings` — smart money token holdings

## ⚠️ Known Gaps

- **GSR Markets**: Entity exists on Arkham but Solana addresses not found via Nansen scans
- **Keyrock, Auros, B2C2, FalconX, Amber Group**: Not detected — may use unlabeled wallets or operate primarily via CEX/OTC
- **Cumberland DRW**: Entity-level data only, individual Solana addresses unknown
- **Galaxy Digital**: $130M+ in jitoSOL but individual addresses not exposed

### Why Some MMs Are Missing
Market makers often:
1. Use fresh/rotating wallets without persistent labels
2. Operate via CEX APIs (no on-chain footprint for MM activity)
3. Use custody solutions (Fireblocks, etc.) that obscure ownership
4. Have Solana activity under different entity names

## 🔗 Additional Resources

- [Arkham Market Makers Dashboard](https://intel.arkm.com/explorer/entity/wintermute) (requires login)
- [Nansen API Docs](https://docs.nansen.ai)
- [Lookonchain](https://lookonchain.com) — on-chain analysis with MM tracking

## 📅 Data Snapshot

- **Date**: 2026-02-17
- **Nansen Credits Used**: ~10-12K
- **Tokens Scanned**: 35

## 📜 License

MIT — Data sourced from Nansen API (paid subscription). Use responsibly.
