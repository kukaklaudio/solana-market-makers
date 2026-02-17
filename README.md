# Solana Market Makers & Institutional Wallets

Mapping market makers, funds, and institutional players on Solana using on-chain analytics.

## Data Sources
- **Nansen API** (paid, 30K credits) — Smart Money labels, entity aggregation, who-bought-sold, DEX trades, flow intelligence
- **Public disclosures** — Official wallet announcements (e.g., DWF Labs May 2025)
- **Arkham Intelligence** — Entity research (requires paid API for direct wallet extraction)

## Methodology
1. **Entity Scan (Phase 1)**: Scanned 65 Solana tokens via Nansen TGM holders with `aggregate_by_entity: true`
2. **Address Extraction (Phase 2)**: Used `who-bought-sold` endpoint with 30-day windows across tokens
3. **Label Verification (Phase 3)**: Cross-referenced via Nansen profiler and smart money labels
4. **Public Source Cross-reference (Phase 4)**: Web research for officially disclosed addresses
5. **MM Pattern Detection (Phase 5)**: Identified high-volume wallets with balanced buy/sell ratios (70-130%)

## Confirmed Market Makers on Solana

### Wintermute ✅ (3 wallets confirmed)
| Address | Role | 30d Volume |
|---------|------|-----------|
| `5sTQ5ih7xtctBhMXHr3f1aWdaXazWrWfoehqWdqWnTFP` | Primary MM | Major |
| `MfDuWeqSHEqTFVYZ7LoexgAK9dxk7cy4DFJWjWMGVWa` | Market Making | $413M+ (WETH alone) |
| `BMnT51N4iSNhWU5PyFFgWwFvN1jgaiiDr9ZHgnkm3iLJ` | OTC/Trading | $182M+ across 6+ tokens |

### DWF Labs ✅ (1 official + 2 suspected)
| Address | Role | Source |
|---------|------|--------|
| `HwDkuDCUipJHHKodBBCjffFvrjhmd4iVVh7fq25fShvt` | Secondary Market Purchases | Officially disclosed by Andrei Grachev (May 2025) |
| `B5dWf97VwfKumCT377Nh8rC51qoi7o5tYou3ZNzrR3P3` | Suspected MM | Nansen entity label |
| `DwF9w6BKa6aTRm5uGw92nN2PBsU2NV3fJv56MveTEu5R` | Suspected MM | Nansen entity label |

### Jump Trading / Jump Capital ✅ (5 wallets)
| Address | Entity | Notes |
|---------|--------|-------|
| `GXbJWY8H5YwvhrRYZvSWUAcGMGjR7ygUkQNwZxefgzdm` | Jump Trading | $2.4M USDC |
| `6v3snejEvRsTzeUZV2yKAcRgbxRz3iMJJgpeqJ1CxM6P` | Jump Capital | Fund wallet |
| `5pU7WKL47At6rHLM4CmFCSPRdT32J1LHSgPFhWGuXZqc` | Jump Capital | Fund wallet |
| `5CmWF9DMrcCtpuw3g1rnx9zYLX39bNwEX7dSEeaKFPPf` | Jump Capital | Fund wallet |
| `69GA1mJCEqyYxj57CCeamy2WGx7wM3ABEwuUFMmatu2d` | Jump Capital | Fund wallet |

## Unidentified High-Volume Wallets (Suspected MMs)

| Address | 30d Volume | Buy/Sell Ratio | Label |
|---------|-----------|----------------|-------|
| `YubFizptp3MXUAtZmqkRS9DyCkMeZaVwiaRCGBTxayo` | $610M (TRUMP) | 99% | "Trading Bot" — likely unlabeled MM |
| `4GQeEya6ZTwvXre4Br6ZfDyfe2WQMkcDz2QbkJZazVqS` | $6.9M (TRUMP) | 97% | "Token Millionaire" |

## MMs NOT Found on Solana (as of Feb 2026)

These major crypto market makers were searched but no labeled Solana wallets were found:

| Entity | Status | Notes |
|--------|--------|-------|
| **GSR Markets** | Arkham shows holdings (JTO $28M, RENDER $3.7M, TNSR $2.8M as of Oct 2024) but no Nansen labels | Likely uses unlabeled wallets |
| **Keyrock** | Not found | May operate primarily via CEX |
| **Auros** | Not found | May operate primarily via CEX |
| **B2C2** | Not found | OTC-focused, may not have on-chain presence |
| **FalconX** | Not found | May operate primarily via CEX |
| **Amber Group** | Not found | May operate primarily via CEX |
| **Cumberland/DRW** | Not found | OTC-focused, SEC lawsuit may have reduced on-chain activity |

## Institutional Funds Detected

