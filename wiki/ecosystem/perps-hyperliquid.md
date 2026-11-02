# Hyperliquid: the perps exchange that became its own chain

> Sources: Oak Research, 2025-08; NewsBTC via TradingView, 2025-05-27; Binance Square, 2025-08-27; VanEck, late 2025; Bankless, 2025-12-10; Bitsgap, 2026; ryder.id, 2026-07; eco.com, 2026; Binance Square, 2026-06-03; SSRN, 2026-08-27; CoinGecko, 2026; DefiLlama, 2026-11-02; verify pass, 2026-11-02
> Raw: [brief](../../raw/use-cases/2026-11-02-crypto-use-cases-competitive-brief.md); [verify report](../../raw/use-cases/2026-11-02-verify-report-use-cases-brief.md)
> Updated: 2026-11-02

## Overview

Hyperliquid is a decentralized exchange for **perpetual futures** ("perps") running on its own purpose-built L1 blockchain — and in 2025–2026 it became the fastest-growing trading venue in crypto. It matters to this curriculum twice over: it is the strongest evidence that a single killer app can *be* the chain (validating Avalanche's appchain thesis), and it is proof that Avalanche lost the trading-venue race anyway. This article covers the architecture, the dated volume milestones (with the verify-corrected full-year number), the HYPE token story, and the honest Avalanche comparison.

## Perps in plain language

**Perpetual futures ("perps")** are leveraged bets on price moves that never expire. Unlike a normal futures contract with an end date, a perp just keeps running — traders put up collateral and win or lose as the price moves, up to the exchange's leverage cap (on Hyperliquid, up to **~25x**). Perps are crypto's highest-revenue product because active traders pay fees constantly.

## One network, two halves: HyperCore and HyperEVM

Hyperliquid runs **two halves in one network**:

- **HyperCore** — the on-chain order-book trading engine where the actual perp trading happens (up to ~25x leverage).
- **HyperEVM** — an EVM-compatible environment (the same tech family as Avalanche's C-Chain), launched in **early 2025** so other apps can build around the exchange (confirmed per verify pass 2026-11-02).

Trading is **gasless for users** — traders don't pay per-transaction gas the way C-Chain users do. The result feels like a centralized exchange (CEX) but with self-custody.

## Volume milestones (with verify corrections)

| Date | Milestone |
|---|---|
| Q4 2024 | Weekly volume ~**$13B** |
| H1 2025 | Average weekly volume ~**$47B** (Oak Research, Aug 2025) |
| **May 21, 2025** | Record single day: **$17.7B** traded |
| Q2 2025 | **$648B** quarterly volume; **$86.6M** revenue (Binance Square, Aug 27, 2025) |
| Full-year 2025 | ≈**$2.7–3.0T** volume — **$2.74T** YTD as of Dec 11, 2025; $2.95T per ASXN year-end data (**per verify pass 2026-11-02**) |
| 2025 (year) | On-chain DEX share of perp trading tripled from **6.42% → 24.3%**; **>$650M** revenue, **#4 in all of crypto**; at times ~70% of the category |
| Q1 2026 | **$633B** in the quarter alone (perps + spot, per VanEck) — this is what the "$633B" figure actually measures (**per verify pass 2026-11-02**) |
| **April 2026** | 30-day perp volume **>$180B** — more than every other on-chain venue combined (Bitsgap) |

> **The biggest correction in the brief:** "~$633B full-year 2025" was **REFUTED** — VanEck's $633B is **Q1 2026** volume, not FY2025 (the brief's own Q2-2025 citation of $648B in one quarter gave it away). Full-year 2025 was roughly **$2.7–3.0T** — several times the quarterly figure. Never quote $633B as an annual figure.

## How big is the lead? (market share, with caveats)

- Hyperliquid ended 2025 with **~56% of all decentralized perp volume** (Oak Research, Dec 5, 2025 update; Bitget & Ainvest, Dec 11, 2025) — **verified but contested** per verify pass 2026-11-02: some trackers showed only **17–20%** in Nov 2025 (rival venues Aster/Lighter counted incentive volume), and DefiLlama Pro showed a 70% → 10% (Sept 2025) → 44% (May 2026) swing depending on methodology.
- The cleaner metric per the verify pass: **open-interest share of ~59–63%** (open interest = the total value of positions currently open).
- ⚠️ **Unverified:** a Hyperliquid X post (late 2026) cited **$2.6B open interest in RWA perps** — tokenized stocks/commodities traded 24/7. Not confirmed by the verify pass; treat as unconfirmed before repeating.

## The HYPE token story

| Date | Event |
|---|---|
| **Nov 29, 2024** | Genesis airdrop: **310M HYPE (~31% of supply)** to **~94K wallets**, **no VC allocation** — the largest airdrop ever, worth ~**$12B at peak** |
| **Sept 10, 2025** | Market cap reached **$18.3B** (rank #11 on CoinMarketCap) |
| **June 2026** | A spot HYPE ETF absorbed **1.04% of market cap in its first 10 trading days** |
| **Aug 2026** | Cumulative protocol fees **>$1.51B** (verify pass: DefiLlama sums to **$1.535B through Aug 31, 2026**) |
| **Sept 23, 2026** | All-time high **$97.96** (CoinGecko; Coinbase printed $97.99, Gate $98.00 the same day) |

The key mechanism: **revenue funds the token via buybacks** — Hyperliquid's trading fees literally buy back HYPE. Compare with Avalanche, where chain fees are burned but there is no exchange revenue engine behind AVAX.

## Why it's the fastest-growing venue in crypto

Four reinforcing choices (per the brief):

1. **It proved a single killer app can BE the chain** — no general-purpose platform, just the exchange, with its own L1 underneath.
2. **Revenue funds the token via buybacks** — users' fees flow to holders.
3. **No gas for traders** — the exchange subsidizes execution.
4. **CEX-like speed with self-custody** — the feel of Binance, the ownership model of DeFi.

## The Avalanche comparison

The uncomfortable, honest framing: **Hyperliquid is not built on Avalanche.** It validates Avalanche's appchain thesis (app-specific chains can win huge) while demonstrating Avalanche lost the trading venue race. The lineage note: **GMX** — the perp pioneer — launched on Arbitrum in late 2021 and expanded to Avalanche in 2022; Hyperliquid later eclipsed it.

| Metric (date) | Hyperliquid | Avalanche |
|---|---|---|
| Token market cap | HYPE peak **$18.3B** (Sept 10, 2025) | AVAX **$3.83B** (Nov 2, 2026, per verify pass; brief's $3.8B refreshed) |
| Token price | HYPE ATH **$97.96** (Sept 23, 2026) | AVAX **$8.62** (Nov 2, 2026, per verify pass) |
| Fees | **>$1.51B cumulative** (Aug 2026) | ~**$11K per day** chain fees (Nov 2, 2026) |
| L1 TVL | **$2.62B** | **$584.0M**, rank #12 (Nov 2, 2026) |

The newer "appchain" token outweighs the older general-purpose one by roughly **5x** — the single clearest lesson in the "app = chain" debate. For the full competitive picture, see [the scoreboard](competitive-scoreboard.md).

## See Also

- [What people actually use blockchains for](use-cases-2026.md) — the Module 3 anchor this article belongs to
- [Memecoins and launchpads](memecoins-launchpads.md) — pump.fun briefly out-earned Hyperliquid ($33.7M vs $32.7M over 30 days, 2026)
- [Avalanche vs the field: the late-2026 scoreboard](competitive-scoreboard.md) — where this comparison sits in Module 11
- [L1s after Etna](../avalanche/l1s-after-etna.md) — Avalanche's own "app = chain" machinery
- [Gas in the dynamic era](../avalanche/dynamic-gas.md) — why Hyperliquid's "gasless trading" is a design choice, not magic
