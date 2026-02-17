# Solana Market Makers & Funds — Address Directory

Curated list of **market maker and fund wallet addresses on Solana**, sourced from [Nansen](https://nansen.ai) API (65 tokens scanned), public on-chain reports, and Lookonchain data.

## 📊 Files

| File | Description |
|---|---|
| [`market_makers.csv`](./market_makers.csv) | Individual MM wallet addresses (11 addresses, 4 entities) |
| [`funds.csv`](./funds.csv) | VC/Fund wallet addresses (19+ addresses, 10 entities) |
| [`exchanges.csv`](./exchanges.csv) | Top exchange wallets on Solana (10 addresses) |
| [`entities.json`](./entities.json) | Aggregated entity holdings across 44 Solana tokens |

## 🏦 Market Makers (9 entities)

| Entity | Total Holdings | Tokens Active | Individual Addresses |
|---|---|---|---|
| **Galaxy Digital** | $131.9M | 10 | entity-level only |
| **Wintermute Market Making** | $9.4M | 26 | ✅ 2 addresses |
| **Jump Trading Market Making** | $2.15M | 15 | entity-level only |
| **Wintermute (OTC)** | $2.1M | 18 | ✅ 1 address |
| **Cumberland DRW** | $322K | 12 | entity-level only |
| **Jump Trading** | $99K | 6 | ✅ 5 addresses |
| **Alameda Research** | $40K | 2 | entity-level only |
| **DWF Labs** | $170 | 1 | ✅ 2 addresses |
| **Flowdesk** | $29 | 2 | entity-level only |

### Key Wintermute Addresses
\`\`\`
5sTQ5ih7xtctBhMXHr3f1aWdaXazWrWfoehqWdqWnTFP  — Primary MM wallet (confirmed ✅)
MfDuWeqSHEqTFVYZ7LoexgAK9dxk7cy4DFJWjWMGVWa   — Secondary MM wallet (confirmed ✅)
BMnT51N4iSNhWU5PyFFgWwFvN1jgaiiDr9ZHgnkm3iLJ  — OTC/Holdings wallet
\`\`\`

### Key Jump Trading Addresses
\`\`\`
GXbJWY8H5YwvhrRYZvSWUAcGMGjR7ygUkQNwZxefgzdm  — Jump Trading (USDC: $2.4M)
6v3snejEvRsTzeUZV2yKAcRgbxRz3iMJJgpeqJ1CxM6P  — Jump Capital
5pU7WKL47At6rHLM4CmFCSPRdT32J1LHSgPFhWGuXZqc  — Jump Capital
5CmWF9DMrcCtpuw3g1rnx9zYLX39bNwEX7dSEeaKFPPf  — Jump Capital
69GA1mJCEqyYxj57CCeamy2WGx7wM3ABEwuUFMmatu2d  — Jump Capital
\`\`\`

## 💰 Funds / VCs (19 entities)

| Entity | Total Holdings | Tokens | Addresses |
|---|---|---|---|
| **Jump Capital** | $3.43M | 7 | ✅ 5 addresses |
| **Sigil Fund** | $3.35M | 8 | ✅ 3 addresses |
| **Borderless Capital** | $1.64M | 7 | ✅ 2 addresses |
| **a16z** | $847K | 1 | entity-level only |
| **Hypersphere Ventures** | $224K | 1 | ✅ 1 address |
| **Defiance Capital** | $46K | 3 | ✅ 1 address |
| **LVT Capital** | $40K | 10 | ✅ 3 addresses |
| **Moonrock Capital** | $32K | 2 | ✅ 1 address |
| **Framework Ventures** | $28K | 1 | ✅ 1 address |
| **Infinity Ventures Crypto** | $15K | 2 | entity-level |
| **Master Ventures** | $10K | 2 | entity-level |
| **6th Man Ventures** | $7K | 1 | entity-level |
| **DevmonsGG** | $4K | 1 | ✅ 1 address |
| **Axia8 Ventures** | $3K | 1 | entity-level |
| **Kenetic Capital** | $2K | 3 | ✅ 1 address |
| **Folius Ventures** | $130 | 1 | entity-level |
| + 3 more small entities | | | |

## 🔧 Methodology

**65 Solana tokens scanned** via Nansen TGM Holders API across 3 waves:

**Wave 1 (10 tokens):** USDC, JUP, BONK, WIF, PYTH, W, ORCA, RAY, JTO, RNDR, PENGU

**Wave 2 (25 tokens):** mSOL, jitoSOL, DRIFT, TENSOR, INF, POPCAT, MEW, BOME, WEN, MOBILE, HONEY, GRASS, IO, RENDER, FARTCOIN, AI16Z, TRUMP, STEP, MNDE, SAMO, KMNO, PRCL, ZEUS, PNUT, TNSR

**Wave 3 (30 tokens):** USDT, JITO, HNT, MSOL, BSOL, LDO, LINK, NEON, SLND, MSRM, UXDO, BLZE, GMT, AUDIT, DFL, MPLX, NATIX, PARCL, ACCESS, TBTC, DUAL, SHDW, MEAN, C98, PORT, PRISM, GENE, SLIM, COPE, SBR

**Endpoints used:**
1. \`POST /api/v1/tgm/holders\` with \`aggregate_by_entity: true\` — entity discovery
2. \`POST /api/v1/tgm/who-bought-sold\` — individual address extraction
3. \`POST /api/beta/profiler/address/labels\` — label verification
4. \`POST /api/v1/smart-money/dex-trades\` — trade activity
5. \`POST /api/v1/smart-money/holdings\` — smart money token holdings
6. \`POST /api/v1/tgm/dex-trades\` — token-specific DEX trades
7. \`POST /api/v1/tgm/flows\` — token flow analysis

## 🔍 Notable Findings

- **Galaxy Digital** holds **$128M+ in jitoSOL** — massive Solana staking position
- **Wintermute** is the most active MM across **26 tokens** including $4.8M in FARTCOIN and $1.2M in TRUMP
- **Jump Trading MM** has $1.5M concentrated in **PYTH**
- **Alameda Research** (FTX) still has $40K in tokens (INF, SHDW)
- **Flowdesk** has minimal on-chain Solana presence ($29 total)

## ⚠️ Known Gaps

- **GSR Markets**: Not found via Nansen — may use unlabeled wallets or operate primarily via CEX
- **Keyrock, Auros, B2C2, FalconX, Amber Group**: Not detected across 65 tokens
- **Cumberland DRW, Galaxy Digital**: Entity-level data only, individual addresses unknown
- MMs often rotate wallets or use CEX APIs with no on-chain footprint

## 🔗 Additional Resources

- [Arkham Market Makers Dashboard](https://intel.arkm.com/explorer/entity/wintermute) (requires Arkham account)
- [Nansen API Docs](https://docs.nansen.ai)
- [Lookonchain](https://lookonchain.com) — on-chain MM tracking

## 📅 Data Snapshot

- **Date**: 2026-02-17
- **Nansen Credits Used**: ~15-18K
- **Tokens Scanned**: 65
- **Entities Found**: 28 (9 MMs + 19 Funds)
- **Individual Addresses**: 40+

## 📜 License

MIT — Data sourced from Nansen API (paid subscription). Use responsibly.