Entities found via Nansen entity aggregation across 65 tokens:
- Galaxy Digital ($130M+ in jitoSOL)
- Alameda Research (defunct, residual holdings)
- Sigil Fund
- Borderless Capital
- Defiance Capital
- Moonrock Capital
- 6th Man Ventures
- LVT Capital
- Infinity Ventures Crypto

## Tokens Scanned (65 total)

### Wave 1-2 (35 tokens)
SOL, USDC, JUP, BONK, jitoSOL, JITO, PYTH, WIF, FARTCOIN, POPCAT, MEW, TRUMP, RAY, ORCA, MANGO, DRIFT, RENDER, TNSR, W, HNT, STEP, MNDE, WBTC, MSOL, BSOL, and more

### Wave 3 (30 tokens)
USDT, JITO, HNT, MSOL, BSOL, LDO, LINK, NEON, SLND, MSRM, UXDO, BLZE, GMT, AUDIT, DFL, MPLX, NATIX, PARCL, ACCESS, TBTC, DUAL, SHDW, MEAN, C98, PORT, PRISM, GENE, SLIM, COPE, SBR

## How to Use This Data

1. **Track MM activity**: Monitor confirmed addresses on [Solscan](https://solscan.io) or [Arkham](https://intel.arkm.com)
2. **Signal detection**: Large inflows/outflows from MM wallets can signal upcoming price movements
3. **Liquidity analysis**: Check which tokens MMs are actively trading

## Limitations

- Nansen's Solana entity coverage is limited compared to Ethereum
- Many MMs use unlabeled/rotating wallets on Solana
- Some MMs (GSR, Keyrock) are visible on Arkham but not extractable without paid API
- CEX-based market making is invisible on-chain
- Data is point-in-time (Feb 2026) — wallets may change

## Contributing

If you know of additional MM wallets on Solana, please open an issue or PR with evidence.

## License

MIT — data compiled from public blockchain analytics for research purposes.

## Smaller / Emerging Market Makers on Solana

Based on web research, these are active smaller MMs on Solana but their wallet addresses are not publicly labeled:

| Entity | Status | Notes |
|--------|--------|-------|
| **Gotbit** | CEO arrested (Oct 2024) | FBI sting operation; wallets likely seized; was major Solana memecoin MM |
| **Kairon Labs** | Active | Belgium-based; CEX-focused, minimal on-chain footprint |
| **Flowdesk** | Active | French MM; growing presence but no public Solana addresses |
| **Folkvang** | Active | Known for derivatives; limited Solana DEX activity |
| **Selini Capital** | Active | Smaller player; no public addresses |
| **Bastion Trading** | Active | OTC-focused |
| **CMS Holdings** | Active (VC/MM hybrid) | Investment + market making |

### Prop AMMs on Solana (On-chain Market Making)
From Figment research (Oct 2025):
- **SolFi** — proprietary AMM absorbing significant Solana volume
- **Humidifi** — prop AMM with lower slippage
- **Tessera V** — prop AMM with optimized routing

### Suspected Unlabeled MM Wallets
| Address | Evidence | Tokens | Volume |
|---------|----------|--------|--------|
| `YubFizptp3MXUAtZmqkRS9DyCkMeZaVwiaRCGBTxayo` | $610M vol, 99% balanced, "Trading Bot" label | TRUMP | $610M/30d |
| `4GQeEya6ZTwvXre4Br6ZfDyfe2WQMkcDz2QbkJZazVqS` | $6.9M vol, 97% balanced, "Token Millionaire" | TRUMP | $6.9M/30d |
| `CreQJ2t94QK5dsxUvYn5PJKpDHDRGizp58Rqho3aE2h3` | $7.2M vol, 98% balanced, "SOL Millionaire" | BOME | $7.2M/30d |
| `GJvewfRjqTUPtx6WsBSUnaFbdgXwgXnWfpDyLm65T4YA` | Appears in BONK + SPX with high balanced volume | BONK, SPX | $4M+/30d |
| `CvGgoUiELpSceMBLRgBJBkYxvELmvMoDc9eCefm9hhYZ` | $7.2M vol, 79% balanced on WETH | WETH | $7.2M/30d |
| `B21oTRzqWNLwfamqpfPjrq4F5jDLGEY1iVYoR7aGS7EB` | $4.6M vol, 85% balanced on WETH | WETH | $4.6M/30d |
| `Fe7SEekiKygziaEGVB6Jj2i88t8HSSPjVrUoE9N5TiN2` | SwissBorg wallet, 90% balanced | SPX | $0.3M/30d |

### Other Institutional Wallets Detected
| Address | Label | Notes |
|---------|-------|-------|
| `Fe7SEekiKygziaEGVB6Jj2i88t8HSSPjVrUoE9N5TiN2` | SwissBorg: Wallet | Swiss crypto bank |
